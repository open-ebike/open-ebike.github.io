---
layout: post
title: Display Statistics (BES2)
date: 2025-10-17 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/16/display-activity-details.html) we displayed the details of a selected activity.
Now let's [load activity statistics](https://github.com/open-ebike/open-ebike-frontend/issues/28) via the [Activity API (eBike System 2)
](https://portal.bosch-ebike.com/data-act/app#/ebike-system-2-activity) and display them. 
To do so we need to

* [add another endpoint in activity service](https://github.com/open-ebike/open-ebike-frontend/commit/0368e830a4e4f8668c16ddd3f7fd9e5e92e4f927) to fetch the activity statistics
* [add mock data](https://github.com/open-ebike/open-ebike-frontend/commit/eb6e051e8ea2aab016881f97de169c698338c89c) for local development
* [add a statistics page](https://github.com/open-ebike/open-ebike-frontend/commit/eda024a3d37f0c8503bfc7f95f1e0b9b450558b1) to display the activities as a list
* [add a bar chart](https://github.com/open-ebike/open-ebike-frontend/commit/79270563cfc609be46f77a1b68db730b5d1be532) to display the distances of the previous 30 days

![web-app-statistics.png](/assets/2025-10-17/web-app-statistics.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/10/19/display-diagnosis-events.html) we will display diagnosis events of a component.