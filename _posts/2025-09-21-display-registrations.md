---
layout: post
title: Display Registrations
date: 2025-09-21 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/20/display-activity-details.html) we displayed the details of a selected activity.
Now let's [load all registrations a user has performed](https://github.com/open-ebike/open-ebike-frontend/issues/7). To do so we need to

* [add an eBike registrations service](https://github.com/open-ebike/open-ebike-frontend/commit/16d8e5926f59ed61727dd36f8a8cf40789e93861) to fetch all the registrations a user has performed
* [add a registrations page](https://github.com/open-ebike/open-ebike-frontend/commit/cedb0d268cf2a9a3ba3d29f2be2f42b030f69d64) to display the registrations as a list

Since registrations can be performed for both eBike and components we add put it on separate page which is reachable from the menu.
To simplify the navigation we also add links from a registered eBike to the eBike details page.  

![web-activity-details.png](/assets/2025-09-21/web-app-registrations.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/09/22/display-bike-passes.html) we will display bike passes associated with an eBike.