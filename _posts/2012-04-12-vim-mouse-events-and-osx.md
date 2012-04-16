---
title: Vim Mouse Events and OS X
tags: vim, OS X
---

There are occaisional times when I want to use the mouse in vim. I found [a post][] that helped me get going. I installed [SIMBL][] and [MouseTerm][]. Then I added <tt>set mouse=a</tt> to my .vimrc file.

There is one problem. When I select text in vim with the mouse, vim intercepts the mouse events and I cannot copy it to the clipboard with &#8984;+C. [A Stack Overflow question][] recommends using the alt/option key when highlighting text to copy.

[a post]: http://blog.roseman.org.uk/2010/12/15/macvim-terminal-vim/
[SIMBL]: http://www.culater.net/software/SIMBL/SIMBL.php
[MouseTerm]: https://bitheap.org/mouseterm/
[A Stack Overflow question]: http://stackoverflow.com/questions/1266950/vim-iterm-how-to-use-mouse-for-everything-except-selection

