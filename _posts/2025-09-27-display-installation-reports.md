---
layout: post
title: Display Installation Reports
date: 2025-09-27 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/26/display-remote-configuration-cases.html) we displayed remote configuration cases associated with an eBike.
Now let's [load all the installation reports](https://github.com/open-ebike/open-ebike-frontend/issues/13) associated with an eBike. To do so we need to

* [add a release management service](https://github.com/open-ebike/open-ebike-frontend/commit/cd5b24cf514e382d5534a9ef3453720cb34bbd96) to fetch all the installation reports associated with an eBike
* [display installation reports](https://github.com/open-ebike/open-ebike-frontend/commit/8786ebc0a2a34dd83d8057c5b288c1a0a3516180) on the eBike details page

![web-app-installation-reports.png](/assets/2025-09-27/web-app-installation-reports.png)![web-app-remote-configuration-cases.png](/assets/2025-09-26/web-app-remote-configuration-cases.png)