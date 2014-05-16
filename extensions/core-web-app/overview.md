---
layout: page
group: subconcept
parent-id: core

title: "Core - Web App Overview"
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

<div markdown="1" class="clearfix">
Sharing and collaboration around mind maps and diagrams are a primary focus. 

The server side code is written in Java and it's modular, packed as [OSGi plugins](http://www.osgi.org) (in an [Eclipse Equinox](http://www.eclipse.org/equinox/) container). 

The client side code (using [Apache Flex](http://flex.apache.org/) and JavaScript) is also modular.
</div>