---
url: https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html
scraped_at: 2025-10-20T03:13:41.215Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html "Hide Sidebar")

[Previous: Switchable Optimizations](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html "Previous: Switchable Optimizations")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Controlling the Query Optimizer](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html "Up: Controlling the Query Optimizer")[Next: Index Hints](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html "Next: Index Hints")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/optimizer-hints.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/optimizer-hints.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/optimizer-hints.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/optimizer-hints.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/optimizer-hints.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/optimizer-hints.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/optimizer-hints.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/optimizer-hints.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Controlling the Query Optimizer](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html)  /

Optimizer Hints


### 10.9.3 Optimizer Hints

One means of control over optimizer strategies is to set the
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) system
variable (see [Section 10.9.2, “Switchable Optimizations”](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html "10.9.2 Switchable Optimizations")).
Changes to this variable affect execution of all subsequent
queries; to affect one query differently from another, it is
necessary to change
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) before each
one.


Another way to control the optimizer is by using optimizer
hints, which can be specified within individual statements.
Because optimizer hints apply on a per-statement basis, they
provide finer control over statement execution plans than can be
achieved using
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch). For example,
you can enable an optimization for one table in a statement and
disable the optimization for a different table. Hints within a
statement take precedence over
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) flags.


Examples:


``` sql

SELECT /*+ NO_RANGE_OPTIMIZATION(t3 PRIMARY, f2_idx) */ f1
  FROM t3 WHERE f1 > 30 AND f1 < 33;
SELECT /*+ BKA(t1) NO_BKA(t2) */ * FROM t1 INNER JOIN t2 WHERE ...;
SELECT /*+ NO_ICP(t1, t2) */ * FROM t1 INNER JOIN t2 WHERE ...;
SELECT /*+ SEMIJOIN(FIRSTMATCH, LOOSESCAN) */ * FROM t1 ...;
EXPLAIN SELECT /*+ NO_ICP(t1) */ * FROM t1 WHERE ...;
SELECT /*+ MERGE(dt) */ * FROM (SELECT * FROM t1) AS dt;
INSERT /*+ SET_VAR(foreign_key_checks=OFF) */ INTO t2 VALUES(2);
```

Optimizer hints, described here, differ from index hints,
described in [Section 10.9.4, “Index Hints”](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html "10.9.4 Index Hints"). Optimizer and index
hints may be used separately or together.

- [Optimizer Hint Overview](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-overview "Optimizer Hint Overview")

- [Optimizer Hint Syntax](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-syntax "Optimizer Hint Syntax")

- [Join-Order Optimizer Hints](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints")

- [Table-Level Optimizer Hints](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints")

- [Index-Level Optimizer Hints](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints")

- [Subquery Optimizer Hints](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints")

- [Statement Execution Time Optimizer Hints](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-execution-time "Statement Execution Time Optimizer Hints")

- [Variable-Setting Hint Syntax](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax")

- [Resource Group Hint Syntax](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-resource-group "Resource Group Hint Syntax")

- [Optimizer Hints for Naming Query Blocks](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-query-block-naming "Optimizer Hints for Naming Query Blocks")


#### Optimizer Hint Overview

Optimizer hints apply at different scope levels:

- Global: The hint affects the entire statement


- Query block: The hint affects a particular query block
within a statement


- Table-level: The hint affects a particular table within a
query block


- Index-level: The hint affects a particular index within a
table


The following table summarizes the available optimizer hints,
the optimizer strategies they affect, and the scope or scopes
at which they apply. More details are given later.

**Table 10.2 Optimizer Hints Available**

| Hint Name | Description | Applicable Scopes |
| --- | --- | --- |
| [`BKA`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"),<br> [`NO_BKA`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") | Affects Batched Key Access join processing | Query block, table |
| [`BNL`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"),<br> [`NO_BNL`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") | Prior to MySQL 8.0.20: affects Block Nested-Loop join processing; MySQL<br> 8.0.18 and later: also affects hash join optimization;<br> MySQL 8.0.20 and later: affects hash join optimization<br> only | Query block, table |
| [`DERIVED_CONDITION_PUSHDOWN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"),<br> [`NO_DERIVED_CONDITION_PUSHDOWN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") | Use or ignore the derived condition pushdown optimization for<br> materialized derived tables (Added in MySQL 8.0.22) | Query block, table |
| [`GROUP_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),<br> [`NO_GROUP_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") | Use or ignore the specified index or indexes for index scans in<br> `GROUP BY` operations (Added in MySQL<br> 8.0.20) | Index |
| [`HASH_JOIN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"),<br> [`NO_HASH_JOIN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") | Affects Hash Join optimization (MySQL 8.0.18 only | Query block, table |
| [`INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),<br> [`NO_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") | Acts as the combination of [`JOIN_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),<br> [`GROUP_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"), and<br> [`ORDER_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"), or as the<br> combination of<br> [`NO_JOIN_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),<br> [`NO_GROUP_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"), and<br> [`NO_ORDER_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") (Added<br> in MySQL 8.0.20) | Index |
| [`INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),<br> [`NO_INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") | Affects Index Merge optimization | Table, index |
| [`JOIN_FIXED_ORDER`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") | Use table order specified in `FROM` clause for join<br> order | Query block |
| [`JOIN_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),<br> [`NO_JOIN_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") | Use or ignore the specified index or indexes for any access method<br> (Added in MySQL 8.0.20) | Index |
| [`JOIN_ORDER`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") | Use table order specified in hint for join order | Query block |
| [`JOIN_PREFIX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") | Use table order specified in hint for first tables of join order | Query block |
| [`JOIN_SUFFIX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") | Use table order specified in hint for last tables of join order | Query block |
| [`MAX_EXECUTION_TIME`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-execution-time "Statement Execution Time Optimizer Hints") | Limits statement execution time | Global |
| [`MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"),<br> [`NO_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") | Affects derived table/view merging into outer query block | Table |
| [`MRR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),<br> [`NO_MRR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") | Affects Multi-Range Read optimization | Table, index |
| [`NO_ICP`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") | Affects Index Condition Pushdown optimization | Table, index |
| [`NO_RANGE_OPTIMIZATION`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") | Affects range optimization | Table, index |
| [`ORDER_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),<br> [`NO_ORDER_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") | Use or ignore the specified index or indexes for sorting rows (Added in<br> MySQL 8.0.20) | Index |
| [`QB_NAME`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-query-block-naming "Optimizer Hints for Naming Query Blocks") | Assigns name to query block | Query block |
| [`RESOURCE_GROUP`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-resource-group "Resource Group Hint Syntax") | Set resource group during statement execution | Global |
| [`SEMIJOIN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints"),<br> [`NO_SEMIJOIN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints") | Affects semijoin strategies; beginning with MySQL 8.0.17, this also<br> applies to antijoins | Query block |
| [`SKIP_SCAN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),<br> [`NO_SKIP_SCAN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") | Affects Skip Scan optimization | Table, index |
| [`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax") | Set variable during statement execution | Global |
| [`SUBQUERY`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints") | Affects materialization,<br> `IN`-to- `EXISTS`<br> subquery strategies | Query block |

| Hint Name | Description | Applicable Scopes |
| --- | --- | --- |

Disabling an optimization prevents the optimizer from using
it. Enabling an optimization means the optimizer is free to
use the strategy if it applies to statement execution, not
that the optimizer necessarily uses it.

#### Optimizer Hint Syntax

MySQL supports comments in SQL statements as described in
[Section 11.7, “Comments”](https://dev.mysql.com/doc/refman/8.0/en/comments.html "11.7 Comments"). Optimizer hints must be specified
within `/*+ ... */` comments. That is,
optimizer hints use a variant of `/* ... */`
C-style comment syntax, with a `+` character
following the `/*` comment opening sequence.
Examples:


``` sql

/*+ BKA(t1) */
/*+ BNL(t1, t2) */
/*+ NO_RANGE_OPTIMIZATION(t4 PRIMARY) */
/*+ QB_NAME(qb2) */
```

Whitespace is permitted after the `+`
character.


The parser recognizes optimizer hint comments after the
initial keyword of [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"),
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"),
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"),
[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement"), and
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statements. Hints are
permitted in these contexts:

- At the beginning of query and data change statements:




``` sql

SELECT /*+ ... */ ...
INSERT /*+ ... */ ...
REPLACE /*+ ... */ ...
UPDATE /*+ ... */ ...
DELETE /*+ ... */ ...
```

- At the beginning of query blocks:




``` sql

(SELECT /*+ ... */ ... )
(SELECT ... ) UNION (SELECT /*+ ... */ ... )
(SELECT /*+ ... */ ... ) UNION (SELECT /*+ ... */ ... )
UPDATE ... WHERE x IN (SELECT /*+ ... */ ...)
INSERT ... SELECT /*+ ... */ ...
```

- In hintable statements prefaced by
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement"). For example:




``` sql

EXPLAIN SELECT /*+ ... */ ...
EXPLAIN UPDATE ... WHERE x IN (SELECT /*+ ... */ ...)
```




The implication is that you can use
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") to see how
optimizer hints affect execution plans. Use
[`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") immediately
after [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") to see how
hints are used. The extended `EXPLAIN`
output displayed by a following [`SHOW\\
                WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") indicates which hints were used.
Ignored hints are not displayed.


A hint comment may contain multiple hints, but a query block
cannot contain multiple hint comments. This is valid:


``` sql

SELECT /*+ BNL(t1) BKA(t2) */ ...
```

But this is invalid:


``` sql

SELECT /*+ BNL(t1) */ /* BKA(t2) */ ...
```

When a hint comment contains multiple hints, the possibility
of duplicates and conflicts exists. The following general
guidelines apply. For specific hint types, additional rules
may apply, as indicated in the hint descriptions.

- Duplicate hints: For a hint such as `/*+ MRR(idx1)
                MRR(idx1) */`, MySQL uses the first hint and
issues a warning about the duplicate hint.


- Conflicting hints: For a hint such as `/*+
                MRR(idx1) NO_MRR(idx1) */`, MySQL uses the first
hint and issues a warning about the second conflicting
hint.


Query block names are identifiers and follow the usual rules
about what names are valid and how to quote them (see
[Section 11.2, “Schema Object Names”](https://dev.mysql.com/doc/refman/8.0/en/identifiers.html "11.2 Schema Object Names")).


Hint names, query block names, and strategy names are not
case-sensitive. References to table and index names follow the
usual identifier case-sensitivity rules (see
[Section 11.2.3, “Identifier Case Sensitivity”](https://dev.mysql.com/doc/refman/8.0/en/identifier-case-sensitivity.html "11.2.3 Identifier Case Sensitivity")).

#### Join-Order Optimizer Hints

Join-order hints affect the order in which the optimizer joins
tables.


Syntax of the
[`JOIN_FIXED_ORDER`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") hint:


``` sql

hint_name([@query_block_name])
```

Syntax of other join-order hints:


``` sql

hint_name([@query_block_name] tbl_name [, tbl_name] ...)
hint_name(tbl_name[@query_block_name] [, tbl_name[@query_block_name]] ...)
```

The syntax refers to these terms:

- _`hint_name`_: These hint names are
permitted:




- [`JOIN_FIXED_ORDER`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints"):
Force the optimizer to join tables using the order in
which they appear in the `FROM`
clause. This is the same as specifying `SELECT
                    STRAIGHT_JOIN`.


- [`JOIN_ORDER`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints"): Instruct
the optimizer to join tables using the specified table
order. The hint applies to the named tables. The
optimizer may place tables that are not named anywhere
in the join order, including between specified tables.


- [`JOIN_PREFIX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints"):
Instruct the optimizer to join tables using the
specified table order for the first tables of the join
execution plan. The hint applies to the named tables.
The optimizer places all other tables after the named
tables.


- [`JOIN_SUFFIX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints"):
Instruct the optimizer to join tables using the
specified table order for the last tables of the join
execution plan. The hint applies to the named tables.
The optimizer places all other tables before the named
tables.


- _`tbl_name`_: The name of a table
used in the statement. A hint that names tables applies to
all tables that it names. The
[`JOIN_FIXED_ORDER`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") hint
names no tables and applies to all tables in the
`FROM` clause of the query block in which
it occurs.



If a table has an alias, hints must refer to the alias,
not the table name.



Table names in hints cannot be qualified with schema
names.


- _`query_block_name`_: The query
block to which the hint applies. If the hint includes no
leading
`@query_block_name`,
the hint applies to the query block in which it occurs.
For
`tbl_name@query_block_name`
syntax, the hint applies to the named table in the named
query block. To assign a name to a query block, see
[Optimizer Hints for Naming Query Blocks](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-query-block-naming "Optimizer Hints for Naming Query Blocks").


Example:


``` sql

SELECT
/*+ JOIN_PREFIX(t2, t5@subq2, t4@subq1)
    JOIN_ORDER(t4@subq1, t3)
    JOIN_SUFFIX(t1) */
COUNT(*) FROM t1 JOIN t2 JOIN t3
           WHERE t1.f1 IN (SELECT /*+ QB_NAME(subq1) */ f1 FROM t4)
             AND t2.f1 IN (SELECT /*+ QB_NAME(subq2) */ f1 FROM t5);
```

Hints control the behavior of semijoin tables that are merged
to the outer query block. If subqueries
`subq1` and `subq2` are
converted to semijoins, tables `t4@subq1` and
`t5@subq2` are merged to the outer query
block. In this case, the hint specified in the outer query
block controls the behavior of `t4@subq1`,
`t5@subq2` tables.


The optimizer resolves join-order hints according to these
principles:

- Multiple hint instances



Only one [`JOIN_PREFIX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") and
[`JOIN_SUFFIX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") hint of each
type are applied. Any later hints of the same type are
ignored with a warning.
[`JOIN_ORDER`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") can be
specified several times.



Examples:




``` sql

/*+ JOIN_PREFIX(t1) JOIN_PREFIX(t2) */
```




The second [`JOIN_PREFIX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints")
hint is ignored with a warning.




``` sql

/*+ JOIN_PREFIX(t1) JOIN_SUFFIX(t2) */
```




Both hints are applicable. No warning occurs.




``` sql

/*+ JOIN_ORDER(t1, t2) JOIN_ORDER(t2, t3) */
```




Both hints are applicable. No warning occurs.


- Conflicting hints



In some cases hints can conflict, such as when
[`JOIN_ORDER`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") and
[`JOIN_PREFIX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") have table
orders that are impossible to apply at the same time:




``` sql

SELECT /*+ JOIN_ORDER(t1, t2) JOIN_PREFIX(t2, t1) */ ... FROM t1, t2;
```




In this case, the first specified hint is applied and
subsequent conflicting hints are ignored with no warning.
A valid hint that is impossible to apply is silently
ignored with no warning.


- Ignored hints



A hint is ignored if a table specified in the hint has a
circular dependency.



Example:




``` sql

/*+ JOIN_ORDER(t1, t2) JOIN_PREFIX(t2, t1) */
```




The [`JOIN_ORDER`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") hint sets
table `t2` dependent on
`t1`. The
[`JOIN_PREFIX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-join-order "Join-Order Optimizer Hints") hint is
ignored because table `t1` cannot be
dependent on `t2`. Ignored hints are not
displayed in extended
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") output.


- Interaction with [`const`](https://dev.mysql.com/doc/refman/8.0/en/explain-output.html#jointype_const)
tables



The MySQL optimizer places `const` tables
first in the join order, and the position of a
`const` table cannot be affected by
hints. References to `const` tables in
join-order hints are ignored, although the hint is still
applicable. For example, these are equivalent:




``` sql

JOIN_ORDER(t1, const_tbl, t2)
JOIN_ORDER(t1, t2)
```




Accepted hints shown in extended
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") output include
`const` tables as they were specified.


- Interaction with types of join operations



MySQL supports several type of joins:
`LEFT`, `RIGHT`,
`INNER`, `CROSS`,
`STRAIGHT_JOIN`. A hint that conflicts
with the specified type of join is ignored with no
warning.



Example:




``` sql

SELECT /*+ JOIN_PREFIX(t1, t2) */FROM t2 LEFT JOIN t1;
```




Here a conflict occurs between the requested join order in
the hint and the order required by the `LEFT
                JOIN`. The hint is ignored with no warning.


#### Table-Level Optimizer Hints

Table-level hints affect:

- Use of the Block Nested-Loop (BNL) and Batched Key Access
(BKA) join-processing algorithms (see
[Section 10.2.1.12, “Block Nested-Loop and Batched Key Access Joins”](https://dev.mysql.com/doc/refman/8.0/en/bnl-bka-optimization.html "10.2.1.12 Block Nested-Loop and Batched Key Access Joins")).


- Whether derived tables, view references, or common table
expressions should be merged into the outer query block,
or materialized using an internal temporary table.


- Use of the derived table condition pushdown optimization
(added in MySQL 8.0.22). See
[Section 10.2.2.5, “Derived Condition Pushdown Optimization”](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html "10.2.2.5 Derived Condition Pushdown Optimization").


These hint types apply to specific tables, or all tables in a
query block.


Syntax of table-level hints:


``` sql

hint_name([@query_block_name] [tbl_name [, tbl_name] ...])
hint_name([tbl_name@query_block_name [, tbl_name@query_block_name] ...])
```

The syntax refers to these terms:

- _`hint_name`_: These hint names are
permitted:




- [`BKA`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"),
[`NO_BKA`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"): Enable or
disable batched key access for the specified tables.


- [`BNL`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"),
[`NO_BNL`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"): Enable or
disable block nested loop for the specified tables. In
MySQL 8.0.18 and later, these hints also enable and
disable the hash join optimization.





Note





The block-nested loop optimization is removed in
MySQL 8.0.20 and later releases, but
`BNL` and `NO_BNL`
continue to be supported for enabling and disabling
hash joins.

- [`DERIVED_CONDITION_PUSHDOWN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"),
[`NO_DERIVED_CONDITION_PUSHDOWN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"):
Enable or disable use of derived table condition
pushdown for the specified tables (added in MySQL
8.0.22). For more information, see
[Section 10.2.2.5, “Derived Condition Pushdown Optimization”](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html "10.2.2.5 Derived Condition Pushdown Optimization").


- [`HASH_JOIN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"),
[`NO_HASH_JOIN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"): In
MySQL 8.0.18 only, enable or disable use of a hash
join for the specified tables. These hints have no
effect in MySQL 8.0.19 or later, where you should use
[`BNL`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") or
[`NO_BNL`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") instead.


- [`MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"),
[`NO_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints"): Enable
merging for the specified tables, view references or
common table expressions; or disable merging and use
materialization instead.


Note

To use a block nested loop or batched key access hint to
enable join buffering for any inner table of an outer
join, join buffering must be enabled for all inner
tables of the outer join.

- _`tbl_name`_: The name of a table
used in the statement. The hint applies to all tables that
it names. If the hint names no tables, it applies to all
tables of the query block in which it occurs.



If a table has an alias, hints must refer to the alias,
not the table name.



Table names in hints cannot be qualified with schema
names.


- _`query_block_name`_: The query
block to which the hint applies. If the hint includes no
leading
`@query_block_name`,
the hint applies to the query block in which it occurs.
For
`tbl_name@query_block_name`
syntax, the hint applies to the named table in the named
query block. To assign a name to a query block, see
[Optimizer Hints for Naming Query Blocks](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-query-block-naming "Optimizer Hints for Naming Query Blocks").


Examples:


``` sql

SELECT /*+ NO_BKA(t1, t2) */ t1.* FROM t1 INNER JOIN t2 INNER JOIN t3;
SELECT /*+ NO_BNL() BKA(t1) */ t1.* FROM t1 INNER JOIN t2 INNER JOIN t3;
SELECT /*+ NO_MERGE(dt) */ * FROM (SELECT * FROM t1) AS dt;
```

A table-level hint applies to tables that receive records from
previous tables, not sender tables. Consider this statement:


``` sql

SELECT /*+ BNL(t2) */ FROM t1, t2;
```

If the optimizer chooses to process `t1`
first, it applies a Block Nested-Loop join to
`t2` by buffering the rows from
`t1` before starting to read from
`t2`. If the optimizer instead chooses to
process `t2` first, the hint has no effect
because `t2` is a sender table.


For the [`MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") and
[`NO_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") hints, these
precedence rules apply:

- A hint takes precedence over any optimizer heuristic that
is not a technical constraint. (If providing a hint as a
suggestion has no effect, the optimizer has a reason for
ignoring it.)


- A hint takes precedence over the
[`derived_merge`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_derived-merge) flag of
the [`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch)
system variable.


- For view references, an
`ALGORITHM={MERGE|TEMPTABLE}` clause in
the view definition takes precedence over a hint specified
in the query referencing the view.


#### Index-Level Optimizer Hints

Index-level hints affect which index-processing strategies the
optimizer uses for particular tables or indexes. These hint
types affect use of Index Condition Pushdown (ICP),
Multi-Range Read (MRR), Index Merge, and range optimizations
(see [Section 10.2.1, “Optimizing SELECT Statements”](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html "10.2.1 Optimizing SELECT Statements")).


Syntax of index-level hints:


``` sql

hint_name([@query_block_name] tbl_name [index_name [, index_name] ...])
hint_name(tbl_name@query_block_name [index_name [, index_name] ...])
```

The syntax refers to these terms:

- _`hint_name`_: These hint names are
permitted:




- [`GROUP_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`NO_GROUP_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"):
Enable or disable the specified index or indexes for
index scans for `GROUP BY`
operations. Equivalent to the index hints
`FORCE INDEX FOR GROUP BY`,
`IGNORE INDEX FOR GROUP BY`.
Available in MySQL 8.0.20 and later.


- [`INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`NO_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"): Acts as
the combination of
[`JOIN_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`GROUP_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"), and
[`ORDER_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"), forcing
the server to use the specified index or indexes for
any and all scopes, or as the combination of
[`NO_JOIN_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`NO_GROUP_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"), and
[`NO_ORDER_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
which causes the server to ignore the specified index
or indexes for any and all scopes. Equivalent to
`FORCE INDEX`, `IGNORE
                    INDEX`. Available beginning with MySQL
8.0.20.


- [`INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`NO_INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"):
Enable or disable the Index Merge access method for
the specified table or indexes. For information about
this access method, see
[Section 10.2.1.3, “Index Merge Optimization”](https://dev.mysql.com/doc/refman/8.0/en/index-merge-optimization.html "10.2.1.3 Index Merge Optimization"). These
hints apply to all three Index Merge algorithms.



The [`INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") hint
forces the optimizer to use Index Merge for the
specified table using the specified set of indexes. If
no index is specified, the optimizer considers all
possible index combinations and selects the least
expensive one. The hint may be ignored if the index
combination is inapplicable to the given statement.



The [`NO_INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints")
hint disables Index Merge combinations that involve
any of the specified indexes. If the hint specifies no
indexes, Index Merge is not permitted for the table.


- [`JOIN_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`NO_JOIN_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"):
Forces MySQL to use or ignore the specified index or
indexes for any access method, such as
`ref`, `range`,
[`index_merge`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_index-merge), and so
on. Equivalent to `FORCE INDEX FOR
                    JOIN`, `IGNORE INDEX FOR
                    JOIN`. Available in MySQL 8.0.20 and later.


- [`MRR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`NO_MRR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"): Enable or
disable MRR for the specified table or indexes. MRR
hints apply only to `InnoDB` and
`MyISAM` tables. For information
about this access method, see
[Section 10.2.1.11, “Multi-Range Read Optimization”](https://dev.mysql.com/doc/refman/8.0/en/mrr-optimization.html "10.2.1.11 Multi-Range Read Optimization").


- [`NO_ICP`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"): Disable ICP
for the specified table or indexes. By default, ICP is
a candidate optimization strategy, so there is no hint
for enabling it. For information about this access
method, see
[Section 10.2.1.6, “Index Condition Pushdown Optimization”](https://dev.mysql.com/doc/refman/8.0/en/index-condition-pushdown-optimization.html "10.2.1.6 Index Condition Pushdown Optimization").


- [`NO_RANGE_OPTIMIZATION`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"):
Disable index range access for the specified table or
indexes. This hint also disables Index Merge and Loose
Index Scan for the table or indexes. By default, range
access is a candidate optimization strategy, so there
is no hint for enabling it.



This hint may be useful when the number of ranges may
be high and range optimization would require many
resources.


- [`ORDER_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`NO_ORDER_INDEX`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"):
Cause MySQL to use or to ignore the specified index or
indexes for sorting rows. Equivalent to `FORCE
                    INDEX FOR ORDER BY`, `IGNORE INDEX
                    FOR ORDER BY`. Available beginning with MySQL
8.0.20.


- [`SKIP_SCAN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"),
[`NO_SKIP_SCAN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"): Enable
or disable the Skip Scan access method for the
specified table or indexes. For information about this
access method, see
[Skip Scan Range Access Method](https://dev.mysql.com/doc/refman/8.0/en/range-optimization.html#range-access-skip-scan "Skip Scan Range Access Method"). These hints
are available as of MySQL 8.0.13.



The [`SKIP_SCAN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") hint
forces the optimizer to use Skip Scan for the
specified table using the specified set of indexes. If
no index is specified, the optimizer considers all
possible indexes and selects the least expensive one.
The hint may be ignored if the index is inapplicable
to the given statement.



The [`NO_SKIP_SCAN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints")
hint disables Skip Scan for the specified indexes. If
the hint specifies no indexes, Skip Scan is not
permitted for the table.


- _`tbl_name`_: The table to which
the hint applies.


- _`index_name`_: The name of an
index in the named table. The hint applies to all indexes
that it names. If the hint names no indexes, it applies to
all indexes in the table.



To refer to a primary key, use the name
`PRIMARY`. To see the index names for a
table, use [`SHOW INDEX`](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "15.7.7.22 SHOW INDEX Statement").


- _`query_block_name`_: The query
block to which the hint applies. If the hint includes no
leading
`@query_block_name`,
the hint applies to the query block in which it occurs.
For
`tbl_name@query_block_name`
syntax, the hint applies to the named table in the named
query block. To assign a name to a query block, see
[Optimizer Hints for Naming Query Blocks](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-query-block-naming "Optimizer Hints for Naming Query Blocks").


Examples:


``` sql

SELECT /*+ INDEX_MERGE(t1 f3, PRIMARY) */ f2 FROM t1
  WHERE f1 = 'o' AND f2 = f3 AND f3 <= 4;
SELECT /*+ MRR(t1) */ * FROM t1 WHERE f2 <= 3 AND 3 <= f3;
SELECT /*+ NO_RANGE_OPTIMIZATION(t3 PRIMARY, f2_idx) */ f1
  FROM t3 WHERE f1 > 30 AND f1 < 33;
INSERT INTO t3(f1, f2, f3)
  (SELECT /*+ NO_ICP(t2) */ t2.f1, t2.f2, t2.f3 FROM t1,t2
   WHERE t1.f1=t2.f1 AND t2.f2 BETWEEN t1.f1
   AND t1.f2 AND t2.f2 + 1 >= t1.f1 + 1);
SELECT /*+ SKIP_SCAN(t1 PRIMARY) */ f1, f2
  FROM t1 WHERE f2 > 40;
```

The following examples use the Index Merge hints, but other
index-level hints follow the same principles regarding hint
ignoring and precedence of optimizer hints in relation to the
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) system
variable or index hints.


Assume that table `t1` has columns
`a`, `b`,
`c`, and `d`; and that
indexes named `i_a`, `i_b`,
and `i_c` exist on `a`,
`b`, and `c`, respectively:


``` sql

SELECT /*+ INDEX_MERGE(t1 i_a, i_b, i_c)*/ * FROM t1
  WHERE a = 1 AND b = 2 AND c = 3 AND d = 4;
```

Index Merge is used for `(i_a, i_b, i_c)` in
this case.


``` sql

SELECT /*+ INDEX_MERGE(t1 i_a, i_b, i_c)*/ * FROM t1
  WHERE b = 1 AND c = 2 AND d = 3;
```

Index Merge is used for `(i_b, i_c)` in this
case.


``` sql

/*+ INDEX_MERGE(t1 i_a, i_b) NO_INDEX_MERGE(t1 i_b) */
```

[`NO_INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") is ignored
because there is a preceding hint for the same table.


``` sql

/*+ NO_INDEX_MERGE(t1 i_a, i_b) INDEX_MERGE(t1 i_b) */
```

[`INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") is ignored
because there is a preceding hint for the same table.


For the [`INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") and
[`NO_INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") optimizer
hints, these precedence rules apply:

- If an optimizer hint is specified and is applicable, it
takes precedence over the Index Merge-related flags of the
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) system
variable.




``` sql

SET optimizer_switch='index_merge_intersection=off';
SELECT /*+ INDEX_MERGE(t1 i_b, i_c) */ * FROM t1
WHERE b = 1 AND c = 2 AND d = 3;
```




The hint takes precedence over
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch). Index
Merge is used for `(i_b, i_c)` in this
case.




``` sql

SET optimizer_switch='index_merge_intersection=on';
SELECT /*+ INDEX_MERGE(t1 i_b) */ * FROM t1
WHERE b = 1 AND c = 2 AND d = 3;
```




The hint specifies only one index, so it is inapplicable,
and the [`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch)
flag ( `on`) applies. Index Merge is used
if the optimizer assesses it to be cost efficient.




``` sql

SET optimizer_switch='index_merge_intersection=off';
SELECT /*+ INDEX_MERGE(t1 i_b) */ * FROM t1
WHERE b = 1 AND c = 2 AND d = 3;
```




The hint specifies only one index, so it is inapplicable,
and the [`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch)
flag ( `off`) applies. Index Merge is not
used.


- The index-level optimizer hints
`GROUP_INDEX`, `INDEX`,
`JOIN_INDEX`, and
`ORDER_INDEX` all take precedence over
the equivalent `FORCE INDEX` hints; that
is, they cause the `FORCE INDEX` hints to
be ignored. Likewise, the
`NO_GROUP_INDEX`,
`NO_INDEX`,
`NO_JOIN_INDEX`, and
`NO_ORDER_INDEX` hints all take
precedence over any `IGNORE INDEX`
equivalents, also causing them to be ignored.



The index-level optimizer hints
`GROUP_INDEX`,
`NO_GROUP_INDEX`,
`INDEX`, `NO_INDEX`,
`JOIN_INDEX`, `NO_JOIN_INDEX`,
`ORDER_INDEX`, and
`NO_ORDER_INDEX` hints all take
precedence over all other optimizer hints, including other
index-level optimizer hints. Any other optimizer hints are
applied only to the indexes permitted by these.



The `GROUP_INDEX`,
`INDEX`, `JOIN_INDEX`,
and `ORDER_INDEX` hints are all
equivalent to `FORCE INDEX` and not to
`USE INDEX`. This is because using one or
more of these hints means that a table scan is used only
if there is no way to use one of the named indexes to find
rows in the table. To cause MySQL to use the same index or
set of indexes as with a given instance of `USE
                INDEX`, you can use `NO_INDEX`,
`NO_JOIN_INDEX`,
`NO_GROUP_INDEX`,
`NO_ORDER_INDEX`, or some combination of
these.



To replicate the effect that `USE INDEX`
has in the query `SELECT a,c FROM t1 USE INDEX FOR
                ORDER BY (i_a) ORDER BY a`, you can use the
`NO_ORDER_INDEX` optimizer hint to cover
all indexes on the table except the one that is desired
like this:




``` sql

SELECT /*+ NO_ORDER_INDEX(t1 i_b,i_c) */ a,c
      FROM t1
      ORDER BY a;
```




Attempting to combine `NO_ORDER_INDEX`
for the table as a whole with `USE INDEX FOR ORDER
                BY` does not work to do this, because
`NO_ORDER_BY` causes `USE
                INDEX` to be ignored, as shown here:




``` sql

mysql> EXPLAIN SELECT /*+ NO_ORDER_INDEX(t1) */ a,c FROM t1
      ->     USE INDEX FOR ORDER BY (i_a) ORDER BY a\G
*************************** 1. row ***************************
             id: 1
    select_type: SIMPLE
          table: t1
     partitions: NULL
           type: ALL
possible_keys: NULL
            key: NULL
        key_len: NULL
            ref: NULL
           rows: 256
       filtered: 100.00
          Extra: Using filesort
```

- The `USE INDEX`, `FORCE
                INDEX`, and `IGNORE INDEX` index
hints have higher priority than the
[`INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") and
[`NO_INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") optimizer
hints.




``` sql

/*+ INDEX_MERGE(t1 i_a, i_b, i_c) */ ... IGNORE INDEX i_a
```



`IGNORE INDEX` takes precedence over
[`INDEX_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints"), so index
`i_a` is excluded from the possible
ranges for Index Merge.




``` sql

/*+ NO_INDEX_MERGE(t1 i_a, i_b) */ ... FORCE INDEX i_a, i_b
```




Index Merge is disallowed for `i_a, i_b`
because of `FORCE INDEX`, but the
optimizer is forced to use either `i_a`
or `i_b` for
[`range`](https://dev.mysql.com/doc/refman/8.0/en/explain-output.html#jointype_range) or
[`ref`](https://dev.mysql.com/doc/refman/8.0/en/explain-output.html#jointype_ref) access. There are
no conflicts; both hints are applicable.


- If an `IGNORE INDEX` hint names multiple
indexes, those indexes are unavailable for Index Merge.


- The `FORCE INDEX` and `USE
                INDEX` hints make only the named indexes to be
available for Index Merge.




``` sql

SELECT /*+ INDEX_MERGE(t1 i_a, i_b, i_c) */ a FROM t1
FORCE INDEX (i_a, i_b) WHERE c = 'h' AND a = 2 AND b = 'b';
```




The Index Merge intersection access algorithm is used for
`(i_a, i_b)`. The same is true if
`FORCE INDEX` is changed to `USE
                INDEX`.


#### Subquery Optimizer Hints

Subquery hints affect whether to use semijoin transformations
and which semijoin strategies to permit, and, when semijoins
are not used, whether to use subquery materialization or
`IN`-to- `EXISTS`
transformations. For more information about these
optimizations, see [Section 10.2.2, “Optimizing Subqueries, Derived Tables, View References, and Common Table\\
Expressions”](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization.html "10.2.2 Optimizing Subqueries, Derived Tables, View References, and Common Table Expressions").


Syntax of hints that affect semijoin strategies:


``` sql

hint_name([@query_block_name] [strategy [, strategy] ...])
```

The syntax refers to these terms:

- _`hint_name`_: These hint names are
permitted:




- [`SEMIJOIN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints"),
[`NO_SEMIJOIN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints"): Enable
or disable the named semijoin strategies.


- _`strategy`_: A semijoin strategy
to be enabled or disabled. These strategy names are
permitted: `DUPSWEEDOUT`,
`FIRSTMATCH`,
`LOOSESCAN`,
`MATERIALIZATION`.



For [`SEMIJOIN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints") hints, if
no strategies are named, semijoin is used if possible
based on the strategies enabled according to the
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) system
variable. If strategies are named but inapplicable for the
statement, `DUPSWEEDOUT` is used.



For [`NO_SEMIJOIN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints") hints,
if no strategies are named, semijoin is not used. If
strategies are named that rule out all applicable
strategies for the statement,
`DUPSWEEDOUT` is used.


If one subquery is nested within another and both are merged
into a semijoin of an outer query, any specification of
semijoin strategies for the innermost query are ignored.
[`SEMIJOIN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints") and
[`NO_SEMIJOIN`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints") hints can still
be used to enable or disable semijoin transformations for such
nested subqueries.


If `DUPSWEEDOUT` is disabled, on occasion the
optimizer may generate a query plan that is far from optimal.
This occurs due to heuristic pruning during greedy search,
which can be avoided by setting
[`optimizer_prune_level=0`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_prune_level).


Examples:


``` sql

SELECT /*+ NO_SEMIJOIN(@subq1 FIRSTMATCH, LOOSESCAN) */ * FROM t2
  WHERE t2.a IN (SELECT /*+ QB_NAME(subq1) */ a FROM t3);
SELECT /*+ SEMIJOIN(@subq1 MATERIALIZATION, DUPSWEEDOUT) */ * FROM t2
  WHERE t2.a IN (SELECT /*+ QB_NAME(subq1) */ a FROM t3);
```

Syntax of hints that affect whether to use subquery
materialization or
`IN`-to- `EXISTS`
transformations:


``` sql

SUBQUERY([@query_block_name] strategy)
```

The hint name is always
[`SUBQUERY`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints").


For [`SUBQUERY`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints") hints, these
_`strategy`_ values are permitted:
`INTOEXISTS`,
`MATERIALIZATION`.


Examples:


``` sql

SELECT id, a IN (SELECT /*+ SUBQUERY(MATERIALIZATION) */ a FROM t1) FROM t2;
SELECT * FROM t2 WHERE t2.a IN (SELECT /*+ SUBQUERY(INTOEXISTS) */ a FROM t1);
```

For semijoin and [`SUBQUERY`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-subquery "Subquery Optimizer Hints")
hints, a leading
`@query_block_name`
specifies the query block to which the hint applies. If the
hint includes no leading
`@query_block_name`,
the hint applies to the query block in which it occurs. To
assign a name to a query block, see
[Optimizer Hints for Naming Query Blocks](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-query-block-naming "Optimizer Hints for Naming Query Blocks").


If a hint comment contains multiple subquery hints, the first
is used. If there are other following hints of that type, they
produce a warning. Following hints of other types are silently
ignored.

#### Statement Execution Time Optimizer Hints

The [`MAX_EXECUTION_TIME`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-execution-time "Statement Execution Time Optimizer Hints") hint
is permitted only for [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statements. It places a limit _`N`_ (a
timeout value in milliseconds) on how long a statement is
permitted to execute before the server terminates it:


``` sql

MAX_EXECUTION_TIME(N)
```

Example with a timeout of 1 second (1000 milliseconds):


``` sql

SELECT /*+ MAX_EXECUTION_TIME(1000) */ * FROM t1 INNER JOIN t2 WHERE ...
```

The
[`MAX_EXECUTION_TIME(N)`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-execution-time "Statement Execution Time Optimizer Hints")
hint sets a statement execution timeout of
_`N`_ milliseconds. If this option is
absent or _`N`_ is 0, the statement
timeout established by the
[`max_execution_time`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_execution_time) system
variable applies.


The [`MAX_EXECUTION_TIME`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-execution-time "Statement Execution Time Optimizer Hints") hint
is applicable as follows:

- For statements with multiple `SELECT`
keywords, such as unions or statements with subqueries,
[`MAX_EXECUTION_TIME`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-execution-time "Statement Execution Time Optimizer Hints")
applies to the entire statement and must appear after the
first [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement").


- It applies to read-only
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements.
Statements that are not read only are those that invoke a
stored function that modifies data as a side effect.


- It does not apply to [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statements in stored programs and is ignored.


#### Variable-Setting Hint Syntax

The [`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax") hint sets the
session value of a system variable temporarily (for the
duration of a single statement). Examples:


``` sql

SELECT /*+ SET_VAR(sort_buffer_size = 16M) */ name FROM people ORDER BY name;
INSERT /*+ SET_VAR(foreign_key_checks=OFF) */ INTO t2 VALUES(2);
SELECT /*+ SET_VAR(optimizer_switch = 'mrr_cost_based=off') */ 1;
```

Syntax of the [`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax") hint:


``` sql

SET_VAR(var_name = value)
```

_`var_name`_ names a system variable
that has a session value (although not all such variables can
be named, as explained later).
_`value`_ is the value to assign to the
variable; the value must be a scalar.


[`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax") makes a temporary
variable change, as demonstrated by these statements:


``` sql

mysql> SELECT @@unique_checks;
+-----------------+
| @@unique_checks |
+-----------------+
|               1 |
+-----------------+
mysql> SELECT /*+ SET_VAR(unique_checks=OFF) */ @@unique_checks;
+-----------------+
| @@unique_checks |
+-----------------+
|               0 |
+-----------------+
mysql> SELECT @@unique_checks;
+-----------------+
| @@unique_checks |
+-----------------+
|               1 |
+-----------------+
```

With [`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax"), there is no
need to save and restore the variable value. This enables you
to replace multiple statements by a single statement. Consider
this sequence of statements:


``` sql

SET @saved_val = @@SESSION.var_name;
SET @@SESSION.var_name = value;
SELECT ...
SET @@SESSION.var_name = @saved_val;
```

The sequence can be replaced by this single statement:


``` sql

SELECT /*+ SET_VAR(var_name = value) ...
```

Standalone
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statements permit any of these syntaxes for naming session
variables:


``` sql

SET SESSION var_name = value;
SET @@SESSION.var_name = value;
SET @@.var_name = value;
```

Because the [`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax") hint
applies only to session variables, session scope is implicit,
and `SESSION`, `@@SESSION.`,
and `@@` are neither needed nor permitted.
Including explicit session-indicator syntax results in the
[`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax") hint being ignored
with a warning.


Not all session variables are permitted for use with
[`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax"). Individual system
variable descriptions indicate whether each variable is
hintable; see [Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables"). You
can also check a system variable at runtime by attempting to
use it with [`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax"). If the
variable is not hintable, a warning occurs:


``` sql

mysql> SELECT /*+ SET_VAR(collation_server = 'utf8mb4') */ 1;
+---+
| 1 |
+---+
| 1 |
+---+
1 row in set, 1 warning (0.00 sec)

mysql> SHOW WARNINGS\G
*************************** 1. row ***************************
  Level: Warning
   Code: 4537
Message: Variable 'collation_server' cannot be set using SET_VAR hint.
```

[`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax") syntax permits
setting only a single variable, but multiple hints can be
given to set multiple variables:


``` sql

SELECT /*+ SET_VAR(optimizer_switch = 'mrr_cost_based=off')
           SET_VAR(max_heap_table_size = 1G) */ 1;
```

If several hints with the same variable name appear in the
same statement, the first one is applied and the others are
ignored with a warning:


``` sql

SELECT /*+ SET_VAR(max_heap_table_size = 1G)
           SET_VAR(max_heap_table_size = 3G) */ 1;
```

In this case, the second hint is ignored with a warning that
it is conflicting.


A [`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax") hint is ignored
with a warning if no system variable has the specified name or
the variable value is incorrect:


``` sql

SELECT /*+ SET_VAR(max_size = 1G) */ 1;
SELECT /*+ SET_VAR(optimizer_switch = 'mrr_cost_based=yes') */ 1;
```

For the first statement, there is no
`max_size` variable. For the second
statement, [`mrr_cost_based`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_mrr-cost-based)
takes values of `on` or
`off`, so attempting to set it to
`yes` is incorrect. In each case, the hint is
ignored with a warning.


The [`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax") hint is
permitted only at the statement level. If used in a subquery,
the hint is ignored with a warning.


Replicas ignore [`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax")
hints in replicated statements to avoid the potential for
security issues.

#### Resource Group Hint Syntax

The [`RESOURCE_GROUP`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-resource-group "Resource Group Hint Syntax") optimizer
hint is used for resource group management (see
[Section 7.1.16, “Resource Groups”](https://dev.mysql.com/doc/refman/8.0/en/resource-groups.html "7.1.16 Resource Groups")). This hint assigns the
thread that executes a statement to the named resource group
temporarily (for the duration of the statement). It requires
the [`RESOURCE_GROUP_ADMIN`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_resource-group-admin) or
[`RESOURCE_GROUP_USER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_resource-group-user) privilege.


Examples:


``` sql

SELECT /*+ RESOURCE_GROUP(USR_default) */ name FROM people ORDER BY name;
INSERT /*+ RESOURCE_GROUP(Batch) */ INTO t2 VALUES(2);
```

Syntax of the [`RESOURCE_GROUP`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-resource-group "Resource Group Hint Syntax")
hint:


``` sql

RESOURCE_GROUP(group_name)
```

_`group_name`_ indicates the resource
group to which the thread should be assigned for the duration
of statement execution. If the group is nonexistent, a warning
occurs and the hint is ignored.


The [`RESOURCE_GROUP`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-resource-group "Resource Group Hint Syntax") hint must
appear after the initial statement keyword
( `SELECT`, `INSERT`,
`REPLACE`, `UPDATE`, or
`DELETE`).


An alternative to
[`RESOURCE_GROUP`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-resource-group "Resource Group Hint Syntax") is the
[`SET RESOURCE GROUP`](https://dev.mysql.com/doc/refman/8.0/en/set-resource-group.html "15.7.2.4 SET RESOURCE GROUP Statement") statement,
which nontemporarily assigns threads to a resource group. See
[Section 15.7.2.4, “SET RESOURCE GROUP Statement”](https://dev.mysql.com/doc/refman/8.0/en/set-resource-group.html "15.7.2.4 SET RESOURCE GROUP Statement").

#### Optimizer Hints for Naming Query Blocks

Table-level, index-level, and subquery optimizer hints permit
specific query blocks to be named as part of their argument
syntax. To create these names, use the
[`QB_NAME`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-query-block-naming "Optimizer Hints for Naming Query Blocks") hint, which assigns
a name to the query block in which it occurs:


``` sql

QB_NAME(name)
```

[`QB_NAME`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-query-block-naming "Optimizer Hints for Naming Query Blocks") hints can be used to
make explicit in a clear way which query blocks other hints
apply to. They also permit all non-query block name hints to
be specified within a single hint comment for easier
understanding of complex statements. Consider the following
statement:


``` sql

SELECT ...
  FROM (SELECT ...
  FROM (SELECT ... FROM ...)) ...
```

[`QB_NAME`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-query-block-naming "Optimizer Hints for Naming Query Blocks") hints assign names
to query blocks in the statement:


``` sql

SELECT /*+ QB_NAME(qb1) */ ...
  FROM (SELECT /*+ QB_NAME(qb2) */ ...
  FROM (SELECT /*+ QB_NAME(qb3) */ ... FROM ...)) ...
```

Then other hints can use those names to refer to the
appropriate query blocks:


``` sql

SELECT /*+ QB_NAME(qb1) MRR(@qb1 t1) BKA(@qb2) NO_MRR(@qb3t1 idx1, id2) */ ...
  FROM (SELECT /*+ QB_NAME(qb2) */ ...
  FROM (SELECT /*+ QB_NAME(qb3) */ ... FROM ...)) ...
```

The resulting effect is as follows:

- [`MRR(@qb1 t1)`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") applies to
table `t1` in query block
`qb1`.


- [`BKA(@qb2)`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") applies to
query block `qb2`.


- [`NO_MRR(@qb3 t1 idx1,\\
                id2)`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-index-level "Index-Level Optimizer Hints") applies to indexes `idx1`
and `idx2` in table `t1`
in query block `qb3`.


Query block names are identifiers and follow the usual rules
about what names are valid and how to quote them (see
[Section 11.2, “Schema Object Names”](https://dev.mysql.com/doc/refman/8.0/en/identifiers.html "11.2 Schema Object Names")). For example, a query block
name that contains spaces must be quoted, which can be done
using backticks:


``` sql

SELECT /*+ BKA(@`my hint name`) */ ...
  FROM (SELECT /*+ QB_NAME(`my hint name`) */ ...) ...
```

If the [`ANSI_QUOTES`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_ansi_quotes) SQL mode
is enabled, it is also possible to quote query block names
within double quotation marks:


``` sql

SELECT /*+ BKA(@"my hint name") */ ...
  FROM (SELECT /*+ QB_NAME("my hint name") */ ...) ...
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html "Previous: Switchable Optimizations") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html "Up: Controlling the Query Optimizer") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html "Next: Index Hints")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html)

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