---
url: https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html
scraped_at: 2025-10-20T03:05:20.036Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html "Hide Sidebar")

[Previous: ALTER LOGFILE GROUP Statement](https://dev.mysql.com/doc/refman/8.0/en/alter-logfile-group.html "Previous: ALTER LOGFILE GROUP Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements")[Next: ALTER SERVER Statement](https://dev.mysql.com/doc/refman/8.0/en/alter-server.html "Next: ALTER SERVER Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/alter-procedure.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/alter-procedure.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/alter-procedure.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/alter-procedure.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/alter-procedure.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/alter-procedure.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/alter-procedure.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/alter-procedure.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html)  /

ALTER PROCEDURE Statement


### 15.1.7 ALTER PROCEDURE Statement

```sql
ALTER PROCEDURE proc_name [characteristic ...]

characteristic: {
    COMMENT 'string'
  | LANGUAGE SQL
  | { CONTAINS SQL | NO SQL | READS SQL DATA | MODIFIES SQL DATA }
  | SQL SECURITY { DEFINER | INVOKER }
}
```

This statement can be used to change the characteristics of a
stored procedure. More than one change may be specified in an
[`ALTER PROCEDURE`](https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html "15.1.7 ALTER PROCEDURE Statement") statement. However,
you cannot change the parameters or body of a stored procedure
using this statement; to make such changes, you must drop and
re-create the procedure using [`DROP\\
      PROCEDURE`](https://dev.mysql.com/doc/refman/8.0/en/drop-procedure.html "15.1.29 DROP PROCEDURE and DROP FUNCTION Statements") and [`CREATE\\
      PROCEDURE`](https://dev.mysql.com/doc/refman/8.0/en/create-procedure.html "15.1.17 CREATE PROCEDURE and CREATE FUNCTION Statements").


You must have the [`ALTER ROUTINE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_alter-routine)
privilege for the procedure. By default, that privilege is granted
automatically to the procedure creator. This behavior can be
changed by disabling the
[`automatic_sp_privileges`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_automatic_sp_privileges) system
variable. See [Section 27.2.2, “Stored Routines and MySQL Privileges”](https://dev.mysql.com/doc/refman/8.0/en/stored-routines-privileges.html "27.2.2 Stored Routines and MySQL Privileges").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/alter-logfile-group.html "Previous: ALTER LOGFILE GROUP Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/alter-server.html "Next: ALTER SERVER Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/alter-procedure.html)

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