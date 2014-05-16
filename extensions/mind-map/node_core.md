---
layout: page
group: subconcept
parent-id: mind-map

title: "Node Core"
labels: [implemented, in-progress]
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---

{% include JB/setup %}

## Edit core in-line

<img class="img-thumbnail center-block pull-right" src="mm_node_core1.png"/>

<div markdown="1" class="clearfix">

Available at ``mouse click`` or ``F2`` pressed on already selected node. <br>
Opens an inline editor for fast entering and modifying text.
</div>

<br>

<div markdown="1" class="alert alert-info">
Inline editor hints:

* ``Ctrl + Enter`` -> add new line 
* ``Enter`` or click outside -> submit 
* ``Esc`` -> abort

</div>

## Edit core in dialog

<img class="img-thumbnail center-block pull-right" src="mm_node_core3.png"/>

<div markdown="1" class="clearfix">
Available as action in selected node's menu.

It provides the ability to see changes in real time, necessary when working with html text.
</div>
<img class="img-thumbnail center-block " src="mm_node_core2.png"/>

<div class="alert alert-info" markdown="1">
To display html text, enclose it with ``html`` tag.
</div>

## Edit node details in dialog

Available as action in selected node's menu.
<img class="img-thumbnail center-block" src="mm_node_details1.png"/>


It provides the ability to add **Node details**.<br>
<img class="img-thumbnail center-block" src="mm_node_details2.png"/>

<div class="alert alert-info" markdown="1">
To display html text, enclose it with ``html`` tag.
</div>

**Node details** can be expanded or collapsed by clicking on the **Note Details Icon**.

<p class="text-center">
<img class="img-thumbnail" src="mm_node_details_icon1.png"/>
<img class="img-thumbnail" src="mm_node_details_icon2.png" hspace="20"/>
</p>

<div markdown="1" class="clearfix">

## Edit note in dialog

Available as action in selected node's menu.
<img class="img-thumbnail center-block" src="mm_node_note1.png"/>


It provides the ability to add **Node notes**.
<img class="img-thumbnail center-block" src="mm_node_note.png"/>

<div class="alert alert-info" markdown="1">
To display html text, enclose it with ``html`` tag.
</div>

Nodes that have notes are preceded with a **note icon**.
**Node note** is visible when the mouse pointer is moved over the node.

<p class="text-center">
<img class="img-thumbnail" src="mm_node_note2.png"/>
<img class="img-thumbnail" src="mm_node_note3.png" hspace="20"/>
</p>