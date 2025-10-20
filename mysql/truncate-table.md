---
url: https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html
scraped_at: 2025-10-20T03:11:15.462Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "Hide Sidebar")

[Previous: RENAME TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/rename-table.html "Previous: RENAME TABLE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements")[Next: Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Next: Data Manipulation Statements")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/truncate-table.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/truncate-table.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/truncate-table.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/truncate-table.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/truncate-table.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/truncate-table.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/truncate-table.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/truncate-table.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html)  /

TRUNCATE TABLE Statement


### 15.1.37 TRUNCATE TABLE Statement

```sql

TRUNCATE [TABLE] tbl_name
```

[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") empties a table
completely. It requires the [`DROP`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_drop)
privilege. Logically, [`TRUNCATE\\
      TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") is similar to a
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statement that deletes all
rows, or a sequence of [`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement")
and [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statements.


To achieve high performance, [`TRUNCATE\\
      TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") bypasses the DML method of deleting data. Thus, it
does not cause `ON DELETE` triggers to fire, it
cannot be performed for `InnoDB` tables with
parent-child foreign key relationships, and it cannot be rolled
back like a DML operation. However, `TRUNCATE
      TABLE` operations on tables that use a storage engine
which supports atomic DDL are either fully committed or rolled
back if the server halts during their operation. For more
information, see [Section 15.1.1, “Atomic Data Definition Statement Support”](https://dev.mysql.com/doc/refman/8.0/en/atomic-ddl.html "15.1.1 Atomic Data Definition Statement Support").


Although [`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") is similar
to [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"), it is classified as a
DDL statement rather than a DML statement. It differs from
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") in the following ways:

- Truncate operations drop and re-create the table, which is
much faster than deleting rows one by one, particularly for
large tables.


- Truncate operations cause an implicit commit, and so cannot be
rolled back. See [Section 15.3.3, “Statements That Cause an Implicit Commit”](https://dev.mysql.com/doc/refman/8.0/en/implicit-commit.html "15.3.3 Statements That Cause an Implicit Commit").


- Truncation operations cannot be performed if the session holds
an active table lock.


- [`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") fails for an
`InnoDB` table or
[`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0") table if there are any
`FOREIGN KEY` constraints from other tables
that reference the table. Foreign key constraints between
columns of the same table are permitted.


- Truncation operations do not return a meaningful value for the
number of deleted rows. The usual result is “0 rows
affected,” which should be interpreted as “no
information.”

- As long as the table definition is valid, the table can be
re-created as an empty table with
[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement"), even if the
data or index files have become corrupted.


- Any `AUTO_INCREMENT` value is reset to its
start value. This is true even for `MyISAM`
and `InnoDB`, which normally do not reuse
sequence values.


- When used with partitioned tables,
[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") preserves the
partitioning; that is, the data and index files are dropped
and re-created, while the partition definitions are
unaffected.


- The [`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") statement
does not invoke `ON DELETE` triggers.


- Truncating a corrupted `InnoDB` table is
supported.


[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") is treated for
purposes of binary logging and replication as DDL rather than DML,
and is always logged as a statement.


[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") for a table closes
all handlers for the table that were opened with
[`HANDLER OPEN`](https://dev.mysql.com/doc/refman/8.0/en/handler.html "15.2.5 HANDLER Statement").


In MySQL 5.7 and earlier, on a system with a large buffer pool and
[`innodb_adaptive_hash_index`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_adaptive_hash_index)
enabled, a `TRUNCATE TABLE` operation could cause
a temporary drop in system performance due to an LRU scan that
occurred when removing the table's adaptive hash index entries
(Bug #68184). The remapping of [`TRUNCATE\\
      TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") to [`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") and
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") in MySQL 8.0 avoids
the problematic LRU scan.


[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") can be used with
Performance Schema summary tables, but the effect is to reset the
summary columns to 0 or `NULL`, not to remove
rows. See [Section 29.12.20, “Performance Schema Summary Tables”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-summary-tables.html "29.12.20 Performance Schema Summary Tables").


Truncating an `InnoDB` table that resides in a
file-per-table tablespace drops the existing tablespace and
creates a new one. As of MySQL 8.0.21, if the tablespace was
created with an earlier version and resides in an unknown
directory, `InnoDB` creates the new tablespace in
the default location and writes the following warning to the error
log: The DATA DIRECTORY location must be in a known
directory. The DATA DIRECTORY location will be ignored and the
file will be put into the default datadir location.
Known directories are those defined by the
[`datadir`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_datadir),
[`innodb_data_home_dir`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_home_dir), and
[`innodb_directories`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_directories) variables. To
have [`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") create the
tablespace in its current location, add the directory to the
[`innodb_directories`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_directories) setting before
running [`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/rename-table.html "Previous: RENAME TABLE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Next: Data Manipulation Statements")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html)

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