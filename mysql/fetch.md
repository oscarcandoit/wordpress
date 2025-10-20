---
url: https://dev.mysql.com/doc/refman/8.0/en/fetch.html
scraped_at: 2025-10-20T03:08:42.077Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/fetch.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/fetch.html "Hide Sidebar")

[Previous: Cursor DECLARE Statement](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html "Previous: Cursor DECLARE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Cursors](https://dev.mysql.com/doc/refman/8.0/en/cursors.html "Up: Cursors")[Next: Cursor OPEN Statement](https://dev.mysql.com/doc/refman/8.0/en/open.html "Next: Cursor OPEN Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/fetch.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/fetch.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/fetch.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/fetch.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/fetch.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/fetch.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/fetch.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/fetch.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/fetch.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/fetch.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/fetch.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/fetch.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/fetch.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/fetch.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Compound Statement Syntax](https://dev.mysql.com/doc/refman/8.0/en/sql-compound-statements.html)  /
[Cursors](https://dev.mysql.com/doc/refman/8.0/en/cursors.html)  /

Cursor FETCH Statement


#### 15.6.6.3 Cursor FETCH Statement

``` sql

FETCH [[NEXT] FROM] cursor_name INTO var_name [, var_name] ...
```

This statement fetches the next row for the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement associated with
the specified cursor (which must be open), and advances the
cursor pointer. If a row exists, the fetched columns are stored
in the named variables. The number of columns retrieved by the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement must match the
number of output variables specified in the
[`FETCH`](https://dev.mysql.com/doc/refman/8.0/en/fetch.html "15.6.6.3 Cursor FETCH Statement") statement.


If no more rows are available, a No Data condition occurs with
SQLSTATE value `'02000'`. To detect this
condition, you can set up a handler for it (or for a
`NOT FOUND` condition). For an example, see
[Section 15.6.6, “Cursors”](https://dev.mysql.com/doc/refman/8.0/en/cursors.html "15.6.6 Cursors").


Be aware that another operation, such as a
`SELECT` or another `FETCH`,
may also cause the handler to execute by raising the same
condition. If it is necessary to distinguish which operation
raised the condition, place the operation within its own
[`BEGIN ...\\
        END`](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement") block so that it can be associated with its own
handler.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html "Previous: Cursor DECLARE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/cursors.html "Up: Cursors") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/open.html "Next: Cursor OPEN Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/fetch.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/fetch.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/fetch.html)

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