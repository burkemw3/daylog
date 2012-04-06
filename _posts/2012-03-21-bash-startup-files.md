---
title: Bash Startup Files (profile, .bash_profile, .bash_login, .profile)
tags: bash
---

When I first setup my work mac 10.7, I had some bash configuration options I wanted to set. The ~/.profile file existed, but no other bash startup files did. I read a little bit about the different files, didn't find any convincing arguments for me to care much, and put my configuration options in ~/.profile. Recently, I noticed that my tab completions and environment variables weren't getting set properly. I investigated a bit more today, and found the ~/.profile wasn't getting executed. I had a ~/.bash_login file! <a href="http://stefaanlippens.net/bashrc_and_others">Bashrc and others</a> taught me about the loading order. I had installed RVM recently, which created my ~/.bash_login file and caused my ~/.profile to be not executed.
