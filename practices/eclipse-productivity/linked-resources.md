---
layout: page
group: subconcept
parent-id: eclipse-productivity

title: "Linked resources"
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

**Linking resources** to your current **project** is very useful, because you may want to keep the project and resources **separate**, also being able to easily change the resources you use.

You may need this to compile in more **exotic configurations**, or even **reuse** code for javascript.

## How?

To link resources to your current project <span class="label label-success">(RIGHT CLICK)</span> on it, choose <span class="label label-default">New</span> then <span class="label label-default">Folder</span>. This will open a window such as the one below:

<img class="img-thumbnail center-block" src="new-folder.png"/>

Press the <span class="label label-info">Advanced</span> button. Then choose the <span class="label label-default">Link to alternate location (Linked folder)</span> option. This will allow you to link folders to an absolute location (by pressing <span class="label label-info">Browse...</span> button), or to a location relative to the project (by pressing the <span class="label label-info">Variables...</span> button).
It is **recommended** to link resources using locations relative to the project, because this will make sure that the resources will be corrected linked even if we open the project on **another station**, which has different **workspace configurations.**

<div class="alert alert-info">
<strong>Example:</strong> You can add a library to a project. And if you need that library in another project you simply link the library in your new project. And you can do this over and over again for each new project. This way you reuse that library. The library will be copied only when you dispatch your project which has it linked.
</div>


To keep your workspace resources **synchronized** with their corresponding resources in the file system **automatically**, you need to go on <span class="label label-info">Window->Preferences</span>. This will open a window such as the one below:

<img class="img-thumbnail center-block" src="autorefresh.png"/>

Then go on <span class="label label-info">General->Workspace</span> and check the <span class="label label-info">Refresh using native hooks or polling</span> checkbox.
This will keep your resources synchronized using native refresh providers (on Windows) or a polling mechanism on other Operating Systems.