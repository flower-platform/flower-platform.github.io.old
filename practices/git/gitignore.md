---
layout: page
group: subconcept
parent-id: git

title: ".gitignore"
comments: true
share: true
---
{% include JB/setup %}

**.gitignore** files contain files that should not be tracked by git. Among the files that we want to be ignored and not be commited are the binary files. **Eclipse** is aware of this and automatically adds the **bin/** directory (which contains the binary files) to project's **.gitignore** file. If additionaly, we want to add another folder to be ignored by git, we will simply right-click on the respective directory and choose <code>Team > Ignore</code> as shown above.

<!-- more -->

<div style="text-align:center;"><img class="img-thumbnail" src="gitignore-images/gitignore_add_to_1.png"/><img class="img-thumbnail" src="gitignore-images/gitignore_add_to_2.png" width="600" height="800"/></div><br>

After this operation, we will see that the directory has been added to **.gitignore** file.

<img class="img-thumbnail center-block" src="gitignore-images/gitignore_add_to_3.png"/>

<div class="alert alert-info">
	<p>
		<strong>HINT.</strong> Sometimes we may not find the <strong>.gitignore</strong> file in our <strong>Project Explorer</strong> view, which for example automatically ignores the <strong>bin/</strong> folder. We recommend switching to <strong>Navigator</strong> view to see all project's files and folders. This can be done by typing <strong>Navigator</strong> in the <em>Quick access</em> text input from the toolbar as described <a href="../eclipse-productivity/WTP.html#adding_the_server">here</a>.
	</p>
</div>