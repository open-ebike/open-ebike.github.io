---
layout: post
title: Cache Fetched Data
date: 2026-01-01 07:00:00 -0200
categories: [devlog]
---

Currently, data retrieved from the Bosch eBike System EUDA API is fetched each time the user opens a page.
This can lead to long loading times, especially if there is a lot of data to fetch, first and foremost activities.
To improve loading times and reduce unnecessary API calls.

The idea is to cache fetched data locally so that subsequent visits to the same page load data from the local cache instead of fetching it again from the API.
To accomplish this we will use the [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) available in modern web browsers.
We will use [Dexie.js](https://dexie.org/) a popular wrapper library for IndexedDB that simplifies its usage.
Data will be fetched on app start as well as when the user manually triggers a data refresh.

Let's build a proof-of-concept for the BES3 activity service. 
To do so we need to

* [add caching](https://github.com/open-ebike/open-ebike-frontend/commit/8dad2deb85a4c1f1b5479abd97b34441721f3043)  
* [display a progress bar](https://github.com/open-ebike/open-ebike-frontend/commit/4b9a62685e37e19872cc3490bcd399a244964e13) that indicates how many activities have been cached so far
* [disable toolbar links and home page tiles](https://github.com/open-ebike/open-ebike-frontend/commit/ff0e6c007e81058c807f362693be8157e88acebd) which require data while caching is in progress 
* [use the cached data](https://github.com/open-ebike/open-ebike-frontend/commit/d5df2a75526d12faf2777cf47bacf0a49cca77c3) instead of calling the API
* [display a snackbar](https://github.com/open-ebike/open-ebike-frontend/commit/027aa9031ced8e94e2c5d7cb7ade7e0e8d769dc1) when caching is complete

We will repeat the same steps for

* [BES3 eBike profile service](https://github.com/open-ebike/open-ebike-frontend/commit/8b8a94c2b1870bb61a1a6efd7a2fca2de2e33e39)
* [BES3 bike pass service](https://github.com/open-ebike/open-ebike-frontend/commit/9d5684825955f306d272d07268f90625820b1c1e)
* [BES3 bulk configuration service](https://github.com/open-ebike/open-ebike-frontend/commit/e3726b4c56e626959366c9b3f1430a19d1225fb3)
* [BES3 diagnosis field data service](https://github.com/open-ebike/open-ebike-frontend/commit/647f64e7f3fc5423586f621b0fa1774dc41e6695)
* [BES3 digital service book service](https://github.com/open-ebike/open-ebike-frontend/commit/d0aeee4b4192bd9de624f6b4738df20340182f55)
* [BES3 eBike registration service](https://github.com/open-ebike/open-ebike-frontend/commit/a98f6f320ac50f7c1fcfb4770c79a1d003d1121c)
* [BES3 release management service](https://github.com/open-ebike/open-ebike-frontend/commit/f30541d538082862a9365f31b798adec233bd9f8)
* [BES3 remote configuration service](https://github.com/open-ebike/open-ebike-frontend/commit/4feb774a68b3fbd409e204d16d9daaeeb0d7572c)

After data is fetched we can reactively calculate 

* [BES3 achievements](https://github.com/open-ebike/open-ebike-frontend/commit/7895b15822bdeccecef8d152e25b9199bfa09ae0)
* [BES3 yearly achievements](https://github.com/open-ebike/open-ebike-frontend/commit/b81f8be120f5a580e211533db2888b7ac3520b44)

Next, we can add caching to

* [BES2 activity service](https://github.com/open-ebike/open-ebike-frontend/commit/529ffd277fb07fb10730ca07c8dadf66461094bb)
* [BES2 eBike profile service](https://github.com/open-ebike/open-ebike-frontend/commit/439e4d3c91dd7e6bf1995fb64c1e35bb28906895)
* [BES2 diagnosis event service](https://github.com/open-ebike/open-ebike-frontend/commit/cb33be9e6bfc838bf1c56940ad8f528b38732453)
* [BES2 diagnosis field data service](https://github.com/open-ebike/open-ebike-frontend/commit/81f3af47b231674d1c8141424bf20c7f11db8f5f)
* [BES2 release management service](https://github.com/open-ebike/open-ebike-frontend/commit/6c7d7801f12f31ee3e22817336b2478442a6d7d0)
* [BES2 remote configuration service](https://github.com/open-ebike/open-ebike-frontend/commit/16f713888c773a5fcc3458d59b4190500fdb7400)

Similar to BES3 we can calculate the 

* [BES2 achievements](https://github.com/open-ebike/open-ebike-frontend/commit/2bc67daf89b70c8ee5772c8b4c2b36bd28a140b7)
* [BES2 yearly achievements](https://github.com/open-ebike/open-ebike-frontend/commit/c9545f0e01a67ddcf6a4a10cc16396f4c3cef158)

Last, we add caching to 

* [COBI hub service](https://github.com/open-ebike/open-ebike-frontend/commit/450bb0589f009470845423c98949cce269b05c17)
* [COBI activity service](https://github.com/open-ebike/open-ebike-frontend/commit/578882faf9488fc06a07874df3a924a35c38c834)

While fetching data we display a progress bar that indicates how many items have been cached so far.
Features that require data are disabled while caching is in progress.

![web-app-caching.png](/assets/2026-01-01/web-app-caching.png)