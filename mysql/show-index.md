---
url: https://dev.mysql.com/doc/refman/8.0/en/show-index.html
scraped_at: 2025-10-20T03:06:36.264Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/show-index.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "Hide Sidebar")

[Previous: SHOW GRANTS Statement](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "Previous: SHOW GRANTS Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements")[Next: SHOW MASTER STATUS Statement](https://dev.mysql.com/doc/refman/8.0/en/show-master-status.html "Next: SHOW MASTER STATUS Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-index.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-index.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-index.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/show-index.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/show-index.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/show-index.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/show-index.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/show-index.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/show-index.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/show-index.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/show-index.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/show-index.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/show-index.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)  /

SHOW INDEX Statement


#### 15.7.7.22 SHOW INDEX Statement

```sql
SHOW [EXTENDED] {INDEX | INDEXES | KEYS}
    {FROM | IN} tbl_name
    [{FROM | IN} db_name]
    [WHERE expr]
```

[`SHOW INDEX`](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "15.7.7.22 SHOW INDEX Statement") returns table index
information. The format resembles that of the
`SQLStatistics` call in ODBC. This statement
requires some privilege for any column in the table.


```sql
mysql> SHOW INDEX FROM City\G
*************************** 1. row ***************************
        Table: city
   Non_unique: 0
     Key_name: PRIMARY
 Seq_in_index: 1
  Column_name: ID
    Collation: A
  Cardinality: 4188
     Sub_part: NULL
       Packed: NULL
         Null:
   Index_type: BTREE
      Comment:
Index_comment:
      Visible: YES
   Expression: NULL
*************************** 2. row ***************************
        Table: city
   Non_unique: 1
     Key_name: CountryCode
 Seq_in_index: 1
  Column_name: CountryCode
    Collation: A
  Cardinality: 232
     Sub_part: NULL
       Packed: NULL
         Null:
   Index_type: BTREE
      Comment:
Index_comment:
      Visible: YES
   Expression: NULL
```

An alternative to `tbl_name
        FROM db_name` syntax is
_`db_name`_. _`tbl_name`_.
These two statements are equivalent:


```sql
SHOW INDEX FROM mytable FROM mydb;
SHOW INDEX FROM mydb.mytable;
```

The optional `EXTENDED` keyword causes the
output to include information about hidden indexes that MySQL
uses internally and are not accessible by users.


The `WHERE` clause can be given to select rows
using more general conditions, as discussed in
[Section 28.8, “Extensions to SHOW Statements”](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html "28.8 Extensions to SHOW Statements").


[`SHOW INDEX`](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "15.7.7.22 SHOW INDEX Statement") returns the following
fields:

- `Table`


The name of the table.


- `Non_unique`


0 if the index cannot contain duplicates, 1 if it can.


- `Key_name`


The name of the index. If the index is the primary key, the
name is always `PRIMARY`.


- `Seq_in_index`


The column sequence number in the index, starting with 1.


- `Column_name`


The column name. See also the description for the
`Expression` column.


- `Collation`


How the column is sorted in the index. This can have values
`A` (ascending), `D`
(descending), or `NULL` (not sorted).


- `Cardinality`


An estimate of the number of unique values in the index. To
update this number, run [`ANALYZE\\
              TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") or (for `MyISAM` tables)
[**myisamchk -a**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility").


`Cardinality` is counted based on
statistics stored as integers, so the value is not
necessarily exact even for small tables. The higher the
cardinality, the greater the chance that MySQL uses the
index when doing joins.


- `Sub_part`


The index prefix. That is, the number of indexed characters
if the column is only partly indexed,
`NULL` if the entire column is indexed.





Note





Prefix _limits_ are measured in bytes.
However, prefix _lengths_ for index
specifications in [`CREATE\\
                TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"), [`ALTER\\
                TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement"), and [`CREATE\\
                INDEX`](https://dev.mysql.com/doc/refman/8.0/en/create-index.html "15.1.15 CREATE INDEX Statement") statements are interpreted as number of
characters for nonbinary string types
( [`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types")) and number of bytes
for binary string types
( [`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"),
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"),
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types")). Take this into
account when specifying a prefix length for a nonbinary
string column that uses a multibyte character set.





For additional information about index prefixes, see
[Section 10.3.5, “Column Indexes”](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html "10.3.5 Column Indexes"), and
[Section 15.1.15, “CREATE INDEX Statement”](https://dev.mysql.com/doc/refman/8.0/en/create-index.html "15.1.15 CREATE INDEX Statement").


- `Packed`


Indicates how the key is packed. `NULL` if
it is not.


- `Null`


Contains `YES` if the column may contain
`NULL` values and `''` if
not.


- `Index_type`


The index method used ( `BTREE`,
`FULLTEXT`, `HASH`,
`RTREE`).


- `Comment`


Information about the index not described in its own column,
such as `disabled` if the index is
disabled.


- `Index_comment`


Any comment provided for the index with a
`COMMENT` attribute when the index was
created.


- `Visible`


Whether the index is visible to the optimizer. See
[Section 10.3.12, “Invisible Indexes”](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html "10.3.12 Invisible Indexes").


- `Expression`


MySQL 8.0.13 and higher supports functional key parts (see
[Functional Key Parts](https://dev.mysql.com/doc/refman/8.0/en/create-index.html#create-index-functional-key-parts "Functional Key Parts")), which
affects both the `Column_name` and
`Expression` columns:




- For a nonfunctional key part,
`Column_name` indicates the column
indexed by the key part and
`Expression` is
`NULL`.


- For a functional key part,
`Column_name` column is
`NULL` and
`Expression` indicates the expression
for the key part.


Information about table indexes is also available from the
`INFORMATION_SCHEMA` [`STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html "28.3.34 The INFORMATION_SCHEMA STATISTICS Table") table. See
[Section 28.3.34, “The INFORMATION\_SCHEMA STATISTICS Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html "28.3.34 The INFORMATION_SCHEMA STATISTICS Table"). The
extended information about hidden indexes is available only
using `SHOW EXTENDED INDEX`; it cannot be
obtained from the [`STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html "28.3.34 The INFORMATION_SCHEMA STATISTICS Table") table.


You can list a table's indexes with the [**mysqlshow -k**\\
**_`db_name`_ _`tbl_name`_**](https://dev.mysql.com/doc/refman/8.0/en/mysqlshow.html "6.5.7 mysqlshow — Display Database, Table, and Column Information") command.


In MySQL 8.0.30 and later, `SHOW INDEX`
includes the table's generated invisible key, if it has
one, by default. You can cause this information to be suppressed
in the statement's output by setting
[`show_gipk_in_create_table_and_information_schema\\
        = OFF`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_show_gipk_in_create_table_and_information_schema). For more information, see
[Section 15.1.20.11, “Generated Invisible Primary Keys”](https://dev.mysql.com/doc/refman/8.0/en/create-table-gipks.html "15.1.20.11 Generated Invisible Primary Keys").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "Previous: SHOW GRANTS Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/show-master-status.html "Next: SHOW MASTER STATUS Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-index.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-index.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-index.html)

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