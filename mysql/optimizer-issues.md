---
url: https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html
scraped_at: 2025-10-20T03:11:58.743Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html "Hide Sidebar")

[Previous: Problems with Floating-Point Values](https://dev.mysql.com/doc/refman/8.0/en/problems-with-float.html "Previous: Problems with Floating-Point Values")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Problems and Common Errors](https://dev.mysql.com/doc/refman/8.0/en/problems.html "Up: Problems and Common Errors")[Next: Table Definition-Related Issues](https://dev.mysql.com/doc/refman/8.0/en/table-definition-issues.html "Next: Table Definition-Related Issues")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/optimizer-issues.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/optimizer-issues.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/optimizer-issues.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/optimizer-issues.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/optimizer-issues.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/optimizer-issues.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/optimizer-issues.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/optimizer-issues.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html)  / [Error Messages and Common Problems](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html)  /
[Problems and Common Errors](https://dev.mysql.com/doc/refman/8.0/en/problems.html)  /

Optimizer-Related Issues


### B.3.5 Optimizer-Related Issues

MySQL uses a cost-based optimizer to determine the best way to
resolve a query. In many cases, MySQL can calculate the best
possible query plan, but sometimes MySQL does not have enough
information about the data at hand and has to make
“educated” guesses about the data.


For the cases when MySQL does not do the "right" thing, tools
that you have available to help MySQL are:

- Use the [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") statement to
get information about how MySQL processes a query. To use
it, just add the keyword
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") to the front of your
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement:



```sql
mysql> EXPLAIN SELECT * FROM t1, t2 WHERE t1.i = t2.i;
```


[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") is discussed in more
detail in [Section 15.8.2, “EXPLAIN Statement”](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement").


- Use `ANALYZE TABLE
              tbl_name` to update the
key distributions for the scanned table. See
[Section 15.7.3.1, “ANALYZE TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement").


- Use `FORCE INDEX` for the scanned table to
tell MySQL that table scans are very expensive compared to
using the given index:



```sql
SELECT * FROM t1, t2 FORCE INDEX (index_for_column)
WHERE t1.col_name=t2.col_name;
```


`USE INDEX` and `IGNORE
              INDEX` may also be useful. See
[Section 10.9.4, “Index Hints”](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html "10.9.4 Index Hints").


- Global and table-level `STRAIGHT_JOIN`. See
[Section 15.2.13, “SELECT Statement”](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement").


- You can tune global or thread-specific system variables. For
example, start [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server") with the
[`--max-seeks-for-key=1000`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_seeks_for_key)
option or use `SET max_seeks_for_key=1000`
to tell the optimizer to assume that no key scan causes more
than 1,000 key seeks. See
[Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables").


[PREV](https://dev.mysql.com/doc/refman/8.0/en/problems-with-float.html "Previous: Problems with Floating-Point Values") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/problems.html "Up: Problems and Common Errors") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/table-definition-issues.html "Next: Table Definition-Related Issues")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html)

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