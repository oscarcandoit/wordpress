---
url: https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html
scraped_at: 2025-10-20T03:14:06.311Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html "Hide Sidebar")

[Previous: Optimizing Subqueries with the EXISTS Strategy](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization-with-exists.html "Previous: Optimizing Subqueries with the EXISTS Strategy")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimizing Subqueries, Derived Tables, View References, and Common Table\
        Expressions](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization.html "Up: Optimizing Subqueries, Derived Tables, View References, and Common Table         Expressions")[Next: Derived Condition Pushdown Optimization](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html "Next: Derived Condition Pushdown Optimization")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/derived-table-optimization.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/derived-table-optimization.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/derived-table-optimization.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/derived-table-optimization.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/derived-table-optimization.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/derived-table-optimization.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/derived-table-optimization.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/derived-table-optimization.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimizing SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)  /
[Optimizing Subqueries, Derived Tables, View References, and Common Table\\
Expressions](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization.html)  /

Optimizing Derived Tables, View References, and Common Table Expressions
with Merging or Materialization


#### 10.2.2.4 Optimizing Derived Tables, View References, and Common Table Expressions with Merging or Materialization

The optimizer can handle derived table references using two
strategies (which also apply to view references and common
table expressions):

- Merge the derived table into the outer query block


- Materialize the derived table to an internal temporary
table


Example 1:


``` sql

SELECT * FROM (SELECT * FROM t1) AS derived_t1;
```

With merging of the derived table
`derived_t1`, that query is executed similar
to:


``` sql

SELECT * FROM t1;
```

Example 2:


``` sql

SELECT *
  FROM t1 JOIN (SELECT t2.f1 FROM t2) AS derived_t2 ON t1.f2=derived_t2.f1
  WHERE t1.f1 > 0;
```

With merging of the derived table
`derived_t2`, that query is executed similar
to:


``` sql

SELECT t1.*, t2.f1
  FROM t1 JOIN t2 ON t1.f2=t2.f1
  WHERE t1.f1 > 0;
```

With materialization, `derived_t1` and
`derived_t2` are each treated as a separate
table within their respective queries.


The optimizer handles derived tables, view references, and
common table expressions the same way: It avoids unnecessary
materialization whenever possible, which enables pushing down
conditions from the outer query to derived tables and produces
more efficient execution plans. (For an example, see
[Section 10.2.2.2, “Optimizing Subqueries with Materialization”](https://dev.mysql.com/doc/refman/8.0/en/subquery-materialization.html "10.2.2.2 Optimizing Subqueries with Materialization").)


If merging would result in an outer query block that
references more than 61 base tables, the optimizer chooses
materialization instead.


The optimizer propagates an `ORDER BY` clause
in a derived table or view reference to the outer query block
if these conditions are all true:

- The outer query is not grouped or aggregated.


- The outer query does not specify
`DISTINCT`, `HAVING`, or
`ORDER BY`.


- The outer query has this derived table or view reference
as the only source in the `FROM` clause.


Otherwise, the optimizer ignores the `ORDER
          BY` clause.


The following means are available to influence whether the
optimizer attempts to merge derived tables, view references,
and common table expressions into the outer query block:

- The [`MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") and
[`NO_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") optimizer hints
can be used. They apply assuming that no other rule
prevents merging. See [Section 10.9.3, “Optimizer Hints”](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html "10.9.3 Optimizer Hints").


- Similarly, you can use the
[`derived_merge`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_derived-merge) flag of
the [`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch)
system variable. See
[Section 10.9.2, “Switchable Optimizations”](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html "10.9.2 Switchable Optimizations"). By default,
the flag is enabled to permit merging. Disabling the flag
prevents merging and avoids
[`ER_UPDATE_TABLE_USED`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_update_table_used)
errors.



The [`derived_merge`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_derived-merge) flag
also applies to views that contain no
`ALGORITHM` clause. Thus, if an
[`ER_UPDATE_TABLE_USED`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_update_table_used) error
occurs for a view reference that uses an expression
equivalent to the subquery, adding
`ALGORITHM=TEMPTABLE` to the view
definition prevents merging and takes precedence over the
[`derived_merge`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_derived-merge) value.


- It is possible to disable merging by using in the subquery
any constructs that prevent merging, although these are
not as explicit in their effect on materialization.
Constructs that prevent merging are the same for derived
tables, common table expressions, and view references:




- Aggregate functions or window functions
( [`SUM()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_sum),
[`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min),
[`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max),
[`COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count), and so forth)


- `DISTINCT`

- `GROUP BY`

- `HAVING`

- `LIMIT`

- [`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause") or
[`UNION\\
                    ALL`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause")

- Subqueries in the select list


- Assignments to user variables


- References only to literal values (in this case, there
is no underlying table)


If the optimizer chooses the materialization strategy rather
than merging for a derived table, it handles the query as
follows:

- The optimizer postpones derived table materialization
until its contents are needed during query execution. This
improves performance because delaying materialization may
result in not having to do it at all. Consider a query
that joins the result of a derived table to another table:
If the optimizer processes that other table first and
finds that it returns no rows, the join need not be
carried out further and the optimizer can completely skip
materializing the derived table.


- During query execution, the optimizer may add an index to
a derived table to speed up row retrieval from it.


Consider the following [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement")
statement, for a [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") query
that contains a derived table:


``` sql

EXPLAIN SELECT * FROM (SELECT * FROM t1) AS derived_t1;
```

The optimizer avoids materializing the derived table by
delaying it until the result is needed during
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") execution. In this case,
the query is not executed (because it occurs in an
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") statement), so the
result is never needed.


Even for queries that are executed, delay of derived table
materialization may enable the optimizer to avoid
materialization entirely. When this happens, query execution
is quicker by the time needed to perform materialization.
Consider the following query, which joins the result of a
derived table to another table:


``` sql

SELECT *
  FROM t1 JOIN (SELECT t2.f1 FROM t2) AS derived_t2
          ON t1.f2=derived_t2.f1
  WHERE t1.f1 > 0;
```

If the optimization processes `t1` first and
the `WHERE` clause produces an empty result,
the join must necessarily be empty and the derived table need
not be materialized.


For cases when a derived table requires materialization, the
optimizer may add an index to the materialized table to speed
up access to it. If such an index enables
[`ref`](https://dev.mysql.com/doc/refman/8.0/en/explain-output.html#jointype_ref) access to the table, it
can greatly reduce amount of data read during query execution.
Consider the following query:


``` sql

SELECT *
 FROM t1 JOIN (SELECT DISTINCT f1 FROM t2) AS derived_t2
         ON t1.f1=derived_t2.f1;
```

The optimizer constructs an index over column
`f1` from `derived_t2` if
doing so would enable use of
[`ref`](https://dev.mysql.com/doc/refman/8.0/en/explain-output.html#jointype_ref) access for the lowest
cost execution plan. After adding the index, the optimizer can
treat the materialized derived table the same as a regular
table with an index, and it benefits similarly from the
generated index. The overhead of index creation is negligible
compared to the cost of query execution without the index. If
[`ref`](https://dev.mysql.com/doc/refman/8.0/en/explain-output.html#jointype_ref) access would result in
higher cost than some other access method, the optimizer
creates no index and loses nothing.


For optimizer trace output, a merged derived table or view
reference is not shown as a node. Only its underlying tables
appear in the top query's plan.


What is true for materialization of derived tables is also
true for common table expressions (CTEs). In addition, the
following considerations pertain specifically to CTEs.


If a CTE is materialized by a query, it is materialized once
for the query, even if the query references it several times.


A recursive CTE is always materialized.


If a CTE is materialized, the optimizer automatically adds
relevant indexes if it estimates that indexing can speed up
access by the top-level statement to the CTE. This is similar
to automatic indexing of derived tables, except that if the
CTE is referenced multiple times, the optimizer may create
multiple indexes, to speed up access by each reference in the
most appropriate way.


The [`MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") and
[`NO_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") optimizer hints can
be applied to CTEs. Each CTE reference in the top-level
statement can have its own hint, permitting CTE references to
be selectively merged or materialized. The following statement
uses hints to indicate that `cte1` should be
merged and `cte2` should be materialized:


``` sql

WITH
  cte1 AS (SELECT a, b FROM table1),
  cte2 AS (SELECT c, d FROM table2)
SELECT /*+ MERGE(cte1) NO_MERGE(cte2) */ cte1.b, cte2.d
FROM cte1 JOIN cte2
WHERE cte1.a = cte2.c;
```

The `ALGORITHM` clause for
[`CREATE VIEW`](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "15.1.23 CREATE VIEW Statement") does not affect
materialization for any [`WITH`](https://dev.mysql.com/doc/refman/8.0/en/with.html "15.2.20 WITH (Common Table Expressions)")
clause preceding the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statement in the view definition. Consider this statement:


``` sql

CREATE ALGORITHM={TEMPTABLE|MERGE} VIEW v1 AS WITH ... SELECT ...
```

The `ALGORITHM` value affects materialization
only of the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"), not the
[`WITH`](https://dev.mysql.com/doc/refman/8.0/en/with.html "15.2.20 WITH (Common Table Expressions)") clause.


Prior to MySQL 8.0.16, if
[`internal_tmp_disk_storage_engine=MYISAM`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_internal_tmp_disk_storage_engine),
an error occurred for any attempt to materialize a CTE using
an on-disk temporary table, since for CTEs, the storage engine
used for on-disk internal temporary tables could not be
`MyISAM`. Beginning with MySQL 8.0.16, this
is no longer an issue, since `TempTable` now
always uses `InnoDB` for on-disk internal
temporary tables.


As mentioned previously, a CTE, if materialized, is
materialized once, even if referenced multiple times. To
indicate one-time materialization, optimizer trace output
contains an occurrence of
`creating_tmp_table` plus one or more
occurrences of `reusing_tmp_table`.


CTEs are similar to derived tables, for which the
`materialized_from_subquery` node follows the
reference. This is true for a CTE that is referenced multiple
times, so there is no duplication of
`materialized_from_subquery` nodes (which
would give the impression that the subquery is executed
multiple times, and produce unnecessarily verbose output).
Only one reference to the CTE has a complete
`materialized_from_subquery` node with the
description of its subquery plan. Other references have a
reduced `materialized_from_subquery` node.
The same idea applies to
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") output in
`TRADITIONAL` format: Subqueries for other
references are not shown.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization-with-exists.html "Previous: Optimizing Subqueries with the EXISTS Strategy") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization.html "Up: Optimizing Subqueries, Derived Tables, View References, and Common Table         Expressions") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html "Next: Derived Condition Pushdown Optimization")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html)

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