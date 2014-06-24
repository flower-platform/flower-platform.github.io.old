---
layout: page
group: subconcept
parent-id: core

title: "Preferences"
labels: [in-progress]
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---

{% include JB/setup %}

## Preferences Editor

A popup (meant to live in a workbench view) with a tree and a property editor. Design to be reused in other contexts as well (e.g. styles editor for a mind map).

The tree displays nodes from the preferences service/system, that combine information from 3 mind maps:

* the default preferences (i.e. shipped with a new installation of Flower Platform)
* the global preferences (active for everybody)
* the user preferences

## Preferences Refresh

On startup, the preferences are retrieved (i.e. the merged tree).

At this point, plugins may scan the tree and use the preferences. E.g. the key bindings will be read.

## Sample Preferences Tree

* [preferenceCategory] General
	* [preferenceCategory] Appearance
		* [preference] Background Color
* [preferenceCategory] Shortcuts
	* [shortcut] Insert as Sibbling (actionId="insertAsSibbling", value="CTRL+ENTER", value.default="ENTER", value.global="CTRL+A")
	* [shortcut] Insert as Child

*Legend: [...] -> contains the node's type*


		