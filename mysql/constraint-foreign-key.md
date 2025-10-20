---
url: https://dev.mysql.com/doc/refman/8.0/en/constraint-foreign-key.html
scraped_at: 2025-10-20T02:59:57.007Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/constraint-foreign-key.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/constraint-foreign-key.html "Hide Sidebar")

[Previous: PRIMARY KEY and UNIQUE Index Constraints](https://dev.mysql.com/doc/refman/8.0/en/constraint-primary-key.html "Previous: PRIMARY KEY and UNIQUE Index Constraints")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: How MySQL Deals with Constraints](https://dev.mysql.com/doc/refman/8.0/en/constraints.html "Up: How MySQL Deals with Constraints")[Next: Enforced Constraints on Invalid Data](https://dev.mysql.com/doc/refman/8.0/en/constraint-invalid-data.html "Next: Enforced Constraints on Invalid Data")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/constraint-foreign-key.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/constraint-foreign-key.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/constraint-foreign-key.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/constraint-foreign-key.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/constraint-foreign-key.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/constraint-foreign-key.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/constraint-foreign-key.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/constraint-foreign-key.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/constraint-foreign-key.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/constraint-foreign-key.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/constraint-foreign-key.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/constraint-foreign-key.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/constraint-foreign-key.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/constraint-foreign-key.html)  / [General Information](https://dev.mysql.com/doc/refman/8.0/en/introduction.html)  /
[MySQL Standards Compliance](https://dev.mysql.com/doc/refman/8.0/en/compatibility.html)  /
[How MySQL Deals with Constraints](https://dev.mysql.com/doc/refman/8.0/en/constraints.html)  /

FOREIGN KEY Constraints


#### 1.6.3.2 FOREIGN KEY Constraints

Foreign keys let you cross-reference related data across
tables, and
[foreign key\\
constraints](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_foreign_key_constraint "FOREIGN KEY constraint") help keep this spread-out data consistent.


MySQL supports `ON UPDATE` and `ON
          DELETE` foreign key references in
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") and
[`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") statements. The
available referential actions are `RESTRICT`,
`CASCADE`, `SET NULL`, and
`NO ACTION` (the default).


`SET DEFAULT` is also supported by the MySQL
Server but is currently rejected as invalid by
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine"). Since MySQL does not
support deferred constraint checking, `NO
          ACTION` is treated as `RESTRICT`.
For the exact syntax supported by MySQL for foreign keys, see
[Section 15.1.20.5, “FOREIGN KEY Constraints”](https://dev.mysql.com/doc/refman/8.0/en/create-table-foreign-keys.html "15.1.20.5 FOREIGN KEY Constraints").


`MATCH FULL`, `MATCH
          PARTIAL`, and `MATCH SIMPLE` are
allowed, but their use should be avoided, as they cause the
MySQL Server to ignore any `ON DELETE` or
`ON UPDATE` clause used in the same
statement. `MATCH` options do not have any
other effect in MySQL, which in effect enforces `MATCH
          SIMPLE` semantics full-time.


MySQL requires that foreign key columns be indexed; if you
create a table with a foreign key constraint but no index on a
given column, an index is created.


You can obtain information about foreign keys from the
Information Schema
[`KEY_COLUMN_USAGE`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-key-column-usage-table.html "28.3.16 The INFORMATION_SCHEMA KEY_COLUMN_USAGE Table") table. An
example of a query against this table is shown here:


```sql
mysql> SELECT TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME, CONSTRAINT_NAME
     > FROM INFORMATION_SCHEMA.KEY_COLUMN_USAGE
     > WHERE REFERENCED_TABLE_SCHEMA IS NOT NULL;
+--------------+---------------+-------------+-----------------+
| TABLE_SCHEMA | TABLE_NAME    | COLUMN_NAME | CONSTRAINT_NAME |
+--------------+---------------+-------------+-----------------+
| fk1          | myuser        | myuser_id   | f               |
| fk1          | product_order | customer_id | f2              |
| fk1          | product_order | product_id  | f1              |
+--------------+---------------+-------------+-----------------+
3 rows in set (0.01 sec)
```

Information about foreign keys on `InnoDB`
tables can also be found in the
[`INNODB_FOREIGN`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-foreign-table.html "28.4.12 The INFORMATION_SCHEMA INNODB_FOREIGN Table") and
[`INNODB_FOREIGN_COLS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-foreign-cols-table.html "28.4.13 The INFORMATION_SCHEMA INNODB_FOREIGN_COLS Table") tables, in
the `INFORMATION_SCHEMA` database.


`InnoDB` and `NDB` tables
support foreign keys.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/constraint-primary-key.html "Previous: PRIMARY KEY and UNIQUE Index Constraints") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/constraints.html "Up: How MySQL Deals with Constraints") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/constraint-invalid-data.html "Next: Enforced Constraints on Invalid Data")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/constraint-foreign-key.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/constraint-foreign-key.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/constraint-foreign-key.html)

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