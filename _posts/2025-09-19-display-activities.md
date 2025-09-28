---
layout: post
title: Display Activities
date: 2025-09-19 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/18/display-ebike-details.html) we displayed all details of a given eBike including its components.
Now let's [load all the activities a user has performed](https://github.com/open-ebike/open-ebike-frontend/issues/5). To do so we need to

* [add an activity record service](https://github.com/open-ebike/open-ebike-frontend/commit/73baccff0ff2344d685cd01eb87ee7e1414f8cf8) to fetch all the activities a user has performed on their eBikes
* [add an activities page](https://github.com/open-ebike/open-ebike-frontend/commit/13faba02fbcb5a923b084a803773e509d7c645db) to display the activities as a list

To give the user an idea about the activity we will display its name, ist start date and the traveled distance.  

![web-app-activities.png](/assets/2025-09-19/web-app-activities.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/09/20/display-activity-details.html) we will display activity details of a selected activity.