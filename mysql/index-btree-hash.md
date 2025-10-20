---
url: https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html
scraped_at: 2025-10-20T03:13:15.227Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html "Hide Sidebar")

[Previous: InnoDB and MyISAM Index Statistics Collection](https://dev.mysql.com/doc/refman/8.0/en/index-statistics.html "Previous: InnoDB and MyISAM Index Statistics Collection")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes")[Next: Use of Index Extensions](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html "Next: Use of Index Extensions")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/index-btree-hash.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/index-btree-hash.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/index-btree-hash.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/index-btree-hash.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/index-btree-hash.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/index-btree-hash.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/index-btree-hash.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/index-btree-hash.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)  /

Comparison of B-Tree and Hash Indexes


### 10.3.9 Comparison of B-Tree and Hash Indexes

Understanding the B-tree and hash data structures can help
predict how different queries perform on different storage
engines that use these data structures in their indexes,
particularly for the `MEMORY` storage engine
that lets you choose B-tree or hash indexes.

- [B-Tree Index Characteristics](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html#btree-index-characteristics "B-Tree Index Characteristics")

- [Hash Index Characteristics](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html#hash-index-characteristics "Hash Index Characteristics")


#### B-Tree Index Characteristics

A B-tree index can be used for column comparisons in
expressions that use the
[`=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_equal),
[`>`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_greater-than),
[`>=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_greater-than-or-equal),
[`<`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_less-than),
[`<=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_less-than-or-equal),
or [`BETWEEN`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_between) operators. The index
also can be used for [`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like)
comparisons if the argument to
[`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) is a constant string that
does not start with a wildcard character. For example, the
following [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements use
indexes:


```sql
SELECT * FROM tbl_name WHERE key_col LIKE 'Patrick%';
SELECT * FROM tbl_name WHERE key_col LIKE 'Pat%_ck%';
```

In the first statement, only rows with `'Patrick'
          <= key_col <
          'Patricl'` are considered. In the second statement,
only rows with `'Pat' <=
          key_col < 'Pau'` are
considered.


The following [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements
do not use indexes:


```sql
SELECT * FROM tbl_name WHERE key_col LIKE '%Patrick%';
SELECT * FROM tbl_name WHERE key_col LIKE other_col;
```

In the first statement, the [`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like)
value begins with a wildcard character. In the second
statement, the [`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) value is not
a constant.


If you use `... LIKE
          '%string%'` and
_`string`_ is longer than three
characters, MySQL uses the Turbo
Boyer-Moore algorithm to initialize the pattern for
the string and then uses this pattern to perform the search
more quickly.


A search using `col_name IS
          NULL` employs indexes if
_`col_name`_ is indexed.


Any index that does not span all
[`AND`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_and) levels in the
`WHERE` clause is not used to optimize the
query. In other words, to be able to use an index, a prefix of
the index must be used in every
[`AND`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_and) group.


The following `WHERE` clauses use indexes:


```sql
... WHERE index_part1=1 AND index_part2=2 AND other_column=3

    /* index = 1 OR index = 2 */
... WHERE index=1 OR A=10 AND index=2

    /* optimized like "index_part1='hello'" */
... WHERE index_part1='hello' AND index_part3=5

    /* Can use index on index1 but not on index2 or index3 */
... WHERE index1=1 AND index2=2 OR index1=3 AND index3=3;
```

These `WHERE` clauses do
_not_ use indexes:


```sql
    /* index_part1 is not used */
... WHERE index_part2=1 AND index_part3=2

    /*  Index is not used in both parts of the WHERE clause  */
... WHERE index=1 OR A=10

    /* No index spans all rows  */
... WHERE index_part1=1 OR index_part2=10
```

Sometimes MySQL does not use an index, even if one is
available. One circumstance under which this occurs is when
the optimizer estimates that using the index would require
MySQL to access a very large percentage of the rows in the
table. (In this case, a table scan is likely to be much faster
because it requires fewer seeks.) However, if such a query
uses `LIMIT` to retrieve only some of the
rows, MySQL uses an index anyway, because it can much more
quickly find the few rows to return in the result.

#### Hash Index Characteristics

Hash indexes have somewhat different characteristics from
those just discussed:

- They are used only for equality comparisons that use the
`=` or `<=>`
operators (but are _very_ fast). They
are not used for comparison operators such as
`<` that find a range of values.
Systems that rely on this type of single-value lookup are
known as “key-value stores”; to use MySQL for
such applications, use hash indexes wherever possible.


- The optimizer cannot use a hash index to speed up
`ORDER BY` operations. (This type of
index cannot be used to search for the next entry in
order.)


- MySQL cannot determine approximately how many rows there
are between two values (this is used by the range
optimizer to decide which index to use). This may affect
some queries if you change a `MyISAM` or
`InnoDB` table to a hash-indexed
`MEMORY` table.


- Only whole keys can be used to search for a row. (With a
B-tree index, any leftmost prefix of the key can be used
to find rows.)


[PREV](https://dev.mysql.com/doc/refman/8.0/en/index-statistics.html "Previous: InnoDB and MyISAM Index Statistics Collection") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html "Next: Use of Index Extensions")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html)

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