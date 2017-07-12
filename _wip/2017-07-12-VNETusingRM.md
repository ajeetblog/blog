---
layout: post
title: VNET provisioning using ARM
description: "VNET provisioning using ARM"
modified: 2016-12-01
tags: [VNET, IaC]
categories: [Azure]
author: Ajeet
---
### Virtual Network
The Azure Virtual Network service enables you to securely connect Azure resources to each other with virtual networks (VNets). A VNet is a representation of your own network in the cloud. A VNet is a logical isolation of the Azure cloud dedicated to your subscription. You can also connect VNets to your on-premises network.

### Subnet

Understand the CIDR notation
        CIDR (Classless Inter-Domain Routing, sometimes called supernetting) is a way to allow more flexible allocation of Internet Protocol (IP) addresses than was possible with the original system of IP address classes. As a result, the number of available Internet addresses was greatly increased, which along with widespread use of network address translation (NAT), has significantly extended the useful life of IPv4.

[http://whatismyipaddress.com/cidr](http://whatismyipaddress.com/cidr)
[CIDR Tool](http://www.ipaddressguide.com/cidr)

### PowerShell

        {% highlight powershell %}
        New-AzureRmResourceGroup -Name TestRG -Location centralus
        {% endhighlight %}

        {% highlight powershell %}
        New-AzureRmVirtualNetwork -ResourceGroupName TestRG -Name TestVNet `
        -AddressPrefix 192.168.0.0/16 -Location centralus
        {% endhighlight %}

        {% highlight powershell %}
        $vnet = Get-AzureRmVirtualNetwork -ResourceGroupName TestRG -Name TestVNet
        {% endhighlight %}

        {% highlight powershell %}
        Add-AzureRmVirtualNetworkSubnetConfig -Name FrontEnd `
        -VirtualNetwork $vnet -AddressPrefix 192.168.1.0/24
        {% endhighlight %}

        {% highlight powershell %}
        Add-AzureRmVirtualNetworkSubnetConfig -Name BackEnd `
        -VirtualNetwork $vnet -AddressPrefix 192.168.2.0/24
        {% endhighlight %}

        {% highlight powershell %}
        Set-AzureRmVirtualNetwork -VirtualNetwork $vnet
        {% endhighlight %}

### ARM Template
understand template

Reusable template

[See complete code - vnet resource](https://github.com/AjeetChouksey/resources/blob/master/network/azure365.vnet.json)

[FAQ](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-networks-faq)

[See Azure documentation](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-networks-overview)