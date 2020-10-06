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

There are various ways by which we can control the resource's connectivity.
Consider the use case where Enterprise is moving some of the existing workloads to the cloud (as-is) some of the apps are getting rebuild as Cloud Native apps to leverage the PaaS services. The connectivity architecture concerns you need to address are
Setup secure private connectivity between On-prem - Azure 
Privately access to Azure Resources (IaaS and PaaS) from on-prem without having public IP needs.

VNET segmentation with the Network Security Group (NSG) is the first step in this direction. With NSG rules, you can control internal and external connectivity. 

Site-to-Site (S2S) VPN feature helps to set up secure connectivity between the On-Prem and Azure using IPSec Tunnel. But still, there are concerns as to it goes over the public internet.
