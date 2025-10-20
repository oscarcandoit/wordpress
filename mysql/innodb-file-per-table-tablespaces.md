---
url: https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html
scraped_at: 2025-10-20T03:15:40.421Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html "Hide Sidebar")

[Previous: The System Tablespace](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html "Previous: The System Tablespace")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html "Up: Tablespaces")[Next: General Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html "Next: General Tablespaces")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/innodb-file-per-table-tablespaces.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/innodb-file-per-table-tablespaces.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/innodb-file-per-table-tablespaces.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/innodb-file-per-table-tablespaces.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/innodb-file-per-table-tablespaces.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/innodb-file-per-table-tablespaces.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/innodb-file-per-table-tablespaces.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/innodb-file-per-table-tablespaces.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html)  / [The InnoDB Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)  /
[InnoDB On-Disk Structures](https://dev.mysql.com/doc/refman/8.0/en/innodb-on-disk-structures.html)  /
[Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)  /

File-Per-Table Tablespaces


#### 17.6.3.2 File-Per-Table Tablespaces

A file-per-table tablespace contains data and indexes for a single
`InnoDB` table, and is stored on the file system
in a single data file.


File-per-table tablespace characteristics are described under the
following topics in this section:

- [File-Per-Table Tablespace Configuration](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html#innodb-file-per-table-configuration "File-Per-Table Tablespace Configuration")

- [File-Per-Table Tablespace Data Files](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html#innodb-file-per-table-data-files "File-Per-Table Tablespace Data Files")

- [File-Per-Table Tablespace Advantages](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html#innodb-file-per-table-advantages "File-Per-Table Tablespace Advantages")

- [File-Per-Table Tablespace Disadvantages](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html#innodb-file-per-table-disadvantages "File-Per-Table Tablespace Disadvantages")


##### File-Per-Table Tablespace Configuration

`InnoDB` creates tables in file-per-table
tablespaces by default. This behavior is controlled by the
[`innodb_file_per_table`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_file_per_table) variable.
Disabling [`innodb_file_per_table`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_file_per_table)
causes `InnoDB` to create tables in the system
tablespace.


An [`innodb_file_per_table`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_file_per_table)
setting can be specified in an option file or configured at
runtime using a
[`SET\\
        GLOBAL`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment") statement. Changing the setting at runtime
requires privileges sufficient to set global system variables.
See [Section 7.1.9.1, “System Variable Privileges”](https://dev.mysql.com/doc/refman/8.0/en/system-variable-privileges.html "7.1.9.1 System Variable Privileges").


Option file:


``` ini

[mysqld]
innodb_file_per_table=ON
```

Using [`SET\\
        GLOBAL`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment") at runtime:


``` sql

mysql> SET GLOBAL innodb_file_per_table=ON;
```

##### File-Per-Table Tablespace Data Files

A file-per-table tablespace is created in an
`.ibd` data file in a schema directory under
the MySQL data directory. The `.ibd` file is
named for the table
( `table_name.ibd`).
For example, the data file for table `test.t1`
is created in the `test` directory under the
MySQL data directory:


``` sql

mysql> USE test;

mysql> CREATE TABLE t1 (
   id INT PRIMARY KEY AUTO_INCREMENT,
   name VARCHAR(100)
 ) ENGINE = InnoDB;

$> cd /path/to/mysql/data/test
$> ls
t1.ibd
```

You can use the `DATA DIRECTORY` clause of the
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement to
implicitly create a file-per-table tablespace data file outside
of the data directory. For more information, see
[Section 17.6.1.2, “Creating Tables Externally”](https://dev.mysql.com/doc/refman/8.0/en/innodb-create-table-external.html "17.6.1.2 Creating Tables Externally").

##### File-Per-Table Tablespace Advantages

File-per-table tablespaces have the following advantages over
shared tablespaces such as the system tablespace or general
tablespaces.

- Disk space is returned to the operating system after
truncating or dropping a table created in a file-per-table
tablespace. Truncating or dropping a table stored in a
shared tablespace creates free space within the shared
tablespace data file, which can only be used for
`InnoDB` data. In other words, a shared
tablespace data file does not shrink in size after a table
is truncated or dropped.


- A table-copying [`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement")
operation on a table that resides in a shared tablespace can
increase the amount of disk space occupied by the
tablespace. Such operations may require as much additional
space as the data in the table plus indexes. This space is
not released back to the operating system as it is for
file-per-table tablespaces.


- [`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") performance is
better when executed on tables that reside in file-per-table
tablespaces.


- File-per-table tablespace data files can be created on
separate storage devices for I/O optimization, space
management, or backup purposes. See
[Section 17.6.1.2, “Creating Tables Externally”](https://dev.mysql.com/doc/refman/8.0/en/innodb-create-table-external.html "17.6.1.2 Creating Tables Externally").


- You can import a table that resides in file-per-table
tablespace from another MySQL instance. See
[Section 17.6.1.3, “Importing InnoDB Tables”](https://dev.mysql.com/doc/refman/8.0/en/innodb-table-import.html "17.6.1.3 Importing InnoDB Tables").


- Tables created in file-per-table tablespaces support
features associated with `DYNAMIC` and
`COMPRESSED` row formats, which are not
supported by the system tablespace. See
[Section 17.10, “InnoDB Row Formats”](https://dev.mysql.com/doc/refman/8.0/en/innodb-row-format.html "17.10 InnoDB Row Formats").


- Tables stored in individual tablespace data files can save
time and improve chances for a successful recovery when data
corruption occurs, when backups or binary logs are
unavailable, or when the MySQL server instance cannot be
restarted.


- Tables created in file-per-table tablespaces can be backed
up or restored quickly using MySQL Enterprise Backup, without interrupting the
use of other `InnoDB` tables. This is
beneficial for tables on varying backup schedules or that
require backup less frequently. See
[Making a Partial Backup](https://dev.mysql.com/doc/mysql-enterprise-backup/8.0/en/partial.html) for details.


- File-per-table tablespaces permit monitoring table size on
the file system by monitoring the size of the tablespace
data file.


- Common Linux file systems do not permit concurrent writes to
a single file such as a shared tablespace data file when
[`innodb_flush_method`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_flush_method) is set
to `O_DIRECT`. As a result, there are
possible performance improvements when using file-per-table
tablespaces in conjunction with this setting.


- Tables in a shared tablespace are limited in size by the
64TB tablespace size limit. By comparison, each
file-per-table tablespace has a 64TB size limit, which
provides plenty of room for individual tables to grow in
size.


##### File-Per-Table Tablespace Disadvantages

File-per-table tablespaces have the following disadvantages
compared to shared tablespaces such as the system tablespace or
general tablespaces.

- With file-per-table tablespaces, each table may have unused
space that can only be utilized by rows of the same table,
which can lead to wasted space if not properly managed.


- `fsync` operations are performed on
multiple file-per-table data files instead of a single
shared tablespace data file. Because
`fsync` operations are per file, write
operations for multiple tables cannot be combined, which can
result in a higher total number of `fsync`
operations.


- [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server") must keep an open file handle for
each file-per-table tablespace, which may impact performance
if you have numerous tables in file-per-table tablespaces.


- More file descriptors are required when each table has its
own data file.


- There is potential for more fragmentation, which can impede
[`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") and table scan
performance. However, if fragmentation is managed,
file-per-table tablespaces can improve performance for these
operations.


- The buffer pool is scanned when dropping a table that
resides in a file-per-table tablespace, which can take
several seconds for large buffer pools. The scan is
performed with a broad internal lock, which may delay other
operations.


- The
[`innodb_autoextend_increment`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_autoextend_increment)
variable, which defines the increment size for extending the
size of an auto-extending shared tablespace file when it
becomes full, does not apply to file-per-table tablespace
files, which are auto-extending regardless of the
[`innodb_autoextend_increment`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_autoextend_increment)
setting. Initial file-per-table tablespace extensions are by
small amounts, after which extensions occur in increments of
4MB.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html "Previous: The System Tablespace") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html "Up: Tablespaces") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html "Next: General Tablespaces")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html)

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