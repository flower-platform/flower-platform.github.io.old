---
layout: page
group: subconcept
parent-id: smart-structure-diagrams

title: "Dynamic Compartments"
#tagline: "tagline"
comments: true
---
{% include JB/setup %}

<div>

	<h1>Dynamic Compartments</h1>
    <ul class="breadcrumb">
	    <li class="active">Labels:</li>
	    <li><span class="label label-ideas">Ideas for Improvements</span></li>
	    <li><span class="label label-planned">Planned</span></li>
    </ul>
    <hr/>
</div>

The UML notation uses "attributes" and "operations" to show the contents of a class. However, often a class or a source file has several groups of attributes + methods, clustered per business role, or other criteria. E.g.:

		//////////////////////////////////////////////////////
		// parse logic
		//////////////////////////////////////////////////////
		
		protected Parser parser;
		
		protected int contentLength;
		
		// ...
		
		public void parse(String content) {
			// ...
		}
		
		protected void parseInternal();
		
		protected void parseUtil();
		
		// ...
		
		//////////////////////////////////////////////////////
		// socket communication logic
		//////////////////////////////////////////////////////
		
		protected Socket socket;
		
		protected boolean connected;
		
		// ...
		
		public void connect() {
			// ...
		}
		
		protected void checkLogin();
		
		protected void logConnection();
		
		// ...
		
For such a case, Flower Platform could create 2 compartments: *parse logic* and *socket communication logic*, instead of the classic "attributes" and "operations" compartment. 
* The CodeSync algorithm would generate and parse the special separator blocks (i.e. `///////////////` ...).
* Dynamic compartments could be added/deleted/moved up/down from the diagram UI
* The separator patterns could be configurable; e.g. `///////////` or `/******************`, or `//########################`etc.  