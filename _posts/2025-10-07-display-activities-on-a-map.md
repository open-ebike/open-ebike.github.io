---
layout: post
title: Display Activities on a Map
date: 2025-10-07 07:00:00 -0200
categories: [devlog]
---

Our web app can now display all the data that we can retrieve via the [EU Data Act API of Bosch eBike Systems](https://flow.bosch-ebike.com/data-act).
Let's go beyond that and [display activities on a map](https://github.com/open-ebike/open-ebike-frontend/issues/20).

As a map library we use [Mapbox](https://www.mapbox.com/) which is also used by Bosch eBike Systems in their Flow app.
To use Mapbox you need to [create a free account](https://account.mapbox.com/auth/signup/) and get an access token.

In our web app we need to do the following steps to display activities on a map

* [add activity ID as query parameter](https://github.com/open-ebike/open-ebike-frontend/commit/ab831a3c7b3bbca5ca1d2bb9fe4f581f21435874) rather than path parameter so that the page does not reload when selecting an activity
* [add a configuration page](https://github.com/open-ebike/open-ebike-frontend/commit/3430c40ad60e399cedcf173a203bd661ba6f60a5) that lets the user enter their Mapbox access token
* [display a map](https://github.com/open-ebike/open-ebike-frontend/commit/75a29103182dc6d525befc6a14c5bc6c071b3716) on the activities page
* [display an activity](https://github.com/open-ebike/open-ebike-frontend/commit/ff468c9efdf7d725311f0ee0b8a8325ed9081e98) on the map

To do so we add a dedicated mapbox service which is able to
* build a geojson based on a list of activity details (which is the data to be displayed on the map)
* build a bounding of a list of activity details (which is needed to zoom to the right area on the map)

![web-app-activity-on-map.png](/assets/2025-10-07/web-app-activity-on-map.png)

To make this feature visible also when developing the web app locally we need to [extend mock data](https://github.com/open-ebike/open-ebike-frontend/commit/f67e5918cc4eac320d73e16d04381d1642ad2237) to contain realistic routes.

Finally, let's [add a paginator to the activities page side navigation](https://github.com/open-ebike/open-ebike-frontend/commit/e5deab6df8db41302aa1aee3346b5323ca92733e) so that the user can navigate through all activities.

![web-app-activity-paginator.png](/assets/2025-10-07/web-app-activity-paginator.png)
