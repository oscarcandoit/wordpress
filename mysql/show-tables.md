---
url: https://dev.mysql.com/doc/refman/8.0/en/show-tables.html
scraped_at: 2025-10-20T03:06:24.780Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html "Hide Sidebar")

[Previous: SHOW TABLE STATUS Statement](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "Previous: SHOW TABLE STATUS Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements")[Next: SHOW TRIGGERS Statement](https://dev.mysql.com/doc/refman/8.0/en/show-triggers.html "Next: SHOW TRIGGERS Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/show-tables.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/show-tables.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/show-tables.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/show-tables.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/show-tables.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/show-tables.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/show-tables.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/show-tables.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)  /

SHOW TABLES Statement


#### 15.7.7.39 SHOW TABLES Statement

```sql
SHOW [EXTENDED] [FULL] TABLES
    [{FROM | IN} db_name]
    [LIKE 'pattern' | WHERE expr]
```

[`SHOW TABLES`](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html "15.7.7.39 SHOW TABLES Statement") lists the
non- `TEMPORARY` tables in a given database. You
can also get this list using the [**mysqlshow**\\
**_`db_name`_**](https://dev.mysql.com/doc/refman/8.0/en/mysqlshow.html "6.5.7 mysqlshow — Display Database, Table, and Column Information") command. The
[`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) clause, if present, indicates
which table names to match. The `WHERE` clause
can be given to select rows using more general conditions, as
discussed in [Section 28.8, “Extensions to SHOW Statements”](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html "28.8 Extensions to SHOW Statements").


Matching performed by the `LIKE` clause is
dependent on the setting of the
[`lower_case_table_names`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_lower_case_table_names) system
variable.


The optional `EXTENDED` modifier causes
[`SHOW TABLES`](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html "15.7.7.39 SHOW TABLES Statement") to list hidden tables
created by failed [`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement")
statements. These temporary tables have names beginning with
`#sql` and can be dropped using
[`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement").


This statement also lists any views in the database. The
optional `FULL` modifier causes
[`SHOW TABLES`](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html "15.7.7.39 SHOW TABLES Statement") to display a second
output column with values of `BASE TABLE` for a
table, `VIEW` for a view, or `SYSTEM
        VIEW` for an `INFORMATION_SCHEMA`
table.


If you have no privileges for a base table or view, it does not
show up in the output from [`SHOW\\
        TABLES`](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html "15.7.7.39 SHOW TABLES Statement") or [**mysqlshow db\_name**](https://dev.mysql.com/doc/refman/8.0/en/mysqlshow.html "6.5.7 mysqlshow — Display Database, Table, and Column Information").


Table information is also available from the
`INFORMATION_SCHEMA` [`TABLES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html "28.3.38 The INFORMATION_SCHEMA TABLES Table") table. See
[Section 28.3.38, “The INFORMATION\_SCHEMA TABLES Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html "28.3.38 The INFORMATION_SCHEMA TABLES Table").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "Previous: SHOW TABLE STATUS Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/show-triggers.html "Next: SHOW TRIGGERS Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html)

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