---
layout: post
title: Display activity details
date: 2025-09-20 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/19/display-activities.html) we displayed all the activities a user has performed.
Now let's [load the details of a given activity](https://github.com/open-ebike/open-ebike-frontend/issues/6). To do so we need to

* [add another endpoint in activity record service](https://github.com/open-ebike/open-ebike-frontend/commit/28787fc92f1e6a431b99a2e8ff9d844911ceba7b) to fetch the activity details for a given activity ID
* [display activity details](https://github.com/open-ebike/open-ebike-frontend/commit/bd5936e7a3c1699a3b8f164448285dd6b5d43e82) in the activities page

To simplify the navigation we move the list of activity summaries to a side navigation bar that can be opened and closed by the user.
The details of the selected activity are displayed on the main page.

![web-activity-details.png](/assets/2025-09-20/web-activity-details.png)