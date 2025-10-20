---
url: https://dev.mysql.com/doc/refman/8.0/en/repair-table.html
scraped_at: 2025-10-20T03:14:49.100Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "Hide Sidebar")

[Previous: OPTIMIZE TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "Previous: OPTIMIZE TABLE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Table Maintenance Statements](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html "Up: Table Maintenance Statements")[Next: Component, Plugin, and Loadable Function Statements](https://dev.mysql.com/doc/refman/8.0/en/component-statements.html "Next: Component, Plugin, and Loadable Function Statements")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/repair-table.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/repair-table.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/repair-table.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/repair-table.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/repair-table.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/repair-table.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/repair-table.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/repair-table.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[Table Maintenance Statements](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html)  /

REPAIR TABLE Statement


#### 15.7.3.5 REPAIR TABLE Statement

```sql
REPAIR [NO_WRITE_TO_BINLOG | LOCAL]
    TABLE tbl_name [, tbl_name] ...
    [QUICK] [EXTENDED] [USE_FRM]
```

[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") repairs a possibly
corrupted table, for certain storage engines only.


This statement requires [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select)
and [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_insert) privileges for the
table.


Although normally you should never have to run
[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement"), if disaster
strikes, this statement is very likely to get back all your data
from a `MyISAM` table. If your tables become
corrupted often, try to find the reason for it, to eliminate the
need to use [`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement"). See
[Section B.3.3.3, “What to Do If MySQL Keeps Crashing”](https://dev.mysql.com/doc/refman/8.0/en/crashing.html "B.3.3.3 What to Do If MySQL Keeps Crashing"), and
[Section 18.2.4, “MyISAM Table Problems”](https://dev.mysql.com/doc/refman/8.0/en/myisam-table-problems.html "18.2.4 MyISAM Table Problems").


[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") checks the table to
see whether an upgrade is required. If so, it performs the
upgrade, following the same rules as
[`CHECK TABLE ... FOR\\
        UPGRADE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement"). See [Section 15.7.3.2, “CHECK TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement"), for more
information.

Important

- Make a backup of a table before performing a table repair
operation; under some circumstances the operation might
cause data loss. Possible causes include but are not
limited to file system errors. See
[Chapter 9, _Backup and Recovery_](https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html "Chapter 9 Backup and Recovery").


- If the server exits during a [`REPAIR\\
                TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") operation, it is essential after
restarting it that you immediately execute another
[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") statement for
the table before performing any other operations on it. In
the worst case, you might have a new clean index file
without information about the data file, and then the next
operation you perform could overwrite the data file. This
is an unlikely but possible scenario that underscores the
value of making a backup first.


- In the event that a table on the source becomes corrupted
and you run [`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") on
it, any resulting changes to the original table are
_not_ propagated to replicas.


- [REPAIR TABLE Storage Engine and Partitioning Support](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html#repair-table-support "REPAIR TABLE Storage Engine and Partitioning Support")

- [REPAIR TABLE Options](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html#repair-table-options "REPAIR TABLE Options")

- [REPAIR TABLE Output](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html#repair-table-output "REPAIR TABLE Output")

- [Table Repair Considerations](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html#repair-table-table-repair-considerations "Table Repair Considerations")


##### REPAIR TABLE Storage Engine and Partitioning Support

[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") works for
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine"),
[`ARCHIVE`](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html "18.5 The ARCHIVE Storage Engine"), and
[`CSV`](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html "18.4 The CSV Storage Engine") tables. For
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine") tables, it has the same
effect as [**myisamchk --recover**\\
**_`tbl_name`_**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") by default. This
statement does not work with views.


[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") is supported for
partitioned tables. However, the `USE_FRM`
option cannot be used with this statement on a partitioned
table.


You can use `ALTER TABLE ... REPAIR
          PARTITION` to repair one or more partitions; for more
information, see [Section 15.1.9, “ALTER TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement"), and
[Section 26.3.4, “Maintenance of Partitions”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-maintenance.html "26.3.4 Maintenance of Partitions").

##### REPAIR TABLE Options

- `NO_WRITE_TO_BINLOG` or
`LOCAL`


By default, the server writes [`REPAIR\\
                TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") statements to the binary log so that they
replicate to replicas. To suppress logging, specify the
optional `NO_WRITE_TO_BINLOG` keyword or
its alias `LOCAL`.


- `QUICK`


If you use the `QUICK` option,
[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") tries to
repair only the index file, and not the data file. This
type of repair is like that done by [**myisamchk**\\
**--recover --quick**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility").


- `EXTENDED`


If you use the `EXTENDED` option, MySQL
creates the index row by row instead of creating one index
at a time with sorting. This type of repair is like that
done by [**myisamchk --safe-recover**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility").


- `USE_FRM`


The `USE_FRM` option is available for use
if the `.MYI` index file is missing or
if its header is corrupted. This option tells MySQL not to
trust the information in the `.MYI`
file header and to re-create it using information from the
data dictionary. This kind of repair cannot be done with
[**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility").





Caution





Use the `USE_FRM` option
_only_ if you cannot use regular
`REPAIR` modes. Telling the server to
ignore the `.MYI` file makes
important table metadata stored in the
`.MYI` unavailable to the repair
process, which can have deleterious consequences:






- The current `AUTO_INCREMENT` value
is lost.


- The link to deleted records in the table is lost,
which means that free space for deleted records
remains unoccupied thereafter.


- The `.MYI` header indicates
whether the table is compressed. If the server
ignores this information, it cannot tell that a
table is compressed and repair can cause change or
loss of table contents. This means that
`USE_FRM` should not be used with
compressed tables. That should not be necessary,
anyway: Compressed tables are read only, so they
should not become corrupt.


If you use `USE_FRM` for a table that
was created by a different version of the MySQL server
than the one you are currently running,
[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") does not
attempt to repair the table. In this case, the result
set returned by [`REPAIR\\
                TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") contains a line with a
`Msg_type` value of
`error` and a
`Msg_text` value of `Failed
                repairing incompatible .FRM file`.


If `USE_FRM` is used,
[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") does not
check the table to see whether an upgrade is required.

##### REPAIR TABLE Output

[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") returns a result
set with the columns shown in the following table.

| Column | Value |
| --- | --- |
| `Table` | The table name |
| `Op` | Always `repair` |
| `Msg_type` | `status`, `error`,<br> `info`, `note`, or<br> `warning` |
| `Msg_text` | An informational message |

The [`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") statement
might produce many rows of information for each repaired
table. The last row has a `Msg_type` value of
`status` and `Msg_test`
normally should be `OK`. For a
`MyISAM` table, if you do not get
`OK`, you should try repairing it with
[**myisamchk --safe-recover**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility").
( [`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") does not
implement all the options of [**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility").
With [**myisamchk --safe-recover**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility"), you can also
use options that [`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement")
does not support, such as
[`--max-record-length`](https://dev.mysql.com/doc/refman/8.0/en/myisamchk-repair-options.html#option_myisamchk_max-record-length).)


[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") table catches and
throws any errors that occur while copying table statistics
from the old corrupted file to the newly created file. For
example. if the user ID of the owner of the
`.MYD` or `.MYI` file is
different from the user ID of the [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server")
process, [`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") generates
a "cannot change ownership of the file" error unless
[**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server") is started by the
`root` user.

##### Table Repair Considerations

[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") upgrades a table
if it contains old temporal columns in pre-5.6.4 format
( [`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type"),
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"), and
[`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") columns without
support for fractional seconds precision) and the
[`avoid_temporal_upgrade`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_avoid_temporal_upgrade) system
variable is disabled. If
[`avoid_temporal_upgrade`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_avoid_temporal_upgrade) is
enabled, [`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") ignores
the old temporal columns present in the table and does not
upgrade them.


To upgrade tables that contain such temporal columns, disable
[`avoid_temporal_upgrade`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_avoid_temporal_upgrade) before
executing [`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement").


You may be able to increase [`REPAIR\\
          TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement") performance by setting certain system
variables. See [Section 10.6.3, “Optimizing REPAIR TABLE Statements”](https://dev.mysql.com/doc/refman/8.0/en/repair-table-optimization.html "10.6.3 Optimizing REPAIR TABLE Statements").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "Previous: OPTIMIZE TABLE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/table-maintenance-statements.html "Up: Table Maintenance Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/component-statements.html "Next: Component, Plugin, and Loadable Function Statements")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html)

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