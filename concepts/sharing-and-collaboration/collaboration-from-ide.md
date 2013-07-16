---
layout: page
group: subconcept
parent-id: sharing-and-collaboration

title: "Collaboration from IDE. Peer Programming"
labels: [ideas]
#tagline: "tagline"
comments: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

The collaboration features work on data that exists on the Flower Platform server. So, prior to collaborating with another developer, we need to upload the data to the server (e.g. commit on a Git branch). When the collaboration session ends, we need to pull the data back to our IDE.

It may be interesting to share with other users *exactly* the data we are working on right now. In this case, our IDE would become a temporary server, that would allow other users to see and work with our diagrams and code. This would even allow to do **peer programming** directly on the code that we compile. I.e. another user adds code and then we compile/run the code right away in our IDE. 