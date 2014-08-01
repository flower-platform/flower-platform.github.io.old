---
layout: page
group: subconcept
parent-id: git

title: "Cloning a Git Repository"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

When we want to store a **remote repository** in our file system, we need to **clone** that repository.
 
E.g. **from Eclipse:**

* we switch to the *Git perspective*;
* from the *Git perspective view* we click on **Clone a Git Repository...** toolbar button. E.g. we put the repo in ``D:\data\git-repos\flower-platform-4``

If we already have a repository stored locally, we need to choose **Add an existing local Git...**.

<img class="img-thumbnail center-block" src="clone-git-repository.png"/>
<img class="img-thumbnail center-block" src="add-git-repository.png"/>

## Importing projects

After cloning the repository, we have to import the projects from it. From the **Git view**, right click on repository and then **Import Projects...**. We should select **all** the projects.

