---
url: https://dev.mysql.com/doc/refman/8.0/en/show-databases.html
scraped_at: 2025-10-20T03:06:21.119Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html "Hide Sidebar")

[Previous: SHOW CREATE VIEW Statement](https://dev.mysql.com/doc/refman/8.0/en/show-create-view.html "Previous: SHOW CREATE VIEW Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements")[Next: SHOW ENGINE Statement](https://dev.mysql.com/doc/refman/8.0/en/show-engine.html "Next: SHOW ENGINE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/show-databases.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/show-databases.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/show-databases.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/show-databases.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/show-databases.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/show-databases.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/show-databases.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/show-databases.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)  /

SHOW DATABASES Statement


#### 15.7.7.14 SHOW DATABASES Statement

```sql
SHOW {DATABASES | SCHEMAS}
    [LIKE 'pattern' | WHERE expr]
```

[`SHOW DATABASES`](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html "15.7.7.14 SHOW DATABASES Statement") lists the
databases on the MySQL server host.
[`SHOW\\
        SCHEMAS`](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html "15.7.7.14 SHOW DATABASES Statement") is a synonym for [`SHOW\\
        DATABASES`](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html "15.7.7.14 SHOW DATABASES Statement"). The [`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like)
clause, if present, indicates which database names to match. The
`WHERE` clause can be given to select rows
using more general conditions, as discussed in
[Section 28.8, “Extensions to SHOW Statements”](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html "28.8 Extensions to SHOW Statements").


You see only those databases for which you have some kind of
privilege, unless you have the global [`SHOW\\
        DATABASES`](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html "15.7.7.14 SHOW DATABASES Statement") privilege. You can also get this list using
the [**mysqlshow**](https://dev.mysql.com/doc/refman/8.0/en/mysqlshow.html "6.5.7 mysqlshow — Display Database, Table, and Column Information") command.


If the server was started with the
[`--skip-show-database`](https://dev.mysql.com/doc/refman/8.0/en/server-options.html#option_mysqld_skip-show-database) option, you
cannot use this statement at all unless you have the
[`SHOW DATABASES`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_show-databases) privilege.


MySQL implements databases as directories in the data directory,
so this statement simply lists directories in that location.
However, the output may include names of directories that do not
correspond to actual databases.


Database information is also available from the
`INFORMATION_SCHEMA` [`SCHEMATA`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-schemata-table.html "28.3.31 The INFORMATION_SCHEMA SCHEMATA Table") table. See
[Section 28.3.31, “The INFORMATION\_SCHEMA SCHEMATA Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-schemata-table.html "28.3.31 The INFORMATION_SCHEMA SCHEMATA Table").

Caution

Because any static global privilege is considered a privilege
for all databases, any static global privilege enables a user
to see all database names with [`SHOW\\
          DATABASES`](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html "15.7.7.14 SHOW DATABASES Statement") or by examining the
[`SCHEMATA`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-schemata-table.html "28.3.31 The INFORMATION_SCHEMA SCHEMATA Table") table of
`INFORMATION_SCHEMA`, except databases that
have been restricted at the database level by partial revokes.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/show-create-view.html "Previous: SHOW CREATE VIEW Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/show-engine.html "Next: SHOW ENGINE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html)

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