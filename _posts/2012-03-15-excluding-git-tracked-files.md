---
title: Excluding Git Tracked Files
tags: git
---

I have a file (.classpath) that git is tracking, but I don't want to see changes to the file with <tt>git status</tt> or commit the changes. The .gitignore file ignores untracked files, but not tracked ones. Some git index abuse allowed me to get what I wanted: <tt>git update-index --assume-unchanged &lt;file&gt;</tt>.

I can see which files are assumed unchanged with <tt>git ls-files -v | grep "^[a-z]"</tt>.

<small>This has been updated; there is <a href="https://github.com/burkemw3/daylog/commits/gh-pages/_posts/2012-03-15-excluding-git-tracked-files.md">history</a> available.</small>

