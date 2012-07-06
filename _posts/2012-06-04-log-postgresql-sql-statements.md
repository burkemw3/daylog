---
title: Log PostgreSQL SQL Statements
tags: PostgreSQL
---

To look at the statements that are being executed against a PostgreSQL database I do the following:

0. enable logging: <tt>sudo sed -e "s/^#log_statement/log_statement/" -i bak /Library/PostgreSQL/9.0/data/postgresql.conf &amp;&amp; sudo -u postgres pg_ctl restart -D/Library/PostgreSQL/9.0/data/</tt>
0. find the log: <tt>sudo ls /Library/PostgreSQL/9.0/data/pg_log</tt>
0. tail the log: <tt>sudo tail -f /Library/PostgreSQL/9.0/data/pg_log/</tt>&lt;logfile-name&gt;
0. disable logging: <tt>sudo sed -e "s/^log_statement/#log_statement/" -i bak /Library/PostgreSQL/9.0/data/postgresql.conf &amp;&amp; sudo -u postgres pg_ctl restart -D/Library/PostgreSQL/9.0/data/</tt>

Below is a longer explanation of these steps:

0. set <tt>log_statement = all</tt> with <tt>sudo vim /Library/PostgreSQL/9.0/data/postgresql.conf</tt> (search for it)
0. restart postgres with <tt>sudo -u postgres pg_ctl restart -D/Library/PostgreSQL/9.0/data/</tt> (shutdown any connections)
0. run the queries
0. find the log file I want to look through with <tt>sudo ls /Library/PostgreSQL/9.0/data/pg_log</tt>
0. dig through the log file with something like <tt>sudo less log-file-path</tt>
0. comment out the log_statement setting, so I'm not always logging
0. restart postgres again

