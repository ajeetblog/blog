---
layout: post
title: Azure Virtual Network - 201
description: "Azure Virtual Network Management"
modified: 2019-12-04
tags: [AZ-300, Azure Exam, Security, Network, Architecture]
categories: [Azure]
author: Ajeet
google_analytics:  UA-101864870-1
google_verify: GKeGILLEWvsJwRfdYMqqoMDZKOBZPWIWpHP9K2uIXHI
production: true
---

Virtual Network (VNET) act as islocation boundry between Azure resources. VNET is a ***container object that provides  a traffic isolation and segmentation.
 
If you are preparing for Azure Certifications Z-300) or new to designing space, I hope this post will help to start with fundamentals. In this post, I will talk about the basic of Azure Virtual Network Managment.

<!--more-->

**VNET Design basic considrations**:
1. Create Subnets based on workload groupings
2. Design NSGs at subnet level 
3. If customer is looking for enterprise grade firewall applicances use Network Virtual Applicances (NVA) and User-defined routing (UDR) to further custmize the traffic.
4. Implment Site-to-Site (S2S) and/ or Point-to-Site (P2S) VPN connectivity between on On-Prem and Cloud.




> ***disclaimer***: References and images are taken from various MS documentations.