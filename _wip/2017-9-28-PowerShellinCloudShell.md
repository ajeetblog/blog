---
layout: post
title: PowerShell in Cloud Shell
description: "PowerShell in Cloud Shell"
modified: 2017-08-31
tags: [Azure, PowerShell]
categories: [Azure, DevOps]
author: Ajeet
---

PowerShell in CloudShell is not available in public preview. It's really nice and cool feature. We can run and manage the operation using PowerShell directly from the Azure Portal. 

Windows and Linux together.
in the back their are bunch of container with PowerShell (Windows) and Bash (Linux). As you connect, Azure go and figure out the respective VM and figure out the container. Please make a note that thier is not cost for these container. You will only pay for the standard storage and the resource you are creating (if any).

Here we have option to increase the font size as well as resize the Window.
More than PowerShell on Windows

Po
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