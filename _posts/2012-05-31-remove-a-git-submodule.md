---
title: Remove a Git Submodule
tags: git
---

I have a git submodule at conf/base. I tried to remove the submodule with <tt>git rm conf/base</tt> and receieved on Operation not permitted error from git in return. Here are my steps to remove the submodule:

1. Remove references to the submodule in .gitmodules with a text editor
1. Remove references to the submodule in .git/config with a text editor
1. Remove the git reference with <tt>git rm --cached conf/base</tt> (no trailing slash)
1. Commit all those changes

