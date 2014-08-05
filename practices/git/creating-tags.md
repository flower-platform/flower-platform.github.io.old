---
layout: page
group: subconcept
parent-id: git

title: "Creating Tags"
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

Among many other features, **Git** provides us the ability of using **tags**. A tag can be used in different cases such as:

* marking a **release version** of our code;
* identifying a **certain** important **commit** in our git history. 

A tag can be seen like a label for a commit, because it contains a name (e.g. ``v1.0``) which identify the commit or the released version and a descriptive message (e.g. ``Mobile Version 1.0 released on 4th August 2014``).

## How?

<!-- more -->

To create a new tag, we must perform the following steps:

* <span class="text-success"><i>Switch to the [Git perspective](git-perspective.html)</i></span> in the Eclipse IDE.

* <span class="text-success"><i>Double click on the repository</i></span> where we want to create the tag. After that operation, we will obtain the following hierarchy:
	<img class="img-thumbnail center-block" src="creating-tags/creatingTags-RepoHierarchy.png"/>
	
* <span class="text-success"><i>Checkout the desired branch</i></span> and then, in the hierarchy, <span class="text-success"><i>left click</i></span> ``Tags / Create Tag...``. In the opened window, we can enter the name of the new tag, as well as the related message, as we have just talked before.
	<img class="img-thumbnail center-block" src="creating-tags/creatingTags.png"/>
	
* After completing all the information, we have to <span class="text-success"><i>choose one of the following options:</i></span>
	* <span class="text-success"><i><b>CreateTag and Start Push...</b></i></span>
		* the new tag will be *automatically pushed* on the remote branch.
	* <span class="text-success"><i><b>Create Tag</b></i></span>
		* the new tag must *manually* be *pushed* on the remote branch. For this action, in the previous hierarchy, <span class="text-success"><i>left click</i></span> ``Tags / Push Tags...``. In the *Push Tags* window we <span class="text-success"><i>select the tags that we want to push</i></span> on a remote branch and then we press ``Next -> Finish -> Ok``.
		<img class="img-thumbnail center-block" src="creating-tags/creatingTags-PushTag.png"/>
		
<div class="alert alert-warning"><strong>Warning!</strong> If we create a tag using the method presented above, then the commit identified by the new tag will be the commit which is the HEAD of the selected branch. <b>To create a tag for a specific commit:</b>
	<ul>
		<li class="circle">In the <a href="git-perspective.html">Git perspective</a>, <i>switch</i> to the <a href="history.html">History view</a>;</li>
		<li class="circle"><i>Right click on the desired commit</i> and select <span class="label label-success">Create Tag...</span>.</li>
	</ul>
The next steps are those that we have already discussed.</div>

<img class="img-thumbnail center-block" src="creating-tags/creatingTags-SelectCommit.png"/>

## Get a file from a specific revision

After we create tags, we can **find** a file from a **specific revision**, or a **tagged commit**. To do that:

* On our repository page from [Github](http://www.github.com), <span class="text-success"><i>left click the down arrow</i></span> from the <span class="label label-success">branch: <b>master</b></span> tab;
* In the drop down menu, <span class="text-success"><i>switch</i></span> to the <span class="label label-success">Tags</span> tab and choose the wanted tag. 

<img class="img-thumbnail center-block" src="creating-tags/creatingTags-ViewTag.png"/>

