---
url: https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html
scraped_at: 2025-10-20T03:15:16.884Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html "Hide Sidebar")

[Previous: Redo Log](https://dev.mysql.com/doc/refman/8.0/en/innodb-redo-log.html "Previous: Redo Log")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: InnoDB On-Disk Structures](https://dev.mysql.com/doc/refman/8.0/en/innodb-on-disk-structures.html "Up: InnoDB On-Disk Structures")[Next: InnoDB Locking and Transaction Model](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html "Next: InnoDB Locking and Transaction Model")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/innodb-undo-logs.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/innodb-undo-logs.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/innodb-undo-logs.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/innodb-undo-logs.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/innodb-undo-logs.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/innodb-undo-logs.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/innodb-undo-logs.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/innodb-undo-logs.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html)  / [The InnoDB Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)  /
[InnoDB On-Disk Structures](https://dev.mysql.com/doc/refman/8.0/en/innodb-on-disk-structures.html)  /

Undo Logs


### 17.6.6 Undo Logs

An undo log is a collection of undo log records associated with a
single read-write transaction. An undo log record contains
information about how to undo the latest change by a transaction
to a [clustered index](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_clustered_index "clustered index")
record. If another transaction needs to see the original data as
part of a consistent read operation, the unmodified data is
retrieved from undo log records. Undo logs exist within
[undo log segments](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_undo_log_segment "undo log segment"),
which are contained within
[rollback segments](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_rollback_segment "rollback segment").
Rollback segments reside in
[undo tablespaces](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_undo_tablespace "undo tablespace") and
in the [global\\
temporary tablespace](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_global_temporary_tablespace "global temporary tablespace").


Undo logs that reside in the global temporary tablespace are used
for transactions that modify data in user-defined temporary
tables. These undo logs are not redo-logged, as they are not
required for crash recovery. They are used only for rollback while
the server is running. This type of undo log benefits performance
by avoiding redo logging I/O.


For information about data-at-rest encryption for undo logs, see
[Undo Log Encryption](https://dev.mysql.com/doc/refman/8.0/en/innodb-data-encryption.html#innodb-data-encryption-undo-log "Undo Log Encryption").


Each undo tablespace and the global temporary tablespace
individually support a maximum of 128 rollback segments. The
[`innodb_rollback_segments`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_rollback_segments) variable
defines the number of rollback segments.


The number of transactions that a rollback segment supports
depends on the number of undo slots in the rollback segment and
the number of undo logs required by each transaction. The number
of undo slots in a rollback segment differs according to
`InnoDB` page size.

| InnoDB Page Size | Number of Undo Slots in a Rollback Segment (InnoDB Page Size / 16) |
| --- | --- |
| `4096 (4KB)` | `256` |
| `8192 (8KB)` | `512` |
| `16384 (16KB)` | `1024` |
| `32768 (32KB)` | `2048` |
| `65536 (64KB)` | `4096` |

A transaction is assigned up to four undo logs, one for each of
the following operation types:

1. [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") operations on
    user-defined tables


2. [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") and
    [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") operations on
    user-defined tables


3. [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") operations on
    user-defined temporary tables


4. [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") and
    [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") operations on
    user-defined temporary tables


Undo logs are assigned as needed. For example, a transaction that
performs [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"),
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"), and
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") operations on regular and
temporary tables requires a full assignment of four undo logs. A
transaction that performs only
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") operations on regular tables
requires a single undo log.


A transaction that performs operations on regular tables is
assigned undo logs from an assigned undo tablespace rollback
segment. A transaction that performs operations on temporary
tables is assigned undo logs from an assigned global temporary
tablespace rollback segment.


An undo log assigned to a transaction remains attached to the
transaction for its duration. For example, an undo log assigned to
a transaction for an [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement")
operation on a regular table is used for all
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") operations on regular tables
performed by that transaction.


Given the factors described above, the following formulas can be
used to estimate the number of concurrent read-write transactions
that `InnoDB` is capable of supporting.

Note

It is possible to encounter a concurrent transaction limit error
before reaching the number of concurrent read-write transactions
that `InnoDB` is capable of supporting. This
occurs when a rollback segment assigned to a transaction runs
out of undo slots. In such cases, try rerunning the transaction.


When transactions perform operations on temporary tables, the
number of concurrent read-write transactions that
`InnoDB` is capable of supporting is
constrained by the number of rollback segments allocated to the
global temporary tablespace, which is 128 by default.

- If each transaction performs either an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") **or** an
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") or
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") operation, the number of
concurrent read-write transactions that
`InnoDB` is capable of supporting is:



```none
(innodb_page_size / 16) * innodb_rollback_segments * number of undo tablespaces
```

- If each transaction performs an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") **and** an
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") or
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") operation, the number of
concurrent read-write transactions that
`InnoDB` is capable of supporting is:



```none
(innodb_page_size / 16 / 2) * innodb_rollback_segments * number of undo tablespaces
```

- If each transaction performs an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") operation on a temporary
table, the number of concurrent read-write transactions that
`InnoDB` is capable of supporting is:



```none
(innodb_page_size / 16) * innodb_rollback_segments
```

- If each transaction performs an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") **and** an
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") or
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") operation on a temporary
table, the number of concurrent read-write transactions that
`InnoDB` is capable of supporting is:



```none
(innodb_page_size / 16 / 2) * innodb_rollback_segments
```


[PREV](https://dev.mysql.com/doc/refman/8.0/en/innodb-redo-log.html "Previous: Redo Log") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/innodb-on-disk-structures.html "Up: InnoDB On-Disk Structures") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html "Next: InnoDB Locking and Transaction Model")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html)

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