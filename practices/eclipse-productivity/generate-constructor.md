---
layout: page
group: subconcept
parent-id: eclipse-productivity

title: "Generate constructor"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}
 
In Java we often need to add a **constructor** to a class based on some/all of its fields or even based on constructors of its superclass.
There are two features to help us generate these **constructor** instantly: *Generate Constructor using Field* and *Generate Constructors from Superclass*.

<!-- more -->

## How?

<br>**Generate a constructor using Field**

Right click / Source <span class="label label-success">(ALT + SHIFT + S)</span> / Generate a constructor using Field <span class="label label-success">(O)</span>

<img class="img-thumbnail center-block" src="generate-constructor/generate-constructor-using-fields.png"/>
   
<br>**Generate Constructors from Superclass**
 
 Sometimes we will want to reimplement some/all of a superclass's constructors.To do this, Right click / Source <span class="label label-success">(ALT + SHIFT + S)</span> / Generate a constructor from superclass <span class="label label-success">(C)</span>

 <img class="img-thumbnail center-block" src="generate-constructor/generate-constructor-from-superclass.png"/>