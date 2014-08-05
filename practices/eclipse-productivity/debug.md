---
layout: page
group: subconcept
parent-id: eclipse-productivity

title: "Debug Eclipse"
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

* **Debugging** allows us to run a program interactively while ``watching the source code`` and the variables during the execution.

* By **breakpoints** in the source code we specify where the execution of the program should **stop**. To stop the execution only if a field is read or modified, we can specify **watchpoints**.

* **Breakpoints** and **watchpoints** can be summarized as stop points.

* Once the **program is stopped** we can investigate ``variables, change their content, etc``. 
	
## How?
* <font size="3"><b>First step:</b></font> We must set **breakpoints**. To set breakpoints in our source code we can *right-click* in the small **left margin** in our source code editor and *select* ``Toggle Breakpoint``. Alternatively we can *double-click* on this position or we can press <span class="label label-success">CTRL+SHIFT+B</span>.
	
<img class="img-thumbnail center-block" src="breakpoint.png"/>

**The Breakpoints view** allows us to delete and deactivate stop points, i.e. ``breakpoints and watchpoints`` and to modify their *properties*. 

<img class="img-thumbnail center-block" src="breakpoints.png"/>

We can *uncheck* the **breapoints** we want to skip or to **skip all**:

<img class="img-thumbnail center-block" src="skip-breakpoints.png"/>

* <font size="3"><b>Second step:</b></font> We press the **debug arrow button**, as we can see in image below, and select our **Run Configuration**:

<img class="img-thumbnail center-block" src="debug.png"/>

<h4><span class="label label-warning"><b><font size="3">Warning:</font></b>  If we have not defined any breakpoints, this will run our program as normal.</span></h4><br>

* <font size="3"><b>Third step:</b></font> After we pressed *debug button*, Eclipse asks us if we want to switch to the **Debug perspective** once a stop point is reached. Answer Yes in the corresponding dialog. 

<img class="img-thumbnail center-block" src="debug-dialog.png"/>

* <font size="3"><b>Fourth step:</b></font> We can now **debug** our *code*:

<img class="img-thumbnail center-block" src="debugging-perspective.png"/>

* <font size="3"><b>Fifth step:</b></font> To ``debug``, we must know how to control the program:

We can use the <span class="label label-success">F5</span>, <span class="label label-success">F6</span>, <span class="label label-success">F7</span> and <span class="label label-success">F8</span> key to **step** through our *coding*. The **meaning** of these *keys* is explained in the following **table**:

 <img class="img-thumbnail center-block" src="table-controls.png"/>
 
**The following picture** displays the **buttons** and their related ``keyboard shortcuts``:
 
 <img class="img-thumbnail center-block" src="buttons.png"/>
 
* <font size="3"><b>Sixth step:</b></font> We can evaluate variables from **Variables view** which displays ``fields`` and ``local variables`` from the current executing **stack**.
<h4><span class="label label-info"><b>Info:</b> We need to run the <b>debugger</b> to see the variables in this view.</span></h4><br>
 
 <img class="img-thumbnail center-block" src="variables.png"/>

**The Variables** view allows you to ``change the values`` assigned to your *variable* at runtime:

<img class="img-thumbnail center-block" src="variables-change.png"/>

##Remote debugging 

* **Step 1**: We need to go to <span class="label label-success">Run -> Debug Configurations</span>:

<img class="img-thumbnail center-block" src="remote-step1.png"/>

* **Step 2**: Then we create a new ``Remote Java Application configuration``:

<img class="img-thumbnail center-block" src="remote-step2.png"/>

* **Step 3**: We ``configure`` the remote application's **details**:

<img class="img-thumbnail center-block" src="remote-step3.png"/>

* **Step 4**: We add this **launch configuration** to ``favorites menu``: 

<img class="img-thumbnail center-block" src="remote-step4.png"/>

<h4><span class="label label-warning"><b><font size="3">Warning:</font></b>Remote debugging requires that we have the project which is debugged, available in our Eclipse. </span></h4><br>
