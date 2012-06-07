---
title: All Firefox Versions
tags: Firefox
---

I was getting an error from my web driver tests:
> org.openqa.selenium.firefox.NotConnectedException: Unable to connect to host 127.0.0.1 on port 7055 after 45000 ms.

I expected this was related to the FireFox driver not being compatible with my current version of FireFox.

I found all the version of FireFox at [http://releases.mozilla.org/pub/mozilla.org/firefox/releases/](http://releases.mozilla.org/pub/mozilla.org/firefox/releases/).

Using version 11 my web drivers worked again.

Then, in Preferences -> Advanced -> Update I told FireFox to "Check for updates, but let me choose whether to install them."

