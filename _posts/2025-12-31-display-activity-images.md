---
layout: post
title: Display Activity Images
date: 2025-12-31 07:00:00 -0200
categories: [devlog]
---

In the previous posts we displayed [continuous achievements](https://open-ebike.github.io/devlog/2025/12/28/display-achievements.html) and [yearly achievements](https://open-ebike.github.io/devlog/2025/12/30/display-yearly-achievements.html).

To make an activity more memorable [display images along the traveled path](https://github.com/open-ebike/open-ebike-frontend/issues/39).
For now, we will use images provided by [Mapillary](https://www.mapillary.com/) a service providing street-level images via API.

The idea is to identify point on the activity path each few hundred meters.
For each point we query the Mapillary API for the closest image.
The images are then displayed on the activity map.
When the user clicks on one marker they should see a larger version of the image and be able to share it.

To do so we need to

* [add a Mapillary service](https://github.com/open-ebike/open-ebike-frontend/commit/d763021014ce494121406e1e9ae6c082c238ef23) that handles calling the Mapillary API
* [add a way to store the Mapillary access token](https://github.com/open-ebike/open-ebike-frontend/commit/43c6f9c9f041e616d613ba2095ee87d7f1f86e7a) on the config page
* [display images on the map](https://github.com/open-ebike/open-ebike-frontend/commit/14e4b23dbf14986c2593e664c1ed1ffc74ce255a) as clickable markers
* [display images on the side navigation](https://github.com/open-ebike/open-ebike-frontend/commit/2f29875ece3e1166206060d5abc680b610d55b95) alonside the activity details
* [add a bottom sheet to display the share picture](https://github.com/open-ebike/open-ebike-frontend/commit/cd3256e7ad3ad40e6d52f51a6910db21e413cd7c)
* [attribute the Mapillary service](https://github.com/open-ebike/open-ebike-frontend/commit/7f5ef6733e322c88bb1796dde80fb05b037e6a11)
* [attribute the creator of the Mapillary image](https://github.com/open-ebike/open-ebike-frontend/commit/90a9b5bbe5547f17e5d71c9d91740bffc6aab4b8)
* [add a button to toggle visibility of images](https://github.com/open-ebike/open-ebike-frontend/commit/0e2750a47d1826864b67595a1e14ba4c8f9735fc)

We display images as clickable markers directly on the map.

![web-app-activity-images.png](/assets/2025-12-31/web-app-activity-images.png)

Similar to the social sharing feature that we introduced in [an earlier post](https://open-ebike.github.io/devlog/2025/12/29/add-social-sharing.html) we now add a sharing option for images.

![web-app-activity-images-sharing.png](/assets/2025-12-31/web-app-activity-images-sharing.png)