---
layout: page
group: subconcept
parent-id: core

title: "Editor"
labels: [implemented, in-progress]
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---

{% include JB/setup %}

A Flower Platform editor is designed to display:

* file system structures
* text files (*to be implemented*)
* mindmap diagrams
* class diagrams (*to be implemented*)

### Dirty State

<img class="img-thumbnail center-block pull-right" src="editor1.png"/>

<div markdown="1" class="clearfix">
An editor is **dirty** if itself or at least one containing resource (e.g. file system case when inner resources are displayed in the same editor) is modified. <br>
It signals the dirty state (i.e. not saved) with a ``*`` decorator.
</div>

### Save & Save All
To save an editor use the application menu bar -> File -> Save (or Save All for saving all the dirty editors). <br>
If an editor has multiple resources modified, a dialog is displayed allowing you to choose which one to save.

<img class="img-thumbnail center-block" src="editor2.png"/>

Also you are asked to save modified resources when closing dirty editors or the application's browser tab.

<div markdown="1" class="alert alert-info">
Regarding shortcuts:

* ``CTRL + S`` = Save, but it doesn't work in Internet Explorer. For mysterious reasons, other browsers as well ignore this shortcut from time to time. We fought to find a solution, but no luck. :-(
* ``CTRL + SHIFT + S`` = Save All. This shortcut is more reliable than its little and naughty brother, CTRL + S.
</div>








