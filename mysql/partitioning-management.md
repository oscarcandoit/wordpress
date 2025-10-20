---
url: https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html
scraped_at: 2025-10-20T03:04:53.027Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html "Hide Sidebar")

[Previous: How MySQL Partitioning Handles NULL](https://dev.mysql.com/doc/refman/8.0/en/partitioning-handling-nulls.html "Previous: How MySQL Partitioning Handles NULL")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html "Up: Partitioning")[Next: Management of RANGE and LIST Partitions](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management-range-list.html "Next: Management of RANGE and LIST Partitions")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/partitioning-management.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/partitioning-management.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/partitioning-management.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/partitioning-management.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/partitioning-management.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/partitioning-management.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/partitioning-management.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/partitioning-management.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)  /
Partition Management


## 26.3 Partition Management

[26.3.1 Management of RANGE and LIST Partitions](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management-range-list.html)[26.3.2 Management of HASH and KEY Partitions](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management-hash-key.html)[26.3.3 Exchanging Partitions and Subpartitions with Tables](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management-exchange.html)[26.3.4 Maintenance of Partitions](https://dev.mysql.com/doc/refman/8.0/en/partitioning-maintenance.html)[26.3.5 Obtaining Information About Partitions](https://dev.mysql.com/doc/refman/8.0/en/partitioning-info.html)

There are a number of ways using SQL statements to modify
partitioned tables; it is possible to add, drop, redefine, merge,
or split existing partitions using the partitioning extensions to
the
[`ALTER\\
      TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table-partition-operations.html "15.1.9.1 ALTER TABLE Partition Operations") statement. There are also ways to obtain
information about partitioned tables and partitions. We discuss
these topics in the sections that follow.

- For information about partition management in tables
partitioned by `RANGE` or
`LIST`, see
[Section 26.3.1, “Management of RANGE and LIST Partitions”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management-range-list.html "26.3.1 Management of RANGE and LIST Partitions").


- For a discussion of managing `HASH` and
`KEY` partitions, see
[Section 26.3.2, “Management of HASH and KEY Partitions”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management-hash-key.html "26.3.2 Management of HASH and KEY Partitions").


- See [Section 26.3.5, “Obtaining Information About Partitions”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-info.html "26.3.5 Obtaining Information About Partitions"), for a discussion of
mechanisms provided in MySQL 8.0 for obtaining
information about partitioned tables and partitions.


- For a discussion of performing maintenance operations on
partitions, see [Section 26.3.4, “Maintenance of Partitions”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-maintenance.html "26.3.4 Maintenance of Partitions").


Note

All partitions of a partitioned table must have the same number
of subpartitions; it is not possible to change the
subpartitioning once the table has been created.

To change a table's partitioning scheme, it is necessary only
to use the
[`ALTER\\
      TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table-partition-operations.html "15.1.9.1 ALTER TABLE Partition Operations") statement with a
_`partition_options`_ option, which has the
same syntax as that as used with [`CREATE\\
      TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") for creating a partitioned table; this option
(also) always begins with the keywords `PARTITION
      BY`. Suppose that the following
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement was used to
create a table that is partitioned by range:


``` sql

CREATE TABLE trb3 (id INT, name VARCHAR(50), purchased DATE)
    PARTITION BY RANGE( YEAR(purchased) ) (
        PARTITION p0 VALUES LESS THAN (1990),
        PARTITION p1 VALUES LESS THAN (1995),
        PARTITION p2 VALUES LESS THAN (2000),
        PARTITION p3 VALUES LESS THAN (2005)
    );
```

To repartition this table so that it is partitioned by key into
two partitions using the `id` column value as the
basis for the key, you can use this statement:


``` sql

ALTER TABLE trb3 PARTITION BY KEY(id) PARTITIONS 2;
```

This has the same effect on the structure of the table as dropping
the table and re-creating it using `CREATE TABLE trb3
      PARTITION BY KEY(id) PARTITIONS 2;`.


`ALTER TABLE ... ENGINE = ...` changes only the
storage engine used by the table, and leaves the table's
partitioning scheme intact. The statement succeeds only if the
target storage engine provides partitioning support. You can use
`ALTER TABLE ... REMOVE PARTITIONING` to remove a
table's partitioning; see [Section 15.1.9, “ALTER TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement").

Important

Only a single `PARTITION BY`, `ADD
        PARTITION`, `DROP PARTITION`,
`REORGANIZE PARTITION`, or `COALESCE
        PARTITION` clause can be used in a given
[`ALTER\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table-partition-operations.html "15.1.9.1 ALTER TABLE Partition Operations") statement. If you (for example) wish to drop a
partition and reorganize a table's remaining partitions,
you must do so in two separate
[`ALTER\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table-partition-operations.html "15.1.9.1 ALTER TABLE Partition Operations") statements (one using `DROP
        PARTITION` and then a second one using
`REORGANIZE PARTITION`).

You can delete all rows from one or more selected partitions using
[`ALTER TABLE ...\\
      TRUNCATE PARTITION`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/partitioning-handling-nulls.html "Previous: How MySQL Partitioning Handles NULL") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html "Up: Partitioning") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management-range-list.html "Next: Management of RANGE and LIST Partitions")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html)

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