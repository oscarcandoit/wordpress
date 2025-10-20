---
url: https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html
scraped_at: 2025-10-20T03:07:19.467Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html "Hide Sidebar")

[Previous: The INFORMATION_SCHEMA COLLATION_CHARACTER_SET_APPLICABILITY Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-collation-character-set-applicability-table.html "Previous: The INFORMATION_SCHEMA COLLATION_CHARACTER_SET_APPLICABILITY Table")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: INFORMATION_SCHEMA General Tables](https://dev.mysql.com/doc/refman/8.0/en/general-information-schema-tables.html "Up: INFORMATION_SCHEMA General Tables")[Next: The INFORMATION_SCHEMA COLUMNS_EXTENSIONS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-extensions-table.html "Next: The INFORMATION_SCHEMA COLUMNS_EXTENSIONS Table")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/information-schema-columns-table.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/information-schema-columns-table.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/information-schema-columns-table.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/information-schema-columns-table.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/information-schema-columns-table.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/information-schema-columns-table.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/information-schema-columns-table.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/information-schema-columns-table.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html)  / [INFORMATION\_SCHEMA Tables](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)  /
[INFORMATION\_SCHEMA General Tables](https://dev.mysql.com/doc/refman/8.0/en/general-information-schema-tables.html)  /

The INFORMATION\_SCHEMA COLUMNS Table


### 28.3.8 The INFORMATION\_SCHEMA COLUMNS Table

The [`COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html "28.3.8 The INFORMATION_SCHEMA COLUMNS Table") table provides
information about columns in tables. The related
[`ST_GEOMETRY_COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-st-geometry-columns-table.html "28.3.35 The INFORMATION_SCHEMA ST_GEOMETRY_COLUMNS Table") table provides
information about table columns that store spatial data. See
[Section 28.3.35, “The INFORMATION\_SCHEMA ST\_GEOMETRY\_COLUMNS Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-st-geometry-columns-table.html "28.3.35 The INFORMATION_SCHEMA ST_GEOMETRY_COLUMNS Table").


The [`COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html "28.3.8 The INFORMATION_SCHEMA COLUMNS Table") table has these columns:

- `TABLE_CATALOG`


The name of the catalog to which the table containing the
column belongs. This value is always `def`.


- `TABLE_SCHEMA`


The name of the schema (database) to which the table
containing the column belongs.


- `TABLE_NAME`


The name of the table containing the column.


- `COLUMN_NAME`


The name of the column.


- `ORDINAL_POSITION`


The position of the column within the table.
`ORDINAL_POSITION` is necessary because you
might want to say `ORDER BY
            ORDINAL_POSITION`. Unlike [`SHOW\\
            COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "15.7.7.5 SHOW COLUMNS Statement"), [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") from
the [`COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html "28.3.8 The INFORMATION_SCHEMA COLUMNS Table") table does not have
automatic ordering.


- `COLUMN_DEFAULT`


The default value for the column. This is
`NULL` if the column has an explicit default
of `NULL`, or if the column definition
includes no `DEFAULT` clause.


- `IS_NULLABLE`


The column nullability. The value is `YES` if
`NULL` values can be stored in the column,
`NO` if not.


- `DATA_TYPE`


The column data type.



The `DATA_TYPE` value is the type name only
with no other information. The `COLUMN_TYPE`
value contains the type name and possibly other information
such as the precision or length.


- `CHARACTER_MAXIMUM_LENGTH`


For string columns, the maximum length in characters.


- `CHARACTER_OCTET_LENGTH`


For string columns, the maximum length in bytes.


- `NUMERIC_PRECISION`


For numeric columns, the numeric precision.


- `NUMERIC_SCALE`


For numeric columns, the numeric scale.


- `DATETIME_PRECISION`


For temporal columns, the fractional seconds precision.


- `CHARACTER_SET_NAME`


For character string columns, the character set name.


- `COLLATION_NAME`


For character string columns, the collation name.


- `COLUMN_TYPE`


The column data type.



The `DATA_TYPE` value is the type name only
with no other information. The `COLUMN_TYPE`
value contains the type name and possibly other information
such as the precision or length.


- `COLUMN_KEY`


Whether the column is indexed:




- If `COLUMN_KEY` is empty, the column
either is not indexed or is indexed only as a secondary
column in a multiple-column, nonunique index.


- If `COLUMN_KEY` is
`PRI`, the column is a `PRIMARY
                KEY` or is one of the columns in a
multiple-column `PRIMARY KEY`.


- If `COLUMN_KEY` is
`UNI`, the column is the first column of
a `UNIQUE` index. (A
`UNIQUE` index permits multiple
`NULL` values, but you can tell whether
the column permits `NULL` by checking the
`Null` column.)


- If `COLUMN_KEY` is
`MUL`, the column is the first column of
a nonunique index in which multiple occurrences of a given
value are permitted within the column.


If more than one of the `COLUMN_KEY` values
applies to a given column of a table,
`COLUMN_KEY` displays the one with the
highest priority, in the order `PRI`,
`UNI`, `MUL`.


A `UNIQUE` index may be displayed as
`PRI` if it cannot contain
`NULL` values and there is no
`PRIMARY KEY` in the table. A
`UNIQUE` index may display as
`MUL` if several columns form a composite
`UNIQUE` index; although the combination of
the columns is unique, each column can still hold multiple
occurrences of a given value.


- `EXTRA`


Any additional information that is available about a given
column. The value is nonempty in these cases:




- `auto_increment` for columns that have
the `AUTO_INCREMENT` attribute.


- `on update CURRENT_TIMESTAMP` for
[`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") or
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") columns that have
the `ON UPDATE CURRENT_TIMESTAMP`
attribute.


- `STORED GENERATED` or `VIRTUAL
                GENERATED` for generated columns.


- `DEFAULT_GENERATED` for columns that have
an expression default value.


- `PRIVILEGES`


The privileges you have for the column.


- `COLUMN_COMMENT`


Any comment included in the column definition.


- `GENERATION_EXPRESSION`


For generated columns, displays the expression used to compute
column values. Empty for nongenerated columns. For information
about generated columns, see
[Section 15.1.20.8, “CREATE TABLE and Generated Columns”](https://dev.mysql.com/doc/refman/8.0/en/create-table-generated-columns.html "15.1.20.8 CREATE TABLE and Generated Columns").


- `SRS_ID`


This value applies to spatial columns. It contains the column
`SRID` value that indicates the spatial
reference system for values stored in the column. See
[Section 13.4.1, “Spatial Data Types”](https://dev.mysql.com/doc/refman/8.0/en/spatial-type-overview.html "13.4.1 Spatial Data Types"), and
[Section 13.4.5, “Spatial Reference System Support”](https://dev.mysql.com/doc/refman/8.0/en/spatial-reference-systems.html "13.4.5 Spatial Reference System Support"). The value is
`NULL` for nonspatial columns and spatial
columns with no `SRID` attribute.


#### Notes

- In [`SHOW COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "15.7.7.5 SHOW COLUMNS Statement"), the
`Type` display includes values from several
different [`COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html "28.3.8 The INFORMATION_SCHEMA COLUMNS Table") columns.


- `CHARACTER_OCTET_LENGTH` should be the same
as `CHARACTER_MAXIMUM_LENGTH`, except for
multibyte character sets.


- `CHARACTER_SET_NAME` can be derived from
`COLLATION_NAME`. For example, if you say
`SHOW FULL COLUMNS FROM t`, and you see in
the `COLLATION_NAME` column a value of
`utf8mb4_swedish_ci`, the character set is
what appears before the first underscore:
`utf8mb4`.


Column information is also available from the
[`SHOW COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "15.7.7.5 SHOW COLUMNS Statement") statement. See
[Section 15.7.7.5, “SHOW COLUMNS Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "15.7.7.5 SHOW COLUMNS Statement"). The following statements are
nearly equivalent:


```sql
SELECT COLUMN_NAME, DATA_TYPE, IS_NULLABLE, COLUMN_DEFAULT
  FROM INFORMATION_SCHEMA.COLUMNS
  WHERE table_name = 'tbl_name'
  [AND table_schema = 'db_name']
  [AND column_name LIKE 'wild']

SHOW COLUMNS
  FROM tbl_name
  [FROM db_name]
  [LIKE 'wild']
```

In MySQL 8.0.30 and later, information about generated invisible
primary key columns is visible in this table by default. You can
cause such information to be hidden by setting
[`show_gipk_in_create_table_and_information_schema\\
      = OFF`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_show_gipk_in_create_table_and_information_schema). For more information, see
[Section 15.1.20.11, “Generated Invisible Primary Keys”](https://dev.mysql.com/doc/refman/8.0/en/create-table-gipks.html "15.1.20.11 Generated Invisible Primary Keys").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/information-schema-collation-character-set-applicability-table.html "Previous: The INFORMATION_SCHEMA COLLATION_CHARACTER_SET_APPLICABILITY Table") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/general-information-schema-tables.html "Up: INFORMATION_SCHEMA General Tables") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-extensions-table.html "Next: The INFORMATION_SCHEMA COLUMNS_EXTENSIONS Table")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html)

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