---
layout: post
title: Perform Small Adjustments
date: 2025-09-28 07:00:00 -0200
categories: [devlog]
---

Now that we have displayed all data provided by the [EU Data Act API of Bosch eBike Systems](https://flow.bosch-ebike.com/data-act) let's take a deep breath and do some small adjustments.

First we [add a mock server](https://github.com/open-ebike/open-ebike-frontend/commit/67e2e445acb45c0260dcc61443277d07b426f82e) that lets us run the app locally without calling the actual API.
This may be useful to develop and test upcoming features even if our Bosch eBike account does not contain all types of data. 

To make the registration state more clear we can display it [directly on the eBike pages](https://github.com/open-ebike/open-ebike-frontend/commit/3e0c95ad011ae88f9b43792a5b4247049e895d38) and the [component page](https://github.com/open-ebike/open-ebike-frontend/commit/da88b97e963e0cb5cfa3f0345f470b1cd28483b2)

![web-app-small-adjustments.png](/assets/2025-09-28/web-app-small-adjustments.png)

Also, let's [add a show-all button to the eBike details page](https://github.com/open-ebike/open-ebike-frontend/commit/25129a1bf69e42bdfde8ad1c118b377110d4e46d) to provide an easier back-navigation.

After working on this project for a week some bugs piled up that need fixing.

* [card heights may be lower](https://github.com/open-ebike/open-ebike-frontend/commit/4098bc06847b01736340451698c686dbb2f8363f) if we remove obsolete mat-action and mat-footer sections
* the side nav on the activity page needs
  * [a consistent behaviour](https://github.com/open-ebike/open-ebike-frontend/commit/714b4d8aa1600e00b992a8f9cbdf42d6ffb42ca3)
  * [a way to wait for it to be closed before updating the page](https://github.com/open-ebike/open-ebike-frontend/commit/d4c677b31c8187af83af8a44b5843e13fa285e40) when selecting an activity
  * [a consistent height](https://github.com/open-ebike/open-ebike-frontend/commit/292b1e001ce04b86deaaff1b4b1e3218014490fa) to prevent scrolling up when an activity is selected
* [the selected theme must persist](https://github.com/open-ebike/open-ebike-frontend/commit/a97d7b8a66392530f1128c3f4b6b013932f366c1) when navigating to a page with other query parameters
* [the side nav toggle button should display different texts](https://github.com/open-ebike/open-ebike-frontend/commit/5bf083521cb3aa2284e25f05886a604c9053bb29) depending on the side nav state
* [some minor typo](https://github.com/open-ebike/open-ebike-frontend/commit/5f7d03d67d03f534f818ddafffcd22a3e1a3c088) may be fixed as well

Since many pages use the same stylesheets we simplify them by [moving them into a central styelsheet](https://github.com/open-ebike/open-ebike-frontend/commit/1977d684add4d810453752f813655a7563580d66).

Last but not least let's add [links to this dev log and the GitHub organization](https://github.com/open-ebike/open-ebike-frontend/commit/dcf6fd9549b8fe96ae0168929863e4e8d4a43bed) to the footer. 