---
layout: page
title: "Download"
comments: true
---

{% include JB/setup %}

# Flower Platform Web App

<p><a class="btn btn-success" href="https://github.com/flower-platform/flower-platform-4/releases/download/2014-05-16-v0.1.1/flower-platform.war">Download Flower Platform 4 Web App<br>v0.1.1 (Proof of Concept)</a></p>

## Install / Upgrade

### Install Tomcat <small>(skip if Tomcat is already installed)</small>

Flower Platform Web App runs inside the [Apache Tomcat](http://tomcat.apache.org/) server. Please install it on your system. If this is something new to you, please use Google to find out more. There are plenty of tutorials (written and video).

We work with Tomcat v7; we haven't tested it with v8, but we don't see any reasons why it shouldn't work.

### Remove Older Version of Flower Platform <small>(skip for first installation)</small>

Stop Tomcat. Go to the ``TOMCAT_INSTALL_DIR/webapps`` directory of your Tomcat installation. Remove:

* ``flower-platform.war`` file and
* ``flower-platform`` directory

<span class="label label-primary">Remark:</span> **Regarding the data (workspace) directory.** By default Flower Platform stores its data in ``TOMCAT_INSTALL_DIR`` (cf. ``TOMCAT_INSTALL_DIR/webapps/flower-platform/WEB-INF/web.xml`` -> search for *workspaceLocation*). 

So if you didn't change this default setting, your data is safe when you delete the dir + file, cf. above. Otherwise, if you did change this setting and you configured the location within the webapp itself, then be careful when you delete the webapp directory.

<span class="label label-warning">In the future:</span> We'll improve the update procedure in the future, by using the Eclipse Update Site mechanism + Eclipse P2.

### Copy the .war File

* Make sure that Tomcat is stopped. 
* Copy ``flower-platform.war`` -> ``TOMCAT_INSTALL_DIR/webapps/flower-platform.war``
* Start Tomcat. After the server has started, you should see a ``flower-platform`` directory (i.e. the unpacked contents of the ``flower-platform.war`` archive file).

<p markdown="1" class="text-success">Flower Platform should now be accessible from your web browser. Usually at [http://localhost:8080/flower-platform](http://localhost:8080/flower-platform).</p>

<span class="label label-primary">Remark:</span> **Regarding Linux installations without X server (without GUI).** The Mind Map Extension uses Freeplane libraries. They require a GUI environment (even if we don't make use of it). You'll need to install [X Virtual Frame Buffer - XVFB](http://en.wikipedia.org/wiki/Xvfb). Tomcat would be started with a command like this: ``xvfb-run catalina.sh run``. You might want to modify ``catalina.sh`` to include ``xvfb-run``. Please contact us, so that we can give additional details.

<div markdown="1" class="alert alert-info">
If you encounter **difficulties** in installing Flower Platform, please **start a discussion** below.
</div>

# Flower Platform Mobile

<p><a class="btn btn-success" href="https://play.google.com/store/apps/details?id=air.org.flowerplatform">Download Flower Platform 4 Mobile<br>(from Google Play)</a></p>

# Flower Platform for IDE

We'll make it available as soon as IDE enabled extensions will be released. 
