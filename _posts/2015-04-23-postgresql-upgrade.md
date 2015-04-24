---
title: Upgrading PostgreSQL with homebrew
tags: OS X, homebrew, PostgreSQL
---

I use [homebrew](http://brew.sh/) to install [PostgreSQL](http://www.postgresql.org/). I've needed to upgrade it a couple times recently, and it requires a little more than installing some software and restarting. The database files are version specific. Postgres, being awesome like it is, has a handy migration tool, [pg_upgrade](http://www.postgresql.org/docs/9.4/static/pgupgrade.html). Here's how I upgrade my local development environment.

1. Shutdown the currently running postgres

       unload ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist

2. Install the next version of postgres

       brew install postgres

3. Move the existing data directory aside

       mv /usr/local/var/postgres /usr/local/var/postgres-old

4. Create a new data directory

       initdb /usr/local/var/postgres -E utf8

5. Migrate the data from the old (e.g. 9.2.4) to the new (e.g. 9.3)

       pg_upgrade \
           -d /usr/local/var/postgres-old -D /usr/local/var/postgres \
           -b /usr/local/Cellar/postgresql/9.2.4/bin/ -B /usr/local/Cellar/postgresql/9.3.0/bin/

6. Start the new database (you might need to use the Launch Agent definition associated with your newer version)

       load ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist

7. If all goes well, then remove your old data directory

       rm -rf /usr/local/var/postgres-old

<small>Directions from [Upgrading PostgreSQL 9.2 to 9.3 with Homebrew](https://mattbrictson.com/postgresql-93-brew-upgrade)</small>