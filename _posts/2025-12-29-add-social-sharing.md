---
layout: post
title: Add Social Sharing 
date: 2025-12-29 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/12/28/display-achievements.html) we displayed achievements.

Now let's [add a social sharing feature for achievements](https://github.com/open-ebike/open-ebike-frontend/issues/37)

To do so we need to

* [add a web share service](https://github.com/open-ebike/open-ebike-frontend/commit/9ca471e69fb79762a000efcaf9c0c0d47f545d7a) that calls the [web share API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Share_API) of the browser to open the native sharing options of the operating system
* [add a bottom sheet](https://github.com/open-ebike/open-ebike-frontend/commit/cd2f1597dd7bff0d43330c769f666e7360fa94a7) that contains a share button
* [add a share picture](https://github.com/open-ebike/open-ebike-frontend/commit/33da1f9b22957004553a1c202d5038b7d73a8618)
* [add a share pitcure generator](https://github.com/open-ebike/open-ebike-frontend/commit/a994c31295df2ffd8b69a968174487d3ba6657ce) so that they do not need to be designed manually for each achievement
* [differentiate between a small preview and a larger share picture](https://github.com/open-ebike/open-ebike-frontend/commit/e11d155f9c4eee7d7d0340dbb7250a7cffa8b211)

After clicking on an achievement badge we display a bottom sheet that contains a preview of the share picture and a share button.
Clicking the share button opens the native sharing options of the operating system.

![web-app-achievements-sharing.png](/assets/2025-12-29/web-app-achievements-sharing.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/12/30/display-yearly-achievements.html) we will display yearly achievements of a user.