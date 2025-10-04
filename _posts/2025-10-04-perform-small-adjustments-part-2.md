---
layout: post
title: Perform Small Adjustments (part 2)
date: 2025-10-04 07:00:00 -0200
categories: [devlog]
---

Now that we managed to
* [deploy the app to Firebase Hosting](https://open-ebike.github.io/devlog/2025/09/30/deploy-to-firebase-hosting.html)
* [enabled it to call the Bosch EUDA API using a Firebase function as a proxy](https://open-ebike.github.io/devlog/2025/10/02/use-firebase-function0to-proxy-api-calls.html) and 
* [make the client ID configurable](https://open-ebike.github.io/devlog/2025/10/03/make-client-id-configurable.html) to that it can be used by different users 

let's take a small break and fix some minor issues such as

* [some unused imports](https://github.com/open-ebike/open-ebike-frontend/commit/9973def7e4eb5872ba8c29ea2583cfa08ebbe482) of Material components
* [some Sass warnings](https://github.com/open-ebike/open-ebike-frontend/commit/272f7529b6b20524376d864b4702192efc624003) caused by a deprecated `color` function
* [a simple typo](https://github.com/open-ebike/open-ebike-frontend/commit/5c76c64b625bc2968a6aef4b4863f70ca0fabf99)
* [a misbehavior of the drawer](https://github.com/open-ebike/open-ebike-frontend/commit/bdaebd9e56bcc2157a9ff145b47fc026ba5d8c57) on the activity page
* [the missing padding on the activity oage](https://github.com/open-ebike/open-ebike-frontend/commit/07802414827b04ab53cd670ea92406abb8e5da58) which is only noticable on mobile devices
* [the closing behavior of the drawer](https://github.com/open-ebike/open-ebike-frontend/commit/4274bbb629a7bdcb3cd106e6847e557411cd83c5) on the activity page
* [missing functions in the authentication mock service](https://github.com/open-ebike/open-ebike-frontend/commit/a4d82a85b81085e4882b7cc9165c46fe99b3742d)
* [some unused imports](https://github.com/open-ebike/open-ebike-frontend/commit/759cdda390da9a2c76acf5dc042e4777a4d148b1) again
* [a height value on the activity page](https://github.com/open-ebike/open-ebike-frontend/commit/d77cc183e614f10c86759d74d05d32f8a88f28fe) again

Furthermore, we added some useful [messages for the case that an entity does not exist](https://github.com/open-ebike/open-ebike-frontend/commit/065eb862af273ec2838bd029edeb03e8415c7c5e), for example a bike pass.