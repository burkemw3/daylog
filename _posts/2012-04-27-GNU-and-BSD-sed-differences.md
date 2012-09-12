---
title: GNU and BSD sed differences
tags: GNU, BSD, sed, perl
---

GNU and BSD sed have different interpretations of the -i (in place edit) flag. This is very annoying for scripts shared between OS X and most linux distributions. So, I use perl instead!

Old sed command: <tt>sed -i 's/foo/bar/g' $filename</tt><br />
New perl command: <tt>perl -pe 's/foo/bar/g' -i $filename</tt>

