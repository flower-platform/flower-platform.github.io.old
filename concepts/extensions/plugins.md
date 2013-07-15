---
layout: page
group: subconcept
parent-id: extensions

title: "Plugins"
#tagline: "tagline"
comments: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

`implemented`

Flower Platform is based on Eclipse and OSGi (i.e. Equinox implementation from Eclipse). All the logic of Flower Platform is organized in plugins that declare extension points to allow other plugins to register and contribute with custom logic.

This way it's straight forward to contribute new plugins. E.g. to support a new language, a new wiki, a new kind of editor (for the web & mobile), etc.
