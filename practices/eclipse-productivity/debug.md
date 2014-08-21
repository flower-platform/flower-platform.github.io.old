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
	
<img class="img-thumbnail center-block" src="debug-images/breakpoint.png"/>

<div class="alert alert-info">A breakpoint is <strong>installed</strong> if the class has been loaded in the target VM and a breakpoint request has been successfully created at the desired location. If so, a <strong>checkmark</strong> will appear on the breakpoint</div>


**The Breakpoints view** allows us to delete and deactivate stop points, i.e. ``breakpoints and watchpoints`` and to modify their *properties*. 

<img class="img-thumbnail center-block" src="debug-images/breakpoints.png"/>

We can *uncheck* the **breakpoints** we want to skip or to **skip them all**:

<img class="img-thumbnail center-block" src="debug-images/skip-breakpoints.png"/>

* <font size="3"><b>Second step:</b></font> We press the **debug arrow button**, as we can see in image below, and select our **Run Configuration**:

<img class="img-thumbnail center-block" src="debug-images/debug.png"/>

<h4><span class="label label-warning"><b><font size="3">Warning: </font></b>  If we have not defined any breakpoints, this will run our program as normal.</span></h4><br>

* <font size="3"><b>Third step:</b></font> After we pressed *debug button*, Eclipse asks us if we want to switch to the **Debug perspective** once a stop point is reached. Answer Yes in the corresponding dialog. 

<img class="img-thumbnail center-block" src="debug-images/debug-dialog.png"/>

* <font size="3"><b>Fourth step:</b></font> We can now **debug** our *code*:

<img class="img-thumbnail center-block" src="debug-images/debugging-perspective.png"/>

* <font size="3"><b>Fifth step:</b></font> To ``debug``, we must know how to control the program:

We can use the <span class="label label-success">F5</span>, <span class="label label-success">F6</span>, <span class="label label-success">F7</span> and <span class="label label-success">F8</span> key to **step** through our *coding*. The **meaning** of these *keys* is explained in the following **table**:

 <img class="img-thumbnail center-block" src="debug-images/table-controls.png"/>
 
**The following picture** displays the **buttons** and their related ``keyboard shortcuts``:
 
 <img class="img-thumbnail center-block" src="debug-images/buttons.png"/>
 
* <font size="3"><b>Sixth step:</b></font> We can evaluate variables from **Variables view** which displays ``fields`` and ``local variables`` from the current executing **stack**.
<h4><span class="label label-info"><b>Info:</b> We need to run the <b>debugger</b> to see the variables in this view.</span></h4><br>
 
 <img class="img-thumbnail center-block" src="debug-images/variables.png"/>

**The Variables** view allows you to ``change the values`` assigned to your *variable* at runtime:

<img class="img-thumbnail center-block" src="debug-images/variables-change.png"/>

##Remote debugging 

* **Step 1**: We need to go to <span class="label label-success">Run -> Debug Configurations</span>:

<img class="img-thumbnail center-block" src="debug-images/remote-step1.png"/>

* **Step 2**: Then we create a new ``Remote Java Application configuration``:

<img class="img-thumbnail center-block" src="debug-images/remote-step2.png"/>

* **Step 3**: We ``configure`` the remote application's **details**:

<img class="img-thumbnail center-block" src="debug-images/remote-step3.png"/>

* **Step 4**: We add this **launch configuration** to ``favorites menu``: 

<img class="img-thumbnail center-block" src="debug-images/remote-step4.png"/>

<h4><span class="label label-warning"><b><font size="3">Warning: </font></b>Remote debugging requires that we have the project which is debugged, available in our Eclipse. </span></h4><br>

<div class="alert alert-danger">When remote debugging, you must pay attention to the situations when a different process is being launched (e.g. Tomcat server launches Hudson continuous integration tool, which launches an Ant build script wich launches Maven). In that case, you  must specify the debug options to Maven: add the <strong>Xdebug</strong> and <strong>Xrunjdwp:transport=dt_socket,server=y,address=5001,suspend=y</strong> parameters to Maven in your build script. Then you can debug the application using the 5001 port.</div>
##For more setup see:

* [Setup Development Environment](../dev-doc/#SetupDevelopmentEnvironment)
 
* [Configure WTP](index.html#WTP)

