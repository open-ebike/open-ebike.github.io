---
layout: post
title: Display Remote Configuration Cases (BES2)
date: 2025-10-22 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/21/display-installation-reports.html) we displayed installation reports.
Now let's [load installation reports](https://github.com/open-ebike/open-ebike-frontend/issues/32) via the [Remote Configuration API
](https://portal.bosch-ebike.com/data-act/app#/smart-system-remote-configuration) and display them. 
To do so we need to

* [add a remote configuration service](https://github.com/open-ebike/open-ebike-frontend/commit/12f830c9101ad38ee448e2237ef55878e993ac4f) to fetch all the installation reports of a given eBike
* [add mock data](https://github.com/open-ebike/open-ebike-frontend/commit/bbc4d431332b65f3916d6116458cc8182c5525ad) for local development
* [display remote configurations](https://github.com/open-ebike/open-ebike-frontend/commit/fe2e6661073fcd10476bb965b4dafb576914ff42) on the eBike details page

![web-app-remote-configuration-cases.png](/assets/2025-10-22/web-app-remote-configuration-cases.png)