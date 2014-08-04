---
layout: page
group: subconcept
parent-id: git

title: "Branch management"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

We can **create** a local branch either from a remote branch or from an existing local branch. (right click on a branch and then choose **Create Branch...**). We have to give a **name** and select whether the **newly created branch** should be checked out.

<img class="img-thumbnail center-block" src="create-branch.png"/>

One way to add a **new branch** to a **remote repository** is to first add the branch to your local repository and then **push** that local branch to the remote repository.

For **deleting** a branch: right click on a branch and then select *Delete Branch*.

##Prune command

**'Prune' command** allows us to prune all of our local branches that track an **already-deleted remote branch**.
