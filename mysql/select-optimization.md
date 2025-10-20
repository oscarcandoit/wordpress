---
url: https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html
scraped_at: 2025-10-20T03:04:02.228Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html "Hide Sidebar")

[Previous: Optimizing SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html "Previous: Optimizing SQL Statements")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimizing SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html "Up: Optimizing SQL Statements")[Next: WHERE Clause Optimization](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html "Next: WHERE Clause Optimization")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/select-optimization.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/select-optimization.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/select-optimization.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/select-optimization.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/select-optimization.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/select-optimization.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/select-optimization.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/select-optimization.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimizing SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)  /

Optimizing SELECT Statements


### 10.2.1 Optimizing SELECT Statements

[10.2.1.1 WHERE Clause Optimization](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html)[10.2.1.2 Range Optimization](https://dev.mysql.com/doc/refman/8.0/en/range-optimization.html)[10.2.1.3 Index Merge Optimization](https://dev.mysql.com/doc/refman/8.0/en/index-merge-optimization.html)[10.2.1.4 Hash Join Optimization](https://dev.mysql.com/doc/refman/8.0/en/hash-joins.html)[10.2.1.5 Engine Condition Pushdown Optimization](https://dev.mysql.com/doc/refman/8.0/en/engine-condition-pushdown-optimization.html)[10.2.1.6 Index Condition Pushdown Optimization](https://dev.mysql.com/doc/refman/8.0/en/index-condition-pushdown-optimization.html)[10.2.1.7 Nested-Loop Join Algorithms](https://dev.mysql.com/doc/refman/8.0/en/nested-loop-joins.html)[10.2.1.8 Nested Join Optimization](https://dev.mysql.com/doc/refman/8.0/en/nested-join-optimization.html)[10.2.1.9 Outer Join Optimization](https://dev.mysql.com/doc/refman/8.0/en/outer-join-optimization.html)[10.2.1.10 Outer Join Simplification](https://dev.mysql.com/doc/refman/8.0/en/outer-join-simplification.html)[10.2.1.11 Multi-Range Read Optimization](https://dev.mysql.com/doc/refman/8.0/en/mrr-optimization.html)[10.2.1.12 Block Nested-Loop and Batched Key Access Joins](https://dev.mysql.com/doc/refman/8.0/en/bnl-bka-optimization.html)[10.2.1.13 Condition Filtering](https://dev.mysql.com/doc/refman/8.0/en/condition-filtering.html)[10.2.1.14 Constant-Folding Optimization](https://dev.mysql.com/doc/refman/8.0/en/constant-folding-optimization.html)[10.2.1.15 IS NULL Optimization](https://dev.mysql.com/doc/refman/8.0/en/is-null-optimization.html)[10.2.1.16 ORDER BY Optimization](https://dev.mysql.com/doc/refman/8.0/en/order-by-optimization.html)[10.2.1.17 GROUP BY Optimization](https://dev.mysql.com/doc/refman/8.0/en/group-by-optimization.html)[10.2.1.18 DISTINCT Optimization](https://dev.mysql.com/doc/refman/8.0/en/distinct-optimization.html)[10.2.1.19 LIMIT Query Optimization](https://dev.mysql.com/doc/refman/8.0/en/limit-optimization.html)[10.2.1.20 Function Call Optimization](https://dev.mysql.com/doc/refman/8.0/en/function-optimization.html)[10.2.1.21 Window Function Optimization](https://dev.mysql.com/doc/refman/8.0/en/window-function-optimization.html)[10.2.1.22 Row Constructor Expression Optimization](https://dev.mysql.com/doc/refman/8.0/en/row-constructor-optimization.html)[10.2.1.23 Avoiding Full Table Scans](https://dev.mysql.com/doc/refman/8.0/en/table-scan-avoidance.html)

Queries, in the form of [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statements, perform all the lookup operations in the database.
Tuning these statements is a top priority, whether to achieve
sub-second response times for dynamic web pages, or to chop
hours off the time to generate huge overnight reports.


Besides [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements, the
tuning techniques for queries also apply to constructs such as
[`CREATE\\
        TABLE...AS SELECT`](https://dev.mysql.com/doc/refman/8.0/en/create-table-select.html "15.1.20.4 CREATE TABLE ... SELECT Statement"),
[`INSERT\\
        INTO...SELECT`](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement"), and `WHERE` clauses in
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statements. Those
statements have additional performance considerations because
they combine write operations with the read-oriented query
operations.


NDB Cluster supports a join pushdown optimization whereby a
qualifying join is sent in its entirety to NDB Cluster data
nodes, where it can be distributed among them and executed in
parallel. For more information about this optimization, see
[Conditions for NDB pushdown joins](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster-options-variables.html#ndb_join_pushdown-conditions "Conditions for NDB pushdown joins").


The main considerations for optimizing queries are:

- To make a slow `SELECT ... WHERE` query
faster, the first thing to check is whether you can add an
[index](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_index "index"). Set up indexes on
columns used in the `WHERE` clause, to
speed up evaluation, filtering, and the final retrieval of
results. To avoid wasted disk space, construct a small set
of indexes that speed up many related queries used in your
application.



Indexes are especially important for queries that reference
different tables, using features such as
[joins](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_join "join") and
[foreign keys](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_foreign_key "foreign key"). You
can use the [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") statement
to determine which indexes are used for a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"). See
[Section 10.3.1, “How MySQL Uses Indexes”](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html "10.3.1 How MySQL Uses Indexes") and
[Section 10.8.1, “Optimizing Queries with EXPLAIN”](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html "10.8.1 Optimizing Queries with EXPLAIN").


- Isolate and tune any part of the query, such as a function
call, that takes excessive time. Depending on how the query
is structured, a function could be called once for every row
in the result set, or even once for every row in the table,
greatly magnifying any inefficiency.


- Minimize the number of
[full table scans](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_full_table_scan "full table scan")
in your queries, particularly for big tables.


- Keep table statistics up to date by using the
[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") statement
periodically, so the optimizer has the information needed to
construct an efficient execution plan.


- Learn the tuning techniques, indexing techniques, and
configuration parameters that are specific to the storage
engine for each table. Both `InnoDB` and
`MyISAM` have sets of guidelines for
enabling and sustaining high performance in queries. For
details, see [Section 10.5.6, “Optimizing InnoDB Queries”](https://dev.mysql.com/doc/refman/8.0/en/optimizing-innodb-queries.html "10.5.6 Optimizing InnoDB Queries") and
[Section 10.6.1, “Optimizing MyISAM Queries”](https://dev.mysql.com/doc/refman/8.0/en/optimizing-queries-myisam.html "10.6.1 Optimizing MyISAM Queries").


- You can optimize single-query transactions for
`InnoDB` tables, using the technique in
[Section 10.5.3, “Optimizing InnoDB Read-Only Transactions”](https://dev.mysql.com/doc/refman/8.0/en/innodb-performance-ro-txn.html "10.5.3 Optimizing InnoDB Read-Only Transactions").


- Avoid transforming the query in ways that make it hard to
understand, especially if the optimizer does some of the
same transformations automatically.


- If a performance issue is not easily solved by one of the
basic guidelines, investigate the internal details of the
specific query by reading the
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") plan and adjusting
your indexes, `WHERE` clauses, join
clauses, and so on. (When you reach a certain level of
expertise, reading the
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") plan might be your
first step for every query.)


- Adjust the size and properties of the memory areas that
MySQL uses for caching. With efficient use of the
`InnoDB` [buffer pool](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_buffer_pool "buffer pool"),
`MyISAM` key cache, and the MySQL query
cache, repeated queries run faster because the results are
retrieved from memory the second and subsequent times.


- Even for a query that runs fast using the cache memory
areas, you might still optimize further so that they require
less cache memory, making your application more scalable.
Scalability means that your application can handle more
simultaneous users, larger requests, and so on without
experiencing a big drop in performance.


- Deal with locking issues, where the speed of your query
might be affected by other sessions accessing the tables at
the same time.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html "Previous: Optimizing SQL Statements") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html "Up: Optimizing SQL Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/where-optimization.html "Next: WHERE Clause Optimization")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html)

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