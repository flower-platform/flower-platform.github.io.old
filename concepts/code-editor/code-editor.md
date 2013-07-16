---
layout: page
group: subconcept
parent-id: code-editor

title: "Basic Editor Operations"
labels: [implemented, ideas]
#tagline: "tagline"
comments: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

<img class="img-polaroid" style="float:right" src="code-editor.png"/>

When working with Flower Platform from a web browser or mobile, we may need to access the code:
* either in read mode: browse source files that have the syntax highlighted
* or in write mode: e.g. write comments, snippets of code or pseudo-code during a collaboration session

Flower Platform supports basic editor operation: create file, open file, save file.

<!-- label:ideas -->
It would be nice to integrate an existing web based editor. E.g. :
* <http://brackets.io/>
* <http://ajaxorg.github.io/ace/>
* The editor used by <http://www.eclipse.org/orion/>

The advantage is that we could reused a lot of editor-related features that don't exist in the current version of Flower Platform