---
layout: post
title: IaC Deployment using VSTS Release and VSTS Repo
description: "IaC Deployment using VSTS Release and VSTS Repo"
modified: 2018-03-02
tags: [IaC, VSTS, CICD]
categories: [Cloud, DevOps]
author: Ajeet
---
In this post we will discuss, how to setup CD for IaC. IaC code is hosted in VSTS repo.

<!--more-->


## Let’s create Build definition 

I am assuming, you already have ARM project created and code is checked in VSTS.
If you are new to this, please refer related posts.

![j](/images/posts/iaccicd/tfcvsource.JPG)

*   Select your source code repository. 
![j](/images/posts/iaccicd/tfvcbuild1.JPG)

*   Choose Build agent.  I am choosing Hosted VS2017**
![j](/images/posts/iaccicd/tfvcbuild2.JPG)

*   Choose Build agent.  I am choosing Hosted VS2017**
![j](/images/posts/iaccicd/tfvcbuild2.JPG)



