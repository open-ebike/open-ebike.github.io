---
layout: post
title: Display Onboarding Guide
date: 2025-10-06 07:00:00 -0200
categories: [devlog]
---

To help the user to actually use the app let's [add an onboarding guide](https://github.com/open-ebike/open-ebike-frontend/issues/19) that helps them to follow the required steps to log in.

The [onboarding guide](https://github.com/open-ebike/open-ebike-frontend/commit/99c1c6fa2682bb955b98b0f1b5bfd665c25ab839) should contain these setps

* steps 1 and 2: creating a SingleKey ID account and using the Bosch eBike Flow app to track data - as described in [this post](https://open-ebike.github.io/devlog/2025/09/11/generate-data-using-a-bosch-powered-ebike.html)
* step 3: requesting data access - as described in [this post](https://open-ebike.github.io/devlog/2025/09/12/register-for-data-access.html) - including the configuration of the client application
* step 4: granting data access - as described in [this post](https://open-ebike.github.io/devlog/2025/09/13/grant-access-to-data.html)
* step 5: logging in using the individual client ID - as described in [this post](https://open-ebike.github.io/devlog/2025/10/03/make-client-id-configurable.html)

![web-app-onboarding-guide.png](/assets/2025-10-06/web-app-onboarding-guide.png)

Additionally let's add [a contact page](https://github.com/open-ebike/open-ebike-frontend/commit/f4622b19dae0d536de370272f8b6a83b0e2cd403) and [an imprint](https://github.com/open-ebike/open-ebike-frontend/commit/3d35e904bc7a6b4ad7f72aaa2f0680e81f4a1083) and link it in the toolbar menu as well as in the footer.