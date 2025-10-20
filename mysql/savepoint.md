---
url: https://dev.mysql.com/doc/refman/8.0/en/savepoint.html
scraped_at: 2025-10-20T03:02:47.644Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html "Hide Sidebar")

[Previous: Statements That Cause an Implicit Commit](https://dev.mysql.com/doc/refman/8.0/en/implicit-commit.html "Previous: Statements That Cause an Implicit Commit")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Transactional and Locking Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-transactional-statements.html "Up: Transactional and Locking Statements")[Next: LOCK INSTANCE FOR BACKUP and UNLOCK INSTANCE Statements](https://dev.mysql.com/doc/refman/8.0/en/lock-instance-for-backup.html "Next: LOCK INSTANCE FOR BACKUP and UNLOCK INSTANCE Statements")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/savepoint.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/savepoint.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/savepoint.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/savepoint.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/savepoint.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/savepoint.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/savepoint.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/savepoint.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Transactional and Locking Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-transactional-statements.html)  /

SAVEPOINT, ROLLBACK TO SAVEPOINT, and RELEASE SAVEPOINT Statements


### 15.3.4 SAVEPOINT, ROLLBACK TO SAVEPOINT, and RELEASE SAVEPOINT Statements

```sql
SAVEPOINT identifier
ROLLBACK [WORK] TO [SAVEPOINT] identifier
RELEASE SAVEPOINT identifier
```

`InnoDB` supports the SQL statements
[`SAVEPOINT`](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html "15.3.4 SAVEPOINT, ROLLBACK TO SAVEPOINT, and RELEASE SAVEPOINT Statements"),
[`ROLLBACK TO\\
      SAVEPOINT`](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html "15.3.4 SAVEPOINT, ROLLBACK TO SAVEPOINT, and RELEASE SAVEPOINT Statements"),
[`RELEASE\\
      SAVEPOINT`](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html "15.3.4 SAVEPOINT, ROLLBACK TO SAVEPOINT, and RELEASE SAVEPOINT Statements") and the optional `WORK`
keyword for
[`ROLLBACK`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements").


The [`SAVEPOINT`](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html "15.3.4 SAVEPOINT, ROLLBACK TO SAVEPOINT, and RELEASE SAVEPOINT Statements") statement sets a
named transaction savepoint with a name of
_`identifier`_. If the current transaction
has a savepoint with the same name, the old savepoint is deleted
and a new one is set.


The [`ROLLBACK TO\\
      SAVEPOINT`](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html "15.3.4 SAVEPOINT, ROLLBACK TO SAVEPOINT, and RELEASE SAVEPOINT Statements") statement rolls back a transaction to the
named savepoint without terminating the transaction. Modifications
that the current transaction made to rows after the savepoint was
set are undone in the rollback, but `InnoDB` does
_not_ release the row locks that were stored in
memory after the savepoint. (For a new inserted row, the lock
information is carried by the transaction ID stored in the row;
the lock is not separately stored in memory. In this case, the row
lock is released in the undo.) Savepoints that were set at a later
time than the named savepoint are deleted.


If the [`ROLLBACK TO\\
      SAVEPOINT`](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html "15.3.4 SAVEPOINT, ROLLBACK TO SAVEPOINT, and RELEASE SAVEPOINT Statements") statement returns the following error, it
means that no savepoint with the specified name exists:


```none
ERROR 1305 (42000): SAVEPOINT identifier does not exist
```

The [`RELEASE\\
      SAVEPOINT`](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html "15.3.4 SAVEPOINT, ROLLBACK TO SAVEPOINT, and RELEASE SAVEPOINT Statements") statement removes the named savepoint from the
set of savepoints of the current transaction. No commit or
rollback occurs. It is an error if the savepoint does not exist.


All savepoints of the current transaction are deleted if you
execute a [`COMMIT`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements"), or a
[`ROLLBACK`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements") that
does not name a savepoint.


A new savepoint level is created when a stored function is invoked
or a trigger is activated. The savepoints on previous levels
become unavailable and thus do not conflict with savepoints on the
new level. When the function or trigger terminates, any savepoints
it created are released and the previous savepoint level is
restored.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/implicit-commit.html "Previous: Statements That Cause an Implicit Commit") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-transactional-statements.html "Up: Transactional and Locking Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/lock-instance-for-backup.html "Next: LOCK INSTANCE FOR BACKUP and UNLOCK INSTANCE Statements")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/savepoint.html)

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