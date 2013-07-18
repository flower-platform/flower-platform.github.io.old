---
layout: page
group: subconcept
parent-id: smart-structure-diagrams

title: "Scenarios"
labels: [in-progress]
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

The **first purpose** of a scenario is to be able to see on a diagram the flow / ordered interactions between the code (e.g. calls to methods, access to attributes). It's like **combining** an **UML class diagram** and an **UML sequence diagram** into a single diagram (or a **stack trace tree** as we see it in the debugger window). 

<div class="alert alert-info">
Scenario examples: <em>register user</em>, <em>activate user</em>, <em>upgrade user to admin</em>. Usually a scenario also represents a test case, and may be captured in a unit test.
</div>

On a diagram, the interactions between the code are shown as dependencies. They are prefixed with a number, which indicates the ordering. These interactions are shown on the same diagram in a tree form, similar to a stack trace. 

The **second purpose** of scenarios is to be able to combine several scenarios on the same diagram, when a group of scenarios uses roughly the same subset of files/classes/methods/attributes. 

<div class="alert alert-info">
E.g. the following scenarios can be on the same diagram: <em>register user</em>, <em>activate user</em>, <em>upgrade user to admin</em>. When the current/selected scenario is <em>register user</em>, the methods, attributes, classes, interactions of the other scenarios will be displayed grayed. So that you can focus on the current scenario, and keep an overview of the items from the related scenarios.
</div>