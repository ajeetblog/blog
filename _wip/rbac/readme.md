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


```JSON

/subscriptions
    /{subscriptionId}
        /resourcegroups
            /{resourceGroupName}
                /providers
                    /{providerName}
                        /{resourceType}
                            /{resourceSubType1}
                                /{resourceSubType2}
                                    /{resourceName}
 ```

[Watch in Action]()

[Lab Link](https://github.com/MicrosoftLearning/AZ-104-MicrosoftAzureAdministrator/blob/master/Instructions/Labs/LAB_02a_Manage_Subscriptions_and_RBAC.md)


#rbac #cloudsecurity #accessmanagement #az-104
