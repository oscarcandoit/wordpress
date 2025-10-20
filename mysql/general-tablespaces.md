---
url: https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html
scraped_at: 2025-10-20T03:15:43.856Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html "Hide Sidebar")

[Previous: File-Per-Table Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html "Previous: File-Per-Table Tablespaces")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html "Up: Tablespaces")[Next: Undo Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-tablespaces.html "Next: Undo Tablespaces")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/general-tablespaces.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/general-tablespaces.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/general-tablespaces.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/general-tablespaces.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/general-tablespaces.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/general-tablespaces.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/general-tablespaces.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/general-tablespaces.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html)  / [The InnoDB Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)  /
[InnoDB On-Disk Structures](https://dev.mysql.com/doc/refman/8.0/en/innodb-on-disk-structures.html)  /
[Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)  /

General Tablespaces


#### 17.6.3.3 General Tablespaces

A general tablespace is a shared `InnoDB`
tablespace that is created using [`CREATE\\
      TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/create-tablespace.html "15.1.21 CREATE TABLESPACE Statement") syntax. General tablespace capabilities and
features are described under the following topics in this section:

- [General Tablespace Capabilities](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html#general-tablespaces-capabilities "General Tablespace Capabilities")

- [Creating a General Tablespace](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html#general-tablespaces-creating "Creating a General Tablespace")

- [Adding Tables to a General Tablespace](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html#general-tablespaces-adding-tables "Adding Tables to a General Tablespace")

- [General Tablespace Row Format Support](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html#general-tablespaces-row-format-support "General Tablespace Row Format Support")

- [Moving Tables Between Tablespaces Using ALTER TABLE](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html#general-tablespaces-moving-non-partitioned-tables "Moving Tables Between Tablespaces Using ALTER TABLE")

- [Renaming a General Tablespace](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html#general-tablespaces-renaming "Renaming a General Tablespace")

- [Dropping a General Tablespace](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html#general-tablespaces-dropping "Dropping a General Tablespace")

- [General Tablespace Limitations](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html#general-tablespaces-limitations "General Tablespace Limitations")


##### General Tablespace Capabilities

General tablespaces provide the following capabilities:

- Similar to the system tablespace, general tablespaces are
shared tablespaces capable of storing data for multiple
tables.


- General tablespaces have a potential memory advantage over
[file-per-table\\
tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html "17.6.3.2 File-Per-Table Tablespaces"). The server keeps tablespace metadata in
memory for the lifetime of a tablespace. Multiple tables in
fewer general tablespaces consume less memory for tablespace
metadata than the same number of tables in separate
file-per-table tablespaces.


- General tablespace data files can be placed in a directory
relative to or independent of the MySQL data directory,
which provides you with many of the data file and storage
management capabilities of
[file-per-table\\
tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html "17.6.3.2 File-Per-Table Tablespaces"). As with file-per-table tablespaces, the
ability to place data files outside of the MySQL data
directory allows you to manage performance of critical
tables separately, setup RAID or DRBD for specific tables,
or bind tables to particular disks, for example.


- General tablespaces support all table row formats and
associated features.


- The `TABLESPACE` option can be used with
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") to create tables
in a general tablespaces, file-per-table tablespace, or in
the system tablespace.


- The `TABLESPACE` option can be used with
[`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") to move tables
between general tablespaces, file-per-table tablespaces, and
the system tablespace.


##### Creating a General Tablespace

General tablespaces are created using
[`CREATE TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/create-tablespace.html "15.1.21 CREATE TABLESPACE Statement") syntax.


```sql
CREATE TABLESPACE tablespace_name
    [ADD DATAFILE 'file_name']
    [FILE_BLOCK_SIZE = value]
        [ENGINE [=] engine_name]
```

A general tablespace can be created in the data directory or
outside of it. To avoid conflicts with implicitly created
file-per-table tablespaces, creating a general tablespace in a
subdirectory under the data directory is not supported. When
creating a general tablespace outside of the data directory, the
directory must exist and must be known to
`InnoDB` prior to creating the tablespace. To
make an unknown directory known to `InnoDB`,
add the directory to the
[`innodb_directories`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_directories) argument
value. [`innodb_directories`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_directories) is a
read-only startup option. Configuring it requires restarting the
server.


Examples:


Creating a general tablespace in the data directory:


```sql
mysql> CREATE TABLESPACE `ts1` ADD DATAFILE 'ts1.ibd' Engine=InnoDB;
```

or


```sql
mysql> CREATE TABLESPACE `ts1` Engine=InnoDB;
```

The `ADD DATAFILE` clause is optional as of
MySQL 8.0.14 and required before that. If the `ADD
        DATAFILE` clause is not specified when creating a
tablespace, a tablespace data file with a unique file name is
created implicitly. The unique file name is a 128 bit UUID
formatted into five groups of hexadecimal numbers separated by
dashes
( _`aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee`_).
General tablespace data files include an
`.ibd` file extension. In a replication
environment, the data file name created on the source is not the
same as the data file name created on the replica.


Creating a general tablespace in a directory outside of the data
directory:


```sql
mysql> CREATE TABLESPACE `ts1` ADD DATAFILE '/my/tablespace/directory/ts1.ibd' Engine=InnoDB;
```

You can specify a path that is relative to the data directory as
long as the tablespace directory is not under the data
directory. In this example, the
`my_tablespace` directory is at the same
level as the data directory:


```sql
mysql> CREATE TABLESPACE `ts1` ADD DATAFILE '../my_tablespace/ts1.ibd' Engine=InnoDB;
```

Note

The `ENGINE = InnoDB` clause must be defined
as part of the [`CREATE\\
          TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/create-tablespace.html "15.1.21 CREATE TABLESPACE Statement") statement, or `InnoDB`
must be defined as the default storage engine
( [`default_storage_engine=InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_default_storage_engine)).

##### Adding Tables to a General Tablespace

After creating a general tablespace,
[`CREATE TABLE\\
        tbl_name ... TABLESPACE [=]\\
        tablespace_name`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") or
[`ALTER TABLE\\
        tbl_name TABLESPACE [=]\\
        tablespace_name`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") statements
can be used to add tables to the tablespace, as shown in the
following examples:


[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"):


```sql
mysql> CREATE TABLE t1 (c1 INT PRIMARY KEY) TABLESPACE ts1;
```

[`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement"):


```sql
mysql> ALTER TABLE t2 TABLESPACE ts1;
```

Note

Support for adding table partitions to shared tablespaces was
deprecated in MySQL 5.7.24 and removed in MySQL 8.0.13. Shared
tablespaces include the `InnoDB` system
tablespace and general tablespaces.

For detailed syntax information, see [`CREATE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") and [`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement").

##### General Tablespace Row Format Support

General tablespaces support all table row formats
( `REDUNDANT`, `COMPACT`,
`DYNAMIC`, `COMPRESSED`) with
the caveat that compressed and uncompressed tables cannot
coexist in the same general tablespace due to different physical
page sizes.


For a general tablespace to contain compressed tables
( `ROW_FORMAT=COMPRESSED`), the
`FILE_BLOCK_SIZE` option must be specified, and
the `FILE_BLOCK_SIZE` value must be a valid
compressed page size in relation to the
[`innodb_page_size`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size) value. Also,
the physical page size of the compressed table
( `KEY_BLOCK_SIZE`) must be equal to
`FILE_BLOCK_SIZE/1024`. For example, if
[`innodb_page_size=16KB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size) and
`FILE_BLOCK_SIZE=8K`, the
`KEY_BLOCK_SIZE` of the table must be 8.


The following table shows permitted
[`innodb_page_size`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size),
`FILE_BLOCK_SIZE`, and
`KEY_BLOCK_SIZE` combinations.
`FILE_BLOCK_SIZE` values may also be specified
in bytes. To determine a valid `KEY_BLOCK_SIZE`
value for a given `FILE_BLOCK_SIZE`, divide the
`FILE_BLOCK_SIZE` value by 1024. Table
compression is not support for 32K and 64K
`InnoDB` page sizes. For more information about
`KEY_BLOCK_SIZE`, see
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"), and
[Section 17.9.1.2, “Creating Compressed Tables”](https://dev.mysql.com/doc/refman/8.0/en/innodb-compression-usage.html "17.9.1.2 Creating Compressed Tables").

**Table 17.3 Permitted Page Size, FILE\_BLOCK\_SIZE, and KEY\_BLOCK\_SIZE Combinations**
**for Compressed Tables**

| InnoDB Page Size (innodb\_page\_size) | Permitted FILE\_BLOCK\_SIZE Value | Permitted KEY\_BLOCK\_SIZE Value |
| --- | --- | --- |
| 64KB | 64K (65536) | Compression is not supported |
| 32KB | 32K (32768) | Compression is not supported |
| 16KB | 16K (16384) | None. If [`innodb_page_size`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size) is equal to<br> `FILE_BLOCK_SIZE`, the tablespace cannot<br> contain a compressed table. |
| 16KB | 8K (8192) | 8 |
| 16KB | 4K (4096) | 4 |
| 16KB | 2K (2048) | 2 |
| 16KB | 1K (1024) | 1 |
| 8KB | 8K (8192) | None. If [`innodb_page_size`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size) is equal to<br> `FILE_BLOCK_SIZE`, the tablespace cannot<br> contain a compressed table. |
| 8KB | 4K (4096) | 4 |
| 8KB | 2K (2048) | 2 |
| 8KB | 1K (1024) | 1 |
| 4KB | 4K (4096) | None. If [`innodb_page_size`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size) is equal to<br> `FILE_BLOCK_SIZE`, the tablespace cannot<br> contain a compressed table. |
| 4KB | 2K (2048) | 2 |
| 4KB | 1K (1024) | 1 |

This example demonstrates creating a general tablespace and
adding a compressed table. The example assumes a default
[`innodb_page_size`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size) of 16KB. The
`FILE_BLOCK_SIZE` of 8192 requires that the
compressed table have a `KEY_BLOCK_SIZE` of 8.


```sql
mysql> CREATE TABLESPACE `ts2` ADD DATAFILE 'ts2.ibd' FILE_BLOCK_SIZE = 8192 Engine=InnoDB;

mysql> CREATE TABLE t4 (c1 INT PRIMARY KEY) TABLESPACE ts2 ROW_FORMAT=COMPRESSED KEY_BLOCK_SIZE=8;
```

If you do not specify `FILE_BLOCK_SIZE` when
creating a general tablespace,
`FILE_BLOCK_SIZE` defaults to
[`innodb_page_size`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size). When
`FILE_BLOCK_SIZE` is equal to
[`innodb_page_size`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size), the
tablespace may only contain tables with an uncompressed row
format ( `COMPACT`,
`REDUNDANT`, and `DYNAMIC` row
formats).

##### Moving Tables Between Tablespaces Using ALTER TABLE

[`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") with the
`TABLESPACE` option can be used to move a table
to an existing general tablespace, to a new file-per-table
tablespace, or to the system tablespace.

Note

Support for placing table partitions in shared tablespaces was
deprecated in MySQL 5.7.24 and removed MySQL 8.0.13. Shared
tablespaces include the `InnoDB` system
tablespace and general tablespaces.

To move a table from a file-per-table tablespace or from the
system tablespace to a general tablespace, specify the name of
the general tablespace. The general tablespace must exist. See
[`ALTER TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/alter-tablespace.html "15.1.10 ALTER TABLESPACE Statement") for more
information.


```sql
ALTER TABLE tbl_name TABLESPACE [=] tablespace_name;
```

To move a table from a general tablespace or file-per-table
tablespace to the system tablespace, specify
`innodb_system` as the tablespace name.


```sql
ALTER TABLE tbl_name TABLESPACE [=] innodb_system;
```

To move a table from the system tablespace or a general
tablespace to a file-per-table tablespace, specify
`innodb_file_per_table` as the tablespace name.


```sql
ALTER TABLE tbl_name TABLESPACE [=] innodb_file_per_table;
```

`ALTER TABLE ... TABLESPACE` operations cause a
full table rebuild, even if the `TABLESPACE`
attribute has not changed from its previous value.


`ALTER TABLE ... TABLESPACE` syntax does not
support moving a table from a temporary tablespace to a
persistent tablespace.


The `DATA DIRECTORY` clause is permitted with
`CREATE TABLE ...
        TABLESPACE=innodb_file_per_table` but is otherwise not
supported for use in combination with the
`TABLESPACE` option. As of MySQL 8.0.21, the
directory specified in a `DATA DIRECTORY`
clause must be known to `InnoDB`. For more
information, see
[Using the DATA DIRECTORY Clause](https://dev.mysql.com/doc/refman/8.0/en/innodb-create-table-external.html#innodb-create-table-external-data-directory "Using the DATA DIRECTORY Clause").


Restrictions apply when moving tables from encrypted
tablespaces. See
[Encryption Limitations](https://dev.mysql.com/doc/refman/8.0/en/innodb-data-encryption.html#innodb-data-encryption-limitations "Encryption Limitations").

##### Renaming a General Tablespace

Renaming a general tablespace is supported using
[`ALTER\\
        TABLESPACE ... RENAME TO`](https://dev.mysql.com/doc/refman/8.0/en/alter-tablespace.html "15.1.10 ALTER TABLESPACE Statement") syntax.


```sql
ALTER TABLESPACE s1 RENAME TO s2;
```

The [`CREATE TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_create-tablespace) privilege
is required to rename a general tablespace.


`RENAME TO` operations are implicitly performed
in [`autocommit`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_autocommit) mode regardless
of the [`autocommit`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_autocommit) setting.


A `RENAME TO` operation cannot be performed
while [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") or
[`FLUSH TABLES WITH READ\\
        LOCK`](https://dev.mysql.com/doc/refman/8.0/en/flush.html "15.7.8.3 FLUSH Statement") is in effect for tables that reside in the
tablespace.


Exclusive [metadata\\
locks](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_metadata_lock "metadata lock") are taken on tables within a general tablespace
while the tablespace is renamed, which prevents concurrent DDL.
Concurrent DML is supported.

##### Dropping a General Tablespace

The [`DROP TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/drop-tablespace.html "15.1.33 DROP TABLESPACE Statement") statement is
used to drop an `InnoDB` general tablespace.


All tables must be dropped from the tablespace prior to a
[`DROP TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/drop-tablespace.html "15.1.33 DROP TABLESPACE Statement") operation. If the
tablespace is not empty, [`DROP\\
        TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/drop-tablespace.html "15.1.33 DROP TABLESPACE Statement") returns an error.


Use a query similar to the following to identify tables in a
general tablespace.


```sql
mysql> SELECT a.NAME AS space_name, b.NAME AS table_name FROM INFORMATION_SCHEMA.INNODB_TABLESPACES a,
       INFORMATION_SCHEMA.INNODB_TABLES b WHERE a.SPACE=b.SPACE AND a.NAME LIKE 'ts1';
+------------+------------+
| space_name | table_name |
+------------+------------+
| ts1        | test/t1    |
| ts1        | test/t2    |
| ts1        | test/t3    |
+------------+------------+
```

A general `InnoDB` tablespace is not deleted
automatically when the last table in the tablespace is dropped.
The tablespace must be dropped explicitly using
[`DROP TABLESPACE\\
        tablespace_name`](https://dev.mysql.com/doc/refman/8.0/en/drop-tablespace.html "15.1.33 DROP TABLESPACE Statement").


A general tablespace does not belong to any particular database.
A [`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement") operation can
drop tables that belong to a general tablespace but it cannot
drop the tablespace, even if the [`DROP\\
        DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement") operation drops all tables that belong to the
tablespace.


Similar to the system tablespace, truncating or dropping tables
stored in a general tablespace creates free space internally in
the general tablespace [.ibd data\\
file](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_ibd_file ".ibd file") which can only be used for new
`InnoDB` data. Space is not released back to
the operating system as it is when a file-per-table tablespace
is deleted during a [`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement")
operation.


This example demonstrates how to drop an
`InnoDB` general tablespace. The general
tablespace `ts1` is created with a single
table. The table must be dropped before dropping the tablespace.


```sql
mysql> CREATE TABLESPACE `ts1` ADD DATAFILE 'ts1.ibd' Engine=InnoDB;

mysql> CREATE TABLE t1 (c1 INT PRIMARY KEY) TABLESPACE ts1 Engine=InnoDB;

mysql> DROP TABLE t1;

mysql> DROP TABLESPACE ts1;
```

Note

`tablespace_name`
is a case-sensitive identifier in MySQL.

##### General Tablespace Limitations

- A generated or existing tablespace cannot be changed to a
general tablespace.


- Creation of temporary general tablespaces is not supported.


- General tablespaces do not support temporary tables.


- Similar to the system tablespace, truncating or dropping
tables stored in a general tablespace creates free space
internally in the general tablespace
[.ibd data file](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_ibd_file ".ibd file") which
can only be used for new `InnoDB` data.
Space is not released back to the operating system as it is
for
[file-per-table](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_file_per_table "file-per-table")
tablespaces.



Additionally, a table-copying [`ALTER\\
              TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") operation on table that resides in a shared
tablespace (a general tablespace or the system tablespace)
can increase the amount of space used by the tablespace.
Such operations require as much additional space as the data
in the table plus indexes. The additional space required for
the table-copying [`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement")
operation is not released back to the operating system as it
is for file-per-table tablespaces.


- [`ALTER TABLE ...\\
              DISCARD TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") and
[`ALTER TABLE\\
              ...IMPORT TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") are not supported for tables
that belong to a general tablespace.


- Support for placing table partitions in general tablespaces
was deprecated in MySQL 5.7.24 and removed in MySQL 8.0.13.


- The `ADD DATAFILE` clause is not supported
in a replication environment where the source and replica
reside on the same host, as it would cause the source and
replica to create a tablespace of the same name in the same
location, which is not supported. However, if the
`ADD DATAFILE` clause is omitted, the
tablespace is created in the data directory with a generated
file name that is unique, which is permitted.


- As of MySQL 8.0.21, general tablespaces cannot be created in
the undo tablespace directory
( [`innodb_undo_directory`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_undo_directory))
unless that directly is known to `InnoDB`.
Known directories are those defined by the
[`datadir`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_datadir),
[`innodb_data_home_dir`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_home_dir), and
[`innodb_directories`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_directories)
variables.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html "Previous: File-Per-Table Tablespaces") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html "Up: Tablespaces") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-tablespaces.html "Next: Undo Tablespaces")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html)

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