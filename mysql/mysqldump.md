---
url: https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html
scraped_at: 2025-10-20T03:03:29.660Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "Hide Sidebar")

[Previous: mysqlcheck — A Table Maintenance Program](https://dev.mysql.com/doc/refman/8.0/en/mysqlcheck.html "Previous: mysqlcheck — A Table Maintenance Program")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Client Programs](https://dev.mysql.com/doc/refman/8.0/en/programs-client.html "Up: Client Programs")[Next: mysqlimport — A Data Import Program](https://dev.mysql.com/doc/refman/8.0/en/mysqlimport.html "Next: mysqlimport — A Data Import Program")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/mysqldump.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/mysqldump.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/mysqldump.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/mysqldump.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/mysqldump.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/mysqldump.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/mysqldump.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/mysqldump.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html)  / [MySQL Programs](https://dev.mysql.com/doc/refman/8.0/en/programs.html)  /
[Client Programs](https://dev.mysql.com/doc/refman/8.0/en/programs-client.html)  /

mysqldump — A Database Backup Program


### 6.5.4 mysqldump — A Database Backup Program

The [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") client utility performs
[logical backups](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_logical_backup "logical backup"),
producing a set of SQL statements that can be executed to
reproduce the original database object definitions and table
data. It dumps one or more MySQL databases for backup or
transfer to another SQL server. The [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program")
command can also generate output in CSV, other delimited text,
or XML format.

Tip

Consider using the [MySQL Shell dump utilities](https://dev.mysql.com/doc/mysql-shell/8.0/en/mysql-shell-utilities-dump-instance-schema.html), which provide parallel dumping with multiple threads, file compression, and progress information display, as well as cloud features such as Oracle Cloud Infrastructure Object Storage streaming, and MySQL HeatWave compatibility checks and modifications. Dumps can be easily imported into a MySQL Server instance or a MySQL HeatWave DB System using the [MySQL Shell load dump utilities](https://dev.mysql.com/doc/mysql-shell/8.0/en/mysql-shell-utilities-load-dump.html). Installation instructions for MySQL Shell can be found [here](https://dev.mysql.com/doc/mysql-shell/8.0/en/mysql-shell-install.html).

- [Performance and Scalability Considerations](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-performance "Performance and Scalability Considerations")

- [Invocation Syntax](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-syntax "Invocation Syntax")

- [Option Syntax - Alphabetical Summary](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-option-summary "Option Syntax - Alphabetical Summary")

- [Connection Options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-connection-options "Connection Options")

- [Option-File Options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-option-file-options "Option-File Options")

- [DDL Options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-ddl-options "DDL Options")

- [Debug Options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-debug-options "Debug Options")

- [Help Options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-help-options "Help Options")

- [Internationalization Options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-i18n-options "Internationalization Options")

- [Replication Options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-replication-options "Replication Options")

- [Format Options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-format-options "Format Options")

- [Filtering Options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-filter-options "Filtering Options")

- [Performance Options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-performance-options "Performance Options")

- [Transactional Options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-transaction-options "Transactional Options")

- [Option Groups](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-option-groups "Option Groups")

- [Examples](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-option-examples "Examples")

- [Restrictions](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-restrictions "Restrictions")


[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") requires at least the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege for dumped
tables, [`SHOW VIEW`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_show-view) for dumped
views, [`TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_trigger) for dumped
triggers, [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_lock-tables) if the
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction) option is
not used, [`PROCESS`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_process) (as of MySQL
8.0.21) if the
`--no-tablespaces` option is
not used, and (as of MySQL 8.0.32) the
[`RELOAD`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_reload) or
[`FLUSH_TABLES`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_flush-tables) privilege with
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction) if both
[`gtid_mode=ON`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_mode) and
[`gtid_purged=ON|AUTO`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_purged). Certain
options might require other privileges as noted in the option
descriptions.


To reload a dump file, you must have the privileges required to
execute the statements that it contains, such as the appropriate
`CREATE` privileges for objects created by
those statements.


[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") output can include
[`ALTER DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/alter-database.html "15.1.2 ALTER DATABASE Statement") statements that
change the database collation. These may be used when dumping
stored programs to preserve their character encodings. To reload
a dump file containing such statements, the
`ALTER` privilege for the affected database is
required.

Note

A dump made using PowerShell on Windows with output
redirection creates a file that has UTF-16 encoding:


``` terminal

mysqldump [options] > dump.sql
```

However, UTF-16 is not permitted as a connection character set
(see
[Impermissible Client Character Sets](https://dev.mysql.com/doc/refman/8.0/en/charset-connection.html#charset-connection-impermissible-client-charset "Impermissible Client Character Sets")),
so the dump file cannot be loaded correctly. To work around
this issue, use the `--result-file` option,
which creates the output in ASCII format:


``` terminal

mysqldump [options] --result-file=dump.sql
```

It is not recommended to load a dump file when GTIDs are enabled
on the server ( [`gtid_mode=ON`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_mode)),
if your dump file includes system tables.
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") issues DML instructions for the
system tables which use the non-transactional MyISAM storage
engine, and this combination is not permitted when GTIDs are
enabled.

#### Performance and Scalability Considerations

`mysqldump` advantages include the convenience
and flexibility of viewing or even editing the output before
restoring. You can clone databases for development and DBA work,
or produce slight variations of an existing database for
testing. It is not intended as a fast or scalable solution for
backing up substantial amounts of data. With large data sizes,
even if the backup step takes a reasonable time, restoring the
data can be very slow because replaying the SQL statements
involves disk I/O for insertion, index creation, and so on.


For large-scale backup and restore, a
[physical](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_physical "physical") backup is more
appropriate, to copy the data files in their original format so
that they can be restored quickly.


If your tables are primarily [`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine")
tables, or if you have a mix of `InnoDB` and
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine") tables, consider using
**mysqlbackup**, which is available as part of
MySQL Enterprise. This tool provides high performance for
`InnoDB` backups with minimal disruption; it
can also back up tables from `MyISAM` and other
storage engines; it also provides a number of convenient options
to accommodate different backup scenarios. See
[Section 32.1, “MySQL Enterprise Backup Overview”](https://dev.mysql.com/doc/refman/8.0/en/mysql-enterprise-backup.html "32.1 MySQL Enterprise Backup Overview").


[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") can retrieve and dump table
contents row by row, or it can retrieve the entire content from
a table and buffer it in memory before dumping it. Buffering in
memory can be a problem if you are dumping large tables. To dump
tables row by row, use the
[`--quick`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quick) option (or
[`--opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt), which enables
[`--quick`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quick)). The
[`--opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt) option (and hence
[`--quick`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quick)) is enabled by
default, so to enable memory buffering, use
[`--skip-quick`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quick).


If you are using a recent version of
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") to generate a dump to be reloaded
into a very old MySQL server, use the
[`--skip-opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-opt) option instead of
the [`--opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt) or
[`--extended-insert`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_extended-insert) option.


For additional information about [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program"),
see [Section 9.4, “Using mysqldump for Backups”](https://dev.mysql.com/doc/refman/8.0/en/using-mysqldump.html "9.4 Using mysqldump for Backups").

#### Invocation Syntax

There are in general three ways to use
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program")—in order to dump a set of one
or more tables, a set of one or more complete databases, or an
entire MySQL server—as shown here:


``` terminal

mysqldump [options] db_name [tbl_name ...]
mysqldump [options] --databases db_name ...
mysqldump [options] --all-databases
```

To dump entire databases, do not name any tables following
_`db_name`_, or use the
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_databases) or
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-databases) option.


To see a list of the options your version of
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") supports, issue the command
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") [`--help`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_help).

#### Option Syntax - Alphabetical Summary

[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") supports the following options,
which can be specified on the command line or in the
`[mysqldump]` and `[client]`
groups of an option file. For information about option files
used by MySQL programs, see [Section 6.2.2.2, “Using Option Files”](https://dev.mysql.com/doc/refman/8.0/en/option-files.html "6.2.2.2 Using Option Files").

**Table 6.15 mysqldump Options**

| Option Name | Description | Introduced | Deprecated |
| --- | --- | --- | --- |
| [--add-drop-database](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-database) | Add DROP DATABASE statement before each CREATE DATABASE statement |  |  |
| [--add-drop-table](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-table) | Add DROP TABLE statement before each CREATE TABLE statement |  |  |
| [--add-drop-trigger](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-trigger) | Add DROP TRIGGER statement before each CREATE TRIGGER statement |  |  |
| [--add-locks](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-locks) | Surround each table dump with LOCK TABLES and UNLOCK TABLES statements |  |  |
| [--all-databases](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-databases) | Dump all tables in all databases |  |  |
| [--allow-keywords](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_allow-keywords) | Allow creation of column names that are keywords |  |  |
| [--apply-replica-statements](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_apply-replica-statements) | Include STOP REPLICA prior to CHANGE REPLICATION SOURCE TO statement and START REPLICA at end of output | 8.0.26 |  |
| [--apply-slave-statements](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_apply-slave-statements) | Include STOP SLAVE prior to CHANGE MASTER statement and START SLAVE at end of output |  | 8.0.26 |
| [--bind-address](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_bind-address) | Use specified network interface to connect to MySQL Server |  |  |
| [--character-sets-dir](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_character-sets-dir) | Directory where character sets are installed |  |  |
| [--column-statistics](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_column-statistics) | Write ANALYZE TABLE statements to generate statistics histograms |  |  |
| [--comments](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_comments) | Add comments to dump file |  |  |
| [--compact](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_compact) | Produce more compact output |  |  |
| [--compatible](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_compatible) | Produce output that is more compatible with other database systems or with older MySQL servers |  |  |
| [--complete-insert](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_complete-insert) | Use complete INSERT statements that include column names |  |  |
| [--compress](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_compress) | Compress all information sent between client and server |  | 8.0.18 |
| [--compression-algorithms](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_compression-algorithms) | Permitted compression algorithms for connections to server | 8.0.18 |  |
| [--create-options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_create-options) | Include all MySQL-specific table options in CREATE TABLE statements |  |  |
| [--databases](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_databases) | Interpret all name arguments as database names |  |  |
| [--debug](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_debug) | Write debugging log |  |  |
| [--debug-check](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_debug-check) | Print debugging information when program exits |  |  |
| [--debug-info](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_debug-info) | Print debugging information, memory, and CPU statistics when program exits |  |  |
| [--default-auth](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_default-auth) | Authentication plugin to use |  |  |
| [--default-character-set](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_default-character-set) | Specify default character set |  |  |
| [--defaults-extra-file](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_defaults-extra-file) | Read named option file in addition to usual option files |  |  |
| [--defaults-file](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_defaults-file) | Read only named option file |  |  |
| [--defaults-group-suffix](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_defaults-group-suffix) | Option group suffix value |  |  |
| [--delete-master-logs](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_delete-master-logs) | On a replication source server, delete the binary logs after performing the dump operation |  | 8.0.26 |
| [--delete-source-logs](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_delete-source-logs) | On a replication source server, delete the binary logs after performing the dump operation | 8.0.26 |  |
| [--disable-keys](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_disable-keys) | For each table, surround INSERT statements with statements to disable and enable keys |  |  |
| [--dump-date](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-date) | Include dump date as "Dump completed on" comment if --comments is given |  |  |
| [--dump-replica](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-replica) | Include CHANGE REPLICATION SOURCE TO statement that lists binary log coordinates of replica's source | 8.0.26 |  |
| [--dump-slave](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-slave) | Include CHANGE MASTER statement that lists binary log coordinates of replica's source |  | 8.0.26 |
| [--enable-cleartext-plugin](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_enable-cleartext-plugin) | Enable cleartext authentication plugin |  |  |
| [--events](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_events) | Dump events from dumped databases |  |  |
| [--extended-insert](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_extended-insert) | Use multiple-row INSERT syntax |  |  |
| [--fields-enclosed-by](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_fields) | This option is used with the --tab option and has the same meaning as the corresponding clause for LOAD DATA |  |  |
| [--fields-escaped-by](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_fields) | This option is used with the --tab option and has the same meaning as the corresponding clause for LOAD DATA |  |  |
| [--fields-optionally-enclosed-by](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_fields) | This option is used with the --tab option and has the same meaning as the corresponding clause for LOAD DATA |  |  |
| [--fields-terminated-by](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_fields) | This option is used with the --tab option and has the same meaning as the corresponding clause for LOAD DATA |  |  |
| [--flush-logs](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_flush-logs) | Flush MySQL server log files before starting dump |  |  |
| [--flush-privileges](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_flush-privileges) | Emit a FLUSH PRIVILEGES statement after dumping mysql database |  |  |
| [--force](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_force) | Continue even if an SQL error occurs during a table dump |  |  |
| [--get-server-public-key](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_get-server-public-key) | Request RSA public key from server |  |  |
| [--help](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_help) | Display help message and exit |  |  |
| [--hex-blob](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_hex-blob) | Dump binary columns using hexadecimal notation |  |  |
| [--host](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_host) | Host on which MySQL server is located |  |  |
| [--ignore-error](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ignore-error) | Ignore specified errors |  |  |
| [--ignore-table](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ignore-table) | Do not dump given table |  |  |
| [--include-master-host-port](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_include-master-host-port) | Include MASTER\_HOST/MASTER\_PORT options in CHANGE MASTER statement produced with --dump-slave |  | 8.0.26 |
| [--include-source-host-port](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_include-source-host-port) | Include SOURCE\_HOST and SOURCE\_PORT options in CHANGE REPLICATION SOURCE TO statement produced with --dump-replica | 8.0.26 |  |
| [--insert-ignore](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_insert-ignore) | Write INSERT IGNORE rather than INSERT statements |  |  |
| [--lines-terminated-by](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lines-terminated-by) | This option is used with the --tab option and has the same meaning as the corresponding clause for LOAD DATA |  |  |
| [--lock-all-tables](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-all-tables) | Lock all tables across all databases |  |  |
| [--lock-tables](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-tables) | Lock all tables before dumping them |  |  |
| [--log-error](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_log-error) | Append warnings and errors to named file |  |  |
| [--login-path](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_login-path) | Read login path options from .mylogin.cnf |  |  |
| [--master-data](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_master-data) | Write the binary log file name and position to the output |  | 8.0.26 |
| [--max-allowed-packet](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_max-allowed-packet) | Maximum packet length to send to or receive from server |  |  |
| [--mysqld-long-query-time](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_mysqld-long-query-time) | Session value for slow query threshold | 8.0.30 |  |
| [--net-buffer-length](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_net-buffer-length) | Buffer size for TCP/IP and socket communication |  |  |
| [--network-timeout](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_network-timeout) | Increase network timeouts to permit larger table dumps |  |  |
| [--no-autocommit](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-autocommit) | Enclose the INSERT statements for each dumped table within SET autocommit = 0 and COMMIT statements |  |  |
| [--no-create-db](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-create-db) | Do not write CREATE DATABASE statements |  |  |
| [--no-create-info](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-create-info) | Do not write CREATE TABLE statements that re-create each dumped table |  |  |
| [--no-data](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-data) | Do not dump table contents |  |  |
| [--no-defaults](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-defaults) | Read no option files |  |  |
| [--no-set-names](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-set-names) | Same as --skip-set-charset |  |  |
| [--no-tablespaces](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-tablespaces) | Do not write any CREATE LOGFILE GROUP or CREATE TABLESPACE statements in output |  |  |
| [--opt](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt) | Shorthand for --add-drop-table --add-locks --create-options --disable-keys --extended-insert --lock-tables --quick --set-charset |  |  |
| [--order-by-primary](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_order-by-primary) | Dump each table's rows sorted by its primary key, or by its first unique index |  |  |
| [--password](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password) | Password to use when connecting to server |  |  |
| [--password1](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password1) | First multifactor authentication password to use when connecting to server | 8.0.27 |  |
| [--password2](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password2) | Second multifactor authentication password to use when connecting to server | 8.0.27 |  |
| [--password3](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password3) | Third multifactor authentication password to use when connecting to server | 8.0.27 |  |
| [--pipe](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_pipe) | Connect to server using named pipe (Windows only) |  |  |
| [--plugin-authentication-kerberos-client-mode](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_plugin-authentication-kerberos-client-mode) | Permit GSSAPI pluggable authentication through the MIT Kerberos library on Windows | 8.0.32 |  |
| [--plugin-dir](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_plugin-dir) | Directory where plugins are installed |  |  |
| [--port](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_port) | TCP/IP port number for connection |  |  |
| [--print-defaults](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_print-defaults) | Print default options |  |  |
| [--protocol](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_protocol) | Transport protocol to use |  |  |
| [--quick](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quick) | Retrieve rows for a table from the server a row at a time |  |  |
| [--quote-names](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quote-names) | Quote identifiers within backtick characters |  |  |
| [--replace](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_replace) | Write REPLACE statements rather than INSERT statements |  |  |
| [--result-file](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_result-file) | Direct output to a given file |  |  |
| [--routines](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_routines) | Dump stored routines (procedures and functions) from dumped databases |  |  |
| [--server-public-key-path](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_server-public-key-path) | Path name to file containing RSA public key |  |  |
| [--set-charset](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_set-charset) | Add SET NAMES default\_character\_set to output |  |  |
| [--set-gtid-purged](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_set-gtid-purged) | Whether to add SET @@GLOBAL.GTID\_PURGED to output |  |  |
| [--shared-memory-base-name](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_shared-memory-base-name) | Shared-memory name for shared-memory connections (Windows only) |  |  |
| [--show-create-skip-secondary-engine](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_show-create-skip-secondary-engine) | Exclude SECONDARY ENGINE clause from CREATE TABLE statements | 8.0.18 |  |
| [--single-transaction](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction) | Issue a BEGIN SQL statement before dumping data from server |  |  |
| [--skip-add-drop-table](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-table) | Do not add a DROP TABLE statement before each CREATE TABLE statement |  |  |
| [--skip-add-locks](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-locks) | Do not add locks |  |  |
| [--skip-comments](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-comments) | Do not add comments to dump file |  |  |
| [--skip-compact](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_compact) | Do not produce more compact output |  |  |
| [--skip-disable-keys](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_disable-keys) | Do not disable keys |  |  |
| [--skip-extended-insert](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_extended-insert) | Turn off extended-insert |  |  |
| [--skip-generated-invisible-primary-key](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-generated-invisible-primary-key) | Do not include generated invisible primary keys in dump file | 8.0.30 |  |
| [--skip-opt](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-opt) | Turn off options set by --opt |  |  |
| [--skip-quick](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quick) | Do not retrieve rows for a table from the server a row at a time |  |  |
| [--skip-quote-names](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quote-names) | Do not quote identifiers |  |  |
| [--skip-set-charset](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_set-charset) | Do not write SET NAMES statement |  |  |
| [--skip-triggers](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_triggers) | Do not dump triggers |  |  |
| [--skip-tz-utc](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tz-utc) | Turn off tz-utc |  |  |
| [--socket](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_socket) | Unix socket file or Windows named pipe to use |  |  |
| [--source-data](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_source-data) | Write the binary log file name and position to the output | 8.0.26 |  |
| [--ssl-ca](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl) | File that contains list of trusted SSL Certificate Authorities |  |  |
| [--ssl-capath](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl) | Directory that contains trusted SSL Certificate Authority certificate files |  |  |
| [--ssl-cert](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl) | File that contains X.509 certificate |  |  |
| [--ssl-cipher](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl) | Permissible ciphers for connection encryption |  |  |
| [--ssl-crl](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl) | File that contains certificate revocation lists |  |  |
| [--ssl-crlpath](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl) | Directory that contains certificate revocation-list files |  |  |
| [--ssl-fips-mode](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl-fips-mode) | Whether to enable FIPS mode on client side |  | 8.0.34 |
| [--ssl-key](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl) | File that contains X.509 key |  |  |
| [--ssl-mode](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl) | Desired security state of connection to server |  |  |
| [--ssl-session-data](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl) | File that contains SSL session data | 8.0.29 |  |
| [--ssl-session-data-continue-on-failed-reuse](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl) | Whether to establish connections if session reuse fails | 8.0.29 |  |
| [--tab](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tab) | Produce tab-separated data files |  |  |
| [--tables](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tables) | Override --databases or -B option |  |  |
| [--tls-ciphersuites](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tls-ciphersuites) | Permissible TLSv1.3 ciphersuites for encrypted connections | 8.0.16 |  |
| [--tls-version](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tls-version) | Permissible TLS protocols for encrypted connections |  |  |
| [--triggers](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_triggers) | Dump triggers for each dumped table |  |  |
| [--tz-utc](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tz-utc) | Add SET TIME\_ZONE='+00:00' to dump file |  |  |
| [--user](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_user) | MySQL user name to use when connecting to server |  |  |
| [--verbose](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_verbose) | Verbose mode |  |  |
| [--version](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_version) | Display version information and exit |  |  |
| [--where](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_where) | Dump only rows selected by given WHERE condition |  |  |
| [--xml](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_xml) | Produce XML output |  |  |
| [--zstd-compression-level](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_zstd-compression-level) | Compression level for connections to server that use zstd compression | 8.0.18 |  |

| Option Name | Description | Introduced | Deprecated |
| --- | --- | --- | --- |

#### Connection Options

The [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") command logs into a MySQL
server to extract information. The following options specify how
to connect to the MySQL server, either on the same machine or a
remote system.

- [`--bind-address=ip_address`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_bind-address)




| Command-Line Format | `--bind-address=ip_address` |




On a computer having multiple network interfaces, use this
option to select which interface to use for connecting to
the MySQL server.


- [`--compress`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_compress),
`-C`




| Command-Line Format | `--compress[={OFF|ON}]` |
| Deprecated | 8.0.18 |
| Type | Boolean |
| Default Value | `OFF` |




Compress all information sent between the client and the
server if possible. See
[Section 6.2.8, “Connection Compression Control”](https://dev.mysql.com/doc/refman/8.0/en/connection-compression-control.html "6.2.8 Connection Compression Control").



As of MySQL 8.0.18, this option is deprecated. Expect it to
be removed in a future version of MySQL. See
[Configuring Legacy Connection Compression](https://dev.mysql.com/doc/refman/8.0/en/connection-compression-control.html#connection-compression-legacy-configuration "Configuring Legacy Connection Compression").


- [`--compression-algorithms=value`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_compression-algorithms)




| Command-Line Format | `--compression-algorithms=value` |
| Introduced | 8.0.18 |
| Type | Set |
| Default Value | `uncompressed` |
| Valid Values | `zlib`<br>`zstd`<br>`uncompressed` |




The permitted compression algorithms for connections to the
server. The available algorithms are the same as for the
[`protocol_compression_algorithms`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_protocol_compression_algorithms)
system variable. The default value is
`uncompressed`.



For more information, see
[Section 6.2.8, “Connection Compression Control”](https://dev.mysql.com/doc/refman/8.0/en/connection-compression-control.html "6.2.8 Connection Compression Control").



This option was added in MySQL 8.0.18.


- [`--default-auth=plugin`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_default-auth)




| Command-Line Format | `--default-auth=plugin` |
| Type | String |




A hint about which client-side authentication plugin to use.
See [Section 8.2.17, “Pluggable Authentication”](https://dev.mysql.com/doc/refman/8.0/en/pluggable-authentication.html "8.2.17 Pluggable Authentication").


- [`--enable-cleartext-plugin`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_enable-cleartext-plugin)




| Command-Line Format | `--enable-cleartext-plugin` |
| Type | Boolean |
| Default Value | `FALSE` |




Enable the `mysql_clear_password` cleartext
authentication plugin. (See
[Section 8.4.1.4, “Client-Side Cleartext Pluggable Authentication”](https://dev.mysql.com/doc/refman/8.0/en/cleartext-pluggable-authentication.html "8.4.1.4 Client-Side Cleartext Pluggable Authentication").)


- [`--get-server-public-key`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_get-server-public-key)




| Command-Line Format | `--get-server-public-key` |
| Type | Boolean |




Request from the server the public key required for RSA key
pair-based password exchange. This option applies to clients
that authenticate with the
`caching_sha2_password` authentication
plugin. For that plugin, the server does not send the public
key unless requested. This option is ignored for accounts
that do not authenticate with that plugin. It is also
ignored if RSA-based password exchange is not used, as is
the case when the client connects to the server using a
secure connection.



If
[`--server-public-key-path=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_server-public-key-path)
is given and specifies a valid public key file, it takes
precedence over
[`--get-server-public-key`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_get-server-public-key).



For information about the
`caching_sha2_password` plugin, see
[Section 8.4.1.2, “Caching SHA-2 Pluggable Authentication”](https://dev.mysql.com/doc/refman/8.0/en/caching-sha2-pluggable-authentication.html "8.4.1.2 Caching SHA-2 Pluggable Authentication").


- [`--host=host_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_host),
`-h host_name`




| Command-Line Format | `--host` |




Dump data from the MySQL server on the given host. The
default host is `localhost`.


- [`--login-path=name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_login-path)




| Command-Line Format | `--login-path=name` |
| Type | String |




Read options from the named login path in the
`.mylogin.cnf` login path file. A
“login path” is an option group containing
options that specify which MySQL server to connect to and
which account to authenticate as. To create or modify a
login path file, use the
[**mysql\_config\_editor**](https://dev.mysql.com/doc/refman/8.0/en/mysql-config-editor.html "6.6.7 mysql_config_editor — MySQL Configuration Utility") utility. See
[Section 6.6.7, “mysql\_config\_editor — MySQL Configuration Utility”](https://dev.mysql.com/doc/refman/8.0/en/mysql-config-editor.html "6.6.7 mysql_config_editor — MySQL Configuration Utility").



For additional information about this and other option-file
options, see [Section 6.2.2.3, “Command-Line Options that Affect Option-File Handling”](https://dev.mysql.com/doc/refman/8.0/en/option-file-options.html "6.2.2.3 Command-Line Options that Affect Option-File Handling").


- [`--password[=password]`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password),
`-p[password]`




| Command-Line Format | `--password[=password]` |
| Type | String |




The password of the MySQL account used for connecting to the
server. The password value is optional. If not given,
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") prompts for one. If given,
there must be _no space_ between
[`--password=`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password) or
`-p` and the password following it. If no
password option is specified, the default is to send no
password.



Specifying a password on the command line should be
considered insecure. To avoid giving the password on the
command line, use an option file. See
[Section 8.1.2.1, “End-User Guidelines for Password Security”](https://dev.mysql.com/doc/refman/8.0/en/password-security-user.html "8.1.2.1 End-User Guidelines for Password Security").



To explicitly specify that there is no password and that
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") should not prompt for one, use
the
[`--skip-password`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password)
option.


- [`--password1[=pass_val]`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password1)


The password for multifactor authentication factor 1 of the
MySQL account used for connecting to the server. The
password value is optional. If not given,
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") prompts for one. If given,
there must be _no space_ between
[`--password1=`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password1) and the
password following it. If no password option is specified,
the default is to send no password.



Specifying a password on the command line should be
considered insecure. To avoid giving the password on the
command line, use an option file. See
[Section 8.1.2.1, “End-User Guidelines for Password Security”](https://dev.mysql.com/doc/refman/8.0/en/password-security-user.html "8.1.2.1 End-User Guidelines for Password Security").



To explicitly specify that there is no password and that
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") should not prompt for one, use
the
[`--skip-password1`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password1)
option.


[`--password1`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password1) and
[`--password`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password) are synonymous,
as are
[`--skip-password1`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password1)
and
[`--skip-password`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password).


- [`--password2[=pass_val]`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password2)


The password for multifactor authentication factor 2 of the
MySQL account used for connecting to the server. The
semantics of this option are similar to the semantics for
[`--password1`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password1); see the
description of that option for details.


- [`--password3[=pass_val]`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password3)


The password for multifactor authentication factor 3 of the
MySQL account used for connecting to the server. The
semantics of this option are similar to the semantics for
[`--password1`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_password1); see the
description of that option for details.


- [`--pipe`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_pipe),
`-W`




| Command-Line Format | `--pipe` |
| Type | String |




On Windows, connect to the server using a named pipe. This
option applies only if the server was started with the
[`named_pipe`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_named_pipe) system variable
enabled to support named-pipe connections. In addition, the
user making the connection must be a member of the Windows
group specified by the
[`named_pipe_full_access_group`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_named_pipe_full_access_group)
system variable.


- [`--plugin-authentication-kerberos-client-mode=value`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_plugin-authentication-kerberos-client-mode)




| Command-Line Format | `--plugin-authentication-kerberos-client-mode` |
| Introduced | 8.0.32 |
| Type | String |
| Default Value | `SSPI` |
| Valid Values | `GSSAPI` |




On Windows, the
`authentication_kerberos_client`
authentication plugin supports this plugin option. It
provides two possible values that the client user can set at
runtime: `SSPI` and
`GSSAPI`.



The default value for the client-side plugin option uses
Security Support Provider Interface (SSPI), which is capable
of acquiring credentials from the Windows in-memory cache.
Alternatively, the client user can select a mode that
supports Generic Security Service Application Program
Interface (GSSAPI) through the MIT Kerberos library on
Windows. GSSAPI is capable of acquiring cached credentials
previously generated by using the **kinit**
command.



For more information, see
[Commands\\
for Windows Clients in GSSAPI Mode](https://dev.mysql.com/doc/refman/8.0/en/kerberos-pluggable-authentication.html#kerberos-usage-win-gssapi-client-commands).


- [`--plugin-dir=dir_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_plugin-dir)




| Command-Line Format | `--plugin-dir=dir_name` |
| Type | Directory name |




The directory in which to look for plugins. Specify this
option if the
[`--default-auth`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_default-auth) option is
used to specify an authentication plugin but
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") does not find it. See
[Section 8.2.17, “Pluggable Authentication”](https://dev.mysql.com/doc/refman/8.0/en/pluggable-authentication.html "8.2.17 Pluggable Authentication").


- [`--port=port_num`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_port),
`-P port_num`




| Command-Line Format | `--port=port_num` |
| Type | Numeric |
| Default Value | `3306` |




For TCP/IP connections, the port number to use.


- [`--protocol={TCP|SOCKET|PIPE|MEMORY}`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_protocol)




| Command-Line Format | `--protocol=type` |
| Type | String |
| Default Value | `[see text]` |
| Valid Values | `TCP`<br>`SOCKET`<br>`PIPE`<br>`MEMORY` |




The transport protocol to use for connecting to the server.
It is useful when the other connection parameters normally
result in use of a protocol other than the one you want. For
details on the permissible values, see
[Section 6.2.7, “Connection Transport Protocols”](https://dev.mysql.com/doc/refman/8.0/en/transport-protocols.html "6.2.7 Connection Transport Protocols").


- [`--server-public-key-path=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_server-public-key-path)




| Command-Line Format | `--server-public-key-path=file_name` |
| Type | File name |




The path name to a file in PEM format containing a
client-side copy of the public key required by the server
for RSA key pair-based password exchange. This option
applies to clients that authenticate with the
`sha256_password` or
`caching_sha2_password` authentication
plugin. This option is ignored for accounts that do not
authenticate with one of those plugins. It is also ignored
if RSA-based password exchange is not used, as is the case
when the client connects to the server using a secure
connection.



If
[`--server-public-key-path=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_server-public-key-path)
is given and specifies a valid public key file, it takes
precedence over
[`--get-server-public-key`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_get-server-public-key).



For `sha256_password`, this option applies
only if MySQL was built using OpenSSL.



For information about the `sha256_password`
and `caching_sha2_password` plugins, see
[Section 8.4.1.3, “SHA-256 Pluggable Authentication”](https://dev.mysql.com/doc/refman/8.0/en/sha256-pluggable-authentication.html "8.4.1.3 SHA-256 Pluggable Authentication"), and
[Section 8.4.1.2, “Caching SHA-2 Pluggable Authentication”](https://dev.mysql.com/doc/refman/8.0/en/caching-sha2-pluggable-authentication.html "8.4.1.2 Caching SHA-2 Pluggable Authentication").


- [`--socket=path`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_socket),
`-S path`




| Command-Line Format | `--socket={file_name|pipe_name}` |
| Type | String |




For connections to `localhost`, the Unix
socket file to use, or, on Windows, the name of the named
pipe to use.



On Windows, this option applies only if the server was
started with the [`named_pipe`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_named_pipe)
system variable enabled to support named-pipe connections.
In addition, the user making the connection must be a member
of the Windows group specified by the
[`named_pipe_full_access_group`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_named_pipe_full_access_group)
system variable.


- `--ssl*`


Options that begin with `--ssl` specify
whether to connect to the server using encryption and
indicate where to find SSL keys and certificates. See
[Command Options for Encrypted Connections](https://dev.mysql.com/doc/refman/8.0/en/connection-options.html#encrypted-connection-options "Command Options for Encrypted Connections").


- [`--ssl-fips-mode={OFF|ON|STRICT}`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl-fips-mode)




| Command-Line Format | `--ssl-fips-mode={OFF|ON|STRICT}` |
| Deprecated | 8.0.34 |
| Type | Enumeration |
| Default Value | `OFF` |
| Valid Values | `OFF`<br>`ON`<br>`STRICT` |




Controls whether to enable FIPS mode on the client side. The
[`--ssl-fips-mode`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl-fips-mode) option
differs from other
`--ssl-xxx`
options in that it is not used to establish encrypted
connections, but rather to affect which cryptographic
operations to permit. See [Section 8.8, “FIPS Support”](https://dev.mysql.com/doc/refman/8.0/en/fips-mode.html "8.8 FIPS Support").



These [`--ssl-fips-mode`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl-fips-mode)
values are permitted:




- `OFF`: Disable FIPS mode.


- `ON`: Enable FIPS mode.


- `STRICT`: Enable “strict”
FIPS mode.


Note

If the OpenSSL FIPS Object Module is not available, the
only permitted value for
[`--ssl-fips-mode`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl-fips-mode) is
`OFF`. In this case, setting
[`--ssl-fips-mode`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ssl-fips-mode) to
`ON` or `STRICT` causes
the client to produce a warning at startup and to operate
in non-FIPS mode.

As of MySQL 8.0.34, this option is deprecated. Expect it to
be removed in a future version of MySQL.


- [`--tls-ciphersuites=ciphersuite_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tls-ciphersuites)




| Command-Line Format | `--tls-ciphersuites=ciphersuite_list` |
| Introduced | 8.0.16 |
| Type | String |




The permissible ciphersuites for encrypted connections that
use TLSv1.3. The value is a list of one or more
colon-separated ciphersuite names. The ciphersuites that can
be named for this option depend on the SSL library used to
compile MySQL. For details, see
[Section 8.3.2, “Encrypted Connection TLS Protocols and Ciphers”](https://dev.mysql.com/doc/refman/8.0/en/encrypted-connection-protocols-ciphers.html "8.3.2 Encrypted Connection TLS Protocols and Ciphers").



This option was added in MySQL 8.0.16.


- [`--tls-version=protocol_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tls-version)




| Command-Line Format | `--tls-version=protocol_list` |
| Type | String |
| Default Value (≥ 8.0.16) | `TLSv1,TLSv1.1,TLSv1.2,TLSv1.3` (OpenSSL 1.1.1 or higher)<br>`TLSv1,TLSv1.1,TLSv1.2` (otherwise) |
| Default Value (≤ 8.0.15) | `TLSv1,TLSv1.1,TLSv1.2` |




The permissible TLS protocols for encrypted connections. The
value is a list of one or more comma-separated protocol
names. The protocols that can be named for this option
depend on the SSL library used to compile MySQL. For
details, see
[Section 8.3.2, “Encrypted Connection TLS Protocols and Ciphers”](https://dev.mysql.com/doc/refman/8.0/en/encrypted-connection-protocols-ciphers.html "8.3.2 Encrypted Connection TLS Protocols and Ciphers").


- [`--user=user_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_user),
`-u user_name`




| Command-Line Format | `--user=user_name` |
| Type | String |




The user name of the MySQL account to use for connecting to
the server.



If you are using the `Rewriter` plugin with
MySQL 8.0.31 or later, you should grant this user the
[`SKIP_QUERY_REWRITE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_skip-query-rewrite) privilege.


- [`--zstd-compression-level=level`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_zstd-compression-level)




| Command-Line Format | `--zstd-compression-level=#` |
| Introduced | 8.0.18 |
| Type | Integer |




The compression level to use for connections to the server
that use the `zstd` compression algorithm.
The permitted levels are from 1 to 22, with larger values
indicating increasing levels of compression. The default
`zstd` compression level is 3. The
compression level setting has no effect on connections that
do not use `zstd` compression.



For more information, see
[Section 6.2.8, “Connection Compression Control”](https://dev.mysql.com/doc/refman/8.0/en/connection-compression-control.html "6.2.8 Connection Compression Control").



This option was added in MySQL 8.0.18.


#### Option-File Options

These options are used to control which option files to read.

- [`--defaults-extra-file=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_defaults-extra-file)




| Command-Line Format | `--defaults-extra-file=file_name` |
| Type | File name |




Read this option file after the global option file but (on
Unix) before the user option file. If the file does not
exist or is otherwise inaccessible, an error occurs. If
_`file_name`_ is not an absolute path
name, it is interpreted relative to the current directory.



For additional information about this and other option-file
options, see [Section 6.2.2.3, “Command-Line Options that Affect Option-File Handling”](https://dev.mysql.com/doc/refman/8.0/en/option-file-options.html "6.2.2.3 Command-Line Options that Affect Option-File Handling").


- [`--defaults-file=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_defaults-file)




| Command-Line Format | `--defaults-file=file_name` |
| Type | File name |




Use only the given option file. If the file does not exist
or is otherwise inaccessible, an error occurs. If
_`file_name`_ is not an absolute path
name, it is interpreted relative to the current directory.



Exception: Even with
[`--defaults-file`](https://dev.mysql.com/doc/refman/8.0/en/option-file-options.html#option_general_defaults-file), client
programs read `.mylogin.cnf`.



For additional information about this and other option-file
options, see [Section 6.2.2.3, “Command-Line Options that Affect Option-File Handling”](https://dev.mysql.com/doc/refman/8.0/en/option-file-options.html "6.2.2.3 Command-Line Options that Affect Option-File Handling").


- [`--defaults-group-suffix=str`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_defaults-group-suffix)




| Command-Line Format | `--defaults-group-suffix=str` |
| Type | String |




Read not only the usual option groups, but also groups with
the usual names and a suffix of
_`str`_. For example,
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") normally reads the
`[client]` and
`[mysqldump]` groups. If this option is
given as
[`--defaults-group-suffix=_other`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_defaults-group-suffix),
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") also reads the
`[client_other]` and
`[mysqldump_other]` groups.



For additional information about this and other option-file
options, see [Section 6.2.2.3, “Command-Line Options that Affect Option-File Handling”](https://dev.mysql.com/doc/refman/8.0/en/option-file-options.html "6.2.2.3 Command-Line Options that Affect Option-File Handling").


- [`--no-defaults`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-defaults)




| Command-Line Format | `--no-defaults` |




Do not read any option files. If program startup fails due
to reading unknown options from an option file,
[`--no-defaults`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-defaults) can be used
to prevent them from being read.



The exception is that the `.mylogin.cnf`
file is read in all cases, if it exists. This permits
passwords to be specified in a safer way than on the command
line even when
[`--no-defaults`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-defaults) is used. To
create `.mylogin.cnf`, use the
[**mysql\_config\_editor**](https://dev.mysql.com/doc/refman/8.0/en/mysql-config-editor.html "6.6.7 mysql_config_editor — MySQL Configuration Utility") utility. See
[Section 6.6.7, “mysql\_config\_editor — MySQL Configuration Utility”](https://dev.mysql.com/doc/refman/8.0/en/mysql-config-editor.html "6.6.7 mysql_config_editor — MySQL Configuration Utility").



For additional information about this and other option-file
options, see [Section 6.2.2.3, “Command-Line Options that Affect Option-File Handling”](https://dev.mysql.com/doc/refman/8.0/en/option-file-options.html "6.2.2.3 Command-Line Options that Affect Option-File Handling").


- [`--print-defaults`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_print-defaults)




| Command-Line Format | `--print-defaults` |




Print the program name and all options that it gets from
option files.



For additional information about this and other option-file
options, see [Section 6.2.2.3, “Command-Line Options that Affect Option-File Handling”](https://dev.mysql.com/doc/refman/8.0/en/option-file-options.html "6.2.2.3 Command-Line Options that Affect Option-File Handling").


#### DDL Options

Usage scenarios for [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") include setting
up an entire new MySQL instance (including database tables), and
replacing data inside an existing instance with existing
databases and tables. The following options let you specify
which things to tear down and set up when restoring a dump, by
encoding various DDL statements within the dump file.

- [`--add-drop-database`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-database)




| Command-Line Format | `--add-drop-database` |




Write a [`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement")
statement before each [`CREATE\\
              DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "15.1.12 CREATE DATABASE Statement") statement. This option is typically used
in conjunction with the
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-databases) or
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_databases) option because
no [`CREATE DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "15.1.12 CREATE DATABASE Statement") statements
are written unless one of those options is specified.





Note





In MySQL 8.0, the `mysql`
schema is considered a system schema that cannot be
dropped by end users. If
[`--add-drop-database`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-database) is
used with
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-databases) or with
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_databases) where the
list of schemas to be dumped includes
`mysql`, the dump file contains a
``DROP DATABASE `mysql` `` statement that
causes an error when the dump file is reloaded.





Instead, to use
[`--add-drop-database`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-database), use
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_databases) with a list
of schemas to be dumped, where the list does not include
`mysql`.

- [`--add-drop-table`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-table)




| Command-Line Format | `--add-drop-table` |




Write a [`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") statement
before each [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement")
statement.


- [`--add-drop-trigger`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-trigger)




| Command-Line Format | `--add-drop-trigger` |




Write a [`DROP TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/drop-trigger.html "15.1.34 DROP TRIGGER Statement")
statement before each [`CREATE\\
              TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "15.1.22 CREATE TRIGGER Statement") statement.


- [`--all-tablespaces`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-tablespaces),
`-Y`




| Command-Line Format | `--all-tablespaces` |




Adds to a table dump all SQL statements needed to create any
tablespaces used by an [`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0")
table. This information is not otherwise included in the
output from [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program"). This option is
currently relevant only to NDB Cluster tables.


- [`--no-create-db`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-create-db),
`-n`




| Command-Line Format | `--no-create-db` |




Suppress the [`CREATE DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "15.1.12 CREATE DATABASE Statement")
statements that are otherwise included in the output if the
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_databases) or
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-databases) option is
given.


- [`--no-create-info`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-create-info),
`-t`




| Command-Line Format | `--no-create-info` |




Do not write [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement")
statements that create each dumped table.





Note





This option does _not_ exclude
statements creating log file groups or tablespaces from
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") output; however, you can use
the [`--no-tablespaces`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-tablespaces)
option for this purpose.

- [`--no-tablespaces`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-tablespaces),
`-y`




| Command-Line Format | `--no-tablespaces` |




This option suppresses all [`CREATE\\
              LOGFILE GROUP`](https://dev.mysql.com/doc/refman/8.0/en/create-logfile-group.html "15.1.16 CREATE LOGFILE GROUP Statement") and [`CREATE\\
              TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/create-tablespace.html "15.1.21 CREATE TABLESPACE Statement") statements in the output of
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program").


- [`--replace`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_replace)




| Command-Line Format | `--replace` |




Write [`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") statements
rather than [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement")
statements.


#### Debug Options

The following options print debugging information, encode
debugging information in the dump file, or let the dump
operation proceed regardless of potential problems.

- [`--allow-keywords`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_allow-keywords)




| Command-Line Format | `--allow-keywords` |




Permit creation of column names that are keywords. This
works by prefixing each column name with the table name.


- [`--comments`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_comments),
`-i`




| Command-Line Format | `--comments` |




Write additional information in the dump file such as
program version, server version, and host. This option is
enabled by default. To suppress this additional information,
use [`--skip-comments`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-comments).


- [`--debug[=debug_options]`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_debug),
`-#
              [debug_options]`




| Command-Line Format | `--debug[=debug_options]` |
| Type | String |
| Default Value | `d:t:o,/tmp/mysqldump.trace` |




Write a debugging log. A typical
_`debug_options`_ string is
`d:t:o,file_name`.
The default value is
`d:t:o,/tmp/mysqldump.trace`.



This option is available only if MySQL was built using
[`WITH_DEBUG`](https://dev.mysql.com/doc/refman/8.0/en/source-configuration-options.html#option_cmake_with_debug). MySQL release
binaries provided by Oracle are _not_
built using this option.


- [`--debug-check`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_debug-check)




| Command-Line Format | `--debug-check` |
| Type | Boolean |
| Default Value | `FALSE` |




Print some debugging information when the program exits.



This option is available only if MySQL was built using
[`WITH_DEBUG`](https://dev.mysql.com/doc/refman/8.0/en/source-configuration-options.html#option_cmake_with_debug). MySQL release
binaries provided by Oracle are _not_
built using this option.


- [`--debug-info`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_debug-info)




| Command-Line Format | `--debug-info` |
| Type | Boolean |
| Default Value | `FALSE` |




Print debugging information and memory and CPU usage
statistics when the program exits.



This option is available only if MySQL was built using
[`WITH_DEBUG`](https://dev.mysql.com/doc/refman/8.0/en/source-configuration-options.html#option_cmake_with_debug). MySQL release
binaries provided by Oracle are _not_
built using this option.


- [`--dump-date`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-date)




| Command-Line Format | `--dump-date` |
| Type | Boolean |
| Default Value | `TRUE` |




If the [`--comments`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_comments) option
is given, [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") produces a comment at
the end of the dump of the following form:




``` none

  -- Dump completed on DATE
```




However, the date causes dump files taken at different times
to appear to be different, even if the data are otherwise
identical. [`--dump-date`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-date) and
[`--skip-dump-date`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-date)
control whether the date is added to the comment. The
default is [`--dump-date`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-date)
(include the date in the comment).
[`--skip-dump-date`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-date)
suppresses date printing.


- [`--force`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_force),
`-f`




| Command-Line Format | `--force` |




Ignore all errors; continue even if an SQL error occurs
during a table dump.



One use for this option is to cause
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") to continue executing even when
it encounters a view that has become invalid because the
definition refers to a table that has been dropped. Without
`--force`, [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") exits
with an error message. With `--force`,
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") prints the error message, but
it also writes an SQL comment containing the view definition
to the dump output and continues executing.



If the [`--ignore-error`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ignore-error)
option is also given to ignore specific errors,
[`--force`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_force) takes precedence.


- [`--log-error=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_log-error)




| Command-Line Format | `--log-error=file_name` |
| Type | File name |




Log warnings and errors by appending them to the named file.
The default is to do no logging.


- [`--skip-comments`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-comments)




| Command-Line Format | `--skip-comments` |




See the description for the
[`--comments`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_comments) option.


- [`--verbose`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_verbose),
`-v`




| Command-Line Format | `--verbose` |




Verbose mode. Print more information about what the program
does.


#### Help Options

The following options display information about the
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") command itself.

- [`--help`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_help),
`-?`




| Command-Line Format | `--help` |




Display a help message and exit.


- [`--version`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_version),
`-V`




| Command-Line Format | `--version` |




Display version information and exit.


#### Internationalization Options

The following options change how the
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") command represents character data
with national language settings.



- [`--character-sets-dir=dir_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_character-sets-dir)




| Command-Line Format | `--character-sets-dir=dir_name` |
| Type | Directory name |




The directory where character sets are installed. See
[Section 12.15, “Character Set Configuration”](https://dev.mysql.com/doc/refman/8.0/en/charset-configuration.html "12.15 Character Set Configuration").


- [`--default-character-set=charset_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_default-character-set)




| Command-Line Format | `--default-character-set=charset_name` |
| Type | String |
| Default Value | `utf8` |




Use _`charset_name`_ as the default
character set. See [Section 12.15, “Character Set Configuration”](https://dev.mysql.com/doc/refman/8.0/en/charset-configuration.html "12.15 Character Set Configuration").
If no character set is specified,
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") uses
`utf8mb4`.


- [`--no-set-names`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-set-names),
`-N`




| Command-Line Format | `--no-set-names` |
| Deprecated | Yes |




Turns off the
[`--set-charset`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_set-charset) setting, the
same as specifying `--skip-set-charset`.


- [`--set-charset`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_set-charset)




| Command-Line Format | `--set-charset` |
| Disabled by | `skip-set-charset` |




Write [`SET NAMES\\
              default_character_set`](https://dev.mysql.com/doc/refman/8.0/en/set-names.html "15.7.6.3 SET NAMES Statement")
to the output. This option is enabled by default. To
suppress the [`SET NAMES`](https://dev.mysql.com/doc/refman/8.0/en/set-names.html "15.7.6.3 SET NAMES Statement")
statement, use
[`--skip-set-charset`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_set-charset).


#### Replication Options

The [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") command is frequently used to
create an empty instance, or an instance including data, on a
replica server in a replication configuration. The following
options apply to dumping and restoring data on replication
source servers and replicas.



- [`--apply-replica-statements`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_apply-replica-statements)




| Command-Line Format | `--apply-replica-statements` |
| Introduced | 8.0.26 |
| Type | Boolean |
| Default Value | `FALSE` |




From MySQL 8.0.26, use
`--apply-replica-statements`, and before
MySQL 8.0.26, use
[`--apply-slave-statements`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_apply-slave-statements).
Both options have the same effect. For a replica dump
produced with the
[`--dump-replica`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-replica) or
[`--dump-slave`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-slave) option, the
options add a
[`STOP\\
              REPLICA`](https://dev.mysql.com/doc/refman/8.0/en/stop-replica.html "15.4.2.8 STOP REPLICA Statement") (or before MySQL 8.0.22,
[`STOP\\
              SLAVE`](https://dev.mysql.com/doc/refman/8.0/en/stop-slave.html "15.4.2.9 STOP SLAVE Statement")) statement before the statement with the
binary log coordinates, and a
[`START\\
              REPLICA`](https://dev.mysql.com/doc/refman/8.0/en/start-replica.html "15.4.2.6 START REPLICA Statement") statement at the end of the output.


- [`--apply-slave-statements`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_apply-slave-statements)




| Command-Line Format | `--apply-slave-statements` |
| Deprecated | 8.0.26 |
| Type | Boolean |
| Default Value | `FALSE` |




Use this option before MySQL 8.0.26 rather than
[`--apply-replica-statements`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_apply-replica-statements).
Both options have the same effect.


- [`--delete-source-logs`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_delete-source-logs)




| Command-Line Format | `--delete-source-logs` |
| Introduced | 8.0.26 |




From MySQL 8.0.26, use
`--delete-source-logs`, and before MySQL
8.0.26, use
[`--delete-master-logs`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_delete-master-logs). Both
options have the same effect. On a replication source
server, the options delete the binary logs by sending a
[`PURGE BINARY LOGS`](https://dev.mysql.com/doc/refman/8.0/en/purge-binary-logs.html "15.4.1.1 PURGE BINARY LOGS Statement") statement
to the server after performing the dump operation. The
options require the [`RELOAD`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_reload)
privilege as well as privileges sufficient to execute that
statement. The options automatically enable
[`--source-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_source-data) or
[`--master-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_master-data).


- [`--delete-master-logs`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_delete-master-logs)




| Command-Line Format | `--delete-master-logs` |
| Deprecated | 8.0.26 |




Use this option before MySQL 8.0.26 rather than
[`--delete-source-logs`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_delete-source-logs). Both
options have the same effect.


- [`--dump-replica[=value]`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-replica)




| Command-Line Format | `--dump-replica[=value]` |
| Introduced | 8.0.26 |
| Type | Numeric |
| Default Value | `1` |
| Valid Values | `1`<br>`2` |




From MySQL 8.0.26, use `--dump-replica`, and
before MySQL 8.0.26, use
[`--dump-slave`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-slave). Both options
have the same effect. The options are similar to
[`--source-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_source-data), except that
they are used to dump a replica server to produce a dump
file that can be used to set up another server as a replica
that has the same source as the dumped server. The options
cause the dump output to include a
[`CHANGE REPLICATION SOURCE TO`](https://dev.mysql.com/doc/refman/8.0/en/change-replication-source-to.html "15.4.2.3 CHANGE REPLICATION SOURCE TO Statement")
statement (from MySQL 8.0.23) or [`CHANGE\\
              MASTER TO`](https://dev.mysql.com/doc/refman/8.0/en/change-master-to.html "15.4.2.1 CHANGE MASTER TO Statement") statement (before MySQL 8.0.23) that
indicates the binary log coordinates (file name and
position) of the dumped replica's source. The
[`CHANGE REPLICATION SOURCE TO`](https://dev.mysql.com/doc/refman/8.0/en/change-replication-source-to.html "15.4.2.3 CHANGE REPLICATION SOURCE TO Statement")
statement reads the values of
`Relay_Master_Log_File` and
`Exec_Master_Log_Pos` from the
[`SHOW\\
              REPLICA STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-replica-status.html "15.7.7.35 SHOW REPLICA STATUS Statement") output and uses them for
`SOURCE_LOG_FILE` and
`SOURCE_LOG_POS` respectively. These are
the replication source server coordinates from which the
replica starts replicating.





Note





Inconsistencies in the sequence of transactions from the
relay log which have been executed can cause the wrong
position to be used. See
[Section 19.5.1.34, “Replication and Transaction Inconsistencies”](https://dev.mysql.com/doc/refman/8.0/en/replication-features-transaction-inconsistencies.html "19.5.1.34 Replication and Transaction Inconsistencies")
for more information.




`--dump-replica` or
`--dump-slave` causes the coordinates from
the source to be used rather than those of the dumped
server, as is done by the
[`--source-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_source-data) or
[`--master-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_master-data) option. In
addition, specifying this option causes the
[`--source-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_source-data) or
`--master-data` option to be overridden, if
used, and effectively ignored.





Warning




`--dump-replica` or
`--dump-slave` should not be used if the
server where the dump is going to be applied uses
[`gtid_mode=ON`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_mode) and
`SOURCE_AUTO_POSITION=1` or
`MASTER_AUTO_POSITION=1`.





The option value is handled the same way as for
[`--source-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_source-data). Setting no
value or 1 causes a [`CHANGE REPLICATION\\
              SOURCE TO`](https://dev.mysql.com/doc/refman/8.0/en/change-replication-source-to.html "15.4.2.3 CHANGE REPLICATION SOURCE TO Statement") statement (from MySQL 8.0.23) or
[`CHANGE MASTER TO`](https://dev.mysql.com/doc/refman/8.0/en/change-master-to.html "15.4.2.1 CHANGE MASTER TO Statement") statement
(before MySQL 8.0.23) to be written to the dump. Setting 2
causes the statement to be written but encased in SQL
comments. It has the same effect as
`--source-data` in terms of enabling or
disabling other options and in how locking is handled.


`--dump-replica` or
`--dump-slave` causes
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") to stop the replication SQL
thread before the dump and restart it again after.


`--dump-replica` or
`--dump-slave` sends a
[`SHOW\\
              REPLICA STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-replica-status.html "15.7.7.35 SHOW REPLICA STATUS Statement") statement to the server to obtain
information, so they require privileges sufficient to
execute that statement.


[`--apply-replica-statements`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_apply-replica-statements)
and
[`--include-source-host-port`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_include-source-host-port)
options can be used in conjunction with
`--dump-replica` or
`--dump-slave`.


- [`--dump-slave[=value]`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-slave)




| Command-Line Format | `--dump-slave[=value]` |
| Deprecated | 8.0.26 |
| Type | Numeric |
| Default Value | `1` |
| Valid Values | `1`<br>`2` |




Use this option before MySQL 8.0.26 rather than
[`--dump-replica`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-replica). Both
options have the same effect.


- [`--include-source-host-port`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_include-source-host-port)




| Command-Line Format | `--include-source-host-port` |
| Introduced | 8.0.26 |
| Type | Boolean |
| Default Value | `FALSE` |




From MySQL 8.0.26, use
`--include-source-host-port`, and before
MySQL 8.0.26, use
[`--include-master-host-port`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_include-master-host-port).
Both options have the same effect. The options add the
`SOURCE_HOST` \|
`MASTER_HOST` and
`SOURCE_PORT` \|
`MASTER_PORT` options for the host name and
TCP/IP port number of the replica's source, to the
[`CHANGE REPLICATION SOURCE TO`](https://dev.mysql.com/doc/refman/8.0/en/change-replication-source-to.html "15.4.2.3 CHANGE REPLICATION SOURCE TO Statement")
statement (from MySQL 8.0.23) or [`CHANGE\\
              MASTER TO`](https://dev.mysql.com/doc/refman/8.0/en/change-master-to.html "15.4.2.1 CHANGE MASTER TO Statement") statement (before MySQL 8.0.23) in a
replica dump produced with the
[`--dump-replica`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-replica) or
[`--dump-slave`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-slave) option.


- [`--include-master-host-port`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_include-master-host-port)




| Command-Line Format | `--include-master-host-port` |
| Deprecated | 8.0.26 |
| Type | Boolean |
| Default Value | `FALSE` |




Use this option before MySQL 8.0.26 rather than
[`--include-source-host-port`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_include-source-host-port).
Both options have the same effect.


- [`--source-data[=value]`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_source-data)




| Command-Line Format | `--source-data[=value]` |
| Introduced | 8.0.26 |
| Type | Numeric |
| Default Value | `1` |
| Valid Values | `1`<br>`2` |




From MySQL 8.0.26, use `--source-data`, and
before MySQL 8.0.26, use
[`--master-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_master-data). Both
options have the same effect. The options are used to dump a
replication source server to produce a dump file that can be
used to set up another server as a replica of the source.
The options cause the dump output to include a
[`CHANGE REPLICATION SOURCE TO`](https://dev.mysql.com/doc/refman/8.0/en/change-replication-source-to.html "15.4.2.3 CHANGE REPLICATION SOURCE TO Statement")
statement (from MySQL 8.0.23) or [`CHANGE\\
              MASTER TO`](https://dev.mysql.com/doc/refman/8.0/en/change-master-to.html "15.4.2.1 CHANGE MASTER TO Statement") statement (before MySQL 8.0.23) that
indicates the binary log coordinates (file name and
position) of the dumped server. These are the replication
source server coordinates from which the replica should
start replicating after you load the dump file into the
replica.



If the option value is 2, the [`CHANGE\\
              REPLICATION SOURCE TO`](https://dev.mysql.com/doc/refman/8.0/en/change-replication-source-to.html "15.4.2.3 CHANGE REPLICATION SOURCE TO Statement") \|
[`CHANGE MASTER TO`](https://dev.mysql.com/doc/refman/8.0/en/change-master-to.html "15.4.2.1 CHANGE MASTER TO Statement") statement is
written as an SQL comment, and thus is informative only; it
has no effect when the dump file is reloaded. If the option
value is 1, the statement is not written as a comment and
takes effect when the dump file is reloaded. If no option
value is specified, the default value is 1.


`--source-data` and
`--master-data` send a
[`SHOW MASTER STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-master-status.html "15.7.7.23 SHOW MASTER STATUS Statement") statement
to the server to obtain information, so they require
privileges sufficient to execute that statement. This option
also requires the [`RELOAD`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_reload)
privilege and the binary log must be enabled.


`--source-data` and
`--master-data` automatically turn off
[`--lock-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-tables). They also
turn on [`--lock-all-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-all-tables),
unless
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction) also
is specified, in which case, a global read lock is acquired
only for a short time at the beginning of the dump (see the
description for
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction)). In
all cases, any action on logs happens at the exact moment of
the dump.



It is also possible to set up a replica by dumping an
existing replica of the source, using the
[`--dump-replica`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-replica) or
[`--dump-slave`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_dump-slave) option, which
overrides `--source-data` and
`--master-data` and causes them to be
ignored.


- [`--master-data[=value]`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_master-data)




| Command-Line Format | `--master-data[=value]` |
| Deprecated | 8.0.26 |
| Type | Numeric |
| Default Value | `1` |
| Valid Values | `1`<br>`2` |




Use this option before MySQL 8.0.26 rather than
[`--source-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_source-data). Both
options have the same effect.


- [`--set-gtid-purged=value`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_set-gtid-purged)




| Command-Line Format | `--set-gtid-purged=value` |
| Type | Enumeration |
| Default Value | `AUTO` |
| Valid Values | `OFF`<br>`ON`<br>`AUTO` |




This option is for servers that use GTID-based replication
( [`gtid_mode=ON`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_mode)). It controls
the inclusion of a `SET
              @@GLOBAL.gtid_purged` statement in the dump output,
which updates the value of
[`gtid_purged`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_purged) on a server
where the dump file is reloaded, to add the GTID set from
the source server's
[`gtid_executed`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_executed) system
variable. [`gtid_purged`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_purged) holds
the GTIDs of all transactions that have been applied on the
server, but do not exist on any binary log file on the
server. [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") therefore adds the
GTIDs for the transactions that were executed on the source
server, so that the target server records these transactions
as applied, although it does not have them in its binary
logs. `--set-gtid-purged` also controls the
inclusion of a `SET
              @@SESSION.sql_log_bin=0` statement, which disables
binary logging while the dump file is being reloaded. This
statement prevents new GTIDs from being generated and
assigned to the transactions in the dump file as they are
executed, so that the original GTIDs for the transactions
are used.



If you do not set the `--set-gtid-purged`
option, the default is that a `SET
              @@GLOBAL.gtid_purged` statement is included in the
dump output if GTIDs are enabled on the server you are
backing up, and the set of GTIDs in the global value of the
[`gtid_executed`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_executed) system
variable is not empty. A `SET
              @@SESSION.sql_log_bin=0` statement is also included
if GTIDs are enabled on the server.



You can either replace the value of
[`gtid_purged`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_purged) with a
specified GTID set, or add a plus sign (+) to the statement
to append a specified GTID set to the GTID set that is
already held by `gtid_purged`. The
`SET @@GLOBAL.gtid_purged` statement
recorded by [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") includes a plus
sign ( `+`) in a version-specific comment,
such that MySQL adds the GTID set from the dump file to the
existing `gtid_purged` value.



It is important to note that the value that is included by
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") for the `SET
              @@GLOBAL.gtid_purged` statement includes the GTIDs
of all transactions in the
[`gtid_executed`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_executed) set on the
server, even those that changed suppressed parts of the
database, or other databases on the server that were not
included in a partial dump. This can mean that after the
[`gtid_purged`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_purged) value has been
updated on the server where the dump file is replayed, GTIDs
are present that do not relate to any data on the target
server. If you do not replay any further dump files on the
target server, the extraneous GTIDs do not cause any
problems with the future operation of the server, but they
make it harder to compare or reconcile GTID sets on
different servers in the replication topology. If you do
replay a further dump file on the target server that
contains the same GTIDs (for example, another partial dump
from the same origin server), any `SET
              @@GLOBAL.gtid_purged` statement in the second dump
file fails. In this case, either remove the statement
manually before replaying the dump file, or output the dump
file without the statement.



Before MySQL 8.0.32: Using this option with the
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction)
option could lead to inconsistencies in the output. If
`--set-gtid-purged=ON` is required, it can be
used with
[`--lock-all-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-all-tables), but
this can prevent parallel queries while
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") is being run.



If the `SET @@GLOBAL.gtid_purged` statement
would not have the desired result on your target server, you
can exclude the statement from the output, or (from MySQL
8.0.17) include it but comment it out so that it is not
actioned automatically. You can also include the statement
but manually edit it in the dump file to achieve the desired
result.



The possible values for the
`--set-gtid-purged` option are as follows:


`AUTO`


The default value. If GTIDs are enabled on the server
you are backing up and
[`gtid_executed`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_executed) is not
empty, `SET @@GLOBAL.gtid_purged` is
added to the output, containing the GTID set from
[`gtid_executed`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_executed). If
GTIDs are enabled, `SET
                    @@SESSION.sql_log_bin=0` is added to the
output. If GTIDs are not enabled on the server, the
statements are not added to the output.


`OFF`

`SET @@GLOBAL.gtid_purged` is not
added to the output, and `SET
                    @@SESSION.sql_log_bin=0` is not added to the
output. For a server where GTIDs are not in use, use
this option or `AUTO`. Only use this
option for a server where GTIDs are in use if you are
sure that the required GTID set is already present in
[`gtid_purged`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_purged) on the
target server and should not be changed, or if you
plan to identify and add any missing GTIDs manually.


`ON`


If GTIDs are enabled on the server you are backing up,
`SET @@GLOBAL.gtid_purged` is added
to the output (unless
[`gtid_executed`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_executed) is
empty), and `SET
                    @@SESSION.sql_log_bin=0` is added to the
output. An error occurs if you set this option but
GTIDs are not enabled on the server. For a server
where GTIDs are in use, use this option or
`AUTO`, unless you are sure that the
GTIDs in
[`gtid_executed`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_executed) are not
needed on the target server.


`COMMENTED`


Available from MySQL 8.0.17. If GTIDs are enabled on
the server you are backing up, `SET
                    @@GLOBAL.gtid_purged` is added to the output
(unless [`gtid_executed`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_executed)
is empty), but it is commented out. This means that
the value of
[`gtid_executed`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_executed) is
available in the output, but no action is taken
automatically when the dump file is reloaded.
`SET @@SESSION.sql_log_bin=0` is
added to the output, and it is not commented out. With
`COMMENTED`, you can control the use
of the [`gtid_executed`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_executed)
set manually or through automation. For example, you
might prefer to do this if you are migrating data to
another server that already has different active
databases.


#### Format Options

The following options specify how to represent the entire dump
file or certain kinds of data in the dump file. They also
control whether certain optional information is written to the
dump file.

- [`--compact`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_compact)




| Command-Line Format | `--compact` |




Produce more compact output. This option enables the
[`--skip-add-drop-table`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-table),
[`--skip-add-locks`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-locks),
[`--skip-comments`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-comments),
[`--skip-disable-keys`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_disable-keys),
and
[`--skip-set-charset`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_set-charset)
options.


- [`--compatible=name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_compatible)




| Command-Line Format | `--compatible=name[,name,...]` |
| Type | String |
| Default Value | `''` |
| Valid Values | `ansi`<br>`mysql323`<br>`mysql40`<br>`postgresql`<br>`oracle`<br>`mssql`<br>`db2`<br>`maxdb`<br>`no_key_options`<br>`no_table_options`<br>`no_key_options` |




Produce output that is more compatible with other database
systems or with older MySQL servers. The only permitted
value for this option is `ansi`, which has
the same meaning as the corresponding option for setting the
server SQL mode. See [Section 7.1.11, “Server SQL Modes”](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html "7.1.11 Server SQL Modes").


- [`--complete-insert`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_complete-insert),
`-c`




| Command-Line Format | `--complete-insert` |




Use complete [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement")
statements that include column names.


- [`--create-options`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_create-options)




| Command-Line Format | `--create-options` |




Include all MySQL-specific table options in the
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statements.


- [`--fields-terminated-by=...`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_fields),
[`--fields-enclosed-by=...`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_fields),
[`--fields-optionally-enclosed-by=...`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_fields),
[`--fields-escaped-by=...`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_fields)




| Command-Line Format | `--fields-terminated-by=string` |
| Type | String |






| Command-Line Format | `--fields-enclosed-by=string` |
| Type | String |






| Command-Line Format | `--fields-optionally-enclosed-by=string` |
| Type | String |






| Command-Line Format | `--fields-escaped-by` |
| Type | String |




These options are used with the
[`--tab`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tab) option and have the
same meaning as the corresponding `FIELDS`
clauses for [`LOAD DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement"). See
[Section 15.2.9, “LOAD DATA Statement”](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement").


- [`--hex-blob`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_hex-blob)




| Command-Line Format | `--hex-blob` |




Dump binary columns using hexadecimal notation (for example,
`'abc'` becomes
`0x616263`). The affected data types are
[`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"),
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"),
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") types,
[`BIT`](https://dev.mysql.com/doc/refman/8.0/en/bit-type.html "13.1.5 Bit-Value Type - BIT"), all spatial data types,
and other non-binary data types when used with the
[`binary`\\
character set](https://dev.mysql.com/doc/refman/8.0/en/charset-binary-set.html "12.10.8 The Binary Character Set").



The [`--hex-blob`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_hex-blob) option is
ignored when the [`--tab`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tab) is
used.


- [`--lines-terminated-by=...`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lines-terminated-by)




| Command-Line Format | `--lines-terminated-by=string` |
| Type | String |




This option is used with the
[`--tab`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tab) option and has the
same meaning as the corresponding `LINES`
clause for [`LOAD DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement"). See
[Section 15.2.9, “LOAD DATA Statement”](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement").


- [`--quote-names`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quote-names),
`-Q`




| Command-Line Format | `--quote-names` |
| Disabled by | `skip-quote-names` |




Quote identifiers (such as database, table, and column
names) within `` ` `` characters. If the
[`ANSI_QUOTES`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_ansi_quotes) SQL mode is
enabled, identifiers are quoted within `"`
characters. This option is enabled by default. It can be
disabled with `--skip-quote-names`, but this
option should be given after any option such as
[`--compatible`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_compatible) that may
enable [`--quote-names`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quote-names).


- [`--result-file=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_result-file),
`-r file_name`




| Command-Line Format | `--result-file=file_name` |
| Type | File name |




Direct output to the named file. The result file is created
and its previous contents overwritten, even if an error
occurs while generating the dump.



This option should be used on Windows to prevent newline
`\n` characters from being converted to
`\r\n` carriage return/newline sequences.


- [`--show-create-skip-secondary-engine=value`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_show-create-skip-secondary-engine)




| Command-Line Format | `--show-create-skip-secondary-engine` |
| Introduced | 8.0.18 |




Excludes the `SECONDARY ENGINE` clause from
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statements. It
does so by enabling the
[`show_create_table_skip_secondary_engine`](https://dev.mysql.com/doc/heatwave/en/heatwave-system-variables.html#sysvar_show_create_table_skip_secondary_engine)
system variable for the duration of the dump operation.
Alternatively, you can enable the
[`show_create_table_skip_secondary_engine`](https://dev.mysql.com/doc/heatwave/en/heatwave-system-variables.html#sysvar_show_create_table_skip_secondary_engine)
system variable prior to using [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program").



This option was added in MySQL 8.0.18. Attempting a
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") operation with the
[`--show-create-skip-secondary-engine`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_show-create-skip-secondary-engine)
option on a release prior to MySQL 8.0.18 that does not
support the
[`show_create_table_skip_secondary_engine`](https://dev.mysql.com/doc/heatwave/en/heatwave-system-variables.html#sysvar_show_create_table_skip_secondary_engine)
variable causes an error.


- [`--tab=dir_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tab),
`-T dir_name`




| Command-Line Format | `--tab=dir_name` |
| Type | Directory name |




Produce tab-separated text-format data files. For each
dumped table, [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") creates a
`tbl_name.sql`
file that contains the [`CREATE\\
              TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement that creates the table, and the
server writes a
`tbl_name.txt`
file that contains its data. The option value is the
directory in which to write the files.





Note





This option should be used only when
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") is run on the same machine as
the [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server") server. Because the server
creates `*.txt` files in the directory
that you specify, the directory must be writable by the
server and the MySQL account that you use must have the
[`FILE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_file) privilege. Because
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") creates
`*.sql` in the same directory, it must
be writable by your system login account.





By default, the `.txt` data files are
formatted using tab characters between column values and a
newline at the end of each line. The format can be specified
explicitly using the
`--fields-xxx` and
[`--lines-terminated-by`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lines-terminated-by)
options.



Column values are converted to the character set specified
by the
[`--default-character-set`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_default-character-set)
option.


- [`--tz-utc`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tz-utc)




| Command-Line Format | `--tz-utc` |
| Disabled by | `skip-tz-utc` |




This option enables [`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types")
columns to be dumped and reloaded between servers in
different time zones. [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") sets its
connection time zone to UTC and adds `SET
              TIME_ZONE='+00:00'` to the dump file. Without this
option, [`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") columns are
dumped and reloaded in the time zones local to the source
and destination servers, which can cause the values to
change if the servers are in different time zones.
`--tz-utc` also protects against changes due
to daylight saving time. `--tz-utc` is
enabled by default. To disable it, use
`--skip-tz-utc`.


- [`--xml`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_xml), `-X`




| Command-Line Format | `--xml` |




Write dump output as well-formed XML.


**`NULL`,**
**`'NULL'`, and Empty Values**: For
a column named _`column_name`_, the
`NULL` value, an empty string, and the
string value `'NULL'` are distinguished
from one another in the output generated by this option as
follows.





| Value: | XML Representation: |
| --- | --- |
| `NULL` (_unknown value_) | `<field<br>                    name="column_name"<br>                    xsi:nil="true" />` |
| `''` (_empty string_) | `<field<br>                    name="column_name"></field>` |
| `'NULL'` (_string value_) | `<field<br>                    name="column_name">NULL</field>` |




The output from the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client when run
using the [`--xml`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_xml) option also
follows the preceding rules. (See
[Section 6.5.1.1, “mysql Client Options”](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html "6.5.1.1 mysql Client Options").)



XML output from [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") includes the
XML namespace, as shown here:




``` terminal

$> mysqldump --xml -u root world City
<?xml version="1.0"?>
<mysqldump xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
<database name="world">
<table_structure name="City">
<field Field="ID" Type="int(11)" Null="NO" Key="PRI" Extra="auto_increment" />
<field Field="Name" Type="char(35)" Null="NO" Key="" Default="" Extra="" />
<field Field="CountryCode" Type="char(3)" Null="NO" Key="" Default="" Extra="" />
<field Field="District" Type="char(20)" Null="NO" Key="" Default="" Extra="" />
<field Field="Population" Type="int(11)" Null="NO" Key="" Default="0" Extra="" />
<key Table="City" Non_unique="0" Key_name="PRIMARY" Seq_in_index="1" Column_name="ID"
Collation="A" Cardinality="4079" Null="" Index_type="BTREE" Comment="" />
<options Name="City" Engine="MyISAM" Version="10" Row_format="Fixed" Rows="4079"
Avg_row_length="67" Data_length="273293" Max_data_length="18858823439613951"
Index_length="43008" Data_free="0" Auto_increment="4080"
Create_time="2007-03-31 01:47:01" Update_time="2007-03-31 01:47:02"
Collation="latin1_swedish_ci" Create_options="" Comment="" />
</table_structure>
<table_data name="City">
<row>
<field name="ID">1</field>
<field name="Name">Kabul</field>
<field name="CountryCode">AFG</field>
<field name="District">Kabol</field>
<field name="Population">1780000</field>
</row>

...

<row>
<field name="ID">4079</field>
<field name="Name">Rafah</field>
<field name="CountryCode">PSE</field>
<field name="District">Rafah</field>
<field name="Population">92020</field>
</row>
</table_data>
</database>
</mysqldump>
```


#### Filtering Options

The following options control which kinds of schema objects are
written to the dump file: by category, such as triggers or
events; by name, for example, choosing which databases and
tables to dump; or even filtering rows from the table data using
a `WHERE` clause.

- [`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-databases),
`-A`




| Command-Line Format | `--all-databases` |




Dump all tables in all databases. This is the same as using
the [`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_databases) option and
naming all the databases on the command line.





Note





See the
[`--add-drop-database`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-database)
description for information about an incompatibility of
that option with
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-databases).





Prior to MySQL 8.0, the
[`--routines`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_routines) and
[`--events`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_events) options for
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") and
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") were not required to include
stored routines and events when using the
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-databases) option:
The dump included the `mysql` system
database, and therefore also the
`mysql.proc` and
`mysql.event` tables containing stored
routine and event definitions. As of MySQL 8.0,
the `mysql.event` and
`mysql.proc` tables are not used.
Definitions for the corresponding objects are stored in data
dictionary tables, but those tables are not dumped. To
include stored routines and events in a dump made using
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-databases), use the
[`--routines`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_routines) and
[`--events`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_events) options
explicitly.


- [`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_databases),
`-B`




| Command-Line Format | `--databases` |




Dump several databases. Normally,
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") treats the first name argument
on the command line as a database name and following names
as table names. With this option, it treats all name
arguments as database names. [`CREATE\\
              DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "15.1.12 CREATE DATABASE Statement") and [`USE`](https://dev.mysql.com/doc/refman/8.0/en/use.html "15.8.4 USE Statement")
statements are included in the output before each new
database.



This option may be used to dump the
`performance_schema` database, which
normally is not dumped even with the
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-databases) option.
(Also use the
[`--skip-lock-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-tables)
option.)





Note





See the
[`--add-drop-database`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-database)
description for information about an incompatibility of
that option with
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_databases).

- [`--events`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_events),
`-E`




| Command-Line Format | `--events` |




Include Event Scheduler events for the dumped databases in
the output. This option requires the
[`EVENT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_event) privileges for those
databases.



The output generated by using `--events`
contains [`CREATE EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement")
statements to create the events.


- [`--ignore-error=error[,error]...`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ignore-error)




| Command-Line Format | `--ignore-error=error[,error]...` |
| Type | String |




Ignore the specified errors. The option value is a list of
comma-separated error numbers specifying the errors to
ignore during [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") execution. If the
[`--force`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_force) option is also
given to ignore all errors,
[`--force`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_force) takes precedence.


- [`--ignore-table=db_name.tbl_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_ignore-table)




| Command-Line Format | `--ignore-table=db_name.tbl_name` |
| Type | String |




Do not dump the given table, which must be specified using
both the database and table names. To ignore multiple
tables, use this option multiple times. This option also can
be used to ignore views.


- [`--no-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-data),
`-d`




| Command-Line Format | `--no-data` |




Do not write any table row information (that is, do not dump
table contents). This is useful if you want to dump only the
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement for
the table (for example, to create an empty copy of the table
by loading the dump file).


- [`--routines`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_routines),
`-R`




| Command-Line Format | `--routines` |




Include stored routines (procedures and functions) for the
dumped databases in the output. This option requires the
global [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege.



The output generated by using `--routines`
contains [`CREATE PROCEDURE`](https://dev.mysql.com/doc/refman/8.0/en/create-procedure.html "15.1.17 CREATE PROCEDURE and CREATE FUNCTION Statements") and
[`CREATE FUNCTION`](https://dev.mysql.com/doc/refman/8.0/en/create-function.html "15.1.14 CREATE FUNCTION Statement") statements to
create the routines.


- [`--skip-generated-invisible-primary-key`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-generated-invisible-primary-key)




| Command-Line Format | `--skip-generated-invisible-primary-key` |
| Introduced | 8.0.30 |
| Type | Boolean |
| Default Value | `FALSE` |




This option is available beginning with MySQL 8.0.30, and
causes generated invisible primary keys to be excluded from
the output. For more information, see
[Section 15.1.20.11, “Generated Invisible Primary Keys”](https://dev.mysql.com/doc/refman/8.0/en/create-table-gipks.html "15.1.20.11 Generated Invisible Primary Keys").


- [`--tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_tables)




| Command-Line Format | `--tables` |




Override the [`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_databases)
or `-B` option. [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program")
regards all name arguments following the option as table
names.


- [`--triggers`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_triggers)




| Command-Line Format | `--triggers` |
| Disabled by | `skip-triggers` |




Include triggers for each dumped table in the output. This
option is enabled by default; disable it with
`--skip-triggers`.



To be able to dump a table's triggers, you must have the
[`TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_trigger) privilege for the
table.



Multiple triggers are permitted.
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") dumps triggers in activation
order so that when the dump file is reloaded, triggers are
created in the same activation order. However, if a
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") dump file contains multiple
triggers for a table that have the same trigger event and
action time, an error occurs for attempts to load the dump
file into an older server that does not support multiple
triggers. (For a workaround, see
[Downgrade Notes](https://dev.mysql.com/doc/refman/5.7/en/downgrading-to-previous-series.html);
you can convert triggers to be compatible with older
servers.)


- [`--where='where_condition'`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_where),
`-w
              'where_condition'`




| Command-Line Format | `--where='where_condition'` |




Dump only rows selected by the given
`WHERE` condition. Quotes around the
condition are mandatory if it contains spaces or other
characters that are special to your command interpreter.





Examples:




``` terminal

  --where="user='jimf'"
  -w"userid>1"
  -w"userid<1"
```


#### Performance Options

The following options are the most relevant for the performance
particularly of the restore operations. For large data sets,
restore operation (processing the `INSERT`
statements in the dump file) is the most time-consuming part.
When it is urgent to restore data quickly, plan and test the
performance of this stage in advance. For restore times measured
in hours, you might prefer an alternative backup and restore
solution, such as
[MySQL Enterprise Backup](https://dev.mysql.com/doc/refman/8.0/en/mysql-enterprise-backup.html "32.1 MySQL Enterprise Backup Overview") for
`InnoDB`-only and mixed-use databases.




Performance is also affected by the
[transactional\\
options](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-transaction-options "Transactional Options"), primarily for the dump operation.

- [`--column-statistics`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_column-statistics)




| Command-Line Format | `--column-statistics` |
| Type | Boolean |
| Default Value | `OFF` |




Add [`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") statements
to the output to generate histogram statistics for dumped
tables when the dump file is reloaded. This option is
disabled by default because histogram generation for large
tables can take a long time.


- [`--disable-keys`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_disable-keys),
`-K`




| Command-Line Format | `--disable-keys` |




For each table, surround the
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements with
`/*!40000 ALTER TABLE
              tbl_name DISABLE KEYS
              */;` and `/*!40000 ALTER TABLE
              tbl_name ENABLE KEYS
              */;` statements. This makes loading the dump file
faster because the indexes are created after all rows are
inserted. This option is effective only for nonunique
indexes of `MyISAM` tables.


- [`--extended-insert`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_extended-insert),
`-e`




| Command-Line Format | `--extended-insert` |
| Disabled by | `skip-extended-insert` |




Write [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements using
multiple-row syntax that includes several
`VALUES` lists. This results in a smaller
dump file and speeds up inserts when the file is reloaded.


- [`--insert-ignore`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_insert-ignore)




| Command-Line Format | `--insert-ignore` |




Write [`INSERT\\
              IGNORE`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements rather than
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements.


- [`--max-allowed-packet=value`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_max-allowed-packet)




| Command-Line Format | `--max-allowed-packet=value` |
| Type | Numeric |
| Default Value | `25165824` |




The maximum size of the buffer for client/server
communication. The default is 24MB, the maximum is 1GB.





Note





The value of this option is specific to
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") and should not be confused
with the MySQL server's
[`max_allowed_packet`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_allowed_packet) system
variable; the server value cannot be exceeded by a single
packet from [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program"), regardless of
any setting for the [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") option,
even if the latter is larger.

- [`--mysqld-long-query-time=value`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_mysqld-long-query-time)




| Command-Line Format | `--mysqld-long-query-time=value` |
| Introduced | 8.0.30 |
| Type | Numeric |
| Default Value | `Server global setting` |




Set the session value of the
[`long_query_time`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_long_query_time) system
variable. Use this option, which is available from MySQL
8.0.30, if you want to increase the time allowed for queries
from [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") before they are logged to
the slow query log file. [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program")
performs a full table scan, which means its queries can
often exceed a global
[`long_query_time`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_long_query_time)
setting that is useful for regular queries. The default
global setting is 10 seconds.



You can use
[`--mysqld-long-query-time`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_mysqld-long-query-time)
to specify a session value from 0 (meaning that every query
from [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") is logged to the slow
query log) to 31536000, which is 365 days in seconds. For
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program")’s option, you can only
specify whole seconds. When you do not specify this option,
the server’s global setting applies to
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program")’s queries.


- [`--net-buffer-length=value`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_net-buffer-length)




| Command-Line Format | `--net-buffer-length=value` |
| Type | Numeric |
| Default Value | `16384` |




The initial size of the buffer for client/server
communication. When creating multiple-row
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements (as with
the [`--extended-insert`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_extended-insert) or
[`--opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt) option),
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") creates rows up to
[`--net-buffer-length`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_net-buffer-length) bytes
long. If you increase this variable, ensure that the MySQL
server [`net_buffer_length`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_net_buffer_length)
system variable has a value at least this large.


- [`--network-timeout`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_network-timeout),
`-M`




| Command-Line Format | `--network-timeout[={0|1}]` |
| Type | Boolean |
| Default Value | `TRUE` |




Enable large tables to be dumped by setting
[`--max-allowed-packet`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_max-allowed-packet) to
its maximum value and network read and write timeouts to a
large value. This option is enabled by default. To disable
it, use
[`--skip-network-timeout`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_network-timeout).


- [`--opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt)




| Command-Line Format | `--opt` |
| Disabled by | `skip-opt` |




This option, enabled by default, is shorthand for the
combination of
[`--add-drop-table`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-drop-table) [`--add-locks`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-locks) [`--create-options`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_create-options) [`--disable-keys`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_disable-keys) [`--extended-insert`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_extended-insert) [`--lock-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-tables) [`--quick`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quick) [`--set-charset`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_set-charset). It gives a
fast dump operation and produces a dump file that can be
reloaded into a MySQL server quickly.



Because the `--opt` option is enabled by
default, you only specify its converse, the
[`--skip-opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-opt) to turn off
several default settings. See the discussion of
[`mysqldump`\\
option groups](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#mysqldump-option-groups "Option Groups") for information about selectively
enabling or disabling a subset of the options affected by
`--opt`.


- [`--quick`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quick),
`-q`




| Command-Line Format | `--quick` |
| Disabled by | `skip-quick` |




This option is useful for dumping large tables. It forces
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") to retrieve rows for a table
from the server a row at a time rather than retrieving the
entire row set and buffering it in memory before writing it
out.


- [`--skip-opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-opt)




| Command-Line Format | `--skip-opt` |




See the description for the
[`--opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt) option.




#### Transactional Options

The following options trade off the performance of the dump
operation, against the reliability and consistency of the
exported data.



- [`--add-locks`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_add-locks)




| Command-Line Format | `--add-locks` |




Surround each table dump with [`LOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") and
[`UNLOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") statements. This results in faster inserts
when the dump file is reloaded. See
[Section 10.2.5.1, “Optimizing INSERT Statements”](https://dev.mysql.com/doc/refman/8.0/en/insert-optimization.html "10.2.5.1 Optimizing INSERT Statements").




- [`--flush-logs`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_flush-logs),
`-F`




| Command-Line Format | `--flush-logs` |




Flush the MySQL server log files before starting the dump.
This option requires the
[`RELOAD`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_reload) privilege. If you use
this option in combination with the
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-databases) option,
the logs are flushed _for each database_
_dumped_. The exception is when using
[`--lock-all-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-all-tables),
[`--source-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_source-data) or
[`--master-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_master-data), or
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction). In
these cases, the logs are flushed only once, corresponding
to the moment that all tables are locked by
[`FLUSH TABLES WITH READ LOCK`](https://dev.mysql.com/doc/refman/8.0/en/flush.html#flush-tables-with-read-lock).
If you want your dump and the log flush to happen at exactly
the same moment, you should use
`--flush-logs` together with
[`--lock-all-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-all-tables),
[`--source-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_source-data) or
[`--master-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_master-data), or
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction).


- [`--flush-privileges`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_flush-privileges)




| Command-Line Format | `--flush-privileges` |




Add a [`FLUSH PRIVILEGES`](https://dev.mysql.com/doc/refman/8.0/en/flush.html#flush-privileges)
statement to the dump output after dumping the
`mysql` database. This option should be
used any time the dump contains the `mysql`
database and any other database that depends on the data in
the `mysql` database for proper
restoration.



Because the dump file contains a [`FLUSH\\
              PRIVILEGES`](https://dev.mysql.com/doc/refman/8.0/en/flush.html#flush-privileges) statement, reloading the file requires
privileges sufficient to execute that statement.





Note





For upgrades to MySQL 5.7 or higher from older versions,
do not use `--flush-privileges`. For
upgrade instructions in this case, see
[Section 3.5, “Changes in MySQL 8.0”](https://dev.mysql.com/doc/refman/8.0/en/upgrading-from-previous-series.html "3.5 Changes in MySQL 8.0").

- [`--lock-all-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-all-tables),
`-x`




| Command-Line Format | `--lock-all-tables` |




Lock all tables across all databases. This is achieved by
acquiring a global read lock for the duration of the whole
dump. This option automatically turns off
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction) and
[`--lock-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-tables).


- [`--lock-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-tables),
`-l`




| Command-Line Format | `--lock-tables` |




For each dumped database, lock all tables to be dumped
before dumping them. The tables are locked with
`READ LOCAL` to permit concurrent inserts
in the case of `MyISAM` tables. For
transactional tables such as `InnoDB`,
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction) is a
much better option than `--lock-tables`
because it does not need to lock the tables at all.



Because `--lock-tables` locks tables for each
database separately, this option does not guarantee that the
tables in the dump file are logically consistent between
databases. Tables in different databases may be dumped in
completely different states.



Some options, such as
[`--opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt), automatically
enable `--lock-tables`. If you want to
override this, use `--skip-lock-tables` at
the end of the option list.


- [`--no-autocommit`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_no-autocommit)




| Command-Line Format | `--no-autocommit` |




Enclose the [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements
for each dumped table within `SET autocommit =
              0` and [`COMMIT`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements")
statements.


- [`--order-by-primary`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_order-by-primary)




| Command-Line Format | `--order-by-primary` |






Dump each table's rows sorted by its primary key, or by its
first unique index, if such an index exists. This is useful
when dumping a `MyISAM` table to be loaded
into an `InnoDB` table, but makes the dump
operation take considerably longer.


- [`--shared-memory-base-name=name`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_shared-memory-base-name)




| Command-Line Format | `--shared-memory-base-name=name` |
| Platform Specific | Windows |




On Windows, the shared-memory name to use for connections
made using shared memory to a local server. The default
value is `MYSQL`. The shared-memory name is
case-sensitive.



This option applies only if the server was started with the
[`shared_memory`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_shared_memory) system
variable enabled to support shared-memory connections.


- [`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction)




| Command-Line Format | `--single-transaction` |




This option sets the transaction isolation mode to
[`REPEATABLE READ`](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html#isolevel_repeatable-read) and sends
a [`START\\
              TRANSACTION`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements") SQL statement to the server before
dumping data. It is useful only with transactional tables
such as `InnoDB`, because then it dumps the
consistent state of the database at the time when
[`START\\
              TRANSACTION`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements") was issued without blocking any
applications.



The [`RELOAD`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_reload) or
[`FLUSH_TABLES`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_flush-tables) privilege is
required with
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction) if
both [`gtid_mode=ON`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_mode) and
[`gtid_purged=ON|AUTO`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-gtids.html#sysvar_gtid_purged). This
requirement was added in MySQL 8.0.32.



When using this option, you should keep in mind that only
`InnoDB` tables are dumped in a consistent
state. For example, any `MyISAM` or
`MEMORY` tables dumped while using this
option may still change state.



While a
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction) dump
is in process, to ensure a valid dump file (correct table
contents and binary log coordinates), no other connection
should use the following statements:
[`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement"),
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"),
[`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement"),
[`RENAME TABLE`](https://dev.mysql.com/doc/refman/8.0/en/rename-table.html "15.1.36 RENAME TABLE Statement"),
[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement"). A consistent
read is not isolated from those statements, so use of them
on a table to be dumped can cause the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") that is performed by
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") to retrieve the table contents
to obtain incorrect contents or fail.



The `--single-transaction` option and the
[`--lock-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-tables) option are
mutually exclusive because [`LOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") causes any pending transactions to be
committed implicitly.



Before 8.0.32: Using `--single-transaction`
together with the
[`--set-gtid-purged`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_set-gtid-purged) option
was not recommended; doing so could lead to inconsistencies
in the output of [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program").



To dump large tables, combine the
`--single-transaction` option with the
[`--quick`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quick) option.


#### Option Groups

- The [`--opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt) option turns on
several settings that work together to perform a fast dump
operation. All of these settings are on by default, because
`--opt` is on by default. Thus you rarely if
ever specify `--opt`. Instead, you can turn
these settings off as a group by specifying
`--skip-opt`, then optionally re-enable
certain settings by specifying the associated options later
on the command line.


- The [`--compact`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_compact) option turns
off several settings that control whether optional
statements and comments appear in the output. Again, you can
follow this option with other options that re-enable certain
settings, or turn all the settings on by using the
`--skip-compact` form.


When you selectively enable or disable the effect of a group
option, order is important because options are processed first
to last. For example,
[`--disable-keys`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_disable-keys) [`--lock-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-tables) [`--skip-opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-opt) would not have the
intended effect; it is the same as
[`--skip-opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-opt) by itself.

#### Examples

To make a backup of an entire database:


``` terminal

mysqldump db_name > backup-file.sql
```

To load the dump file back into the server:


``` terminal

mysql db_name < backup-file.sql
```

Another way to reload the dump file:


``` terminal

mysql -e "source /path-to-backup/backup-file.sql" db_name
```

[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") is also very useful for populating
databases by copying data from one MySQL server to another:


``` terminal

mysqldump --opt db_name | mysql --host=remote_host -C db_name
```

You can dump several databases with one command:


``` terminal

mysqldump --databases db_name1 [db_name2 ...] > my_databases.sql
```

To dump all databases, use the
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_all-databases) option:


``` terminal

mysqldump --all-databases > all_databases.sql
```

For `InnoDB` tables,
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") provides a way of making an online
backup:


``` terminal

mysqldump --all-databases --master-data --single-transaction > all_databases.sql
```

Or, in MySQL 8.0.26 and later:


``` terminal

mysqldump --all-databases --source-data --single-transaction > all_databases.sql
```

This backup acquires a global read lock on all tables (using
[`FLUSH TABLES WITH READ LOCK`](https://dev.mysql.com/doc/refman/8.0/en/flush.html#flush-tables-with-read-lock)) at
the beginning of the dump. As soon as this lock has been
acquired, the binary log coordinates are read and the lock is
released. If long updating statements are running when the
[`FLUSH`](https://dev.mysql.com/doc/refman/8.0/en/flush.html "15.7.8.3 FLUSH Statement") statement is issued, the
MySQL server may get stalled until those statements finish.
After that, the dump becomes lock free and does not disturb
reads and writes on the tables. If the update statements that
the MySQL server receives are short (in terms of execution
time), the initial lock period should not be noticeable, even
with many updates.


For point-in-time recovery (also known as
“roll-forward,” when you need to restore an old
backup and replay the changes that happened since that backup),
it is often useful to rotate the binary log (see
[Section 7.4.4, “The Binary Log”](https://dev.mysql.com/doc/refman/8.0/en/binary-log.html "7.4.4 The Binary Log")) or at least know the binary log
coordinates to which the dump corresponds:


``` terminal

mysqldump --all-databases --master-data=2 > all_databases.sql
```

Or, in MySQL 8.0.26 and later:


``` terminal

mysqldump --all-databases --source-data=2 > all_databases.sql
```

Or:


``` terminal

mysqldump --all-databases --flush-logs --master-data=2 > all_databases.sql
```

Or, in MySQL 8.0.26 and later:


``` terminal

mysqldump --all-databases --flush-logs --source-data=2 > all_databases.sql
```

The [`--source-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_source-data) or
[`--master-data`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_master-data) option can be
used simultaneously with the
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_single-transaction) option,
which provides a convenient way to make an online backup
suitable for use prior to point-in-time recovery if tables are
stored using the `InnoDB` storage engine.


For more information on making backups, see
[Section 9.2, “Database Backup Methods”](https://dev.mysql.com/doc/refman/8.0/en/backup-methods.html "9.2 Database Backup Methods"), and
[Section 9.3, “Example Backup and Recovery Strategy”](https://dev.mysql.com/doc/refman/8.0/en/backup-strategy-example.html "9.3 Example Backup and Recovery Strategy").

- To select the effect of
[`--opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt) except for some
features, use the `--skip` option for each
feature. To disable extended inserts and memory buffering,
use [`--opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt) [`--skip-extended-insert`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_extended-insert) [`--skip-quick`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quick).
(Actually,
[`--skip-extended-insert`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_extended-insert) [`--skip-quick`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_quick)
is sufficient because
[`--opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt) is on by default.)


-

To reverse [`--opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_opt) for all
features except disabling of indexes and table locking, use
[`--skip-opt`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_skip-opt) [`--disable-keys`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_disable-keys) [`--lock-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-tables).


#### Restrictions

[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") does not dump the
`performance_schema` or `sys`
schema by default. To dump any of these, name them explicitly on
the command line. You can also name them with the
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_databases) option. For
`performance_schema`, also use the
[`--skip-lock-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html#option_mysqldump_lock-tables)
option.


[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") does not dump the
`INFORMATION_SCHEMA` schema.


[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") does not dump
`InnoDB` [`CREATE\\
        TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/create-tablespace.html "15.1.21 CREATE TABLESPACE Statement") statements.


[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") does not dump the NDB Cluster
[`ndbinfo`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster-ndbinfo.html "25.6.16 ndbinfo: The NDB Cluster Information Database") information database.


[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") includes statements to recreate the
`general_log` and
`slow_query_log` tables for dumps of the
`mysql` database. Log table contents are not
dumped.


If you encounter problems backing up views due to insufficient
privileges, see [Section 27.9, “Restrictions on Views”](https://dev.mysql.com/doc/refman/8.0/en/view-restrictions.html "27.9 Restrictions on Views") for a
workaround.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/mysqlcheck.html "Previous: mysqlcheck — A Table Maintenance Program") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/programs-client.html "Up: Client Programs") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/mysqlimport.html "Next: mysqlimport — A Data Import Program")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html)

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