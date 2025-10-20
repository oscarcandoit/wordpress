---
url: https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html
scraped_at: 2025-10-20T03:12:36.075Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html "Hide Sidebar")

[Previous: Phantom Rows](https://dev.mysql.com/doc/refman/8.0/en/innodb-next-key-locking.html "Previous: Phantom Rows")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: InnoDB Locking and Transaction Model](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html "Up: InnoDB Locking and Transaction Model")[Next: An InnoDB Deadlock Example](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-example.html "Next: An InnoDB Deadlock Example")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/innodb-deadlocks.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/innodb-deadlocks.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/innodb-deadlocks.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/innodb-deadlocks.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/innodb-deadlocks.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/innodb-deadlocks.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/innodb-deadlocks.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/innodb-deadlocks.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html)  / [The InnoDB Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)  /
[InnoDB Locking and Transaction Model](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html)  /

Deadlocks in InnoDB


### 17.7.5 Deadlocks in InnoDB

[17.7.5.1 An InnoDB Deadlock Example](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-example.html)[17.7.5.2 Deadlock Detection](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html)[17.7.5.3 How to Minimize and Handle Deadlocks](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks-handling.html)

A deadlock is a situation in which multiple transactions are
unable to proceed because each transaction holds a lock that is
needed by another one. Because all transactions involved are
waiting for the same resource to become available, none of them
ever releases the lock it holds.


A deadlock can occur when transactions lock rows in multiple
tables (through statements such as
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") or
[`SELECT ... FOR\\
      UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")), but in the opposite order. A deadlock can also
occur when such statements lock ranges of index records and gaps,
with each transaction acquiring some locks but not others due to a
timing issue. For a deadlock example, see
[Section 17.7.5.1, “An InnoDB Deadlock Example”](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-example.html "17.7.5.1 An InnoDB Deadlock Example").


To reduce the possibility of deadlocks, use transactions rather
than [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") statements; keep
transactions that insert or update data small enough that they do
not stay open for long periods of time; when different
transactions update multiple tables or large ranges of rows, use
the same order of operations (such as
[`SELECT ... FOR\\
      UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")) in each transaction; create indexes on the
columns used in [`SELECT ...\\
      FOR UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") and
[`UPDATE ... WHERE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement")
statements. The possibility of deadlocks is not affected by the
isolation level, because the isolation level changes the behavior
of read operations, while deadlocks occur because of write
operations. For more information about avoiding and recovering
from deadlock conditions, see
[Section 17.7.5.3, “How to Minimize and Handle Deadlocks”](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks-handling.html "17.7.5.3 How to Minimize and Handle Deadlocks").


When deadlock detection is enabled (the default) and a deadlock
does occur, `InnoDB` detects the condition and
rolls back one of the transactions (the victim). If deadlock
detection is disabled using the
[`innodb_deadlock_detect`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_deadlock_detect) variable,
`InnoDB` relies on the
[`innodb_lock_wait_timeout`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_lock_wait_timeout) setting
to roll back transactions in case of a deadlock. Thus, even if
your application logic is correct, you must still handle the case
where a transaction must be retried. To view the last deadlock in
an `InnoDB` user transaction, use
[`SHOW ENGINE INNODB\\
      STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-engine.html "15.7.7.15 SHOW ENGINE Statement"). If frequent deadlocks highlight a problem with
transaction structure or application error handling, enable
[`innodb_print_all_deadlocks`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_print_all_deadlocks) to
print information about all deadlocks to the
[**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server") error log. For more information about
how deadlocks are automatically detected and handled, see
[Section 17.7.5.2, “Deadlock Detection”](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html "17.7.5.2 Deadlock Detection").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/innodb-next-key-locking.html "Previous: Phantom Rows") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html "Up: InnoDB Locking and Transaction Model") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-example.html "Next: An InnoDB Deadlock Example")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html)

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