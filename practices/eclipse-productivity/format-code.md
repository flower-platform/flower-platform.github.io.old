---
layout: page
group: subconcept
parent-id: eclipse-productivity

title: "Format Code"
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

* **Formatting rules** are recomended especially when *developers* work on the **same code** using a ``version control system``. 
* **Merging** can be a ``pain``, if developers have different formatting rules.

<div class="alert alert-warning" role="alert">
<strong>Warning!</strong> It is recommended to <font color="red"><i>write formatted code</i></font>.</div>


## How?

We have an ``unformatted`` source code file:

<img class="img-thumbnail center-block" src="format-code-images/unformatted.png"/>

After ``formatting`` the code with **Right click / Source / Format** or <span class="label label-success">(CTRL + SHIFT + F)</span>, we get:

<img class="img-thumbnail center-block" src="format-code-images/sformatted.png"/>

<div class="alert alert-info"> <font size="4"><span class="label label-danger"><strong>Hint:</strong></span></font> When working on a <font color="red"><i>version control system</i></font> is really <b>indicated to format</b> only code that we added to the file, because it is possible that <i>other colleagues have formatted</i> their particular portions of the <b>source file for some reason</b>.</div>

**Formatting settings:** [Configure Workspace](index.html#ConfigureWorkspace)