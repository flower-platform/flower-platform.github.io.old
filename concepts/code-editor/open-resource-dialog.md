---
layout: page
group: subconcept
parent-id: code-editor

title: "Open Resource Dialog"
labels: [implemented]
#tagline: "tagline"
comments: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

Flower Platform gives you the possibility to open quickly any resource by pressing the CTRL + SHIFT + R (or menu → Navigate → Open Resource…).

This is a very useful feature inspired from Eclipse. The Open Resource dialog helps you even if you don't know the entire name of the resource, but you know only a part of it. Use the * wildcard for this. Or, for camel case named resources, type the capital letters (e.g. PSE would find PasswordSafeException.java).

<p class="text-center">
<img class="img-polaroid" src="open-resource-dialog.png"/>
</p> 