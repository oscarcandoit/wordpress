---
url: https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html
scraped_at: 2025-10-20T03:13:11.338Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html "Hide Sidebar")

[Previous: Invisible Indexes](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html "Previous: Invisible Indexes")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes")[Next: Indexed Lookups from TIMESTAMP Columns](https://dev.mysql.com/doc/refman/8.0/en/timestamp-lookups.html "Next: Indexed Lookups from TIMESTAMP Columns")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/descending-indexes.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/descending-indexes.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/descending-indexes.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/descending-indexes.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/descending-indexes.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/descending-indexes.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/descending-indexes.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)  /

Descending Indexes


### 10.3.13 Descending Indexes

MySQL supports descending indexes: `DESC` in an
index definition is no longer ignored but causes storage of key
values in descending order. Previously, indexes could be scanned
in reverse order but at a performance penalty. A descending
index can be scanned in forward order, which is more efficient.
Descending indexes also make it possible for the optimizer to
use multiple-column indexes when the most efficient scan order
mixes ascending order for some columns and descending order for
others.


Consider the following table definition, which contains two
columns and four two-column index definitions for the various
combinations of ascending and descending indexes on the columns:


```sql
CREATE TABLE t (
  c1 INT, c2 INT,
  INDEX idx1 (c1 ASC, c2 ASC),
  INDEX idx2 (c1 ASC, c2 DESC),
  INDEX idx3 (c1 DESC, c2 ASC),
  INDEX idx4 (c1 DESC, c2 DESC)
);
```

The table definition results in four distinct indexes. The
optimizer can perform a forward index scan for each of the
`ORDER BY` clauses and need not use a
`filesort` operation:


```sql
ORDER BY c1 ASC, c2 ASC    -- optimizer can use idx1
ORDER BY c1 DESC, c2 DESC  -- optimizer can use idx4
ORDER BY c1 ASC, c2 DESC   -- optimizer can use idx2
ORDER BY c1 DESC, c2 ASC   -- optimizer can use idx3
```

Use of descending indexes is subject to these conditions:

- Descending indexes are supported only for the
`InnoDB` storage engine, with these
limitations:




- Change buffering is not supported for a secondary index
if the index contains a descending index key column or
if the primary key includes a descending index column.


- The `InnoDB` SQL parser does not use
descending indexes. For `InnoDB`
full-text search, this means that the index required on
the `FTS_DOC_ID` column of the indexed
table cannot be defined as a descending index. For more
information, see
[Section 17.6.2.4, “InnoDB Full-Text Indexes”](https://dev.mysql.com/doc/refman/8.0/en/innodb-fulltext-index.html "17.6.2.4 InnoDB Full-Text Indexes").


- Descending indexes are supported for all data types for
which ascending indexes are available.


- Descending indexes are supported for ordinary (nongenerated)
and generated columns (both `VIRTUAL` and
`STORED`).


- `DISTINCT` can use any index containing
matching columns, including descending key parts.


- Indexes that have descending key parts are not used for
[`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min)/ [`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max)
optimization of queries that invoke aggregate functions but
do not have a `GROUP BY` clause.


- Descending indexes are supported for
`BTREE` but not `HASH`
indexes. Descending indexes are not supported for
`FULLTEXT` or `SPATIAL`
indexes.



Explicitly specified `ASC` and
`DESC` designators for
`HASH`, `FULLTEXT`, and
`SPATIAL` indexes results in an error.


You can see in the **`Extra`** column of the
output of [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") that the
optimizer is able to use a descending index, as shown here:


```sql
mysql> CREATE TABLE t1 (
    -> a INT,
    -> b INT,
    -> INDEX a_desc_b_asc (a DESC, b ASC)
    -> );

mysql> EXPLAIN SELECT * FROM t1 ORDER BY a ASC\G
*************************** 1. row ***************************
           id: 1
  select_type: SIMPLE
        table: t1
   partitions: NULL
         type: index
possible_keys: NULL
          key: a_desc_b_asc
      key_len: 10
          ref: NULL
         rows: 1
     filtered: 100.00
        Extra: Backward index scan; Using index
```

In `EXPLAIN FORMAT=TREE` output, use of a
descending index is indicated by the addition of
`(reverse)` following the name of the index,
like this:


```sql
mysql> EXPLAIN FORMAT=TREE SELECT * FROM t1 ORDER BY a ASC\G
*************************** 1. row ***************************
EXPLAIN: -> Index scan on t1 using a_desc_b_asc (reverse)  (cost=0.35 rows=1)
```

See also [EXPLAIN Extra Information](https://dev.mysql.com/doc/refman/8.0/en/explain-output.html#explain-extra-information "EXPLAIN Extra Information").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html "Previous: Invisible Indexes") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/timestamp-lookups.html "Next: Indexed Lookups from TIMESTAMP Columns")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html)

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