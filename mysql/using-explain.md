---
url: https://dev.mysql.com/doc/refman/8.0/en/using-explain.html
scraped_at: 2025-10-20T03:04:21.778Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html "Hide Sidebar")

[Previous: Understanding the Query Execution Plan](https://dev.mysql.com/doc/refman/8.0/en/execution-plan-information.html "Previous: Understanding the Query Execution Plan")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Understanding the Query Execution Plan](https://dev.mysql.com/doc/refman/8.0/en/execution-plan-information.html "Up: Understanding the Query Execution Plan")[Next: EXPLAIN Output Format](https://dev.mysql.com/doc/refman/8.0/en/explain-output.html "Next: EXPLAIN Output Format")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/using-explain.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/using-explain.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/using-explain.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/using-explain.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/using-explain.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/using-explain.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/using-explain.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/using-explain.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Understanding the Query Execution Plan](https://dev.mysql.com/doc/refman/8.0/en/execution-plan-information.html)  /

Optimizing Queries with EXPLAIN


### 10.8.1 Optimizing Queries with EXPLAIN

The [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") statement provides
information about how MySQL executes statements:

- [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") works with
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"),
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"),
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"),
[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement"), and
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statements.


- When [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") is used with an
explainable statement, MySQL displays information from the
optimizer about the statement execution plan. That is, MySQL
explains how it would process the statement, including
information about how tables are joined and in which order.
For information about using
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") to obtain execution
plan information, see [Section 10.8.2, “EXPLAIN Output Format”](https://dev.mysql.com/doc/refman/8.0/en/explain-output.html "10.8.2 EXPLAIN Output Format").


- When [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") is used with
`FOR CONNECTION
              connection_id` rather
than an explainable statement, it displays the execution
plan for the statement executing in the named connection.
See [Section 10.8.4, “Obtaining Execution Plan Information for a Named Connection”](https://dev.mysql.com/doc/refman/8.0/en/explain-for-connection.html "10.8.4 Obtaining Execution Plan Information for a Named Connection").


- For [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements,
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") produces additional
execution plan information that can be displayed using
[`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement"). See
[Section 10.8.3, “Extended EXPLAIN Output Format”](https://dev.mysql.com/doc/refman/8.0/en/explain-extended.html "10.8.3 Extended EXPLAIN Output Format").


- [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") is useful for
examining queries involving partitioned tables. See
[Section 26.3.5, “Obtaining Information About Partitions”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-info.html "26.3.5 Obtaining Information About Partitions").


- The `FORMAT` option can be used to select
the output format. `TRADITIONAL` presents
the output in tabular format. This is the default if no
`FORMAT` option is present.
`JSON` format displays the information in
JSON format.


With the help of [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement"), you can
see where you should add indexes to tables so that the statement
executes faster by using indexes to find rows. You can also use
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") to check whether the
optimizer joins the tables in an optimal order. To give a hint
to the optimizer to use a join order corresponding to the order
in which the tables are named in a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement, begin the
statement with `SELECT STRAIGHT_JOIN` rather
than just [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"). (See
[Section 15.2.13, “SELECT Statement”](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement").) However,
`STRAIGHT_JOIN` may prevent indexes from being
used because it disables semijoin transformations. See
[Section 10.2.2.1, “Optimizing IN and EXISTS Subquery Predicates with Semijoin\\
Transformations”](https://dev.mysql.com/doc/refman/8.0/en/semijoins.html "10.2.2.1 Optimizing IN and EXISTS Subquery Predicates with Semijoin Transformations").


The optimizer trace may sometimes provide information
complementary to that of [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement").
However, the optimizer trace format and content are subject to
change between versions. For details, see
[Section 10.15, “Tracing the Optimizer”](https://dev.mysql.com/doc/refman/8.0/en/optimizer-tracing.html "10.15 Tracing the Optimizer").


If you have a problem with indexes not being used when you
believe that they should be, run [`ANALYZE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") to update table statistics, such as cardinality
of keys, that can affect the choices the optimizer makes. See
[Section 15.7.3.1, “ANALYZE TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement").

Note

[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") can also be used to
obtain information about the columns in a table.
[`EXPLAIN\\
          tbl_name`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") is synonymous
with `DESCRIBE
          tbl_name` and
`SHOW COLUMNS FROM
          tbl_name`. For more
information, see [Section 15.8.1, “DESCRIBE Statement”](https://dev.mysql.com/doc/refman/8.0/en/describe.html "15.8.1 DESCRIBE Statement"), and
[Section 15.7.7.5, “SHOW COLUMNS Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "15.7.7.5 SHOW COLUMNS Statement").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/execution-plan-information.html "Previous: Understanding the Query Execution Plan") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/execution-plan-information.html "Up: Understanding the Query Execution Plan") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/explain-output.html "Next: EXPLAIN Output Format")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html)

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