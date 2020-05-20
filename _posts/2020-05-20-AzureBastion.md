---
layout: post
title: Azure Bastion
description: "Private and fully managed remote access to your virtual machines"
modified: 2020-05-20
tags: [Azure, AzureExam]
categories: [Azure]
author: Ajeet
---

Organizations always have issues and concerns that how to remove the risk of threats and malware attacks when users connect to VMs (using RDP or SSH) inside the network.

Azure Bastionnot only helps you to address these issues, but also reduce the lot of managment overhead. In this post we will discuss the concepts and how to configure it.

<!--more-->

You can connect to remote VMs using the following method:

1. **The easiest way to connect VMs is by using RDP or SSH protocols directly over the internet using public ip**.
   
   Organizations follow "Closed by default and Open by exception" or "Shift Left" principals while defining the network security policies. You have faced this issue day in day out where your project needs to take the approval before using any required port for the application. 
  
   In most of the Organization ports of RDP or SSH is not open by default. 

   Many of us have used one of the following hacks to connect our dev VMs hosted on Azure. 

   a. In Azure classic (Service Management), you used to create the Access control list, and map one of the open ports (e.g. 80 or 443) with 3389 for RDP :).

   b. Microsoft very well addresses this issue in V2 (Resource Manager), where you do not have ACL to do port forwarding. But you have the other trick here. Create a Load balancer and do a port forwarding using the backend pool. 

    >These hacks help you to bypass the policies and connect with the VMs but create a serious security risk.

2. **The other better option Organization have is use the Jump box as an entry point for Remote Desktop connections**.

    VMs in your customer network perimeter will not have a public IP associated with RDP access. This at-least addresses the concern of exposing VMs directly over the Internet. 

    Only Jump box will have the public IP which allows the remote desktop connections. Once you are inside the jump box you can connect VM using private IP. It's like a remote session inside another remote session.

    >Sometimes it slows down the connections and moreover, you need to own all the management overhead for this box (e.g. patch management, security management, etc.)

    The following diagram shows an example of the Azure Jump box.


    ![](/images/posts/azure/jumpbox.jpg)

    *image credit [**Microsoft**](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/identity/adds-extend-domain)*

**Azure Bastion is the solution for you to address all the issues and reduce the management overhead.**

It's fully managed PaaS service that provides secure and seamless RDP and SSH access to your virtual machines directly through the Azure Portal. 

---
*Azure Bastion is provisioned directly in your Virtual Network (VNet) and supports all VMs in your Virtual Network (VNet) using SSL without any exposure through public IP addresses*.

---


![](/images/posts/azure/azurebastion.jpg)

*image credit **Microsoft***