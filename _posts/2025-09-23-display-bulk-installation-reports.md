---
layout: post
title: Display Bulk Installation Reports
date: 2025-09-23 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/22/display-bike-passes.html) we displayed bike passes associated with an eBike.
Now let's [load all bulk installation reports](https://github.com/open-ebike/open-ebike-frontend/issues/9) associated with an eBike. To do so we need to

* [add a bulk configuration service](https://github.com/open-ebike/open-ebike-frontend/commit/f96c30019d480126d82ba3f4284203ac75375f6e) to fetch all the bulk installation reports associated with an eBike
* [add a tree component](https://github.com/open-ebike/open-ebike-frontend/commit/b0bbaff144367efd653bbb10cbcec1d9f1bf3765) to display complex data structures
* [display the bulk installation reports](https://github.com/open-ebike/open-ebike-frontend/commit/8b9f467e5219b63146a8cc16d9a52c1b923de1ee) on the eBike details page

![web-app-bulk-installation-reports.png](/assets/2025-09-23/web-app-bulk-installation-reports.png)


---

In [the next post](https://open-ebike.github.io/devlog/2025/09/24/display-field-data.html) we will display field data associated with a component.