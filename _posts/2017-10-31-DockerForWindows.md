---
layout: post
title: Setting up Docker on Windows 10 environment
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

Base machine must have Windows 10 Anniversary Edition or Creators Update (Professional or Enterprise).
<!--more-->

[Get code to install and configure docker for windows](https://github.com/AjeetChouksey/IaCLab/tree/master/Containers/DockerforWindows)

After installation Docker for Windows defaults to running Linux containers. Switch to Windows containers using either the Docker tray-menu or by running the following command in a PowerShell prompt 

```PowerShell
& $Env:ProgramFiles\Docker\Docker\DockerCli.exe -SwitchDaemon
```
![Switch Container](\images\posts\container\switchcontainer.JPG)

Following PS will give you the installed version
```PowerShell
docker version
```
Will discuss more about containers in upcoming posts.
