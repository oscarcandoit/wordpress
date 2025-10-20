---
url: https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html
scraped_at: 2025-10-20T03:13:03.280Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html "Hide Sidebar")

[Previous: Foreign Key Optimization](https://dev.mysql.com/doc/refman/8.0/en/foreign-key-optimization.html "Previous: Foreign Key Optimization")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes")[Next: Multiple-Column Indexes](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html "Next: Multiple-Column Indexes")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/column-indexes.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/column-indexes.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/column-indexes.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/column-indexes.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/column-indexes.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/column-indexes.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/column-indexes.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/column-indexes.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)  /

Column Indexes


### 10.3.5 Column Indexes

The most common type of index involves a single column, storing
copies of the values from that column in a data structure,
allowing fast lookups for the rows with the corresponding column
values. The B-tree data structure lets the index quickly find a
specific value, a set of values, or a range of values,
corresponding to operators such as `=`,
`>`, `≤`,
`BETWEEN`, `IN`, and so on, in
a `WHERE` clause.


The maximum number of indexes per table and the maximum index
length is defined per storage engine. See
[Chapter 17, _The InnoDB Storage Engine_](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine"), and
[Chapter 18, _Alternative Storage Engines_](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html "Chapter 18 Alternative Storage Engines"). All storage engines support
at least 16 indexes per table and a total index length of at
least 256 bytes. Most storage engines have higher limits.


For additional information about column indexes, see
[Section 15.1.15, “CREATE INDEX Statement”](https://dev.mysql.com/doc/refman/8.0/en/create-index.html "15.1.15 CREATE INDEX Statement").

- [Index Prefixes](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html#column-indexes-prefix "Index Prefixes")

- [FULLTEXT Indexes](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html#column-indexes-fulltext "FULLTEXT Indexes")

- [Spatial Indexes](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html#column-indexes-spatial "Spatial Indexes")

- [Indexes in the MEMORY Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html#column-indexes-memory-storage-engine "Indexes in the MEMORY Storage Engine")


#### Index Prefixes

With
`col_name(N)`
syntax in an index specification for a string column, you can
create an index that uses only the first
_`N`_ characters of the column.
Indexing only a prefix of column values in this way can make
the index file much smaller. When you index a
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") or
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") column, you
_must_ specify a prefix length for the
index. For example:


```sql
CREATE TABLE test (blob_col BLOB, INDEX(blob_col(10)));
```

Prefixes can be up to 767 bytes long for
`InnoDB` tables that use the
`[REDUNDANT](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_redundant_row_format "redundant row format")`
or
`[COMPACT](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_compact_row_format "compact row format")`
row format. The prefix length limit is 3072 bytes for
`InnoDB` tables that use the
`[DYNAMIC](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_dynamic_row_format "dynamic row format")`
or
`[COMPRESSED](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_compressed_row_format "compressed row format")`
row format. For MyISAM tables, the prefix length limit is 1000
bytes.

Note

Prefix limits are measured in bytes, whereas the prefix
length in [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"),
[`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement"), and
[`CREATE INDEX`](https://dev.mysql.com/doc/refman/8.0/en/create-index.html "15.1.15 CREATE INDEX Statement") statements is
interpreted as number of characters for nonbinary string
types ( [`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types")) and number of bytes for
binary string types ( [`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"),
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"),
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types")). Take this into account
when specifying a prefix length for a nonbinary string
column that uses a multibyte character set.

If a search term exceeds the index prefix length, the index is
used to exclude non-matching rows, and the remaining rows are
examined for possible matches.


For additional information about index prefixes, see
[Section 15.1.15, “CREATE INDEX Statement”](https://dev.mysql.com/doc/refman/8.0/en/create-index.html "15.1.15 CREATE INDEX Statement").

#### FULLTEXT Indexes

`FULLTEXT` indexes are used for full-text
searches. Only the [`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") and
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine") storage engines support
`FULLTEXT` indexes and only for
[`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"), and
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns. Indexing always
takes place over the entire column and column prefix indexing
is not supported. For details, see
[Section 14.9, “Full-Text Search Functions”](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html "14.9 Full-Text Search Functions").


Optimizations are applied to certain kinds of
`FULLTEXT` queries against single
`InnoDB` tables. Queries with these
characteristics are particularly efficient:

- `FULLTEXT` queries that only return the
document ID, or the document ID and the search rank.


- `FULLTEXT` queries that sort the matching
rows in descending order of score and apply a
`LIMIT` clause to take the top N matching
rows. For this optimization to apply, there must be no
`WHERE` clauses and only a single
`ORDER BY` clause in descending order.


- `FULLTEXT` queries that retrieve only the
`COUNT(*)` value of rows matching a
search term, with no additional `WHERE`
clauses. Code the `WHERE` clause as
`WHERE MATCH(text)
                AGAINST
                ('other_text')`,
without any `> 0` comparison operator.


For queries that contain full-text expressions, MySQL
evaluates those expressions during the optimization phase of
query execution. The optimizer does not just look at full-text
expressions and make estimates, it actually evaluates them in
the process of developing an execution plan.


An implication of this behavior is that
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") for full-text queries
is typically slower than for non-full-text queries for which
no expression evaluation occurs during the optimization phase.


[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") for full-text queries
may show `Select tables optimized away` in
the `Extra` column due to matching occurring
during optimization; in this case, no table access need occur
during later execution.

#### Spatial Indexes

You can create indexes on spatial data types.
`MyISAM` and `InnoDB`
support R-tree indexes on spatial types. Other storage engines
use B-trees for indexing spatial types (except for
`ARCHIVE`, which does not support spatial
type indexing).

#### Indexes in the MEMORY Storage Engine

The `MEMORY` storage engine uses
`HASH` indexes by default, but also supports
`BTREE` indexes.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/foreign-key-optimization.html "Previous: Foreign Key Optimization") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html "Next: Multiple-Column Indexes")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html)

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