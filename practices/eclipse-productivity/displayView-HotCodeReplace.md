---
layout: page
group: subconcept
parent-id: eclipse-productivity

title: "Display View.Hot Code Replace"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

### **Design View**

The Debug perspective in Eclipse can open a **display view** that allows to enter some code for execution when we hit a breakpoint and so, we dinamically execute code related to the variables that are in scope.

<!-- more -->

#### How?

To open this view, select **Window / Show View / Other**<span class="label label-success">(ALT + SHIFT + Q,Q)</span> **/ Display**

<div style="text-align:center;"><br><img class="img-thumbnail" src="displayView/display-view-step1.png" width="420"><img class="img-thumbnail" src="displayView/display-view-step2.png" width="300" ></div>

<br>When the debugger hits a break point, we can type some code in the *Display view*. The code is executed within the context of the current debugging positions, which means that we can use **all the variables** and even **content assist**.

<br><img class="img-thumbnail" src="displayView/display-view-step3.png" >

<br>To execute our code just <code>select</code> it and <code>use the context menu</code> or <span class="label label-success">CTRL + U</span> (execute) or <span class="label label-success">CTRL + SHIFT + I</span> (inspect).

<br><img class="img-thumbnail" src="displayView/display-view-step4.png" >
 
<div class="alert alert-info"><strong>Hint:</strong> To evaluate expressions in the editor in the Debug perspective, select the entire line where the breakpoint is set, and from the context menu, select the <strong>Inspect option</strong> <span class="label label-success">(CTRL + SHIFT + I)</span> or <strong>right-clicking</strong> on the variable we are interested in.</div> 

### **Hot Code Replace**

**Hot Code Replace** lets us make changes to a Java class and see the effect immediately in a running JVM without restarting our application.

#### How it works?

If we debug a class in Java we can make changes to it without restarting JVM (*e.g: try setting a breakpoint on the second line of findAndChangeNumber(). Next, change the number to a new value. Save the file and the program will continue running with the new code*)

<div style="text-align:center;"><br><img class="img-thumbnail" src="displayView/hot-code-replace_1.png" width="420"><img class="img-thumbnail" src="displayView/hot-code-replace_2.png" width="420" height="800"></div>

#### <br>Configuring TomCat Server

To see how to configure TomCat Server search [here](../WTP.html#hot_code_swap)













