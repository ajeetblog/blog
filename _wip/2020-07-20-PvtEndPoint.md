---
layout: post
title: Privatley connect with Azure Resources
description: "Privatley connect with Azure Resources"
modified: 2020-10-10
tags: [ Azure, AZ-300, AZ-303, Az-301]
categories: [Azure]
author: Ajeet
---
"Moving to the cloud or Journey to the cloud" is the topmost priority of the Enterprise these days. The demand for Cloud adoption is continuously increasing. However, the biggest concern with moving to Public Cloud is SECURITY. Microsoft Azure is improving the SECURITY features within the services and between the services.

There are various reference patterns provided by which we can control the resource's connectivity.
Consider the use case where Enterprise has started its Journey to Cloud by migrating their existing apps to the cloud (as-is) or re-design the apps (if not possible to migrate as-is) as Cloud Native apps. Also, leverage the PaaS services where ever possible. **[Microsoft Cloud Adoption Framework](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/)** will help you to plan and execute the migration.

The connectivity architecture concerns you need to address are:

Provide role-based network segmentation with control over the resources connectivity. 
Connectivity between VNETs. But access to Azure Resources (IaaS and PaaS) from on-prem to Azure or between the VNETs must be private (any communication over the public internet is restricted).
Setup secure private connectivity between On-prem - Azure 

VNET segmentation with the Network Security Group (NSG) is the first step in this direction. With NSG rules, you can control internal and external connectivity. 

Site-to-Site (S2S) VPN feature helps to set up secure connectivity between the On-Prem and Azure using IPSec Tunnel. But still, there are concerns as to it goes over the public internet.



