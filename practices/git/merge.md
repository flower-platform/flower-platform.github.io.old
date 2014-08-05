---
layout: page
group: subconcept
parent-id: git

title: "Merge"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---

#What does merge mean?

A <span class="label label-info">merge</span> incorporates changes from another branch or tag, since the time their histories diverged from the current branch, into the currently checked out branch.

#How?

There are tree ways to trigger merge:

<ul>
	<li>from the <strong>History View</strong> </li>
	<li>from the <strong>Team menu</strong> </li>
	<li>from the <strong>Git Repositories View</strong> </li>
</ul>

<!-- more -->

#Starting merge from the History View 


Ensure that the toggle button <span class="label label-info">Show all Branches and Tags</span> is selected in the History View's toolbar. This ensures that you see the complete history of your repository in order to decide which branch you want to merge. Select the commit with the branch or tag label you want to merge and click  <span class="label label-info">Merge</span>.

<img class="img-thumbnail center-block" src="merge-from-history.png"/>
 
#Starting merge from Team Menu


In the Package Explorer or Navigator, open the context menu on a project node. Select **Team** > **Merge...**

Select a branch or a tag you want to merge with your current branch. This dialog also allows you to select merge squash and fast-forward options.

<img class="img-thumbnail center-block" src="merge-1.png"/>

# Starting merge from the Git Repositories View


You can trigger a merge from any branch and tag node and from the repository node if you have checked out a local branch. You just have to right-click the branch you want to merge with and choose the merge option.


<div class="alert alert-danger"><strong>Attention:</strong> Some merges can`t be performed directly from Eclipse! When that happens, you must use <span class="label label-danger">Git Bash</span> or <span class="label label-danger">Git GUI</span>.</div>

