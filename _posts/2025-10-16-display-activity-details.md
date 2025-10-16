---
layout: post
title: Display Activity Details (BES2)
date: 2025-10-16 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/15/display-activities.html) we displayed all the activities a user has performed.
Now let's [load the details of a given activity](https://github.com/open-ebike/open-ebike-frontend/issues/27) via the [Activity API (eBike System 2)
](https://portal.bosch-ebike.com/data-act/app#/ebike-system-2-activity) and display them. 
To do so we need to

* [add another endpoint in activity service](https://github.com/open-ebike/open-ebike-frontend/commit/4b66b18ae20f06089dfca05dd2e98437b641d1ef) to fetch the activity details for a given activity ID
* [add mock data](https://github.com/open-ebike/open-ebike-frontend/commit/ad09f14647c7e697b8d450833c3e02b511c644ff) for local development
* [display the activity details in a sidenav](https://github.com/open-ebike/open-ebike-frontend/commit/9d4237ec90040599650cc0a9632537c86f7814f5) that appear like part of the activity summary
* [display activity details](https://github.com/open-ebike/open-ebike-frontend/commit/618077d4b047ad2563a447535146bf5c2a953608) in the activities page
* [display activity coordinates on a map](https://github.com/open-ebike/open-ebike-frontend/commit/4f29cbbd141f3d3a143a8e42f61620b72174d6b3)

Note that in contrast to the [Activity Records API (Smart System)
](https://portal.bosch-ebike.com/data-act/app#/smart-system-activity) most attributes of activity details belong to the activity itself.
Details of trip such as altitude and coordinates are stored in nested arrays.

![web-app-activity-details.png](/assets/2025-10-16/web-app-activity-details.png)