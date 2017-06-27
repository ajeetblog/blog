---
layout: post
title: Azure ARM Templates
description: "Azure ARM Templates"
modified: 2016-12-01
tags: [post, code, highlighting, blog]
categories: [intro]
---

# Azure ARM Templates

###
Enterprises have started adoption of Cloud, whether its  Private, Public or Hybrid cloud model. To get the advantage of on-demand, Agility and DevOps, clients are now not only demanding rapid, scalable, reusable, innovative cloud base solutions for their applications but also looking for consistent, test driven Infrastructure and configuration automation solutions.

There are lot of tools available in market which support Infrastructure and Configuration ‘As-Code’ as well as follow other DevOps culture and principals’ to support these requirements.

Azure new architecture bring the concept of Azure Resource Manager and Group. Azure Resource Manager enables you to work with the resources in your solution as a group. Azure Resource groups are logical containers that are used to group resources such as virtual machines, storage accounts, databases, websites, and others that share a common life cycle.
Azure Resource Manager Templates consists of JSON and expressions which you can use to construct values for deployment.

In an Azure Resource Manager template, you can define the resources to deploy for a solution, and specify parameters as well as variables that enable you to input values for different environments. The template consists of JSON and expressions which you can use to construct values for deployment. 

Resources deployed in parallel – Define the resource which can be deployed in parallel.
Resource dependency constraints enforced- Define dependencies for the resources which can only be provisioned after one or more other resources. Example: VM, before creating a VM you must have at least a storage account and a Virtual Network. 
Storage and Virtual Network can be provisioned parallel but VM needs to wait until both are not provisioned.
Template language provides some built-in functions – this help to manipulate the strings.

By using the ARM you can
        Ensure Idempotency
        Simplify Orchestration
        Simplify Roll-back
        Provide Cross Resource Configuration and update support

Azure Resource Templates are:
        Source files, can be checked-in
        Specifies resources and dependencies
        Support parameterized input/output

Resource Manager provides several benefits
          You can deploy, manage, and monitor all of the resources for your solution as a group, rather than handling these resources individually.
         You can repeatedly deploy your solution throughout the development lifecycle and have confidence your resources are deployed in a consistent state.
         You can use declarative templates to define your deployment.
         You can define the dependencies between resources so they are deployed in the correct order.
        You can apply access control to all services in your resource group because Role-Based Access Control (RBAC) is natively integrated into the management platform.
        You can apply tags to resources to logically organize all of the resources in your subscription.
Tags:

Tags help you to view billing for your organization by viewing the rolled-up costs for the entire group or for a group of resources sharing the same tag.

in upcoming post, I will talk more concept about ARM template and how to create them.