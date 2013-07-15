---
layout: page
group: subconcept
parent-id: integration-with-dev-tools

title: "Issue Tracker"
#tagline: "tagline"
comments: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

`in progress`

Flower Platform (server) will integrate with the following issue trackers:

* GitHub

The data from issue trackers will be shown on [mindmap diagrams] (../mindmap-diagrams).

`idea`
Support additional issue trackers:
* Redmine
* JIRA
* Trac
* etc.

`idea`
Flower Platform might show data from issue trackers (i.e. issues) on Gantt diagrams as well. Depending on the issue tracker API, we might see on a Gantt diagram:
* the issues with time related details (planned start, end, actual start, end)
* work logs
* relations between issues (blocked by, precedes, etc.) 