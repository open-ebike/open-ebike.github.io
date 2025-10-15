---
layout: post
title: Display Activity Summaries (BES2)
date: 2025-10-15 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/14/display-component-details.html) we displayed the details of a selected component.
Now let's [load all the activities a user has performed](https://github.com/open-ebike/open-ebike-frontend/issues/26) via the [Activity API (eBike System 2)
](https://portal.bosch-ebike.com/data-act/app#/ebike-system-2-activity). 
To do so we need to

* [add an activity service](https://github.com/open-ebike/open-ebike-frontend/commit/a94da1ae28d381ff9a1537272f934e2f5574807a) to fetch all the activities a user has performed on their eBikes
* [add mock data](https://github.com/open-ebike/open-ebike-frontend/commit/9fb0a2203a8152f2179651e384b6ec7b8149d1a3) for local development
* [add an activities page](https://github.com/open-ebike/open-ebike-frontend/commit/3f585100b7df2d88c6f90f236cbf785fd5df6aea) to display the activities as a list
* [display the activity summary in a sidenav](https://github.com/open-ebike/open-ebike-frontend/commit/59bd3db5754b348aee4b4f1cdb3c9634b2fbae03)

To give the user an idea about the activity we will display its name, ist start date and the traveled distance.

![web-app-activity-summary.png](/assets/2025-10-15/web-app-activity-summary.png)