---
layout: post
title: Git v/s TFVC
description: "Git"
modified: 2017-07-27
tags: [Git]
categories: [DevOps]
author: Ajeet
---



# Git (distributed)
Git is a distributed version control system. Each developer has a copy of the source repository on their dev machine. Developers can commit each set of changes on their dev machine and perform version control operations such as history and compare without a network connection. Branches are lightweight. When you need to switch contexts, you can create a private local branch. You can quickly switch from one branch to another to pivot among different variations of your codebase. Later, you can merge, publish, or dispose of the branch

# TFVC (centralized)
Team Foundation Version Control (TFVC) is a centralized version control system. Typically, team members have only one version of each file on their dev machines. Historical data is maintained only on the server. Branches are path-based and created on the server.

TFVC has two workflow models:

1.	Server workspaces - Before making changes, team members publicly check out files. Most operations require developers to be connected to the server. This system facilitates locking workflows. Other systems that work this way include Visual Source Safe, Perforce, and CVS. With server workspaces, you can scale up to very large codebases with millions of files per branch and large binary files.

2.	Local workspaces - Each team member takes a copy of the latest version of the codebase with them and works offline as needed. Developers check in their changes and resolve conflicts as necessary. Another system that works this way is Subversion.

### Moving from TFVC to Git
If you have existing TFVC repos, you can migrate them to Git repos using the git-tfs tool. The tool allows you to migrate a TFVC repo to a Git repo in just a couple of commands.


|   Capablity	| TFVC   	|  Git  	|  
|---	|---	|---	|
|   	|   	|   	|   	|   	|
|   	|   	|   	|   	|   	|
|   	|   	|   	|   	|   	|
