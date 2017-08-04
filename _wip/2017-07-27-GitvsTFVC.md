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
|  Changes 	|  Team members can concurrently change files on their dev machines. You upload (check-in) changesets to the server when you create them. You can upload your changes at any time. However, you might be interrupted by conflicts. You can change the comment of a changeset after you check it in. You can link changesets to work items and associate them with completed builds. 	| 	Team members can concurrently change files on their dev machines. You create commits on your dev machine independently of contributing them to the team. When you’re ready you must pull the latest commits before you upload (push) yours to the server. When you pull, you might be interrupted by conflicts. You can amend the latest local commit. You cannot change older commits. You can link commits to work items and associate them with completed builds. You can modify and combine local commits from the command prompt.| 
|   Branching	|  	Path-based branches are used mostly as long-standing constructs to isolate risk of change among feature teams and releases. Team members typically set up an additional workspace for each branch they work on. Changes in each branch are independent from each other, so you don’t have to check them in before switching from one branch to another. Merging between sibling branches requires a baseless merging. You can get visualizations of your branch structures and where your changesets have been merged.
See Use branches to isolate risk in Team Foundation Version Control. 	|  Branching is lightweight and path independent. Many developers create a branch for each new feature they are coding, sometimes on a daily basis. You can quickly switch from one branch to another to pivot among different variations of your codebase. You can create branches that exist only on your dev machine and share them if and when you’re ready. You must commit, branch, stash, or undo changes before switching branches. Merging is simple and independent of the commit that the branch is based on. You can compare branches to see which commits exist on which branches.  See Use Git branches to switch contexts, suspend work, and isolate risk. 	|
|   	|   	|   	|
