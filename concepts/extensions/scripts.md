---
layout: page
group: subconcept
parent-id: extensions

title: "Scripts"
labels: [ideas]
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

Flower Platform will allow users to upload their own scripts.

<div class="alert alert-info">
There are many possible usages for scripts. One scenario could be: 
<ul>
<li>listen for changes on something <em>(e.g. a class)</em></li>
<li>when a change notification is received, verify if certain conditions are met <em>(e.g. the name of the class ends with "Service"?)</em></li>
<li>if the conditions test is true => do something <em>(e.g. add it on a special diagram, called "Services", and color it with orange)</em> </li>
</ul>
</div>

Everything that happens on the server side is executed in a secure sandbox, with the permissions of the current user. This means that users could add, modify, remove scripts while the server is running, without risk.

We could support several scripting technologies; e.g. Groovy, JavaScript, etc.