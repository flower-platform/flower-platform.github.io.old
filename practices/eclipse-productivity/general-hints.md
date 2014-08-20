---
layout: page
group: subconcept
parent-id: eclipse-productivity

title: "General Hints"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

### Ctrl + Click

When we work with larger files or anything with long methods, it can get extremely annoying to see where some variables are declared.All we have to do is hold to <span class="label label-success">CTRL down</span> and click the <span class="label label-success">hyperlinked</span> variable, method or class to see their source.

<br><img class="img-thumbnail center-block" src="general-hints/ctrl-click.png"/>

### Letters + Ctrl + Space

You can use <code>content assist</code> to speed up the creation of fields, method parameters and local variables. With the cursor positioned after the type name of the declaration, press <span class="label label-success">Ctrl+Space</span>.


<br><img class="img-thumbnail center-block" src="general-hints/letter-ctrl-space.png"/>


<br>Code completion supports <code>camel case</code> patterns.It is useful to search using only first letters or some letters from the name (e.g completing on **_FNFE_** or **_FiNoFoE_** will propose **_FileNotFoundException_**)

<br><img class="img-thumbnail center-block" src="general-hints/camel-case.png"/>

### Alt + Shift + S

<span class="label label-success">Alt + Shift + S</span> shows the Source Menu which includes menu options.                  
Some of the menu options have direct shortcuts (e.g **format** - <span class="label label-success">Ctrl + Shift + F</span> ), but a lot of the generate commands don't,so we must press the *underlined letter* that appears on menu options (e.g: **generate getters and setters** - <span class="label label-success">R</span>, **generate constructors using fields** - <span class="label label-success">O</span>)


<br> <img class="img-thumbnail center-block" src="general-hints/source-menu.png"/>


