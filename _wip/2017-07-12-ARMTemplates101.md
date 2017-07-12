---
layout: post
title: IaC - ARM Templates Fundamental
description: "IaC - ARM Templates Fundamental"
modified: 2017-07-12
tags: [IaC]
categories: [Azure]
author: Ajeet
---
### Intro

We have started Azure automation ~3yrs back. I use Azure classic PowerShell to perform IaC. However it was bit complex as have to write lots of checks and control, workflows. Also these PowerShell scripts was not easy for the end users.

With the introduction of Azure Resource Manager model life become much easier. New model not only provide much more granul control over design and managment but it also come with the JSON base template deployment. 
Azure ASM  (classic) is based on XML whereas Azure RM is based on JSON. JSON is easy to understand by the developer, infra guys and power users.  

We can create a template (in JSON format) that defines the infrastructure and configuration of your Azure solution. By using a template, we can repeatedly deploy your solution throughout its lifecycle and have confidence your resources are deployed in a consistent state. 

If you are beginner, lets go step by step. I always recommand to start with the Azure Portal and try to understand how it works. I am assuming you already have basic knowledge on Azure and Infrastrcture.
 
 1.  Login to [https://portal.azure.com](https://portal.azure.com)


### Strcuture
```JSON
    {
    "$schema": "http://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {  },
    "variables": {  },
    "resources": [  ],
    "outputs": {  }
    }
```
### Let's Start
