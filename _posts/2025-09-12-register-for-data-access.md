---
layout: post
title: Register for Data Access
date: 2025-09-12 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/11/generate-data-using-a-bosch-powered-ebike.html) we learned how to generate data using a Bosch-powered eBike. Now let's continue with the registration for data access.

# Step 2: Register for Data Access

To register for data access we as a data recipient need to follow a three-part process which includes
* log in or sign in with SingleKey ID
* accept terms and conditions for data recipients
* create a client application

## Log in or sign in with SingleKey ID

First of all we need to log in or sign up with our SingleKey ID at [https://portal.bosch-ebike.com](https://portal.bosch-ebike.com). Since we already created an SingleKey ID account in the previous post we can simply log in.

![data-act-at-bosch-ebike-systems.png](/assets/2025-09-12/data-act-at-bosch-ebike-systems.png)

## Accept terms and conditions for data recipients

Afterward, we proceed as a user (since we want to access our own data) and accept the terms and conditions. 

![data-recipient-or-data-access-profile.png](/assets/2025-09-12/data-recipient-or-data-access-profile.png)

## Create a client application

Finally, we create a client application that will be used to retrieve the data via REST calls

* client application name: test-confidential
* login URL: http://localhost:4200
* redirect URL: http://localhost:4200/*
* confidential client: yes

![manage-your-access-and-data.png](/assets/2025-09-12/manage-your-access-and-data.png)

After creating the client application we can see the client ID and client secret which we will need later for the authentication.

---

In [the next post](https://open-ebike.github.io/devlog/2025/09/13/grant-access-to-data.html) we will learn how to grant access to data.