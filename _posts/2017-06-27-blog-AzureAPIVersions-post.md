---
layout: post
title: Azure API Versions
description: "Azure API Versions"
modified: 2016-12-01
tags: [post, code, blog]
categories: [azure]
---

# Get list of Azure RM API versions
{% highlight css %}
#container {
    float: left;
    margin: 0 -240px 0 0;
    width: 100%;
}

{% endhighlight %}

 {% highlight powershell %}
   $listProviderNameSpace=Get-AzureRmResourceProvider -ListAvailable
   foreach($provideNameSpace in $listProviderNameSpace.ProviderNamespace)
    {
       if(($provideNameSpace -eq "microsoft.compute") -or($provideNameSpace -eq "microsoft.storage") -or ($provideNameSpace -eq "microsoft.network"))
        {
            Write-Host $provideNameSpace
            $providerList = (Get-AzureRmResourceProvider -ProviderNamespace $provideNameSpace).ResourceTypes
            foreach($providerType in $providerList.ResourceTypeName)
            {     
                Write-Host $providerType
                ((Get-AzureRmResourceProvider -ProviderNamespace $provideNameSpace).ResourceTypes | Where-Object ResourceTypeName -eq $providerType).ApiVersions
            }
        }
   }
{% endhighlight %}