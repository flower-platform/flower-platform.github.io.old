---
layout: page
group: subconcept
parent-id: mind-map

title: "Node Properties and Styles"
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

We are inspiring our node properties and styles from [Freeplane](http://freeplane.sourceforge.net).
We currently support a subset of Freeplane's properties and styles. 

A property can be changed by using our [Properties Editor](../core/properties_editor.html).

## Style

We can attach one style to a node by selecting the style name(s) from a list of predefined and user defined styles.

[Manage Styles](manage_styles.html)

## Icons

<img class="img-thumbnail center-block pull-right" src="mm_icons2.png"/>

<div markdown="1" class="clearfix">
The selected icon from list will be added to selected node(s).
</div>

We provide 2 ways to change a node's icons:

1. using the Icons property from Properties Editor
2. using the icons sidebar

<p class="text-center">
<img class="img-thumbnail" src="mm_icons1.png"/>
<img class="img-thumbnail" src="mm_icons3.png"  hspace="100"/>
</p>

## Color
<img class="img-thumbnail center-block pull-right" src="mm_color.png"/>

<div markdown="1" class="clearfix">
* **Text** - foreground color (the color is applied to all text)
* **Background** - background color (the color is applied to the entire node)
</div>

## Font

<img class="img-thumbnail center-block pull-right" src="mm_font.png"/>

<div markdown="1" class="clearfix">
* **Font Family**
* **Size** 
* **Bold** 
* **Italic** 
</div>

## Node Shape

<img class="img-thumbnail center-block pull-right" src="mm_node_shape.png"/>

<div markdown="1" class="clearfix">
* **Min node width** (in pixels)
* **Max node width** (in pixels)
</div>

## Edges

<img class="img-thumbnail center-block pull-right" src="mm_edges.png"/>

<div markdown="1" class="clearfix">
* **Edge width** (in pixels)
* **Edge style**
* **Edge color**
</div>

## Clouds

<img class="img-thumbnail center-block pull-right" src="mm_cloud.png"/>

<div markdown="1" class="clearfix">
* **Cloud Color** - background cloud color 
* **Cloud Shape** - cloud form (Rectangle and Round Rectangle forms are supported).
</div>
