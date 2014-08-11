---
layout: page
group: subconcept
parent-id: eclipse-productivity

title: "Override"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

If a class inherits a method from its super class, then there it is a chance to **override** the method.
The benefit of **overriding** is the ability to <code>define a behavior</code> that is specific to the subclass type 
which means a subclass can implement a parent class method based on its requirement.

<!-- more -->

## How?

Right click / Source <span class="label label-success">(ALT + SHIFT + S)</span> on any space on your source code and invoke Override / Implement Methods <span class="label label-success">(V)</span> (e.g: we want to **override** the method *design()*).

<br><img class="img-thumbnail center-block" src="override/override-step1.png"/>

<br>We can select the desired method(s) to be inserted and also the insertion point, click <span class="label label-success">OK</span>. 

<div style="text-align:center;"><br><img class="img-thumbnail" src="override/override-step2.png" width="420"><img class="img-thumbnail" src="override/override-step3.png" width="420" height="800"></div>

