---
layout: post
title: Implement a Web App
date: 2025-09-15 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/14/retrieve-data-via-rest-calls.html) we learned how to authenticate and how to access our data via REST calls. 
Now let's continue with the implementation of a web app to display our data.

# Step 5: Implement a web app

Our web app will be built using [Angular](https://angular.dev/) and can be found on GitHub at [open-ebike/open-ebike-frontend](https://github.com/open-ebike/open-ebike-frontend).

As a foundation we will [implement an app frame](https://github.com/open-ebike/open-ebike-frontend/issues/1) that includes basic features such as

* [support for different themes](https://github.com/open-ebike/open-ebike-frontend/commit/9d3080ddb824b6034723d68d7c824b09b3765c58)
* [a service to handle themes](https://github.com/open-ebike/open-ebike-frontend/commit/18db310fa869921ca1303532c8915f3d84c67171)
* [a service to handle screen sizes](https://github.com/open-ebike/open-ebike-frontend/commit/b91dfae27bbe6f782356af0dbc8602dd93446c75)
* [a service to handle translations](https://github.com/open-ebike/open-ebike-frontend/commit/aa9cc6a442cfbf46451d81990cc11f24fd815ef7)
* [a toolbar](https://github.com/open-ebike/open-ebike-frontend/commit/6ebb469bfbbd441b172cd71bfd028efeece8f429) which will contain our menu
* [a footer](https://github.com/open-ebike/open-ebike-frontend/commit/ce57cd1a4d8e70af5c726b5433d9f4012e0cda7e) which will contain static information
* [a home page](https://github.com/open-ebike/open-ebike-frontend/commit/bb8cf9e0afb0912b16efbf5063146cf0181110a5) which will be displayed when initially loading the app
* [an app frame](https://github.com/open-ebike/open-ebike-frontend/commit/a48bda87508e0c57691c7f44b2f877a06c25cd23) bringing everything together
* [a theme switcher](https://github.com/open-ebike/open-ebike-frontend/commit/790f998babe428192343be110fce07aa8804e420) to switch between light and dark mode

![web-app-home-page.png](/assets/2025-09-15/web-app-home-page.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/09/16/implement-authentication) we will add authentication via SingleKey ID to our web app.