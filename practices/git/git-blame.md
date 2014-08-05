---
layout: page
group: subconcept
parent-id: git

title: "Git Blame"
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

As most of the version control systems, **Git** embrace the idea of **blame**. This concept is very useful when a project is developed by more than two programmers, because in these cases there can be even methods to whom implementation have contributed **many developers**. We use git blame every time we want to figure out who committed a bug or who implement efficiently a method. Not in so many words, Git blame option gives us the possibility to see, **for every line of a file**:

* who is its **author** (e.g. ``paul-smith``);
* **when** it was **modified** (e.g. ``29.07.2014 17:40``);
* in which **commit** it was modified (e.g. ``Commit a51f6fd``).

## How?

<!-- more -->

To see the authors of a certain file using git blame, we must perform the following steps:

* <span class="text-success"><i>Open the file</i></span> in the Eclipse IDE.

* <span class="text-success"><i>Right click</i></span> anywhere in the <span class="text-success"><b>Source View</b></span> and choose ``Team / Show Annotations``

<img class="img-thumbnail center-block" src="git-blame/gitBlame-ShowAnnotations.png"/>
<br />

* <span class="text-success"><i>Select</i></span> <span class="label label-success">Ok</span> in the popup window that appears. We will see a <span class="text-success"><b>coloured rectangle</b></span> in front of every line from our file.

<img class="img-thumbnail center-block" src="git-blame/gitBalme-DiffReference.png"/>
<br />

* <span class="text-success"><i>Move the cursor</i></span> of the mouse <span class="text-success"><i>on the rectangle</i></span> corresponding to the line that we want to inspect. We will obtain all the <span class="text-success"><b>details</b></span> that we have been looking for, such as the author, the commit, the date modified.	

<img class="img-thumbnail center-block" src="git-blame/gitBlame-ShowDetails.png"/>
<br />

<div class="alert alert-danger"><strong>Note:</strong> Notice that once we are with the cursor above a rectangle, other <b>rectangles</b> with the same color are suddenly receiving a <b>black border</b>. This means that the <b>lines</b> corresponding to those rectangles have the <b>same features</b> as the inspected line.</div>

<div class="alert alert-info"><strong>Hint!</strong> We can obtain the <b>same result</b> if we <i>right click</i> anywhere in the vertical bar in front of the code lines (the vertical bar which contains the line numbers or the code folding buttons) and choose <span class="label label-success">Show Annotations</span>.</div>