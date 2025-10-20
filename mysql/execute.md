---
url: https://dev.mysql.com/doc/refman/8.0/en/execute.html
scraped_at: 2025-10-20T03:09:48.825Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/execute.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/execute.html "Hide Sidebar")

[Previous: PREPARE Statement](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "Previous: PREPARE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Prepared Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html "Up: Prepared Statements")[Next: DEALLOCATE PREPARE Statement](https://dev.mysql.com/doc/refman/8.0/en/deallocate-prepare.html "Next: DEALLOCATE PREPARE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/execute.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/execute.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/execute.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/execute.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/execute.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/execute.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/execute.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/execute.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/execute.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/execute.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/execute.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/execute.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/execute.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/execute.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Prepared Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html)  /

EXECUTE Statement


### 15.5.2 EXECUTE Statement

```sql
EXECUTE stmt_name
    [USING @var_name [, @var_name] ...]
```

After preparing a statement with
[`PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "15.5.1 PREPARE Statement"), you execute it with an
[`EXECUTE`](https://dev.mysql.com/doc/refman/8.0/en/execute.html "15.5.2 EXECUTE Statement") statement that refers to
the prepared statement name. If the prepared statement contains
any parameter markers, you must supply a `USING`
clause that lists user variables containing the values to be bound
to the parameters. Parameter values can be supplied only by user
variables, and the `USING` clause must name
exactly as many variables as the number of parameter markers in
the statement.


You can execute a given prepared statement multiple times, passing
different variables to it or setting the variables to different
values before each execution.


For examples, see [Section 15.5, “Prepared Statements”](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html "15.5 Prepared Statements").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "Previous: PREPARE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html "Up: Prepared Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/deallocate-prepare.html "Next: DEALLOCATE PREPARE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/execute.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/execute.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/execute.html)

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