---
layout: post
title: Display Diagnosis Field Data (BES2)
date: 2025-10-20 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/19/display-diagnosis-events.html) we displayed diagnosis events.
Now let's [load diagnosis events](https://github.com/open-ebike/open-ebike-frontend/issues/30) via the [Diagnosis Field Data API
](https://portal.bosch-ebike.com/data-act/app#/smart-system-diagnosis-field-data) and display them. 
To do so we need to

* [add a diagnosis field data service](https://github.com/open-ebike/open-ebike-frontend/commit/1775174113ea2fbbde5746c09e8f1ea487d98d54) to fetch the diagnosis field data of a given component
* [add mock data](https://github.com/open-ebike/open-ebike-frontend/commit/d5b6ba8b39b8187bb8856c61ad7a4e3dbfa5d83a) for local development
* [display diagnosis events](https://github.com/open-ebike/open-ebike-frontend/commit/5230d1239018a35bf7ce342182d548b6044c8d57) on the component details page

![web-app-diagnosis-events.png](/assets/2025-10-20/web-app-diagnosis-field-data.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/10/21/display-installation-reports.html) we will display installation reports of an eBike.