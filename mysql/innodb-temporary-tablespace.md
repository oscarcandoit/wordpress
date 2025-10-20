---
url: https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html
scraped_at: 2025-10-20T03:15:53.732Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html "Hide Sidebar")

[Previous: Undo Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-tablespaces.html "Previous: Undo Tablespaces")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html "Up: Tablespaces")[Next: Moving Tablespace Files While the Server is Offline](https://dev.mysql.com/doc/refman/8.0/en/innodb-moving-data-files-offline.html "Next: Moving Tablespace Files While the Server is Offline")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/innodb-temporary-tablespace.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/innodb-temporary-tablespace.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/innodb-temporary-tablespace.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/innodb-temporary-tablespace.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/innodb-temporary-tablespace.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/innodb-temporary-tablespace.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/innodb-temporary-tablespace.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/innodb-temporary-tablespace.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html)  / [The InnoDB Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)  /
[InnoDB On-Disk Structures](https://dev.mysql.com/doc/refman/8.0/en/innodb-on-disk-structures.html)  /
[Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)  /

Temporary Tablespaces


#### 17.6.3.5 Temporary Tablespaces

`InnoDB` uses session temporary tablespaces and a
global temporary tablespace.

##### Session Temporary Tablespaces

Session temporary tablespaces store user-created temporary
tables and internal temporary tables created by the optimizer
when `InnoDB` is configured as the storage
engine for on-disk internal temporary tables. Beginning with
MySQL 8.0.16, the storage engine used for on-disk internal
temporary tables is `InnoDB`. (Previously, the
storage engine was determined by the value of
[`internal_tmp_disk_storage_engine`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_internal_tmp_disk_storage_engine).)


Session temporary tablespaces are allocated to a session from a
pool of temporary tablespaces on the first request to create an
on-disk temporary table. A maximum of two tablespaces is
allocated to a session, one for user-created temporary tables
and the other for internal temporary tables created by the
optimizer. The temporary tablespaces allocated to a session are
used for all on-disk temporary tables created by the session.
When a session disconnects, its temporary tablespaces are
truncated and released back to the pool. A pool of 10 temporary
tablespaces is created when the server is started. The size of
the pool never shrinks and tablespaces are added to the pool
automatically as necessary. The pool of temporary tablespaces is
removed on normal shutdown or on an aborted initialization.
Session temporary tablespace files are five pages in size when
created and have an `.ibt` file name
extension.


A range of 400 thousand space IDs is reserved for session
temporary tablespaces. Because the pool of session temporary
tablespaces is recreated each time the server is started, space
IDs for session temporary tablespaces are not persisted when the
server is shut down, and may be reused.


The [`innodb_temp_tablespaces_dir`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_temp_tablespaces_dir)
variable defines the location where session temporary
tablespaces are created. The default location is the
`#innodb_temp` directory in the data
directory. Startup is refused if the pool of temporary
tablespaces cannot be created.


```terminal
$> cd BASEDIR/data/#innodb_temp
$> ls
temp_10.ibt  temp_2.ibt  temp_4.ibt  temp_6.ibt  temp_8.ibt
temp_1.ibt   temp_3.ibt  temp_5.ibt  temp_7.ibt  temp_9.ibt
```

In statement based replication (SBR) mode, temporary tables
created on a replica reside in a single session temporary
tablespace that is truncated only when the MySQL server is shut
down.


The [`INNODB_SESSION_TEMP_TABLESPACES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-session-temp-tablespaces-table.html "28.4.22 The INFORMATION_SCHEMA INNODB_SESSION_TEMP_TABLESPACES Table")
table provides metadata about session temporary tablespaces.


The Information Schema
[`INNODB_TEMP_TABLE_INFO`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-temp-table-info-table.html "28.4.27 The INFORMATION_SCHEMA INNODB_TEMP_TABLE_INFO Table") table
provides metadata about user-created temporary tables that are
active in an `InnoDB` instance.

##### Global Temporary Tablespace

The global temporary tablespace ( `ibtmp1`)
stores rollback segments for changes made to user-created
temporary tables.


The [`innodb_temp_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_temp_data_file_path)
variable defines the relative path, name, size, and attributes
for global temporary tablespace data files. If no value is
specified for
[`innodb_temp_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_temp_data_file_path), the
default behavior is to create a single auto-extending data file
named `ibtmp1` in the
[`innodb_data_home_dir`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_home_dir) directory.
The initial file size is slightly larger than 12MB.


The global temporary tablespace is removed on normal shutdown or
on an aborted initialization, and recreated each time the server
is started. The global temporary tablespace receives a
dynamically generated space ID when it is created. Startup is
refused if the global temporary tablespace cannot be created.
The global temporary tablespace is not removed if the server
halts unexpectedly. In this case, a database administrator can
remove the global temporary tablespace manually or restart the
MySQL server. Restarting the MySQL server removes and recreates
the global temporary tablespace automatically.


The global temporary tablespace cannot reside on a raw device.


The Information Schema [`FILES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-files-table.html "28.3.15 The INFORMATION_SCHEMA FILES Table") table
provides metadata about the global temporary tablespace. Issue a
query similar to this one to view global temporary tablespace
metadata:


```sql
mysql> SELECT * FROM INFORMATION_SCHEMA.FILES WHERE TABLESPACE_NAME='innodb_temporary'\G
```

By default, the global temporary tablespace data file is
autoextending and increases in size as necessary.


To determine if a global temporary tablespace data file is
autoextending, check the
[`innodb_temp_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_temp_data_file_path)
setting:


```sql
mysql> SELECT @@innodb_temp_data_file_path;
+------------------------------+
| @@innodb_temp_data_file_path |
+------------------------------+
| ibtmp1:12M:autoextend        |
+------------------------------+
```

To check the size of global temporary tablespace data files,
examine the Information Schema
[`FILES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-files-table.html "28.3.15 The INFORMATION_SCHEMA FILES Table") table using a query similar
to this one:


```sql
mysql> SELECT FILE_NAME, TABLESPACE_NAME, ENGINE, INITIAL_SIZE, TOTAL_EXTENTS*EXTENT_SIZE
       AS TotalSizeBytes, DATA_FREE, MAXIMUM_SIZE FROM INFORMATION_SCHEMA.FILES
       WHERE TABLESPACE_NAME = 'innodb_temporary'\G
*************************** 1. row ***************************
      FILE_NAME: ./ibtmp1
TABLESPACE_NAME: innodb_temporary
         ENGINE: InnoDB
   INITIAL_SIZE: 12582912
 TotalSizeBytes: 12582912
      DATA_FREE: 6291456
   MAXIMUM_SIZE: NULL
```

`TotalSizeBytes` shows the current size of the
global temporary tablespace data file. For information about
other field values, see
[Section 28.3.15, “The INFORMATION\_SCHEMA FILES Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-files-table.html "28.3.15 The INFORMATION_SCHEMA FILES Table").


Alternatively, check the global temporary tablespace data file
size on your operating system. The global temporary tablespace
data file is located in the directory defined by the
[`innodb_temp_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_temp_data_file_path)
variable.


To reclaim disk space occupied by a global temporary tablespace
data file, restart the MySQL server. Restarting the server
removes and recreates the global temporary tablespace data file
according to the attributes defined by
[`innodb_temp_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_temp_data_file_path).


To limit the size of the global temporary tablespace data file,
configure
[`innodb_temp_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_temp_data_file_path) to
specify a maximum file size. For example:


```ini
[mysqld]
innodb_temp_data_file_path=ibtmp1:12M:autoextend:max:500M
```

Configuring
[`innodb_temp_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_temp_data_file_path)
requires restarting the server.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-tablespaces.html "Previous: Undo Tablespaces") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html "Up: Tablespaces") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/innodb-moving-data-files-offline.html "Next: Moving Tablespace Files While the Server is Offline")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html)

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