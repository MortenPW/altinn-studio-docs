---
title: Application arhicture profile component - Altinn Platform
linktitle: Profile
description: Description of profile component
tags: [architecture, solution]
weight: 100
---

The profile component is an ASP.Net Core MVC Application exposing REST-API to Altinn Apps.

The profile solution is now available locally at http://platform.altinn.cloud/profile/api/v1 and all resources are avaiable through endpoints defined below.

Resources: users

## /users
A user is the entity which is logged in in Altinn and performs actions for on behalf of an instance owner.

Get information about a user:

```http
/users/{userId}
```