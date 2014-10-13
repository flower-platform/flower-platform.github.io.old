---
layout: page
group: subconcept
parent-id: dev-doc

title: "Adding Libraries for a Plugin"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

Third-party libraries may be added to the bundle classpath in the ``MANIFEST.MF`` file of a project and must be included in the project. This can get tricky for libraries that also depend on other libraries, as you need to make sure that everything on their dependency tree is included at runtime. This guide will show how to manage bundle dependencies in the IDE using Maven.

<!-- more -->

## Manage Maven dependencies

For dependencies that are available via Maven (e.g. Central Repository, local repository), there is an easy way out, namely the [*dependency:copy-dependencies* goal](http://maven.apache.org/plugins/maven-dependency-plugin/copy-dependencies-mojo.html).

<span class="badge">1</span> Create the ``lib-from-maven-pom.xml`` file in your project. Fill in the groupId, artifactId and version; however, these are not important and are only there to avoid runtime errors.

<span class="badge">2</span> Now the important part: the dependencies. **Add the dependencies** you want to include in your bundle classpath; transitive dependencies will also be downloaded. Of course, you can use exclusions to exclude certain transitive dependencies.

<div markdown="1" class="alert alert-info">
In this example, we have added the *jersey-media-json-jackson* library, and the *jersey-container-servlet* library. Maven will download both libraries and **all** their dependencies, **except** *javax.ws.rs-api*, as it was explicitely excluded.

	<dependencies>
		<dependency>
			<groupId>org.glassfish.jersey.media</groupId>
			<artifactId>jersey-media-json-jackson</artifactId>
			<version>2.11</version>
		</dependency>
		
		<dependency>
			<groupId>org.glassfish.jersey.containers</groupId>
			<artifactId>jersey-container-servlet</artifactId>
			<version>2.11</version>
			<scope>provided</scope>
			<exclusions>
				<exclusion>
					<!-- this dependency comes from .util -->
					<!-- to avoid class loader problems -->
					<groupId>javax.ws.rs</groupId>
					<artifactId>javax.ws.rs-api</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
	</dependencies>
</div>

<span class="badge">3</span> Now that we have our dependencies declared in the POM file, we will **download the JARs** using ``dependency:copy-dependencies``, either from the command line, or running the ``clean-and-copy-maven-deps`` target in Eclipse. The target relies on the ``project_loc`` variable; make sure you select any file inside your project (or the project itself) and run the ``FP Clean and Copy Maven Deps.launch``, available in the ``/org.flowerplatform.build/launch_configs`` folder. The dependencies will be downloaded to the ``lib-from-maven`` folder inside your project; for the example above, more than 15 JARs were downloaded, which would have been difficult to handle by hand.

<div markdown="1" class="alert alert-warning">
This operation must be repeated every time a dependency is added, removed or modified (i.e. version upgrade). The ``lib-from-maven`` folder will be deleted before each run, so make sure not to modify any of the libraries.
</div>

<span class="badge">4</span> You can now **add the libraries to the bundle classpath**.

<div markdown="1" class="alert alert-warning">
Warning: after adding a library to the bundle classpath, make sure to add the ``.`` entry as well, to allow loading your classes from the root of the bundle.
</div>

## Modifying libraries

While generally not advisable, there may be cases when you need to modify a third-party library. In this case, do **not** use Maven to manage your library, as it will be overwritten every time the ``lib-from-maven-pom.xml`` is modified and run. Instead, copy the modified version to a ``lib`` folder inside the project. Make a note that the library is modified in the readme file of the project, to avoid accidentally deleting the file.