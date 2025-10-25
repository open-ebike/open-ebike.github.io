---
layout: post
title: Display Activities (COBI)
date: 2025-10-25 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/24/display-hubs.html) we displayed COBI hubs.
Now let's [load activities](https://github.com/open-ebike/open-ebike-frontend/issues/35) via the [COBI Huba & Activity API](https://portal.bosch-ebike.com/data-act/app#/cobi-hub-activity) and display them. 
To do so we need to

* [add an activity service](https://github.com/open-ebike/open-ebike-frontend/commit/9e32cd696c79e98d405c210940e9146d196035d4) to fetch the COBI activities of the logged-in user
* [add mock data](https://github.com/open-ebike/open-ebike-frontend/commit/cba33879322752c78013992abc32154ae4e09820) for local development
* [add a separate activities page](https://github.com/open-ebike/open-ebike-frontend/commit/e4d7540f4e68c88b4a05fa065b4b8e466db1768a) to display the activities as a list

![web-app-activities.png](/assets/2025-10-25/web-app-activities.png)