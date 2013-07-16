---
layout: page
group: subconcept
parent-id: mindmap-diagrams

title: "Mindmap Connected with Other Tools"
labels: [in-progress]
#tagline: "tagline"
comments: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

Mindmaps display hierarchical data. And a lot of data that we handle daily can be represented as a hierarchy. I.e. shown as a mindmap.

So mindmaps are a great tool to display data that comes from other (development) tools Flower Platform connects with. E.g. data from wiki (namespaces, articles, heading, etc). Or issues from an issue tracker. Or a website.

<div class="alert alert-info">

E.g. Flower Platform will show us the contents from a wiki page in a mindmap format. When we edit nodes from the mindmap, we are actually adding headings, paragraphs, etc. which will be synchronized with the wiki page:

<p class="text-center">
<img class="img-polaroid" src="mindmap-wiki.png"/>
</p>

</div>