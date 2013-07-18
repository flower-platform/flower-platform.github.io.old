---
layout: post
title: "New Flower Dev Center Version - 1.0.3_2013-02-19"
description: ""
category: releases
tags: [releases, news]
---
{% include JB/setup %}



We are happy to announce that the final version 1.0.3 has been released. We have worked hard for this release that contains over 100 improvements. Some of them are listed below.

We are even happier to see the first users and open source projects added in Flower Dev Center. :-)

# New Features

* Users, Groups, Organizations management. Permissions
* Generate link of current open resources + open resources based on a link
* Java libraries within the model (during the new model wizard & from the model tree)
* GIT Support: first iteration/experimental: clone repositories and import projects
* Dock/Undock Mechanism for windows

# Bugs Fixed
## CodeSync & Model Related

* Solved many ActionScript/MXML code synchronization issues. Among them: support for lines that are not terminated with ; and attributes that are initialized with blocks
* Solved several Java code sync issues
* Allow setting project as source directory
* Synchronization doesn't work for nested src dirs
* Synchronization fails for src dirs e.g. ../`<project_name`>/src
* After sync although a new dialog with "new errors" appears, there is a stray Alert with the first error
* After sync the "new errors" dialog pops up for Unknown Types too
* ClassCastException thrown when synchronizing
* When loading a model that no longer exists, we get a strange error
* Deactivating the UID/flowerModelElementId doesn't seem to work
* Model Creation Wizard allows choosing illegal paths 

* "Delete Unused Elements" within UnknownTypes doesn't seem to work
* Performance improvement related to validation errors

## Visual

* Cannot modify styles for a diagram
* Visual issues with the diagram selection tools

## Other

* Error when deleting a Java class from default package
* Exception when a client reconnects
* A class from default package doesn't refresh on rename
* Exception thrown while expanding and collapsing immediately a node in tree
* Performance improvement for the Project Explorer tree client/server communication


