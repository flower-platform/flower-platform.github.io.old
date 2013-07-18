---
layout: page
group: subconcept
parent-id: sharing-and-collaboration

title: "Real Time Collaboration on Diagrams"
labels: [implemented]
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

The web (and mobile) version of Flower Platform allows people to collaborate in real time on any editor (diagram, code and other editors). Any modification made by one user is instantly propagated to the other people that view the same resource (diagram, file, etc.).

A temporary lock mechanism exists:

<p class="text-center">
	<img class="img-polaroid" src="real-time-collaboration1.png"/><br/>
	<em>User "dana" is editing the resource. I.e. the resource is temporarily locked by "dana"</em><br/><br/>
	<img class="img-polaroid" src="real-time-collaboration2.png"/><br/>
	<em>User "cristi" receives updates in real time. But he cannot edit the resource while it is locked by "dana"</em>
</p>

The *Open Resources* view shows which are the users that are viewing the current resource. 

<p class="text-center">
	<img class="img-polaroid" src="real-time-collaboration3.png"/>
</p>
