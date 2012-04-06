---
title: Excluding Git Tracked Files
tags: git
---

I have a file (.classpath) that git was tracking, but I didn't want to see changes to with git status or commit them. The .gitignore file ignores untracked files, but not tracked ones. Some git index abuse allowed me to get what I wanted: <tt>git update-index --assume-unchanged &lt;file&gt;</tt>.
