---
layout: post
title: Azure SQL provisionig using CLI
description: "Azure SQL provisionig using CLI"
modified: 2017-07-04
tags: [Azure SQL, CLI]
categories: [Azure]
---

{% highlight powershell %}

# Set an admin login and password for your database
             export adminlogin=ServerAdmin
            export password=ChangeYourAdminPassword1

# other parameters
            export servername=clisqlserver1
            export myResourceGroup=clisqlrg
            export location=westeurope

# The ip address range that you want to allow to access your DB
            export startip=0.0.0.0
             export endip=0.0.0.0

# Create a resource group
            az group create   --name $myResourceGroup   --location $location

# Create a logical server in the resource group
            az sql server create   --name $servername  --resource-group $myResourceGroup  --location $location   --admin-user $adminlogin   --admin-password $password

# Configure a firewall rule for the server
            az sql server firewall-rule create  --resource-group $myResourceGroup   --server $servername   -n AllowYourIp  --start-ip-address $startip  --end-ip-address $endip

# Create a database in the server
            az sql db create  --resource-group $myResourceGroup   --server $servername  --name mySampleDatabase  --sample-name AdventureWorksLT   --service-objective S0
            
#Cleanup the depployment
            az group delete --name myResourceGroup

{% endhighlight %}