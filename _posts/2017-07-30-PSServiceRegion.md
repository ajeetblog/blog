---
---
layout: post
title: PowerShell to find service  across the region
description: "PowerShell to find service availablity across the region"
modified: 2017-07-30
tags: [PowerShell]
categories: [Azure]
author: Ajeet
---

It's always good to have pre-flight validation check. Many time we have face the problem where end customer is deploying service which is not available to desired region. Output of the below script return the regions where the particular service.

{% highlight powershell %}
$resources = Get-AzureRmResourceProvider -ProviderNamespace Microsoft.Compute
$resources.ResourceTypes.Where{($_.ResourceTypeName -eq 'virtualMachines')}.Locations
{% endhighlight %}

![PS](/images/posts/resoursregionps/psresrg.JPG)