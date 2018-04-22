---
layout: post
title: Design VM Scale Sets
description: "Design Compute Infrastructure-   Design solutions using virtual machines - design VM Scale Sets"
modified: 2018-04-22
tags: [Compute, 70-535, 70-533, VM Scale set]
categories: [Azure]
author: Ajeet
---
Scale Sets part -1

**Scale sets provide high availability to your applications.**

With virtual machine scale sets, you can build large-scale services for areas such as compute, big data, and container workloads.

 In this post we will discuss about design VM Scale Sets.

 <!--more-->
 ## Why Scale sets
To provide redundancy and improved performance, applications are typically distributed across multiple instances. 

- With Scale sets you can create **identical, Load balanced VM** and managed them centrally. 

        
    -   Identical:  All VM instances are created from the **same base OS image and configuration**. This approach lets you easily manage hundreds of VMs without additional configuration tasks or network management.
    - Load balancer: Scale sets supports both **Azure Load balancer (layer 4) and Application load balancer (layer 7)**. 

- If one of these VM instances has a problem, customers continue to access your application through one of the other VM instances with minimal interruption.
- The number of VM instances can **automatically increase or decrease** in response to demand or a defined schedule.
- Scale sets **support up to 1000 VM instances**. If you create and upload your **own custom VM images, the limit is 300 VM instances**. Remember this as scale set limit.

- **High availability and application resiliency**: Scale sets provide HA and resiliency, but as we know availability,    performance, resilience need to design at each level. You can increase the availability by using Managed Disk, Premium storage, Availability zones. All these services are manged by Azure and provide HA and resilience to these services. 


>**Do I need to Pay additional charges?** 
**No**. There is no charges for scale sets features (automation, management). You only need to pay for Azure resources like VMs, Storage, Managed Disks etc.

## What are the advantages in-terms of management compared to VM

-   **Add additional VM instances**: You need to add, configure VM manually in group of VMs, whereas in *Scale sets it automatically create from central configuration.*
-   **Traffic balancing and distribution**: Manual process to add, configure load balancer or application load balance. Scale sets *can automatically create and integrate with Azure load balancer or Application Gateway*.
- **High availability and redundancy**: Manually create Availability Set or distribute and track VMs across Availability Zones, *whereas scale sets can automatically distribute VM instances across Availability Zones or Availability Sets*. 