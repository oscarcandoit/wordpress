---
url: https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html
scraped_at: 2025-10-20T03:12:18.248Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html "Hide Sidebar")

[Previous: Table Locking Issues](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html "Previous: Table Locking Issues")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimizing Locking Operations](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html "Up: Optimizing Locking Operations")[Next: Metadata Locking](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html "Next: Metadata Locking")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/concurrent-inserts.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/concurrent-inserts.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/concurrent-inserts.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/concurrent-inserts.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/concurrent-inserts.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/concurrent-inserts.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/concurrent-inserts.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/concurrent-inserts.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimizing Locking Operations](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html)  /

Concurrent Inserts


### 10.11.3 Concurrent Inserts

The `MyISAM` storage engine supports concurrent
inserts to reduce contention between readers and writers for a
given table: If a `MyISAM` table has no holes
in the data file (deleted rows in the middle), an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement can be executed
to add rows to the end of the table at the same time that
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements are reading
rows from the table. If there are multiple
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements, they are
queued and performed in sequence, concurrently with the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements. The results of
a concurrent [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") may not be
visible immediately.


The [`concurrent_insert`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_concurrent_insert) system
variable can be set to modify the concurrent-insert processing.
By default, the variable is set to `AUTO` (or
1) and concurrent inserts are handled as just described. If
[`concurrent_insert`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_concurrent_insert) is set to
`NEVER` (or 0), concurrent inserts are
disabled. If the variable is set to `ALWAYS`
(or 2), concurrent inserts at the end of the table are permitted
even for tables that have deleted rows. See also the description
of the [`concurrent_insert`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_concurrent_insert) system
variable.


If you are using the binary log, concurrent inserts are
converted to normal inserts for `CREATE ...
        SELECT` or
[`INSERT ...\\
        SELECT`](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement") statements. This is done to ensure that you can
re-create an exact copy of your tables by applying the log
during a backup operation. See [Section 7.4.4, “The Binary Log”](https://dev.mysql.com/doc/refman/8.0/en/binary-log.html "7.4.4 The Binary Log"). In
addition, for those statements a read lock is placed on the
selected-from table such that inserts into that table are
blocked. The effect is that concurrent inserts for that table
must wait as well.


With [`LOAD DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement"), if you specify
`CONCURRENT` with a `MyISAM`
table that satisfies the condition for concurrent inserts (that
is, it contains no free blocks in the middle), other sessions
can retrieve data from the table while [`LOAD\\
        DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement") is executing. Use of the
`CONCURRENT` option affects the performance of
[`LOAD DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement") a bit, even if no other
session is using the table at the same time.


If you specify `HIGH_PRIORITY`, it overrides
the effect of the
[`--low-priority-updates`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_low_priority_updates) option if
the server was started with that option. It also causes
concurrent inserts not to be used.


For [`LOCK\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"), the difference between `READ
        LOCAL` and `READ` is that
`READ LOCAL` permits nonconflicting
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements (concurrent
inserts) to execute while the lock is held. However, this cannot
be used if you are going to manipulate the database using
processes external to the server while you hold the lock.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html "Previous: Table Locking Issues") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html "Up: Optimizing Locking Operations") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html "Next: Metadata Locking")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html)

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