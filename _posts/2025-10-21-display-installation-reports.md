---
layout: post
title: Display Installation Reports (BES2)
date: 2025-10-21 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/20/display-diagnosis-field-data.html) we displayed diagnosis field data.
Now let's [load installation reports](https://github.com/open-ebike/open-ebike-frontend/issues/31) via the [Release Management API (eBike System 2)
](https://portal.bosch-ebike.com/data-act/app#/ebike-system-2-release-management) and display them. 
To do so we need to

* [add a release management service](https://github.com/open-ebike/open-ebike-frontend/commit/07c0954975a1aaff5e7f2f39d69feb9425214005) to fetch all the installation reports of a given eBike
* [add mock data](https://github.com/open-ebike/open-ebike-frontend/commit/279da695365896f00d388b56feb4ae3496171f46) for local development
* [display installation reports](https://github.com/open-ebike/open-ebike-frontend/commit/c4c5702d7d6e3d6871afc656856f6e8090d28bbf) on the eBike details page

![web-app-diagnosis-events.png](/assets/2025-10-20/web-app-diagnosis-field-data.png)
