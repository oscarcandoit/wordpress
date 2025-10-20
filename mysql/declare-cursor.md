---
url: https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html
scraped_at: 2025-10-20T03:08:29.571Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html "Hide Sidebar")

[Previous: Cursor CLOSE Statement](https://dev.mysql.com/doc/refman/8.0/en/close.html "Previous: Cursor CLOSE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Cursors](https://dev.mysql.com/doc/refman/8.0/en/cursors.html "Up: Cursors")[Next: Cursor FETCH Statement](https://dev.mysql.com/doc/refman/8.0/en/fetch.html "Next: Cursor FETCH Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/declare-cursor.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/declare-cursor.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/declare-cursor.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/declare-cursor.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/declare-cursor.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/declare-cursor.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/declare-cursor.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/declare-cursor.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Compound Statement Syntax](https://dev.mysql.com/doc/refman/8.0/en/sql-compound-statements.html)  /
[Cursors](https://dev.mysql.com/doc/refman/8.0/en/cursors.html)  /

Cursor DECLARE Statement


#### 15.6.6.2 Cursor DECLARE Statement

```sql
DECLARE cursor_name CURSOR FOR select_statement
```

This statement declares a cursor and associates it with a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement that retrieves
the rows to be traversed by the cursor. To fetch the rows later,
use a [`FETCH`](https://dev.mysql.com/doc/refman/8.0/en/fetch.html "15.6.6.3 Cursor FETCH Statement") statement. The number
of columns retrieved by the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement must match the
number of output variables specified in the
[`FETCH`](https://dev.mysql.com/doc/refman/8.0/en/fetch.html "15.6.6.3 Cursor FETCH Statement") statement.


The [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement cannot have
an `INTO` clause.


Cursor declarations must appear before handler declarations and
after variable and condition declarations.


A stored program may contain multiple cursor declarations, but
each cursor declared in a given block must have a unique name.
For an example, see [Section 15.6.6, “Cursors”](https://dev.mysql.com/doc/refman/8.0/en/cursors.html "15.6.6 Cursors").


For information available through
[`SHOW`](https://dev.mysql.com/doc/refman/8.0/en/show.html "15.7.7 SHOW Statements") statements, it is possible
in many cases to obtain equivalent information by using a cursor
with an `INFORMATION_SCHEMA` table.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/close.html "Previous: Cursor CLOSE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/cursors.html "Up: Cursors") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/fetch.html "Next: Cursor FETCH Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/declare-cursor.html)

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