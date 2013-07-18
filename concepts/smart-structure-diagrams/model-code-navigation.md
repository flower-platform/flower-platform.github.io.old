---
layout: page
group: subconcept
parent-id: smart-structure-diagrams

title: "Model - Code Navigation"
labels: [ideas, planned]
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

By model  - code navigation we understand the following items:

* after selecting a diagram element (e.g. class, method), the context menu action will propose some actions: *Show file in tree*, *Show file in editor*
* on right click from source code (in Eclipse, Web) , the context menu will show the diagrams that contain the element at cursor (file, class, method, etc)
* the Explorer tree will have a button similar with "Link with Editor" from Eclipse. Clicking on it will synchronize the tree with the current selection from diagram
 

