---
layout: post
title: Display eBike details
date: 2025-09-18 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/17/display-ebikes.html) we displayed a list of all eBikes associated with the logged-in user.
Now let's [load an eBike's details and display it](https://github.com/open-ebike/open-ebike-frontend/issues/4). To do so we need to

* [add another endpoint in eBike profile service](https://github.com/open-ebike/open-ebike-frontend/commit/4dc426fc96e65a56db9264a0e33c256e84a02816) to fetch the eBike profile details for a given eBike ID
* [add a separate eBike details page](https://github.com/open-ebike/open-ebike-frontend/commit/18b1ee2ea8f1d0fc1fd7c4daf1b1d364abf17cd3) to display the eBike profile details including the components
* [display a list of all eBike components](https://github.com/open-ebike/open-ebike-frontend/commit/b77333a744f21d2848ef058a7ae5fa6aa158c322) in the eBike details page
* [display other attributes if an eBike](https://github.com/open-ebike/open-ebike-frontend/commit/4d16addaf0a5451985ace2e0a050c0b45d8c5154) in the eBike details page

To let the user identify the components mounted to their eBike we display serial number and part number of each component as well as other attributes and different icons.

![web-app-ebike-details.png](/assets/2025-09-18/web-app-ebike-details.png)