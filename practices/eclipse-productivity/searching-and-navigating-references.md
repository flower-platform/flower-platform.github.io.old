---
layout: page
group: subconcept
parent-id: eclipse-productivity

title: "Searching and navigating references"
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

**Searching** is an **indispensable tool** for programming. So when we need to **find** something in our project, we can use this helpful tool.
 
There are **2 ways** of searching: by **plain String (or regex)** or by **reference**.
Since java is **strongly typed**, Eclipse can search references very fast, which often comes in handy.

## How?

<h3>Simple search</h3>

If we want to use the **simple search**, we can either search in the **current file** using <span class="label label-success">(CTRL + k)</span> to find following occurrences of the selected word and <span class="label label-success">(CTRL + SHIFT + k)</span> to find previous occurrences, or we can search **globally** using <span class="label label-success">(CTRL + h)</span>. This last option will show you the <span class="label label-info">Search view</span> 

<h3>Global search</h3>

If you use the **global search**, you will be provided with other tools which will help you to **refine** your search.

You can search by a **regular expression** and **replace** all those occurrences with some other string.

<h3>Search by reference</h3>

To search by **reference**, select an item ( e.g. a method ) then press <span class="label label-success">(CTRL + SHIFT + g)</span> and it will show you in the <span class="label label-info">Search</span> tab all the occurences.

The <span class="label label-info">Search view</span> looks as it is shown below:

<img class="img-thumbnail center-block" src="search-view.png"/>

In the first **text box** you can enter the string or regular expression you want to search for. If you want to **search** by a regular expression, you have to **check** this option on the **right** side. By doing that, you can access the content assist by pressing
<span class="label label-success">(CTRL + SPACE)</span> in the first text box. This will provide you a list with all possible regex symbols.

The second **text box** allows you to search only in those files whose names match a string or a regex.

After this being done, you can either **search**, by pressing the <span class="label label-info">Search</span> button, or **search & replace** by pressing the <span class="label label-info">Replace</span> button.

Pressing the <span class="label label-info">Replace</span> button will show you the <span class="label label-info">Replace view</span> which looks as it is shown below: 

<img class="img-thumbnail center-block" src="replace-view.png"/>

Type a string or a regex here and **every occurrence** of the searched string/regex will be **replaced** with the one you entered here.

There is also a <span class="label label-info">Search tab</span> on the bottom toolbar. It looks like this:

<img class="img-thumbnail center-block" src="search-tab.png"/>

Here all the matches are shown **hierarchical**. Also on the upper right corner there are some tools that come in handy:

1. Show next match <span class="label label-success">CTRL + .</span>

2. Show previous match <span class="label label-success">CTRL + ,</span>

3. Remove selected matches <span class="label label-success">Delete</span>

4. Remove all matches

5. Expand all

6. Collapse all

7. Run the current search again <span class="label label-success">F5</span>

8. Cancel current search

9. Show previous searches

10. Pin the search view


<div class="alert alert-info">
<strong>Search and replace example:

</strong>
Lets say you have a method which is called "showEmployees" and you want to replace "show" with "hide".

<ul> 
 <li>You press <span class="label label-success">(CTRL + h)</span>, check the Regular expression on the right side, then you type in <span class="label label-default">"(show)(.*)"</span>. This will search for all strings which begin with <span class="label label-default">"show"</span> and are followed by any set of characters. Also, this will create two groups (the two expressions within brackets). This will help you replace the string.</li>
 <li>After you press the replace button on the bottom, you will see the Replace view. Here you type in <span class="label label-default">"hide$2"</span>. This will keep the second group, which in our case is any set of string (.*) and will replace everything before it with <span class="label label-default">"hide"</span>. Thus, the result will be that your method will be renamed to <span class="label label-default">"hideEmployees"</span> everywhere it appeared.</li>
</ul>

</div>

<h3>Type hierarchy</h3>

Another powerful tool is the <span class="label label-info">Type hierarchy</span>. To access it, **select** an item, <span class="label label-success">RIGHT CLICK</span> then choose <span class="label label-default">Open type hierarchy</span>. This will show you on the **left side** the class hierarchy of the selected item (method, type, class).

<h3>Call hierarchy</h3>

Using the same method you can open the <span class="label label-info">Call hierarchy</span> choosing <span class="label label-default">Open call hierarchy</span> instead of <span class="label label-default">Open type hierarchy</span>. The <span class="label label-info">Call hierarchy</span> on the bottom will make it possible to see both the <span class="label label-info">Caller hierarchy</span> and the <span class="label label-info">Callee hierarchy</span>, a both way view on the calls.