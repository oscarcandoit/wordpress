---
url: https://dev.mysql.com/doc/refman/8.0/en/drop-table.html
scraped_at: 2025-10-20T02:59:22.231Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "Hide Sidebar")

[Previous: DROP SPATIAL REFERENCE SYSTEM Statement](https://dev.mysql.com/doc/refman/8.0/en/drop-spatial-reference-system.html "Previous: DROP SPATIAL REFERENCE SYSTEM Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements")[Next: DROP TABLESPACE Statement](https://dev.mysql.com/doc/refman/8.0/en/drop-tablespace.html "Next: DROP TABLESPACE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/drop-table.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/drop-table.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/drop-table.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/drop-table.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/drop-table.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/drop-table.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/drop-table.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/drop-table.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html)  /

DROP TABLE Statement


### 15.1.32 DROP TABLE Statement

``` sql

DROP [TEMPORARY] TABLE [IF EXISTS]
    tbl_name [, tbl_name] ...
    [RESTRICT | CASCADE]
```

[`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") removes one or more
tables. You must have the [`DROP`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_drop)
privilege for each table.


_Be careful_ with this statement! For each
table, it removes the table definition and all table data. If the
table is partitioned, the statement removes the table definition,
all its partitions, all data stored in those partitions, and all
partition definitions associated with the dropped table.


Dropping a table also drops any triggers for the table.


[`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") causes an implicit
commit, except when used with the `TEMPORARY`
keyword. See [Section 15.3.3, “Statements That Cause an Implicit Commit”](https://dev.mysql.com/doc/refman/8.0/en/implicit-commit.html "15.3.3 Statements That Cause an Implicit Commit").

Important

When a table is dropped, privileges granted specifically for the
table are _not_ automatically dropped. They
must be dropped manually. See [Section 15.7.1.6, “GRANT Statement”](https://dev.mysql.com/doc/refman/8.0/en/grant.html "15.7.1.6 GRANT Statement").

If any tables named in the argument list do not exist,
[`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") behavior depends on
whether the `IF EXISTS` clause is given:

- Without `IF EXISTS`, the statement fails with
an error indicating which nonexisting tables it was unable to
drop, and no changes are made.


- With `IF EXISTS`, no error occurs for
nonexisting tables. The statement drops all named tables that
do exist, and generates a `NOTE` diagnostic
for each nonexistent table. These notes can be displayed with
[`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement"). See
[Section 15.7.7.42, “SHOW WARNINGS Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement").


`IF EXISTS` can also be useful for dropping
tables in unusual circumstances under which there is an entry in
the data dictionary but no table managed by the storage engine.
(For example, if an abnormal server exit occurs after removal of
the table from the storage engine but before removal of the data
dictionary entry.)


The `TEMPORARY` keyword has the following
effects:

- The statement drops only `TEMPORARY` tables.


- The statement does not cause an implicit commit.


- No access rights are checked. A `TEMPORARY`
table is visible only with the session that created it, so no
check is necessary.


Including the `TEMPORARY` keyword is a good way
to prevent accidentally dropping non- `TEMPORARY`
tables.


The `RESTRICT` and `CASCADE`
keywords do nothing. They are permitted to make porting easier
from other database systems.


[`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") is not supported with
all [`innodb_force_recovery`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_force_recovery)
settings. See [Section 17.21.3, “Forcing InnoDB Recovery”](https://dev.mysql.com/doc/refman/8.0/en/forcing-innodb-recovery.html "17.21.3 Forcing InnoDB Recovery").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/drop-spatial-reference-system.html "Previous: DROP SPATIAL REFERENCE SYSTEM Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/drop-tablespace.html "Next: DROP TABLESPACE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html)

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