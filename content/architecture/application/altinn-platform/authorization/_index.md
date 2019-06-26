---
title: Altinn Platform - Authorization
linktitle: Authorization
description: Description of authorization component
tags: ["solution", "architecture"]
weight: 100
alwaysopen: true
---

{{%notice warning%}}
This page is a work-in-progress. Currently we haven't defined all the resources and operations for the authorization component.
{{% /notice%}}

The Authorization component exposes a REST-API to Altinn Apps.

Authorization is used by the applications to authorize an action requested by the logged in user on a given resource and to retreive policy information. Use the authorization api to manage authorizations in altinn platform.

Resources: Actor, Roles

Parties
A party is a person whom  you can represent and perform a request on his behalf. A logged in user can retrieve a list of parties that he/she can represent.

Operations

Get a list of parties that the user (identified by JWT) can represent

```http
GET /authorization/api/v1/actors
```

{{%notice warning%}}
There can be terminology change shortly. So the url might change
{{% /notice%}}

Roles
A role in altinn offers or denies right to the logged in user to perform an action or group of actions for him or on behalf of someone. 

Get a list of roles that the user can perform for the selected party

```http
GET /authorization/api/v1/roles
```