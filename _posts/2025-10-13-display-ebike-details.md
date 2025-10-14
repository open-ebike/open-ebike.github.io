---
layout: post
title: Display eBike Details (BES2)
date: 2025-10-13 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/12/display-ebikes.html) we displayed a list of all eBikes associated with the logged-in user.
Now let's [load an eBike's details](https://github.com/open-ebike/open-ebike-frontend/issues/24) via the [eBike Profile API (eBike System 2)](https://portal.bosch-ebike.com/data-act/app#/ebike-system-2-bike-profile) and display them. 
To do so we need to

* [add a separate eBikes details page](https://github.com/open-ebike/open-ebike-frontend/commit/f9526eea80d28f9f48e70202820eeaa98d3f042a) to display the eBike details

Note that in contrast to the [eBike Profile API (Smart System)
](https://portal.bosch-ebike.com/data-act/app#/smart-system-bike-profile) there is no dedicated endpoint to retrieve the details of a single eBike. 

![web-app-ebike-details.png](/assets/2025-10-13/web-app-ebike-details.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/10/14/display-component-details.html) we will display component details.