---
layout: post
title: Git with VSTS - Git Branching -1
description: "Git and VSTS"
modified: 2017-07-27
tags: [VSTS, Git]
categories: [DevOps]
author: Ajeet
---

## Branching

A branch in Git is simply a "lightweight movable pointer to one of these commits". The default branch name in Git is master. As you start making commits, you’re given a master branch that points to the last commit you made. Every time you commit, it moves forward automatically.

The “master” branch in Git is not a special branch. It is exactly like any other branch. The only reason nearly every repository has one is that the git init command creates it by default and most people don’t bother to change it

Git doesn’t store data as a series of changesets or differences, but instead as a series of snapshots.
When you make a commit, Git stores a commit object that contains a pointer to the snapshot of the content you staged. This object also contains the author’s name and email, the message that you typed, and pointers to the commit or commits that directly came before this commit (its parent or parents):
	• zero parents for the initial commit, 
	• one parent for a normal commit, and 
	• multiple parents for a commit that results from a merge of two or more branches.
![](<<commit image>>)

Let's make more commits - next commit stores a pointer to the commit that came immediately before it.

![](<<commit image>>)

### Let's create a branch

When you create a new branch it create a new pointer to the same commit that you are on

```PowerShell
git branch dev
```

The very next question comes in my mind here is **How git knows that which branch is currently on?**
The Answer is a special pointer 'HEAD'. It always point to local branch that you are currently on.

<<image>>

### Switching Branches

```PowerShell
Git checkout dev
```

Above cmd will move point from currently on branch (in above case master) to dev.
So what happen when you make a commit to your dev branch

```PowerShell
Git commit -a -m "Update"
```

Your dev branch is moved forward, but your master branch is still pointing to last commit you were on before switching to master.

<<image>> 

```PowerShell
Git checkout master
```
Above cmd will do 2 things. 

	• It will move 'HEAD' pointer to master.
	• Reverted the files in your working directory back to the snapshot that master points to. 
