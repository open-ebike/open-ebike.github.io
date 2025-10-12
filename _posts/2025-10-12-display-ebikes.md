---
layout: post
title: Display eBikes (BES2)
date: 2025-10-12 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/11/implement-authentication-bes2.html) we implemented a user authentication via **eBike Connect*.
Now that the user can log in let's [load their eBikes](https://github.com/open-ebike/open-ebike-frontend/issues/23) via the [eBike Profile API (eBike System 2)](https://portal.bosch-ebike.com/data-act/app#/ebike-system-2-bike-profile) and display them. 
To do so we need to

* [add an eBike profile service](https://github.com/open-ebike/open-ebike-frontend/commit/5de844163a1ff028c4ea241c09af7d21dd3ee4a4) to fetch the eBike profiles of the logged-in user
* [add mock data](https://github.com/open-ebike/open-ebike-frontend/commit/59b18e57f18efad13fccbc396f92401dbe34dd13) for local development
* [add a separate eBikes page](https://github.com/open-ebike/open-ebike-frontend/commit/e3617be533f31477559b4f76603b1e58e3cc77e0) to display the eBike profiles as a list

Note that in contrast to the [eBike Profile API (Smart System)
](https://portal.bosch-ebike.com/data-act/app#/smart-system-bike-profile) and eBike has no ID to distinguish it from others.

![web-app-ebikes.png](/assets/2025-10-12/web-app-ebikes.png)