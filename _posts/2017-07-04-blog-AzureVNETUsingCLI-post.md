---
layout: post
title: Azure SQL provisionig using CLI
description: "Azure SQL provisionig using CLI"
modified: 2017-07-04
tags: [VNET, CLI, 70-533]
categories: [Azure]
---
 

#### The Azure CLI 2.0 is Azure's new command-line experience for managing Azure resources. You can use it in your browser with Azure Cloud Shell, or you can install it on macOS, Linux, and Windows and run it from the command line.

Learning Azure CLI is pretty simple specially if you are comfort with PowerShell. Following script block shows how to create SQL server with database using Azure CLI
{% highlight powershell %}
# Variables
# Create a resource group
            az group create   --name $myResourceGroup   --location $location
# Create a VNET with single subnet
            azure network vnet create --vnet TestVNet -e 192.168.0.0 -i 16 -n FrontEnd -p 192.168.1.0 -r 24 -l "Central US"
# Create an additional subnet
            azure network vnet subnet create -t TestVNet -n BackEnd -a 192.168.2.0/24
# List VNET
            azure network vnet show
# Cleanup the deployment
            az group delete --name myResourceGroup
{% endhighlight %}