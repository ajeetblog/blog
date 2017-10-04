---
layout: post
title: PowerShell in Cloud Shell
description: "PowerShell in Cloud Shell"
modified: 2017-08-31
tags: [Azure, PowerShell]
categories: [Azure, DevOps]
author: Ajeet
---

PowerShell in CloudShell is now available in public preview. It's really nice and cool feature. We can run and manage the operation using PowerShell directly from the Azure Portal. 

#### Advantages:
-   Shell access from virtually anywhere: Connect to Azure using an authenticated, browser-based shell experience that is hosted in the cloud and accessible from virtually anywhere. Azure Cloud Shell is assigned per unique user account and automatically authenticated with each session. Combined with Azure portal’s familiar GUI experience, Cloud Shell adds the power and flexibility of using a modern command-line experience.
-   Choose your preferred shell experience: Microsoft routinely maintains and updates Cloud Shell, which comes equipped with commonly used CLI tools including Linux shell interpreters, PowerShell modules, Azure tools, text editors, source control, build tools, container tools, database tools and more. Cloud Shell also includes language support for several popular programming languages such as Node.js, .NET and Python.
-   Common tools and programming languages included: Microsoft routinely maintains and updates Cloud Shell, which comes equipped with commonly used CLI tools including Linux shell interpreters, PowerShell modules, Azure tools, text editors, source control, build tools, container tools, database tools and more. Cloud Shell also includes language support for several popular programming languages such as Node.js, .NET and Python.
-   Persist your files in attached cloud storage: Cloud Shell attaches an Azure File share to persist your data. On first use, Cloud Shell will prompt to create a file share in Azure File storage (or attach an existing one) to persist your data across sessions and Cloud Shell will automatically re-attach it for subsequent sessions.

#### Windows and Linux together.
in the back their are bunch of container with PowerShell (Windows) and Bash (Linux). As you connect, Azure go and figure out the respective VM and figure out the container. Please make a note that thier is not cost for these container. Cloud Shell billing is based only on the Azure File storage used to persist your data. Your total cost depends on how much you store, the volume and type of storage transactions and outbound data transfers, and which data redundancy option you choose.

-   Cloud Shell runs on a temporary machine provided on a per-session, per-user basis
-   Cloud Shell times out after 20 minutes without interactive activity
-   Cloud Shell can only be accessed with a file share attached
-   Cloud Shell uses a the same file share for both Bash and PowerShell
-   Cloud Shell is assigned one machine per user account
-   Permissions are set as a regular Linux user (Bash)

Here we have option to increase the font size as well as resize the Window.
More than PowerShell on Windows


Azure:\>PowerShell has a concept of namespaces. What its doing mounting your Azure resources as file system. 

dir listing all the subscription 

cd <<subscription name>>  (autocomplition)

ls -- resource group with multiple view

most common things

get-AzureRMVM

list of all VM

cd .\<<resgrp>> -res    

ls

gt-AzureRMVM

clouddrive
same clud drive is available with both Bash ad PoswerShell container

cd $home c 

ce lets mount your
list of all the subscription
in the back their are container. its authenticating 




Azure it self provider

CD <<subscription name>>
 List of res group multiple view

 you are in Azure drive

 get-AzureRMVM

 cd .\<resgroup>\name

 get-AzureRMVM against the context

 Cloud drive same cloud drive will be availabe 
CD$home
clouddrive is free
get-module AzureRM*

Find-Module AzurAD figure out and find AD and if you install in your cloud drive

get-clouddrive

help

git --version


ls

vim .\cloudshell.ps1

intellsense 


nano






![Create new project](/images/posts/PSCloudShell/crtstr.jpg)

![Create new project](/images/posts/PSCloudShell/dir.jpg)

![Create new project](/images/posts/PSCloudShell/login.jpg)