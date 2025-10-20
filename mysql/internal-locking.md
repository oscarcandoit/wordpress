---
url: https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html
scraped_at: 2025-10-20T03:12:11.388Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html "Hide Sidebar")

[Previous: Optimizing Locking Operations](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html "Previous: Optimizing Locking Operations")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimizing Locking Operations](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html "Up: Optimizing Locking Operations")[Next: Table Locking Issues](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html "Next: Table Locking Issues")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/internal-locking.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/internal-locking.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/internal-locking.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/internal-locking.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/internal-locking.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/internal-locking.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/internal-locking.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/internal-locking.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimizing Locking Operations](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html)  /

Internal Locking Methods


### 10.11.1 Internal Locking Methods

This section discusses internal locking; that is, locking
performed within the MySQL server itself to manage contention
for table contents by multiple sessions. This type of locking is
internal because it is performed entirely by the server and
involves no other programs. For locking performed on MySQL files
by other programs, see [Section 10.11.5, “External Locking”](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html "10.11.5 External Locking").

- [Row-Level Locking](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html#internal-row-level-locking "Row-Level Locking")

- [Table-Level Locking](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html#internal-table-level-locking "Table-Level Locking")

- [Choosing the Type of Locking](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html#internal-locking-choices "Choosing the Type of Locking")


#### Row-Level Locking

MySQL uses [row-level\\
locking](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_row_lock "row lock") for `InnoDB` tables to support
simultaneous write access by multiple sessions, making them
suitable for multi-user, highly concurrent, and OLTP
applications.


To avoid [deadlocks](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_deadlock "deadlock") when
performing multiple concurrent write operations on a single
`InnoDB` table, acquire necessary locks at
the start of the transaction by issuing a `SELECT ...
          FOR UPDATE` statement for each group of rows expected
to be modified, even if the data change statements come later
in the transaction. If transactions modify or lock more than
one table, issue the applicable statements in the same order
within each transaction. Deadlocks affect performance rather
than representing a serious error, because
`InnoDB` automatically
[detects](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_deadlock_detection "deadlock detection")
deadlock conditions by default and rolls back one of the
affected transactions.


On high concurrency systems, deadlock detection can cause a
slowdown when numerous threads wait for the same lock. At
times, it may be more efficient to disable deadlock detection
and rely on the
[`innodb_lock_wait_timeout`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_lock_wait_timeout)
setting for transaction rollback when a deadlock occurs.
Deadlock detection can be disabled using the
[`innodb_deadlock_detect`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_deadlock_detect)
configuration option.


Advantages of row-level locking:

- Fewer lock conflicts when different sessions access
different rows.


- Fewer changes for rollbacks.


- Possible to lock a single row for a long time.


#### Table-Level Locking

MySQL uses [table-level\\
locking](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_table_lock "table lock") for `MyISAM`,
`MEMORY`, and `MERGE`
tables, permitting only one session to update those tables at
a time. This locking level makes these storage engines more
suitable for read-only, read-mostly, or single-user
applications.


These storage engines avoid
[deadlocks](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_deadlock "deadlock") by always
requesting all needed locks at once at the beginning of a
query and always locking the tables in the same order. The
tradeoff is that this strategy reduces concurrency; other
sessions that want to modify the table must wait until the
current data change statement finishes.


Advantages of table-level locking:

- Relatively little memory required (row locking requires
memory per row or group of rows locked)


- Fast when used on a large part of the table because only a
single lock is involved.


- Fast if you often do `GROUP BY`
operations on a large part of the data or must scan the
entire table frequently.


MySQL grants table write locks as follows:

1. If there are no locks on the table, put a write lock on
    it.


2. Otherwise, put the lock request in the write lock queue.


MySQL grants table read locks as follows:

1. If there are no write locks on the table, put a read lock
    on it.


2. Otherwise, put the lock request in the read lock queue.


Table updates are given higher priority than table retrievals.
Therefore, when a lock is released, the lock is made available
to the requests in the write lock queue and then to the
requests in the read lock queue. This ensures that updates to
a table are not “starved” even when there is
heavy [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") activity for the
table. However, if there are many updates for a table,
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements wait until
there are no more updates.


For information on altering the priority of reads and writes,
see [Section 10.11.2, “Table Locking Issues”](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html "10.11.2 Table Locking Issues").


You can analyze the table lock contention on your system by
checking the
[`Table_locks_immediate`](https://dev.mysql.com/doc/refman/8.0/en/server-status-variables.html#statvar_Table_locks_immediate) and
[`Table_locks_waited`](https://dev.mysql.com/doc/refman/8.0/en/server-status-variables.html#statvar_Table_locks_waited) status
variables, which indicate the number of times that requests
for table locks could be granted immediately and the number
that had to wait, respectively:


``` sql

mysql> SHOW STATUS LIKE 'Table%';
+-----------------------+---------+
| Variable_name         | Value   |
+-----------------------+---------+
| Table_locks_immediate | 1151552 |
| Table_locks_waited    | 15324   |
+-----------------------+---------+
```

The Performance Schema lock tables also provide locking
information. See
[Section 29.12.13, “Performance Schema Lock Tables”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-lock-tables.html "29.12.13 Performance Schema Lock Tables").


The `MyISAM` storage engine supports
concurrent inserts to reduce contention between readers and
writers for a given table: If a `MyISAM`
table has no free blocks in the middle of the data file, rows
are always inserted at the end of the data file. In this case,
you can freely mix concurrent
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") and
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements for a
`MyISAM` table without locks. That is, you
can insert rows into a `MyISAM` table at the
same time other clients are reading from it. Holes can result
from rows having been deleted from or updated in the middle of
the table. If there are holes, concurrent inserts are disabled
but are enabled again automatically when all holes have been
filled with new data. To control this behavior, use the
[`concurrent_insert`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_concurrent_insert) system
variable. See [Section 10.11.3, “Concurrent Inserts”](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html "10.11.3 Concurrent Inserts").


If you acquire a table lock explicitly with
[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"), you can request a
`READ LOCAL` lock rather than a
`READ` lock to enable other sessions to
perform concurrent inserts while you have the table locked.


To perform many [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") and
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") operations on a table
`t1` when concurrent inserts are not
possible, you can insert rows into a temporary table
`temp_t1` and update the real table with the
rows from the temporary table:


``` sql

mysql> LOCK TABLES t1 WRITE, temp_t1 WRITE;
mysql> INSERT INTO t1 SELECT * FROM temp_t1;
mysql> DELETE FROM temp_t1;
mysql> UNLOCK TABLES;
```

#### Choosing the Type of Locking

Generally, table locks are superior to row-level locks in the
following cases:

- Most statements for the table are reads.


- Statements for the table are a mix of reads and writes,
where writes are updates or deletes for a single row that
can be fetched with one key read:




``` sql

UPDATE tbl_name SET column=value WHERE unique_key_col=key_value;
DELETE FROM tbl_name WHERE unique_key_col=key_value;
```

- [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") combined with
concurrent [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement")
statements, and very few
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") or
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statements.


- Many scans or `GROUP BY` operations on
the entire table without any writers.


With higher-level locks, you can more easily tune applications
by supporting locks of different types, because the lock
overhead is less than for row-level locks.


Options other than row-level locking:

- Versioning (such as that used in MySQL for concurrent
inserts) where it is possible to have one writer at the
same time as many readers. This means that the database or
table supports different views for the data depending on
when access begins. Other common terms for this are
“time travel,”“copy on write,”
or “copy on demand.”

- Copy on demand is in many cases superior to row-level
locking. However, in the worst case, it can use much more
memory than using normal locks.


- Instead of using row-level locks, you can employ
application-level locks, such as those provided by
[`GET_LOCK()`](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html#function_get-lock) and
[`RELEASE_LOCK()`](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html#function_release-lock) in MySQL.
These are advisory locks, so they work only with
applications that cooperate with each other. See
[Section 14.14, “Locking Functions”](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html "14.14 Locking Functions").


[PREV](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html "Previous: Optimizing Locking Operations") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html "Up: Optimizing Locking Operations") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html "Next: Table Locking Issues")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html)

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