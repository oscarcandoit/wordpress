---
url: https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html
scraped_at: 2025-10-20T03:06:55.243Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html "Hide Sidebar")

[Previous: SHOW PROCEDURE STATUS Statement](https://dev.mysql.com/doc/refman/8.0/en/show-procedure-status.html "Previous: SHOW PROCEDURE STATUS Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements")[Next: SHOW PROFILE Statement](https://dev.mysql.com/doc/refman/8.0/en/show-profile.html "Next: SHOW PROFILE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html)

[PDF (US Ltr)](https://downloads.mysql.com/docs/refman-8.0-en.pdf)
\- 43.3Mb

[PDF (A4)](https://downloads.mysql.com/docs/refman-8.0-en.a4.pdf)
\- 43.4Mb

[Man Pages (TGZ)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.tar.gz)
\- 297.2Kb

[Man Pages (Zip)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.zip)
\- 402.4Kb

[Info (Gzip)](https://downloads.mysql.com/docs/mysql-8.0.info.gz)
\- 4.3Mb

[Info (Zip)](https://downloads.mysql.com/docs/mysql-8.0.info.zip)
\- 4.3Mb

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html)

[MySQL Backup and Recovery](https://dev.mysql.com/doc/mysql-backup-excerpt/8.0/en/)

[MySQL Globalization](https://dev.mysql.com/doc/mysql-g11n-excerpt/8.0/en/)

[MySQL Information Schema](https://dev.mysql.com/doc/mysql-infoschema-excerpt/8.0/en/)

[MySQL Installation Guide](https://dev.mysql.com/doc/mysql-installation-excerpt/8.0/en/)

[Security in MySQL](https://dev.mysql.com/doc/mysql-security-excerpt/8.0/en/)

[Starting and Stopping MySQL](https://dev.mysql.com/doc/mysql-startstop-excerpt/8.0/en/)

[MySQL and Linux/Unix](https://dev.mysql.com/doc/mysql-linuxunix-excerpt/8.0/en/)

[MySQL and Windows](https://dev.mysql.com/doc/mysql-windows-excerpt/8.0/en/)

[MySQL and macOS](https://dev.mysql.com/doc/mysql-macos-excerpt/8.0/en/)

[MySQL and Solaris](https://dev.mysql.com/doc/mysql-solaris-excerpt/8.0/en/)

[Building MySQL from Source](https://dev.mysql.com/doc/mysql-sourcebuild-excerpt/8.0/en/)

[MySQL Restrictions and Limitations](https://dev.mysql.com/doc/mysql-reslimits-excerpt/8.0/en/)

[MySQL Partitioning](https://dev.mysql.com/doc/mysql-partitioning-excerpt/8.0/en/)

[MySQL Tutorial](https://dev.mysql.com/doc/mysql-tutorial-excerpt/8.0/en/)

[MySQL Performance Schema](https://dev.mysql.com/doc/mysql-perfschema-excerpt/8.0/en/)

[MySQL Replication](https://dev.mysql.com/doc/mysql-replication-excerpt/8.0/en/)

[Using the MySQL Yum Repository](https://dev.mysql.com/doc/mysql-repo-excerpt/8.0/en/)

[MySQL NDB Cluster 8.0](https://dev.mysql.com/doc/mysql-cluster-excerpt/8.0/en/)

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/show-processlist.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/show-processlist.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/show-processlist.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/show-processlist.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/show-processlist.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/show-processlist.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/show-processlist.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/show-processlist.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)  /

SHOW PROCESSLIST Statement


#### 15.7.7.29 SHOW PROCESSLIST Statement

``` sql

SHOW [FULL] PROCESSLIST
```

Important

The INFORMATION SCHEMA implementation of
[`SHOW PROCESSLIST`](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html "15.7.7.29 SHOW PROCESSLIST Statement") is deprecated
and subject to removal in a future MySQL release. It is
recommended to use the Performance Schema implementation of
`SHOW PROCESSLIST` instead.

The MySQL process list indicates the operations currently being
performed by the set of threads executing within the server. The
[`SHOW PROCESSLIST`](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html "15.7.7.29 SHOW PROCESSLIST Statement") statement is one
source of process information. For a comparison of this
statement with other sources, see
[Sources of Process Information](https://dev.mysql.com/doc/refman/8.0/en/processlist-access.html#processlist-sources "Sources of Process Information").

Note

As of MySQL 8.0.22, an alternative implementation for
[`SHOW PROCESSLIST`](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html "15.7.7.29 SHOW PROCESSLIST Statement") is available
based on the Performance Schema
[`processlist`](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-processlist-table.html "29.12.21.7 The processlist Table") table, which, unlike
the default [`SHOW PROCESSLIST`](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html "15.7.7.29 SHOW PROCESSLIST Statement")
implementation, does not require a mutex and has better
performance characteristics. For details, see
[Section 29.12.21.7, “The processlist Table”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-processlist-table.html "29.12.21.7 The processlist Table").

If you have the [`PROCESS`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_process)
privilege, you can see all threads, even those belonging to
other users. Otherwise (without the
[`PROCESS`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_process) privilege), nonanonymous
users have access to information about their own threads but not
threads for other users, and anonymous users have no access to
thread information.


Without the `FULL` keyword,
[`SHOW PROCESSLIST`](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html "15.7.7.29 SHOW PROCESSLIST Statement") displays only
the first 100 characters of each statement in the
`Info` field.


The [`SHOW PROCESSLIST`](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html "15.7.7.29 SHOW PROCESSLIST Statement") statement is
very useful if you get the “too many connections”
error message and want to find out what is going on. MySQL
reserves one extra connection to be used by accounts that have
the [`CONNECTION_ADMIN`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_connection-admin) privilege
(or the deprecated [`SUPER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_super)
privilege), to ensure that administrators should always be able
to connect and check the system (assuming that you are not
giving this privilege to all your users).


Threads can be killed with the
[`KILL`](https://dev.mysql.com/doc/refman/8.0/en/kill.html "15.7.8.4 KILL Statement") statement. See
[Section 15.7.8.4, “KILL Statement”](https://dev.mysql.com/doc/refman/8.0/en/kill.html "15.7.8.4 KILL Statement").


Example of [`SHOW PROCESSLIST`](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html "15.7.7.29 SHOW PROCESSLIST Statement")
output:


``` sql

mysql> SHOW FULL PROCESSLIST\G
*************************** 1. row ***************************
     Id: 1
   User: system user
   Host:
     db: NULL
Command: Connect
   Time: 1030455
  State: Waiting for source to send event
   Info: NULL
*************************** 2. row ***************************
     Id: 2
   User: system user
   Host:
     db: NULL
Command: Connect
   Time: 1004
  State: Has read all relay log; waiting for the replica
         I/O thread to update it
   Info: NULL
*************************** 3. row ***************************
     Id: 3112
   User: replikator
   Host: artemis:2204
     db: NULL
Command: Binlog Dump
   Time: 2144
  State: Has sent all binlog to replica; waiting for binlog to be updated
   Info: NULL
*************************** 4. row ***************************
     Id: 3113
   User: replikator
   Host: iconnect2:45781
     db: NULL
Command: Binlog Dump
   Time: 2086
  State: Has sent all binlog to replica; waiting for binlog to be updated
   Info: NULL
*************************** 5. row ***************************
     Id: 3123
   User: stefan
   Host: localhost
     db: apollon
Command: Query
   Time: 0
  State: NULL
   Info: SHOW FULL PROCESSLIST
```

[`SHOW PROCESSLIST`](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html "15.7.7.29 SHOW PROCESSLIST Statement") output has these
columns:

- `Id`


The connection identifier. This is the same value displayed
in the `ID` column of the
`INFORMATION_SCHEMA` [`PROCESSLIST`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-processlist-table.html "28.3.23 The INFORMATION_SCHEMA PROCESSLIST Table") table, displayed in
the `PROCESSLIST_ID` column of the
Performance Schema [`threads`](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-threads-table.html "29.12.21.8 The threads Table")
table, and returned by the
[`CONNECTION_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_connection-id) function
within the thread.


- `User`


The MySQL user who issued the statement. A value of
`system user` refers to a nonclient thread
spawned by the server to handle tasks internally, for
example, a delayed-row handler thread or an I/O (receiver)
or SQL (applier) thread used on replica hosts. For
`system user`, there is no host specified
in the `Host` column.
`unauthenticated user` refers to a thread
that has become associated with a client connection but for
which authentication of the client user has not yet
occurred. `event_scheduler` refers to the
thread that monitors scheduled events (see
[Section 27.4, “Using the Event Scheduler”](https://dev.mysql.com/doc/refman/8.0/en/event-scheduler.html "27.4 Using the Event Scheduler")).





Note





A `User` value of `system
                user` is distinct from the
[`SYSTEM_USER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_system-user) privilege. The
former designates internal threads. The latter
distinguishes the system user and regular user account
categories (see [Section 8.2.11, “Account Categories”](https://dev.mysql.com/doc/refman/8.0/en/account-categories.html "8.2.11 Account Categories")).

- `Host`


The host name of the client issuing the statement (except
for `system user`, for which there is no
host). The host name for TCP/IP connections is reported in
`host_name:client_port`
format to make it easier to determine which client is doing
what.


- `db`


The default database for the thread, or
`NULL` if none has been selected.


- `Command`


The type of command the thread is executing on behalf of the
client, or `Sleep` if the session is idle.
For descriptions of thread commands, see
[Section 10.14, “Examining Server Thread (Process) Information”](https://dev.mysql.com/doc/refman/8.0/en/thread-information.html "10.14 Examining Server Thread (Process) Information"). The value of this
column corresponds to the
`COM_xxx`
commands of the client/server protocol and
`Com_xxx` status
variables. See [Section 7.1.10, “Server Status Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-status-variables.html "7.1.10 Server Status Variables").


- `Time`


The time in seconds that the thread has been in its current
state. For a replica SQL thread, the value is the number of
seconds between the timestamp of the last replicated event
and the real time of the replica host. See
[Section 19.2.3, “Replication Threads”](https://dev.mysql.com/doc/refman/8.0/en/replication-threads.html "19.2.3 Replication Threads").


- `State`


An action, event, or state that indicates what the thread is
doing. For descriptions of `State` values,
see [Section 10.14, “Examining Server Thread (Process) Information”](https://dev.mysql.com/doc/refman/8.0/en/thread-information.html "10.14 Examining Server Thread (Process) Information").



Most states correspond to very quick operations. If a thread
stays in a given state for many seconds, there might be a
problem that needs to be investigated.


- `Info`


The statement the thread is executing, or
`NULL` if it is executing no statement. The
statement might be the one sent to the server, or an
innermost statement if the statement executes other
statements. For example, if a `CALL`
statement executes a stored procedure that is executing a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement, the
`Info` value shows the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/show-procedure-status.html "Previous: SHOW PROCEDURE STATUS Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/show-profile.html "Next: SHOW PROFILE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html)

[PDF (US Ltr)](https://downloads.mysql.com/docs/refman-8.0-en.pdf)
\- 43.3Mb

[PDF (A4)](https://downloads.mysql.com/docs/refman-8.0-en.a4.pdf)
\- 43.4Mb

[Man Pages (TGZ)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.tar.gz)
\- 297.2Kb

[Man Pages (Zip)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.zip)
\- 402.4Kb

[Info (Gzip)](https://downloads.mysql.com/docs/mysql-8.0.info.gz)
\- 4.3Mb

[Info (Zip)](https://downloads.mysql.com/docs/mysql-8.0.info.zip)
\- 4.3Mb

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html)

[MySQL Backup and Recovery](https://dev.mysql.com/doc/mysql-backup-excerpt/8.0/en/)

[MySQL Globalization](https://dev.mysql.com/doc/mysql-g11n-excerpt/8.0/en/)

[MySQL Information Schema](https://dev.mysql.com/doc/mysql-infoschema-excerpt/8.0/en/)

[MySQL Installation Guide](https://dev.mysql.com/doc/mysql-installation-excerpt/8.0/en/)

[Security in MySQL](https://dev.mysql.com/doc/mysql-security-excerpt/8.0/en/)

[Starting and Stopping MySQL](https://dev.mysql.com/doc/mysql-startstop-excerpt/8.0/en/)

[MySQL and Linux/Unix](https://dev.mysql.com/doc/mysql-linuxunix-excerpt/8.0/en/)

[MySQL and Windows](https://dev.mysql.com/doc/mysql-windows-excerpt/8.0/en/)

[MySQL and macOS](https://dev.mysql.com/doc/mysql-macos-excerpt/8.0/en/)

[MySQL and Solaris](https://dev.mysql.com/doc/mysql-solaris-excerpt/8.0/en/)

[Building MySQL from Source](https://dev.mysql.com/doc/mysql-sourcebuild-excerpt/8.0/en/)

[MySQL Restrictions and Limitations](https://dev.mysql.com/doc/mysql-reslimits-excerpt/8.0/en/)

[MySQL Partitioning](https://dev.mysql.com/doc/mysql-partitioning-excerpt/8.0/en/)

[MySQL Tutorial](https://dev.mysql.com/doc/mysql-tutorial-excerpt/8.0/en/)

[MySQL Performance Schema](https://dev.mysql.com/doc/mysql-perfschema-excerpt/8.0/en/)

[MySQL Replication](https://dev.mysql.com/doc/mysql-replication-excerpt/8.0/en/)

[Using the MySQL Yum Repository](https://dev.mysql.com/doc/mysql-repo-excerpt/8.0/en/)

[MySQL NDB Cluster 8.0](https://dev.mysql.com/doc/mysql-cluster-excerpt/8.0/en/)