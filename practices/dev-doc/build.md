---
layout: page
group: subconcept
parent-id: dev-doc

title: "Building Flower Platform"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

The Flower Platform build process was made to be as painless as possible. It compiles the Flex and Java source code, packages the Eclipse product bundled with all our plugins and packages a WAR that can then be deployed to a server. For the Java build, we use [Tycho](https://www.eclipse.org/tycho/) to integrate Maven with the OSGi architecture. For the Flex build, we use [flexmojos](https://flexmojos.atlassian.net/wiki/display/FLEXMOJOS/Home).

<!-- more -->

Most build phases can easily be run from the [Ant[(http://ant.apache.org/) script, ``org.flowerplatform.build/build.xml``; build properties can be tweaked from the ``org.flowerplatform.build/build.properties`` file, e.g. version numbers, platform target, output directories. Machine-dependent or confidential properties (e.g. Maven installation location, keystore and password for the mobile APK packaging) may and should be stored in ``DO_NOT_COMMIT/build.properties.local``.

<span class="badge">1</span> **(One-time operation) Mavenize and install the Flex SDK in the local repository.** Flexmojos will then use these artifacts during the Maven build. A mavenized FDK can be easily created and installed using the [mavenizer tool](http://flex.apache.org/download-utilities.html) provided by Apache.

How to mavenize your FDK, as described [here](https://cwiki.apache.org/confluence/display/FLEX/Apache+Flex+SDK+Mavenizer):

1. Check-out the utilities project from: https://git-wip-us.apache.org/repos/asf/flex-utilities.git. It should contain a ``mavenizer`` dir.
1. In ``mavenizer``, run ``mvn package`` (or build using the m2 plugin in Eclipse). A jar (e.g. ``flex-sdk-converter-1.0.0-SNAPSHOT.jar``) will be generated in ``mavenizer/target``.
1. Create a ``mavenizer/target/flex-sdk`` directory. Within this dir:
	* Create a ``flex`` directory, and copy your Flex SDK(s) there. E.g. ``mavenizer/target/flex-sdk/flex/4.11.0``.
	* [OPTIONAL] Create an ``air`` directory, and copy your AIR SDK(s) there (optional; probably your SDK already has AIR embeded).
1. In ``mavenizer/target`` directory, run:

	java -cp flex-sdk-converter-1.0.0-SNAPSHOT.jar SDKGenerator flex-sdk flex-sdk-mavenized true

And then deploy the artifacts to your local repository: 

	java -cp flex-sdk-converter-1.0.0-SNAPSHOT.jar SDKInVMDeployer flex-sdk-mavenized file:\\%USERPROFILE%\.m2\repository

<span class="badge">2</span> **(One-time operation) Install extra Flex dependencies.** Some of our Flex projects depend on various libraries packaged as ``.swc``; flexmojos requires that these libraries must also be available in a Maven repository.

We use the [Maven _install_ plugin](http://maven.apache.org/plugins/maven-install-plugin/) to install these libraries in the local repository. There is already an Ant target that will install all the libraries needed by our Flex plugins: ``install-flex-deps``. It must be run once per machine, and then updated and run every time a library is added, removed or modified.

<span class="badge">3</span> **Update license headers.** Make sure that all the source files have the license header. Ant target: ``update-license-header``.

<span class="badge">4</span> **Update version numbers.** If needed, the version numbers may be changed in the ``build.properties`` file. The ``set-version`` Ant target will then update the version numbers throughout the projects: ``pom.xml`` files, ``MANIFEST.MF`` files, Java and Flex constants.

The output WAR and Eclipse plugins will be suffixed with the version number and timestamp of the build, e.g. ``0.1.1.v20141030-1345``.

<span class="badge">5</span> **Run the build script.** We use an Ant target to easily pass properties (e.g. output folders, version numbers) and run the Maven build.

The Maven buidl is a multi-module build:

* **flex/pom.xml**: multi-module build that aggregates the Flex libraries. Output directories: ``flex/classes`` and ``flex/distr``. The resulting ``swc`` files will be copied to the ``public-resources/swc`` directory of the corresponding Eclipse plugin.
* **java/pom.xml**: multi-module build that aggregates the Flower Platform plug-ins, the product project and test project.  Output directories:
	* ``java/classes`` - compiled classes
	* ``java/distr`` - ``.jar`` files
	* ``java/product`` - Eclipse product; will be contained in the WAR.
	* ``java/tests`` - test reports
* **../org.flowerplatform.host.web_app/war-pck**: builds the WAR to be deployed on the server.
* **pom.xml**: aggregates all the modules above

### Limitations

Since Tycho does not support multiple modules in the same base directory, we were forced to have our parent pom files in the ``flex`` and ``java`` sub-directories, instead of having all three files (parent, parent-flex and parent-java) in the project root.

Also, for modules that participate in both builds, (i.e. packaged as both ``eclipse-plugin`` and ``swc``), the pom file for the Java build stays in the project root, per Tycho requirement, and the pom file for the Flex build stays in the ``flex-pom`` sub-directory, for the same reason stated above.
