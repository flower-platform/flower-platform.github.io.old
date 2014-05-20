---
layout: page
group: subconcept
parent-id: core

title: "Undo, Redo, Command Stack"
labels: [in-progress]
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---

{% include JB/setup %}

## Server Side

All commands that are initiated by the client app, are saved in a command stack. 

## Flex Client

**Undo and Redo actions** display the name of the current action. 

The ***Command Stack* view** displays the list of commands (i.e. command stack).

The actions and the view are updated in real time with information from other users. I.e. if another users performs an "add node", then the *Command Stack* view is updated, along with the label of "Undo".

<span class="label label-danger">Remark on concurrency</span> An user can undo the commands that were note executed by him/her. E.g. John and Lisa edit a resource. 

* John performs 2 commands. 
* Lisa performs 2 commands. 
* Mary joins and performs 3 commands. 

At this point, any user (including Mary) could undo 1, 2 or all the commands (7 cf. above). 