# Git
Git Tutorial and Reference

## Overview

### What is Git?

### Why Git?

## Installing Git

* Installing on Linux

    sudo yum install git
    sudo apt-get install git

* Installing on Mac


* Installing on Windows


## Configuration

    git config --global user.name "Name"
    git config --global user.email "name@domain.com"

    git config --global color.ui.auto

Checking setting

    git config --list
    git config

Remove/Change a entry

    git config --global unset user.name
    git config --global --replace-all user.name "New Name"
    git config --global --edit

## Generate ssh key

Generate private key(`id_rsa`) and public key(`id_rsa_pub`) by `ssh-keygen`

    ssh-keygen -t rsa -b 4096 -C "email@example.com"

Add key to ssh-agent

Ensure ssh-agent is enabled
    
    ## Git Bash
    ssh-agent -s 
    ## other terminal prompt, msygit
    eval $(ssh-agent -s)

Add SSH key to ssh-agent

    ssh-add ~/.ssh/id_rsa

## Create Repository

Create a new local repository with specified name

    git init <project-name>

Download a project and its entire version history

    git clone <url>


## Status and Compare

List all modified files to be committed

    git status

Show file differences not yet staged

    git diff

Show content differences between two branches

    git diff <first-branch> <seconde-branch>

Show file differences between staging and the last file version

    git diff --staged

## History
Show all commits, starting with newest

    git log
    git log --graph --pretty=oneline --abbrev-commit

Show changes over time for a specific file

    git log -p <file>

List version history for a file, including renames

    git log --follow <file>

Who changed what and when in a file

    git blame <file>


## Branches
List branches

    git branch
    git branch -a
    git branch -r

Switch to an existing branch

    git checkout <branch>

Create a new branch based on current branch

    git checkout -b <branch>

Create a new branch based on a specified branch

    git branch <branch> <exist-branch>
    git branch <branch> <exist-commit-id>

Delete a local branch

    git branch -d <branch>

Delete a local branch even if the branch wasn't merged

    git branch -D <branch>


## Local Changes

Snapshots the file in preparation for versioning

    git add <file>
    git add *.<extension>
    git add .

Commit previously staged changes

    git commit -m "comment"

Change the last commit(Don't amentd published commits)

    git commit --amend

## Update & Publish

List all current configured remotes

    git remote -v

Show information about a remote

    git remote show <remote>

Add new remote repository

    git remote add <shortname> <url>

Remove existing remote repository

    git remote rm <shortname>
    git remote rm origin

Download all changes from remote, but don't integrate into HEAD

    git fetch remote

Download all changes and directly merge/integrate into HEAD

    git pull
    git pull <remote> <branch>

Publish local changes on a remote

    git push <remote> <branch>

Delete a branch on the remote

    git branch -dr <remote/branch>

## Merge & Rebase

Merge branch into current HEAD

    git merge <branch>

Rebase current HEAD onto branch

    git rebase <branch>

Abort rebase

    git rebase --abort

Continue a rebase after resolving conflicts

    git rebase --continue

Using configured merge tool to solve conflicts

    git mergetool


## Undo
Discard all local changes in working directory

    git rest --hard HEAD
    git reset --hard <commit>

Discard local changes in a specified file

    git checkout HEAD <file>

Unstages the file, but preserve its contents

    git reset <file>

Revert a cinnut

    git revert <commit>

## Save Fragments

Temporatily stores all modified tracked files

    git stash

Restores the most recently stashed files

    git stash pop

List all stashed changesets

    git stash list

Discards the most recently stashed changeset

    git stash drop


## Reference
* [Pro Git](http://progit.org/book)
* [Git - the simple guide](http://rogerdudler.github.io/git-guide/index.html)
* [Think like a git](http://think-like-a-git.net/)
* [Visual Git Guide](http://marklodato.github.com/visual-git-guide/index-en.html)
* [Git Reference](http://gitref.org)
* [Git Cheat Sheet](http://www.git-tower.com/blog/git-cheat-sheet)
* [Github Git Cheat Sheet](https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf)
* [TryGit](https://try.github.io)
* [Git Tutorial by LiXueFeng - Chinese](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
