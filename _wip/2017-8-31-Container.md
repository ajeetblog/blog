---
layout: post
title: My First Container
description: "My First Docker Container"
modified: 2017-08-31
tags: [Container, Docker]
categories: [Azure, DevOps]
author: Ajeet
---


https://www.youtube.com/watch?v=yDmkWUjiQAw

Virtual Machine v/s Container

Conainer Ecosystem

Native Windows Container 

. Installation

Open a PowerShell command prompt, and type the following commands:

PS> Install-Module -Name DockerMsftProvider -Force
PS> Unregister-PackageSource -ProviderName DockerMsftProvider -Name DockerDefault -Erroraction Ignore
PS> Register-PackageSource -ProviderName DockerMsftProvider -Name Docker -Location https://download.docker.com/components/engine/windows-server/index.json
PS> Install-Package -Name docker -ProviderName DockerMsftProvider -Source Docker -Force
PS> Restart-Computer -Force
2. Test your Docker EE Installation

Test your Docker EE installation by running the hello-world container:

PS> docker run hello-world:nanoserver

Unable to find image 'hello-world:nanoserver' locally
nanoserver: Pulling from library/hello-world
bce2fbc256ea: Pull complete
3ac17e2e6106: Pull complete
8cac44e17f16: Pull complete
5e160e4d8db3: Pull complete
Digest: sha256:25eac12ba40f7591969085ab3fb9772e8a4307553c14ea72d0e6f98b2c8ced9d
Status: Downloaded newer image for hello-world:nanoserver

Hello from Docker!
This message shows that your installation appears to be working correctly.
Check out the docs for details.



Vedio
https://www.youtube.com/watch?v=5DO1ectDTos
https://www.youtube.com/watch?v=RjWFILSvhCs 
https://www.youtube.com/watch?v=BRaEC1KKJsg 
https://www.youtube.com/watch?v=Vyp5_F42NGs 
[Windows Containers: What, Why and How]:https://www.youtube.com/watch?v=BRaEC1KKJsg 
https://www.youtube.com/watch?v=-Sr0lfowvBM 