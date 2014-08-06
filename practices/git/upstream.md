---
layout: page
group: subconcept
parent-id: git

title: "Working with Upstream"
comments: true
share: true
---
{% include JB/setup %}

<div class="alert alert-info">
	<p>
		<strong>HINT.</strong> When working on a repository and making changes, we may want to send the changes back "upstream" so that everyone working on that repository will work on the same changes.
	</p>
</div>

<!-- more -->

When creating a new branch (as indicated [here](./#Branchmanagement)) based on a **remote tracking branch** (which is mostly the common way of creating a branch), one of the already checked options is **Configure upstream for push and pull**. 

**But what does this mean?** It means that given the fact that every _remote tracking branch_ is associated with a _remote_ and this _remote_ contains the information required to access the corresponding _remote repository_, there is the possibility of automatically creating the upstream configuration while creating the new local branch. In the following example, we created a new branch called _test-branch_ starting from _origin/1_3_x_collaboration_ remote branch. 

<img class="img-thumbnail center-block" src="upstream-images/upstream_create_branch.png"/> 

After creating the branch, its configuration can be seen by right clicking on the newly created branch and selecting **Configure Branch...**. In the popup window that appears, you can see that the **Upstream Branch** is, as expected, the branch we started our branch from: _origin/1_3_x_collaboration_. 

<img class="img-thumbnail center-block" src="upstream-images/upstream_configure_branch.png"/> 

<div class="alert alert-danger">
	<p>
		<strong>IMPORTANT.</strong> In fact, the <strong>Upstream</strong> tracking branch is the correspondence between the local and the remote branch.
	</p>
</div>

<div class="alert alert-info">
	<p>
		<strong>HINT.</strong> Another aspect that prooves the importance of correctly configuring the upstream branch is that in this way we can use the <strong>Commit and Push</strong> option instead of only <strong>Commit</strong> and then manually selecting the remote repository to push at. 
		
		<img class="img-thumbnail center-block" src="upstream-images/upstream_commit_and_push.png"/> 
	</p>
</div>

<div class="alert alert-info">
	<p>
		<strong>HINT.</strong> Another important thing about <strong>upstream</strong> is that after a <strong>Fetch</strong>, you can see how many commits you are ahead or behind the corresponding remote branch.
		
		In the following example, we can see that our <em>local branch</em> is <strong>ahead</strong> of its corresponding <em>remote branch</em> by 1 commit.
		
		<img class="img-thumbnail center-block" src="upstream-images/upstream_ahead_behind.png"/> 
		
		If we were to make a <strong>Checkout</strong>, we could have seen how many commits our <em>local branch</em> is <strong>behind</strong> the corresponding <em>remote branch</em>.
	</p>
</div>
