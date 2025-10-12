---
layout: post
title: Implement Authentication (BES2)
date: 2025-10-11 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/10/retrieve-data-via-rest-calls-bes2.html) we learned how to authenticate with eBike Connect and how to access our data via REST calls. 
Now let's continue with [the user authentication with eBike Connect](https://github.com/open-ebike/open-ebike-frontend/issues/22) inside our web app.

First, let's [extend the authentication to support eBike Connect](https://github.com/open-ebike/open-ebike-frontend/commit/5361be0be42721258fad217d409b64518e0f8be4). 
To do so we need to adjust the authentication service and add another button to the login page.

![web-app-bes2-login.png](/assets/2025-10-11/web-app-bes2-login.png)

Second, let's [update the onboarding guide](https://github.com/open-ebike/open-ebike-frontend/commit/5b18bbad5add332ea290c83bbd5cb80f0607fac9) to explain the new authentication option.

![web-app-onboarding-guide.png](/assets/2025-10-11/web-app-onboarding-guide.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/10/12/display-ebikes.html) we will load and display our first data point.