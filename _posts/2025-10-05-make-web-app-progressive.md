---
layout: post
title: Make Web App Progressive
date: 2025-10-05 07:00:00 -0200
categories: [devlog]
---

Our web app is now available at [https://open-ebike.web.app](https://open-ebike.web.app).
Tough it looks nice on a laptop the same is not true for mobile devices. 
Let's change this by [making the web app progressive](https://github.com/open-ebike/open-ebike-frontend/issues/18) and by adjusting some UI controls for smaller devices.

While still being web apps [progressive web apps (PWAs)](https://web.dev/explore/progressive-web-apps) aim to be
* **capable** of things that native apps can do which are usually installed from Play Store or the App Store, e.g. push notifications, camera usage 
* **reliable** even if used offline
* **installable** so that it behaves more like a native app even if technically running a browser window

Now let's make our web app progressive - we can so by calling [a single command](https://angular.dev/ecosystem/service-workers/getting-started) which will create a [service worker](https://angular.dev/ecosystem/service-workers) and a web manifest.

```shell
ng add @angular/pwa
```

The service worker [defines the caching strategy of our web app](https://github.com/open-ebike/open-ebike-frontend/commit/9df9a1be30f2e7267c23a511fd2a940adf654117) in `ngsw-config.json` and needs to be registered in the application config in `src/app/app.config.ts`

```typescript
export const appConfig: ApplicationConfig = {
  providers: [
    provideServiceWorker('ngsw-worker.js', {
      enabled: !isDevMode(),
      registrationStrategy: 'registerWhenStable:30000',
    }),
  ],
};
```

The web manifest [specifies how the web app will be presented](https://github.com/open-ebike/open-ebike-frontend/commit/3966edbf7acb8a37f9e3ce19423dfc596d43cb1d) including
* its name
* maskable app icons in various resolutions (which can be easily designed at [https://maskable.app/editor](https://maskable.app/editor))
* screenshots of the app that are displayed when the user tries to install the app

One last thing to do to make the app usable on mobile devices is to [add a menu for smaller decices](https://github.com/open-ebike/open-ebike-frontend/commit/690aac7f2cf6308723f73c8ce7bcd8aa8fbb858a) that is displayed vertically.

![web-app-mobile-menu.png](/assets/2025-10-05/web-app-mobile-menu.png)

Et voilà, the web app is now installable.

Using [Lighthouse](https://developer.chrome.com/docs/lighthouse/overview) which is integrated into the Chrome browser we can analyze our app metrics such as performance, accessibility, best practices and SEO.