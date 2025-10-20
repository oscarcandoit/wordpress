---
url: https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html
scraped_at: 2025-10-20T03:03:34.777Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "Hide Sidebar")

[Previous: mysqlimport — A Data Import Program](https://dev.mysql.com/doc/refman/8.0/en/mysqlimport.html "Previous: mysqlimport — A Data Import Program")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Client Programs](https://dev.mysql.com/doc/refman/8.0/en/programs-client.html "Up: Client Programs")[Next: mysqlshow — Display Database, Table, and Column Information](https://dev.mysql.com/doc/refman/8.0/en/mysqlshow.html "Next: mysqlshow — Display Database, Table, and Column Information")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/mysqlpump.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/mysqlpump.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html)  / [MySQL Programs](https://dev.mysql.com/doc/refman/8.0/en/programs.html)  /
[Client Programs](https://dev.mysql.com/doc/refman/8.0/en/programs-client.html)  /

mysqlpump — A Database Backup Program


### 6.5.6 mysqlpump — A Database Backup Program

- [mysqlpump Invocation Syntax](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-syntax "mysqlpump Invocation Syntax")

- [mysqlpump Option Summary](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-option-summary "mysqlpump Option Summary")

- [mysqlpump Option Descriptions](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-options "mysqlpump Option Descriptions")

- [mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection")

- [mysqlpump Parallel Processing](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-parallelism "mysqlpump Parallel Processing")

- [mysqlpump Restrictions](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-restrictions "mysqlpump Restrictions")


The [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") client utility performs
[logical backups](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_logical_backup "logical backup"),
producing a set of SQL statements that can be executed to
reproduce the original database object definitions and table
data. It dumps one or more MySQL databases for backup or
transfer to another SQL server.

Note

[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") is deprecated as of MySQL 8.0.34;
expect it to be removed in a future version of MySQL. You can
use such MySQL programs as [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") and
MySQL Shell to perform logical backups, dump databases, and
similar tasks instead.

Tip

Consider using the [MySQL Shell dump utilities](https://dev.mysql.com/doc/mysql-shell/8.0/en/mysql-shell-utilities-dump-instance-schema.html), which provide parallel dumping with multiple threads, file compression, and progress information display, as well as cloud features such as Oracle Cloud Infrastructure Object Storage streaming, and MySQL HeatWave compatibility checks and modifications. Dumps can be easily imported into a MySQL Server instance or a MySQL HeatWave DB System using the [MySQL Shell load dump utilities](https://dev.mysql.com/doc/mysql-shell/8.0/en/mysql-shell-utilities-load-dump.html). Installation instructions for MySQL Shell can be found [here](https://dev.mysql.com/doc/mysql-shell/8.0/en/mysql-shell-install.html).

[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") features include:

- Parallel processing of databases, and of objects within
databases, to speed up the dump process


- Better control over which databases and database objects
(tables, stored programs, user accounts) to dump


- Dumping of user accounts as account-management statements
( [`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement"),
[`GRANT`](https://dev.mysql.com/doc/refman/8.0/en/grant.html "15.7.1.6 GRANT Statement")) rather than as inserts
into the `mysql` system database


- Capability of creating compressed output


- Progress indicator (the values are estimates)


- For dump file reloading, faster secondary index creation for
`InnoDB` tables by adding indexes after
rows are inserted


Note

[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") uses MySQL features introduced in
MySQL 5.7, and thus assumes use with MySQL 5.7 or higher.

[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") requires at least the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege for dumped
tables, [`SHOW VIEW`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_show-view) for dumped
views, [`TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_trigger) for dumped
triggers, and [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_lock-tables) if the
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_single-transaction) option is
not used. The [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege on
the `mysql` system database is required to dump
user definitions. Certain options might require other privileges
as noted in the option descriptions.


To reload a dump file, you must have the privileges required to
execute the statements that it contains, such as the appropriate
`CREATE` privileges for objects created by
those statements.

Note

A dump made using PowerShell on Windows with output
redirection creates a file that has UTF-16 encoding:


``` terminal

mysqlpump [options] > dump.sql
```

However, UTF-16 is not permitted as a connection character set
(see [Section 12.4, “Connection Character Sets and Collations”](https://dev.mysql.com/doc/refman/8.0/en/charset-connection.html "12.4 Connection Character Sets and Collations")), so the dump file
cannot be loaded correctly. To work around this issue, use the
`--result-file` option, which creates the
output in ASCII format:


``` terminal

mysqlpump [options] --result-file=dump.sql
```

#### mysqlpump Invocation Syntax

By default, [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") dumps all databases
(with certain exceptions noted in
[mysqlpump Restrictions](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-restrictions "mysqlpump Restrictions")). To specify this
behavior explicitly, use the
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_all-databases) option:


``` terminal

mysqlpump --all-databases
```

To dump a single database, or certain tables within that
database, name the database on the command line, optionally
followed by table names:


``` terminal

mysqlpump db_name
mysqlpump db_name tbl_name1 tbl_name2 ...
```

To treat all name arguments as database names, use the
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_databases) option:


``` terminal

mysqlpump --databases db_name1 db_name2 ...
```

By default, [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") does not dump user
account definitions, even if you dump the
`mysql` system database that contains the grant
tables. To dump grant table contents as logical definitions in
the form of [`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") and
[`GRANT`](https://dev.mysql.com/doc/refman/8.0/en/grant.html "15.7.1.6 GRANT Statement") statements, use the
[`--users`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_users) option and suppress
all database dumping:


``` terminal

mysqlpump --exclude-databases=% --users
```

In the preceding command, `%` is a wildcard
that matches all database names for the
[`--exclude-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-databases) option.


[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") supports several options for
including or excluding databases, tables, stored programs, and
user definitions. See [mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


To reload a dump file, execute the statements that it contains.
For example, use the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client:


``` terminal

mysqlpump [options] > dump.sql
mysql < dump.sql
```

The following discussion provides additional
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") usage examples.


To see a list of the options [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program")
supports, issue the command [**mysqlpump --help**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program").

#### mysqlpump Option Summary

[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") supports the following options,
which can be specified on the command line or in the
`[mysqlpump]` and `[client]`
groups of an option file. (Prior to MySQL 8.0.20,
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") read the
`[mysql_dump]` group rather than
`[mysqlpump]`. As of 8.0.20,
`[mysql_dump]` is still accepted but is
deprecated.) For information about option files used by MySQL
programs, see [Section 6.2.2.2, “Using Option Files”](https://dev.mysql.com/doc/refman/8.0/en/option-files.html "6.2.2.2 Using Option Files").

**Table 6.17 mysqlpump Options**

| Option Name | Description | Introduced | Deprecated |
| --- | --- | --- | --- |
| [--add-drop-database](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-drop-database) | Add DROP DATABASE statement before each CREATE DATABASE statement |  |  |
| [--add-drop-table](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-drop-table) | Add DROP TABLE statement before each CREATE TABLE statement |  |  |
| [--add-drop-user](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-drop-user) | Add DROP USER statement before each CREATE USER statement |  |  |
| [--add-locks](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-locks) | Surround each table dump with LOCK TABLES and UNLOCK TABLES statements |  |  |
| [--all-databases](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_all-databases) | Dump all databases |  |  |
| [--bind-address](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_bind-address) | Use specified network interface to connect to MySQL Server |  |  |
| [--character-sets-dir](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_character-sets-dir) | Directory where character sets are installed |  |  |
| [--column-statistics](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_column-statistics) | Write ANALYZE TABLE statements to generate statistics histograms |  |  |
| [--complete-insert](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_complete-insert) | Use complete INSERT statements that include column names |  |  |
| [--compress](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_compress) | Compress all information sent between client and server |  | 8.0.18 |
| [--compress-output](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_compress-output) | Output compression algorithm |  |  |
| [--compression-algorithms](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_compression-algorithms) | Permitted compression algorithms for connections to server | 8.0.18 |  |
| [--databases](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_databases) | Interpret all name arguments as database names |  |  |
| [--debug](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_debug) | Write debugging log |  |  |
| [--debug-check](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_debug-check) | Print debugging information when program exits |  |  |
| [--debug-info](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_debug-info) | Print debugging information, memory, and CPU statistics when program exits |  |  |
| [--default-auth](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_default-auth) | Authentication plugin to use |  |  |
| [--default-character-set](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_default-character-set) | Specify default character set |  |  |
| [--default-parallelism](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_default-parallelism) | Default number of threads for parallel processing |  |  |
| [--defaults-extra-file](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_defaults-extra-file) | Read named option file in addition to usual option files |  |  |
| [--defaults-file](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_defaults-file) | Read only named option file |  |  |
| [--defaults-group-suffix](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_defaults-group-suffix) | Option group suffix value |  |  |
| [--defer-table-indexes](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_defer-table-indexes) | For reloading, defer index creation until after loading table rows |  |  |
| [--events](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_events) | Dump events from dumped databases |  |  |
| [--exclude-databases](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-databases) | Databases to exclude from dump |  |  |
| [--exclude-events](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-events) | Events to exclude from dump |  |  |
| [--exclude-routines](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-routines) | Routines to exclude from dump |  |  |
| [--exclude-tables](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-tables) | Tables to exclude from dump |  |  |
| [--exclude-triggers](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-triggers) | Triggers to exclude from dump |  |  |
| [--exclude-users](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-users) | Users to exclude from dump |  |  |
| [--extended-insert](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_extended-insert) | Use multiple-row INSERT syntax |  |  |
| [--get-server-public-key](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_get-server-public-key) | Request RSA public key from server |  |  |
| [--help](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_help) | Display help message and exit |  |  |
| [--hex-blob](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_hex-blob) | Dump binary columns using hexadecimal notation |  |  |
| [--host](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_host) | Host on which MySQL server is located |  |  |
| [--include-databases](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-databases) | Databases to include in dump |  |  |
| [--include-events](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-events) | Events to include in dump |  |  |
| [--include-routines](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-routines) | Routines to include in dump |  |  |
| [--include-tables](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-tables) | Tables to include in dump |  |  |
| [--include-triggers](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-triggers) | Triggers to include in dump |  |  |
| [--include-users](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-users) | Users to include in dump |  |  |
| [--insert-ignore](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_insert-ignore) | Write INSERT IGNORE rather than INSERT statements |  |  |
| [--log-error-file](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_log-error-file) | Append warnings and errors to named file |  |  |
| [--login-path](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_login-path) | Read login path options from .mylogin.cnf |  |  |
| [--max-allowed-packet](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_max-allowed-packet) | Maximum packet length to send to or receive from server |  |  |
| [--net-buffer-length](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_net-buffer-length) | Buffer size for TCP/IP and socket communication |  |  |
| [--no-create-db](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_no-create-db) | Do not write CREATE DATABASE statements |  |  |
| [--no-create-info](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_no-create-info) | Do not write CREATE TABLE statements that re-create each dumped table |  |  |
| [--no-defaults](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_no-defaults) | Read no option files |  |  |
| [--parallel-schemas](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_parallel-schemas) | Specify schema-processing parallelism |  |  |
| [--password](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password) | Password to use when connecting to server |  |  |
| [--password1](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password1) | First multifactor authentication password to use when connecting to server | 8.0.27 |  |
| [--password2](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password2) | Second multifactor authentication password to use when connecting to server | 8.0.27 |  |
| [--password3](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password3) | Third multifactor authentication password to use when connecting to server | 8.0.27 |  |
| [--plugin-dir](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_plugin-dir) | Directory where plugins are installed |  |  |
| [--port](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_port) | TCP/IP port number for connection |  |  |
| [--print-defaults](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_print-defaults) | Print default options |  |  |
| [--protocol](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_protocol) | Transport protocol to use |  |  |
| [--replace](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_replace) | Write REPLACE statements rather than INSERT statements |  |  |
| [--result-file](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_result-file) | Direct output to a given file |  |  |
| [--routines](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_routines) | Dump stored routines (procedures and functions) from dumped databases |  |  |
| [--server-public-key-path](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_server-public-key-path) | Path name to file containing RSA public key |  |  |
| [--set-charset](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_set-charset) | Add SET NAMES default\_character\_set to output |  |  |
| [--set-gtid-purged](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_set-gtid-purged) | Whether to add SET @@GLOBAL.GTID\_PURGED to output |  |  |
| [--single-transaction](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_single-transaction) | Dump tables within single transaction |  |  |
| [--skip-definer](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_skip-definer) | Omit DEFINER and SQL SECURITY clauses from view and stored program CREATE statements |  |  |
| [--skip-dump-rows](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_skip-dump-rows) | Do not dump table rows |  |  |
| [--skip-generated-invisible-primary-key](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_skip-generated-invisible-primary-key) | Do not dump information about generated invisible primary keys | 8.0.30 |  |
| [--socket](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_socket) | Unix socket file or Windows named pipe to use |  |  |
| [--ssl-ca](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl) | File that contains list of trusted SSL Certificate Authorities |  |  |
| [--ssl-capath](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl) | Directory that contains trusted SSL Certificate Authority certificate files |  |  |
| [--ssl-cert](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl) | File that contains X.509 certificate |  |  |
| [--ssl-cipher](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl) | Permissible ciphers for connection encryption |  |  |
| [--ssl-crl](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl) | File that contains certificate revocation lists |  |  |
| [--ssl-crlpath](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl) | Directory that contains certificate revocation-list files |  |  |
| [--ssl-fips-mode](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl-fips-mode) | Whether to enable FIPS mode on client side |  | 8.0.34 |
| [--ssl-key](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl) | File that contains X.509 key |  |  |
| [--ssl-mode](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl) | Desired security state of connection to server |  |  |
| [--ssl-session-data](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl) | File that contains SSL session data | 8.0.29 |  |
| [--ssl-session-data-continue-on-failed-reuse](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl) | Whether to establish connections if session reuse fails | 8.0.29 |  |
| [--tls-ciphersuites](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_tls-ciphersuites) | Permissible TLSv1.3 ciphersuites for encrypted connections | 8.0.16 |  |
| [--tls-version](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_tls-version) | Permissible TLS protocols for encrypted connections |  |  |
| [--triggers](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_triggers) | Dump triggers for each dumped table |  |  |
| [--tz-utc](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_tz-utc) | Add SET TIME\_ZONE='+00:00' to dump file |  |  |
| [--user](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_user) | MySQL user name to use when connecting to server |  |  |
| [--users](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_users) | Dump user accounts |  |  |
| [--version](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_version) | Display version information and exit |  |  |
| [--watch-progress](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_watch-progress) | Display progress indicator |  |  |
| [--zstd-compression-level](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_zstd-compression-level) | Compression level for connections to server that use zstd compression | 8.0.18 |  |

| Option Name | Description | Introduced | Deprecated |
| --- | --- | --- | --- |

#### mysqlpump Option Descriptions

- [`--help`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_help),
`-?`




| Command-Line Format | `--help` |




Display a help message and exit.


- [`--add-drop-database`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-drop-database)




| Command-Line Format | `--add-drop-database` |




Write a [`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement")
statement before each [`CREATE\\
              DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "15.1.12 CREATE DATABASE Statement") statement.





Note





In MySQL 8.0, the `mysql`
schema is considered a system schema that cannot be
dropped by end users. If
[`--add-drop-database`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-drop-database) is
used with
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_all-databases) or with
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_databases) where the
list of schemas to be dumped includes
`mysql`, the dump file contains a
``DROP DATABASE `mysql` `` statement that
causes an error when the dump file is reloaded.





Instead, to use
[`--add-drop-database`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-drop-database), use
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_databases) with a list
of schemas to be dumped, where the list does not include
`mysql`.

- [`--add-drop-table`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-drop-table)




| Command-Line Format | `--add-drop-table` |




Write a [`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") statement
before each [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement")
statement.


- [`--add-drop-user`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-drop-user)




| Command-Line Format | `--add-drop-user` |




Write a [`DROP USER`](https://dev.mysql.com/doc/refman/8.0/en/drop-user.html "15.7.1.5 DROP USER Statement") statement
before each [`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement")
statement.


- [`--add-locks`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-locks)




| Command-Line Format | `--add-locks` |




Surround each table dump with [`LOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") and
[`UNLOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") statements. This results in faster inserts
when the dump file is reloaded. See
[Section 10.2.5.1, “Optimizing INSERT Statements”](https://dev.mysql.com/doc/refman/8.0/en/insert-optimization.html "10.2.5.1 Optimizing INSERT Statements").



This option does not work with parallelism because
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements from
different tables can be interleaved and
[`UNLOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") following the end of the inserts for one
table could release locks on tables for which inserts
remain.


[`--add-locks`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-locks) and
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_single-transaction) are
mutually exclusive.


- [`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_all-databases),
`-A`




| Command-Line Format | `--all-databases` |




Dump all databases (with certain exceptions noted in
[mysqlpump Restrictions](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-restrictions "mysqlpump Restrictions")). This is the
default behavior if no other is specified explicitly.


[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_all-databases) and
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_databases) are mutually
exclusive.





Note





See the
[`--add-drop-database`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-drop-database)
description for information about an incompatibility of
that option with
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_all-databases).





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


- [`--bind-address=ip_address`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_bind-address)




| Command-Line Format | `--bind-address=ip_address` |




On a computer having multiple network interfaces, use this
option to select which interface to use for connecting to
the MySQL server.


- [`--character-sets-dir=path`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_character-sets-dir)




| Command-Line Format | `--character-sets-dir=dir_name` |
| Type | Directory name |




The directory where character sets are installed. See
[Section 12.15, “Character Set Configuration”](https://dev.mysql.com/doc/refman/8.0/en/charset-configuration.html "12.15 Character Set Configuration").


- [`--column-statistics`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_column-statistics)




| Command-Line Format | `--column-statistics` |
| Type | Boolean |
| Default Value | `OFF` |




Add [`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") statements
to the output to generate histogram statistics for dumped
tables when the dump file is reloaded. This option is
disabled by default because histogram generation for large
tables can take a long time.


- [`--complete-insert`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_complete-insert)




| Command-Line Format | `--complete-insert` |




Write complete [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement")
statements that include column names.


- [`--compress`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_compress),
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


- [`--compress-output=algorithm`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_compress-output)




| Command-Line Format | `--compress-output=algorithm` |
| Type | Enumeration |
| Valid Values | `LZ4`<br>`ZLIB` |




By default, [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") does not compress
output. This option specifies output compression using the
specified algorithm. Permitted algorithms are
`LZ4` and `ZLIB`.



To uncompress compressed output, you must have an
appropriate utility. If the system commands
**lz4** and **openssl zlib**
are not available, MySQL distributions include
[**lz4\_decompress**](https://dev.mysql.com/doc/refman/8.0/en/lz4-decompress.html "6.8.1 lz4_decompress — Decompress mysqlpump LZ4-Compressed Output") and
[**zlib\_decompress**](https://dev.mysql.com/doc/refman/8.0/en/zlib-decompress.html "6.8.3 zlib_decompress — Decompress mysqlpump ZLIB-Compressed Output") utilities that can be
used to decompress [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") output that
was compressed using the
[`--compress-output=LZ4`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_compress-output) and
[`--compress-output=ZLIB`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_compress-output)
options. For more information, see
[Section 6.8.1, “lz4\_decompress — Decompress mysqlpump LZ4-Compressed Output”](https://dev.mysql.com/doc/refman/8.0/en/lz4-decompress.html "6.8.1 lz4_decompress — Decompress mysqlpump LZ4-Compressed Output"), and
[Section 6.8.3, “zlib\_decompress — Decompress mysqlpump ZLIB-Compressed Output”](https://dev.mysql.com/doc/refman/8.0/en/zlib-decompress.html "6.8.3 zlib_decompress — Decompress mysqlpump ZLIB-Compressed Output").


- [`--compression-algorithms=value`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_compression-algorithms)




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


- [`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_databases),
`-B`




| Command-Line Format | `--databases` |




Normally, [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") treats the first name
argument on the command line as a database name and any
following names as table names. With this option, it treats
all name arguments as database names.
[`CREATE DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "15.1.12 CREATE DATABASE Statement") statements
are included in the output before each new database.


[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_all-databases) and
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_databases) are mutually
exclusive.





Note





See the
[`--add-drop-database`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-drop-database)
description for information about an incompatibility of
that option with
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_databases).

- [`--debug[=debug_options]`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_debug),
`-#
              [debug_options]`




| Command-Line Format | `--debug[=debug_options]` |
| Type | String |
| Default Value | `d:t:O,/tmp/mysqlpump.trace` |




Write a debugging log. A typical
_`debug_options`_ string is
`d:t:o,file_name`.
The default is
`d:t:O,/tmp/mysqlpump.trace`.



This option is available only if MySQL was built using
[`WITH_DEBUG`](https://dev.mysql.com/doc/refman/8.0/en/source-configuration-options.html#option_cmake_with_debug). MySQL release
binaries provided by Oracle are _not_
built using this option.


- [`--debug-check`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_debug-check)




| Command-Line Format | `--debug-check` |
| Type | Boolean |
| Default Value | `FALSE` |




Print some debugging information when the program exits.



This option is available only if MySQL was built using
[`WITH_DEBUG`](https://dev.mysql.com/doc/refman/8.0/en/source-configuration-options.html#option_cmake_with_debug). MySQL release
binaries provided by Oracle are _not_
built using this option.


- [`--debug-info`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_debug-info),
`-T`




| Command-Line Format | `--debug-info` |
| Type | Boolean |
| Default Value | `FALSE` |




Print debugging information and memory and CPU usage
statistics when the program exits.



This option is available only if MySQL was built using
[`WITH_DEBUG`](https://dev.mysql.com/doc/refman/8.0/en/source-configuration-options.html#option_cmake_with_debug). MySQL release
binaries provided by Oracle are _not_
built using this option.


- [`--default-auth=plugin`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_default-auth)




| Command-Line Format | `--default-auth=plugin` |
| Type | String |




A hint about which client-side authentication plugin to use.
See [Section 8.2.17, “Pluggable Authentication”](https://dev.mysql.com/doc/refman/8.0/en/pluggable-authentication.html "8.2.17 Pluggable Authentication").


- [`--default-character-set=charset_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_default-character-set)




| Command-Line Format | `--default-character-set=charset_name` |
| Type | String |
| Default Value | `utf8` |




Use _`charset_name`_ as the default
character set. See [Section 12.15, “Character Set Configuration”](https://dev.mysql.com/doc/refman/8.0/en/charset-configuration.html "12.15 Character Set Configuration").
If no character set is specified,
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") uses
`utf8mb4`.


- [`--default-parallelism=N`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_default-parallelism)




| Command-Line Format | `--default-parallelism=N` |
| Type | Integer |
| Default Value | `2` |




The default number of threads for each parallel processing
queue. The default is 2.



The [`--parallel-schemas`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_parallel-schemas)
option also affects parallelism and can be used to override
the default number of threads. For more information, see
[mysqlpump Parallel Processing](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-parallelism "mysqlpump Parallel Processing").



With
[`--default-parallelism=0`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_default-parallelism)
and no [`--parallel-schemas`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_parallel-schemas)
options, [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") runs as a
single-threaded process and creates no queues.



With parallelism enabled, it is possible for output from
different databases to be interleaved.


- [`--defaults-extra-file=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_defaults-extra-file)




| Command-Line Format | `--defaults-extra-file=file_name` |
| Type | File name |




Read this option file after the global option file but (on
Unix) before the user option file. If the file does not
exist or is otherwise inaccessible, an error occurs. If
_`file_name`_ is not an absolute path
name, it is interpreted relative to the current directory.



For additional information about this and other option-file
options, see [Section 6.2.2.3, “Command-Line Options that Affect Option-File Handling”](https://dev.mysql.com/doc/refman/8.0/en/option-file-options.html "6.2.2.3 Command-Line Options that Affect Option-File Handling").


- [`--defaults-file=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_defaults-file)




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


- [`--defaults-group-suffix=str`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_defaults-group-suffix)




| Command-Line Format | `--defaults-group-suffix=str` |
| Type | String |




Read not only the usual option groups, but also groups with
the usual names and a suffix of
_`str`_. For example,
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") normally reads the
`[client]` and
`[mysqlpump]` groups. If this option is
given as
[`--defaults-group-suffix=_other`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_defaults-group-suffix),
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") also reads the
`[client_other]` and
`[mysqlpump_other]` groups.



For additional information about this and other option-file
options, see [Section 6.2.2.3, “Command-Line Options that Affect Option-File Handling”](https://dev.mysql.com/doc/refman/8.0/en/option-file-options.html "6.2.2.3 Command-Line Options that Affect Option-File Handling").


- [`--defer-table-indexes`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_defer-table-indexes)




| Command-Line Format | `--defer-table-indexes` |
| Type | Boolean |
| Default Value | `TRUE` |




In the dump output, defer index creation for each table
until after its rows have been loaded. This works for all
storage engines, but for `InnoDB` applies
only for secondary indexes.



This option is enabled by default; use
[`--skip-defer-table-indexes`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_defer-table-indexes)
to disable it.


- [`--events`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_events)




| Command-Line Format | `--events` |
| Type | Boolean |
| Default Value | `TRUE` |




Include Event Scheduler events for the dumped databases in
the output. Event dumping requires the
[`EVENT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_event) privileges for those
databases.



The output generated by using
[`--events`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_events) contains
[`CREATE EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement") statements to
create the events.



This option is enabled by default; use
[`--skip-events`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_events)
to disable it.


- [`--exclude-databases=db_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-databases)




| Command-Line Format | `--exclude-databases=db_list` |
| Type | String |




Do not dump the databases in
_`db_list`_, which is a list of one
or more comma-separated database names. Multiple instances
of this option are additive. For more information, see
[mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


- [`--exclude-events=event_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-events)




| Command-Line Format | `--exclude-events=event_list` |
| Type | String |




Do not dump the databases in
_`event_list`_, which is a list of
one or more comma-separated event names. Multiple instances
of this option are additive. For more information, see
[mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


- [`--exclude-routines=routine_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-routines)




| Command-Line Format | `--exclude-routines=routine_list` |
| Type | String |




Do not dump the events in
_`routine_list`_, which is a list of
one or more comma-separated routine (stored procedure or
function) names. Multiple instances of this option are
additive. For more information, see
[mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


- [`--exclude-tables=table_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-tables)




| Command-Line Format | `--exclude-tables=table_list` |
| Type | String |




Do not dump the tables in
_`table_list`_, which is a list of
one or more comma-separated table names. Multiple instances
of this option are additive. For more information, see
[mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


- [`--exclude-triggers=trigger_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-triggers)




| Command-Line Format | `--exclude-triggers=trigger_list` |
| Type | String |




Do not dump the triggers in
_`trigger_list`_, which is a list of
one or more comma-separated trigger names. Multiple
instances of this option are additive. For more information,
see [mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


- [`--exclude-users=user_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-users)




| Command-Line Format | `--exclude-users=user_list` |
| Type | String |




Do not dump the user accounts in
_`user_list`_, which is a list of one
or more comma-separated account names. Multiple instances of
this option are additive. For more information, see
[mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


- [`--extended-insert=N`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_extended-insert)




| Command-Line Format | `--extended-insert=N` |




Write [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements using
multiple-row syntax that includes several
`VALUES` lists. This results in a smaller
dump file and speeds up inserts when the file is reloaded.



The option value indicates the number of rows to include in
each [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement. The
default is 250. A value of 1 produces one
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement per table
row.


- [`--get-server-public-key`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_get-server-public-key)




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
[`--server-public-key-path=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_server-public-key-path)
is given and specifies a valid public key file, it takes
precedence over
[`--get-server-public-key`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_get-server-public-key).



For information about the
`caching_sha2_password` plugin, see
[Section 8.4.1.2, “Caching SHA-2 Pluggable Authentication”](https://dev.mysql.com/doc/refman/8.0/en/caching-sha2-pluggable-authentication.html "8.4.1.2 Caching SHA-2 Pluggable Authentication").


- [`--hex-blob`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_hex-blob)




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


- [`--host=host_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_host),
`-h host_name`




| Command-Line Format | `--host` |




Dump data from the MySQL server on the given host.


- [`--include-databases=db_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-databases)




| Command-Line Format | `--include-databases=db_list` |
| Type | String |




Dump the databases in _`db_list`_,
which is a list of one or more comma-separated database
names. The dump includes all objects in the named databases.
Multiple instances of this option are additive. For more
information, see [mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


- [`--include-events=event_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-events)




| Command-Line Format | `--include-events=event_list` |
| Type | String |




Dump the events in _`event_list`_,
which is a list of one or more comma-separated event names.
Multiple instances of this option are additive. For more
information, see [mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


- [`--include-routines=routine_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-routines)




| Command-Line Format | `--include-routines=routine_list` |
| Type | String |




Dump the routines in
_`routine_list`_, which is a list of
one or more comma-separated routine (stored procedure or
function) names. Multiple instances of this option are
additive. For more information, see
[mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


- [`--include-tables=table_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-tables)




| Command-Line Format | `--include-tables=table_list` |
| Type | String |




Dump the tables in _`table_list`_,
which is a list of one or more comma-separated table names.
Multiple instances of this option are additive. For more
information, see [mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


- [`--include-triggers=trigger_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-triggers)




| Command-Line Format | `--include-triggers=trigger_list` |
| Type | String |




Dump the triggers in
_`trigger_list`_, which is a list of
one or more comma-separated trigger names. Multiple
instances of this option are additive. For more information,
see [mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


- [`--include-users=user_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-users)




| Command-Line Format | `--include-users=user_list` |
| Type | String |




Dump the user accounts in
_`user_list`_, which is a list of one
or more comma-separated user names. Multiple instances of
this option are additive. For more information, see
[mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection").


- [`--insert-ignore`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_insert-ignore)




| Command-Line Format | `--insert-ignore` |




Write [`INSERT\\
              IGNORE`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements rather than
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements.


- [`--log-error-file=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_log-error-file)




| Command-Line Format | `--log-error-file=file_name` |
| Type | File name |




Log warnings and errors by appending them to the named file.
If this option is not given, [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program")
writes warnings and errors to the standard error output.


- [`--login-path=name`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_login-path)




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


- [`--max-allowed-packet=N`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_max-allowed-packet)




| Command-Line Format | `--max-allowed-packet=N` |
| Type | Numeric |
| Default Value | `25165824` |




The maximum size of the buffer for client/server
communication. The default is 24MB, the maximum is 1GB.


- [`--net-buffer-length=N`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_net-buffer-length)




| Command-Line Format | `--net-buffer-length=N` |
| Type | Numeric |
| Default Value | `1047552` |




The initial size of the buffer for client/server
communication. When creating multiple-row
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements (as with
the [`--extended-insert`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_extended-insert)
option), [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") creates rows up to
_`N`_ bytes long. If you use this
option to increase the value, ensure that the MySQL server
[`net_buffer_length`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_net_buffer_length) system
variable has a value at least this large.


- [`--no-create-db`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_no-create-db)




| Command-Line Format | `--no-create-db` |




Suppress any [`CREATE DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "15.1.12 CREATE DATABASE Statement")
statements that might otherwise be included in the output.


- [`--no-create-info`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_no-create-info),
`-t`




| Command-Line Format | `--no-create-info` |




Do not write [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement")
statements that create each dumped table.


- [`--no-defaults`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_no-defaults)




| Command-Line Format | `--no-defaults` |




Do not read any option files. If program startup fails due
to reading unknown options from an option file,
[`--no-defaults`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_no-defaults) can be used
to prevent them from being read.



The exception is that the `.mylogin.cnf`
file is read in all cases, if it exists. This permits
passwords to be specified in a safer way than on the command
line even when
[`--no-defaults`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_no-defaults) is used. To
create `.mylogin.cnf`, use the
[**mysql\_config\_editor**](https://dev.mysql.com/doc/refman/8.0/en/mysql-config-editor.html "6.6.7 mysql_config_editor — MySQL Configuration Utility") utility. See
[Section 6.6.7, “mysql\_config\_editor — MySQL Configuration Utility”](https://dev.mysql.com/doc/refman/8.0/en/mysql-config-editor.html "6.6.7 mysql_config_editor — MySQL Configuration Utility").



For additional information about this and other option-file
options, see [Section 6.2.2.3, “Command-Line Options that Affect Option-File Handling”](https://dev.mysql.com/doc/refman/8.0/en/option-file-options.html "6.2.2.3 Command-Line Options that Affect Option-File Handling").


- [`--parallel-schemas=[N:]db_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_parallel-schemas)




| Command-Line Format | `--parallel-schemas=[N:]schema_list` |
| Type | String |




Create a queue for processing the databases in
_`db_list`_, which is a list of one
or more comma-separated database names. If
_`N`_ is given, the queue uses
_`N`_ threads. If
_`N`_ is not given, the
[`--default-parallelism`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_default-parallelism)
option determines the number of queue threads.



Multiple instances of this option create multiple queues.
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") also creates a default queue to
use for databases not named in any
[`--parallel-schemas`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_parallel-schemas) option,
and for dumping user definitions if command options select
them. For more information, see
[mysqlpump Parallel Processing](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-parallelism "mysqlpump Parallel Processing").


- [`--password[=password]`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password),
`-p[password]`




| Command-Line Format | `--password[=password]` |
| Type | String |




The password of the MySQL account used for connecting to the
server. The password value is optional. If not given,
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") prompts for one. If given,
there must be _no space_ between
[`--password=`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password) or
`-p` and the password following it. If no
password option is specified, the default is to send no
password.



Specifying a password on the command line should be
considered insecure. To avoid giving the password on the
command line, use an option file. See
[Section 8.1.2.1, “End-User Guidelines for Password Security”](https://dev.mysql.com/doc/refman/8.0/en/password-security-user.html "8.1.2.1 End-User Guidelines for Password Security").



To explicitly specify that there is no password and that
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") should not prompt for one, use
the
[`--skip-password`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password)
option.


- [`--password1[=pass_val]`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password1)


The password for multifactor authentication factor 1 of the
MySQL account used for connecting to the server. The
password value is optional. If not given,
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") prompts for one. If given,
there must be _no space_ between
[`--password1=`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password1) and the
password following it. If no password option is specified,
the default is to send no password.



Specifying a password on the command line should be
considered insecure. To avoid giving the password on the
command line, use an option file. See
[Section 8.1.2.1, “End-User Guidelines for Password Security”](https://dev.mysql.com/doc/refman/8.0/en/password-security-user.html "8.1.2.1 End-User Guidelines for Password Security").



To explicitly specify that there is no password and that
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") should not prompt for one, use
the
[`--skip-password1`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password1)
option.


[`--password1`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password1) and
[`--password`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password) are synonymous,
as are
[`--skip-password1`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password1)
and
[`--skip-password`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password).


- [`--password2[=pass_val]`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password2)


The password for multifactor authentication factor 2 of the
MySQL account used for connecting to the server. The
semantics of this option are similar to the semantics for
[`--password1`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password1); see the
description of that option for details.


- [`--password3[=pass_val]`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password3)


The password for multifactor authentication factor 3 of the
MySQL account used for connecting to the server. The
semantics of this option are similar to the semantics for
[`--password1`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_password1); see the
description of that option for details.


- [`--plugin-dir=dir_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_plugin-dir)




| Command-Line Format | `--plugin-dir=dir_name` |
| Type | Directory name |




The directory in which to look for plugins. Specify this
option if the
[`--default-auth`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_default-auth) option is
used to specify an authentication plugin but
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") does not find it. See
[Section 8.2.17, “Pluggable Authentication”](https://dev.mysql.com/doc/refman/8.0/en/pluggable-authentication.html "8.2.17 Pluggable Authentication").


- [`--port=port_num`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_port),
`-P port_num`




| Command-Line Format | `--port=port_num` |
| Type | Numeric |
| Default Value | `3306` |




For TCP/IP connections, the port number to use.


- [`--print-defaults`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_print-defaults)




| Command-Line Format | `--print-defaults` |




Print the program name and all options that it gets from
option files.



For additional information about this and other option-file
options, see [Section 6.2.2.3, “Command-Line Options that Affect Option-File Handling”](https://dev.mysql.com/doc/refman/8.0/en/option-file-options.html "6.2.2.3 Command-Line Options that Affect Option-File Handling").


- [`--protocol={TCP|SOCKET|PIPE|MEMORY}`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_protocol)




| Command-Line Format | `--protocol=type` |
| Type | String |
| Default Value | `[see text]` |
| Valid Values | `TCP`<br>`SOCKET`<br>`PIPE`<br>`MEMORY` |




The transport protocol to use for connecting to the server.
It is useful when the other connection parameters normally
result in use of a protocol other than the one you want. For
details on the permissible values, see
[Section 6.2.7, “Connection Transport Protocols”](https://dev.mysql.com/doc/refman/8.0/en/transport-protocols.html "6.2.7 Connection Transport Protocols").


- [`--replace`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_replace)




| Command-Line Format | `--replace` |




Write [`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") statements
rather than [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement")
statements.


- [`--result-file=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_result-file)




| Command-Line Format | `--result-file=file_name` |
| Type | File name |




Direct output to the named file. The result file is created
and its previous contents overwritten, even if an error
occurs while generating the dump.



This option should be used on Windows to prevent newline
`\n` characters from being converted to
`\r\n` carriage return/newline sequences.


- [`--routines`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_routines)




| Command-Line Format | `--routines` |
| Type | Boolean |
| Default Value | `TRUE` |




Include stored routines (procedures and functions) for the
dumped databases in the output. This option requires the
global [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege.



The output generated by using
[`--routines`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_routines) contains
[`CREATE PROCEDURE`](https://dev.mysql.com/doc/refman/8.0/en/create-procedure.html "15.1.17 CREATE PROCEDURE and CREATE FUNCTION Statements") and
[`CREATE FUNCTION`](https://dev.mysql.com/doc/refman/8.0/en/create-function.html "15.1.14 CREATE FUNCTION Statement") statements to
create the routines.



This option is enabled by default; use
[`--skip-routines`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_routines)
to disable it.


- [`--server-public-key-path=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_server-public-key-path)




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
[`--server-public-key-path=file_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_server-public-key-path)
is given and specifies a valid public key file, it takes
precedence over
[`--get-server-public-key`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_get-server-public-key).



For `sha256_password`, this option applies
only if MySQL was built using OpenSSL.



For information about the `sha256_password`
and `caching_sha2_password` plugins, see
[Section 8.4.1.3, “SHA-256 Pluggable Authentication”](https://dev.mysql.com/doc/refman/8.0/en/sha256-pluggable-authentication.html "8.4.1.3 SHA-256 Pluggable Authentication"), and
[Section 8.4.1.2, “Caching SHA-2 Pluggable Authentication”](https://dev.mysql.com/doc/refman/8.0/en/caching-sha2-pluggable-authentication.html "8.4.1.2 Caching SHA-2 Pluggable Authentication").


- [`--set-charset`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_set-charset)




| Command-Line Format | `--set-charset` |




Write [`SET NAMES\\
              default_character_set`](https://dev.mysql.com/doc/refman/8.0/en/set-names.html "15.7.6.3 SET NAMES Statement")
to the output.



This option is enabled by default. To disable it and
suppress the [`SET NAMES`](https://dev.mysql.com/doc/refman/8.0/en/set-names.html "15.7.6.3 SET NAMES Statement")
statement, use
[`--skip-set-charset`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_set-charset).


- `--set-gtid-purged=value`




| Command-Line Format | `--set-gtid-purged=value` |
| Type | Enumeration |
| Default Value | `AUTO` |
| Valid Values | `OFF`<br>`ON`<br>`AUTO` |




This option enables control over global transaction ID
(GTID) information written to the dump file, by indicating
whether to add a
[`SET\\
              @@GLOBAL.gtid_purged`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment") statement to the output. This
option may also cause a statement to be written to the
output that disables binary logging while the dump file is
being reloaded.



The following table shows the permitted option values. The
default value is `AUTO`.





| Value | Meaning |
| --- | --- |
| `OFF` | Add no `SET` statement to the output. |
| `ON` | Add a `SET` statement to the output. An error occurs if<br> GTIDs are not enabled on the server. |
| `AUTO` | Add a `SET` statement to the output if GTIDs are<br> enabled on the server. |




The `--set-gtid-purged` option has the
following effect on binary logging when the dump file is
reloaded:




- `--set-gtid-purged=OFF`: `SET
                  @@SESSION.SQL_LOG_BIN=0;` is not added to the
output.


- `--set-gtid-purged=ON`: `SET
                  @@SESSION.SQL_LOG_BIN=0;` is added to the
output.


- `--set-gtid-purged=AUTO`: `SET
                  @@SESSION.SQL_LOG_BIN=0;` is added to the
output if GTIDs are enabled on the server you are
backing up (that is, if `AUTO`
evaluates to `ON`).


- [`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_single-transaction)




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



When using this option, you should keep in mind that only
`InnoDB` tables are dumped in a consistent
state. For example, any `MyISAM` or
`MEMORY` tables dumped while using this
option may still change state.



While a
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_single-transaction) dump
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
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") to retrieve the table contents
to obtain incorrect contents or fail.


[`--add-locks`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_add-locks) and
[`--single-transaction`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_single-transaction) are
mutually exclusive.


- [`--skip-definer`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_skip-definer)




| Command-Line Format | `--skip-definer` |
| Type | Boolean |
| Default Value | `FALSE` |




Omit `DEFINER` and `SQL
              SECURITY` clauses from the
`CREATE` statements for views and stored
programs. The dump file, when reloaded, creates objects that
use the default `DEFINER` and `SQL
              SECURITY` values. See
[Section 27.6, “Stored Object Access Control”](https://dev.mysql.com/doc/refman/8.0/en/stored-objects-security.html "27.6 Stored Object Access Control").


- [`--skip-dump-rows`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_skip-dump-rows),
`-d`




| Command-Line Format | `--skip-dump-rows` |
| Type | Boolean |
| Default Value | `FALSE` |




Do not dump table rows.


- [`--skip-generated-invisible-primary-key`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_skip-generated-invisible-primary-key)




| Command-Line Format | `--skip-generated-invisible-primary-key` |
| Introduced | 8.0.30 |
| Type | Boolean |
| Default Value | `FALSE` |




This option is available beginning with MySQL 8.0.30, and
causes generated invisible primary keys (GIPKs) to be
excluded from the dump. See
[Section 15.1.20.11, “Generated Invisible Primary Keys”](https://dev.mysql.com/doc/refman/8.0/en/create-table-gipks.html "15.1.20.11 Generated Invisible Primary Keys"), for more information
about GIPKs and GIPK mode.


- [`--socket=path`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_socket),
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


- [`--ssl-fips-mode={OFF|ON|STRICT}`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl-fips-mode)




| Command-Line Format | `--ssl-fips-mode={OFF|ON|STRICT}` |
| Deprecated | 8.0.34 |
| Type | Enumeration |
| Default Value | `OFF` |
| Valid Values | `OFF`<br>`ON`<br>`STRICT` |




Controls whether to enable FIPS mode on the client side. The
[`--ssl-fips-mode`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl-fips-mode) option
differs from other
`--ssl-xxx`
options in that it is not used to establish encrypted
connections, but rather to affect which cryptographic
operations to permit. See [Section 8.8, “FIPS Support”](https://dev.mysql.com/doc/refman/8.0/en/fips-mode.html "8.8 FIPS Support").



These [`--ssl-fips-mode`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl-fips-mode)
values are permitted:




- `OFF`: Disable FIPS mode.


- `ON`: Enable FIPS mode.


- `STRICT`: Enable “strict”
FIPS mode.


Note

If the OpenSSL FIPS Object Module is not available, the
only permitted value for
[`--ssl-fips-mode`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl-fips-mode) is
`OFF`. In this case, setting
[`--ssl-fips-mode`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_ssl-fips-mode) to
`ON` or `STRICT` causes
the client to produce a warning at startup and to operate
in non-FIPS mode.

As of MySQL 8.0.34, this option is deprecated. Expect it to
be removed in a future version of MySQL.


- [`--tls-ciphersuites=ciphersuite_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_tls-ciphersuites)




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


- [`--tls-version=protocol_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_tls-version)




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


- [`--triggers`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_triggers)




| Command-Line Format | `--triggers` |
| Type | Boolean |
| Default Value | `TRUE` |




Include triggers for each dumped table in the output.



This option is enabled by default; use
[`--skip-triggers`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_triggers)
to disable it.


- [`--tz-utc`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_tz-utc)




| Command-Line Format | `--tz-utc` |




This option enables [`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types")
columns to be dumped and reloaded between servers in
different time zones. [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") sets its
connection time zone to UTC and adds `SET
              TIME_ZONE='+00:00'` to the dump file. Without this
option, [`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") columns are
dumped and reloaded in the time zones local to the source
and destination servers, which can cause the values to
change if the servers are in different time zones.
[`--tz-utc`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_tz-utc) also protects
against changes due to daylight saving time.



This option is enabled by default; use
[`--skip-tz-utc`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_tz-utc)
to disable it.


- [`--user=user_name`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_user),
`-u user_name`




| Command-Line Format | `--user=user_name` |
| Type | String |




The user name of the MySQL account to use for connecting to
the server.



If you are using the `Rewriter` plugin with
MySQL 8.0.31 or later, you should grant this user the
[`SKIP_QUERY_REWRITE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_skip-query-rewrite) privilege.


- [`--users`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_users)




| Command-Line Format | `--users` |
| Type | Boolean |
| Default Value | `FALSE` |




Dump user accounts as logical definitions in the form of
[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") and
[`GRANT`](https://dev.mysql.com/doc/refman/8.0/en/grant.html "15.7.1.6 GRANT Statement") statements.



User definitions are stored in the grant tables in the
`mysql` system database. By default,
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") does not include the grant
tables in `mysql` database dumps. To dump
the contents of the grant tables as logical definitions, use
the [`--users`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_users) option and
suppress all database dumping:




``` terminal

mysqlpump --exclude-databases=% --users
```

- [`--version`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_version),
`-V`




| Command-Line Format | `--version` |




Display version information and exit.


- [`--watch-progress`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_watch-progress)




| Command-Line Format | `--watch-progress` |
| Type | Boolean |
| Default Value | `TRUE` |




Periodically display a progress indicator that provides
information about the completed and total number of tables,
rows, and other objects.



This option is enabled by default; use
[`--skip-watch-progress`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_watch-progress)
to disable it.


- [`--zstd-compression-level=level`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_zstd-compression-level)




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


#### mysqlpump Object Selection

[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") has a set of inclusion and
exclusion options that enable filtering of several object types
and provide flexible control over which objects to dump:

- [`--include-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-databases) and
[`--exclude-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-databases) apply
to databases and all objects within them.


- [`--include-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-tables) and
[`--exclude-tables`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-tables) apply to
tables. These options also affect triggers associated with
tables unless the trigger-specific options are given.


- [`--include-triggers`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-triggers) and
[`--exclude-triggers`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-triggers) apply
to triggers.


- [`--include-routines`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-routines) and
[`--exclude-routines`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-routines) apply
to stored procedures and functions. If a routine option
matches a stored procedure name, it also matches a stored
function of the same name.


- [`--include-events`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-events) and
[`--exclude-events`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-events) apply to
Event Scheduler events.


- [`--include-users`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-users) and
[`--exclude-users`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_exclude-users) apply to
user accounts.


Any inclusion or exclusion option may be given multiple times.
The effect is additive. Order of these options does not matter.


The value of each inclusion and exclusion option is a list of
comma-separated names of the appropriate object type. For
example:


``` terminal

--exclude-databases=test,world
--include-tables=customer,invoice
```

Wildcard characters are permitted in the object names:

- `%` matches any sequence of zero or more
characters.


- `_` matches any single character.


For example,
[`--include-tables=t%,__tmp`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-tables)
matches all table names that begin with `t` and
all five-character table names that end with
`tmp`.


For users, a name specified without a host part is interpreted
with an implied host of `%`. For example,
`u1` and `u1@%` are
equivalent. This is the same equivalence that applies in MySQL
generally (see [Section 8.2.4, “Specifying Account Names”](https://dev.mysql.com/doc/refman/8.0/en/account-names.html "8.2.4 Specifying Account Names")).


Inclusion and exclusion options interact as follows:

- By default, with no inclusion or exclusion options,
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") dumps all databases (with
certain exceptions noted in
[mysqlpump Restrictions](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-restrictions "mysqlpump Restrictions")).


- If inclusion options are given in the absence of exclusion
options, only the objects named as included are dumped.


- If exclusion options are given in the absence of inclusion
options, all objects are dumped except those named as
excluded.


- If inclusion and exclusion options are given, all objects
named as excluded and not named as included are not dumped.
All other objects are dumped.


If multiple databases are being dumped, it is possible to name
tables, triggers, and routines in a specific database by
qualifying the object names with the database name. The
following command dumps databases `db1` and
`db2`, but excludes tables
`db1.t1` and `db2.t2`:

``` terminal

mysqlpump --include-databases=db1,db2 --exclude-tables=db1.t1,db2.t2
```

The following options provide alternative ways to specify which
databases to dump:

- The [`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_all-databases) option
dumps all databases (with certain exceptions noted in
[mysqlpump Restrictions](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-restrictions "mysqlpump Restrictions")). It is equivalent
to specifying no object options at all (the default
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") action is to dump everything).


[`--include-databases=%`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-databases) is
similar to
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_all-databases), but
selects all databases for dumping, even those that are
exceptions for
[`--all-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_all-databases).


- The [`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_databases) option
causes [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") to treat all name
arguments as names of databases to dump. It is equivalent to
an [`--include-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-databases)
option that names the same databases.


#### mysqlpump Parallel Processing

[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") can use parallelism to achieve
concurrent processing. You can select concurrency between
databases (to dump multiple databases simultaneously) and within
databases (to dump multiple objects from a given database
simultaneously).


By default, [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") sets up one queue with
two threads. You can create additional queues and control the
number of threads assigned to each one, including the default
queue:

- [`--default-parallelism=N`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_default-parallelism)
specifies the default number of threads used for each queue.
In the absence of this option, _`N`_
is 2.



The default queue always uses the default number of threads.
Additional queues use the default number of threads unless
you specify otherwise.


- [`--parallel-schemas=[N:]db_list`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_parallel-schemas)
sets up a processing queue for dumping the databases named
in _`db_list`_ and optionally
specifies how many threads the queue uses.
_`db_list`_ is a list of
comma-separated database names. If the option argument
begins with
`N:`, the queue
uses _`N`_ threads. Otherwise, the
[`--default-parallelism`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_default-parallelism)
option determines the number of queue threads.



Multiple instances of the
[`--parallel-schemas`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_parallel-schemas) option
create multiple queues.



Names in the database list are permitted to contain the same
`%` and `_` wildcard
characters supported for filtering options (see
[mysqlpump Object Selection](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#mysqlpump-filtering "mysqlpump Object Selection")).


[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") uses the default queue for
processing any databases not named explicitly with a
[`--parallel-schemas`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_parallel-schemas) option, and
for dumping user definitions if command options select them.


In general, with multiple queues, [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program")
uses parallelism between the sets of databases processed by the
queues, to dump multiple databases simultaneously. For a queue
that uses multiple threads, [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") uses
parallelism within databases, to dump multiple objects from a
given database simultaneously. Exceptions can occur; for
example, [**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") may block queues while it
obtains from the server lists of objects in databases.


With parallelism enabled, it is possible for output from
different databases to be interleaved. For example,
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements from multiple
tables dumped in parallel can be interleaved; the statements are
not written in any particular order. This does not affect
reloading because output statements qualify object names with
database names or are preceded by
[`USE`](https://dev.mysql.com/doc/refman/8.0/en/use.html "15.8.4 USE Statement") statements as required.


The granularity for parallelism is a single database object. For
example, a single table cannot be dumped in parallel using
multiple threads.


Examples:


``` terminal

mysqlpump --parallel-schemas=db1,db2 --parallel-schemas=db3
```

[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") sets up a queue to process
`db1` and `db2`, another queue
to process `db3`, and a default queue to
process all other databases. All queues use two threads.


``` terminal

mysqlpump --parallel-schemas=db1,db2 --parallel-schemas=db3
          --default-parallelism=4
```

This is the same as the previous example except that all queues
use four threads.


``` terminal

mysqlpump --parallel-schemas=5:db1,db2 --parallel-schemas=3:db3
```

The queue for `db1` and `db2`
uses five threads, the queue for `db3` uses
three threads, and the default queue uses the default of two
threads.


As a special case, with
[`--default-parallelism=0`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_default-parallelism) and no
[`--parallel-schemas`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_parallel-schemas) options,
[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") runs as a single-threaded process
and creates no queues.

#### mysqlpump Restrictions

[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") does not dump the
`performance_schema`,
`ndbinfo`, or `sys` schema by
default. To dump any of these, name them explicitly on the
command line. You can also name them with the
[`--databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_databases) or
[`--include-databases`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-databases) option.


[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") does not dump the
`INFORMATION_SCHEMA` schema.


[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") does not dump
`InnoDB` [`CREATE\\
        TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/create-tablespace.html "15.1.21 CREATE TABLESPACE Statement") statements.


[**mysqlpump**](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html "6.5.6 mysqlpump — A Database Backup Program") dumps user accounts in logical form
using [`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") and
[`GRANT`](https://dev.mysql.com/doc/refman/8.0/en/grant.html "15.7.1.6 GRANT Statement") statements (for example,
when you use the
[`--include-users`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_include-users) or
[`--users`](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html#option_mysqlpump_users) option). For this
reason, dumps of the `mysql` system database do
not by default include the grant tables that contain user
definitions: `user`, `db`,
`tables_priv`, `columns_priv`,
`procs_priv`, or
`proxies_priv`. To dump any of the grant
tables, name the `mysql` database followed by
the table names:


``` terminal

mysqlpump mysql user db ...
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/mysqlimport.html "Previous: mysqlimport — A Data Import Program") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/programs-client.html "Up: Client Programs") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/mysqlshow.html "Next: mysqlshow — Display Database, Table, and Column Information")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysqlpump.html)

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