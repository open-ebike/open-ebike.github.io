---
layout: post
title: Display Hubs (COBI)
date: 2025-10-24 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/23/implement-authentication-cobi.html) we implemented a user authentication for COBI.
Now that the user can log in let's [load their hubs](https://github.com/open-ebike/open-ebike-frontend/issues/34) via the [COBI Huba & Activity API](https://portal.bosch-ebike.com/data-act/app#/cobi-hub-activity) and display them. 
To do so we need to

* [add a hub service](https://github.com/open-ebike/open-ebike-frontend/commit/7f1cf1301865c520e43e32df261e33210d886d79) to fetch the COBI hubs of the logged-in user
* [add mock data](https://github.com/open-ebike/open-ebike-frontend/commit/f31ca5d5873c6feaff0f9f19af511eea69c63de0) for local development
* [add a separate hubs page](https://github.com/open-ebike/open-ebike-frontend/commit/3d2f3e2e7a7157ba98e02cb8c65e4fd35dd76607) to display the hubs as a list

![web-app-hubs.png](/assets/2025-10-24/web-app-hubs.png)