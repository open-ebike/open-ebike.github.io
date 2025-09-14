---
layout: post
title: Grant access to data
date: 2025-09-13 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/12/register-for-data-access.html) we learned how to register for data access via [the Bosch eBike portal](https://portal.bosch-ebike.com) (taking the role of a data recipient).

# Step 3: Grant access to data

Now we need to grant access to the data generated with our eBike (taking the role of a user).
Remember that we are both the user and the data recipient at the same time in this sample project.

## Log in or sign uo with SingleKey ID

First of all we need to log in or sign up with our SingleKey ID at [https://flow.bosch-ebike.com](https://flow.bosch-ebike.com).
Since we already created an SingleKey ID account in the previous post we can simply log in.

![data-act-at-bosch-ebike-systems.png](/assets/2025-09-13/data-act-at-bosch-ebike-systems.png)

## Grant data access for a given client application

After logging in we can see a list of eBikes that are associated with our SingleKey ID account.
For each eBike we can decide which client application we want to grant access to.
Let's select the client application we created in the previous post and grant access to our eBike's data.

![your-rider-your-data-your-choice.png](/assets/2025-09-13/your-rider-your-data-your-choice.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/09/14/retrieve-data-via-rest-calls) we will learn how to retrieve data via REST calls.