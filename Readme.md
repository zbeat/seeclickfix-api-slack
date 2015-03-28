
# SeeClickFix API public Slack channel

### Problem
* We need a realtime group communication tool for third-party developers and SCF employees to communicate with each other (e.g. during a hackathon).
* Slack is the obvious choice, so we setup [seeclickfix-api.slack.com](https://seeclickfix-api.slack.com).
* Unfortunately Slack "teams" are gated, either by the email domain of the organization/company, or by invite-only. So we have to manually invite interested users, who have given us their email address. This is obviously not a scalable/viable process.

### Solution
Enter [slackin](http://rauchg.com/slackin), a server/module that enables public access to an invite-only Slack team. Think Freenode for Slack.

It provides:

1. A **landing page** we can point users, featuring a self-serve, automatic invite generator to our gated Slack channel. 
2. A **realtime badge** (`<iframe>`) to embed on any website, that shows the number of connected users (via [socket.io](http://socket.io)).
3. A **static badge** (SVG) that works well from static mediums (e.g. README file, GitHub pages).

#### Landing page

Point to http://seeclickfix-api-slack.herokuapp.com.

The image for our logo on the landing page is retrieved from the Slack API. It can be managed in the [admin settings](https://seeclickfix-api.slack.com/admin/settings) on the Slack team.

#### Realtime Badge

```html
<script async defer src="http://slackin.yourhost.com/slackin.js"></script>
```

or for the large version, append `?large`:

```html
<script async defer src="http://slackin.yourhost.com/slackin.js?large"></script>
```

#### Static Badge

```html
<img src="http://seeclickfix-api-slack.herokuapp.com/badge.svg">
```
