---
layout: post
title: Make Client ID Configurable
date: 2025-10-03 07:00:00 -0200
categories: [devlog]
---

In [the previous post](https://open-ebike.github.io/devlog/2025/10/02/use-firebase-function0to-proxy-api-calls.html) we managed to address the issue with same-origin policy we faced when calling Bosch EUDA APIs directly from our web app by using Firebase Functions.

Now that the deployed web app can call the EUDA APIs one problem remains: The client ID is currently hard-coded.
Based on the legal text a user is entitled to read their own data only.
That means we need to [make the client credentials configurable at runtime](https://github.com/open-ebike/open-ebike-frontend/issues/17) so that each user can specify the client ID of their client application.

To do so we need to
* [remove hard-coded client IDs](https://github.com/open-ebike/open-ebike-frontend/commit/7e53a5d9935eef88b9fc6f9fd551e481570b191f) that were specified in `environment` files
* [remove the configuration of the OAuth service during the app initialization](https://github.com/open-ebike/open-ebike-frontend/commit/84dca96b6d953770758cc5d2d3ea2f32e59fc5b8)

By [adding a dedicated login page](https://github.com/open-ebike/open-ebike-frontend/commit/ed9a2a4457f96f27f2dbe1447d6c17c23677d0a0) to give users the chance to enter their individual client ID. 

![web-app-configurable-client-id.png](/assets/2025-10-03/web-app-configurable-client-id.png)

Since we now skip the configuration of the OAuth service during the bootstrapping phase we need to manually handle the two phases of the [authorization code flow](https://auth0.com/docs/get-started/authentication-and-authorization-flow/authorization-code-flow).

**Retrieve the authorization code**

After the user has specified the client ID and clicked on the `Save and Login` button on the login page the OAuth service is configured using the provided client ID. The configuration comprises
* setting the client ID in the auth config
* configuring the auth config itself
* loading the discovery document
* storing the client ID value in `localStorage` since we need it in the second phase (and the page will reload until then)

```typescript
onSaveAndLoginClicked(clientId: string) {
  this.authenticationService.configure(clientId).then(() => {
    this.authenticationService.login();
  });
}
```

```typescript
async configure(clientId: string): Promise<void> {
  this.clientId.set(clientId);

  // Set client ID auth config
  const authConfig = { ...environment.authConfig };
  authConfig.clientId = clientId;

  // Configure auth config
  this.oauthService.configure(authConfig);

  // Fetch token endpoint
  await this.oauthService.loadDiscoveryDocument();

  // Store client ID
  localStorage.setItem('clientId', clientId);
}

login() {
  this.oauthService.initCodeFlow();
}
```

**Exchange the authorization code for an access token**

We want the user to land on the `/home` page after successful login.
To ensure this behavior we specify the `redirectUri` in the `environment.firebase-hosting.ts` file accordingly.

```ts
export const environment = {
  redirectUri: 'https://open-ebike.web.app/home'
}
```

Since the user will be redirected to the `/home` page we need to continue the second phase of the authorization code flow during the component's initialization. Here we need to
* restore the client ID we previously stored in `localStorage`
* running the login code flow which exchanges the authorization code for a bearer token

```typescript
async ngOnInit() {
  await this.authenticationService.restoreConfig();
  await this.authenticationService.processLoginCallback();
}
```

```typescript
async processLoginCallback() {
  await this.oauthService.tryLoginCodeFlow();
}
```
