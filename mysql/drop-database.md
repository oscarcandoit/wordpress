---
url: https://dev.mysql.com/doc/refman/8.0/en/drop-database.html
scraped_at: 2025-10-20T03:00:50.867Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "Hide Sidebar")

[Previous: CREATE VIEW Statement](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "Previous: CREATE VIEW Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements")[Next: DROP EVENT Statement](https://dev.mysql.com/doc/refman/8.0/en/drop-event.html "Next: DROP EVENT Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/drop-database.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/drop-database.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/drop-database.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/drop-database.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/drop-database.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/drop-database.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/drop-database.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/drop-database.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html)  /

DROP DATABASE Statement


### 15.1.24 DROP DATABASE Statement

``` sql

DROP {DATABASE | SCHEMA} [IF EXISTS] db_name
```

[`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement") drops all tables in
the database and deletes the database. Be
_very_ careful with this statement! To use
[`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement"), you need the
[`DROP`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_drop) privilege on the database.
[`DROP\\
      SCHEMA`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement") is a synonym for [`DROP\\
      DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement").

Important

When a database is dropped, privileges granted specifically for
the database are _not_ automatically dropped.
They must be dropped manually. See [Section 15.7.1.6, “GRANT Statement”](https://dev.mysql.com/doc/refman/8.0/en/grant.html "15.7.1.6 GRANT Statement").

`IF EXISTS` is used to prevent an error from
occurring if the database does not exist.


If the default database is dropped, the default database is unset
(the [`DATABASE()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_database) function returns
`NULL`).


If you use [`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement") on a
symbolically linked database, both the link and the original
database are deleted.


[`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement") returns the number of
tables that were removed.


The [`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement") statement removes
from the given database directory those files and directories that
MySQL itself may create during normal operation. This includes all
files with the extensions shown in the following list:

- `.BAK`

- `.DAT`

- `.HSH`

- `.MRG`

- `.MYD`

- `.MYI`

- `.cfg`

- `.db`

- `.ibd`

- `.ndb`


If other files or directories remain in the database directory
after MySQL removes those just listed, the database directory
cannot be removed. In this case, you must remove any remaining
files or directories manually and issue the
[`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "15.1.24 DROP DATABASE Statement") statement again.


Dropping a database does not remove any
`TEMPORARY` tables that were created in that
database. `TEMPORARY` tables are automatically
removed when the session that created them ends. See
[Section 15.1.20.2, “CREATE TEMPORARY TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/create-temporary-table.html "15.1.20.2 CREATE TEMPORARY TABLE Statement").


You can also drop databases with [**mysqladmin**](https://dev.mysql.com/doc/refman/8.0/en/mysqladmin.html "6.5.2 mysqladmin — A MySQL Server Administration Program").
See [Section 6.5.2, “mysqladmin — A MySQL Server Administration Program”](https://dev.mysql.com/doc/refman/8.0/en/mysqladmin.html "6.5.2 mysqladmin — A MySQL Server Administration Program").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "Previous: CREATE VIEW Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/drop-event.html "Next: DROP EVENT Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html)

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