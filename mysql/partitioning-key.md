---
url: https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html
scraped_at: 2025-10-20T03:04:49.265Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html "Hide Sidebar")

[Previous: LINEAR HASH Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-linear-hash.html "Previous: LINEAR HASH Partitioning")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Partitioning Types](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "Up: Partitioning Types")[Next: Subpartitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-subpartitions.html "Next: Subpartitioning")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/partitioning-key.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/partitioning-key.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/partitioning-key.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/partitioning-key.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/partitioning-key.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/partitioning-key.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/partitioning-key.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/partitioning-key.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html)  / [Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)  /
[Partitioning Types](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html)  /

KEY Partitioning


### 26.2.5 KEY Partitioning

Partitioning by key is similar to partitioning by hash, except
that where hash partitioning employs a user-defined expression,
the hashing function for key partitioning is supplied by the
MySQL server. NDB Cluster uses
[`MD5()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_md5) for this purpose; for
tables using other storage engines, the server employs its own
internal hashing function.


The syntax rules for `CREATE TABLE ... PARTITION BY
        KEY` are similar to those for creating a table that is
partitioned by hash. The major differences are listed here:

- `KEY` is used rather than
`HASH`.


- `KEY` takes only a list of zero or more
column names. Any columns used as the partitioning key must
comprise part or all of the table's primary key, if the
table has one. Where no column name is specified as the
partitioning key, the table's primary key is used, if
there is one. For example, the following
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement is
valid in MySQL 8.0:



```sql
CREATE TABLE k1 (
      id INT NOT NULL PRIMARY KEY,
      name VARCHAR(20)
)
PARTITION BY KEY()
PARTITIONS 2;
```



If there is no primary key but there is a unique key, then
the unique key is used for the partitioning key:



```sql
CREATE TABLE k1 (
      id INT NOT NULL,
      name VARCHAR(20),
      UNIQUE KEY (id)
)
PARTITION BY KEY()
PARTITIONS 2;
```



However, if the unique key column were not defined as
`NOT NULL`, then the previous statement
would fail.



In both of these cases, the partitioning key is the
`id` column, even though it is not shown in
the output of [`SHOW CREATE\\
              TABLE`](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html "15.7.7.10 SHOW CREATE TABLE Statement") or in the
`PARTITION_EXPRESSION` column of the
Information Schema [`PARTITIONS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-partitions-table.html "28.3.21 The INFORMATION_SCHEMA PARTITIONS Table")
table.



Unlike the case with other partitioning types, columns used
for partitioning by `KEY` are not
restricted to integer or `NULL` values. For
example, the following [`CREATE\\
              TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement is valid:



```sql
CREATE TABLE tm1 (
      s1 CHAR(32) PRIMARY KEY
)
PARTITION BY KEY(s1)
PARTITIONS 10;
```



The preceding statement would _not_ be
valid, were a different partitioning type to be specified.
(In this case, simply using `PARTITION BY
              KEY()` would also be valid and have the same effect
as `PARTITION BY KEY(s1)`, since
`s1` is the table's primary key.)



For additional information about this issue, see
[Section 26.6, “Restrictions and Limitations on Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-limitations.html "26.6 Restrictions and Limitations on Partitioning").



Columns with index prefixes are not supported in
partitioning keys. This means that
[`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"), and
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types") columns can be used
in a partitioning key, as long as they do not employ
prefixes; because a prefix must be specified for
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") and
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns in index
definitions, it is not possible to use columns of these two
types in partitioning keys. Prior to MySQL 8.0.21, columns
using prefixes were permitted when creating, altering, or
upgrading a partitioned table, even though they were not
included in the table's partitioning key; in MySQL
8.0.21 and later, this permissive behavior is deprecated,
and the server displays appropriate warnings or errors when
one or more such columns are used. See
[Column index prefixes not supported for key partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-limitations.html#partitioning-limitations-prefixes "Column index prefixes not supported for key partitioning"), for
more information and examples.





Note





Tables using the [`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0") storage
engine are implicitly partitioned by
`KEY`, using the table's primary key
as the partitioning key (as with other MySQL storage
engines). In the event that the NDB Cluster table has no
explicit primary key, the “hidden” primary
key generated by the [`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0")
storage engine for each NDB Cluster table is used as the
partitioning key.





If you define an explicit partitioning scheme for an
[`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0") table, the table must
have an explicit primary key, and any columns used in the
partitioning expression must be part of this key. However,
if the table uses an “empty” partitioning
expression—that is, `PARTITION BY
                KEY()` with no column references—then no
explicit primary key is required.





You can observe this partitioning using the
[**ndb\_desc**](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster-programs-ndb-desc.html "25.5.9 ndb_desc — Describe NDB Tables") utility (with the
`-p` option).







Important





For a key-partitioned table, you cannot execute an
`ALTER TABLE DROP PRIMARY KEY`, as doing
so generates the error ERROR 1466 (HY000):
Field in list of fields for partition function not found
in table. This is not an issue for NDB Cluster
tables which are partitioned by `KEY`; in
such cases, the table is reorganized using the
“hidden” primary key as the table's new
partitioning key. See [Chapter 25, _MySQL NDB Cluster 8.0_](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0").


It is also possible to partition a table by linear key. Here is
a simple example:


```sql
CREATE TABLE tk (
    col1 INT NOT NULL,
    col2 CHAR(5),
    col3 DATE
)
PARTITION BY LINEAR KEY (col1)
PARTITIONS 3;
```

The `LINEAR` keyword has the same effect on
`KEY` partitioning as it does on
`HASH` partitioning, with the partition number
being derived using a powers-of-two algorithm rather than modulo
arithmetic. See [Section 26.2.4.1, “LINEAR HASH Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-linear-hash.html "26.2.4.1 LINEAR HASH Partitioning"), for
a description of this algorithm and its implications.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/partitioning-linear-hash.html "Previous: LINEAR HASH Partitioning") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "Up: Partitioning Types") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/partitioning-subpartitions.html "Next: Subpartitioning")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html)

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