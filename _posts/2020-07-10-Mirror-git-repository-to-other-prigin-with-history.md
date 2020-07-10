---
layout: post
title: How to mirror / move Git repository to another origin, with full commit history, tags and branches
---

Step by step script

```
#clone existing repo to selected directory
$ git clone https://url-to-repo new-repo-dir
$ cd new-repo-dir
#show list of branches
$ git branch -a
#checkout branches to copy
$ git checkout branch-name-to-copy
#fetch all tags
$ git fetch --tags
#check
$ git git tag
$ git branch -a
#remove origin
$ git remote rm origin
#set new origin
$ git remote add origin https://url-to-new-repo
#push
$git push origin --all
$git push --tags
```
