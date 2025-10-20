---
url: https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html
scraped_at: 2025-10-20T03:14:10.430Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html "Hide Sidebar")

[Previous: Optimizing Derived Tables, View References, and Common Table Expressions\
with Merging or Materialization](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html "Previous: Optimizing Derived Tables, View References, and Common Table Expressions with Merging or Materialization")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimizing Subqueries, Derived Tables, View References, and Common Table\
        Expressions](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization.html "Up: Optimizing Subqueries, Derived Tables, View References, and Common Table         Expressions")[Next: Optimizing INFORMATION_SCHEMA Queries](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html "Next: Optimizing INFORMATION_SCHEMA Queries")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/derived-condition-pushdown-optimization.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/derived-condition-pushdown-optimization.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/derived-condition-pushdown-optimization.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/derived-condition-pushdown-optimization.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/derived-condition-pushdown-optimization.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/derived-condition-pushdown-optimization.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/derived-condition-pushdown-optimization.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimizing SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)  /
[Optimizing Subqueries, Derived Tables, View References, and Common Table\\
Expressions](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization.html)  /

Derived Condition Pushdown Optimization


#### 10.2.2.5 Derived Condition Pushdown Optimization

MySQL 8.0.22 and later supports derived condition pushdown for
eligible subqueries. For a query such as `SELECT *
          FROM (SELECT i, j FROM t1) AS dt WHERE i >
          constant`, it is possible
in many cases to push the outer `WHERE`
condition down to the derived table, in this case resulting in
`SELECT * FROM (SELECT i, j FROM t1 WHERE i >
          constant) AS dt`. When a
derived table cannot be merged into the outer query (for
example, if the derived table uses aggregation), pushing the
outer `WHERE` condition down to the derived
table should decrease the number of rows that need to be
processed and thus speed up execution of the query.

Note

Prior to MySQL 8.0.22, if a derived table was materialized
but not merged, MySQL materialized the entire table, then
qualified all of the resulting rows with the
`WHERE` condition. This is still the case
if derived condition pushdown is not enabled, or cannot be
employed for some other reason.

Outer `WHERE` conditions can be pushed down
to derived materialized tables under the following
circumstances:

- When the derived table uses no aggregate or window
functions, the outer `WHERE` condition
can be pushed down to it directly. This includes
`WHERE` conditions having multiple
predicates joined with `AND`,
`OR`, or both.



For example, the query `SELECT * FROM (SELECT f1,
                f2 FROM t1) AS dt WHERE f1 < 3 AND f2 > 11`
is rewritten as `SELECT f1, f2 FROM (SELECT f1, f2
                FROM t1 WHERE f1 < 3 AND f2 > 11) AS dt`.


- When the derived table has a `GROUP BY`
and uses no window functions, an outer
`WHERE` condition referencing one or more
columns which are not part of the `GROUP
                BY` can be pushed down to the derived table as a
`HAVING` condition.



For example, `SELECT * FROM (SELECT i, j, SUM(k)
                AS sum FROM t1 GROUP BY i, j) AS dt WHERE sum >
                100` is rewritten following derived condition
pushdown as `SELECT * FROM (SELECT i, j, SUM(k) AS
                sum FROM t1 GROUP BY i, j HAVING sum > 100) AS
                dt`.


- When the derived table uses a `GROUP BY`
and the columns in the outer `WHERE`
condition are `GROUP BY` columns, the
`WHERE` conditions referencing those
columns can be pushed down directly to the derived table.



For example, the query `SELECT * FROM (SELECT i,j,
                SUM(k) AS sum FROM t1 GROUP BY i,j) AS dt WHERE i >
                10` is rewritten as `SELECT * FROM
                (SELECT i,j, SUM(k) AS sum FROM t1 WHERE i > 10 GROUP
                BY i,j) AS dt`.



In the event that the outer `WHERE`
condition has predicates referencing columns which are
part of the `GROUP BY` as well as
predicates referencing columns which are not, predicates
of the former sort are pushed down as
`WHERE` conditions, while those of the
latter type are pushed down as `HAVING`
conditions. For example, in the query `SELECT *
                FROM (SELECT i, j, SUM(k) AS sum FROM t1 GROUP BY i,j) AS
                dt WHERE i > 10 AND sum > 100`, the
predicate `i > 10` in the outer
`WHERE` clause references a
`GROUP BY` column, whereas the predicate
`sum > 100` does not reference any
`GROUP BY` column. Thus the derived table
pushdown optimization causes the query to be rewritten in
a manner similar to what is shown here:




``` sql

SELECT * FROM (
      SELECT i, j, SUM(k) AS sum FROM t1
          WHERE i > 10
          GROUP BY i, j
          HAVING sum > 100
      ) AS dt;
```


To enable derived condition pushdown, the
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) system
variable's
[`derived_condition_pushdown`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_derived-condition-pushdown)
flag (added in this release) must be set to
`on`, which is the default setting. If this
optimization is disabled by
`optimizer_switch`, you can enable it for a
specific query using the
[`DERIVED_CONDITION_PUSHDOWN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints")
optimizer hint. To disable the optimization for a given query,
use the
[`NO_DERIVED_CONDITION_PUSHDOWN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints")
optimizer hint.


The following restrictions and limitations apply to the
derived table condition pushdown optimization:

- The optimization cannot be used if the derived table
contains [`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause"). This
restriction is lifted in MySQL 8.0.29. Consider two tables
`t1` and `t2`, and a
view `v` containing their union, created
as shown here:




``` sql

CREATE TABLE t1 (
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    c1 INT,
    KEY i1 (c1)
);

CREATE TABLE t2 (
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    c1 INT,
    KEY i1 (c1)
);

CREATE OR REPLACE VIEW v AS
       SELECT id, c1 FROM t1
       UNION ALL
       SELECT id, c1 FROM t2;
```




As be seen in the output of
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html#explain-execution-plan "Obtaining Execution Plan Information"),
a condition present in the top level of a query such as
`SELECT * FROM v WHERE c1 = 12` can now
be pushed down to both query blocks in the derived table:




``` sql

mysql> EXPLAIN FORMAT=TREE SELECT * FROM v WHERE c1 = 12\G
*************************** 1. row ***************************
EXPLAIN: -> Table scan on v  (cost=1.26..2.52 rows=2)
      -> Union materialize  (cost=2.16..3.42 rows=2)
          -> Covering index lookup on t1 using i1 (c1=12)  (cost=0.35 rows=1)
          -> Covering index lookup on t2 using i1 (c1=12)  (cost=0.35 rows=1)

1 row in set (0.00 sec)
```




In MySQL 8.0.29 and later, the derived table condition
pushdown optimization can be employed with
`UNION` queries, with the following
exceptions:




- Condition pushdown cannot be used with a
`UNION` query if any materialized
derived table that is part of the
`UNION` is a recursive common table
expression (see
[Recursive Common Table Expressions](https://dev.mysql.com/doc/refman/8.0/en/with.html#common-table-expressions-recursive "Recursive Common Table Expressions")).


- Conditions containing nondeterministic expressions
cannot be pushed down to a derived table.


- The derived table cannot use a `LIMIT`
clause.


- Conditions containing subqueries cannot be pushed down.


- The optimization cannot be used if the derived table is an
inner table of an outer join.


- If a materialized derived table is a common table
expression, conditions are not pushed down to it if it is
referenced multiple times.


- Conditions using parameters can be pushed down if the
condition is of the form
`derived_column >
                ?`. If a derived column in an outer
`WHERE` condition is an expression having
a `?` in the underlying derived table,
this condition cannot be pushed down.


- For a query in which the condition is on the tables of a
view created using `ALGORITHM=TEMPTABLE`
instead of on the view itself, the multiple equality is
not recognized at resolution, and thus the condition
cannot be not pushed down. This because, when optimizing a
query, condition pushdown takes place during resolution
phase while multiple equality propagation occurs during
optimization.



This is not an issue in such cases for a view using
`ALGORITHM=MERGE`, where the equality can
be propagated and the condition pushed down.


- Beginning with MySQL 8.0.28, a condition cannot be pushed
down if the derived table's `SELECT`
list contain any assignments to user variables. (Bug
#104918)


[PREV](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html "Previous: Optimizing Derived Tables, View References, and Common Table Expressions with Merging or Materialization") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization.html "Up: Optimizing Subqueries, Derived Tables, View References, and Common Table         Expressions") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html "Next: Optimizing INFORMATION_SCHEMA Queries")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html)

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