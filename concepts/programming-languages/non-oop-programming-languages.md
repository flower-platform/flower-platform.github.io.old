---
layout: page
group: subconcept
parent-id: programming-languages

title: "Non Object Oriented Programming Languages"
labels: [in-progress, ideas]
#tagline: "tagline"
comments: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

We think that diagramming shouldn't be limited to object oriented programming languages. Non-oop constructs can be added to our Smart Structure Diagrams, which resemble a lot with class diagrams from UML. Actually this is the reason why we call them Structure Diagrams instead of Class Diagrams. And we added "Smart" because they are smarter than normal diagrams. :)

<div class="alert alert-info">
E.g. a source file with C code can be represented as a box, the same way a Java class is. It would show visually the variables, functions, structs defined in that file the same way we would show (for a Java class) the attributes, methods, inner classes. 
</div> 

<!-- label:ideas -->
We plan to support the C programming language, because there are a lot of open-source communities that develop code in C and could take advantage of Flower Platform. 

<!-- label:in-progress -->
Besides the languages that don't support object oriented programming (e.g. C), most of the OOP languages allow the developer to write code in a non-OOP manner. E.g. PHP, JavaScript. We plan to support this kind of constructs.

<div class="alert alert-info">
E.g. a source file with PHP code (that can contain HTML code) could be shown on a diagram as a box. If the file contains functions, they will be shown as children of this box.
</div> 
