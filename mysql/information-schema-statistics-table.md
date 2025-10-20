---
url: https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html
scraped_at: 2025-10-20T03:07:22.707Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html "Hide Sidebar")

[Previous: The INFORMATION_SCHEMA SCHEMA_PRIVILEGES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-schema-privileges-table.html "Previous: The INFORMATION_SCHEMA SCHEMA_PRIVILEGES Table")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: INFORMATION_SCHEMA General Tables](https://dev.mysql.com/doc/refman/8.0/en/general-information-schema-tables.html "Up: INFORMATION_SCHEMA General Tables")[Next: The INFORMATION_SCHEMA ST_GEOMETRY_COLUMNS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-st-geometry-columns-table.html "Next: The INFORMATION_SCHEMA ST_GEOMETRY_COLUMNS Table")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/information-schema-statistics-table.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/information-schema-statistics-table.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/information-schema-statistics-table.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/information-schema-statistics-table.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/information-schema-statistics-table.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/information-schema-statistics-table.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/information-schema-statistics-table.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/information-schema-statistics-table.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html)  / [INFORMATION\_SCHEMA Tables](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)  /
[INFORMATION\_SCHEMA General Tables](https://dev.mysql.com/doc/refman/8.0/en/general-information-schema-tables.html)  /

The INFORMATION\_SCHEMA STATISTICS Table


### 28.3.34 The INFORMATION\_SCHEMA STATISTICS Table

The [`STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html "28.3.34 The INFORMATION_SCHEMA STATISTICS Table") table provides
information about table indexes.


Columns in [`STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html "28.3.34 The INFORMATION_SCHEMA STATISTICS Table") that represent
table statistics hold cached values. The
[`information_schema_stats_expiry`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_information_schema_stats_expiry)
system variable defines the period of time before cached table
statistics expire. The default is 86400 seconds (24 hours). If
there are no cached statistics or statistics have expired,
statistics are retrieved from storage engines when querying table
statistics columns. To update cached values at any time for a
given table, use [`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement"). To
always retrieve the latest statistics directly from storage
engines, set
[`information_schema_stats_expiry=0`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_information_schema_stats_expiry).
For more information, see
[Section 10.2.3, “Optimizing INFORMATION\_SCHEMA Queries”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html "10.2.3 Optimizing INFORMATION_SCHEMA Queries").

Note

If the [`innodb_read_only`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_read_only) system
variable is enabled, [`ANALYZE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") may fail because it cannot update statistics
tables in the data dictionary, which use
`InnoDB`. For [`ANALYZE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") operations that update the key distribution,
failure may occur even if the operation updates the table itself
(for example, if it is a `MyISAM` table). To
obtain the updated distribution statistics, set
[`information_schema_stats_expiry=0`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_information_schema_stats_expiry).

The [`STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html "28.3.34 The INFORMATION_SCHEMA STATISTICS Table") table has these
columns:

- `TABLE_CATALOG`


The name of the catalog to which the table containing the
index belongs. This value is always `def`.


- `TABLE_SCHEMA`


The name of the schema (database) to which the table
containing the index belongs.


- `TABLE_NAME`


The name of the table containing the index.


- `NON_UNIQUE`


0 if the index cannot contain duplicates, 1 if it can.


- `INDEX_SCHEMA`


The name of the schema (database) to which the index belongs.


- `INDEX_NAME`


The name of the index. If the index is the primary key, the
name is always `PRIMARY`.


- `SEQ_IN_INDEX`


The column sequence number in the index, starting with 1.


- `COLUMN_NAME`


The column name. See also the description for the
`EXPRESSION` column.


- `COLLATION`


How the column is sorted in the index. This can have values
`A` (ascending), `D`
(descending), or `NULL` (not sorted).


- `CARDINALITY`


An estimate of the number of unique values in the index. To
update this number, run [`ANALYZE\\
            TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") or (for `MyISAM` tables)
[**myisamchk -a**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility").


`CARDINALITY` is counted based on statistics
stored as integers, so the value is not necessarily exact even
for small tables. The higher the cardinality, the greater the
chance that MySQL uses the index when doing joins.


- `SUB_PART`


The index prefix. That is, the number of indexed characters if
the column is only partly indexed, `NULL` if
the entire column is indexed.





Note





Prefix _limits_ are measured in bytes.
However, prefix _lengths_ for index
specifications in [`CREATE\\
              TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"), [`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement"),
and [`CREATE INDEX`](https://dev.mysql.com/doc/refman/8.0/en/create-index.html "15.1.15 CREATE INDEX Statement") statements
are interpreted as number of characters for nonbinary string
types ( [`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types")) and number of bytes for
binary string types ( [`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"),
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"),
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types")). Take this into account
when specifying a prefix length for a nonbinary string
column that uses a multibyte character set.





For additional information about index prefixes, see
[Section 10.3.5, “Column Indexes”](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html "10.3.5 Column Indexes"), and
[Section 15.1.15, “CREATE INDEX Statement”](https://dev.mysql.com/doc/refman/8.0/en/create-index.html "15.1.15 CREATE INDEX Statement").


- `PACKED`


Indicates how the key is packed. `NULL` if it
is not.


- `NULLABLE`


Contains `YES` if the column may contain
`NULL` values and `''` if
not.


- `INDEX_TYPE`


The index method used ( `BTREE`,
`FULLTEXT`, `HASH`,
`RTREE`).


- `COMMENT`


Information about the index not described in its own column,
such as `disabled` if the index is disabled.


- `INDEX_COMMENT`


Any comment provided for the index with a
`COMMENT` attribute when the index was
created.


- `IS_VISIBLE`


Whether the index is visible to the optimizer. See
[Section 10.3.12, “Invisible Indexes”](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html "10.3.12 Invisible Indexes").


- `EXPRESSION`


MySQL 8.0.13 and higher supports functional key parts (see
[Functional Key Parts](https://dev.mysql.com/doc/refman/8.0/en/create-index.html#create-index-functional-key-parts "Functional Key Parts")), which
affects both the `COLUMN_NAME` and
`EXPRESSION` columns:




- For a nonfunctional key part,
`COLUMN_NAME` indicates the column
indexed by the key part and `EXPRESSION`
is `NULL`.


- For a functional key part, `COLUMN_NAME`
column is `NULL` and
`EXPRESSION` indicates the expression for
the key part.


#### Notes

- There is no standard `INFORMATION_SCHEMA`
table for indexes. The MySQL column list is similar to what
SQL Server 2000 returns for `sp_statistics`,
except that `QUALIFIER` and
`OWNER` are replaced with
`CATALOG` and `SCHEMA`,
respectively.


Information about table indexes is also available from the
[`SHOW INDEX`](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "15.7.7.22 SHOW INDEX Statement") statement. See
[Section 15.7.7.22, “SHOW INDEX Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "15.7.7.22 SHOW INDEX Statement"). The following statements are
equivalent:


```sql
SELECT * FROM INFORMATION_SCHEMA.STATISTICS
  WHERE table_name = 'tbl_name'
  AND table_schema = 'db_name'

SHOW INDEX
  FROM tbl_name
  FROM db_name
```

In MySQL 8.0.30 and later, information about generated invisible
primary key columns is visible in this table by default. You can
cause such information to be hidden by setting
[`show_gipk_in_create_table_and_information_schema\\
      = OFF`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_show_gipk_in_create_table_and_information_schema). For more information, see
[Section 15.1.20.11, “Generated Invisible Primary Keys”](https://dev.mysql.com/doc/refman/8.0/en/create-table-gipks.html "15.1.20.11 Generated Invisible Primary Keys").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/information-schema-schema-privileges-table.html "Previous: The INFORMATION_SCHEMA SCHEMA_PRIVILEGES Table") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/general-information-schema-tables.html "Up: INFORMATION_SCHEMA General Tables") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/information-schema-st-geometry-columns-table.html "Next: The INFORMATION_SCHEMA ST_GEOMETRY_COLUMNS Table")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html)

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