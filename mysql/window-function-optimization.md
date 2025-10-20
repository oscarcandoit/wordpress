---
url: https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html
scraped_at: 2025-10-20T03:14:14.743Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html "Hide Sidebar")

[Previous: Function Call Optimization](https://dev.mysql.com/doc/refman/8.0/en/function-optimization.html "Previous: Function Call Optimization")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimizing SELECT Statements](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html "Up: Optimizing SELECT Statements")[Next: Row Constructor Expression Optimization](https://dev.mysql.com/doc/refman/8.0/en/row-constructor-optimization.html "Next: Row Constructor Expression Optimization")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/window-function-optimization.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/window-function-optimization.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/window-function-optimization.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/window-function-optimization.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/window-function-optimization.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/window-function-optimization.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/window-function-optimization.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimizing SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)  /
[Optimizing SELECT Statements](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html)  /

Window Function Optimization


#### 10.2.1.21 Window Function Optimization

Window functions affect the strategies the optimizer
considers:

- Derived table merging for a subquery is disabled if the
subquery has window functions. The subquery is always
materialized.


- Semijoins are not applicable to window function
optimization because semijoins apply to subqueries in
`WHERE` and `JOIN ...
                ON`, which cannot contain window functions.


- The optimizer processes multiple windows that have the
same ordering requirements in sequence, so sorting can be
skipped for windows following the first one.


- The optimizer makes no attempt to merge windows that could
be evaluated in a single step (for example, when multiple
`OVER` clauses contain identical window
definitions). The workaround is to define the window in a
`WINDOW` clause and refer to the window
name in the `OVER` clauses.


An aggregate function not used as a window function is
aggregated in the outermost possible query. For example, in
this query, MySQL sees that `COUNT(t1.b)` is
something that cannot exist in the outer query because of its
placement in the `WHERE` clause:


```sql
SELECT * FROM t1 WHERE t1.a = (SELECT COUNT(t1.b) FROM t2);
```

Consequently, MySQL aggregates inside the subquery, treating
`t1.b` as a constant and returning the count
of rows of `t2`.


Replacing `WHERE` with
`HAVING` results in an error:


```sql
mysql> SELECT * FROM t1 HAVING t1.a = (SELECT COUNT(t1.b) FROM t2);
ERROR 1140 (42000): In aggregated query without GROUP BY, expression #1
of SELECT list contains nonaggregated column 'test.t1.a'; this is
incompatible with sql_mode=only_full_group_by
```

The error occurs because `COUNT(t1.b)` can
exist in the `HAVING`, and so makes the outer
query aggregated.


Window functions (including aggregate functions used as window
functions) do not have the preceding complexity. They always
aggregate in the subquery where they are written, never in the
outer query.


Window function evaluation may be affected by the value of the
[`windowing_use_high_precision`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_windowing_use_high_precision)
system variable, which determines whether to compute window
operations without loss of precision. By default,
[`windowing_use_high_precision`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_windowing_use_high_precision)
is enabled.


For some moving frame aggregates, the inverse aggregate
function can be applied to remove values from the aggregate.
This can improve performance but possibly with a loss of
precision. For example, adding a very small floating-point
value to a very large value causes the very small value to be
“hidden” by the large value. When inverting the
large value later, the effect of the small value is lost.


Loss of precision due to inverse aggregation is a factor only
for operations on floating-point (approximate-value) data
types. For other types, inverse aggregation is safe; this
includes [`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC"), which permits
a fractional part but is an exact-value type.


For faster execution, MySQL always uses inverse aggregation
when it is safe:

- For floating-point values, inverse aggregation is not
always safe and might result in loss of precision. The
default is to avoid inverse aggregation, which is slower
but preserves precision. If it is permissible to sacrifice
safety for speed,
[`windowing_use_high_precision`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_windowing_use_high_precision)
can be disabled to permit inverse aggregation.


- For nonfloating-point data types, inverse aggregation is
always safe and is used regardless of the
[`windowing_use_high_precision`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_windowing_use_high_precision)
value.


- [`windowing_use_high_precision`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_windowing_use_high_precision)
has no effect on [`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min) and
[`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max), which do not use
inverse aggregation in any case.


For evaluation of the variance functions
[`STDDEV_POP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev-pop),
[`STDDEV_SAMP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev-samp),
[`VAR_POP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_var-pop),
[`VAR_SAMP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_var-samp), and their synonyms,
evaluation can occur in optimized mode or default mode.
Optimized mode may produce slightly different results in the
last significant digits. If such differences are permissible,
[`windowing_use_high_precision`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_windowing_use_high_precision)
can be disabled to permit optimized mode.


For [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement"), windowing
execution plan information is too extensive to display in
traditional output format. To see windowing information, use
[`EXPLAIN\\
          FORMAT=JSON`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") and look for the
`windowing` element.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/function-optimization.html "Previous: Function Call Optimization") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html "Up: Optimizing SELECT Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/row-constructor-optimization.html "Next: Row Constructor Expression Optimization")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html)

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