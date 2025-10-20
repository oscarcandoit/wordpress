---
url: https://dev.mysql.com/doc/refman/8.0/en/create-database.html
scraped_at: 2025-10-20T03:00:01.714Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/create-database.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "Hide Sidebar")

[Previous: ALTER VIEW Statement](https://dev.mysql.com/doc/refman/8.0/en/alter-view.html "Previous: ALTER VIEW Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements")[Next: CREATE EVENT Statement](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "Next: CREATE EVENT Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/create-database.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-database.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-database.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/create-database.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/create-database.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/create-database.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/create-database.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/create-database.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/create-database.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/create-database.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/create-database.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/create-database.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/create-database.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html)  /

CREATE DATABASE Statement


### 15.1.12 CREATE DATABASE Statement

```sql

CREATE {DATABASE | SCHEMA} [IF NOT EXISTS] db_name
    [create_option] ...

create_option: [DEFAULT] {
    CHARACTER SET [=] charset_name
  | COLLATE [=] collation_name
  | ENCRYPTION [=] {'Y' | 'N'}
}
```

[`CREATE DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "15.1.12 CREATE DATABASE Statement") creates a database
with the given name. To use this statement, you need the
[`CREATE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_create) privilege for the database.
[`CREATE\\
      SCHEMA`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "15.1.12 CREATE DATABASE Statement") is a synonym for [`CREATE\\
      DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "15.1.12 CREATE DATABASE Statement").


An error occurs if the database exists and you did not specify
`IF NOT EXISTS`.


[`CREATE DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "15.1.12 CREATE DATABASE Statement") is not permitted
within a session that has an active [`LOCK\\
      TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") statement.


Each _`create_option`_ specifies a database
characteristic. Database characteristics are stored in the data
dictionary.

- The `CHARACTER SET` option specifies the
default database character set. The `COLLATE`
option specifies the default database collation. For
information about character set and collation names, see
[Chapter 12, _Character Sets, Collations, Unicode_](https://dev.mysql.com/doc/refman/8.0/en/charset.html "Chapter 12 Character Sets, Collations, Unicode").



To see the available character sets and collations, use the
the [`SHOW CHARACTER SET`](https://dev.mysql.com/doc/refman/8.0/en/show-character-set.html "15.7.7.3 SHOW CHARACTER SET Statement") and
[`SHOW COLLATION`](https://dev.mysql.com/doc/refman/8.0/en/show-collation.html "15.7.7.4 SHOW COLLATION Statement") statements,
respectively. See [Section 15.7.7.3, “SHOW CHARACTER SET Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-character-set.html "15.7.7.3 SHOW CHARACTER SET Statement"), and
[Section 15.7.7.4, “SHOW COLLATION Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-collation.html "15.7.7.4 SHOW COLLATION Statement").


- The `ENCRYPTION` option, introduced in MySQL
8.0.16, defines the default database encryption, which is
inherited by tables created in the database. The permitted
values are `'Y'` (encryption enabled) and
`'N'` (encryption disabled). If the
`ENCRYPTION` option is not specified, the
value of the
[`default_table_encryption`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_default_table_encryption)
system variable defines the default database encryption. If
the
[`table_encryption_privilege_check`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_table_encryption_privilege_check)
system variable is enabled, the
[`TABLE_ENCRYPTION_ADMIN`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_table-encryption-admin)
privilege is required to specify a default encryption setting
that differs from the
[`default_table_encryption`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_default_table_encryption)
setting. For more information, see
[Defining an Encryption Default for Schemas and General Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-data-encryption.html#innodb-schema-tablespace-encryption-default "Defining an Encryption Default for Schemas and General Tablespaces").


A database in MySQL is implemented as a directory containing files
that correspond to tables in the database. Because there are no
tables in a database when it is initially created, the
[`CREATE DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "15.1.12 CREATE DATABASE Statement") statement creates
only a directory under the MySQL data directory. Rules for
permissible database names are given in
[Section 11.2, “Schema Object Names”](https://dev.mysql.com/doc/refman/8.0/en/identifiers.html "11.2 Schema Object Names"). If a database name contains special
characters, the name for the database directory contains encoded
versions of those characters as described in
[Section 11.2.4, “Mapping of Identifiers to File Names”](https://dev.mysql.com/doc/refman/8.0/en/identifier-mapping.html "11.2.4 Mapping of Identifiers to File Names").


Creating a database directory by manually creating a directory
under the data directory (for example, with
**mkdir**) is unsupported in MySQL 8.0.


When you create a database, let the server manage the directory
and the files in it. Manipulating database directories and files
directly can cause inconsistencies and unexpected results.


MySQL has no limit on the number of databases. The underlying file
system may have a limit on the number of directories.


You can also use the [**mysqladmin**](https://dev.mysql.com/doc/refman/8.0/en/mysqladmin.html "6.5.2 mysqladmin — A MySQL Server Administration Program") program to
create databases. See [Section 6.5.2, “mysqladmin — A MySQL Server Administration Program”](https://dev.mysql.com/doc/refman/8.0/en/mysqladmin.html "6.5.2 mysqladmin — A MySQL Server Administration Program").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/alter-view.html "Previous: ALTER VIEW Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "Next: CREATE EVENT Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/create-database.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-database.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-database.html)

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