---
layout: post
title: Azure Role Based Access Control - 1
description: "Azure RBAC"
modified: 2021-06-14
tags: [Azure, RBAC, CloudSecurity]
categories: [Azure]
author: Ajeet
---


Define Zero trust

What is RBAC

How it works

```json
"Actions": [
    "*"
],
"NotActions": [
    "Authorization/*/Delete",
    "Authorization/*/Write",
    "Authorization/elevateAccess/Action",
],
"DataActions": [ ],
"NotDataActions" : [ ],
"AssignableScopes": [
    "/"
]
```





#rbac #cloudsecurity #accessmanagement #az-104
