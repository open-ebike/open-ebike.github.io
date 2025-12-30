---
layout: post
title: Display Yearly Achievements
date: 2025-12-30 07:00:00 -0200
categories: [devlog]
---

In the previous posts we [displayed achievements](https://open-ebike.github.io/devlog/2025/12/28/display-achievements.html) and [added social sharing](https://open-ebike.github.io/devlog/2025/12/29/add-social-sharing.html).

Now let's [add yearly achievements](https://github.com/open-ebike/open-ebike-frontend/issues/38) that either sum up values across a year (e.g. total distance travled) or find a maximum (e.g. maximum altitude).

To do so we need to

* [add a yearly achievement service](https://github.com/open-ebike/open-ebike-frontend/commit/5267b29e787002e3b531f0c02e2b81fdb1d733e3) that calculates yearly achievements based on activities
* [add a yearly achievement page](https://github.com/open-ebike/open-ebike-frontend/commit/d3f0db39c6dabee3eecbe595a7652322f7bece1b) that display yearly achievements
* [add a grid component](https://github.com/open-ebike/open-ebike-frontend/commit/7b6c4028d006f57bfe32fa3b70d3cd8f9164cf70) that lists available years
* [add the selected year to the URL path](https://github.com/open-ebike/open-ebike-frontend/commit/723f2c1d2c7c5598babd7e49b8392c8449e6adb2)

To reuse the sharing feature that we implemented previously we also need to
* [add a dedicated share picture service](https://github.com/open-ebike/open-ebike-frontend/commit/040c81f47606bac65949649bdf6f0e8338bfee01)
* [add a share picture component](https://github.com/open-ebike/open-ebike-frontend/commit/db04b93752f466fc1a4d7e98c7bd8a882817739b)
* [reuse the share picture component](https://github.com/open-ebike/open-ebike-frontend/commit/ffd209d4f684e826bf7215ed04a7a598a6ca541c)
* [add the sharing bottom sheet to yearly achievements](https://github.com/open-ebike/open-ebike-frontend/commit/1090ce94f55fc7f94da96285eeb823055b875745)

Some sample achievements can be based on 
* [basic values](https://github.com/open-ebike/open-ebike-frontend/commit/36429fdb48a24fff215735ec325b54e892f62150), e.g. total activity count, total distance, total elevation gain or total calories burned
* [based on maximum altitude](https://github.com/open-ebike/open-ebike-frontend/commit/711486bdb83918e947b2af3cf044a64cb0c7e3e0)
* [based on total duration](https://github.com/open-ebike/open-ebike-frontend/commit/3402691567eab1123c830a3d58d8890efd09911a)

Furthermore, we need to
* [add an initialization of yearly achievements](https://github.com/open-ebike/open-ebike-frontend/commit/e0fc8b8cdb25c405e57811c31222737aa8655903)
* [add an evaluation of yearly achievements](https://github.com/open-ebike/open-ebike-frontend/commit/b815be66ee878f86f93249ebc376c6d2e55fb143)
* [add a carousel to display yearly achievements](https://github.com/open-ebike/open-ebike-frontend/commit/bf098f2d5a8d087301f935757370bb545b3eeb62)

For user convenience, we
* [highlight the selected year](https://github.com/open-ebike/open-ebike-frontend/commit/fcf827d3dec2fa85c8e5025aa064e33b7591212c)
* [disable selection of year without any activity](https://github.com/open-ebike/open-ebike-frontend/commit/28c3983b766186d4bced1a91f023eb55bb3726a9)
* [automatically select a year of there is only one with activities](https://github.com/open-ebike/open-ebike-frontend/commit/62bb3b7adf6e4f5074ce85af400dfa1c4d818fd2)
* [automatically unselect a year if it has no activities](https://github.com/open-ebike/open-ebike-frontend/commit/6b8c6bbce8c0d9e7eb17e16a3a5c97e79e978522)

We display yearly  achievements in a carousel so that the user can swipe through them after selecting the year.

![web-app-yearly-achievements.png](/assets/2025-12-30/web-app-yearly-achievements.png)

Similar to the social sharing feature that we introduced in [the previous post](https://open-ebike.github.io/devlog/2025/12/29/add-social-sharing.html) we now add a sharing option for yearly achievements.

![web-app-yearly-achievements-sharing.png](/assets/2025-12-30/web-app-yearly-achievements-sharing.png)
