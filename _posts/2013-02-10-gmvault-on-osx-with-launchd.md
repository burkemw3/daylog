---
title: gmvault on OS X with launchd
tags: OS X, gmvault, launchd
---

I use [gmvault](http://gmvault.org/) to backup my emails on gmail on my MacBook. I usually shutdown (not sleep) my MacBook when I'm not using it. I want my backups to run daily, if my computer is on. I use the launchd LaunchAgent script here (with the stuff between the hashes replaced appropriately):

{% highlight xml linenos %}
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>Label</key>
        <string>com.#username#.gmvault</string>
    <key>Disabled</key>
        <false/>
    <key>ProgramArguments</key>
    <array>
        <string>/usr/local/bin/gmvault</string>
        <string>sync</string>
        <string>--type</string>
        <string>quick</string>
        <string>#gmail address#</string>
    </array>
    <key>StandardOutPath</key>
        <string>#path to stdout log file#</string>
    <key>StandardErrorPath</key>
        <string>#path to stderr log file#</string>
    <key>RunAtLoad</key>
        <true/>
    <key>StartCalendarInterval</key>
        <dict>
            <key>Hour</key>
                <integer>12</integer>
            <key>Minute</key>
                <integer>15</integer>
        </dict>
</dict>
</plist>
{% endhighlight %}

I place this script in ~/Library/LaunchAgents, and launchd runs gmvault on startup. If the computer is awake at 12:15pm, then the sync runs again. If the computer is asleep at 12:15pm, then the sync runs when the computer wakes up.

I configured [newsyslog](https://developer.apple.com/library/mac/#documentation/Darwin/Reference/Manpages/man5/newsyslog.conf.5.html) to rotate the logs each week and keep 6 weeks of logs with the following in a file in /etc/newsyslog.d/:

    #path to stdout log file#      640  6     *    $W1D0 J
    #path to stderr log file#      640  6     *    $W1D0 J
