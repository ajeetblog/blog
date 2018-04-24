---
layout: post
title: IaC Deployment using VSTS Build and Release 
description: "IaC Deployment using VSTS Build and Release "
modified: 2017-10-22
tags: [IaC, VSTS, CICD]
categories: [Cloud]
author: Ajeet
google_analytics:  UA-101864870-1
google_verify: GKeGILLEWvsJwRfdYMqqoMDZKOBZPWIWpHP9K2uIXHI
production: true
---


[Before we start please refer](http://www.azure365.co.in/devops/GitwithVSTS)

*   Go to Build and Release menu, click on Release  in sub menu. Choose the "+" icon to create a new release definition.Create release definition dialog, select the Empty Process.

![j](/images/posts/iaccicd/crerls.JPG)

Give Environment a name and specify who is the owner of it.

![j](/images/posts/iaccicd/devenv.JPG)

Add another environment by 

![j](/images/posts/iaccicd/newenv.JPG)


![j](/images/posts/iaccicd/azdeploymenttask.JPG)

![j](/images/posts/iaccicd/taskadded.JPG)


![j](/images/posts/iaccicd/var.JPG)

![j](/images/posts/iaccicd/template.JPG)

![j](/images/posts/iaccicd/cloneenv.JPG)

![j](/images/posts/iaccicd/prodenv.JPG)

![j](/images/posts/iaccicd/prodvalue.JPG)


![j](/images/posts/iaccicd/res2.JPG)

![j](/images/posts/iaccicd/res3.JPG)

![j](/images/posts/iaccicd/resmsg.JPG)

![j](/images/posts/iaccicd/res4.JPG)

![j](/images/posts/iaccicd/agent.JPG)
