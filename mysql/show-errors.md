---
url: https://dev.mysql.com/doc/refman/8.0/en/show-errors.html
scraped_at: 2025-10-20T03:11:24.452Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html "Hide Sidebar")

[Previous: SHOW ENGINES Statement](https://dev.mysql.com/doc/refman/8.0/en/show-engines.html "Previous: SHOW ENGINES Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements")[Next: SHOW EVENTS Statement](https://dev.mysql.com/doc/refman/8.0/en/show-events.html "Next: SHOW EVENTS Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/show-errors.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/show-errors.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/show-errors.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/show-errors.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/show-errors.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/show-errors.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/show-errors.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/show-errors.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)  /

SHOW ERRORS Statement


#### 15.7.7.17 SHOW ERRORS Statement

```sql
SHOW ERRORS [LIMIT [offset,] row_count]
SHOW COUNT(*) ERRORS
```

[`SHOW ERRORS`](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html "15.7.7.17 SHOW ERRORS Statement") is a diagnostic
statement that is similar to [`SHOW\\
        WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement"), except that it displays information only for
errors, rather than for errors, warnings, and notes.


The `LIMIT` clause has the same syntax as for
the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement. See
[Section 15.2.13, “SELECT Statement”](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement").


The [`SHOW COUNT(*)\\
        ERRORS`](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html "15.7.7.17 SHOW ERRORS Statement") statement displays the number of errors. You
can also retrieve this number from the
[`error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_error_count) variable:


```sql
SHOW COUNT(*) ERRORS;
SELECT @@error_count;
```

[`SHOW ERRORS`](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html "15.7.7.17 SHOW ERRORS Statement") and
[`error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_error_count) apply only to
errors, not warnings or notes. In other respects, they are
similar to [`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") and
[`warning_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_warning_count). In particular,
[`SHOW ERRORS`](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html "15.7.7.17 SHOW ERRORS Statement") cannot display
information for more than
[`max_error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_error_count) messages, and
[`error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_error_count) can exceed the
value of [`max_error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_error_count) if the
number of errors exceeds
[`max_error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_error_count).


For more information, see [Section 15.7.7.42, “SHOW WARNINGS Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/show-engines.html "Previous: SHOW ENGINES Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/show-events.html "Next: SHOW EVENTS Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html)

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