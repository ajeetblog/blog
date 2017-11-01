---
layout: post
title: Setting up Docker for Windows environment
description: "Docker for Windows"
modified: 2017-10-31
tags: [Docker, Container]
categories: [Container]
author: Ajeet
google_analytics:  UA-101864870-1
google_verify: GKeGILLEWvsJwRfdYMqqoMDZKOBZPWIWpHP9K2uIXHI
production: true
---

## Docker for Windows


An integrated, easy-to-deploy development environment for building, debugging and testing Docker apps on a Windows PC. Docker for Windows is a native Windows app deeply integrated with Hyper-V virtualization, networking and file system, making it the fastest and most reliable Docker environment for Windows.

I will walk through basic deployment and use of the Windows container feature on Windows 10 Professional or Enterprise (Anniversary Edition). After completion, you will have installed Docker for Windows and run a simple container.
<!--more-->
Base machine must have Windows 10 Anniversary Edition or Creators Update (Professional or Enterprise).


[Get code to install and configure docker for windows](https://github.com/AjeetChouksey/IaCLab/tree/master/Containers/DockerforWindows)

After installation Docker for Windows defaults to running Linux containers. Switch to Windows containers using either the Docker tray-menu or by running the following command in a PowerShell prompt 
```PowerShell
& $Env:ProgramFiles\Docker\Docker\DockerCli.exe -SwitchDaemon.
```
![Switch Container](\images\posts\container\switchcontainer.JPG)

## Let's play
Following PS will give you the installed version
```PowerShell
docker version
```

