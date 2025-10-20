---
url: https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html
scraped_at: 2025-10-20T03:12:39.177Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html "Hide Sidebar")

[Previous: An InnoDB Deadlock Example](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-example.html "Previous: An InnoDB Deadlock Example")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Deadlocks in InnoDB](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html "Up: Deadlocks in InnoDB")[Next: How to Minimize and Handle Deadlocks](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks-handling.html "Next: How to Minimize and Handle Deadlocks")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/innodb-deadlock-detection.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/innodb-deadlock-detection.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/innodb-deadlock-detection.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/innodb-deadlock-detection.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/innodb-deadlock-detection.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/innodb-deadlock-detection.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/innodb-deadlock-detection.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/innodb-deadlock-detection.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html)  / [The InnoDB Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)  /
[InnoDB Locking and Transaction Model](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html)  /
[Deadlocks in InnoDB](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html)  /

Deadlock Detection


#### 17.7.5.2 Deadlock Detection

When [deadlock\\
detection](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_deadlock_detection "deadlock detection") is enabled (the default),
`InnoDB` automatically detects transaction
[deadlocks](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_deadlock "deadlock") and rolls back a
transaction or transactions to break the deadlock.
`InnoDB` tries to pick small transactions to
roll back, where the size of a transaction is determined by the
number of rows inserted, updated, or deleted.


`InnoDB` is aware of table locks if
`innodb_table_locks = 1` (the default) and
[`autocommit = 0`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_autocommit), and the MySQL
layer above it knows about row-level locks. Otherwise,
`InnoDB` cannot detect deadlocks where a table
lock set by a MySQL [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements")
statement or a lock set by a storage engine other than
`InnoDB` is involved. Resolve these situations
by setting the value of the
[`innodb_lock_wait_timeout`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_lock_wait_timeout) system
variable.


If the `LATEST DETECTED DEADLOCK` section of
`InnoDB` Monitor output includes a message
stating TOO DEEP OR LONG SEARCH IN THE LOCK TABLE
WAITS-FOR GRAPH, WE WILL ROLL BACK FOLLOWING
TRANSACTION, this indicates that the number of
transactions on the wait-for list has reached a limit of 200. A
wait-for list that exceeds 200 transactions is treated as a
deadlock and the transaction attempting to check the wait-for
list is rolled back. The same error may also occur if the
locking thread must look at more than 1,000,000 locks owned by
transactions on the wait-for list.


For techniques to organize database operations to avoid
deadlocks, see [Section 17.7.5, “Deadlocks in InnoDB”](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html "17.7.5 Deadlocks in InnoDB").

##### Disabling Deadlock Detection

On high concurrency systems, deadlock detection can cause a
slowdown when numerous threads wait for the same lock. At
times, it may be more efficient to disable deadlock detection
and rely on the
[`innodb_lock_wait_timeout`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_lock_wait_timeout)
setting for transaction rollback when a deadlock occurs.
Deadlock detection can be disabled using the
[`innodb_deadlock_detect`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_deadlock_detect)
variable.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-example.html "Previous: An InnoDB Deadlock Example") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html "Up: Deadlocks in InnoDB") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks-handling.html "Next: How to Minimize and Handle Deadlocks")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html)

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