---
url: https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html
scraped_at: 2025-10-20T03:07:15.953Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html "Hide Sidebar")

[Previous: The INFORMATION_SCHEMA ST_UNITS_OF_MEASURE Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-st-units-of-measure-table.html "Previous: The INFORMATION_SCHEMA ST_UNITS_OF_MEASURE Table")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: INFORMATION_SCHEMA General Tables](https://dev.mysql.com/doc/refman/8.0/en/general-information-schema-tables.html "Up: INFORMATION_SCHEMA General Tables")[Next: The INFORMATION_SCHEMA TABLES_EXTENSIONS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-extensions-table.html "Next: The INFORMATION_SCHEMA TABLES_EXTENSIONS Table")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/information-schema-tables-table.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/information-schema-tables-table.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/information-schema-tables-table.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/information-schema-tables-table.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/information-schema-tables-table.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/information-schema-tables-table.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/information-schema-tables-table.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/information-schema-tables-table.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html)  / [INFORMATION\_SCHEMA Tables](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)  /
[INFORMATION\_SCHEMA General Tables](https://dev.mysql.com/doc/refman/8.0/en/general-information-schema-tables.html)  /

The INFORMATION\_SCHEMA TABLES Table


### 28.3.38 The INFORMATION\_SCHEMA TABLES Table

The [`TABLES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html "28.3.38 The INFORMATION_SCHEMA TABLES Table") table provides information
about tables in databases.


Columns in [`TABLES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html "28.3.38 The INFORMATION_SCHEMA TABLES Table") that represent
table statistics hold cached values. The
[`information_schema_stats_expiry`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_information_schema_stats_expiry)
system variable defines the period of time before cached table
statistics expire. The default is 86400 seconds (24 hours). If
there are no cached statistics or statistics have expired,
statistics are retrieved from storage engines when querying table
statistics columns. To update cached values at any time for a
given table, use [`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement"). To
always retrieve the latest statistics directly from storage
engines, set
[`information_schema_stats_expiry`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_information_schema_stats_expiry)
to `0`. For more information, see
[Section 10.2.3, “Optimizing INFORMATION\_SCHEMA Queries”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html "10.2.3 Optimizing INFORMATION_SCHEMA Queries").

Note

If the [`innodb_read_only`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_read_only) system
variable is enabled, [`ANALYZE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") may fail because it cannot update statistics
tables in the data dictionary, which use
`InnoDB`. For [`ANALYZE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") operations that update the key distribution,
failure may occur even if the operation updates the table itself
(for example, if it is a `MyISAM` table). To
obtain the updated distribution statistics, set
[`information_schema_stats_expiry=0`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_information_schema_stats_expiry).

The [`TABLES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html "28.3.38 The INFORMATION_SCHEMA TABLES Table") table has these columns:

- `TABLE_CATALOG`


The name of the catalog to which the table belongs. This value
is always `def`.


- `TABLE_SCHEMA`


The name of the schema (database) to which the table belongs.


- `TABLE_NAME`


The name of the table.


- `TABLE_TYPE`

`BASE TABLE` for a table,
`VIEW` for a view, or `SYSTEM
            VIEW` for an `INFORMATION_SCHEMA`
table.



The [`TABLES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html "28.3.38 The INFORMATION_SCHEMA TABLES Table") table does not list
`TEMPORARY` tables.


- `ENGINE`


The storage engine for the table. See
[Chapter 17, _The InnoDB Storage Engine_](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine"), and
[Chapter 18, _Alternative Storage Engines_](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html "Chapter 18 Alternative Storage Engines").



For partitioned tables, `ENGINE` shows the
name of the storage engine used by all partitions.


- `VERSION`


This column is unused. With the removal of
`.frm` files in MySQL 8.0, this column now
reports a hardcoded value of `10`, which is
the last `.frm` file version used in MySQL
5.7.


- `ROW_FORMAT`


The row-storage format ( `Fixed`,
`Dynamic`, `Compressed`,
`Redundant`, `Compact`). For
`MyISAM` tables, `Dynamic`
corresponds to what [**myisamchk -dvv**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") reports
as `Packed`.


- `TABLE_ROWS`


The number of rows. Some storage engines, such as
`MyISAM`, store the exact count. For other
storage engines, such as `InnoDB`, this value
is an approximation, and may vary from the actual value by as
much as 40% to 50%. In such cases, use `SELECT
            COUNT(*)` to obtain an accurate count.


`TABLE_ROWS` is `NULL` for
`INFORMATION_SCHEMA` tables.



For [`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") tables, the row count
is only a rough estimate used in SQL optimization. (This is
also true if the [`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") table is
partitioned.)


- `AVG_ROW_LENGTH`


The average row length.


- `DATA_LENGTH`


For `MyISAM`, `DATA_LENGTH`
is the length of the data file, in bytes.



For `InnoDB`, `DATA_LENGTH`
is the approximate amount of space allocated for the clustered
index, in bytes. Specifically, it is the clustered index size,
in pages, multiplied by the `InnoDB` page
size.



Refer to the notes at the end of this section for information
regarding other storage engines.


- `MAX_DATA_LENGTH`


For `MyISAM`,
`MAX_DATA_LENGTH` is maximum length of the
data file. This is the total number of bytes of data that can
be stored in the table, given the data pointer size used.



Unused for `InnoDB`.



Refer to the notes at the end of this section for information
regarding other storage engines.


- `INDEX_LENGTH`


For `MyISAM`, `INDEX_LENGTH`
is the length of the index file, in bytes.



For `InnoDB`, `INDEX_LENGTH`
is the approximate amount of space allocated for non-clustered
indexes, in bytes. Specifically, it is the sum of
non-clustered index sizes, in pages, multiplied by the
`InnoDB` page size.



Refer to the notes at the end of this section for information
regarding other storage engines.


- `DATA_FREE`


The number of allocated but unused bytes.


`InnoDB` tables report the free space of the
tablespace to which the table belongs. For a table located in
the shared tablespace, this is the free space of the shared
tablespace. If you are using multiple tablespaces and the
table has its own tablespace, the free space is for only that
table. Free space means the number of bytes in completely free
extents minus a safety margin. Even if free space displays as
0, it may be possible to insert rows as long as new extents
need not be allocated.



For NDB Cluster, `DATA_FREE` shows the space
allocated on disk for, but not used by, a Disk Data table or
fragment on disk. (In-memory data resource usage is reported
by the `DATA_LENGTH` column.)



For partitioned tables, this value is only an estimate and may
not be absolutely correct. A more accurate method of obtaining
this information in such cases is to query the
`INFORMATION_SCHEMA` [`PARTITIONS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-partitions-table.html "28.3.21 The INFORMATION_SCHEMA PARTITIONS Table") table, as shown in
this example:




``` sql

SELECT SUM(DATA_FREE)
      FROM  INFORMATION_SCHEMA.PARTITIONS
      WHERE TABLE_SCHEMA = 'mydb'
      AND   TABLE_NAME   = 'mytable';
```




For more information, see
[Section 28.3.21, “The INFORMATION\_SCHEMA PARTITIONS Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-partitions-table.html "28.3.21 The INFORMATION_SCHEMA PARTITIONS Table").


- `AUTO_INCREMENT`


The next `AUTO_INCREMENT` value.


- `CREATE_TIME`


When the table was created.


- `UPDATE_TIME`


When the table was last updated. For some storage engines,
this value is `NULL`. Even with
[file-per-table](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_file_per_table "file-per-table") mode
with each `InnoDB` table in a separate
`.ibd` file,
[change buffering](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_change_buffering "change buffering")
can delay the write to the data file, so the file modification
time is different from the time of the last insert, update, or
delete. For `MyISAM`, the data file timestamp
is used; however, on Windows the timestamp is not updated by
updates, so the value is inaccurate.


`UPDATE_TIME` displays a timestamp value for
the last [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"),
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"), or
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") performed on
`InnoDB` tables that are not partitioned. For
MVCC, the timestamp value reflects the
[`COMMIT`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements") time, which is
considered the last update time. Timestamps are not persisted
when the server is restarted or when the table is evicted from
the `InnoDB` data dictionary cache.


- `CHECK_TIME`


When the table was last checked. Not all storage engines
update this time, in which case, the value is always
`NULL`.



For partitioned [`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") tables,
`CHECK_TIME` is always
`NULL`.


- `TABLE_COLLATION`


The table default collation. The output does not explicitly
list the table default character set, but the collation name
begins with the character set name.


- `CHECKSUM`


The live checksum value, if any.


- `CREATE_OPTIONS`


Extra options used with [`CREATE\\
            TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement").


`CREATE_OPTIONS` shows
`partitioned` for a partitioned table.



Prior to MySQL 8.0.16, `CREATE_OPTIONS` shows
the `ENCRYPTION` clause specified for tables
created in file-per-table tablespaces. As of MySQL 8.0.16, it
shows the encryption clause for file-per-table tablespaces if
the table is encrypted or if the specified encryption differs
from the schema encryption. The encryption clause is not shown
for tables created in general tablespaces. To identify
encrypted file-per-table and general tablespaces, query the
[`INNODB_TABLESPACES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-tablespaces-table.html "28.4.24 The INFORMATION_SCHEMA INNODB_TABLESPACES Table") `ENCRYPTION` column.



When creating a table with
[strict mode](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_strict_mode "strict mode") disabled,
the storage engine's default row format is used if the
specified row format is not supported. The actual row format
of the table is reported in the `ROW_FORMAT`
column. `CREATE_OPTIONS` shows the row format
that was specified in the [`CREATE\\
            TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement.



When altering the storage engine of a table, table options
that are not applicable to the new storage engine are retained
in the table definition to enable reverting the table with its
previously defined options to the original storage engine, if
necessary. The `CREATE_OPTIONS` column may
show retained options.


- `TABLE_COMMENT`


The comment used when creating the table (or information as to
why MySQL could not access the table information).


#### Notes

- For [`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0") tables, the output of
this statement shows appropriate values for the
`AVG_ROW_LENGTH` and
`DATA_LENGTH` columns, with the exception
that [`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns are not taken
into account.


- For [`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0") tables,
`DATA_LENGTH` includes data stored in main
memory only; the `MAX_DATA_LENGTH` and
`DATA_FREE` columns apply to Disk Data.


- For NDB Cluster Disk Data tables,
`MAX_DATA_LENGTH` shows the space allocated
for the disk part of a Disk Data table or fragment. (In-memory
data resource usage is reported by the
`DATA_LENGTH` column.)


- For `MEMORY` tables, the
`DATA_LENGTH`,
`MAX_DATA_LENGTH`, and
`INDEX_LENGTH` values approximate the actual
amount of allocated memory. The allocation algorithm reserves
memory in large amounts to reduce the number of allocation
operations.


- For views, most [`TABLES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html "28.3.38 The INFORMATION_SCHEMA TABLES Table") columns
are 0 or `NULL` except that
`TABLE_NAME` indicates the view name,
`CREATE_TIME` indicates the creation time,
and `TABLE_COMMENT` says
`VIEW`.


Table information is also available from the
[`SHOW TABLE STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement") and
[`SHOW TABLES`](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html "15.7.7.39 SHOW TABLES Statement") statements. See
[Section 15.7.7.38, “SHOW TABLE STATUS Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement"), and
[Section 15.7.7.39, “SHOW TABLES Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html "15.7.7.39 SHOW TABLES Statement"). The following statements are
equivalent:


``` sql

SELECT
    TABLE_NAME, ENGINE, VERSION, ROW_FORMAT, TABLE_ROWS, AVG_ROW_LENGTH,
    DATA_LENGTH, MAX_DATA_LENGTH, INDEX_LENGTH, DATA_FREE, AUTO_INCREMENT,
    CREATE_TIME, UPDATE_TIME, CHECK_TIME, TABLE_COLLATION, CHECKSUM,
    CREATE_OPTIONS, TABLE_COMMENT
  FROM INFORMATION_SCHEMA.TABLES
  WHERE table_schema = 'db_name'
  [AND table_name LIKE 'wild']

SHOW TABLE STATUS
  FROM db_name
  [LIKE 'wild']
```

The following statements are equivalent:


``` sql

SELECT
  TABLE_NAME, TABLE_TYPE
  FROM INFORMATION_SCHEMA.TABLES
  WHERE table_schema = 'db_name'
  [AND table_name LIKE 'wild']

SHOW FULL TABLES
  FROM db_name
  [LIKE 'wild']
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/information-schema-st-units-of-measure-table.html "Previous: The INFORMATION_SCHEMA ST_UNITS_OF_MEASURE Table") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/general-information-schema-tables.html "Up: INFORMATION_SCHEMA General Tables") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-extensions-table.html "Next: The INFORMATION_SCHEMA TABLES_EXTENSIONS Table")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html)

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