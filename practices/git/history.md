---
layout: page
group: subconcept
parent-id: git

title: "History View"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---

#What is History View?


The <span class="label label-info">History View</span> is a commit-centric view of the resources in a given Repository.

<img class="img-thumbnail center-block" src="history.png"/>

<!-- more -->


<div class="alert alert-warning">You can open it in the Git Perspective by clicking <strong>Window</strong> > <strong>Show View</strong> > <strong>Other...</strong>, then <strong>Team</strong> > <strong>History</strong>.</div>


#Commit Graph


The <span class="label label-info">Commit Graph</span> area is the main part of the History View

Each line in the Commit Graph corresponds to a commit. Branches, tags and HEAD are visualized as follows:

<ul>
    <li>The peaks of <strong>local branches</strong> are shown as green rectangles</li>
    <li>The peaks of <strong>remote branches</strong> are shown as grey rectangles</li>
    <li><strong>HEAD</strong> is shown as a white rectangle</li>
    <li><strong>Tags</strong> are shown as yellow rectangles</li> 
</ul>


#Actions that can be performed from the History View

 
You can perform many tasks form the **History View**, such as:

<ul>
	<li>Inspecting the change history of a particular file from the repository</li>
	<li>Search for a commit</li>
	<li>Display details about a commit, like author, modified files, commit message</li>
	<li>Check-out of a certain commit</li>
	<li>Create/delete branches and tags</li>
	<li>Reset the repository to a certain commit</li>
	<li>Merge branches</li>
</ul>

<div class="alert alert-info"><strong>Hint:</strong>It is recommended to have the <span class="label label-info">Link with Editor and Selection</span> button pressed. This way, the History View will be  synchronised with the <strong>Repositories Navigator</strong> and with the current selection from it. 
<img class="img-thumbnail center-block" src="history-link-editor.png"/></div>
