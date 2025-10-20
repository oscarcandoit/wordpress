---
url: https://dev.mysql.com/doc/refman/8.0/en/replace.html
scraped_at: 2025-10-20T03:11:11.864Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/replace.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/replace.html "Hide Sidebar")

[Previous: Parenthesized Query Expressions](https://dev.mysql.com/doc/refman/8.0/en/parenthesized-query-expressions.html "Previous: Parenthesized Query Expressions")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Up: Data Manipulation Statements")[Next: SELECT Statement](https://dev.mysql.com/doc/refman/8.0/en/select.html "Next: SELECT Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/replace.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/replace.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/replace.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/replace.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/replace.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/replace.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/replace.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/replace.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/replace.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/replace.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/replace.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/replace.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/replace.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/replace.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html)  /

REPLACE Statement


### 15.2.12 REPLACE Statement

``` sql

REPLACE [LOW_PRIORITY | DELAYED]
    [INTO] tbl_name
    [PARTITION (partition_name [, partition_name] ...)]
    [(col_name [, col_name] ...)]
    { {VALUES | VALUE} (value_list) [, (value_list)] ...
      |
      VALUES row_constructor_list
    }

REPLACE [LOW_PRIORITY | DELAYED]
    [INTO] tbl_name
    [PARTITION (partition_name [, partition_name] ...)]
    SET assignment_list

REPLACE [LOW_PRIORITY | DELAYED]
    [INTO] tbl_name
    [PARTITION (partition_name [, partition_name] ...)]
    [(col_name [, col_name] ...)]
    {SELECT ... | TABLE table_name}

value:
    {expr | DEFAULT}

value_list:
    value [, value] ...

row_constructor_list:
    ROW(value_list)[, ROW(value_list)][, ...]

assignment:
    col_name = value

assignment_list:
    assignment [, assignment] ...
```

[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") works exactly like
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"), except that if an old row
in the table has the same value as a new row for a
`PRIMARY KEY` or a `UNIQUE`
index, the old row is deleted before the new row is inserted. See
[Section 15.2.7, “INSERT Statement”](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement").


[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") is a MySQL extension to the
SQL standard. It either inserts, or _deletes_
and inserts. For another MySQL extension to standard
SQL—that either inserts or
_updates_—see
[Section 15.2.7.2, “INSERT ... ON DUPLICATE KEY UPDATE Statement”](https://dev.mysql.com/doc/refman/8.0/en/insert-on-duplicate.html "15.2.7.2 INSERT ... ON DUPLICATE KEY UPDATE Statement").


`DELAYED` inserts and replaces were deprecated in
MySQL 5.6. In MySQL 8.0, `DELAYED`
is not supported. The server recognizes but ignores the
`DELAYED` keyword, handles the replace as a
nondelayed replace, and generates an
[`ER_WARN_LEGACY_SYNTAX_CONVERTED`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_warn_legacy_syntax_converted)
warning: REPLACE DELAYED is no longer supported. The
statement was converted to REPLACE. The
`DELAYED` keyword is scheduled for removal in a
future release. release.

Note

[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") makes sense only if a
table has a `PRIMARY KEY` or
`UNIQUE` index. Otherwise, it becomes
equivalent to [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"), because
there is no index to be used to determine whether a new row
duplicates another.

Values for all columns are taken from the values specified in the
[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") statement. Any missing
columns are set to their default values, just as happens for
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"). You cannot refer to values
from the current row and use them in the new row. If you use an
assignment such as `SET
      col_name =
      col_name + 1`, the reference
to the column name on the right hand side is treated as
[`DEFAULT(col_name)`](https://dev.mysql.com/doc/refman/8.0/en/miscellaneous-functions.html#function_default),
so the assignment is equivalent to `SET
      col_name =
      DEFAULT(col_name) + 1`.


In MySQL 8.0.19 and later, you can specify the column values that
`REPLACE` attempts to insert using
[`VALUES ROW()`](https://dev.mysql.com/doc/refman/8.0/en/values.html "15.2.19 VALUES Statement").


To use [`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement"), you must have both
the [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_insert) and
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_delete) privileges for the table.


If a generated column is replaced explicitly, the only permitted
value is `DEFAULT`. For information about
generated columns, see
[Section 15.1.20.8, “CREATE TABLE and Generated Columns”](https://dev.mysql.com/doc/refman/8.0/en/create-table-generated-columns.html "15.1.20.8 CREATE TABLE and Generated Columns").


`REPLACE` supports explicit partition selection
using the `PARTITION` clause with a list of
comma-separated names of partitions, subpartitions, or both. As
with [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"), if it is not possible
to insert the new row into any of these partitions or
subpartitions, the `REPLACE` statement fails with
the error Found a row not matching the given partition
set. For more information and examples, see
[Section 26.5, “Partition Selection”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-selection.html "26.5 Partition Selection").


The [`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") statement returns a
count to indicate the number of rows affected. This is the sum of
the rows deleted and inserted. If the count is 1 for a single-row
[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement"), a row was inserted and no
rows were deleted. If the count is greater than 1, one or more old
rows were deleted before the new row was inserted. It is possible
for a single row to replace more than one old row if the table
contains multiple unique indexes and the new row duplicates values
for different old rows in different unique indexes.


The affected-rows count makes it easy to determine whether
[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") only added a row or whether
it also replaced any rows: Check whether the count is 1 (added) or
greater (replaced).


If you are using the C API, the affected-rows count can be
obtained using the
[`mysql_affected_rows()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-affected-rows.html) function.


You cannot replace into a table and select from the same table in
a subquery.


MySQL uses the following algorithm for
[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") (and
[`LOAD DATA ...\\
      REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement")):

1. Try to insert the new row into the table


2. While the insertion fails because a duplicate-key error occurs
    for a primary key or unique index:




1. Delete from the table the conflicting row that has the
    duplicate key value


2. Try again to insert the new row into the table


It is possible that in the case of a duplicate-key error, a
storage engine may perform the `REPLACE` as an
update rather than a delete plus insert, but the semantics are the
same. There are no user-visible effects other than a possible
difference in how the storage engine increments
`Handler_xxx` status
variables.


Because the results of `REPLACE ... SELECT`
statements depend on the ordering of rows from the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") and this order cannot always
be guaranteed, it is possible when logging these statements for
the source and the replica to diverge. For this reason,
`REPLACE ... SELECT` statements are flagged as
unsafe for statement-based replication. such statements produce a
warning in the error log when using statement-based mode and are
written to the binary log using the row-based format when using
`MIXED` mode. See also
[Section 19.2.1.1, “Advantages and Disadvantages of Statement-Based and Row-Based\\
Replication”](https://dev.mysql.com/doc/refman/8.0/en/replication-sbr-rbr.html "19.2.1.1 Advantages and Disadvantages of Statement-Based and Row-Based Replication").


MySQL 8.0.19 and later supports
[`TABLE`](https://dev.mysql.com/doc/refman/8.0/en/table.html "15.2.16 TABLE Statement") as well as
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") with
`REPLACE`, just as it does with
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"). See
[Section 15.2.7.1, “INSERT ... SELECT Statement”](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement"), for more information and
examples.


When modifying an existing table that is not partitioned to
accommodate partitioning, or, when modifying the partitioning of
an already partitioned table, you may consider altering the
table's primary key (see
[Section 26.6.1, “Partitioning Keys, Primary Keys, and Unique Keys”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-limitations-partitioning-keys-unique-keys.html "26.6.1 Partitioning Keys, Primary Keys, and Unique Keys")).
You should be aware that, if you do this, the results of
`REPLACE` statements may be affected, just as
they would be if you modified the primary key of a nonpartitioned
table. Consider the table created by the following
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement:


``` sql

CREATE TABLE test (
  id INT UNSIGNED NOT NULL AUTO_INCREMENT,
  data VARCHAR(64) DEFAULT NULL,
  ts TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (id)
);
```

When we create this table and run the statements shown in the
mysql client, the result is as follows:


``` sql

mysql> REPLACE INTO test VALUES (1, 'Old', '2014-08-20 18:47:00');
Query OK, 1 row affected (0.04 sec)

mysql> REPLACE INTO test VALUES (1, 'New', '2014-08-20 18:47:42');
Query OK, 2 rows affected (0.04 sec)

mysql> SELECT * FROM test;
+----+------+---------------------+
| id | data | ts                  |
+----+------+---------------------+
|  1 | New  | 2014-08-20 18:47:42 |
+----+------+---------------------+
1 row in set (0.00 sec)
```

Now we create a second table almost identical to the first, except
that the primary key now covers 2 columns, as shown here
(emphasized text):


``` sql

CREATE TABLE test2 (
  id INT UNSIGNED NOT NULL AUTO_INCREMENT,
  data VARCHAR(64) DEFAULT NULL,
  ts TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (id, ts)
);
```

When we run on `test2` the same two
`REPLACE` statements as we did on the original
`test` table, we obtain a different result:


``` sql

mysql> REPLACE INTO test2 VALUES (1, 'Old', '2014-08-20 18:47:00');
Query OK, 1 row affected (0.05 sec)

mysql> REPLACE INTO test2 VALUES (1, 'New', '2014-08-20 18:47:42');
Query OK, 1 row affected (0.06 sec)

mysql> SELECT * FROM test2;
+----+------+---------------------+
| id | data | ts                  |
+----+------+---------------------+
|  1 | Old  | 2014-08-20 18:47:00 |
|  1 | New  | 2014-08-20 18:47:42 |
+----+------+---------------------+
2 rows in set (0.00 sec)
```

This is due to the fact that, when run on
`test2`, both the `id` and
`ts` column values must match those of an
existing row for the row to be replaced; otherwise, a row is
inserted.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/parenthesized-query-expressions.html "Previous: Parenthesized Query Expressions") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Up: Data Manipulation Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/select.html "Next: SELECT Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/replace.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/replace.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/replace.html)

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