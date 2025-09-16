---
layout: post
title: Retrieve data via REST calls
date: 2025-09-14 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/09/13/grant-access-to-data.html) we learned how to grant data access via [the Bosch eBike flow page](https://flow.bosch-ebike.com). Now let's continue with the actual data retrieval.

# Step 4: Retrieve data via REST calls

Browsing [https://portal.bosch-ebike.com/data-act/app#/introduction](https://portal.bosch-ebike.com/data-act/app#/introduction) we can find the API documentation for the EU Data Act interface. It comprises
* an [introduction](https://portal.bosch-ebike.com/data-act/app#/introduction) that explains the basic architecture and the steps to get access (which we already covered in [the previous post](https://open-ebike.github.io/devlog/2025/09/12/register-for-data-access.html))
* a [description how to authenticate](https://portal.bosch-ebike.com/data-act/app#/authentication) with your user credentials
* a [description of the pagination mechanism](https://portal.bosch-ebike.com/data-act/app#/pagination)
* a [description of error responses](https://portal.bosch-ebike.com/data-act/app#/error-responses)
* the [contact information for support cases](https://portal.bosch-ebike.com/data-act/app#/support)
* an [FAQ section](https://portal.bosch-ebike.com/data-act/app#/faq)

![api-documentation.png](/assets/2025-09-14/api-documentation.png)

As our first call we will retrieve all bikes that are registered to our user account using the API documentation [Smart System > eBike Profile API > List all eBikes
](https://portal.bosch-ebike.com/data-act/app#/smart-system-bike-profile/operations/list-bikes)

![list-all-ebikes.png](/assets/2025-09-14/api-list-all-ebikes.png)

There are multiple ways to call the endpoint. In the following sections we will explore

* [Bruno](#retrieve-data-data-via-bruno)
* [IntelliJ http client](#retrieve-data-data-via-intellij-http-client)

For both we need to download the [open-ebike-backend](https://github.com/open-ebike/open-ebike-backend) from GitHub which contains all necessary configuration files.

## Retrieve data via Bruno

[Bruno](https://usebruno.com) is an API client that can be used to call REST endpoints. It is available as a [desktop app](https://usebruno.com/download).
After downloading and launching Bruno we need open a collection from `open-ebike-backend/bruno/bosch-ebike-systems` which will import all available requests.

![bruno-collection.png](/assets/2025-09-14/bruno-collection.png)

We need to specify the client ID and client secret of the client application we created in [the previous post](https://open-ebike.github.io/devlog/2025/09/12/register-for-data-access.html) in the file `open-ebike-backend/bruno/.env` so that we can use them later.
(Replace the placeholders with your actual client ID and client secret.)

```ini
euda-test-confidential-client-id=euda-xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
euda-test-confidential-client-secret=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

Since we want to use the same user authentication for all REST API calls we can define it for the entire collection.
We need to configure **OAuth 2.0** with grant type **authorization code**.
The configuration is based on the client application we created in [the previous post](https://open-ebike.github.io/devlog/2025/09/12/register-for-data-access.html).
Note that client ID and client secret are referenced from the `.env` file.

* callback URL: `http://localhost:4200`
* authorization URL: `https://p9.authz.bosch.com/auth/realms/obc/protocol/openid-connect/auth`
* access token URL: `https://p9.authz.bosch.com/auth/realms/obc/protocol/openid-connect/token`
* client ID: `{{process.env.euda-test-confidential-client-id}}`
* client secret: `{{process.env.euda-test-confidential-client-secret}}`

![bruno-auth.png](/assets/2025-09-14/bruno-auth.png)

After saving the configuration we can authenticate by clicking on **Get New Access Token**.
This will open a browser window where we can log in with our SingleKey ID credentials and authorize the client application to access our data.

Finally, we can call the endpoint **List all eBikes** which will return all bikes that are registered to our user account.
You can find it in `bosch-ebike-systems > eBike Profile API > List all eBikes` in Bruno.

![bruno-list-all-ebikes.png](/assets/2025-09-14/bruno-list-all-ebikes.png)

## Retrieve data via Jetbrains http client plugin

Another way to call REST endpoints is the [Jetbrains http client plugin](https://www.jetbrains.com/help/idea/http-client-in-product-code-editor.html) which is part of IntelliJ IDEA and other JetBrains IDEs.

We need to specify the client ID and client secret of the client application we created in [the previous post](https://open-ebike.github.io/devlog/2025/09/12/register-for-data-access.html) in the file `open-ebike-backend/http/http-client.private.env.json` so that we can use them later.
(Replace the placeholders with your actual client ID and client secret.)

```json
{
  "local": {
    "euda-test-confidential-client-id": "euda-xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "euda-test-confidential-client-secret": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
  }
}
```

Since we want to use the same user authentication for all REST API calls we can define it once.
We need to configure an authentication of type **OAuth 2.0** with grant type **Authorization Code** in `open-ebike-backend/http/http-client.env.json`
The configuration is based on the client application we created in [the previous post](https://open-ebike.github.io/devlog/2025/09/12/register-for-data-access.html).
Note that client ID and client secret are referenced from file `open-ebike-backend/http/http-client.private.env.json`.

```json
{
  "local": {
    "ebike-api-url" : "https://api.bosch-ebike.com",
    "authorize-url": "https://p9.authz.bosch.com/auth/realms/obc/protocol/openid-connect/auth",
    "token-url": "https://p9.authz.bosch.com/auth/realms/obc/protocol/openid-connect/token",
    "refresh-url": "https://p9.authz.bosch.com/auth/realms/obc/protocol/openid-connect/token",
    "Security": {
      "Auth": {
        "euda-test-confidential": {
          "Type": "OAuth2",
          "Grant Type": "Authorization Code",
          "Auth URL": "{{authorize-url}}",
          "Token URL": "{{token-url}}",
          "Client ID": "{{euda-test-confidential-client-id}}",
          "Client Secret": "{{euda-test-confidential-client-secret}}",
          "Redirect URL" : "http://localhost:4200"
        }
      }
    }
  }
}
```

![jetbrains-auth.png](/assets/2025-09-14/jetbrains-auth.png)

After saving the configuration we can authenticate by clicking on the green arrow icon and on the option to use `/http/http-client.private.env.json`.
This will open a browser window where we can log in with our SingleKey ID credentials and authorize the client application to access our data.

Finally, we can call the endpoint **List all eBikes** which will return all bikes that are registered to our user account.
You can find it in the file `open-ebike-backend/http/ebike-profile.http`.

![jetbrains-list-all-ebikes.png](/assets/2025-09-14/jetbrains-list-all-ebikes.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/09/15/implement-a-web-app) we will start implementing a web app to display our data.