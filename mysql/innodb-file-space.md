---
url: https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html
scraped_at: 2025-10-20T03:14:53.761Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html "Hide Sidebar")

[Previous: InnoDB Disk I/O](https://dev.mysql.com/doc/refman/8.0/en/innodb-disk-io.html "Previous: InnoDB Disk I/O")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: InnoDB Disk I/O and File Space Management](https://dev.mysql.com/doc/refman/8.0/en/innodb-disk-management.html "Up: InnoDB Disk I/O and File Space Management")[Next: InnoDB Checkpoints](https://dev.mysql.com/doc/refman/8.0/en/innodb-checkpoints.html "Next: InnoDB Checkpoints")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/innodb-file-space.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/innodb-file-space.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/innodb-file-space.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/innodb-file-space.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/innodb-file-space.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/innodb-file-space.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/innodb-file-space.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/innodb-file-space.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html)  / [The InnoDB Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)  /
[InnoDB Disk I/O and File Space Management](https://dev.mysql.com/doc/refman/8.0/en/innodb-disk-management.html)  /

File Space Management


### 17.11.2 File Space Management

The data files that you define in the configuration file using the
[`innodb_data_file_path`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_data_file_path)
configuration option form the `InnoDB` [system tablespace](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_system_tablespace "system tablespace").
The files are logically concatenated to form the system
tablespace. There is no striping in use. You cannot define where
within the system tablespace your tables are allocated. In a newly
created system tablespace, `InnoDB` allocates
space starting from the first data file.


To avoid the issues that come with storing all tables and indexes
inside the system tablespace, you can enable the
[`innodb_file_per_table`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_file_per_table)
configuration option (the default), which stores each newly
created table in a separate tablespace file (with extension
`.ibd`). For tables stored this way, there is
less fragmentation within the disk file, and when the table is
truncated, the space is returned to the operating system rather
than still being reserved by InnoDB within the system tablespace.
For more information, see
[Section 17.6.3.2, “File-Per-Table Tablespaces”](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html "17.6.3.2 File-Per-Table Tablespaces").


You can also store tables in
[general\\
tablespaces](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_general_tablespace "general tablespace"). General tablespaces are shared tablespaces
created using [`CREATE TABLESPACE`](https://dev.mysql.com/doc/refman/8.0/en/create-tablespace.html "15.1.21 CREATE TABLESPACE Statement")
syntax. They can be created outside of the MySQL data directory,
are capable of holding multiple tables, and support tables of all
row formats. For more information, see
[Section 17.6.3.3, “General Tablespaces”](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html "17.6.3.3 General Tablespaces").

#### Pages, Extents, Segments, and Tablespaces

Each tablespace consists of database
[pages](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_page "page"). Every tablespace in a
MySQL instance has the same [page\\
size](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_page_size "page size"). By default, all tablespaces have a page size of
16KB; you can reduce the page size to 8KB or 4KB by specifying
the [`innodb_page_size`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size) option
when you create the MySQL instance. You can also increase the
page size to 32KB or 64KB. For more information, refer to the
[`innodb_page_size`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size) documentation.


The pages are grouped into
[extents](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_extent "extent") of size 1MB for pages
up to 16KB in size (64 consecutive 16KB pages, or 128 8KB pages,
or 256 4KB pages). For a page size of 32KB, extent size is 2MB.
For page size of 64KB, extent size is 4MB. The
“files” inside a tablespace are called
[segments](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_segment "segment") in
`InnoDB`. (These segments are different from
the [rollback\\
segment](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_rollback_segment "rollback segment"), which actually contains many tablespace
segments.)


When a segment grows inside the tablespace,
`InnoDB` allocates the first 32 pages to it one
at a time. After that, `InnoDB` starts to
allocate whole extents to the segment. `InnoDB`
can add up to 4 extents at a time to a large segment to ensure
good sequentiality of data.


Two segments are allocated for each index in
`InnoDB`. One is for nonleaf nodes of the
[B-tree](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_b_tree "B-tree"), the other is for the
leaf nodes. Keeping the leaf nodes contiguous on disk enables
better sequential I/O operations, because these leaf nodes
contain the actual table data.


Some pages in the tablespace contain bitmaps of other pages, and
therefore a few extents in an `InnoDB`
tablespace cannot be allocated to segments as a whole, but only
as individual pages.


When you ask for available free space in the tablespace by
issuing a [`SHOW TABLE STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement")
statement, `InnoDB` reports the extents that
are definitely free in the tablespace. `InnoDB`
always reserves some extents for cleanup and other internal
purposes; these reserved extents are not included in the free
space.


When you delete data from a table, `InnoDB`
contracts the corresponding B-tree indexes. Whether the freed
space becomes available for other users depends on whether the
pattern of deletes frees individual pages or extents to the
tablespace. Dropping a table or deleting all rows from it is
guaranteed to release the space to other users, but remember
that deleted rows are physically removed only by the
[purge](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_purge "purge") operation, which happens
automatically some time after they are no longer needed for
transaction rollbacks or consistent reads. (See
[Section 17.3, “InnoDB Multi-Versioning”](https://dev.mysql.com/doc/refman/8.0/en/innodb-multi-versioning.html "17.3 InnoDB Multi-Versioning").)

#### Configuring the Percentage of Reserved File Segment Pages

The
[`innodb_segment_reserve_factor`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_segment_reserve_factor)
variable, introduced in MySQL 8.0.26, is an advanced feature
that permits defining the percentage of tablespace file segment
pages reserved as empty pages. A percentage of pages are
reserved for future growth so that pages in the B-tree can be
allocated contiguously. The ability to modify the percentage of
reserved pages permits fine-tuning `InnoDB` to
address issues of data fragmentation or inefficient use of
storage space.


The setting is applicable to file-per-table and general
tablespaces. The
[`innodb_segment_reserve_factor`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_segment_reserve_factor)
default setting is 12.5 percent, which is the same percentage of
pages reserved in previous MySQL releases.


The
[`innodb_segment_reserve_factor`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_segment_reserve_factor)
variable is dynamic and can be configured using a
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set.html "13.3.6 The SET Type") statement. For example:

```sql
mysql> SET GLOBAL innodb_segment_reserve_factor=10;
```

#### How Pages Relate to Table Rows

For for 4KB, 8KB, 16KB, and 32KB
[`innodb_page_size`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size) settings, the
maximum row length is slightly less than half a database page
size. For example, the maximum row length is slightly less than
8KB for the default 16KB `InnoDB` page size.
For a 64KB [`innodb_page_size`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_page_size)
setting, the maximum row length is slightly less than 16KB.


If a row does not exceed the maximum row length, all of it is
stored locally within the page. If a row exceeds the maximum row
length,
[variable-length\\
columns](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_variable_length_type "variable-length type") are chosen for external off-page storage until
the row fits within the maximum row length limit. External
off-page storage for variable-length columns differs by row
format:

- _COMPACT and REDUNDANT Row Formats_


When a variable-length column is chosen for external
off-page storage, `InnoDB` stores the first
768 bytes locally in the row, and the rest externally into
overflow pages. Each such column has its own list of
overflow pages. The 768-byte prefix is accompanied by a
20-byte value that stores the true length of the column and
points into the overflow list where the rest of the value is
stored. See [Section 17.10, “InnoDB Row Formats”](https://dev.mysql.com/doc/refman/8.0/en/innodb-row-format.html "17.10 InnoDB Row Formats").


- _DYNAMIC and COMPRESSED Row Formats_


When a variable-length column is chosen for external
off-page storage, `InnoDB` stores a 20-byte
pointer locally in the row, and the rest externally into
overflow pages. See [Section 17.10, “InnoDB Row Formats”](https://dev.mysql.com/doc/refman/8.0/en/innodb-row-format.html "17.10 InnoDB Row Formats").


[`LONGBLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") and
[`LONGTEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns
must be less than 4GB, and the total row length, including
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") and
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns, must be less than
4GB.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/innodb-disk-io.html "Previous: InnoDB Disk I/O") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/innodb-disk-management.html "Up: InnoDB Disk I/O and File Space Management") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/innodb-checkpoints.html "Next: InnoDB Checkpoints")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html)

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