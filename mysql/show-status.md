---
url: https://dev.mysql.com/doc/refman/8.0/en/show-status.html
scraped_at: 2025-10-20T03:07:03.478Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/show-status.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-status.html "Hide Sidebar")

[Previous: SHOW SLAVE | REPLICA STATUS Statement](https://dev.mysql.com/doc/refman/8.0/en/show-slave-status.html "Previous: SHOW SLAVE | REPLICA STATUS Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements")[Next: SHOW TABLE STATUS Statement](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "Next: SHOW TABLE STATUS Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-status.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-status.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-status.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/show-status.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/show-status.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/show-status.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/show-status.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/show-status.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/show-status.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/show-status.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/show-status.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/show-status.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-status.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/show-status.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)  /

SHOW STATUS Statement


#### 15.7.7.37 SHOW STATUS Statement

```sql

SHOW [GLOBAL | SESSION] STATUS
    [LIKE 'pattern' | WHERE expr]
```

[`SHOW STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-status.html "15.7.7.37 SHOW STATUS Statement") provides server
status information (see
[Section 7.1.10, “Server Status Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-status-variables.html "7.1.10 Server Status Variables")). This statement does
not require any privilege. It requires only the ability to
connect to the server.


Status variable information is also available from these
sources:

- Performance Schema tables. See
[Section 29.12.15, “Performance Schema Status Variable Tables”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-status-variable-tables.html "29.12.15 Performance Schema Status Variable Tables").


- The [**mysqladmin extended-status**](https://dev.mysql.com/doc/refman/8.0/en/mysqladmin.html "6.5.2 mysqladmin — A MySQL Server Administration Program") command.
See [Section 6.5.2, “mysqladmin — A MySQL Server Administration Program”](https://dev.mysql.com/doc/refman/8.0/en/mysqladmin.html "6.5.2 mysqladmin — A MySQL Server Administration Program").


For [`SHOW STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-status.html "15.7.7.37 SHOW STATUS Statement"), a
[`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) clause, if present, indicates
which variable names to match. A `WHERE` clause
can be given to select rows using more general conditions, as
discussed in [Section 28.8, “Extensions to SHOW Statements”](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html "28.8 Extensions to SHOW Statements").


[`SHOW STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-status.html "15.7.7.37 SHOW STATUS Statement") accepts an optional
`GLOBAL` or `SESSION` variable
scope modifier:

- With a `GLOBAL` modifier, the statement
displays the global status values. A global status variable
may represent status for some aspect of the server itself
(for example, `Aborted_connects`), or the
aggregated status over all connections to MySQL (for
example, `Bytes_received` and
`Bytes_sent`). If a variable has no global
value, the session value is displayed.


- With a `SESSION` modifier, the statement
displays the status variable values for the current
connection. If a variable has no session value, the global
value is displayed. `LOCAL` is a synonym
for `SESSION`.


- If no modifier is present, the default is
`SESSION`.


The scope for each status variable is listed at
[Section 7.1.10, “Server Status Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-status-variables.html "7.1.10 Server Status Variables").


Each invocation of the [`SHOW\\
        STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-status.html "15.7.7.37 SHOW STATUS Statement") statement uses an internal temporary table and
increments the global
[`Created_tmp_tables`](https://dev.mysql.com/doc/refman/8.0/en/server-status-variables.html#statvar_Created_tmp_tables) value.


Partial output is shown here. The list of names and values may
differ for your server. The meaning of each variable is given in
[Section 7.1.10, “Server Status Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-status-variables.html "7.1.10 Server Status Variables").


```sql

mysql> SHOW STATUS;
+--------------------------+------------+
| Variable_name            | Value      |
+--------------------------+------------+
| Aborted_clients          | 0          |
| Aborted_connects         | 0          |
| Bytes_received           | 155372598  |
| Bytes_sent               | 1176560426 |
| Connections              | 30023      |
| Created_tmp_disk_tables  | 0          |
| Created_tmp_tables       | 8340       |
| Created_tmp_files        | 60         |
...
| Open_tables              | 1          |
| Open_files               | 2          |
| Open_streams             | 0          |
| Opened_tables            | 44600      |
| Questions                | 2026873    |
...
| Table_locks_immediate    | 1920382    |
| Table_locks_waited       | 0          |
| Threads_cached           | 0          |
| Threads_created          | 30022      |
| Threads_connected        | 1          |
| Threads_running          | 1          |
| Uptime                   | 80380      |
+--------------------------+------------+
```

With a [`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) clause, the statement
displays only rows for those variables with names that match the
pattern:


```sql

mysql> SHOW STATUS LIKE 'Key%';
+--------------------+----------+
| Variable_name      | Value    |
+--------------------+----------+
| Key_blocks_used    | 14955    |
| Key_read_requests  | 96854827 |
| Key_reads          | 162040   |
| Key_write_requests | 7589728  |
| Key_writes         | 3813196  |
+--------------------+----------+
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/show-slave-status.html "Previous: SHOW SLAVE | REPLICA STATUS Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "Next: SHOW TABLE STATUS Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-status.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-status.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-status.html)

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