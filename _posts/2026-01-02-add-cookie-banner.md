---
layout: post
title: Add Cookie Banner
date: 2026-01-02 07:00:00 -0200
categories: [devlog]
---

To comply with privacy regulations such as [General Data Protection Regulation (GDPR)](https://eur-lex.europa.eu/eli/reg/2016/679/oj/eng) and [ePrivacy Directive](https://eur-lex.europa.eu/legal-content/EN/ALL/?uri=celex%3A32002L0058), we need to inform users about the use of cookies (and other ways to store data locally) and obtain their consent before storing any non-essential cookies on their devices.

To do so we need to

* [add the cookie banner](https://github.com/open-ebike/open-ebike-frontend/commit/e5013183436a042dfa21f86982645da2b9540b28) that displays types of stored data and how they are used
  * caching data in IndexedDB as described in [the previous post](https://open-ebike.github.io/devlog/2026/01/01/cache-fetched-data.html)
  * caching the client ID which needed for the login mechanism
  * Mapbox data in local storage for displaying activities on maps 
  * Mapillary data in cookies for displaying images along activities
* [make sure that the user need to make any decision](https://github.com/open-ebike/open-ebike-frontend/commit/f27e6d2998ee03784c460793003fdddc195d77d2) before closing the banner
* [disable features that require local data storage](https://github.com/open-ebike/open-ebike-frontend/commit/ff1b1941078b73957098c50c1250fad9a773a2cc) in case the user has not given consent
* [remove local storage and cookies](https://github.com/open-ebike/open-ebike-frontend/commit/b7155abc09b3972109ed109191f8f8b148890312) after the user has withdrawn consent

We display the cookie banner on the first visit to the web app and after clicking on the cookie button in the toolbar. 

![web-app-cookie-banner.png](/assets/2026-01-02/web-app-cookie-banner.png)