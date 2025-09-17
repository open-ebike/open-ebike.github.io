---
layout: post
title: Implement authentication
date: 2025-09-16 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/15/implement-a-web-app.html) we implemented a frame for our web app that acts as a basis for the data we want to display. 
Now let's continue with the user authentication via SingleKey ID.

Since our web app is a public client application we will use the OAuth 2.0 authorization code flow with PKCE (Proof Key for Code Exchange) to authenticate users via SingleKey ID.
For that we need to register another client application at [https://portal.bosch-ebike.com](https://portal.bosch-ebike.com) (as described in [an earlier post](https://open-ebike.github.io/devlog/2025/09/12/register-for-data-access.html)) with the following settings:

* client application name: test-public
* login URL: http://localhost:4200/*
* redirect URL: http://localhost:4200/*
* confidential client: no

Similar to the confidential client application (as described in [an earlier post](https://open-ebike.github.io/devlog/2025/09/13/grant-access-to-data.html)) we need to grant access to the bike data.

![your-rider-your-data-your-choice.png](/assets/2025-09-16/your-rider-your-data-your-choice.png)

To be able to display user data we will [add authentication](https://github.com/open-ebike/open-ebike-frontend/issues/2) to our web app including

* [an authentication service](https://github.com/open-ebike/open-ebike-frontend/commit/0cf3180345273f7b89ab4ed70497bf55008b89dc) to utilizes [angular-oauth2-oidc](https://www.npmjs.com/package/angular-oauth2-oidc) and the public client application we just configured
* [a way to login and logout](https://github.com/open-ebike/open-ebike-frontend/commit/c0dcf7fabcf0e5a86a1ad259ad62accfe7d6e731) in the toolbar
* [a user greeting on the home page](https://github.com/open-ebike/open-ebike-frontend/commit/442fea825fd7fa0d1dc1ee795bcc39150be7121d)

![web-app-login-button.png](/assets/2025-09-16/web-app-login-button.png)

After a successful login the user is greeted by their email address.

![web-app-user-greeting.png](/assets/2025-09-16/web-app-user-greeting.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/09/17/display-ebikes.html) we will load and display our first data point.