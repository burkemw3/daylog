---
title: Deleting old logs
tags: OSX, unix
---

A few applications I use rotate their own log files, but don't delete them. I have added a crontab entry to delete logs older than 14 days:

    find /path/to/log.* -type f -mtime +14 -exec rm -f {} \;

I configured it to run everyday.
