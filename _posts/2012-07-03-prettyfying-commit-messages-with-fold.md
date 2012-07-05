---
title: Prettyfying Commit Messages with fold
tags: git, unix, bash
---

I've been writing longer commit messages to provide background information and/or justification for decisions I made. Initially, I wasn't wrapping lines, and the messages were not very pretty in most log viewers. I found a short and sweet unix tool to help me wrap the messages: fold.

Now, I usually compose the messages in TextEdit. Then, I copy the message to the clipboard. I use <tt>pbpaste | fold -s | pbcopy</tt> to wrap the lines to 80 characters and put the wrapped message on the clipboard. Then I paste the message into vim during commit.

