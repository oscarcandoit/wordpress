---
url: https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html
scraped_at: 2025-10-20T03:03:06.742Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "Hide Sidebar")

[Previous: Setting the Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/storage-engine-setting.html "Previous: Setting the Storage Engine")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Alternative Storage Engines](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html "Up: Alternative Storage Engines")[Next: MyISAM Startup Options](https://dev.mysql.com/doc/refman/8.0/en/myisam-start.html "Next: MyISAM Startup Options")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/myisam-storage-engine.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/myisam-storage-engine.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/myisam-storage-engine.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/myisam-storage-engine.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/myisam-storage-engine.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/myisam-storage-engine.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/myisam-storage-engine.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/myisam-storage-engine.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Alternative Storage Engines](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html)  /
The MyISAM Storage Engine


## 18.2 The MyISAM Storage Engine

[18.2.1 MyISAM Startup Options](https://dev.mysql.com/doc/refman/8.0/en/myisam-start.html)[18.2.2 Space Needed for Keys](https://dev.mysql.com/doc/refman/8.0/en/key-space.html)[18.2.3 MyISAM Table Storage Formats](https://dev.mysql.com/doc/refman/8.0/en/myisam-table-formats.html)[18.2.4 MyISAM Table Problems](https://dev.mysql.com/doc/refman/8.0/en/myisam-table-problems.html)

`MyISAM` is based on the older (and no longer
available) `ISAM` storage engine but has many
useful extensions.

**Table 18.2 MyISAM Storage Engine Features**

| Feature | Support |
| --- | --- |
| **B-tree indexes** | Yes |
| **Backup/point-in-time recovery** (Implemented in the server, rather than in the storage engine.) | Yes |
| **Cluster database support** | No |
| **Clustered indexes** | No |
| **Compressed data** | Yes (Compressed MyISAM tables are supported only when using the compressed row format. Tables using the compressed row format with MyISAM are read only.) |
| **Data caches** | No |
| **Encrypted data** | Yes (Implemented in the server via encryption functions.) |
| **Foreign key support** | No |
| **Full-text search indexes** | Yes |
| **Geospatial data type support** | Yes |
| **Geospatial indexing support** | Yes |
| **Hash indexes** | No |
| **Index caches** | Yes |
| **Locking granularity** | Table |
| **MVCC** | No |
| **Replication support** (Implemented in the server, rather than in the storage engine.) | Yes |
| **Storage limits** | 256TB |
| **T-tree indexes** | No |
| **Transactions** | No |
| **Update statistics for data dictionary** | Yes |

Each `MyISAM` table is stored on disk in two files.
The files have names that begin with the table name and have an
extension to indicate the file type. The data file has an
`.MYD` ( `MYData`) extension. The
index file has an `.MYI`
( `MYIndex`) extension. The table definition is
stored in the MySQL data dictionary.


To specify explicitly that you want a `MyISAM`
table, indicate that with an `ENGINE` table option:


```sql
CREATE TABLE t (i INT) ENGINE = MYISAM;
```

In MySQL 8.0, it is normally necessary to use
`ENGINE` to specify the `MyISAM`
storage engine because `InnoDB` is the default
engine.


You can check or repair `MyISAM` tables with the
[**mysqlcheck**](https://dev.mysql.com/doc/refman/8.0/en/mysqlcheck.html "6.5.3 mysqlcheck — A Table Maintenance Program") client or [**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility")
utility. You can also compress `MyISAM` tables with
[**myisampack**](https://dev.mysql.com/doc/refman/8.0/en/myisampack.html "6.6.6 myisampack — Generate Compressed, Read-Only MyISAM Tables") to take up much less space. See
[Section 6.5.3, “mysqlcheck — A Table Maintenance Program”](https://dev.mysql.com/doc/refman/8.0/en/mysqlcheck.html "6.5.3 mysqlcheck — A Table Maintenance Program"), [Section 6.6.4, “myisamchk — MyISAM Table-Maintenance Utility”](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility"), and
[Section 6.6.6, “myisampack — Generate Compressed, Read-Only MyISAM Tables”](https://dev.mysql.com/doc/refman/8.0/en/myisampack.html "6.6.6 myisampack — Generate Compressed, Read-Only MyISAM Tables").


In MySQL 8.0, the `MyISAM` storage
engine provides no partitioning support. _Partitioned_
_`MyISAM` tables created in previous versions of_
_MySQL cannot be used in MySQL 8.0_. For more
information, see
[Section 26.6.2, “Partitioning Limitations Relating to Storage Engines”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-limitations-storage-engines.html "26.6.2 Partitioning Limitations Relating to Storage Engines"). For help
with upgrading such tables so that they can be used in MySQL
8.0, see
[Section 3.5, “Changes in MySQL 8.0”](https://dev.mysql.com/doc/refman/8.0/en/upgrading-from-previous-series.html "3.5 Changes in MySQL 8.0").


`MyISAM` tables have the following characteristics:

- All data values are stored with the low byte first. This makes
the data machine and operating system independent. The only
requirements for binary portability are that the machine uses
two's-complement signed integers and IEEE floating-point format.
These requirements are widely used among mainstream machines.
Binary compatibility might not be applicable to embedded
systems, which sometimes have peculiar processors.



There is no significant speed penalty for storing data low byte
first; the bytes in a table row normally are unaligned and it
takes little more processing to read an unaligned byte in order
than in reverse order. Also, the code in the server that fetches
column values is not time critical compared to other code.


- All numeric key values are stored with the high byte first to
permit better index compression.


- Large files (up to 63-bit file length) are supported on file
systems and operating systems that support large files.


- There is a limit of
(232)2
(1.844E+19) rows in a `MyISAM` table.


- The maximum number of indexes per `MyISAM`
table is 64.



The maximum number of columns per index is 16.


- The maximum key length is 1000 bytes. This can also be changed
by changing the source and recompiling. For the case of a key
longer than 250 bytes, a larger key block size than the default
of 1024 bytes is used.


- When rows are inserted in sorted order (as when you are using an
`AUTO_INCREMENT` column), the index tree is
split so that the high node only contains one key. This improves
space utilization in the index tree.


- Internal handling of one `AUTO_INCREMENT`
column per table is supported. `MyISAM`
automatically updates this column for
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") and
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") operations. This makes
`AUTO_INCREMENT` columns faster (at least 10%).
Values at the top of the sequence are not reused after being
deleted. (When an `AUTO_INCREMENT` column is
defined as the last column of a multiple-column index, reuse of
values deleted from the top of a sequence does occur.) The
`AUTO_INCREMENT` value can be reset with
[`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") or
[**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility").


- Dynamic-sized rows are much less fragmented when mixing deletes
with updates and inserts. This is done by automatically
combining adjacent deleted blocks and by extending blocks if the
next block is deleted.


- `MyISAM` supports concurrent inserts: If a
table has no free blocks in the middle of the data file, you can
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") new rows into it at the
same time that other threads are reading from the table. A free
block can occur as a result of deleting rows or an update of a
dynamic length row with more data than its current contents.
When all free blocks are used up (filled in), future inserts
become concurrent again. See
[Section 10.11.3, “Concurrent Inserts”](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html "10.11.3 Concurrent Inserts").


- You can put the data file and index file in different
directories on different physical devices to get more speed with
the `DATA DIRECTORY` and `INDEX
          DIRECTORY` table options to [`CREATE\\
          TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"). See [Section 15.1.20, “CREATE TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement").


- [`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") and
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns can be indexed.


- `NULL` values are permitted in indexed columns.
This takes 0 to 1 bytes per key.


- Each character column can have a different character set. See
[Chapter 12, _Character Sets, Collations, Unicode_](https://dev.mysql.com/doc/refman/8.0/en/charset.html "Chapter 12 Character Sets, Collations, Unicode").


- There is a flag in the `MyISAM` index file that
indicates whether the table was closed correctly. If
[**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server") is started with the
[`myisam_recover_options`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_myisam_recover_options) system
variable set, `MyISAM` tables are automatically
checked when opened, and are repaired if the table wasn't closed
properly.


- [**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") marks tables as checked if you run
it with the [`--update-state`](https://dev.mysql.com/doc/refman/8.0/en/myisamchk-check-options.html#option_myisamchk_update-state)
option. [**myisamchk --fast**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") checks only those
tables that don't have this mark.


- [**myisamchk --analyze**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") stores statistics for
portions of keys, as well as for entire keys.


- [**myisampack**](https://dev.mysql.com/doc/refman/8.0/en/myisampack.html "6.6.6 myisampack — Generate Compressed, Read-Only MyISAM Tables") can pack
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") and
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") columns.


`MyISAM` also supports the following features:

- Support for a true [`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") type;
a [`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") column starts with a
length stored in one or two bytes.


- Tables with [`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") columns may
have fixed or dynamic row length.


- The sum of the lengths of the
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") and
[`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") columns in a table may be up
to 64KB.


- Arbitrary length `UNIQUE` constraints.


### Additional Resources

- A forum dedicated to the `MyISAM` storage
engine is available at [https://forums.mysql.com/list.php?21](https://forums.mysql.com/list.php?21).


[PREV](https://dev.mysql.com/doc/refman/8.0/en/storage-engine-setting.html "Previous: Setting the Storage Engine") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html "Up: Alternative Storage Engines") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/myisam-start.html "Next: MyISAM Startup Options")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html)

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