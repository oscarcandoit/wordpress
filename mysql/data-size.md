---
url: https://dev.mysql.com/doc/refman/8.0/en/data-size.html
scraped_at: 2025-10-20T03:14:22.719Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/data-size.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/data-size.html "Hide Sidebar")

[Previous: Optimizing Database Structure](https://dev.mysql.com/doc/refman/8.0/en/optimizing-database-structure.html "Previous: Optimizing Database Structure")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimizing Database Structure](https://dev.mysql.com/doc/refman/8.0/en/optimizing-database-structure.html "Up: Optimizing Database Structure")[Next: Optimizing MySQL Data Types](https://dev.mysql.com/doc/refman/8.0/en/optimize-data-types.html "Next: Optimizing MySQL Data Types")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/data-size.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/data-size.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/data-size.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/data-size.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/data-size.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/data-size.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/data-size.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/data-size.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/data-size.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/data-size.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/data-size.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/data-size.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/data-size.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/data-size.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimizing Database Structure](https://dev.mysql.com/doc/refman/8.0/en/optimizing-database-structure.html)  /

Optimizing Data Size


### 10.4.1 Optimizing Data Size

Design your tables to minimize their space on the disk. This can
result in huge improvements by reducing the amount of data
written to and read from disk. Smaller tables normally require
less main memory while their contents are being actively
processed during query execution. Any space reduction for table
data also results in smaller indexes that can be processed
faster.


MySQL supports many different storage engines (table types) and
row formats. For each table, you can decide which storage and
indexing method to use. Choosing the proper table format for
your application can give you a big performance gain. See
[Chapter 17, _The InnoDB Storage Engine_](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine"), and
[Chapter 18, _Alternative Storage Engines_](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html "Chapter 18 Alternative Storage Engines").


You can get better performance for a table and minimize storage
space by using the techniques listed here:

- [Table Columns](https://dev.mysql.com/doc/refman/8.0/en/data-size.html#data-size-table-columns "Table Columns")

- [Row Format](https://dev.mysql.com/doc/refman/8.0/en/data-size.html#data-size-row-format "Row Format")

- [Indexes](https://dev.mysql.com/doc/refman/8.0/en/data-size.html#data-size-indexes "Indexes")

- [Joins](https://dev.mysql.com/doc/refman/8.0/en/data-size.html#data-size-joins "Joins")

- [Normalization](https://dev.mysql.com/doc/refman/8.0/en/data-size.html#data-size-normalization "Normalization")


#### Table Columns

- Use the most efficient (smallest) data types possible.
MySQL has many specialized types that save disk space and
memory. For example, use the smaller integer types if
possible to get smaller tables.
[`MEDIUMINT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT") is often a better
choice than [`INT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT") because a
[`MEDIUMINT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT") column uses 25%
less space.


- Declare columns to be `NOT NULL` if
possible. It makes SQL operations faster, by enabling
better use of indexes and eliminating overhead for testing
whether each value is `NULL`. You also
save some storage space, one bit per column. If you really
need `NULL` values in your tables, use
them. Just avoid the default setting that allows
`NULL` values in every column.


#### Row Format

- `InnoDB` tables are created using the
`DYNAMIC` row format by default. To use a
row format other than `DYNAMIC`,
configure
[`innodb_default_row_format`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_default_row_format),
or specify the `ROW_FORMAT` option
explicitly in a [`CREATE\\
                TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") or [`ALTER\\
                TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") statement.



The compact family of row formats, which includes
`COMPACT`, `DYNAMIC`,
and `COMPRESSED`, decreases row storage
space at the cost of increasing CPU use for some
operations. If your workload is a typical one that is
limited by cache hit rates and disk speed it is likely to
be faster. If it is a rare case that is limited by CPU
speed, it might be slower.



The compact family of row formats also optimizes
[`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") column storage when
using a variable-length character set such as
`utf8mb3` or `utf8mb4`.
With `ROW_FORMAT=REDUNDANT`,
`CHAR(N)`
occupies _`N`_ × the maximum
byte length of the character set. Many languages can be
written primarily using single-byte
`utf8mb3` or `utf8mb4`
characters, so a fixed storage length often wastes space.
With the compact family of rows formats,
`InnoDB` allocates a variable amount of
storage in the range of _`N`_ to
_`N`_ × the maximum byte
length of the character set for these columns by stripping
trailing spaces. The minimum storage length is
_`N`_ bytes to facilitate in-place
updates in typical cases. For more information, see
[Section 17.10, “InnoDB Row Formats”](https://dev.mysql.com/doc/refman/8.0/en/innodb-row-format.html "17.10 InnoDB Row Formats").


- To minimize space even further by storing table data in
compressed form, specify
`ROW_FORMAT=COMPRESSED` when creating
`InnoDB` tables, or run the
[**myisampack**](https://dev.mysql.com/doc/refman/8.0/en/myisampack.html "6.6.6 myisampack — Generate Compressed, Read-Only MyISAM Tables") command on an existing
`MyISAM` table.
( `InnoDB` compressed tables are readable
and writable, while `MyISAM` compressed
tables are read-only.)


- For `MyISAM` tables, if you do not have
any variable-length columns
( [`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types"), or
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns), a fixed-size
row format is used. This is faster but may waste some
space. See [Section 18.2.3, “MyISAM Table Storage Formats”](https://dev.mysql.com/doc/refman/8.0/en/myisam-table-formats.html "18.2.3 MyISAM Table Storage Formats"). You can
hint that you want to have fixed length rows even if you
have [`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") columns with
the [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") option
`ROW_FORMAT=FIXED`.


#### Indexes

- The primary index of a table should be as short as
possible. This makes identification of each row easy and
efficient. For `InnoDB` tables, the
primary key columns are duplicated in each secondary index
entry, so a short primary key saves considerable space if
you have many secondary indexes.


- Create only the indexes that you need to improve query
performance. Indexes are good for retrieval, but slow down
insert and update operations. If you access a table mostly
by searching on a combination of columns, create a single
composite index on them rather than a separate index for
each column. The first part of the index should be the
column most used. If you _always_ use
many columns when selecting from the table, the first
column in the index should be the one with the most
duplicates, to obtain better compression of the index.


- If it is very likely that a long string column has a
unique prefix on the first number of characters, it is
better to index only this prefix, using MySQL's
support for creating an index on the leftmost part of the
column (see [Section 15.1.15, “CREATE INDEX Statement”](https://dev.mysql.com/doc/refman/8.0/en/create-index.html "15.1.15 CREATE INDEX Statement")). Shorter
indexes are faster, not only because they require less
disk space, but because they also give you more hits in
the index cache, and thus fewer disk seeks. See
[Section 7.1.1, “Configuring the Server”](https://dev.mysql.com/doc/refman/8.0/en/server-configuration.html "7.1.1 Configuring the Server").


#### Joins

- In some circumstances, it can be beneficial to split into
two a table that is scanned very often. This is especially
true if it is a dynamic-format table and it is possible to
use a smaller static format table that can be used to find
the relevant rows when scanning the table.


- Declare columns with identical information in different
tables with identical data types, to speed up joins based
on the corresponding columns.


- Keep column names simple, so that you can use the same
name across different tables and simplify join queries.
For example, in a table named `customer`,
use a column name of `name` instead of
`customer_name`. To make your names
portable to other SQL servers, consider keeping them
shorter than 18 characters.


#### Normalization

- Normally, try to keep all data nonredundant (observing
what is referred to in database theory as
third normal form).
Instead of repeating lengthy values such as names and
addresses, assign them unique IDs, repeat these IDs as
needed across multiple smaller tables, and join the tables
in queries by referencing the IDs in the join clause.


- If speed is more important than disk space and the
maintenance costs of keeping multiple copies of data, for
example in a business intelligence scenario where you
analyze all the data from large tables, you can relax the
normalization rules, duplicating information or creating
summary tables to gain more speed.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/optimizing-database-structure.html "Previous: Optimizing Database Structure") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/optimizing-database-structure.html "Up: Optimizing Database Structure") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/optimize-data-types.html "Next: Optimizing MySQL Data Types")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/data-size.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/data-size.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/data-size.html)

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