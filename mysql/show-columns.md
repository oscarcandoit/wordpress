---
url: https://dev.mysql.com/doc/refman/8.0/en/show-columns.html
scraped_at: 2025-10-20T03:06:28.798Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "Hide Sidebar")

[Previous: SHOW COLLATION Statement](https://dev.mysql.com/doc/refman/8.0/en/show-collation.html "Previous: SHOW COLLATION Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements")[Next: SHOW CREATE DATABASE Statement](https://dev.mysql.com/doc/refman/8.0/en/show-create-database.html "Next: SHOW CREATE DATABASE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/show-columns.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/show-columns.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/show-columns.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/show-columns.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/show-columns.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/show-columns.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/show-columns.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/show-columns.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)  /

SHOW COLUMNS Statement


#### 15.7.7.5 SHOW COLUMNS Statement

``` sql

SHOW [EXTENDED] [FULL] {COLUMNS | FIELDS}
    {FROM | IN} tbl_name
    [{FROM | IN} db_name]
    [LIKE 'pattern' | WHERE expr]
```

[`SHOW COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "15.7.7.5 SHOW COLUMNS Statement") displays information
about the columns in a given table. It also works for views.
[`SHOW COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "15.7.7.5 SHOW COLUMNS Statement") displays information
only for those columns for which you have some privilege.


``` sql

mysql> SHOW COLUMNS FROM City;
+-------------+----------+------+-----+---------+----------------+
| Field       | Type     | Null | Key | Default | Extra          |
+-------------+----------+------+-----+---------+----------------+
| ID          | int(11)  | NO   | PRI | NULL    | auto_increment |
| Name        | char(35) | NO   |     |         |                |
| CountryCode | char(3)  | NO   | MUL |         |                |
| District    | char(20) | NO   |     |         |                |
| Population  | int(11)  | NO   |     | 0       |                |
+-------------+----------+------+-----+---------+----------------+
```

An alternative to `tbl_name
        FROM db_name` syntax is
_`db_name.tbl_name`_. These two
statements are equivalent:


``` sql

SHOW COLUMNS FROM mytable FROM mydb;
SHOW COLUMNS FROM mydb.mytable;
```

The optional `EXTENDED` keyword causes the
output to include information about hidden columns that MySQL
uses internally and are not accessible by users.


The optional `FULL` keyword causes the output
to include the column collation and comments, as well as the
privileges you have for each column.


The [`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) clause, if present,
indicates which column names to match. The
`WHERE` clause can be given to select rows
using more general conditions, as discussed in
[Section 28.8, “Extensions to SHOW Statements”](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html "28.8 Extensions to SHOW Statements").


The data types may differ from what you expect them to be based
on a [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement
because MySQL sometimes changes data types when you create or
alter a table. The conditions under which this occurs are
described in [Section 15.1.20.7, “Silent Column Specification Changes”](https://dev.mysql.com/doc/refman/8.0/en/silent-column-changes.html "15.1.20.7 Silent Column Specification Changes").


[`SHOW COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "15.7.7.5 SHOW COLUMNS Statement") displays the
following values for each table column:

- `Field`


The name of the column.


- `Type`


The column data type.


- `Collation`


The collation for nonbinary string columns, or
`NULL` for other columns. This value is
displayed only if you use the `FULL`
keyword.


- `Null`


The column nullability. The value is `YES`
if `NULL` values can be stored in the
column, `NO` if not.


- `Key`


Whether the column is indexed:




- If `Key` is empty, the column either is
not indexed or is indexed only as a secondary column in
a multiple-column, nonunique index.


- If `Key` is `PRI`, the
column is a `PRIMARY KEY` or is one of
the columns in a multiple-column `PRIMARY
                  KEY`.


- If `Key` is `UNI`, the
column is the first column of a
`UNIQUE` index. (A
`UNIQUE` index permits multiple
`NULL` values, but you can tell whether
the column permits `NULL` by checking
the `Null` field.)


- If `Key` is `MUL`, the
column is the first column of a nonunique index in which
multiple occurrences of a given value are permitted
within the column.


If more than one of the `Key` values
applies to a given column of a table, `Key`
displays the one with the highest priority, in the order
`PRI`, `UNI`,
`MUL`.


A `UNIQUE` index may be displayed as
`PRI` if it cannot contain
`NULL` values and there is no
`PRIMARY KEY` in the table. A
`UNIQUE` index may display as
`MUL` if several columns form a composite
`UNIQUE` index; although the combination of
the columns is unique, each column can still hold multiple
occurrences of a given value.


- `Default`


The default value for the column. This is
`NULL` if the column has an explicit
default of `NULL`, or if the column
definition includes no `DEFAULT` clause.


- `Extra`


Any additional information that is available about a given
column. The value is nonempty in these cases:




- `auto_increment` for columns that have
the `AUTO_INCREMENT` attribute.


- `on update CURRENT_TIMESTAMP` for
[`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") or
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") columns that
have the `ON UPDATE CURRENT_TIMESTAMP`
attribute.


- `VIRTUAL GENERATED` or `STORED
                  GENERATED` for generated columns.


- `DEFAULT_GENERATED` for columns that
have an expression default value.


- `Privileges`


The privileges you have for the column. This value is
displayed only if you use the `FULL`
keyword.


- `Comment`


Any comment included in the column definition. This value is
displayed only if you use the `FULL`
keyword.


Table column information is also available from the
`INFORMATION_SCHEMA` [`COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html "28.3.8 The INFORMATION_SCHEMA COLUMNS Table") table. See
[Section 28.3.8, “The INFORMATION\_SCHEMA COLUMNS Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html "28.3.8 The INFORMATION_SCHEMA COLUMNS Table"). The extended
information about hidden columns is available only using
`SHOW EXTENDED COLUMNS`; it cannot be obtained
from the [`COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html "28.3.8 The INFORMATION_SCHEMA COLUMNS Table") table.


You can list a table's columns with the [**mysqlshow**\\
**_`db_name`_ _`tbl_name`_**](https://dev.mysql.com/doc/refman/8.0/en/mysqlshow.html "6.5.7 mysqlshow — Display Database, Table, and Column Information") command.


The [`DESCRIBE`](https://dev.mysql.com/doc/refman/8.0/en/describe.html "15.8.1 DESCRIBE Statement") statement provides
information similar to [`SHOW\\
        COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "15.7.7.5 SHOW COLUMNS Statement"). See [Section 15.8.1, “DESCRIBE Statement”](https://dev.mysql.com/doc/refman/8.0/en/describe.html "15.8.1 DESCRIBE Statement").


The [`SHOW CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html "15.7.7.10 SHOW CREATE TABLE Statement"),
[`SHOW TABLE STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement"), and
[`SHOW INDEX`](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "15.7.7.22 SHOW INDEX Statement") statements also
provide information about tables. See [Section 15.7.7, “SHOW Statements”](https://dev.mysql.com/doc/refman/8.0/en/show.html "15.7.7 SHOW Statements").


In MySQL 8.0.30 and later, `SHOW COLUMNS`
includes the table's generated invisible primary key, if it
has one, by default. You can cause this information to be
suppressed in the statement's output by setting
[`show_gipk_in_create_table_and_information_schema\\
        = OFF`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_show_gipk_in_create_table_and_information_schema). For more information, see
[Section 15.1.20.11, “Generated Invisible Primary Keys”](https://dev.mysql.com/doc/refman/8.0/en/create-table-gipks.html "15.1.20.11 Generated Invisible Primary Keys").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/show-collation.html "Previous: SHOW COLLATION Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/show-create-database.html "Next: SHOW CREATE DATABASE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html)

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