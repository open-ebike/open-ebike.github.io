---
layout: post
title: Display field data
date: 2025-09-24 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/23/display-bulk-installation-reports.html) we displayed bulk installation reports associated with an eBike.
Now let's [load field data](https://github.com/open-ebike/open-ebike-frontend/issues/10) associated with a component. To do so we need to

* [add a diagnosis field data service](https://github.com/open-ebike/open-ebike-frontend/commit/46148097056a36d4b6545b3e359c5ea5d35ae8d8) to fetch the field data associated with a component
* [add a separate component details pags](https://github.com/open-ebike/open-ebike-frontend/commit/b27e5fd7cead1e9780c62cfb00c195af39aefb45) to display a components and its attributes
* [display the field](https://github.com/open-ebike/open-ebike-frontend/commit/4bce57521517450a11f26f1669f8471248983390) on the component details page

![web-app-field-data.png](/assets/2025-09-24/web-app-field-data.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/09/25/display-service-book.html) we will display the service book associated with an eBike.