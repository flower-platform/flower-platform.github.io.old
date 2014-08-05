---
layout: page
group: subconcept
parent-id: git

title: "Git Staging"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---

Whenever you modify a file from your working directory, a <span class="label label-info"> > </span>  sign will appear in front of it in the Project Explorer/ Navigator view (it will propagate up to it`s root directory). This means that it was modified after the last commit was made.

<img class="img-thumbnail center-block" src="file-modified.png"/>

<!-- more -->

All the files that were modified will appear in the <span class="label label-info">Git Staging</span> view from the **Git perspective**.

<img class="img-thumbnail center-block" src="git-staging-view.png"/>

Here they can be split into two categories:
<ul>
	<li><strong>Unstaged changes:</strong> changes that will not be included in the commit.</li>
	<li><strong>Staged changes:</strong> changes that are ready to be committed.</li>
</ul> 

<div class="alert alert-success">You can <strong>drag and drop</strong> them from one category to another. Note how the file`s icon changed!</div>

<img class="img-thumbnail center-block" src="git-staging-drag-and-drop.png"/>


<div class="alert alert-danger"><strong>Attention:</strong>The unstaged changes will not appear into the commit! So make sure that you staged all the changes that you need before committing!</div>

You can commit your changes by pressing the <span class="label label-info">Commit</span> button from the bottom-down corner of the Git Staging view.

You can also commit and push by pressing the <span class="label label-info">Commit and Push</span> button.

<div class="alert alert-danger"><strong>Attention:</strong>You must assign a message to the commit. It should contain a short and clear description of what the commit is about.</div>

