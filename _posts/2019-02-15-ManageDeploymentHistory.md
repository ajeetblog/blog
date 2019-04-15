---
layout: post
title: Manage Deployment History
description: "Manage Azure Resource Group Deployment History"
modified: 2019-04-15
tags: [ARM]
categories: [Azures]
author: Ajeet
google_analytics:  UA-101864870-1
google_verify: GKeGILLEWvsJwRfdYMqqoMDZKOBZPWIWpHP9K2uIXHI
production: true
---   
Recently, I have faced an issue, where our CD pipeline start failing into one environment and my team was not able to deploy Azure resource into the 'Resource Group', few second back things were working fine.

After investing the issue we found that Resource Group have the limitation on deployment history.

<!--more-->

As per MS documentation, RG can only keep the history of the last 800 deployments. You can not deploy/re-deploy anything once the deployment history reaches 800. 

To solve this we need to use a simple but very useful PS

```PowerShell

$resourceGroup = 'your-resource-group'`

Get-AzureRmResourceGroupDeployment -ResourceGroupName $resourceGroup `

| Select-Object -Skip 100 `

| Remove-AzureRmResourceGroupDeployment

```
**skip will ensure to keep latest deployments (in this case latest 100)**.

This PS only delete the deployment history and does't has any impact on deployment, they will remain untouched. 
