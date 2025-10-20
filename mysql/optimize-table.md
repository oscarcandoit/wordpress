---
url: https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html
scraped_at: 2025-10-20T03:14:26.850Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "Hide Sidebar")

[Previous: CHECKSUM TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/checksum-table.html "Previous: CHECKSUM TABLE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Table Maintenance Statements](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html "Up: Table Maintenance Statements")[Next: REPAIR TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "Next: REPAIR TABLE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/optimize-table.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/optimize-table.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/optimize-table.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/optimize-table.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/optimize-table.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/optimize-table.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/optimize-table.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/optimize-table.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[Table Maintenance Statements](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html)  /

OPTIMIZE TABLE Statement


#### 15.7.3.4 OPTIMIZE TABLE Statement

``` sql

OPTIMIZE [NO_WRITE_TO_BINLOG | LOCAL]
    TABLE tbl_name [, tbl_name] ...
```

[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") reorganizes the
physical storage of table data and associated index data, to
reduce storage space and improve I/O efficiency when accessing
the table. The exact changes made to each table depend on the
[storage engine](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_storage_engine "storage engine") used
by that table.


Use [`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") in these
cases, depending on the type of table:

- After doing substantial insert, update, or delete operations
on an `InnoDB` table that has its own
[.ibd file](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_ibd_file ".ibd file") because it
was created with the
[`innodb_file_per_table`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_file_per_table)
option enabled. The table and indexes are reorganized, and
disk space can be reclaimed for use by the operating system.


- After doing substantial insert, update, or delete operations
on columns that are part of a `FULLTEXT`
index in an `InnoDB` table. Set the
configuration option
[`innodb_optimize_fulltext_only=1`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_optimize_fulltext_only)
first. To keep the index maintenance period to a reasonable
time, set the
[`innodb_ft_num_word_optimize`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_ft_num_word_optimize)
option to specify how many words to update in the search
index, and run a sequence of `OPTIMIZE
              TABLE` statements until the search index is fully
updated.


- After deleting a large part of a `MyISAM`
or `ARCHIVE` table, or making many changes
to a `MyISAM` or `ARCHIVE
              ` table with variable-length rows (tables that have
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"),
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types"), or
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns). Deleted rows
are maintained in a linked list and subsequent
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") operations reuse old
row positions. You can use [`OPTIMIZE\\
              TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") to reclaim the unused space and to
defragment the data file. After extensive changes to a
table, this statement may also improve performance of
statements that use the table, sometimes significantly.


This statement requires [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select)
and [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_insert) privileges for the
table.


[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") works for
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine"),
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine"), and
[`ARCHIVE`](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html "18.5 The ARCHIVE Storage Engine") tables.
[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") is also supported
for dynamic columns of in-memory
[`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0") tables. It does not work for
fixed-width columns of in-memory tables, nor does it work for
Disk Data tables. The performance of `OPTIMIZE`
on NDB Cluster tables can be tuned using
[`--ndb-optimization-delay`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster-options-variables.html#option_mysqld_ndb-optimization-delay), which
controls the length of time to wait between processing batches
of rows by [`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement"). For
more information, see
[Section 25.2.7.11, “Previous NDB Cluster Issues Resolved in NDB Cluster 8.0”](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster-limitations-resolved.html "25.2.7.11 Previous NDB Cluster Issues Resolved in NDB Cluster 8.0").


For NDB Cluster tables, [`OPTIMIZE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") can be interrupted by (for example) killing the
SQL thread performing the `OPTIMIZE` operation.


By default, [`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") does
_not_ work for tables created using any other
storage engine and returns a result indicating this lack of
support. You can make [`OPTIMIZE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") work for other storage engines by starting
[**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server") with the
[`--skip-new`](https://dev.mysql.com/doc/refman/8.0/en/server-options.html#option_mysqld_skip-new) option. In this case,
[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") is just mapped to
[`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement").


This statement does not work with views.


[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") is supported for
partitioned tables. For information about using this statement
with partitioned tables and table partitions, see
[Section 26.3.4, “Maintenance of Partitions”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-maintenance.html "26.3.4 Maintenance of Partitions").


By default, the server writes [`OPTIMIZE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") statements to the binary log so that they
replicate to replicas. To suppress logging, specify the optional
`NO_WRITE_TO_BINLOG` keyword or its alias
`LOCAL`.

- [OPTIMIZE TABLE Output](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html#optimize-table-output "OPTIMIZE TABLE Output")

- [InnoDB Details](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html#optimize-table-innodb-details "InnoDB Details")

- [MyISAM Details](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html#optimize-table-myisam-details "MyISAM Details")

- [Other Considerations](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html#optimize-table-other-considerations "Other Considerations")


##### OPTIMIZE TABLE Output

[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") returns a result
set with the columns shown in the following table.

| Column | Value |
| --- | --- |
| `Table` | The table name |
| `Op` | Always `optimize` |
| `Msg_type` | `status`, `error`,<br> `info`, `note`, or<br> `warning` |
| `Msg_text` | An informational message |

[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") table catches
and throws any errors that occur while copying table
statistics from the old file to the newly created file. For
example. if the user ID of the owner of the
`.MYD` or `.MYI` file is
different from the user ID of the [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server")
process, [`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement")
generates a "cannot change ownership of the file" error unless
[**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server") is started by the
`root` user.

##### InnoDB Details

For `InnoDB` tables,
[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") is mapped to
[`ALTER TABLE ...\\
          FORCE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement"), which rebuilds the table to update index
statistics and free unused space in the clustered index. This
is displayed in the output of [`OPTIMIZE\\
          TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") when you run it on an
`InnoDB` table, as shown here:


``` sql

mysql> OPTIMIZE TABLE foo;
+----------+----------+----------+-------------------------------------------------------------------+
| Table    | Op       | Msg_type | Msg_text                                                          |
+----------+----------+----------+-------------------------------------------------------------------+
| test.foo | optimize | note     | Table does not support optimize, doing recreate + analyze instead |
| test.foo | optimize | status   | OK                                                                |
+----------+----------+----------+-------------------------------------------------------------------+
```

[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") uses
[online DDL](https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl.html "17.12 InnoDB and Online DDL") for
regular and partitioned `InnoDB` tables,
which reduces downtime for concurrent DML operations. The
table rebuild triggered by [`OPTIMIZE\\
          TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") is completed in place. An exclusive table lock
is only taken briefly during the prepare phase and the commit
phase of the operation. During the prepare phase, metadata is
updated and an intermediate table is created. During the
commit phase, table metadata changes are committed.


[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") rebuilds the
table using the table copy method under the following
conditions:

- When the [`old_alter_table`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_old_alter_table)
system variable is enabled.


- When the server is started with the
[`--skip-new`](https://dev.mysql.com/doc/refman/8.0/en/server-options.html#option_mysqld_skip-new) option.


[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") using
[online DDL](https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl.html "17.12 InnoDB and Online DDL") is not
supported for `InnoDB` tables that contain
`FULLTEXT` indexes. The table copy method is
used instead.


`InnoDB` stores data using a page-allocation
method and does not suffer from fragmentation in the same way
that legacy storage engines (such as
`MyISAM`) do. When considering whether or not
to run optimize, consider the workload of transactions that
your server is expected to process:

- Some level of fragmentation is expected.
`InnoDB` only fills
[pages](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_page "page") 93% full, to
leave room for updates without having to split pages.


- Delete operations might leave gaps that leave pages less
filled than desired, which could make it worthwhile to
optimize the table.


- Updates to rows usually rewrite the data within the same
page, depending on the data type and row format, when
sufficient space is available. See
[Section 17.9.1.5, “How Compression Works for InnoDB Tables”](https://dev.mysql.com/doc/refman/8.0/en/innodb-compression-internals.html "17.9.1.5 How Compression Works for InnoDB Tables") and
[Section 17.10, “InnoDB Row Formats”](https://dev.mysql.com/doc/refman/8.0/en/innodb-row-format.html "17.10 InnoDB Row Formats").


- High-concurrency workloads might leave gaps in indexes
over time, as `InnoDB` retains multiple
versions of the same data due through its
[MVCC](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_mvcc "MVCC") mechanism. See
[Section 17.3, “InnoDB Multi-Versioning”](https://dev.mysql.com/doc/refman/8.0/en/innodb-multi-versioning.html "17.3 InnoDB Multi-Versioning").


##### MyISAM Details

For `MyISAM` tables,
[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") works as
follows:

1. If the table has deleted or split rows, repair the table.


2. If the index pages are not sorted, sort them.


3. If the table's statistics are not up to date (and the
    repair could not be accomplished by sorting the index),
    update them.


##### Other Considerations

[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") is performed
online for regular and partitioned `InnoDB`
tables. Otherwise, MySQL [locks\\
the table](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_table_lock "table lock") during the time [`OPTIMIZE\\
          TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") is running.


[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") does not sort
R-tree indexes, such as spatial indexes on
`POINT` columns. (Bug #23578)

[PREV](https://dev.mysql.com/doc/refman/8.0/en/checksum-table.html "Previous: CHECKSUM TABLE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html "Up: Table Maintenance Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "Next: REPAIR TABLE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html)

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