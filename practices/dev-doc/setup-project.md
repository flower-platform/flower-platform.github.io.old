---
layout: page
group: subconcept
parent-id: dev-doc

title: "Project Setup"
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

## IDE setup

### Eclipse plugin setup

First we create a new project as an **Eclipse plugin** project. It should be a singleton plugin, and should be activated when one of its classes is loaded. The activator class may extend ``AbstractFlowerJavaPlugin``.

To add our new project to Flower Platform, we add the plugin and all its dependencies to the Eclipse product configuration, located at ``/org.flowerplatform.product/flowerplatform.product``, with the **default start level** and **auto-start enabled**. Then, we need to [run the product file](setup-dev-environment.html#product-run). The next time we run the server, our new project will be included.

<div markdown="1" class="alert alert-warning">
If there are any errors starting the server (e.g. missing classes, activation errors), then:

 - Check if we added all the dependencies to the product configuration
 - Check if there were any exceptions thrown during plugin activation
</div>

### Flex plugin setup

A **Flex plugin** is an Eclipse plugin (i.e. it is included in the Eclipse product by following the steps above), and a Flex library at the same time.

To include our new plugin into the Flex application, we add the plugin to the ``\org.flowerplatform.flex_client.host_app.config.web\WebContent\flexHostAppConfig.js`` configuration file, so the SWF file will be loaded at runtime. We set the output path to ``public-resources/swc``, that is were the SWC file will be downloaded from. 

Our plugin is expected to declare an **activator**, i.e. a class that extends ``AbstractFlowerFlexPlugin``; after the plugin is loaded, the activator is located and its ``start()`` method is invoked. By default, the activator is located in the base package and borrows the name of the project, i.e. for the ``org.flowerplatform.flex_client.core``, the activator is ``org.flowerplatform.flex_client.core.CorePlugin``. The name of the plugin can be overwritten in the configuration file, e.g. ``?pluginClass=CodeSyncRegexPlugin``.

This is what the ``flexHostAppConfig.js`` looks like for some projects:
	
	flashvars.pluginUrls = 					
		'servlet/public-resources/org.flowerplatform.flex_client.core/swc/org.flowerplatform.flex_client.core.swc|library.swf,' + 
		'servlet/public-resources/org.flowerplatform.flex_client.properties/swc/org.flowerplatform.flex_client.properties.swc|library.swf,' + 	
		'servlet/public-resources/org.flowerplatform.flex_client.mindmap/swc/org.flowerplatform.flex_client.mindmap.swc|library.swf?pluginClass=MindMapPlugin';

All the plugins added to the configuration will be loaded at runtime, so they should **not** be merged into the application file. With Flash Builder, we need to set the link type for our libraries as ``external`` (see [Set the SWC file as an external library file](http://help.adobe.com/en_US/Flex/4.0/UsingFlashBuilder/WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7fe6.html#WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7f7a)). This is the equivalent of the ``external-library-path`` compiler option.
		
## Automatic build setup

Flower Platform is built via an [Ant](http://ant.apache.org/) + [Maven](http://maven.apache.org/) script, using [Tycho](http://www.eclipse.org/tycho/) for the Java build, to integrate Maven with the OSGi technology, and [Flexmojos](https://flexmojos.atlassian.net/wiki/display/FLEXMOJOS/Home) for the Flex build. The build output is an Eclipse product bundled with all our plugins, packaged in a ``war`` file that can be deployed to a server.

### Eclipse plugin setup

The Java build is a multi-module build (i.e. reactor), rooted at ``/org.flowerplatform.build/java/`` that aggregates our plugins. To add our new plugin to the reactor, first we need to create a POM file for our project. Then:

 - We declare the parent module in our POM, and add our project to the parent's list of modules.
 - We set the packaging type to Tycho's ``eclipse-plugin``.
 - The artifact ID **must** be the plugin's name, as per Tycho requirements.
 - We set the plugin version in the ``MANIFEST.MF`` file to match the version from the build properties, e.g. for version ``0.1.1``, set the plugin verstion to ``0.1.1.qualifier``.

This is what a basic POM looks like:

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
	
		<artifactId>org.flowerplatform.mindmap</artifactId>
		<packaging>eclipse-plugin</packaging>
	</project>

<div markdown="1" class="alert alert-info">
Notice how the plugin's dependencies do **not** have to be set in the POM, as Tycho uses the Eclipse configuration to get the dependencies.
</div>

### Flex plugin setup

The Flex build is also a reactor, rooted at ``/org.flowerplatform.build/flex/``, that aggregates our Flex plugins. Since we already have a POM file used for the Java build, we need another POM file for the Flex build, and we add it to the ``flex`` directory in our project, rather than the root of the project, because Tycho does not support multiple modules in the same directory. Then:

 - We declare the parent module in our POM, and add our project to the parent's list of modules.
 - We set the packaging type to Flexmojos' ``swc``.
 - We add the project's dependencies, and set the scope to ``external``, the equivalent of the ``external-library-path`` compiler option. Unlike the Tycho build, where the dependencies are extracted from the Eclipse setup, the Flex dependencies must be duplicated in the POM file.
 
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
			<dependency>
				<groupId>org.apache.flex.framework</groupId>
				<artifactId>flex-framework</artifactId>
				<version>${flexVersion}</version>
				<type>pom</type>
			</dependency>
	
			<!-- other dependencies -->
	
		</dependencies>
	</project>
 
<div markdown="1" class="alert alert-warning">
**IMPORTANT.** The Apache Flex SDK must have already been [mavenized](https://cwiki.apache.org/confluence/display/FLEX/Apache+Flex+SDK+Mavenizer) and available in a repository. 

Furthermore, if the project depends on any external libraries, they must also be installed before running the Maven build. To do this, we run the [install:install-file](http://maven.apache.org/plugins/maven-install-plugin/install-file-mojo.html) goal for the library. We may also add a new ``mvn`` task to the ``install-flex-deps`` target in the Ant script to do this automatically.
</div>
 