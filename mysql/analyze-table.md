---
url: https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html
scraped_at: 2025-10-20T03:14:36.217Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "Hide Sidebar")

[Previous: Table Maintenance Statements](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html "Previous: Table Maintenance Statements")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Table Maintenance Statements](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html "Up: Table Maintenance Statements")[Next: CHECK TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "Next: CHECK TABLE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/analyze-table.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/analyze-table.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/analyze-table.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/analyze-table.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/analyze-table.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/analyze-table.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/analyze-table.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/analyze-table.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[Table Maintenance Statements](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html)  /

ANALYZE TABLE Statement


#### 15.7.3.1 ANALYZE TABLE Statement

``` sql

ANALYZE [NO_WRITE_TO_BINLOG | LOCAL]
    TABLE tbl_name [, tbl_name] ...

ANALYZE [NO_WRITE_TO_BINLOG | LOCAL]
    TABLE tbl_name
    UPDATE HISTOGRAM ON col_name [, col_name] ...
        [WITH N BUCKETS]

ANALYZE [NO_WRITE_TO_BINLOG | LOCAL]
    TABLE tbl_name
    UPDATE HISTOGRAM ON col_name [USING DATA 'json_data']

ANALYZE [NO_WRITE_TO_BINLOG | LOCAL]
    TABLE tbl_name
    DROP HISTOGRAM ON col_name [, col_name] ...
```

[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") generates table
statistics:

- [`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") without any
`HISTOGRAM` clause performs a key
distribution analysis and stores the distribution for the
named table or tables. For `MyISAM` tables,
[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") for key
distribution analysis is equivalent to using
[**myisamchk --analyze**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility").


- [`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") with the
`UPDATE HISTOGRAM` clause generates
histogram statistics for the named table columns and stores
them in the data dictionary. Only one table name is
permitted for this syntax. MySQL 8.0.31 and later also
supports setting the histogram of a single column to a
user-defined JSON value.


- [`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") with the
`DROP HISTOGRAM` clause removes histogram
statistics for the named table columns from the data
dictionary. Only one table name is permitted for this
syntax.


This statement requires [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select)
and [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_insert) privileges for the
table.


[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") works with
`InnoDB`, `NDB`, and
`MyISAM` tables. It does not work with views.


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


[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") is supported for
partitioned tables, and you can use `ALTER TABLE ...
        ANALYZE PARTITION` to analyze one or more partitions;
for more information, see [Section 15.1.9, “ALTER TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement"), and
[Section 26.3.4, “Maintenance of Partitions”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-maintenance.html "26.3.4 Maintenance of Partitions").


During the analysis, the table is locked with a read lock for
`InnoDB` and `MyISAM`.


By default, the server writes [`ANALYZE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") statements to the binary log so that they
replicate to replicas. To suppress logging, specify the optional
`NO_WRITE_TO_BINLOG` keyword or its alias
`LOCAL`.


Previously, `ANALYZE TABLE` required a flush
lock. This meant that, when there were long running statements
or transactions still using the table when `ANALYZE
        TABLE` was invoked, any following statements and
transactions had to wait for those operations to finish before
the flush lock could be released. This issue is resolved in
MySQL 8.0.24 (and later), where `ANALYZE TABLE`
no longer causes subsequent operations to wait.

- [ANALYZE TABLE Output](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html#analyze-table-output "ANALYZE TABLE Output")

- [Key Distribution Analysis](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html#analyze-table-key-distribution-analysis "Key Distribution Analysis")

- [Histogram Statistics Analysis](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html#analyze-table-histogram-statistics-analysis "Histogram Statistics Analysis")

- [Other Considerations](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html#analyze-table-other-considerations "Other Considerations")


##### ANALYZE TABLE Output

[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") returns a result
set with the columns shown in the following table.

| Column | Value |
| --- | --- |
| `Table` | The table name |
| `Op` | `analyze` or `histogram` |
| `Msg_type` | `status`, `error`,<br> `info`, `note`, or<br> `warning` |
| `Msg_text` | An informational message |

##### Key Distribution Analysis

[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") without either
`HISTOGRAM` clause performs a key
distribution analysis and stores the distribution for the
table or tables. Any existing histogram statistics remain
unaffected.


If the table has not changed since the last key distribution
analysis, the table is not analyzed again.


MySQL uses the stored key distribution to decide the order in
which tables should be joined for joins on something other
than a constant. In addition, key distributions can be used
when deciding which indexes to use for a specific table within
a query.


To check the stored key distribution cardinality, use the
[`SHOW INDEX`](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "15.7.7.22 SHOW INDEX Statement") statement or the
`INFORMATION_SCHEMA` [`STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html "28.3.34 The INFORMATION_SCHEMA STATISTICS Table") table. See
[Section 15.7.7.22, “SHOW INDEX Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "15.7.7.22 SHOW INDEX Statement"), and
[Section 28.3.34, “The INFORMATION\_SCHEMA STATISTICS Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html "28.3.34 The INFORMATION_SCHEMA STATISTICS Table").


For `InnoDB` tables,
[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") determines index
cardinality by performing random dives on each of the index
trees and updating index cardinality estimates accordingly.
Because these are only estimates, repeated runs of
[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") could produce
different numbers. This makes [`ANALYZE\\
          TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") fast on `InnoDB` tables but
not 100% accurate because it does not take all rows into
account.


You can make the
[statistics](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_statistics "statistics") collected by
[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") more precise and
more stable by enabling
[`innodb_stats_persistent`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_stats_persistent), as
explained in [Section 17.8.10.1, “Configuring Persistent Optimizer Statistics Parameters”](https://dev.mysql.com/doc/refman/8.0/en/innodb-persistent-stats.html "17.8.10.1 Configuring Persistent Optimizer Statistics Parameters"). When
[`innodb_stats_persistent`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_stats_persistent) is
enabled, it is important to run [`ANALYZE\\
          TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") after major changes to index column data, as
statistics are not recalculated periodically (such as after a
server restart).


If [`innodb_stats_persistent`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_stats_persistent) is
enabled, you can change the number of random dives by
modifying the
[`innodb_stats_persistent_sample_pages`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_stats_persistent_sample_pages)
system variable. If
[`innodb_stats_persistent`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_stats_persistent) is
disabled, modify
[`innodb_stats_transient_sample_pages`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_stats_transient_sample_pages)
instead.


For more information about key distribution analysis in
`InnoDB`, see
[Section 17.8.10.1, “Configuring Persistent Optimizer Statistics Parameters”](https://dev.mysql.com/doc/refman/8.0/en/innodb-persistent-stats.html "17.8.10.1 Configuring Persistent Optimizer Statistics Parameters"), and
[Section 17.8.10.3, “Estimating ANALYZE TABLE Complexity for InnoDB Tables”](https://dev.mysql.com/doc/refman/8.0/en/innodb-analyze-table-complexity.html "17.8.10.3 Estimating ANALYZE TABLE Complexity for InnoDB Tables").


MySQL uses index cardinality estimates in join optimization.
If a join is not optimized in the right way, try running
[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement"). In the few cases
that [`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") does not
produce values good enough for your particular tables, you can
use `FORCE INDEX` with your queries to force
the use of a particular index, or set the
[`max_seeks_for_key`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_seeks_for_key) system
variable to ensure that MySQL prefers index lookups over table
scans. See [Section B.3.5, “Optimizer-Related Issues”](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html "B.3.5 Optimizer-Related Issues").

##### Histogram Statistics Analysis

[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") with the
`HISTOGRAM` clause enables management of
histogram statistics for table column values. For information
about histogram statistics, see
[Section 10.9.6, “Optimizer Statistics”](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html "10.9.6 Optimizer Statistics").


These histogram operations are available:

- [`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") with an
`UPDATE HISTOGRAM` clause generates
histogram statistics for the named table columns and
stores them in the data dictionary. Only one table name is
permitted for this syntax.



The optional `WITH N
                BUCKETS` clause specifies the number of buckets
for the histogram. The value of
_`N`_ must be an integer in the
range from 1 to 1024. If this clause is omitted, the
number of buckets is 100.


- [`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") with a
`DROP HISTOGRAM` clause removes histogram
statistics for the named table columns from the data
dictionary. Only one table name is permitted for this
syntax.


Stored histogram management statements affect only the named
columns. Consider these statements:


``` sql

ANALYZE TABLE t UPDATE HISTOGRAM ON c1, c2, c3 WITH 10 BUCKETS;
ANALYZE TABLE t UPDATE HISTOGRAM ON c1, c3 WITH 10 BUCKETS;
ANALYZE TABLE t DROP HISTOGRAM ON c2;
```

The first statement updates the histograms for columns
`c1`, `c2`, and
`c3`, replacing any existing histograms for
those columns. The second statement updates the histograms for
`c1` and `c3`, leaving the
`c2` histogram unaffected. The third
statement removes the histogram for `c2`,
leaving those for `c1` and
`c3` unaffected.


When sampling user data as part of building a histogram, not
all values are read; this may lead to missing some values
considered important. In such cases, it might be useful to
modify the histogram, or to set your own histogram explicitly
based on your own criteria, such as the complete data set.
MySQL 8.0.31 adds support for `ANALYZE TABLE
          tbl_name UPDATE HISTOGRAM ON
          col_name USING DATA
          'json_data'` for updating
a column of the histogram table with data supplied in the same
JSON format used to display `HISTOGRAM`
column values from the Information Schema
[`COLUMN_STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-column-statistics-table.html "28.3.11 The INFORMATION_SCHEMA COLUMN_STATISTICS Table") table. Only one
column can be modified when updating the histogram with JSON
data.


We can illustrate the use of `USING DATA` by
first generating a histogram on column `c1`
of table `t`, like this:


``` sql

mysql> ANALYZE TABLE t UPDATE HISTOGRAM ON c1;
+--------+-----------+----------+-----------------------------------------------+
| Table  | Op        | Msg_type | Msg_text                                      |
+--------+-----------+----------+-----------------------------------------------+
| mydb.t | histogram | status   | Histogram statistics created for column 'c1'. |
+--------+-----------+----------+-----------------------------------------------+
```

We can see the histogram generated in the
`COLUMN_STATISTICS` table:


``` sql

mysql> TABLE information_schema.column_statistics\G
*************************** 1. row ***************************
SCHEMA_NAME: mydb
 TABLE_NAME: t
COLUMN_NAME: c1
  HISTOGRAM: {"buckets": [[206, 0.0625], [456, 0.125], [608, 0.1875]],
"data-type": "int", "null-values": 0.0, "collation-id": 8, "last-updated":
"2022-10-11 16:13:14.563319", "sampling-rate": 1.0, "histogram-type":
"singleton", "number-of-buckets-specified": 100}
```

Now we drop the histogram, and when we check
`COLUMN_STATISTICS`, it is now empty:


``` sql

mysql> ANALYZE TABLE t DROP HISTOGRAM ON c1;
+--------+-----------+----------+-----------------------------------------------+
| Table  | Op        | Msg_type | Msg_text                                      |
+--------+-----------+----------+-----------------------------------------------+
| mydb.t | histogram | status   | Histogram statistics removed for column 'c1'. |
+--------+-----------+----------+-----------------------------------------------+

mysql> TABLE information_schema.column_statistics\G
Empty set (0.00 sec)
```

We can restore the dropped histogram by inserting its JSON
representation obtained previously from the
`HISTOGRAM` column of the
`COLUMN_STATISTICS` table, and when we query
that table again, we can see that the histogram has been
restored to its previous state:


``` sql

mysql> ANALYZE TABLE t UPDATE HISTOGRAM ON c1
    ->     USING DATA '{"buckets": [[206, 0.0625], [456, 0.125], [608, 0.1875]],
    ->               "data-type": "int", "null-values": 0.0, "collation-id":
    ->               8, "last-updated": "2022-10-11 16:13:14.563319",
    ->               "sampling-rate": 1.0, "histogram-type": "singleton",
    ->               "number-of-buckets-specified": 100}';
+--------+-----------+----------+-----------------------------------------------+
| Table  | Op        | Msg_type | Msg_text                                      |
+--------+-----------+----------+-----------------------------------------------+
| mydb.t | histogram | status   | Histogram statistics created for column 'c1'. |
+--------+-----------+----------+-----------------------------------------------+

mysql> TABLE information_schema.column_statistics\G
*************************** 1. row ***************************
SCHEMA_NAME: mydb
 TABLE_NAME: t
COLUMN_NAME: c1
  HISTOGRAM: {"buckets": [[206, 0.0625], [456, 0.125], [608, 0.1875]],
"data-type": "int", "null-values": 0.0, "collation-id": 8, "last-updated":
"2022-10-11 16:13:14.563319", "sampling-rate": 1.0, "histogram-type":
"singleton", "number-of-buckets-specified": 100}
```

Histogram generation is not supported for encrypted tables (to
avoid exposing data in the statistics) or
`TEMPORARY` tables.


Histogram generation applies to columns of all data types
except geometry types (spatial data) and
[`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type").


Histograms can be generated for stored and virtual generated
columns.


Histograms cannot be generated for columns that are covered by
single-column unique indexes.


Histogram management statements attempt to perform as much of
the requested operation as possible, and report diagnostic
messages for the remainder. For example, if an `UPDATE
          HISTOGRAM` statement names multiple columns, but some
of them do not exist or have an unsupported data type,
histograms are generated for the other columns, and messages
are produced for the invalid columns.


Histograms are affected by these DDL statements:

- [`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") removes
histograms for columns in the dropped table.


- [`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement") removes
histograms for any table in the dropped database because
the statement drops all tables in the database.


- [`RENAME TABLE`](https://dev.mysql.com/doc/refman/8.0/en/rename-table.html "15.1.36 RENAME TABLE Statement") does not
remove histograms. Instead, it renames histograms for the
renamed table to be associated with the new table name.


- [`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") statements that
remove or modify a column remove histograms for that
column.


- [`ALTER TABLE\\
                ... CONVERT TO CHARACTER SET`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") removes histograms
for character columns because they are affected by the
change of character set. Histograms for noncharacter
columns remain unaffected.


The
[`histogram_generation_max_mem_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_histogram_generation_max_mem_size)
system variable controls the maximum amount of memory
available for histogram generation. The global and session
values may be set at runtime.


Changing the global
[`histogram_generation_max_mem_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_histogram_generation_max_mem_size)
value requires privileges sufficient to set global system
variables. Changing the session
[`histogram_generation_max_mem_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_histogram_generation_max_mem_size)
value requires privileges sufficient to set restricted session
system variables. See
[Section 7.1.9.1, “System Variable Privileges”](https://dev.mysql.com/doc/refman/8.0/en/system-variable-privileges.html "7.1.9.1 System Variable Privileges").


If the estimated amount of data to be read into memory for
histogram generation exceeds the limit defined by
[`histogram_generation_max_mem_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_histogram_generation_max_mem_size),
MySQL samples the data rather than reading all of it into
memory. Sampling is evenly distributed over the entire table.
MySQL uses `SYSTEM` sampling, which is a
page-level sampling method.


The `sampling-rate` value in the
`HISTOGRAM` column of the Information Schema
[`COLUMN_STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-column-statistics-table.html "28.3.11 The INFORMATION_SCHEMA COLUMN_STATISTICS Table") table can be
queried to determine the fraction of data that was sampled to
create the histogram. The `sampling-rate` is
a number between 0.0 and 1.0. A value of 1 means that all of
the data was read (no sampling).


The following example demonstrates sampling. To ensure that
the amount of data exceeds the
[`histogram_generation_max_mem_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_histogram_generation_max_mem_size)
limit for the purpose of the example, the limit is set to a
low value (2000000 bytes) prior to generating histogram
statistics for the `birth_date` column of the
`employees` table.


``` sql

mysql> SET histogram_generation_max_mem_size = 2000000;

mysql> USE employees;

mysql> ANALYZE TABLE employees UPDATE HISTOGRAM ON birth_date WITH 16 BUCKETS\G
*************************** 1. row ***************************
   Table: employees.employees
      Op: histogram
Msg_type: status
Msg_text: Histogram statistics created for column 'birth_date'.

mysql> SELECT HISTOGRAM->>'$."sampling-rate"'
       FROM INFORMATION_SCHEMA.COLUMN_STATISTICS
       WHERE TABLE_NAME = "employees"
       AND COLUMN_NAME = "birth_date";
+---------------------------------+
| HISTOGRAM->>'$."sampling-rate"' |
+---------------------------------+
| 0.0491431208869665              |
+---------------------------------+
```

A `sampling-rate` value of 0.0491431208869665
means that approximately 4.9% of the data from the
`birth_date` column was read into memory for
generating histogram statistics.


As of MySQL 8.0.19, the `InnoDB` storage
engine provides its own sampling implementation for data
stored in `InnoDB` tables. The default
sampling implementation used by MySQL when storage engines do
not provide their own requires a full table scan, which is
costly for large tables. The `InnoDB`
sampling implementation improves sampling performance by
avoiding full table scans.


The `sampled_pages_read` and
`sampled_pages_skipped` [`INNODB_METRICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-metrics-table.html "28.4.21 The INFORMATION_SCHEMA INNODB_METRICS Table") counters can be
used to monitor sampling of `InnoDB` data
pages. (For general
[`INNODB_METRICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-metrics-table.html "28.4.21 The INFORMATION_SCHEMA INNODB_METRICS Table") counter usage
information, see
[Section 28.4.21, “The INFORMATION\_SCHEMA INNODB\_METRICS Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-metrics-table.html "28.4.21 The INFORMATION_SCHEMA INNODB_METRICS Table").)


The following example demonstrates sampling counter usage,
which requires enabling the counters prior to generating
histogram statistics.


``` sql

mysql> SET GLOBAL innodb_monitor_enable = 'sampled%';

mysql> USE employees;

mysql> ANALYZE TABLE employees UPDATE HISTOGRAM ON birth_date WITH 16 BUCKETS\G
*************************** 1. row ***************************
   Table: employees.employees
      Op: histogram
Msg_type: status
Msg_text: Histogram statistics created for column 'birth_date'.

mysql> USE INFORMATION_SCHEMA;

mysql> SELECT NAME, COUNT FROM INNODB_METRICS WHERE NAME LIKE 'sampled%'\G
*************************** 1. row ***************************
 NAME: sampled_pages_read
COUNT: 43
*************************** 2. row ***************************
 NAME: sampled_pages_skipped
COUNT: 843
```

This formula approximates a sampling rate based on the
sampling counter data:


``` none

sampling rate = sampled_page_read/(sampled_pages_read + sampled_pages_skipped)
```

A sampling rate based on sampling counter data is roughly the
same as the `sampling-rate` value in the
`HISTOGRAM` column of the Information Schema
[`COLUMN_STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-column-statistics-table.html "28.3.11 The INFORMATION_SCHEMA COLUMN_STATISTICS Table") table.


For information about memory allocations performed for
histogram generation, monitor the Performance Schema
`memory/sql/histograms` instrument. See
[Section 29.12.20.10, “Memory Summary Tables”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-memory-summary-tables.html "29.12.20.10 Memory Summary Tables").

##### Other Considerations

`ANALYZE TABLE` clears table statistics from
the Information Schema
[`INNODB_TABLESTATS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-tablestats-table.html "28.4.26 The INFORMATION_SCHEMA INNODB_TABLESTATS View") table and sets
the `STATS_INITIALIZED` column to
`Uninitialized`. Statistics are collected
again the next time the table is accessed.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html "Previous: Table Maintenance Statements") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html "Up: Table Maintenance Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "Next: CHECK TABLE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html)

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