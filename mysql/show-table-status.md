---
url: https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html
scraped_at: 2025-10-20T03:06:43.467Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "Hide Sidebar")

[Previous: SHOW STATUS Statement](https://dev.mysql.com/doc/refman/8.0/en/show-status.html "Previous: SHOW STATUS Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements")[Next: SHOW TABLES Statement](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html "Next: SHOW TABLES Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/show-table-status.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/show-table-status.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/show-table-status.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/show-table-status.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/show-table-status.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/show-table-status.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/show-table-status.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/show-table-status.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)  /

SHOW TABLE STATUS Statement


#### 15.7.7.38 SHOW TABLE STATUS Statement

```sql
SHOW TABLE STATUS
    [{FROM | IN} db_name]
    [LIKE 'pattern' | WHERE expr]
```

[`SHOW TABLE STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement") works likes
[`SHOW TABLES`](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html "15.7.7.39 SHOW TABLES Statement"), but provides a lot
of information about each non- `TEMPORARY`
table. You can also get this list using the [**mysqlshow**\\
**--status _`db_name`_**](https://dev.mysql.com/doc/refman/8.0/en/mysqlshow.html "6.5.7 mysqlshow — Display Database, Table, and Column Information") command.
The [`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) clause, if present,
indicates which table names to match. The
`WHERE` clause can be given to select rows
using more general conditions, as discussed in
[Section 28.8, “Extensions to SHOW Statements”](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html "28.8 Extensions to SHOW Statements").


This statement also displays information about views.


[`SHOW TABLE STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement") output has
these columns:

- `Name`


The name of the table.


- `Engine`


The storage engine for the table. See
[Chapter 17, _The InnoDB Storage Engine_](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine"), and
[Chapter 18, _Alternative Storage Engines_](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html "Chapter 18 Alternative Storage Engines").



For partitioned tables, `Engine` shows the
name of the storage engine used by all partitions.


- `Version`


This column is unused. With the removal of
`.frm` files in MySQL 8.0, this column
now reports a hardcoded value of `10`,
which is the last `.frm` file version
used in MySQL 5.7.


- `Row_format`


The row-storage format ( `Fixed`,
`Dynamic`, `Compressed`,
`Redundant`, `Compact`).
For `MyISAM` tables,
`Dynamic` corresponds to what
[**myisamchk -dvv**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") reports as
`Packed`.


- `Rows`


The number of rows. Some storage engines, such as
`MyISAM`, store the exact count. For other
storage engines, such as `InnoDB`, this
value is an approximation, and may vary from the actual
value by as much as 40% to 50%. In such cases, use
`SELECT COUNT(*)` to obtain an accurate
count.



The `Rows` value is `NULL`
for `INFORMATION_SCHEMA` tables.



For [`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") tables, the row
count is only a rough estimate used in SQL optimization.
(This is also true if the
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") table is partitioned.)


- `Avg_row_length`


The average row length.


- `Data_length`


For `MyISAM`,
`Data_length` is the length of the data
file, in bytes.



For `InnoDB`,
`Data_length` is the approximate amount of
space allocated for the clustered index, in bytes.
Specifically, it is the clustered index size, in pages,
multiplied by the `InnoDB` page size.



Refer to the notes at the end of this section for
information regarding other storage engines.


- `Max_data_length`


For `MyISAM`,
`Max_data_length` is maximum length of the
data file. This is the total number of bytes of data that
can be stored in the table, given the data pointer size
used.



Unused for `InnoDB`.



Refer to the notes at the end of this section for
information regarding other storage engines.


- `Index_length`


For `MyISAM`,
`Index_length` is the length of the index
file, in bytes.



For `InnoDB`,
`Index_length` is the approximate amount of
space allocated for non-clustered indexes, in bytes.
Specifically, it is the sum of non-clustered index sizes, in
pages, multiplied by the `InnoDB` page
size.



Refer to the notes at the end of this section for
information regarding other storage engines.


- `Data_free`


The number of allocated but unused bytes.


`InnoDB` tables report the free space of
the tablespace to which the table belongs. For a table
located in the shared tablespace, this is the free space of
the shared tablespace. If you are using multiple tablespaces
and the table has its own tablespace, the free space is for
only that table. Free space means the number of bytes in
completely free extents minus a safety margin. Even if free
space displays as 0, it may be possible to insert rows as
long as new extents need not be allocated.



For NDB Cluster, `Data_free` shows the
space allocated on disk for, but not used by, a Disk Data
table or fragment on disk. (In-memory data resource usage is
reported by the `Data_length` column.)



For partitioned tables, this value is only an estimate and
may not be absolutely correct. A more accurate method of
obtaining this information in such cases is to query the
`INFORMATION_SCHEMA` [`PARTITIONS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-partitions-table.html "28.3.21 The INFORMATION_SCHEMA PARTITIONS Table") table, as shown in
this example:



```sql
SELECT SUM(DATA_FREE)
      FROM  INFORMATION_SCHEMA.PARTITIONS
      WHERE TABLE_SCHEMA = 'mydb'
      AND   TABLE_NAME   = 'mytable';
```



For more information, see
[Section 28.3.21, “The INFORMATION\_SCHEMA PARTITIONS Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-partitions-table.html "28.3.21 The INFORMATION_SCHEMA PARTITIONS Table").


- `Auto_increment`


The next `AUTO_INCREMENT` value.


- `Create_time`


When the table was created.


- `Update_time`


When the data file was last updated. For some storage
engines, this value is `NULL`. For example,
`InnoDB` stores multiple tables in its
[system\\
tablespace](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_system_tablespace "system tablespace") and the data file timestamp does not
apply. Even with
[file-per-table](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_file_per_table "file-per-table")
mode with each `InnoDB` table in a separate
`.ibd` file,
[change\\
buffering](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_change_buffering "change buffering") can delay the write to the data file, so
the file modification time is different from the time of the
last insert, update, or delete. For
`MyISAM`, the data file timestamp is used;
however, on Windows the timestamp is not updated by updates,
so the value is inaccurate.


`Update_time` displays a timestamp value
for the last [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"),
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"), or
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") performed on
`InnoDB` tables that are not partitioned.
For MVCC, the timestamp value reflects the
[`COMMIT`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements") time, which is
considered the last update time. Timestamps are not
persisted when the server is restarted or when the table is
evicted from the `InnoDB` data dictionary
cache.


- `Check_time`


When the table was last checked. Not all storage engines
update this time, in which case, the value is always
`NULL`.



For partitioned [`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") tables,
`Check_time` is always
`NULL`.


- `Collation`


The table default collation. The output does not explicitly
list the table default character set, but the collation name
begins with the character set name.


- `Checksum`


The live checksum value, if any.


- `Create_options`


Extra options used with [`CREATE\\
              TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement").


`Create_options` shows
`partitioned` for a partitioned table.



Prior to MySQL 8.0.16, `Create_options`
shows the `ENCRYPTION` clause specified for
tables created in file-per-table tablespaces. As of MySQL
8.0.16, it shows the encryption clause for file-per-table
tablespaces if the table is encrypted or if the specified
encryption differs from the schema encryption. The
encryption clause is not shown for tables created in general
tablespaces. To identify encrypted file-per-table and
general tablespaces, query the
[`INNODB_TABLESPACES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-tablespaces-table.html "28.4.24 The INFORMATION_SCHEMA INNODB_TABLESPACES Table") `ENCRYPTION` column.



When creating a table with
[strict mode](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_strict_mode "strict mode")
disabled, the storage engine's default row format is
used if the specified row format is not supported. The
actual row format of the table is reported in the
`Row_format` column.
`Create_options` shows the row format that
was specified in the [`CREATE\\
              TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement.



When altering the storage engine of a table, table options
that are not applicable to the new storage engine are
retained in the table definition to enable reverting the
table with its previously defined options to the original
storage engine, if necessary.
`Create_options` may show retained options.


- `Comment`


The comment used when creating the table (or information as
to why MySQL could not access the table information).


##### Notes

- For `InnoDB` tables,
[`SHOW TABLE STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement") does not
give accurate statistics except for the physical size
reserved by the table. The row count is only a rough
estimate used in SQL optimization.


- For [`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0") tables, the output of
this statement shows appropriate values for the
`Avg_row_length` and
`Data_length` columns, with the exception
that [`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns are not
taken into account.


- For [`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0") tables,
`Data_length` includes data stored in main
memory only; the `Max_data_length` and
`Data_free` columns apply to Disk Data.


- For NDB Cluster Disk Data tables,
`Max_data_length` shows the space allocated
for the disk part of a Disk Data table or fragment.
(In-memory data resource usage is reported by the
`Data_length` column.)


- For `MEMORY` tables, the
`Data_length`,
`Max_data_length`, and
`Index_length` values approximate the
actual amount of allocated memory. The allocation algorithm
reserves memory in large amounts to reduce the number of
allocation operations.


- For views, most columns displayed by
[`SHOW TABLE STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement") are 0 or
`NULL` except that `Name`
indicates the view name, `Create_time`
indicates the creation time, and `Comment`
says `VIEW`.


Table information is also available from the
`INFORMATION_SCHEMA` [`TABLES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html "28.3.38 The INFORMATION_SCHEMA TABLES Table") table. See
[Section 28.3.38, “The INFORMATION\_SCHEMA TABLES Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html "28.3.38 The INFORMATION_SCHEMA TABLES Table").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/show-status.html "Previous: SHOW STATUS Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html "Next: SHOW TABLES Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html)

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