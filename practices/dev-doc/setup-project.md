---
layout: page
group: subconcept
parent-id: dev-doc

title: "Creating a New Plugin"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

**Flower Platform** is a modular application and runs in an Eclipse Equinox container: there is a **core** component and several **extensions**, i.e. one or more OSGi plugins that are dynamically loaded at runtime. See how to **setup** and **run** a new plugin project inside Flower Platform.

<!-- more -->

A new project can easily be created, configured and built from the IDE (e.g. Eclipse, Flash Builder). Additionally, Flower Platform is compiled and packaged with [Maven](http://maven.apache.org/), as described in the [build documentation](build.html), so the projects also need to be configured for the Maven build.

## Creating a new Java plugin

### IDE setup

<span class="badge">1</span> **Create a new project as an Eclipse plugin project**. In the ``MANIFEST.MF`` file, set is as a singleton plugin, and enable activation only when one of its classes is loaded. The activator class may extend ``AbstractFlowerJavaPlugin``.

<span class="badge">2</span> **Import library dependencies** as described [here](add-libs.html). 

<span class="badge">3</span> To add the new project to Flower Platform, **add the plugin to the Eclipse product configuration**, located at ``/org.flowerplatform.product/flowerplatform.product``, with **default start level** and **auto-start enabled**. Make sure to also add all the project's plugin dependencies. Then, [run the product file](setup-dev-environment.html#product-run). The next time you run the server, the new project will be included.

<div markdown="1" class="alert alert-warning">
If there are any errors starting the server (e.g. missing classes, activation errors), then:

 - Check if all the plugin dependencies were added to the product configuration
 - Check if there are any exceptions thrown during plugin activation
</div>

### Maven setup

<span class="badge">4</span> The Java build is a multi-module build (i.e. reactor), rooted at ``/org.flowerplatform.build/java/`` that aggregates our plugins. To add a new plugin to the reactor, first **create a POM file**. This is what a basic POM looks like:

	<?xml version="1.0" encoding="UTF-8"?>
	<project xmlns="http://maven.apache.org/POM/4.0.0"
	    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
		<modelVersion>4.0.0</modelVersion>
		
		<parent>
			<relativePath>../org.flowerplatform.build/java/pom.xml</relativePath>
			<groupId>org.flowerplatform</groupId>
			<artifactId>parent-java</artifactId>
			<version>0.1.1.qualifier</version>
		</parent>
	
		<artifactId>org.flowerplatform.core</artifactId>
		<packaging>eclipse-plugin</packaging>
	</project>
	
POM description:

 - Set ``parent-java`` as the parent module.
 - Set the packaging type to Tycho's ``eclipse-plugin``.
 - The artifact ID **must** be the plugin's name as declared in the MANIFEST file, as per Tycho requirements.

<div markdown="1" class="alert alert-info">
Notice how the plugin's dependencies do **not** have to be set in the POM, as Tycho uses the Eclipse configuration to get the dependencies.
</div>

<span class="badge">5</span> **Add the project to ``parent-java``.** Simply add it to the list of modules in the ``java-base`` profile like this:

	<module>../../org.flowerplatform.name.of.project</module>

Note that the path is relative to the ``/org.flowerplatform.build/java/`` directory.

<span class="badge">6</span> The version declared in the MANIFEST.MF file must match the application version declared in the ``org.flowerplatform.build/build.properties`` file, e.g. for version ``0.1.1``, set the plugin version to ``0.1.1.qualifier``. This way, the plugin will be suffixed with the timestamp when the build was performed.

## Creating a new Flex plugin

### IDE setup

<span class="badge">1</span> A **Flex plugin** is both an Eclipse plugin and a Flex library at the same time, so first **create a new Eclipse plugin as described above**.

<span class="badge">2</span> Import the project into Flash Builder and **add Flex library nature**.

<span class="badge">3</span> Flex configuration: 

1. Set the output path to ``public-resources/swc``; this is were the SWC file will be downloaded from at runtime.
2. Configure the library path. Third-party ibraries may be copied into the ``lib`` directory and will be merged into the application. Flower Platform plugins **must** be linked as external; they will be loaded into memory at runtime. For Flash Builder, this means setting the link type to ``external`` (see [Set the SWC file as an external library file](http://help.adobe.com/en_US/Flex/4.0/UsingFlashBuilder/WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7fe6.html#WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7f7a)). This is the equivalent of the ``external-library-path`` compiler option.
3. Create an **activator**, i.e. a class that extends ``AbstractFlowerFlexPlugin``, where you can perform initializations. After the plugin is loaded, the activator is located and its ``start()`` method is invoked. By default, the activator is located in the base package and borrows the name of the project, e.g. for the ``org.flowerplatform.flex_client.core``, the activator is ``org.flowerplatform.flex_client.core.CorePlugin``. 

<span class="badge">4</span> To **include the new plugin into the Flex application**, add the plugin path to the ``\org.flowerplatform.flex_client.host_app.config.web\WebContent\flexHostAppConfig.js`` configuration file, so the SWF file will be loaded at runtime. This is also the place where the activator name can be overwritten using an URL parameter, e.g. ``?pluginClass=CodeSyncRegexPlugin``.

This is what the ``flexHostAppConfig.js`` looks like with some projects:
	
	flashvars.pluginUrls = 					
		'servlet/public-resources/org.flowerplatform.flex_client.core/swc/org.flowerplatform.flex_client.core.swc|library.swf,' + 
		'servlet/public-resources/org.flowerplatform.flex_client.properties/swc/org.flowerplatform.flex_client.properties.swc|library.swf,' + 	
		'servlet/public-resources/org.flowerplatform.flex_client.mindmap/swc/org.flowerplatform.flex_client.mindmap.swc|library.swf?pluginClass=MindMapPlugin';

### Maven setup

<span class="badge">5</span> As an Eclipse plugin, the project must also be added to the Tycho build as described above.

<span class="badge">6</span> The Flex build is also a reactor, rooted at ``/org.flowerplatform.build/flex/``, that aggregates our Flex plugins. Since we already have a POM file used for the Java build, we need another POM file for the Flex build, and we add it to the ``flex-pom`` directory in our project, rather than the root of the project, because Tycho does not support multiple modules in the same directory.

This is what a basic POM looks like:

	<?xml version="1.0" encoding="UTF-8"?>
	<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
		xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
		<modelVersion>4.0.0</modelVersion>
	
		<parent>
			<relativePath>../../org.flowerplatform.build/flex/pom.xml</relativePath>
			<groupId>org.flowerplatform</groupId>
			<artifactId>parent-flex</artifactId>
			<version>0.1.1_flex</version>
		</parent>
	
		<artifactId>org.flowerplatform.flex_client.core</artifactId>
		<packaging>swc</packaging>
	
		<dependencies>
			...
		</dependencies>
	</project>

POM description:

 - Set ``parent-flex`` as the parent module.
 - Set the packaging type to Flexmojos' ``swc``.
 
<div markdown="1" class="alert alert-warning">
Unlike the Tycho build, where the dependencies are extracted from the Eclipse setup, the Flex dependencies **must** be duplicated in the POM file. The link type must also match the one configured in the IDE configuration, and will be set in the ``scope`` tag for each dependencies. Here is a rundown of some possible dependencies:

Flex SDK - notice the POM packaging type.

	<dependency>
		<groupId>org.apache.flex.framework</groupId>
		<artifactId>flex-framework</artifactId>
		<version>${flexVersion}</version>
		<type>pom</type>
	</dependency>

Flex SDK + AIR framework - notice the exclusion.

	<dependency>
		<groupId>org.apache.flex.framework</groupId>
		<artifactId>flex-framework</artifactId>
		<version>${flexVersion}</version>
		<type>pom</type>
		<exclusions>
			<!-- exclude playerglobal for the classes from the AIR framework to be compiled -->
			<exclusion>
				<groupId>com.adobe.flash.framework</groupId>
				<artifactId>playerglobal</artifactId>
			</exclusion>
		</exclusions>
	</dependency>

	<dependency>
		<groupId>com.adobe.air.framework</groupId>
		<artifactId>airglobal</artifactId>
		<version>3.2</version>
		<type>swc</type>
		<scope>merged</scope>
	</dependency>	

Third-party library - SWC type and **merged** scope; this matches the merged into code linking type.

	<dependency>
		<groupId>com.google.code.stagewebviewbridge</groupId>
		<artifactId>stagewebviewbridge</artifactId>
		<version>1.0</version>
		<type>swc</type>
		<scope>merged</scope>
	</dependency>

Flower Platform project - SWC type and **external** scope; this matches the external linking type.

	<dependency>
		<groupId>org.flowerplatform</groupId>
		<artifactId>org.flowerplatform.flexutil</artifactId>
		<version>${project.version}</version>
		<type>swc</type>
		<scope>external</scope>
	</dependency>

</div>

<span class="badge">7</span> **Add the project to ``parent-flex``.** Simply add it to the list of modules in the ``flex-base`` profile like this:

	<module>../../org.flowerplatform.flex_client.core/flex-pom</module>

Note that the path is relative to the ``/org.flowerplatform.build/flex/`` directory.
 