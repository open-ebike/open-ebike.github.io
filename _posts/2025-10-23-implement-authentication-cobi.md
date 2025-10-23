---
layout: post
title: Implement Authentication (COBI)
date: 2025-10-23 07:00:00 -0200
categories: [devlog]
---

After we have integrated authentication for the Smart System (BES3) and eBike System 2 (BES2) one section remains: [authentication for COBI](https://github.com/open-ebike/open-ebike-frontend/issues/33). 
Luckily, with SingleKey ID COBI uses the same authentication mechanism as Smart System (BES3) so we can reuse most of the code.

First, let's [add another authentication option](https://github.com/open-ebike/open-ebike-frontend/commit/33b91c942b8292d2e9f3d288d109d0d8e09b30c1) for COBI.
This triggers the same authentication flow as for Smart System (BES3) but sets the value of `EbikeGeneration` differently.

```html
<button
  mat-flat-button
  color="primary"
  class="button"
  [disabled]="!authenticationService.clientId()"
  (click)="onSaveAndLoginClicked(input.value, 'COBI')"
>
  {{ t("actions.login-cobi") }}
</button>
```

![web-app-cobi-login.png](/assets/2025-10-23/web-app-cobi-login.png)

Next we need to [update the onboarding guide](https://github.com/open-ebike/open-ebike-frontend/commit/7f7173077c67a20d50ee888d507ebb0a041f9e80) on the home page to include COBI as a valid login option.

![web-app-onboarding-guide.png](/assets/2025-10-11/web-app-onboarding-guide.png)