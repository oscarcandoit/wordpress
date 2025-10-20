---
url: https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html
scraped_at: 2025-10-20T03:15:48.714Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html "Hide Sidebar")

[Previous: Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html "Previous: Tablespaces")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html "Up: Tablespaces")[Next: File-Per-Table Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html "Next: File-Per-Table Tablespaces")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/innodb-system-tablespace.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/innodb-system-tablespace.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/innodb-system-tablespace.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/innodb-system-tablespace.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/innodb-system-tablespace.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/innodb-system-tablespace.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/innodb-system-tablespace.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/innodb-system-tablespace.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html)  / [The InnoDB Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)  /
[InnoDB On-Disk Structures](https://dev.mysql.com/doc/refman/8.0/en/innodb-on-disk-structures.html)  /
[Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)  /

The System Tablespace


#### 17.6.3.1 The System Tablespace

The system tablespace is the storage area for the change buffer.
It may also contain table and index data if tables are created in
the system tablespace rather than file-per-table or general
tablespaces. In previous MySQL versions, the system tablespace
contained the `InnoDB` data dictionary. In MySQL
8.0, `InnoDB` stores metadata in the
MySQL data dictionary. See [Chapter 16, _MySQL Data Dictionary_](https://dev.mysql.com/doc/refman/8.0/en/data-dictionary.html "Chapter 16 MySQL Data Dictionary"). In
previous MySQL releases, the system tablespace also contained the
doublewrite buffer storage area. This storage area resides in
separate doublewrite files as of MySQL 8.0.20. See
[Section 17.6.4, “Doublewrite Buffer”](https://dev.mysql.com/doc/refman/8.0/en/innodb-doublewrite-buffer.html "17.6.4 Doublewrite Buffer").


The system tablespace can have one or more data files. By default,
a single system tablespace data file, named
`ibdata1`, is created in the data directory.
The size and number of system tablespace data files is defined by
the [`innodb_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_file_path) startup
option. For configuration information, see
[System Tablespace Data File Configuration](https://dev.mysql.com/doc/refman/8.0/en/innodb-init-startup-configuration.html#innodb-startup-data-file-configuration "System Tablespace Data File Configuration").


Additional information about the system tablespace is provided
under the following topics in the section:

- [Resizing the System Tablespace](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html#innodb-resize-system-tablespace "Resizing the System Tablespace")

- [Using Raw Disk Partitions for the System Tablespace](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html#innodb-raw-devices "Using Raw Disk Partitions for the System Tablespace")


##### Resizing the System Tablespace

This section describes how to increase or decrease the size of
the system tablespace.


###### Increasing the Size of the System Tablespace

The easiest way to increase the size of the system tablespace is
to configure it to be auto-extending. To do so, specify the
`autoextend` attribute for the last data file
in the [`innodb_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_file_path)
setting, and restart the server. For example:


```ini
innodb_data_file_path=ibdata1:10M:autoextend
```

When the `autoextend` attribute is specified,
the data file automatically increases in size by 8MB increments
as space is required. The
[`innodb_autoextend_increment`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_autoextend_increment)
variable controls the increment size.


You can also increase system tablespace size by adding another
data file. To do so:

1. Stop the MySQL server.


2. If the last data file in the
    [`innodb_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_file_path)
    setting is defined with the `autoextend`
    attribute, remove it, and modify the size attribute to
    reflect the current data file size. To determine the
    appropriate data file size to specify, check your file
    system for the file size, and round that value down to the
    closest MB value, where a MB is equal to 1024 x 1024 bytes.


3. Append a new data file to the
    [`innodb_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_file_path)
    setting, optionally specifying the
    `autoextend` attribute. The
    `autoextend` attribute can be specified
    only for the last data file in the
    [`innodb_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_file_path)
    setting.


4. Start the MySQL server.


For example, this tablespace has one auto-extending data file:


```none
innodb_data_home_dir =
innodb_data_file_path = /ibdata/ibdata1:10M:autoextend
```

Suppose that the data file has grown to 988MB over time. This is
the [`innodb_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_file_path)
setting after modifying the size attribute to reflect the
current data file size, and after specifying a new 50MB
auto-extending data file:


```none
innodb_data_home_dir =
innodb_data_file_path = /ibdata/ibdata1:988M;/disk2/ibdata2:50M:autoextend
```

When adding a new data file, do not specify an existing file
name. `InnoDB` creates and initializes the new
data file when you start the server.

Note

You cannot increase the size of an existing system tablespace
data file by changing its size attribute. For example,
changing the
[`innodb_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_file_path) setting
from `ibdata1:10M:autoextend` to
`ibdata1:12M:autoextend` produces the
following error when starting the server:


```terminal
[ERROR] [MY-012263] [InnoDB] The Auto-extending innodb_system
data file './ibdata1' is of a different size 640 pages (rounded down to MB) than
specified in the .cnf file: initial 768 pages, max 0 (relevant if non-zero) pages!
```

The error indicates that the existing data file size
(expressed in `InnoDB` pages) is different
from the data file size specified in the configuration file.
If you encounter this error, restore the previous
[`innodb_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_file_path)
setting, and refer to the system tablespace resizing
instructions.

###### Decreasing the Size of the InnoDB System Tablespace

Decreasing the size of an existing system tablespace is not
supported. The only option to achieve a smaller system
tablespace is to restore your data from a backup to a new MySQL
instance created with the desired system tablespace size
configuration.


For information about creating backups, see
[Section 17.18.1, “InnoDB Backup”](https://dev.mysql.com/doc/refman/8.0/en/innodb-backup.html "17.18.1 InnoDB Backup").


For information about configuring data files for a new system
tablespace. See
[System Tablespace Data File Configuration](https://dev.mysql.com/doc/refman/8.0/en/innodb-init-startup-configuration.html#innodb-startup-data-file-configuration "System Tablespace Data File Configuration").


To avoid a large system tablespace, consider using
file-per-table tablespaces or general tablespaces for your data.
File-per-table tablespaces are the default tablespace type and
are used implicitly when creating an `InnoDB`
table. Unlike the system tablespace, file-per-table tablespaces
return disk space to the operating system when they are
truncated or dropped. For more information, see
[Section 17.6.3.2, “File-Per-Table Tablespaces”](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html "17.6.3.2 File-Per-Table Tablespaces"). General
tablespaces are multi-table tablespaces that can also be used as
an alternative to the system tablespace. See
[Section 17.6.3.3, “General Tablespaces”](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html "17.6.3.3 General Tablespaces").

##### Using Raw Disk Partitions for the System Tablespace

Raw disk partitions can be used as system tablespace data files.
This technique enables nonbuffered I/O on Windows and some Linux
and Unix systems without file system overhead. Perform tests
with and without raw partitions to verify whether they improve
performance on your system.


When using a raw disk partition, ensure that the user ID that
runs the MySQL server has read and write privileges for that
partition. For example, if running the server as the
`mysql` user, the partition must be readable
and writeable by `mysql`. If running the server
with the [`--memlock`](https://dev.mysql.com/doc/refman/8.0/en/server-options.html#option_mysqld_memlock) option, the
server must be run as `root`, so the partition
must be readable and writeable by `root`.


The procedures described below involve option file modification.
For additional information, see [Section 6.2.2.2, “Using Option Files”](https://dev.mysql.com/doc/refman/8.0/en/option-files.html "6.2.2.2 Using Option Files").

###### Allocating a Raw Disk Partition on Linux and Unix Systems

1. To use a raw device for a new server instance, first prepare
    the configuration file by setting
    [`innodb_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_file_path) with
    the `raw` keyword. For example:



```ini
[mysqld]
innodb_data_home_dir=
innodb_data_file_path=/dev/hdd1:3Graw;/dev/hdd2:2Graw
```



    The partition must be at least as large as the size that you
    specify. Note that 1MB in `InnoDB` is 1024
    × 1024 bytes, whereas 1MB in disk specifications
    usually means 1,000,000 bytes.


2. Then initialize the server for the first time by using
    [`--initialize`](https://dev.mysql.com/doc/refman/8.0/en/server-options.html#option_mysqld_initialize) or
    [`--initialize-insecure`](https://dev.mysql.com/doc/refman/8.0/en/server-options.html#option_mysqld_initialize-insecure). InnoDB
    notices the `raw` keyword and initializes
    the new partition, and then it stops the server.


3. Now restart the server. `InnoDB` now
    permits changes to be made.


###### Allocating a Raw Disk Partition on Windows

On Windows systems, the same steps and accompanying guidelines
described for Linux and Unix systems apply except that the
[`innodb_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_file_path) setting
differs slightly on Windows. For example:


```none
[mysqld]
innodb_data_home_dir=
innodb_data_file_path=//./D::10Graw
```

The `//./` corresponds to the Windows syntax
of `\\.\` for accessing physical drives. In
the example above, `D:` is the drive letter of
the partition.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html "Previous: Tablespaces") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html "Up: Tablespaces") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html "Next: File-Per-Table Tablespaces")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html)

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