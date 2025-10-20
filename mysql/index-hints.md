---
url: https://dev.mysql.com/doc/refman/8.0/en/index-hints.html
scraped_at: 2025-10-20T03:04:09.012Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html "Hide Sidebar")

[Previous: Optimizer Hints](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html "Previous: Optimizer Hints")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Controlling the Query Optimizer](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html "Up: Controlling the Query Optimizer")[Next: The Optimizer Cost Model](https://dev.mysql.com/doc/refman/8.0/en/cost-model.html "Next: The Optimizer Cost Model")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/index-hints.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/index-hints.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/index-hints.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/index-hints.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/index-hints.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/index-hints.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/index-hints.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/index-hints.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Controlling the Query Optimizer](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html)  /

Index Hints


### 10.9.4 Index Hints

Index hints give the optimizer information about how to choose
indexes during query processing. Index hints, described here,
differ from optimizer hints, described in
[Section 10.9.3, “Optimizer Hints”](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html "10.9.3 Optimizer Hints"). Index and optimizer hints may
be used separately or together.


Index hints apply to [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") and
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statements. They also work
with multi-table [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement")
statements, but not with single-table `DELETE`,
as shown later in this section.


Index hints are specified following a table name. (For the
general syntax for specifying tables in a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement, see
[Section 15.2.13.2, “JOIN Clause”](https://dev.mysql.com/doc/refman/8.0/en/join.html "15.2.13.2 JOIN Clause").) The syntax for referring to an
individual table, including index hints, looks like this:


``` sql

tbl_name [[AS] alias] [index_hint_list]

index_hint_list:
    index_hint [index_hint] ...

index_hint:
    USE {INDEX|KEY}
      [FOR {JOIN|ORDER BY|GROUP BY}] ([index_list])
  | {IGNORE|FORCE} {INDEX|KEY}
      [FOR {JOIN|ORDER BY|GROUP BY}] (index_list)

index_list:
    index_name [, index_name] ...
```

The `USE INDEX
        (index_list)` hint tells
MySQL to use only one of the named indexes to find rows in the
table. The alternative syntax `IGNORE INDEX
        (index_list)` tells MySQL to
not use some particular index or indexes. These hints are useful
if [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") shows that MySQL is
using the wrong index from the list of possible indexes.


The `FORCE INDEX` hint acts like `USE
        INDEX (index_list)`, with
the addition that a table scan is assumed to be
_very_ expensive. In other words, a table
scan is used only if there is no way to use one of the named
indexes to find rows in the table.

Note

As of MySQL 8.0.20, the server supports the index-level
optimizer hints [`JOIN_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`GROUP_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`ORDER_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"), and
[`INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"), which are equivalent
to and intended to supersede `FORCE INDEX`
index hints, as well as the
[`NO_JOIN_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`NO_GROUP_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`NO_ORDER_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"), and
[`NO_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") optimizer hints,
which are equivalent to and intended to supersede
`IGNORE INDEX` index hints. Thus, you should
expect `USE INDEX`, `FORCE
          INDEX`, and `IGNORE INDEX` to be
deprecated in a future release of MySQL, and at some time
thereafter to be removed altogether.


These index-level optimizer hints are supported with both
single-table and multi-table
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statements.


For more information, see
[Index-Level Optimizer Hints](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints").

Each hint requires index names, not column names. To refer to a
primary key, use the name `PRIMARY`. To see the
index names for a table, use the [`SHOW\\
        INDEX`](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "15.7.7.22 SHOW INDEX Statement") statement or the Information Schema
[`STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html "28.3.34 The INFORMATION_SCHEMA STATISTICS Table") table.


An _`index_name`_ value need not be a
full index name. It can be an unambiguous prefix of an index
name. If a prefix is ambiguous, an error occurs.


Examples:


``` sql

SELECT * FROM table1 USE INDEX (col1_index,col2_index)
  WHERE col1=1 AND col2=2 AND col3=3;

SELECT * FROM table1 IGNORE INDEX (col3_index)
  WHERE col1=1 AND col2=2 AND col3=3;
```

The syntax for index hints has the following characteristics:

- It is syntactically valid to omit
_`index_list`_ for `USE
              INDEX`, which means “use no indexes.”
Omitting _`index_list`_ for
`FORCE INDEX` or `IGNORE
              INDEX` is a syntax error.


- You can specify the scope of an index hint by adding a
`FOR` clause to the hint. This provides
more fine-grained control over optimizer selection of an
execution plan for various phases of query processing. To
affect only the indexes used when MySQL decides how to find
rows in the table and how to process joins, use `FOR
              JOIN`. To influence index usage for sorting or
grouping rows, use `FOR ORDER BY` or
`FOR GROUP BY`.


- You can specify multiple index hints:




``` sql

SELECT * FROM t1 USE INDEX (i1) IGNORE INDEX FOR ORDER BY (i2) ORDER BY a;
```




It is not an error to name the same index in several hints
(even within the same hint):




``` sql

SELECT * FROM t1 USE INDEX (i1) USE INDEX (i1,i1);
```




However, it is an error to mix `USE INDEX`
and `FORCE INDEX` for the same table:




``` sql

SELECT * FROM t1 USE INDEX FOR JOIN (i1) FORCE INDEX FOR JOIN (i2);
```


If an index hint includes no `FOR` clause, the
scope of the hint is to apply to all parts of the statement. For
example, this hint:


``` sql

IGNORE INDEX (i1)
```

is equivalent to this combination of hints:


``` sql

IGNORE INDEX FOR JOIN (i1)
IGNORE INDEX FOR ORDER BY (i1)
IGNORE INDEX FOR GROUP BY (i1)
```

In MySQL 5.0, hint scope with no `FOR` clause
was to apply only to row retrieval. To cause the server to use
this older behavior when no `FOR` clause is
present, enable the [`old`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_old) system
variable at server startup. Take care about enabling this
variable in a replication setup. With statement-based binary
logging, having different modes for the source and replicas
might lead to replication errors.


When index hints are processed, they are collected in a single
list by type ( `USE`, `FORCE`,
`IGNORE`) and by scope ( `FOR
        JOIN`, `FOR ORDER BY`, `FOR
        GROUP BY`). For example:


``` sql

SELECT * FROM t1
  USE INDEX () IGNORE INDEX (i2) USE INDEX (i1) USE INDEX (i2);
```

is equivalent to:


``` sql

SELECT * FROM t1
   USE INDEX (i1,i2) IGNORE INDEX (i2);
```

The index hints then are applied for each scope in the following
order:

1. `{USE|FORCE} INDEX` is applied if present.
    (If not, the optimizer-determined set of indexes is used.)


2. `IGNORE INDEX` is applied over the result
    of the previous step. For example, the following two queries
    are equivalent:




``` sql

SELECT * FROM t1 USE INDEX (i1) IGNORE INDEX (i2) USE INDEX (i2);

SELECT * FROM t1 USE INDEX (i1);
```


For `FULLTEXT` searches, index hints work as
follows:

- For natural language mode searches, index hints are silently
ignored. For example, `IGNORE INDEX(i1)` is
ignored with no warning and the index is still used.


- For boolean mode searches, index hints with `FOR
              ORDER BY` or `FOR GROUP BY` are
silently ignored. Index hints with `FOR
              JOIN` or no `FOR` modifier are
honored. In contrast to how hints apply for
non- `FULLTEXT` searches, the hint is used
for all phases of query execution (finding rows and
retrieval, grouping, and ordering). This is true even if the
hint is given for a non- `FULLTEXT` index.



For example, the following two queries are equivalent:




``` sql

SELECT * FROM t
    USE INDEX (index1)
    IGNORE INDEX FOR ORDER BY (index1)
    IGNORE INDEX FOR GROUP BY (index1)
    WHERE ... IN BOOLEAN MODE ... ;

SELECT * FROM t
    USE INDEX (index1)
    WHERE ... IN BOOLEAN MODE ... ;
```


Index hints work with [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement")
statements, but only if you use multi-table
`DELETE` syntax, as shown here:


``` sql

mysql> EXPLAIN DELETE FROM t1 USE INDEX(col2)
    -> WHERE col1 BETWEEN 1 AND 100 AND COL2 BETWEEN 1 AND 100\G
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that
corresponds to your MySQL server version for the right syntax to use near 'use
index(col2) where col1 between 1 and 100 and col2 between 1 and 100' at line 1

mysql> EXPLAIN DELETE t1.* FROM t1 USE INDEX(col2)
    -> WHERE col1 BETWEEN 1 AND 100 AND COL2 BETWEEN 1 AND 100\G
*************************** 1. row ***************************
           id: 1
  select_type: DELETE
        table: t1
   partitions: NULL
         type: range
possible_keys: col2
          key: col2
      key_len: 5
          ref: NULL
         rows: 72
     filtered: 11.11
        Extra: Using where
1 row in set, 1 warning (0.00 sec)
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html "Previous: Optimizer Hints") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html "Up: Controlling the Query Optimizer") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/cost-model.html "Next: The Optimizer Cost Model")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html)

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