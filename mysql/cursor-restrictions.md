---
url: https://dev.mysql.com/doc/refman/8.0/en/cursor-restrictions.html
scraped_at: 2025-10-20T03:08:51.314Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/cursor-restrictions.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/cursor-restrictions.html "Hide Sidebar")

[Previous: Cursor OPEN Statement](https://dev.mysql.com/doc/refman/8.0/en/open.html "Previous: Cursor OPEN Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Cursors](https://dev.mysql.com/doc/refman/8.0/en/cursors.html "Up: Cursors")[Next: Condition Handling](https://dev.mysql.com/doc/refman/8.0/en/condition-handling.html "Next: Condition Handling")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/cursor-restrictions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/cursor-restrictions.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/cursor-restrictions.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/cursor-restrictions.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/cursor-restrictions.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/cursor-restrictions.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/cursor-restrictions.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/cursor-restrictions.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/cursor-restrictions.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/cursor-restrictions.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/cursor-restrictions.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/cursor-restrictions.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/cursor-restrictions.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/cursor-restrictions.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Compound Statement Syntax](https://dev.mysql.com/doc/refman/8.0/en/sql-compound-statements.html)  /
[Cursors](https://dev.mysql.com/doc/refman/8.0/en/cursors.html)  /

Restrictions on Server-Side Cursors


#### 15.6.6.5 Restrictions on Server-Side Cursors

Server-side cursors are implemented in the C API using the
[`mysql_stmt_attr_set()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-stmt-attr-set.html) function.
The same implementation is used for cursors in stored routines.
A server-side cursor enables a result set to be generated on the
server side, but not transferred to the client except for those
rows that the client requests. For example, if a client executes
a query but is only interested in the first row, the remaining
rows are not transferred.


In MySQL, a server-side cursor is materialized into an internal
temporary table. Initially, this is a `MEMORY`
table, but is converted to a `MyISAM` table
when its size exceeds the minimum value of the
[`max_heap_table_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_heap_table_size) and
[`tmp_table_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_tmp_table_size) system
variables. The same restrictions apply to internal temporary
tables created to hold the result set for a cursor as for other
uses of internal temporary tables. See
[Section 10.4.4, “Internal Temporary Table Use in MySQL”](https://dev.mysql.com/doc/refman/8.0/en/internal-temporary-tables.html "10.4.4 Internal Temporary Table Use in MySQL"). One limitation of
the implementation is that for a large result set, retrieving
its rows through a cursor might be slow.


Cursors are read only; you cannot use a cursor to update rows.


`UPDATE WHERE CURRENT OF` and `DELETE
        WHERE CURRENT OF` are not implemented, because
updatable cursors are not supported.


Cursors are nonholdable (not held open after a commit).


Cursors are asensitive.


Cursors are nonscrollable.


Cursors are not named. The statement handler acts as the cursor
ID.


You can have open only a single cursor per prepared statement.
If you need several cursors, you must prepare several
statements.


You cannot use a cursor for a statement that generates a result
set if the statement is not supported in prepared mode. This
includes statements such as [`CHECK\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement"), `HANDLER READ`, and
[`SHOW BINLOG EVENTS`](https://dev.mysql.com/doc/refman/8.0/en/show-binlog-events.html "15.7.7.2 SHOW BINLOG EVENTS Statement").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/open.html "Previous: Cursor OPEN Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/cursors.html "Up: Cursors") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/condition-handling.html "Next: Condition Handling")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/cursor-restrictions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/cursor-restrictions.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/cursor-restrictions.html)

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