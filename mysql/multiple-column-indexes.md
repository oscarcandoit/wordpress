---
url: https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html
scraped_at: 2025-10-20T03:12:56.762Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html "Hide Sidebar")

[Previous: Column Indexes](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html "Previous: Column Indexes")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes")[Next: Verifying Index Usage](https://dev.mysql.com/doc/refman/8.0/en/verifying-index-usage.html "Next: Verifying Index Usage")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/multiple-column-indexes.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/multiple-column-indexes.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/multiple-column-indexes.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/multiple-column-indexes.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/multiple-column-indexes.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/multiple-column-indexes.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/multiple-column-indexes.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/multiple-column-indexes.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)  /

Multiple-Column Indexes


### 10.3.6 Multiple-Column Indexes

MySQL can create composite indexes (that is, indexes on multiple
columns). An index may consist of up to 16 columns. For certain
data types, you can index a prefix of the column (see
[Section 10.3.5, “Column Indexes”](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html "10.3.5 Column Indexes")).


MySQL can use multiple-column indexes for queries that test all
the columns in the index, or queries that test just the first
column, the first two columns, the first three columns, and so
on. If you specify the columns in the right order in the index
definition, a single composite index can speed up several kinds
of queries on the same table.


A multiple-column index can be considered a sorted array, the
rows of which contain values that are created by concatenating
the values of the indexed columns.

Note

As an alternative to a composite index, you can introduce a
column that is “hashed” based on information from
other columns. If this column is short, reasonably unique, and
indexed, it might be faster than a “wide” index
on many columns. In MySQL, it is very easy to use this extra
column:


```sql
SELECT * FROM tbl_name
  WHERE hash_col=MD5(CONCAT(val1,val2))
  AND col1=val1 AND col2=val2;
```

Suppose that a table has the following specification:


```sql
CREATE TABLE test (
    id         INT NOT NULL,
    last_name  CHAR(30) NOT NULL,
    first_name CHAR(30) NOT NULL,
    PRIMARY KEY (id),
    INDEX name (last_name,first_name)
);
```

The `name` index is an index over the
`last_name` and `first_name`
columns. The index can be used for lookups in queries that
specify values in a known range for combinations of
`last_name` and `first_name`
values. It can also be used for queries that specify just a
`last_name` value because that column is a
leftmost prefix of the index (as described later in this
section). Therefore, the `name` index is used
for lookups in the following queries:


```sql
SELECT * FROM test WHERE last_name='Jones';

SELECT * FROM test
  WHERE last_name='Jones' AND first_name='John';

SELECT * FROM test
  WHERE last_name='Jones'
  AND (first_name='John' OR first_name='Jon');

SELECT * FROM test
  WHERE last_name='Jones'
  AND first_name >='M' AND first_name < 'N';
```

However, the `name` index is
_not_ used for lookups in the following
queries:


```sql
SELECT * FROM test WHERE first_name='John';

SELECT * FROM test
  WHERE last_name='Jones' OR first_name='John';
```

Suppose that you issue the following
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement:


```sql
SELECT * FROM tbl_name
  WHERE col1=val1 AND col2=val2;
```

If a multiple-column index exists on `col1` and
`col2`, the appropriate rows can be fetched
directly. If separate single-column indexes exist on
`col1` and `col2`, the
optimizer attempts to use the Index Merge optimization (see
[Section 10.2.1.3, “Index Merge Optimization”](https://dev.mysql.com/doc/refman/8.0/en/index-merge-optimization.html "10.2.1.3 Index Merge Optimization")), or attempts to find
the most restrictive index by deciding which index excludes more
rows and using that index to fetch the rows.


If the table has a multiple-column index, any leftmost prefix of
the index can be used by the optimizer to look up rows. For
example, if you have a three-column index on `(col1,
        col2, col3)`, you have indexed search capabilities on
`(col1)`, `(col1, col2)`, and
`(col1, col2, col3)`.


MySQL cannot use the index to perform lookups if the columns do
not form a leftmost prefix of the index. Suppose that you have
the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements shown here:


```sql
SELECT * FROM tbl_name WHERE col1=val1;
SELECT * FROM tbl_name WHERE col1=val1 AND col2=val2;

SELECT * FROM tbl_name WHERE col2=val2;
SELECT * FROM tbl_name WHERE col2=val2 AND col3=val3;
```

If an index exists on `(col1, col2, col3)`,
only the first two queries use the index. The third and fourth
queries do involve indexed columns, but do not use an index to
perform lookups because `(col2)` and
`(col2, col3)` are not leftmost prefixes of
`(col1, col2, col3)`.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html "Previous: Column Indexes") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/verifying-index-usage.html "Next: Verifying Index Usage")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html)

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