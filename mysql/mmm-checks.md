# What mysql-mmm checks

Here is the list of checks [mysql-mmm](http://mysql-mmm.org/mysql-mmm.html) does to ensure replication goes well,
you can easily see them with a `ps aux | grep mmm`:

- `ping_ip` checks if the monitor network is up by pinging a single ip.
- `ping` ping every ip in the configuration ping_ips.
- `mysql` tries to connect to mysql and execute a simple `select now()`
sql query.
- `rep_backlog` tries to connect mysql run a `show slave status` to get the `rep_backlog` status.
- `rep_threads` tries to connect mysql run a `show slave status` to get the `rep_threads` status.
