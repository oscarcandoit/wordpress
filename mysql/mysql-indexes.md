---
url: https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html
scraped_at: 2025-10-20T03:12:53.677Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html "Hide Sidebar")

[Previous: Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Previous: Optimization and Indexes")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes")[Next: Primary Key Optimization](https://dev.mysql.com/doc/refman/8.0/en/primary-key-optimization.html "Next: Primary Key Optimization")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/mysql-indexes.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/mysql-indexes.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/mysql-indexes.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/mysql-indexes.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/mysql-indexes.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/mysql-indexes.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/mysql-indexes.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/mysql-indexes.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)  /

How MySQL Uses Indexes


### 10.3.1 How MySQL Uses Indexes

Indexes are used to find rows with specific column values
quickly. Without an index, MySQL must begin with the first row
and then read through the entire table to find the relevant
rows. The larger the table, the more this costs. If the table
has an index for the columns in question, MySQL can quickly
determine the position to seek to in the middle of the data file
without having to look at all the data. This is much faster than
reading every row sequentially.


Most MySQL indexes ( `PRIMARY KEY`,
`UNIQUE`, `INDEX`, and
`FULLTEXT`) are stored in
[B-trees](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_b_tree "B-tree"). Exceptions: Indexes
on spatial data types use R-trees; `MEMORY`
tables also support [hash\\
indexes](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_hash_index "hash index"); `InnoDB` uses inverted lists
for `FULLTEXT` indexes.


In general, indexes are used as described in the following
discussion. Characteristics specific to hash indexes (as used in
`MEMORY` tables) are described in
[Section 10.3.9, “Comparison of B-Tree and Hash Indexes”](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html "10.3.9 Comparison of B-Tree and Hash Indexes").


MySQL uses indexes for these operations:

- To find the rows matching a `WHERE` clause
quickly.


- To eliminate rows from consideration. If there is a choice
between multiple indexes, MySQL normally uses the index that
finds the smallest number of rows (the most
[selective](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_selectivity "selectivity") index).


- If the table has a multiple-column index, any leftmost
prefix of the index can be used by the optimizer to look up
rows. For example, if you have a three-column index on
`(col1, col2, col3)`, you have indexed
search capabilities on `(col1)`,
`(col1, col2)`, and `(col1, col2,
              col3)`. For more information, see
[Section 10.3.6, “Multiple-Column Indexes”](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html "10.3.6 Multiple-Column Indexes").


- To retrieve rows from other tables when performing joins.
MySQL can use indexes on columns more efficiently if they
are declared as the same type and size. In this context,
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") and
[`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") are considered the same
if they are declared as the same size. For example,
`VARCHAR(10)` and
`CHAR(10)` are the same size, but
`VARCHAR(10)` and
`CHAR(15)` are not.



For comparisons between nonbinary string columns, both
columns should use the same character set. For example,
comparing a `utf8mb4` column with a
`latin1` column precludes use of an index.



Comparison of dissimilar columns (comparing a string column
to a temporal or numeric column, for example) may prevent
use of indexes if values cannot be compared directly without
conversion. For a given value such as `1`
in the numeric column, it might compare equal to any number
of values in the string column such as
`'1'`, `' 1'`,
`'00001'`, or `'01.e1'`.
This rules out use of any indexes for the string column.


- To find the [`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min) or
[`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max) value for a specific
indexed column _`key_col`_. This is
optimized by a preprocessor that checks whether you are
using `WHERE key_part_N =
              constant` on all key
parts that occur before _`key_col`_
in the index. In this case, MySQL does a single key lookup
for each [`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min) or
[`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max) expression and replaces
it with a constant. If all expressions are replaced with
constants, the query returns at once. For example:



```sql
SELECT MIN(key_part2),MAX(key_part2)
    FROM tbl_name WHERE key_part1=10;
```

- To sort or group a table if the sorting or grouping is done
on a leftmost prefix of a usable index (for example,
`ORDER BY key_part1,
              key_part2`). If all key
parts are followed by `DESC`, the key is
read in reverse order. (Or, if the index is a descending
index, the key is read in forward order.) See
[Section 10.2.1.16, “ORDER BY Optimization”](https://dev.mysql.com/doc/refman/8.0/en/order-by-optimization.html "10.2.1.16 ORDER BY Optimization"),
[Section 10.2.1.17, “GROUP BY Optimization”](https://dev.mysql.com/doc/refman/8.0/en/group-by-optimization.html "10.2.1.17 GROUP BY Optimization"), and
[Section 10.3.13, “Descending Indexes”](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html "10.3.13 Descending Indexes").


- In some cases, a query can be optimized to retrieve values
without consulting the data rows. (An index that provides
all the necessary results for a query is called a
[covering index](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_covering_index "covering index").)
If a query uses from a table only columns that are included
in some index, the selected values can be retrieved from the
index tree for greater speed:



```sql
SELECT key_part3 FROM tbl_name
    WHERE key_part1=1
```


Indexes are less important for queries on small tables, or big
tables where report queries process most or all of the rows.
When a query needs to access most of the rows, reading
sequentially is faster than working through an index. Sequential
reads minimize disk seeks, even if not all the rows are needed
for the query. See [Section 10.2.1.23, “Avoiding Full Table Scans”](https://dev.mysql.com/doc/refman/8.0/en/table-scan-avoidance.html "10.2.1.23 Avoiding Full Table Scans") for
details.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Previous: Optimization and Indexes") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/primary-key-optimization.html "Next: Primary Key Optimization")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html)

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