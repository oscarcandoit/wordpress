---
url: https://dev.mysql.com/doc/refman/8.0/en/table-locking.html
scraped_at: 2025-10-20T03:12:04.188Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html "Hide Sidebar")

[Previous: Internal Locking Methods](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html "Previous: Internal Locking Methods")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimizing Locking Operations](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html "Up: Optimizing Locking Operations")[Next: Concurrent Inserts](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html "Next: Concurrent Inserts")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/table-locking.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/table-locking.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/table-locking.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/table-locking.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/table-locking.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/table-locking.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/table-locking.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/table-locking.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimizing Locking Operations](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html)  /

Table Locking Issues


### 10.11.2 Table Locking Issues

`InnoDB` tables use row-level locking so that
multiple sessions and applications can read from and write to
the same table simultaneously, without making each other wait or
producing inconsistent results. For this storage engine, avoid
using the [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") statement,
because it does not offer any extra protection, but instead
reduces concurrency. The automatic row-level locking makes these
tables suitable for your busiest databases with your most
important data, while also simplifying application logic since
you do not need to lock and unlock tables. Consequently, the
`InnoDB` storage engine is the default in
MySQL.


MySQL uses table locking (instead of page, row, or column
locking) for all storage engines except
`InnoDB`. The locking operations themselves do
not have much overhead. But because only one session can write
to a table at any one time, for best performance with these
other storage engines, use them primarily for tables that are
queried often and rarely inserted into or updated.

- [Performance Considerations Favoring InnoDB](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html#table-locking-innodb "Performance Considerations Favoring InnoDB")

- [Workarounds for Locking Performance Issues](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html#table-locking-workarounds "Workarounds for Locking Performance Issues")


#### Performance Considerations Favoring InnoDB

When choosing whether to create a table using
`InnoDB` or a different storage engine, keep
in mind the following disadvantages of table locking:

- Table locking enables many sessions to read from a table
at the same time, but if a session wants to write to a
table, it must first get exclusive access, meaning it
might have to wait for other sessions to finish with the
table first. During the update, all other sessions that
want to access this particular table must wait until the
update is done.


- Table locking causes problems when a session is waiting
because the disk is full and free space needs to become
available before the session can proceed. In this case,
all sessions that want to access the problem table are
also put in a waiting state until more disk space is made
available.


- A [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement that
takes a long time to run prevents other sessions from
updating the table in the meantime, making the other
sessions appear slow or unresponsive. While a session is
waiting to get exclusive access to the table for updates,
other sessions that issue
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements queue up
behind it, reducing concurrency even for read-only
sessions.


#### Workarounds for Locking Performance Issues

The following items describe some ways to avoid or reduce
contention caused by table locking:

- Consider switching the table to the
`InnoDB` storage engine, either using
`CREATE TABLE ... ENGINE=INNODB` during
setup, or using `ALTER TABLE ...
                ENGINE=INNODB` for an existing table. See
[Chapter 17, _The InnoDB Storage Engine_](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") for more details
about this storage engine.


- Optimize [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements
to run faster so that they lock tables for a shorter time.
You might have to create some summary tables to do this.


- Start [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server") with
[`--low-priority-updates`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_low_priority_updates). For
storage engines that use only table-level locking (such as
`MyISAM`, `MEMORY`, and
`MERGE`), this gives all statements that
update (modify) a table lower priority than
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements. In this
case, the second [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statement in the preceding scenario would execute before
the [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement, and
would not wait for the first
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") to finish.


- To specify that all updates issued in a specific
connection should be done with low priority, set the
[`low_priority_updates`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_low_priority_updates)
server system variable equal to 1.


- To give a specific [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"),
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"), or
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statement lower
priority, use the `LOW_PRIORITY`
attribute.


- To give a specific [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statement higher priority, use the
`HIGH_PRIORITY` attribute. See
[Section 15.2.13, “SELECT Statement”](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement").


- Start [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server") with a low value for the
[`max_write_lock_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_write_lock_count)
system variable to force MySQL to temporarily elevate the
priority of all [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statements that are waiting for a table after a specific
number of write locks to the table occur (for example, for
insert operations). This permits read locks after a
certain number of write locks.


- If you have problems with mixed
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") and
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statements, the
`LIMIT` option to
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") may help. See
[Section 15.2.2, “DELETE Statement”](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement").


- Using `SQL_BUFFER_RESULT` with
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements can help
to make the duration of table locks shorter. See
[Section 15.2.13, “SELECT Statement”](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement").


- Splitting table contents into separate tables may help, by
allowing queries to run against columns in one table,
while updates are confined to columns in a different
table.


- You could change the locking code in
`mysys/thr_lock.c` to use a single
queue. In this case, write locks and read locks would have
the same priority, which might help some applications.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html "Previous: Internal Locking Methods") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html "Up: Optimizing Locking Operations") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html "Next: Concurrent Inserts")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html)

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