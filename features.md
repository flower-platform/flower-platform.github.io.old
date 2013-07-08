---
layout: page-navigation
title: Features
tagline: "Things that Flower Platform can do"
group: 
subnavigation:
 - id: modelling
   title: Modelling
 - id: code_synchronization
   title: Code Synchronization
 - id: collab_edit
   title: Collaborative editing
 - id: fast_navigation
   title: Fast navigation
 - id: developer_tools
   title: Developer tools integration
---
{% include JB/setup %}

{% assign subcontent_id = 'modelling' %}
{% assign subcontent_title = 'Modelling' %}
{% capture subcontent_image %}{{ BASE_PATH }}assets/imgs/modelling_thumb.png{% endcapture %}

{% capture subcontent_lead %}
Easy modelling using UML.
{% endcapture %}

{% capture subcontent_content %}
Allows drawing diagrams and modelling the interaction between classes, code, ..
{% endcapture %}

{% include themes/flower/subnavigation.html %}


{% assign subcontent_id = 'code_synchronization' %}
{% assign subcontent_title = 'Code Synchronization' %}
{% capture subcontent_image %}{{ BASE_PATH }}assets/imgs/synchronization_thumb.png{% endcapture %}
{% assign subcontent_image_position = 'right' %}

{% capture subcontent_lead %}
Make modification to either code or UML model, and Flower Platform will take care to have them both in sync
{% endcapture %}

{% capture subcontent_content %}
Now there is no need to throw away the model after the code was generated, or to recreate the model after the code was written, because the model can easily be obtain from the code, and the code can be easily generated from the model, and both of them can be easily kept up to date.
{% endcapture %}

{% include themes/flower/subnavigation.html %}


{% assign subcontent_id = 'collab_edit' %}
{% assign subcontent_title = 'Collaborative editing' %}
{% capture subcontent_image %}{{ BASE_PATH }}assets/imgs/collab_thumb.png{% endcapture %}

{% capture subcontent_lead %}
Easy to share and collaborate
{% endcapture %}

{% capture subcontent_content %}
Create and modify code and model with the help of your collegues. Allows highlighting the exact pieces of code/UML model you want to discuss about.
{% endcapture %}

{% include themes/flower/subnavigation.html %}


{% assign subcontent_id = 'fast_navigation' %}
{% assign subcontent_title = 'Fast navigation' %}
{% capture subcontent_image %}{{ BASE_PATH }}assets/imgs/java_editor_link.png{% endcapture %}
{% assign subcontent_image_position = 'right' %}

{% capture subcontent_lead %}
Switch between code and UML model fast and easy.
{% endcapture %}

{% capture subcontent_content %}
Navigation in code is done using CTRL + Click on a source element navigates to the above element (just like in Eclipse).

Find a file rapidly using CTRL + SHIFT + R (just like in Eclipse)
{% endcapture %}

{% include themes/flower/subnavigation.html %}


{% assign subcontent_id = 'developer_tools' %}
{% assign subcontent_title = 'Developer tools integration' %}
{% capture subcontent_image %}{{ BASE_PATH }}assets/imgs/fast_navig_thumb.png{% endcapture %}
{% assign subcontent_image_position = 'left' %}

{% capture subcontent_lead %}
Integrates with other tools and services from developer's ecosystem: IDE, Source code repositories (SVN, GIT, Mercurial), Issue trackers (Jira, Redmine, Github, etc), Wikis, Code Review.
{% endcapture %}

{% capture subcontent_content %}
Allows adding intelligent links between the code and diagrams, issues, wiki pages
{% endcapture %}

{% include themes/flower/subnavigation.html %}


<div class="row-fluid">
	<div class="span4">
		<div class="thumbnail">
			<img src="{{ BASE_PATH }}assets/imgs/modelling_thumb.png"/>
			<h3>Modelling</h3>
			<p class="lead">Easy modelling using UML.</p>
			<p>Allows drawing diagrams and modelling the interaction between classes, code, ..</p>
		</div>
	</div>
	<div class="span4">
		<div class="thumbnail">
			<img src="{{ BASE_PATH }}assets/imgs/synchronization_thumb.png"/>
			<h3>Code Synchronization</h3>
			<p class="lead">Make modification to either code or UML model, and Flower Platform will take care to have them both in sync</p>
			<p>Now there is no need to throw away the model after the code was generated, or to recreate the model after the code was written, because the model can easily be obtain from the code, and the code can be easily generated from the model, and both of them can be easily kept up to date.</p>
		</div>
	</div>
	<div class="span4">
		<div class="thumbnail">
			<img src="{{ BASE_PATH }}assets/imgs/collab_thumb.png"/>
			<h3>Collaborative editing</h3>
			<p class="lead">Easy to share and collaborate</p>
			<p>Create and modify code and model with the help of your collegues. Allows highlighting the exact pieces of code/UML model you want to discuss about.</p>
		</div>
	</div>
</div>

