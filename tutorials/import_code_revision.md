---
layout: page
title: "Import Code"
tagline: "Import Code From Revision Systems (SVN)"
---
{% include JB/setup %}

The ergonomics and UI of the SVN features are inspired from the [Eclipse](http://www.eclipse.org "Eclipse") and its excellent SVN plugin: [Subclipse](http://subclipse.tigris.org/ "Subclipse"). 
Flower Dev Center offers a subset of the features available in the Subclipse plugin.

###SVN Perspective and Views

Similar to Eclipse, Fower Dev Center gives you the possibility to layout the components in your workbench by using the **perspectives** and **views** concepts.

For switching to **SVN Repository Exploring Perspective** go to application menu bar > Window > Switch Perspective > and choose SVN Repository Exploring Perspective.

![Switch to SVN perspective]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/switch_to_svn_perspective.png)

By default the SVN Repository Exploring Perspective shows the following **views**:

* **SVN Repositories**
* **SVN History**
* **SVN Console**

![SVN Views]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/svn_views.png)

Like in Eclipse, you can use the **SVN views** also being in another perspective than SVN perspective: Window > Show View > ...:

![Open SVN Views]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/open_svn_views.png)

For **removing a view** use the **red X** button that appears when you go with the mouse over the view tab title, or **click the middle mouse button**, over the tab.

![Close View]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/close_view.png)

You can change the position of the views: click the tab title and **drag and drop** them in the desired location.

![Drag View]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/drag_view.png) 
![]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/arrow_right.png) 
![Drop View]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/drop_view.png)

###Add/Browse SVN Repositories

From the SVN Repository Exploring view **add a new SVN repository** by **right clicking** on the view > New > Repository Location...

![Add SVN Repository Menu Entry]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/add_svn_repository_menu_entry.png) 
![]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/arrow_right.png) 
![Add SVN Repository Window]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/add_svn_repository_window.png)

Once you have created the repositories you can **browse** through them using the same view. 

![Browse SVN repository]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/browse_svn_repository.png)

In this view, by **right clicking** on your repository elements (repositories, folders, files) you can find various **actions**.

![SVN Repository context menu actions]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/svn_repository_context_menu_actions.png)

###Checkout a Project

For checking out a project, in the **SVN Repositories view**, **right click on the project** you want to do the checkout > **Checkout**

![Checkout menu entry]({{ BASE_PATH }}/assets/imgs/tutorials/rev_system/checkout_menu_entry.png)

After that you need to select the **name** and **location** of the new project and other various **SVN related parameters**: revision, etc.

