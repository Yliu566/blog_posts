---
aliases:
- /cheatsheet/2022/06/01/git-cheatsheet
categories:
- cheatsheet
date: '2022-06-01'
description: Useful git commands
layout: post
title: Git cheatsheet
toc: true

---

# git commands

Workspace
<!-- 工作区 -->
Index / Stage
<!-- 暂存区 -->
Repository
<!-- 仓库区（或本地仓库） -->
Remote
<!-- 远程仓库 -->

## create a repository

Create a git repository in current directory
<!-- 在当前目录新建一个Git代码库 -->
> git init

Create a directory and initialize it as a git repository
<!-- 新建一个目录，将其初始化为Git代码库 -->
> git init [project-name]

Download a git repository
<!-- 下载一个项目和它的整个代码历史 -->
> git clone [url]

## configuration
The configuation file of Git is stored as .gitconfig. This file exits in the /home/USER/ as a configuration for global use, and also exists in repository folder as a configuration for specific use.
<!-- Git的设置文件为.gitconfig，它可以在用户主目录下（全局配置），也可以在项目目录下（项目配置）。 -->

Display current Git configuration settings
> git config --list

Edit the configuration file
> git config -e [--global]

Set up the user info 
> git config [--global] user.name "[name]"
> git config [--global] user.email "[email address]"

## add/remove file
Add specific file/files to stage areas
> git add [file1] [file2] ...

Add folder to stage areas
> git add [dir]

Add all files in current folder to stage areas
> git add .

If a file has multiple changes, it is okay to add every change individually
> git add -p

Delete a file in the workspace and save this deletion to stage areas
> git rm [file1] [file2] ...

Stop track the changes of a file, this file will stay in workspace
> git rm --cached [file]

Change file names, and save this rename action in stage areas
> git mv [file-original] [file-renamed]

## submit code
Submit files in stage areas to repository
> git commit -m [message]

Submit specific files from Stage to Repository
> git commit [file1] [file2] ... -m [message]

Directly submit all changes after previous submission from Workspace to Repository
> git commit -a

Display the difference info when submitting the code
> git commit -v

If you want to change the commit message, you can use this code: (use only when no modification after previous commit):
> git commit --amend -m [message]

Re-commit last code, including the new changes of certain files.
> git commit --amend [file1] [file2]

## branch
list all local branches
> git branch

list all remote branches
> gti branch -r

list all local and remote brances
> git branch -a

Create a new branch (local)
> git branch [branch-name]

Create a new branch (local), and switch to this branch
> git checkout -b [branch-name]

Create a new branch and direct to certain commit
> git branch [branch-name] [commit]

Create a new branch and add track with remote branch
> git branch --track [branch] [remote-branch]

Switch to specific branch and update workspace
> git checkout [branch-name]

Switch to last branch
> git checkout -

Build track connection between current branch and remote branch
> git branch --set-upstream [branch] [remote-branch]

Merge specific branch to current branch
> git merge [branch]

Choose a commit and merge to current branch
> git cherry-pick [commit]

Delete a branch
> git branch -d [branch-name]

Delete a remote branch
> git push origin --delete [branch-name]
> git branch -dr [remote/branch]

## tags

List all tags
> git tag

Create a tage for current commit 
> git tag [tag]

Create a tag for specific commit
> git tag [tag] [commit]

Delete local tag
> git tag -d [tag]

Delete remote tag
> git push origin :refs/tags/[tagName]

Show tag infos
> git show [tag]

Submit a specfic tag
> git push [remote] [tag]

Submit all tags
> git push [remote] --tags

Create a branch and direct to a specific tag
> git checkout -b [branch] [tag]

## visualize difference

Display changed files
> git status

Display the history version of current branch
> git log

Display history of commits and changed files in every commit
> git log --stat

Search commit history by keywords
> git log -S [keyword]

Display all changes afer a commit, and format displays as one commit per row.
> git log [tag] HEAD --pretty=format:%s

<!-- 显示某个commit之后的所有变动，其"提交说明"必须符合搜索条件 -->
Display all changes of a specific commit, of whose commit message fits seach words.
> git log [tag] HEAD --grep feature

Display the version history of a file.
> git log --follow [file]
> git whatchanged [file]

Display all differences of a file in every commit.
> git log -p [file]

Show last 5 commits info.
> git log -5 --pretty --oneline

Show users who add commits, ordered in frequency.
> git shortlog -sn

Show who and when changed a file.
> git blame [file]

Show the difference between workspace and stage.
> git diff

Show the difference between stage and last commit.
> git diff --cached [file]

Show the diffrence between workspace and the newest commit in current branch
> git diff HEAD

Show the difference between two commits
> git diff [first-branch]...[second-branch]

Show how many codes do you write today.
> git diff --shortstat "@{0 day ago}"

Show changes of a specific commit
> git show [commit]

Show file changes of a specific commit
> git show --name-only [commit]

git show filename of a commit
> git show [commit]:[filename]

Show recent commits of current branch
> git reflog

## remote sync

Download all changes from remote repository
> git fetch [remote]

Display all remote repository
> git remote -v

Display infomation of a remote repository
> git remote show [remote]

Add a new remote repository and a name for the repository
> git remote add [shortname] [url]

Pull the changes of the remote repository and merge it with local repository
> git pull [remote] [branch]

Upload local branch of the repository to remote repository
> git push [remote] [branch]

Force upload this current branch to remote repository ignoring conflicts.
> git push [remote] --force

Push all branches to remote repository
> git push [remote] --all

## restoration

Restore file from Stage area to Workspace
> git checkout [file]

Restore a file in a commit from Stage area to workspace
> git checkout [commit] [file]

Restore all files from Stage area to Workspace
> git checkout .

Restore a file from Stage and keep the file the same as last commit, but file in Workspace is unchanged
> git reset [file]


Reset Stage area and Workspace to keep the same as last commit.
> git reset --hard

<!-- 重置当前分支的指针为指定commit，同时重置暂存区，但工作区不变 -->
Reset a commit of current branch, also reset the Stage area but change nothing in Workspace
> git reset [commit]

<!-- 重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致 -->
Reset the HEAD of current branch as a specific commit, also reset stage and workspace to keep the same as the commit.
> git reset --hard [commit]

<!-- 重置当前HEAD为指定commit，但保持暂存区和工作区不变 -->
Rest current HEAD as a specific commit, but keep no changes in stage and workspace.
> git reset --keep [commit]

<!-- 新建一个commit，用来撤销指定commit,后者的所有变化都将被前者抵消，并且应用到当前分支 -->
Create a new commit, which is used to restore another commit. The changes of the later commit will be restored by the former one and will be applied to current branch.
> git revert [commit]

<!-- 暂时将未提交的变化移除，稍后再移入 -->
Temporally remove current uncommited changes and add them later
> git stash
> git stash pop

## Others
Create an archive file of a Git repository
> git archive

<The End>

<!-- some of the code comes to this reference: [A blog post](https://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html) -->