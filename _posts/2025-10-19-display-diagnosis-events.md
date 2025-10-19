---
layout: post
title: Display Diagnosis Events (BES2)
date: 2025-10-19 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/17/display-statistics.html) we displayed activity statistics.
Now let's [load diagnosis events](https://github.com/open-ebike/open-ebike-frontend/issues/29) via the [Diagnosis Event API
](https://portal.bosch-ebike.com/data-act/app#/ebike-system-2-diagnosis-event) and display them. 
To do so we need to

* [add a diagnosis event service](https://github.com/open-ebike/open-ebike-frontend/commit/9af8ef9ef001c1a8e70cfa0c83c2d2d02e88dd24) to fetch all diagnosis events of a given component
* [add mock data](https://github.com/open-ebike/open-ebike-frontend/commit/cad2145758044498589492f8072bf15462e41ba1) for local development
* [display diagnosis events](https://github.com/open-ebike/open-ebike-frontend/commit/3181b18bf060d42845c868d16b5d36c205eceab9) on the component details page

![web-app-diagnosis-events.png](/assets/2025-10-19/web-app-diagnosis-events.png)