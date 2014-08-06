---
layout: page
group: subconcept
parent-id: git

title: "Reset vs. replace"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---

#Why?


Sometimes you need to undo **all** the changes that you have made, sometimes just **some** of them.


#Reset


The <span class="label label-info">reset</span> command removes all the changes.

To reset: Right-click on the repository, choose the **reset** option, then choose the reset point and the reset type (usually choose **HARD**, this will remove all the changes).

<!-- more -->

<img class="img-thumbnail center-block" src="reset-replace/reset.png"/>

<div class="alert alert-danger"><strong>Attention:</strong>Reset will undo all the changes from the <strong>entire</strong> current repository!</div>


#Replace


When you want to undo only the changes from some particular files, you can use <span class="label label-info">replace</span> instead.

To replace: Right-click on the file that contains the changes you want to undo/Replace with/HEAD revision

<img class="img-thumbnail center-block" src="reset-replace/replace.png"/>

