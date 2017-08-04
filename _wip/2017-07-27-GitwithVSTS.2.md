---
layout: post
title: Git with VSTS - Part 3- Branching and Merging Fundamentals
description: "Git and VSTS"
modified: 2017-07-27
tags: [VSTS, Git]
categories: [DevOps]
author: Ajeet
---

# Branching fundamentals

A branch in Git is simply a "lightweight movable pointer to one of these commits". The default branch name in Git is master. As you start making commits, you’re given a master branch that points to the last commit you made. Every time you commit, it moves forward automatically.

Branch in Git is actually a simple file that contains the 40 character SHA-1 checksum of the commit it points to, branches are cheap to create and destroy. Creating a new branch is as quick and simple as writing 41 bytes to a file (40 characters and a newline).

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

Above cmd will move pointer from currently on branch (in above case master) to dev.
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
<<image>>

Let's try to make a direct commit to master branch. This means your project history has diverged. Changes that you made in your dev and master branch are isolated in separated branch. You can switch back and forth between the branches and merge them once you are ready.

### git log
```PowerShell
Git log --online --decorate --graph --all
```
Above cmd will print history of your commits.

<<image>>

# Basic branching and merging 

Lets consider that we are working on Web app and we already have few commit, and currently have master branch.
We received request in VSTS for to add a new feature
 
<<image>>

What we will do:

	• Lets create a branch (for feature ) - its always better to give task ID as branch name
	• And checkout to your new branch so HEAD pointer start pointing it.
	• Run Pull request to get code from master, before starting your work.
	• Perform necessary changes in code base
	• Commit your changes to feature branch
	• 
	• At the end merge these changes to master branch

### Create a branch

```PowerShell
git checkout -b task1114
```
Above command will create a new branch called 'task114' and switch to this branch. '-b' is used to create a new branch using cmd.

Now the HEAD is pointing to task1114 branch

Perform all required changes and commit to branch

```PowerShell
git add <<file name>>
```
*Or*
```PowerShell
git add .
```

```PowerShell
git commit -a -m "added file for new feature task1114"
```
Suddenly you get a request to provide hotfix immediately. Which you can not deploy along with 'task1114' as work is still in progress.
In order to do this simply switch back to master create a new branch called 'hotfix'.
Switch again to hot fix branch and execute pull request so you will get latest code from master branch.

Now perform all necessary changes here and commit the changes to hotfix branch once its done.

<<image>>

You can run all your test to ensure that hotfix is now ready to deploy on production.

Now checkout to master branch and run git merge cmd to merge all your changes to master.

Because the commit C4 pointed to by the branch hotfix you merged in was directly ahead of the commit C2 you’re on, Git simply moves the pointer forward. To phrase that another way, when you try to merge one commit with a commit that can be reached by following the first commit’s history, Git simplifies things by moving the pointer forward because there is no divergent work to merge together – this is called a “fast-forward.”

<<image>>

Delete the hotfix branch 

```PowerShell
git branch -d hotfix
```

Now you need to merge feature branch 'task1114', switch to the 'task114' branch and complete the development.
Once you are done, commit the changes.

<<images and cmd>>

If you noticed here that your hotfix changes are not here in task1114 branch. So either you can merge from master to task1114 to get latest changes or you can merge your task1114 changes with master once your done with development.

## Merging fundamentals

Let's continue above requirement. Our feature is completed and ready to merge into our master branch.

```PowerShell
git checkout master
Git merge task1114
```
<<image>>

If you noticed here that your hotfix changes are not here in task1114 branch. So either you can merge from master to task1114 to get latest changes or you can merge your task1114 changes with master once your done with development.

So we have diverged here. Because the commit on the branch you’re on isn’t a direct ancestor of the branch you’re merging in, Git has to do some work. In this case, Git does a simple three-way merge, using the two snapshots pointed to by the branch tips and the common ancestor of the two.

	1. Snapshot to merge in
	2. Snapshot to merge into
	3. Common Ancestor

<<image>>


*Git use merge commit*. Instead of moving pointer, git create a new snapshot that results from this three way merge and automatically creates a new commit that points to it. Merge commit is special in that it has more than one parent (#1 and #2).

*Common Ancestor*: git automatically determines the best common ancestor to use it for merge base. Once you done with merging delete the branch.

## Merging conflicts 

Consider a case where you have made some changes on the same part of the same file in two different branches.
You will get a merge conflict.

```PowerShell
git merge iss53
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```

Git hasn’t automatically created a new merge commit. It has paused the process while you resolve the conflict. If you want to see which files are unmerged at any point after a merge conflict, you can run git status:

git mergetool is graphical tool to resolve these issues

<<>>
After you exit the merge tool, Git asks you if the merge was successful. If you tell the script that it was, it stages the file to mark it as resolved for you. You can run git status again to verify that all conflicts have been resolved:

if you’re happy with that, and you verify that everything that had conflicts has been staged, you can type git commit to finalize the merge commit. The commit message by default looks something like this:

<<>>

## Branch management

The git branch command does more than just create and delete branches. If you run it with no arguments, you get a simple listing of your current branches:
$ git branch
  iss53
* master
  testing
Notice the * character that prefixes the master branch: it indicates the branch that you currently have checked out (i.e., the branch that HEAD points to). This means that if you commit at this point, the masterbranch will be moved forward with your new work. To see the last commit on each branch, you can run git branch -v:
$ git branch -v
  iss53   93b412c fix javascript issue
* master  7a98805 Merge branch 'iss53'
  testing 782fd34 add scott to the author list in the readmes
The useful --merged and --no-merged options can filter this list to branches that you have or have not yet merged into the branch you’re currently on. To see which branches are already merged into the branch you’re on, you can run git branch --merged:
$ git branch --merged
  iss53
* master
Because you already merged in iss53 earlier, you see it in your list. Branches on this list without the * in front of them are generally fine to delete with git branch -d; you’ve already incorporated their work into another branch, so you’re not going to lose anything.
To see all the branches that contain work you haven’t yet merged in, you can run git branch --no-merged:
$ git branch --no-merged
  testing
This shows your other branch. Because it contains work that isn’t merged in yet, trying to delete it with git branch -d will fail:
$ git branch -d testing
error: The branch 'testing' is not fully merged.
If you are sure you want to delete it, run 'git branch -D testing'.
If you really do want to delete the branch and lose that work, you can force it with -D, as the helpful message points out.
