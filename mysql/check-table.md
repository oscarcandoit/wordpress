---
url: https://dev.mysql.com/doc/refman/8.0/en/check-table.html
scraped_at: 2025-10-20T03:14:44.954Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/check-table.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "Hide Sidebar")

[Previous: ANALYZE TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "Previous: ANALYZE TABLE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Table Maintenance Statements](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html "Up: Table Maintenance Statements")[Next: CHECKSUM TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/checksum-table.html "Next: CHECKSUM TABLE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/check-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/check-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/check-table.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/check-table.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/check-table.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/check-table.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/check-table.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/check-table.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/check-table.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/check-table.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/check-table.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/check-table.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/check-table.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[Table Maintenance Statements](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html)  /

CHECK TABLE Statement


#### 15.7.3.2 CHECK TABLE Statement

``` sql

CHECK TABLE tbl_name [, tbl_name] ... [option] ...

option: {
    FOR UPGRADE
  | QUICK
  | FAST
  | MEDIUM
  | EXTENDED
  | CHANGED
}
```

[`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") checks a table or
tables for errors. [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement")
can also check views for problems, such as tables that are
referenced in the view definition that no longer exist.


To check a table, you must have some privilege for it.


[`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") works for
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine"),
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine"),
[`ARCHIVE`](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html "18.5 The ARCHIVE Storage Engine"), and
[`CSV`](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html "18.4 The CSV Storage Engine") tables.


Before running [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") on
`InnoDB` tables, see
[CHECK TABLE Usage Notes for InnoDB Tables](https://dev.mysql.com/doc/refman/8.0/en/check-table.html#check-table-innodb "CHECK TABLE Usage Notes for InnoDB Tables").


[`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") is supported for
partitioned tables, and you can use `ALTER TABLE ...
        CHECK PARTITION` to check one or more partitions; for
more information, see [Section 15.1.9, “ALTER TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement"), and
[Section 26.3.4, “Maintenance of Partitions”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-maintenance.html "26.3.4 Maintenance of Partitions").


[`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") ignores virtual
generated columns that are not indexed.

- [CHECK TABLE Output](https://dev.mysql.com/doc/refman/8.0/en/check-table.html#check-table-output "CHECK TABLE Output")

- [Checking Version Compatibility](https://dev.mysql.com/doc/refman/8.0/en/check-table.html#check-table-version-compatibility "Checking Version Compatibility")

- [Checking Data Consistency](https://dev.mysql.com/doc/refman/8.0/en/check-table.html#check-table-data-consistency "Checking Data Consistency")

- [CHECK TABLE Usage Notes for InnoDB Tables](https://dev.mysql.com/doc/refman/8.0/en/check-table.html#check-table-innodb "CHECK TABLE Usage Notes for InnoDB Tables")

- [CHECK TABLE Usage Notes for MyISAM Tables](https://dev.mysql.com/doc/refman/8.0/en/check-table.html#check-table-myisam "CHECK TABLE Usage Notes for MyISAM Tables")


##### CHECK TABLE Output

[`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") returns a result
set with the columns shown in the following table.

| Column | Value |
| --- | --- |
| `Table` | The table name |
| `Op` | Always `check` |
| `Msg_type` | `status`, `error`,<br> `info`, `note`, or<br> `warning` |
| `Msg_text` | An informational message |

The statement might produce many rows of information for each
checked table. The last row has a `Msg_type`
value of `status` and the
`Msg_text` normally should be
`OK`. `Table is already up to
          date` means that the storage engine for the table
indicated that there was no need to check the table.

##### Checking Version Compatibility

The `FOR UPGRADE` option checks whether the
named tables are compatible with the current version of MySQL.
With `FOR UPGRADE`, the server checks each
table to determine whether there have been any incompatible
changes in any of the table's data types or indexes since the
table was created. If not, the check succeeds. Otherwise, if
there is a possible incompatibility, the server runs a full
check on the table (which might take some time).


Incompatibilities might occur because the storage format for a
data type has changed or because its sort order has changed.
Our aim is to avoid these changes, but occasionally they are
necessary to correct problems that would be worse than an
incompatibility between releases.


`FOR UPGRADE` discovers these
incompatibilities:

- The indexing order for end-space in
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns for
`InnoDB` and `MyISAM`
tables changed between MySQL 4.1 and 5.0.


- The storage method of the new
[`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC") data type changed
between MySQL 5.0.3 and 5.0.5.


- Changes are sometimes made to character sets or collations
that require table indexes to be rebuilt. For details
about such changes, see
[Section 3.5, “Changes in MySQL 8.0”](https://dev.mysql.com/doc/refman/8.0/en/upgrading-from-previous-series.html "3.5 Changes in MySQL 8.0"). For
information about rebuilding tables, see
[Section 3.14, “Rebuilding or Repairing Tables or Indexes”](https://dev.mysql.com/doc/refman/8.0/en/rebuilding-tables.html "3.14 Rebuilding or Repairing Tables or Indexes").


- MySQL 8.0 does not support the 2-digit
[`YEAR(2)`](https://dev.mysql.com/doc/refman/8.0/en/year.html "13.2.4 The YEAR Type") data type permitted
in older versions of MySQL. For tables containing
[`YEAR(2)`](https://dev.mysql.com/doc/refman/8.0/en/year.html "13.2.4 The YEAR Type") columns,
[`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") recommends
[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement"), which
converts 2-digit [`YEAR(2)`](https://dev.mysql.com/doc/refman/8.0/en/year.html "13.2.4 The YEAR Type")
columns to 4-digit [`YEAR`](https://dev.mysql.com/doc/refman/8.0/en/year.html "13.2.4 The YEAR Type")
columns.


- Trigger creation time is maintained.


- A table is reported as needing a rebuild if it contains
old temporal columns in pre-5.6.4 format
( [`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type"),
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"), and
[`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") columns without
support for fractional seconds precision) and the
[`avoid_temporal_upgrade`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_avoid_temporal_upgrade)
system variable is disabled. This helps the MySQL upgrade
procedure detect and upgrade tables containing old
temporal columns. If
[`avoid_temporal_upgrade`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_avoid_temporal_upgrade) is
enabled, `FOR UPGRADE` ignores the old
temporal columns present in the table; consequently, the
upgrade procedure does not upgrade them.



To check for tables that contain such temporal columns and
need a rebuild, disable
[`avoid_temporal_upgrade`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_avoid_temporal_upgrade)
before executing
[`CHECK TABLE\\
                ... FOR UPGRADE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement").


- Warnings are issued for tables that use nonnative
partitioning because nonnative partitioning is removed in
MySQL 8.0. See
[Chapter 26, _Partitioning_](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html "Chapter 26 Partitioning").


##### Checking Data Consistency

The following table shows the other check options that can be
given. These options are passed to the storage engine, which
may use or ignore them.

| Type | Meaning |
| --- | --- |
| `QUICK` | Do not scan the rows to check for incorrect links. Applies to<br> `InnoDB` and `MyISAM`<br> tables and views. |
| `FAST` | Check only tables that have not been closed properly. Ignored for<br> `InnoDB`; applies only to<br> `MyISAM` tables and views. |
| `CHANGED` | Check only tables that have been changed since the last check or that<br> have not been closed properly. Ignored for<br> `InnoDB`; applies only to<br> `MyISAM` tables and views. |
| `MEDIUM` | Scan rows to verify that deleted links are valid. This also calculates a<br> key checksum for the rows and verifies this with a<br> calculated checksum for the keys. Ignored for<br> `InnoDB`; applies only to<br> `MyISAM` tables and views. |
| `EXTENDED` | Do a full key lookup for all keys for each row. This ensures that the<br> table is 100% consistent, but takes a long time. Ignored<br> for `InnoDB`; applies only to<br> `MyISAM` tables and views. |

You can combine check options, as in the following example
that does a quick check on the table to determine whether it
was closed properly:


``` sql

CHECK TABLE test_table FAST QUICK;
```

Note

If [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") finds no
problems with a table that is marked as
“corrupted” or “not closed
properly”, [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement")
may remove the mark.

If a table is corrupted, the problem is most likely in the
indexes and not in the data part. All of the preceding check
types check the indexes thoroughly and should thus find most
errors.


To check a table that you assume is okay, use no check options
or the `QUICK` option. The latter should be
used when you are in a hurry and can take the very small risk
that `QUICK` does not find an error in the
data file. (In most cases, under normal usage, MySQL should
find any error in the data file. If this happens, the table is
marked as “corrupted” and cannot be used until it
is repaired.)


`FAST` and `CHANGED` are
mostly intended to be used from a script (for example, to be
executed from **cron**) to check tables
periodically. In most cases, `FAST` is to be
preferred over `CHANGED`. (The only case when
it is not preferred is when you suspect that you have found a
bug in the `MyISAM` code.)


`EXTENDED` is to be used only after you have
run a normal check but still get errors from a table when
MySQL tries to update a row or find a row by key. This is very
unlikely if a normal check has succeeded.


Use of [`CHECK\\
          TABLE ... EXTENDED`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") might influence execution plans
generated by the query optimizer.


Some problems reported by [`CHECK\\
          TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") cannot be corrected automatically:

- `Found row where the auto_increment column has the
                value 0`.



This means that you have a row in the table where the
`AUTO_INCREMENT` index column contains
the value 0. (It is possible to create a row where the
`AUTO_INCREMENT` column is 0 by
explicitly setting the column to 0 with an
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement.)



This is not an error in itself, but could cause trouble if
you decide to dump the table and restore it or do an
[`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") on the table.
In this case, the `AUTO_INCREMENT` column
changes value according to the rules of
`AUTO_INCREMENT` columns, which could
cause problems such as a duplicate-key error.



To get rid of the warning, execute an
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement to set the
column to some value other than 0.


##### CHECK TABLE Usage Notes for InnoDB Tables

The following notes apply to
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") tables:

- If [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") encounters a
corrupt page, the server exits to prevent error
propagation (Bug #10132). If the corruption occurs in a
secondary index but table data is readable, running
[`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") can still cause
a server exit.


- If [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") encounters a
corrupted `DB_TRX_ID` or
`DB_ROLL_PTR` field in a clustered index,
[`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") can cause
`InnoDB` to access an invalid undo log
record, resulting in an
[MVCC](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_mvcc "MVCC")-related server exit.


- If [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") encounters
errors in `InnoDB` tables or indexes, it
reports an error, and usually marks the index and
sometimes marks the table as corrupted, preventing further
use of the index or table. Such errors include an
incorrect number of entries in a secondary index or
incorrect links.


- If [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") finds an
incorrect number of entries in a secondary index, it
reports an error but does not cause a server exit or
prevent access to the file.


- [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") surveys the
index page structure, then surveys each key entry. It does
not validate the key pointer to a clustered record or
follow the path for [`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types")
pointers.


- When an `InnoDB` table is stored in its
own
[`.ibd`\\
file](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_ibd_file ".ibd file"), the first 3
[pages](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_page "page") of the
`.ibd` file contain header information
rather than table or index data. The
[`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") statement does
not detect inconsistencies that affect only the header
data. To verify the entire contents of an
`InnoDB` `.ibd` file,
use the [**innochecksum**](https://dev.mysql.com/doc/refman/8.0/en/innochecksum.html "6.6.2 innochecksum — Offline InnoDB File Checksum Utility") command.


- When running [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") on
large `InnoDB` tables, other threads may
be blocked during [`CHECK\\
                TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") execution. To avoid timeouts, the
semaphore wait threshold (600 seconds) is extended by 2
hours (7200 seconds) for [`CHECK\\
                TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") operations. If `InnoDB`
detects semaphore waits of 240 seconds or more, it starts
printing `InnoDB` monitor output to the
error log. If a lock request extends beyond the semaphore
wait threshold, `InnoDB` aborts the
process. To avoid the possibility of a semaphore wait
timeout entirely, run
[`CHECK TABLE\\
                QUICK`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") instead of [`CHECK\\
                TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement").


- [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") functionality
for `InnoDB` `SPATIAL`
indexes includes an R-tree validity check and a check to
ensure that the R-tree row count matches the clustered
index.


- [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") supports
secondary indexes on virtual generated columns, which are
supported by `InnoDB`.


- As of MySQL 8.0.14, `InnoDB` supports
parallel clustered index reads, which can improve
[`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") performance.
`InnoDB` reads the clustered index twice
during a [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement")
operation. The second read can be performed in parallel.
The
[`innodb_parallel_read_threads`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_parallel_read_threads)
session variable must be set to a value greater than 1 for
parallel clustered index reads to occur. The default value
is 4. The actual number of threads used to perform a
parallel clustered index read is determined by the
[`innodb_parallel_read_threads`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_parallel_read_threads)
setting or the number of index subtrees to scan, whichever
is smaller.


##### CHECK TABLE Usage Notes for MyISAM Tables

The following notes apply to
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine") tables:

- [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") updates key
statistics for `MyISAM` tables.


- If [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") output does
not return `OK` or `Table is
                already up to date`, you should normally run a
repair of the table. See
[Section 9.6, “MyISAM Table Maintenance and Crash Recovery”](https://dev.mysql.com/doc/refman/8.0/en/myisam-table-maintenance.html "9.6 MyISAM Table Maintenance and Crash Recovery").


- If none of the [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement")
options `QUICK`,
`MEDIUM`, or `EXTENDED`
are specified, the default check type for dynamic-format
`MyISAM` tables is
`MEDIUM`. This has the same result as
running [**myisamchk --medium-check**\\
**_`tbl_name`_**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") on the
table. The default check type also is
`MEDIUM` for static-format
`MyISAM` tables, unless
`CHANGED` or `FAST` is
specified. In that case, the default is
`QUICK`. The row scan is skipped for
`CHANGED` and `FAST`
because the rows are very seldom corrupted.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "Previous: ANALYZE TABLE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html "Up: Table Maintenance Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/checksum-table.html "Next: CHECKSUM TABLE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/check-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/check-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/check-table.html)

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