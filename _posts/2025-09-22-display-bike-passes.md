---
layout: post
title: Display Bike Passes
date: 2025-09-22 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/21/display-registration.html) we displayed registrations of eBikes and components.
Now let's [load all bike passes](https://github.com/open-ebike/open-ebike-frontend/issues/8) associated with an eBike. To do so we need to

* [add a bike pass service](https://github.com/open-ebike/open-ebike-frontend/commit/9386263e7afe0655f2c3845fc38e6448fab9a595) to fetch all the bike passes associated with an eBike
* [display the bike passes](https://github.com/open-ebike/open-ebike-frontend/commit/5dfce998ea5ce5fdb1724acc47bbda16fcca1340) on the eBike details page

![web-app-bike-passes.png](/assets/2025-09-22/web-app-bike-passes.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/09/23/display-bulk-installation-reports.html) we will display bulk installation reports associated with an eBike.