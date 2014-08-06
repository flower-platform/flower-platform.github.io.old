---
layout: page
group: subconcept
parent-id: eclipse-productivity

title: "Outline and Quick Outline"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

The **Outline view** displays an outline of structured file that is currently opened in the editor area and lists 
structural elements.It is very useful for jumping between sections in a class, or finding that one method we want to get to.

<!-- more -->

##How?

<span class="label label-success">CTRL + O</span> shows the methods and properties of a class. We can start typing to filter and hit enter to jump to a particular signature/type.
 
<div style="text-align:center;"><br><img class="img-thumbnail" src="outline/outline-step1.png" width="420" height="900"><img class="img-thumbnail" src="outline/outline-step2.png" width="420" height="900"></div>
 
<br> Pressing again, <span class="label label-success">CTRL + O</span> lists including inherited methods.
 
<br><img class="img-thumbnail center-block" src="outline/outline-step3.png"/>
