---
url: https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html
scraped_at: 2025-10-20T03:13:36.280Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html "Hide Sidebar")

[Previous: Controlling Query Plan Evaluation](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html "Previous: Controlling Query Plan Evaluation")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Controlling the Query Optimizer](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html "Up: Controlling the Query Optimizer")[Next: Optimizer Hints](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html "Next: Optimizer Hints")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/switchable-optimizations.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/switchable-optimizations.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/switchable-optimizations.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/switchable-optimizations.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/switchable-optimizations.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/switchable-optimizations.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/switchable-optimizations.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/switchable-optimizations.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Controlling the Query Optimizer](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html)  /

Switchable Optimizations


### 10.9.2 Switchable Optimizations

The [`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) system
variable enables control over optimizer behavior. Its value is a
set of flags, each of which has a value of `on`
or `off` to indicate whether the corresponding
optimizer behavior is enabled or disabled. This variable has
global and session values and can be changed at runtime. The
global default can be set at server startup.


To see the current set of optimizer flags, select the variable
value:


``` sql

mysql> SELECT @@optimizer_switch\G
*************************** 1. row ***************************
@@optimizer_switch: index_merge=on,index_merge_union=on,
                    index_merge_sort_union=on,index_merge_intersection=on,
                    engine_condition_pushdown=on,index_condition_pushdown=on,
                    mrr=on,mrr_cost_based=on,block_nested_loop=on,
                    batched_key_access=off,materialization=on,semijoin=on,
                    loosescan=on,firstmatch=on,duplicateweedout=on,
                    subquery_materialization_cost_based=on,
                    use_index_extensions=on,condition_fanout_filter=on,
                    derived_merge=on,use_invisible_indexes=off,skip_scan=on,
                    hash_join=on,subquery_to_derived=off,
                    prefer_ordering_index=on,hypergraph_optimizer=off,
                    derived_condition_pushdown=on
1 row in set (0.00 sec)
```

To change the value of
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch), assign a
value consisting of a comma-separated list of one or more
commands:


``` sql

SET [GLOBAL|SESSION] optimizer_switch='command[,command]...';
```

Each _`command`_ value should have one of
the forms shown in the following table.

| Command Syntax | Meaning |
| --- | --- |
| `default` | Reset every optimization to its default value |
| `opt_name=default` | Set the named optimization to its default value |
| `opt_name=off` | Disable the named optimization |
| `opt_name=on` | Enable the named optimization |

The order of the commands in the value does not matter, although
the `default` command is executed first if
present. Setting an _`opt_name`_ flag to
`default` sets it to whichever of
`on` or `off` is its default
value. Specifying any given _`opt_name`_
more than once in the value is not permitted and causes an
error. Any errors in the value cause the assignment to fail with
an error, leaving the value of
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) unchanged.


The following list describes the permissible
_`opt_name`_ flag names, grouped by
optimization strategy:

- Batched Key Access Flags




- [`batched_key_access`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_batched-key-access)
(default `off`)



Controls use of BKA join algorithm.


For [`batched_key_access`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_batched-key-access) to
have any effect when set to `on`, the
[`mrr`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_mrr) flag must also be
`on`. Currently, the cost estimation for
MRR is too pessimistic. Hence, it is also necessary for
[`mrr_cost_based`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_mrr-cost-based) to be
`off` for BKA to be used.


For more information, see
[Section 10.2.1.12, “Block Nested-Loop and Batched Key Access Joins”](https://dev.mysql.com/doc/refman/8.0/en/bnl-bka-optimization.html "10.2.1.12 Block Nested-Loop and Batched Key Access Joins").


- Block Nested-Loop Flags




- [`block_nested_loop`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_block-nested-loop)
(default `on`)



Controls use of BNL join algorithm. In MySQL 8.0.18 and
later, this also controls use of hash joins, as do the
[`BNL`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") and
[`NO_BNL`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") optimizer
hints. In MySQL 8.0.20 and later, block nested loop
support is removed from the MySQL server, and this flag
controls the use of hash joins only, as do the
referenced optimizer hints.


For more information, see
[Section 10.2.1.12, “Block Nested-Loop and Batched Key Access Joins”](https://dev.mysql.com/doc/refman/8.0/en/bnl-bka-optimization.html "10.2.1.12 Block Nested-Loop and Batched Key Access Joins").


- Condition Filtering Flags




- [`condition_fanout_filter`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_condition-fanout-filter)
(default `on`)



Controls use of condition filtering.


For more information, see
[Section 10.2.1.13, “Condition Filtering”](https://dev.mysql.com/doc/refman/8.0/en/condition-filtering.html "10.2.1.13 Condition Filtering").


- Derived Condition Pushdown Flags




- [`derived_condition_pushdown`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_derived-condition-pushdown)
(default `on`)



Controls derived condition pushdown.


For more information, see
[Section 10.2.2.5, “Derived Condition Pushdown Optimization”](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html "10.2.2.5 Derived Condition Pushdown Optimization")

- Derived Table Merging Flags




- [`derived_merge`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_derived-merge) (default
`on`)



Controls merging of derived tables and views into outer
query block.


The [`derived_merge`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_derived-merge) flag
controls whether the optimizer attempts to merge derived
tables, view references, and common table expressions into
the outer query block, assuming that no other rule prevents
merging; for example, an `ALGORITHM`
directive for a view takes precedence over the
[`derived_merge`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_derived-merge) setting. By
default, the flag is `on` to enable
merging.


For more information, see
[Section 10.2.2.4, “Optimizing Derived Tables, View References, and Common Table Expressions\\
with Merging or Materialization”](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html "10.2.2.4 Optimizing Derived Tables, View References, and Common Table Expressions with Merging or Materialization").


- Engine Condition Pushdown Flags




- [`engine_condition_pushdown`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_engine-condition-pushdown)
(default `on`)



Controls engine condition pushdown.


For more information, see
[Section 10.2.1.5, “Engine Condition Pushdown Optimization”](https://dev.mysql.com/doc/refman/8.0/en/engine-condition-pushdown-optimization.html "10.2.1.5 Engine Condition Pushdown Optimization").


- Hash Join Flags




- [`hash_join`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_hash-join) (default
`on`)



Controls hash joins in MySQL 8.0.18 only, and has no
effect in any subsequent version. In MySQL 8.0.19 and
later, to control hash join usage, use the
[`block_nested_loop`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_block-nested-loop)
flag, instead.


For more information, see [Section 10.2.1.4, “Hash Join Optimization”](https://dev.mysql.com/doc/refman/8.0/en/hash-joins.html "10.2.1.4 Hash Join Optimization").


- Index Condition Pushdown Flags




- [`index_condition_pushdown`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_index-condition-pushdown)
(default `on`)



Controls index condition pushdown.


For more information, see
[Section 10.2.1.6, “Index Condition Pushdown Optimization”](https://dev.mysql.com/doc/refman/8.0/en/index-condition-pushdown-optimization.html "10.2.1.6 Index Condition Pushdown Optimization").


- Index Extensions Flags




- [`use_index_extensions`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_use-index-extensions)
(default `on`)



Controls use of index extensions.


For more information, see
[Section 10.3.10, “Use of Index Extensions”](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html "10.3.10 Use of Index Extensions").


- Index Merge Flags




- [`index_merge`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_index-merge) (default
`on`)



Controls all Index Merge optimizations.


- [`index_merge_intersection`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_index-merge-intersection)
(default `on`)



Controls the Index Merge Intersection Access
optimization.


- [`index_merge_sort_union`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_index-merge-sort-union)
(default `on`)



Controls the Index Merge Sort-Union Access optimization.


- [`index_merge_union`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_index-merge-union)
(default `on`)



Controls the Index Merge Union Access optimization.


For more information, see
[Section 10.2.1.3, “Index Merge Optimization”](https://dev.mysql.com/doc/refman/8.0/en/index-merge-optimization.html "10.2.1.3 Index Merge Optimization").


- Index Visibility Flags




- [`use_invisible_indexes`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_use-invisible-indexes)
(default `off`)



Controls use of invisible indexes.


For more information, see
[Section 10.3.12, “Invisible Indexes”](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html "10.3.12 Invisible Indexes").


- Limit Optimization Flags




- [`prefer_ordering_index`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_prefer-ordering-index)
(default `on`)



Controls whether, in the case of a query having an
`ORDER BY` or `GROUP
                  BY` with a `LIMIT` clause, the
optimizer tries to use an ordered index instead of an
unordered index, a filesort, or some other optimization.
This optimization is performed by default whenever the
optimizer determines that using it would allow for
faster execution of the query.



Because the algorithm that makes this determination
cannot handle every conceivable case (due in part to the
assumption that the distribution of data is always more
or less uniform), there are cases in which this
optimization may not be desirable. Prior to MySQL
8.0.21, it was not possible to disable this
optimization, but in MySQL 8.0.21 and later, while it
remains the default behavior, it can be disabled by
setting the
[`prefer_ordering_index`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_prefer-ordering-index)
flag to `off`.


For more information and examples, see
[Section 10.2.1.19, “LIMIT Query Optimization”](https://dev.mysql.com/doc/refman/8.0/en/limit-optimization.html "10.2.1.19 LIMIT Query Optimization").


- Multi-Range Read Flags




- [`mrr`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_mrr) (default
`on`)



Controls the Multi-Range Read strategy.


- [`mrr_cost_based`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_mrr-cost-based)
(default `on`)



Controls use of cost-based MRR if
[`mrr=on`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_mrr).


For more information, see
[Section 10.2.1.11, “Multi-Range Read Optimization”](https://dev.mysql.com/doc/refman/8.0/en/mrr-optimization.html "10.2.1.11 Multi-Range Read Optimization").


- Semijoin Flags




- [`duplicateweedout`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_duplicateweedout)
(default `on`)



Controls the semijoin Duplicate Weedout strategy.


- [`firstmatch`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_firstmatch) (default
`on`)



Controls the semijoin FirstMatch strategy.


- [`loosescan`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_loosescan) (default
`on`)



Controls the semijoin LooseScan strategy (not to be
confused with Loose Index Scan for `GROUP
                  BY`).


- [`semijoin`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_semijoin) (default
`on`)



Controls all semijoin strategies.



In MySQL 8.0.17 and later, this also applies to the
antijoin optimization.


The [`semijoin`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_semijoin),
[`firstmatch`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_firstmatch),
[`loosescan`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_loosescan), and
[`duplicateweedout`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_duplicateweedout) flags
enable control over semijoin strategies. The
[`semijoin`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_semijoin) flag controls
whether semijoins are used. If it is set to
`on`, the
[`firstmatch`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_firstmatch) and
[`loosescan`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_loosescan) flags enable
finer control over the permitted semijoin strategies.


If the [`duplicateweedout`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_duplicateweedout)
semijoin strategy is disabled, it is not used unless all
other applicable strategies are also disabled.


If [`semijoin`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_semijoin) and
[`materialization`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_materialization) are both
`on`, semijoins also use materialization
where applicable. These flags are `on` by
default.


For more information, see [Section 10.2.2.1, “Optimizing IN and EXISTS Subquery Predicates with Semijoin\\
Transformations”](https://dev.mysql.com/doc/refman/8.0/en/semijoins.html "10.2.2.1 Optimizing IN and EXISTS Subquery Predicates with Semijoin Transformations").


- Skip Scan Flags




- [`skip_scan`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_skip-scan) (default
`on`)



Controls use of Skip Scan access method.


For more information, see
[Skip Scan Range Access Method](https://dev.mysql.com/doc/refman/8.0/en/range-optimization.html#range-access-skip-scan "Skip Scan Range Access Method").


- Subquery Materialization Flags




- [`materialization`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_materialization)
(default `on`)



Controls materialization (including semijoin
materialization).


- [`subquery_materialization_cost_based`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_subquery-materialization-cost-based)
(default `on`)



Use cost-based materialization choice.


The [`materialization`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_materialization) flag
controls whether subquery materialization is used. If
[`semijoin`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_semijoin) and
[`materialization`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_materialization) are both
`on`, semijoins also use materialization
where applicable. These flags are `on` by
default.


The
[`subquery_materialization_cost_based`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_subquery-materialization-cost-based)
flag enables control over the choice between subquery
materialization and
`IN`-to- `EXISTS` subquery
transformation. If the flag is `on` (the
default), the optimizer performs a cost-based choice between
subquery materialization and
`IN`-to- `EXISTS` subquery
transformation if either method could be used. If the flag
is `off`, the optimizer chooses subquery
materialization over
`IN`-to- `EXISTS` subquery
transformation.


For more information, see
[Section 10.2.2, “Optimizing Subqueries, Derived Tables, View References, and Common Table\\
Expressions”](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization.html "10.2.2 Optimizing Subqueries, Derived Tables, View References, and Common Table Expressions").


- Subquery Transformation Flags




- [`subquery_to_derived`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_subquery-to-derived)
(default `off`)



Beginning with MySQL 8.0.21, the optimizer is able in
many cases to transform a scalar subquery in a
`SELECT`, `WHERE`,
`JOIN`, or `HAVING`
clause into a left outer join on a derived table.
(Depending on the nullability of the derived table, this
can sometimes be simplified further to an inner join.)
This can be done for a subquery which meets the
following conditions:




- The subquery does not make use of any
nondeterministic functions, such as
[`RAND()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_rand).


- The subquery is not an `ANY` or
`ALL` subquery which can be
rewritten to use
[`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min) or
[`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max).


- The parent query does not set a user variable, since
rewriting it may affect the order of execution,
which could lead to unexpected results if the
variable is accessed more than once in the same
query.


- The subquery should not be correlated, that is, it
should not reference a column from a table in the
outer query, or contain an aggregate that is
evaluated in the outer query.


Prior to MySQL 8.0.22, the subquery could not contain a
`GROUP BY` clause.


This optimization can also be applied to a table
subquery which is the argument to `IN`,
`NOT IN`, `EXISTS`, or
`NOT EXISTS`, that does not contain a
`GROUP BY`.


The default value for this flag is
`off`, since, in most cases, enabling
this optimization does not produce any noticeable
improvement in performance (and in many cases can even
make queries run more slowly), but you can enable the
optimization by setting the
[`subquery_to_derived`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_subquery-to-derived)
flag to `on`. It is primarily intended
for use in testing.


Example, using a scalar subquery:


``` sql

d
mysql> CREATE TABLE t1(a INT);

mysql> CREATE TABLE t2(a INT);

mysql> INSERT INTO t1 VALUES ROW(1), ROW(2), ROW(3), ROW(4);

mysql> INSERT INTO t2 VALUES ROW(1), ROW(2);

mysql> SELECT * FROM t1
    ->     WHERE t1.a > (SELECT COUNT(a) FROM t2);
+------+
| a    |
+------+
|    3 |
|    4 |
+------+

mysql> SELECT @@optimizer_switch LIKE '%subquery_to_derived=off%';
+-----------------------------------------------------+
| @@optimizer_switch LIKE '%subquery_to_derived=off%' |
+-----------------------------------------------------+
|                                                   1 |
+-----------------------------------------------------+

mysql> EXPLAIN SELECT * FROM t1 WHERE t1.a > (SELECT COUNT(a) FROM t2)\G
*************************** 1. row ***************************
           id: 1
  select_type: PRIMARY
        table: t1
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 4
     filtered: 33.33
        Extra: Using where
*************************** 2. row ***************************
           id: 2
  select_type: SUBQUERY
        table: t2
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 2
     filtered: 100.00
        Extra: NULL

mysql> SET @@optimizer_switch='subquery_to_derived=on';

mysql> SELECT @@optimizer_switch LIKE '%subquery_to_derived=off%';
+-----------------------------------------------------+
| @@optimizer_switch LIKE '%subquery_to_derived=off%' |
+-----------------------------------------------------+
|                                                   0 |
+-----------------------------------------------------+

mysql> SELECT @@optimizer_switch LIKE '%subquery_to_derived=on%';
+----------------------------------------------------+
| @@optimizer_switch LIKE '%subquery_to_derived=on%' |
+----------------------------------------------------+
|                                                  1 |
+----------------------------------------------------+

mysql> EXPLAIN SELECT * FROM t1 WHERE t1.a > (SELECT COUNT(a) FROM t2)\G
*************************** 1. row ***************************
           id: 1
  select_type: PRIMARY
        table: <derived2>
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 1
     filtered: 100.00
        Extra: NULL
*************************** 2. row ***************************
           id: 1
  select_type: PRIMARY
        table: t1
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 4
     filtered: 33.33
        Extra: Using where; Using join buffer (hash join)
*************************** 3. row ***************************
           id: 2
  select_type: DERIVED
        table: t2
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 2
     filtered: 100.00
        Extra: NULL
```

As can be seen from executing [`SHOW\\
                WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") immediately following the second
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") statement, with
the optimization enabled, the query `SELECT *
                FROM t1 WHERE t1.a > (SELECT COUNT(a) FROM
                t2)` is rewritten in a form similar to what is
shown here:


``` sql

SELECT t1.a FROM t1
    JOIN  ( SELECT COUNT(t2.a) AS c FROM t2 ) AS d
            WHERE t1.a > d.c;
```

Example, using a query with `IN
                (subquery)`:


``` sql

mysql> DROP TABLE IF EXISTS t1, t2;

mysql> CREATE TABLE t1 (a INT, b INT);
mysql> CREATE TABLE t2 (a INT, b INT);

mysql> INSERT INTO t1 VALUES ROW(1,10), ROW(2,20), ROW(3,30);
mysql> INSERT INTO t2
    ->    VALUES ROW(1,10), ROW(2,20), ROW(3,30), ROW(1,110), ROW(2,120), ROW(3,130);

mysql> SELECT * FROM t1
    ->     WHERE   t1.b < 0
    ->             OR
    ->             t1.a IN (SELECT t2.a + 1 FROM t2);
+------+------+
| a    | b    |
+------+------+
|    2 |   20 |
|    3 |   30 |
+------+------+

mysql> SET @@optimizer_switch="subquery_to_derived=off";

mysql> EXPLAIN SELECT * FROM t1
    ->             WHERE   t1.b < 0
    ->                     OR
    ->                     t1.a IN (SELECT t2.a + 1 FROM t2)\G
*************************** 1. row ***************************
           id: 1
  select_type: PRIMARY
        table: t1
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 3
     filtered: 100.00
        Extra: Using where
*************************** 2. row ***************************
           id: 2
  select_type: DEPENDENT SUBQUERY
        table: t2
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 6
     filtered: 100.00
        Extra: Using where

mysql> SET @@optimizer_switch="subquery_to_derived=on";

mysql> EXPLAIN SELECT * FROM t1
    ->             WHERE   t1.b < 0
    ->                     OR
    ->                     t1.a IN (SELECT t2.a + 1 FROM t2)\G
*************************** 1. row ***************************
           id: 1
  select_type: PRIMARY
        table: t1
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 3
     filtered: 100.00
        Extra: NULL
*************************** 2. row ***************************
           id: 1
  select_type: PRIMARY
        table: <derived2>
   partitions: NULL
         type: ref
possible_keys: <auto_key0>
          key: <auto_key0>
      key_len: 9
          ref: std2.t1.a
         rows: 2
     filtered: 100.00
        Extra: Using where; Using index
*************************** 3. row ***************************
           id: 2
  select_type: DERIVED
        table: t2
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 6
     filtered: 100.00
        Extra: Using temporary
```

Checking and simplifying the result of
[`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") after
executing [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") on this
query shows that, when the
[`subquery_to_derived`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_subquery-to-derived)
flag enabled, `SELECT * FROM t1 WHERE t1.b <
                0 OR t1.a IN (SELECT t2.a + 1 FROM t2)` is
rewritten in a form similar to what is shown here:


``` sql

SELECT a, b FROM t1
    LEFT JOIN (SELECT DISTINCT a + 1 AS e FROM t2) d
    ON t1.a = d.e
    WHERE   t1.b < 0
            OR
            d.e IS NOT NULL;
```

Example, using a query with `EXISTS
                (subquery)` and the
same tables and data as in the previous example:


``` sql

mysql> SELECT * FROM t1
    ->     WHERE   t1.b < 0
    ->             OR
    ->             EXISTS(SELECT * FROM t2 WHERE t2.a = t1.a + 1);
+------+------+
| a    | b    |
+------+------+
|    1 |   10 |
|    2 |   20 |
+------+------+

mysql> SET @@optimizer_switch="subquery_to_derived=off";

mysql> EXPLAIN SELECT * FROM t1
    ->             WHERE   t1.b < 0
    ->                     OR
    ->                     EXISTS(SELECT * FROM t2 WHERE t2.a = t1.a + 1)\G
*************************** 1. row ***************************
           id: 1
  select_type: PRIMARY
        table: t1
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 3
     filtered: 100.00
        Extra: Using where
*************************** 2. row ***************************
           id: 2
  select_type: DEPENDENT SUBQUERY
        table: t2
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 6
     filtered: 16.67
        Extra: Using where

mysql> SET @@optimizer_switch="subquery_to_derived=on";

mysql> EXPLAIN SELECT * FROM t1
    ->             WHERE   t1.b < 0
    ->                     OR
    ->                     EXISTS(SELECT * FROM t2 WHERE t2.a = t1.a + 1)\G
*************************** 1. row ***************************
           id: 1
  select_type: PRIMARY
        table: t1
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 3
     filtered: 100.00
        Extra: NULL
*************************** 2. row ***************************
           id: 1
  select_type: PRIMARY
        table: <derived2>
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 6
     filtered: 100.00
        Extra: Using where; Using join buffer (hash join)
*************************** 3. row ***************************
           id: 2
  select_type: DERIVED
        table: t2
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 6
     filtered: 100.00
        Extra: Using temporary
```

If we execute [`SHOW\\
                WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") after running
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") on the query
`SELECT * FROM t1 WHERE t1.b < 0 OR
                EXISTS(SELECT * FROM t2 WHERE t2.a = t1.a + 1)`
when
[`subquery_to_derived`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_subquery-to-derived)
has been enabled, and simplify the second row of the
result, we see that it has been rewritten in a form
which resembles this:


``` sql

SELECT a, b FROM t1
LEFT JOIN (SELECT DISTINCT 1 AS e1, t2.a AS e2 FROM t2) d
ON t1.a + 1 = d.e2
WHERE   t1.b < 0
        OR
        d.e1 IS NOT NULL;
```

For more information, see
[Section 10.2.2.4, “Optimizing Derived Tables, View References, and Common Table Expressions\\
with Merging or Materialization”](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html "10.2.2.4 Optimizing Derived Tables, View References, and Common Table Expressions with Merging or Materialization"), as well as
[Section 10.2.1.19, “LIMIT Query Optimization”](https://dev.mysql.com/doc/refman/8.0/en/limit-optimization.html "10.2.1.19 LIMIT Query Optimization"), and
[Section 10.2.2.1, “Optimizing IN and EXISTS Subquery Predicates with Semijoin\\
Transformations”](https://dev.mysql.com/doc/refman/8.0/en/semijoins.html "10.2.2.1 Optimizing IN and EXISTS Subquery Predicates with Semijoin Transformations").

When you assign a value to
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch), flags that
are not mentioned keep their current values. This makes it
possible to enable or disable specific optimizer behaviors in a
single statement without affecting other behaviors. The
statement does not depend on what other optimizer flags exist
and what their values are. Suppose that all Index Merge
optimizations are enabled:


``` sql

mysql> SELECT @@optimizer_switch\G
*************************** 1. row ***************************
@@optimizer_switch: index_merge=on,index_merge_union=on,
                    index_merge_sort_union=on,index_merge_intersection=on,
                    engine_condition_pushdown=on,index_condition_pushdown=on,
                    mrr=on,mrr_cost_based=on,block_nested_loop=on,
                    batched_key_access=off,materialization=on,semijoin=on,
                    loosescan=on, firstmatch=on,
                    subquery_materialization_cost_based=on,
                    use_index_extensions=on,condition_fanout_filter=on,
                    derived_merge=on,use_invisible_indexes=off,skip_scan=on,
                    hash_join=on,subquery_to_derived=off,
                    prefer_ordering_index=on
```

If the server is using the Index Merge Union or Index Merge
Sort-Union access methods for certain queries and you want to
check whether the optimizer can perform better without them, set
the variable value like this:


``` sql

mysql> SET optimizer_switch='index_merge_union=off,index_merge_sort_union=off';

mysql> SELECT @@optimizer_switch\G
*************************** 1. row ***************************
@@optimizer_switch: index_merge=on,index_merge_union=off,
                    index_merge_sort_union=off,index_merge_intersection=on,
                    engine_condition_pushdown=on,index_condition_pushdown=on,
                    mrr=on,mrr_cost_based=on,block_nested_loop=on,
                    batched_key_access=off,materialization=on,semijoin=on,
                    loosescan=on, firstmatch=on,
                    subquery_materialization_cost_based=on,
                    use_index_extensions=on,condition_fanout_filter=on,
                    derived_merge=on,use_invisible_indexes=off,skip_scan=on,
                    hash_join=on,subquery_to_derived=off,
                    prefer_ordering_index=on
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html "Previous: Controlling Query Plan Evaluation") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html "Up: Controlling the Query Optimizer") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html "Next: Optimizer Hints")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html)

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