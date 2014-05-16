---
layout: page
group: subconcept
parent-id: mobile

title: "Server Accounts screen"
labels: [in-progress]
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---

{% include JB/setup %}
Server accounts screen is used to manage the list of server accounts. It can be opened by clicking on the **Open Accounts** button.

<img class="img-thumbnail center-block" src="server_accounts.png"/>

## New Server Account
To create a new Server account, use the **Add Server Account** action.

<img class="img-thumbnail center-block" src="add_server_account.png"/>

## Edit Server Account
To edit a server account, click on the account you want to edit, this will open the [Edit Server Account](edit_server_account.html) screen.

## Select Default Server Account
To mark a server account as the default one, the checkbox, next to it, must be selected.
The next time application starts it will connect with the selected default account.


