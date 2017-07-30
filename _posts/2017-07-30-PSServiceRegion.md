---
layout: post
title: PowerShell to find service availablity across the region
description: "PowerShell to find service availablity across the region"
modified: 2016-12-01
tags: [PowerShell]
categories: [Azure]
author: Ajeet
---


{% highlight powershell %}
$resources = Get-AzureRmResourceProvider -ProviderNamespace Microsoft.Compute
$resources.ResourceTypes.Where{($_.ResourceTypeName -eq 'virtualMachines')}.Locations
{% endhighlight %}

![PS](/images/posts/resoursregionps/psresrg.JPG)