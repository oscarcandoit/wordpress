---
url: https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html
scraped_at: 2025-10-20T03:13:53.901Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html "Hide Sidebar")

[Previous: Controlling the Query Optimizer](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html "Previous: Controlling the Query Optimizer")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Controlling the Query Optimizer](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html "Up: Controlling the Query Optimizer")[Next: Switchable Optimizations](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html "Next: Switchable Optimizations")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/controlling-query-plan-evaluation.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/controlling-query-plan-evaluation.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/controlling-query-plan-evaluation.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/controlling-query-plan-evaluation.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/controlling-query-plan-evaluation.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/controlling-query-plan-evaluation.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/controlling-query-plan-evaluation.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/controlling-query-plan-evaluation.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Controlling the Query Optimizer](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html)  /

Controlling Query Plan Evaluation


### 10.9.1 Controlling Query Plan Evaluation

The task of the query optimizer is to find an optimal plan for
executing an SQL query. Because the difference in performance
between “good” and “bad” plans can be
orders of magnitude (that is, seconds versus hours or even
days), most query optimizers, including that of MySQL, perform a
more or less exhaustive search for an optimal plan among all
possible query evaluation plans. For join queries, the number of
possible plans investigated by the MySQL optimizer grows
exponentially with the number of tables referenced in a query.
For small numbers of tables (typically less than 7 to 10) this
is not a problem. However, when larger queries are submitted,
the time spent in query optimization may easily become the major
bottleneck in the server's performance.


A more flexible method for query optimization enables the user
to control how exhaustive the optimizer is in its search for an
optimal query evaluation plan. The general idea is that the
fewer plans that are investigated by the optimizer, the less
time it spends in compiling a query. On the other hand, because
the optimizer skips some plans, it may miss finding an optimal
plan.


The behavior of the optimizer with respect to the number of
plans it evaluates can be controlled using two system variables:

- The [`optimizer_prune_level`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_prune_level)
variable tells the optimizer to skip certain plans based on
estimates of the number of rows accessed for each table. Our
experience shows that this kind of “educated
guess” rarely misses optimal plans, and may
dramatically reduce query compilation times. That is why
this option is on
( `optimizer_prune_level=1`) by default.
However, if you believe that the optimizer missed a better
query plan, this option can be switched off
( `optimizer_prune_level=0`) with the risk
that query compilation may take much longer. Note that, even
with the use of this heuristic, the optimizer still explores
a roughly exponential number of plans.


- The [`optimizer_search_depth`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_search_depth)
variable tells how far into the “future” of
each incomplete plan the optimizer should look to evaluate
whether it should be expanded further. Smaller values of
[`optimizer_search_depth`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_search_depth) may
result in orders of magnitude smaller query compilation
times. For example, queries with 12, 13, or more tables may
easily require hours and even days to compile if
[`optimizer_search_depth`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_search_depth) is
close to the number of tables in the query. At the same
time, if compiled with
[`optimizer_search_depth`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_search_depth)
equal to 3 or 4, the optimizer may compile in less than a
minute for the same query. If you are unsure of what a
reasonable value is for
[`optimizer_search_depth`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_search_depth),
this variable can be set to 0 to tell the optimizer to
determine the value automatically.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html "Previous: Controlling the Query Optimizer") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html "Up: Controlling the Query Optimizer") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html "Next: Switchable Optimizations")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html)

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