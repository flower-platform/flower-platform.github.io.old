---
layout: page
group: subconcept
parent-id: eclipse-productivity

title: "Generate Getters and Setters"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

## Why?

Java practices recommend to always use **getter** and **setter** methods (+ private or protected attributes), and to **avoid** using **public attributes**.

So when we want to add a new attribute (e.g. ``Contact.dateOfBirth``, 1 line) we have to add the corresponding getters and setters (3 + 3 lines).

## How?

Right click / Source <span class="label label-success">(ALT + SHIFT + S)</span> / Generate Getters and Setters <span class="label label-success">(R)</span>

<img class="img-thumbnail center-block" src="generate-getters-setters-images/generate-getters-setters.png"/>

<div class="alert alert-info"><strong>Hint:</strong> Once you open the window, you can use the keyboard: <span class="label label-success">ARROW KEYS</span>, <span class="label label-success">SPACE</span> and then <span class="label label-success">ENTER</span>.</div>