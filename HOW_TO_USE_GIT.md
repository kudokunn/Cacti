Git
---

Git clone
---------

> Clone a repository into a new directory

Command
```
git clone git@git.appota.com:kdata-research/network-office.git
```
Change directory to cloned directory:
```
cd network-office
```

Git user information
--------------------

Add user information
```
git config user.email "chungbd@appota.com"
git config user.name "Chung Bui"
```

Git branch
----------

> git-checkout - Checkout a branch or paths to the working tree

Display current branch:
```
git branch
```
Create new branch:
```
git checkout -b branch_name
```
Change branch:
```
git checkout branch_name
```
Change code, then add it to git:
```
git add *
```
Commit it:
```
git commit -m 'add docs'
```
Push branch to remote:
```
git push remote_name branch_name
E.g: git push origin chungbd:chungbd
```
Delete branch:
```
git branch -d branch_name
```

Git commands
------------

- git status
- git fetch
- git merge
- git pull
- git remote -v
- get help XXX
- git checkout branch
- git log
- ``git add .``
- ``git add -u``
- git revert
- git pull = git fetch + git merge
- let's merge!
- git log --graph

Merge request (MR)
------------------

- learn to create branch
- create MR
- review on MR
