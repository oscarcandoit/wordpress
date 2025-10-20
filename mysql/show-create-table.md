---
url: https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html
scraped_at: 2025-10-20T03:06:40.162Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html "Hide Sidebar")

[Previous: SHOW CREATE PROCEDURE Statement](https://dev.mysql.com/doc/refman/8.0/en/show-create-procedure.html "Previous: SHOW CREATE PROCEDURE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements")[Next: SHOW CREATE TRIGGER Statement](https://dev.mysql.com/doc/refman/8.0/en/show-create-trigger.html "Next: SHOW CREATE TRIGGER Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/show-create-table.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/show-create-table.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/show-create-table.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/show-create-table.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/show-create-table.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/show-create-table.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/show-create-table.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/show-create-table.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)  /

SHOW CREATE TABLE Statement


#### 15.7.7.10 SHOW CREATE TABLE Statement

``` sql

SHOW CREATE TABLE tbl_name
```

Shows the [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement
that creates the named table. To use this statement, you must
have some privilege for the table. This statement also works
with views.


``` sql

mysql> SHOW CREATE TABLE t\G
*************************** 1. row ***************************
       Table: t
Create Table: CREATE TABLE `t` (
  `id` int NOT NULL AUTO_INCREMENT,
  `s` char(60) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```

As of MySQL 8.0.16, MySQL implements `CHECK`
constraints and [`SHOW CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html "15.7.7.10 SHOW CREATE TABLE Statement")
displays them. All `CHECK` constraints are
displayed as table constraints. That is, a
`CHECK` constraint originally specified as part
of a column definition displays as a separate clause not part of
the column definition. Example:


``` sql

mysql> CREATE TABLE t1 (
         i1 INT CHECK (i1 <> 0),      -- column constraint
         i2 INT,
         CHECK (i2 > i1),             -- table constraint
         CHECK (i2 <> 0) NOT ENFORCED -- table constraint, not enforced
       );

mysql> SHOW CREATE TABLE t1\G
*************************** 1. row ***************************
       Table: t1
Create Table: CREATE TABLE `t1` (
  `i1` int DEFAULT NULL,
  `i2` int DEFAULT NULL,
  CONSTRAINT `t1_chk_1` CHECK ((`i1` <> 0)),
  CONSTRAINT `t1_chk_2` CHECK ((`i2` > `i1`)),
  CONSTRAINT `t1_chk_3` CHECK ((`i2` <> 0)) /*!80016 NOT ENFORCED */
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```

[`SHOW CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html "15.7.7.10 SHOW CREATE TABLE Statement") quotes table
and column names according to the value of the
[`sql_quote_show_create`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_sql_quote_show_create) option.
See [Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables").


When altering the storage engine of a table, table options that
are not applicable to the new storage engine are retained in the
table definition to enable reverting the table with its
previously defined options to the original storage engine, if
necessary. For example, when changing the storage engine from
`InnoDB` to `MyISAM`, options
specific to `InnoDB`, such as
`ROW_FORMAT=COMPACT`, are retained, as shown
here:


``` sql

mysql> CREATE TABLE t1 (c1 INT PRIMARY KEY) ROW_FORMAT=COMPACT ENGINE=InnoDB;
mysql> ALTER TABLE t1 ENGINE=MyISAM;
mysql> SHOW CREATE TABLE t1\G
*************************** 1. row ***************************
       Table: t1
Create Table: CREATE TABLE `t1` (
  `c1` int NOT NULL,
  PRIMARY KEY (`c1`)
) ENGINE=MyISAM DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci ROW_FORMAT=COMPACT
```

When creating a table with
[strict mode](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_strict_mode "strict mode") disabled,
the storage engine's default row format is used if the
specified row format is not supported. The actual row format of
the table is reported in the `Row_format`
column in response to [`SHOW TABLE\\
        STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement"). [`SHOW CREATE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html "15.7.7.10 SHOW CREATE TABLE Statement") shows the row format that was specified in the
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement.


In MySQL 8.0.30 and later, `SHOW CREATE TABLE`
includes the definition of the table's generated invisible
primary key, if it has such a key, by default. You can cause
this information to be suppressed in the statement's output
by setting
[`show_gipk_in_create_table_and_information_schema\\
        = OFF`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_show_gipk_in_create_table_and_information_schema). For more information, see
[Section 15.1.20.11, “Generated Invisible Primary Keys”](https://dev.mysql.com/doc/refman/8.0/en/create-table-gipks.html "15.1.20.11 Generated Invisible Primary Keys").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/show-create-procedure.html "Previous: SHOW CREATE PROCEDURE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/show-create-trigger.html "Next: SHOW CREATE TRIGGER Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html)

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