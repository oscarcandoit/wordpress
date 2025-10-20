---
url: https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html
scraped_at: 2025-10-20T03:04:05.329Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html "Hide Sidebar")

[Previous: Optimizing SELECT Statements](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html "Previous: Optimizing SELECT Statements")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimizing SELECT Statements](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html "Up: Optimizing SELECT Statements")[Next: Range Optimization](https://dev.mysql.com/doc/refman/8.0/en/range-optimization.html "Next: Range Optimization")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/where-optimization.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/where-optimization.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/where-optimization.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/where-optimization.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/where-optimization.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/where-optimization.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/where-optimization.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/where-optimization.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimizing SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)  /
[Optimizing SELECT Statements](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html)  /

WHERE Clause Optimization


#### 10.2.1.1 WHERE Clause Optimization

This section discusses optimizations that can be made for
processing `WHERE` clauses. The examples use
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements, but the same
optimizations apply for `WHERE` clauses in
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") and
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statements.

Note

Because work on the MySQL optimizer is ongoing, not all of
the optimizations that MySQL performs are documented here.

You might be tempted to rewrite your queries to make
arithmetic operations faster, while sacrificing readability.
Because MySQL does similar optimizations automatically, you
can often avoid this work, and leave the query in a more
understandable and maintainable form. Some of the
optimizations performed by MySQL follow:

- Removal of unnecessary parentheses:



```sql
     ((a AND b) AND c OR (((a AND b) AND (c AND d))))
  -> (a AND b AND c) OR (a AND b AND c AND d)
```

- Constant folding:



```sql
     (a<b AND b=c) AND a=5
  -> b>5 AND b=c AND a=5
```

- Constant condition removal:



```sql
     (b>=5 AND b=5) OR (b=6 AND 5=5) OR (b=7 AND 5=6)
  -> b=5 OR b=6
```



In MySQL 8.0.14 and later, this takes place during
preparation rather than during the optimization phase,
which helps in simplification of joins. See
[Section 10.2.1.9, “Outer Join Optimization”](https://dev.mysql.com/doc/refman/8.0/en/outer-join-optimization.html "10.2.1.9 Outer Join Optimization"), for further
information and examples.


- Constant expressions used by indexes are evaluated only
once.


- Beginning with MySQL 8.0.16, comparisons of columns of
numeric types with constant values are checked and folded
or removed for invalid or out-of-rage values:



```sql
# CREATE TABLE t (c TINYINT UNSIGNED NOT NULL);
    SELECT * FROM t WHERE c < 256;
  -≫ SELECT * FROM t WHERE 1;
```



See [Section 10.2.1.14, “Constant-Folding Optimization”](https://dev.mysql.com/doc/refman/8.0/en/constant-folding-optimization.html "10.2.1.14 Constant-Folding Optimization"), for
more information.


- [`COUNT(*)`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count) on a single table
without a `WHERE` is retrieved directly
from the table information for `MyISAM`
and `MEMORY` tables. This is also done
for any `NOT NULL` expression when used
with only one table.


- Early detection of invalid constant expressions. MySQL
quickly detects that some
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements are
impossible and returns no rows.


- `HAVING` is merged with
`WHERE` if you do not use `GROUP
                BY` or aggregate functions
( [`COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count),
[`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min), and so on).


- For each table in a join, a simpler
`WHERE` is constructed to get a fast
`WHERE` evaluation for the table and also
to skip rows as soon as possible.


- All constant tables are read first before any other tables
in the query. A constant table is any of the following:




- An empty table or a table with one row.


- A table that is used with a `WHERE`
clause on a `PRIMARY KEY` or a
`UNIQUE` index, where all index parts
are compared to constant expressions and are defined
as `NOT NULL`.


All of the following tables are used as constant tables:


```sql
SELECT * FROM t WHERE primary_key=1;
SELECT * FROM t1,t2
  WHERE t1.primary_key=1 AND t2.primary_key=t1.id;
```

- The best join combination for joining the tables is found
by trying all possibilities. If all columns in
`ORDER BY` and `GROUP
                BY` clauses come from the same table, that table
is preferred first when joining.


- If there is an `ORDER BY` clause and a
different `GROUP BY` clause, or if the
`ORDER BY` or `GROUP BY`
contains columns from tables other than the first table in
the join queue, a temporary table is created.


- If you use the `SQL_SMALL_RESULT`
modifier, MySQL uses an in-memory temporary table.


- Each table index is queried, and the best index is used
unless the optimizer believes that it is more efficient to
use a table scan. At one time, a scan was used based on
whether the best index spanned more than 30% of the table,
but a fixed percentage no longer determines the choice
between using an index or a scan. The optimizer now is
more complex and bases its estimate on additional factors
such as table size, number of rows, and I/O block size.


- In some cases, MySQL can read rows from the index without
even consulting the data file. If all columns used from
the index are numeric, only the index tree is used to
resolve the query.


- Before each row is output, those that do not match the
`HAVING` clause are skipped.


Some examples of queries that are very fast:


```sql
SELECT COUNT(*) FROM tbl_name;

SELECT MIN(key_part1),MAX(key_part1) FROM tbl_name;

SELECT MAX(key_part2) FROM tbl_name
  WHERE key_part1=constant;

SELECT ... FROM tbl_name
  ORDER BY key_part1,key_part2,... LIMIT 10;

SELECT ... FROM tbl_name
  ORDER BY key_part1 DESC, key_part2 DESC, ... LIMIT 10;
```

MySQL resolves the following queries using only the index
tree, assuming that the indexed columns are numeric:


```sql
SELECT key_part1,key_part2 FROM tbl_name WHERE key_part1=val;

SELECT COUNT(*) FROM tbl_name
  WHERE key_part1=val1 AND key_part2=val2;

SELECT MAX(key_part2) FROM tbl_name GROUP BY key_part1;
```

The following queries use indexing to retrieve the rows in
sorted order without a separate sorting pass:


```sql
SELECT ... FROM tbl_name
  ORDER BY key_part1,key_part2,... ;

SELECT ... FROM tbl_name
  ORDER BY key_part1 DESC, key_part2 DESC, ... ;
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html "Previous: Optimizing SELECT Statements") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html "Up: Optimizing SELECT Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/range-optimization.html "Next: Range Optimization")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html)

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