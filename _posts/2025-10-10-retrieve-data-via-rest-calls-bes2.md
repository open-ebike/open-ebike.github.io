---
layout: post
title: Retrieve Data via REST calls (BES2)
date: 2025-10-10 07:00:00 -0200
categories: [devlog]
---

Up until now we have retrieved and displayed data generated with a Bosch-powered eBike with Smart System (generation 3).
Let's do the same for Bosch eBike System 2 (generation 2) to make our web app useful for even more users.

First of all we need to register for eBike Connect which can be done via [https://www.ebike-connect.com/registration](https://www.ebike-connect.com/registration).

![ebike-connect-login.png](/assets/2025-10-10/ebike-connect-login.png)

After we have done so we can
* [extend the Bruno collection](https://github.com/open-ebike/open-ebike-backend/commit/ce2f652924e4239583b6dac89cef8515adc106b0) and
* [extend the Jetbrains http client](https://github.com/open-ebike/open-ebike-backend/commit/1623e6aba10384b4a22159425df3235dab23dee9) 

that we have created in [an earlier post](https://open-ebike.github.io/devlog/2025/09/14/retrieve-data-via-rest-calls.html) by the new endpoints.

**Note:** As pointed out in [the API documentation](https://portal.bosch-ebike.com/data-act/app#/ebike-system-2-bike-profile) it is crucial to [add the query parameter](https://github.com/open-ebike/open-ebike-backend/commit/41f73a2b4abc039c583f973e45fbd48c3e24ce22) `kc_idp_hint=ebike-connect` to the authentication request.

---

In [the next post](https://open-ebike.github.io/devlog/2025/10/11/implement-authentication-bes2.html) we will integrate the authentication for eBike Connect into our web app.