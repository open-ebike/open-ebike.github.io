---
layout: post
title: Display remote configuration cases
date: 2025-09-26 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/25/display-service-book.html) we displayed the service book associated with an eBike.
Now let's [load all the remote configuration cases](https://github.com/open-ebike/open-ebike-frontend/issues/12) associated with an eBike. To do so we need to

* [add a remote configuration service](https://github.com/open-ebike/open-ebike-frontend/commit/063df3aa4f199a5af8ec9c59e7ecf2e9faedb830) to fetch all the remote configuration cases associated with an eBike
* [display remote configuration cases](https://github.com/open-ebike/open-ebike-frontend/commit/33c740cbacafb8f8efb84ed81e93f4e2bd52d54a) on the eBike details page

![web-app-remote-configuration-cases.png](/assets/2025-09-26/web-app-remote-configuration-cases.png)