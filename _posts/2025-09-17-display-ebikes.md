---
layout: post
title: Display eBikes
date: 2025-09-17 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/16/implement-authentication.html) we implemented user authentication for our web app.
Now that the user can log in let's [load their eBike data and display it](https://github.com/open-ebike/open-ebike-frontend/issues/3). To do so we need to

* [add a proxy configuration](https://github.com/open-ebike/open-ebike-frontend/commit/aff24419ea0e0d8a92db04cb1ee0545664cd878a) to avoid CORS issues when accessing the Bosch eBike API
* [add an eBike profile service](https://github.com/open-ebike/open-ebike-frontend/commit/3feaeb583a583bf9efdf1bb02959f7964ff60184) to fetch the eBike profiles of the logged-in user
* [add an auth gard and an auth interceptor](https://github.com/open-ebike/open-ebike-frontend/commit/124afd8bd49f9b5f21c5d124df77e1b33ad19338) to protect routes and add the access token to API requests
* [add a separate eBikes page](https://github.com/open-ebike/open-ebike-frontend/commit/131309abd8cccbd9b1470016d67bfe083d8d7ca8) to display the eBike profiles as a list

To help the user to distinguish between multiple eBikes we display the eBike ID on each card.

![web-app-ebikes.png](/assets/2025-09-17/web-app-ebikes.png)