---
url: https://dev.mysql.com/doc/refman/8.0/en/insert.html
scraped_at: 2025-10-20T02:58:33.719Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/insert.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/insert.html "Hide Sidebar")

[Previous: IMPORT TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/import-table.html "Previous: IMPORT TABLE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Up: Data Manipulation Statements")[Next: INSERT ... SELECT Statement](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "Next: INSERT ... SELECT Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/insert.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/insert.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/insert.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/insert.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/insert.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/insert.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/insert.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/insert.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/insert.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/insert.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/insert.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/insert.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/insert.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/insert.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html)  /

INSERT Statement


### 15.2.7 INSERT Statement

[15.2.7.1 INSERT ... SELECT Statement](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html)[15.2.7.2 INSERT ... ON DUPLICATE KEY UPDATE Statement](https://dev.mysql.com/doc/refman/8.0/en/insert-on-duplicate.html)[15.2.7.3 INSERT DELAYED Statement](https://dev.mysql.com/doc/refman/8.0/en/insert-delayed.html)

```sql
INSERT [LOW_PRIORITY | DELAYED | HIGH_PRIORITY] [IGNORE]
    [INTO] tbl_name
    [PARTITION (partition_name [, partition_name] ...)]
    [(col_name [, col_name] ...)]
    { {VALUES | VALUE} (value_list) [, (value_list)] ... }
    [AS row_alias[(col_alias [, col_alias] ...)]]
    [ON DUPLICATE KEY UPDATE assignment_list]

INSERT [LOW_PRIORITY | DELAYED | HIGH_PRIORITY] [IGNORE]
    [INTO] tbl_name
    [PARTITION (partition_name [, partition_name] ...)]
    SET assignment_list
    [AS row_alias[(col_alias [, col_alias] ...)]]
    [ON DUPLICATE KEY UPDATE assignment_list]

INSERT [LOW_PRIORITY | HIGH_PRIORITY] [IGNORE]
    [INTO] tbl_name
    [PARTITION (partition_name [, partition_name] ...)]
    [(col_name [, col_name] ...)]
    { SELECT ...
      | TABLE table_name
      | VALUES row_constructor_list
    }
    [ON DUPLICATE KEY UPDATE assignment_list]

value:
    {expr | DEFAULT}

value_list:
    value [, value] ...

row_constructor_list:
    ROW(value_list)[, ROW(value_list)][, ...]

assignment:
    col_name =
          value
        | [row_alias.]col_name
        | [tbl_name.]col_name
        | [row_alias.]col_alias

assignment_list:
    assignment [, assignment] ...
```

[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") inserts new rows into an
existing table. The [`INSERT\\
      ... VALUES`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"),
[`INSERT ... VALUES\\
      ROW()`](https://dev.mysql.com/doc/refman/8.0/en/values.html "15.2.19 VALUES Statement"), and
[`INSERT ... SET`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement")
forms of the statement insert rows based on explicitly specified
values. The [`INSERT\\
      ... SELECT`](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement") form inserts rows selected from another table
or tables. You can also use
[`INSERT ... TABLE`](https://dev.mysql.com/doc/refman/8.0/en/table.html "15.2.16 TABLE Statement")
in MySQL 8.0.19 and later to insert rows from a single table.
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") with an `ON
      DUPLICATE KEY UPDATE` clause enables existing rows to be
updated if a row to be inserted would cause a duplicate value in a
`UNIQUE` index or `PRIMARY KEY`.
In MySQL 8.0.19 and later, a row alias with one or more optional
column aliases can be used with `ON DUPLICATE KEY
      UPDATE` to refer to the row to be inserted.


For additional information about
[`INSERT ...\\
      SELECT`](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement") and
[`INSERT ... ON\\
      DUPLICATE KEY UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/insert-on-duplicate.html "15.2.7.2 INSERT ... ON DUPLICATE KEY UPDATE Statement"), see
[Section 15.2.7.1, “INSERT ... SELECT Statement”](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement"), and
[Section 15.2.7.2, “INSERT ... ON DUPLICATE KEY UPDATE Statement”](https://dev.mysql.com/doc/refman/8.0/en/insert-on-duplicate.html "15.2.7.2 INSERT ... ON DUPLICATE KEY UPDATE Statement").


In MySQL 8.0, the `DELAYED` keyword
is accepted but ignored by the server. For the reasons for this,
see [Section 15.2.7.3, “INSERT DELAYED Statement”](https://dev.mysql.com/doc/refman/8.0/en/insert-delayed.html "15.2.7.3 INSERT DELAYED Statement"),


Inserting into a table requires the
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_insert) privilege for the table. If
the `ON DUPLICATE KEY UPDATE` clause is used and
a duplicate key causes an [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") to
be performed instead, the statement requires the
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_update) privilege for the columns to
be updated. For columns that are read but not modified you need
only the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege (such as
for a column referenced only on the right hand side of an
_`col_name`_ = _`expr`_
assignment in an `ON DUPLICATE KEY UPDATE`
clause).


When inserting into a partitioned table, you can control which
partitions and subpartitions accept new rows. The
`PARTITION` clause takes a list of the
comma-separated names of one or more partitions or subpartitions
(or both) of the table. If any of the rows to be inserted by a
given [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement do not match
one of the partitions listed, the
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement fails with the
error Found a row not matching the given partition
set. For more information and examples, see
[Section 26.5, “Partition Selection”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-selection.html "26.5 Partition Selection").


_`tbl_name`_ is the table into which rows
should be inserted. Specify the columns for which the statement
provides values as follows:

- Provide a parenthesized list of comma-separated column names
following the table name. In this case, a value for each named
column must be provided by the `VALUES` list,
[`VALUES ROW()`](https://dev.mysql.com/doc/refman/8.0/en/values.html "15.2.19 VALUES Statement")
list, or [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement. For
the `INSERT TABLE` form, the number of
columns in the source table must match the number of columns
to be inserted.


- If you do not specify a list of column names for
[`INSERT ...\\
            VALUES`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") or
[`INSERT ...\\
            SELECT`](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement"), values for every column in the table must be
provided by the `VALUES` list,
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement, or
[`TABLE`](https://dev.mysql.com/doc/refman/8.0/en/table.html "15.2.16 TABLE Statement") statement. If you do not
know the order of the columns in the table, use
`DESCRIBE
            tbl_name` to find out.


- A `SET` clause indicates columns explicitly
by name, together with the value to assign each one.


Column values can be given in several ways:

- If strict SQL mode is not enabled, any column not explicitly
given a value is set to its default (explicit or implicit)
value. For example, if you specify a column list that does not
name all the columns in the table, unnamed columns are set to
their default values. Default value assignment is described in
[Section 13.6, “Data Type Default Values”](https://dev.mysql.com/doc/refman/8.0/en/data-type-defaults.html "13.6 Data Type Default Values"). See also
[Section 1.6.3.3, “Enforced Constraints on Invalid Data”](https://dev.mysql.com/doc/refman/8.0/en/constraint-invalid-data.html "1.6.3.3 Enforced Constraints on Invalid Data").



If strict SQL mode is enabled, an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement generates an
error if it does not specify an explicit value for every
column that has no default value. See
[Section 7.1.11, “Server SQL Modes”](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html "7.1.11 Server SQL Modes").


- If both the column list and the `VALUES` list
are empty, [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") creates a row
with each column set to its default value:



```sql
INSERT INTO tbl_name () VALUES();
```



If strict mode is not enabled, MySQL uses the implicit default
value for any column that has no explicitly defined default.
If strict mode is enabled, an error occurs if any column has
no default value.


- Use the keyword `DEFAULT` to set a column
explicitly to its default value. This makes it easier to write
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements that assign
values to all but a few columns, because it enables you to
avoid writing an incomplete `VALUES` list
that does not include a value for each column in the table.
Otherwise, you must provide the list of column names
corresponding to each value in the `VALUES`
list.


- If a generated column is inserted into explicitly, the only
permitted value is `DEFAULT`. For information
about generated columns, see
[Section 15.1.20.8, “CREATE TABLE and Generated Columns”](https://dev.mysql.com/doc/refman/8.0/en/create-table-generated-columns.html "15.1.20.8 CREATE TABLE and Generated Columns").


- In expressions, you can use
[`DEFAULT(col_name)`](https://dev.mysql.com/doc/refman/8.0/en/miscellaneous-functions.html#function_default)
to produce the default value for column
_`col_name`_.


- Type conversion of an expression
_`expr`_ that provides a column value
might occur if the expression data type does not match the
column data type. Conversion of a given value can result in
different inserted values depending on the column type. For
example, inserting the string `'1999.0e-2'`
into an [`INT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT"),
[`FLOAT`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE"),
[`DECIMAL(10,6)`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC"), or
[`YEAR`](https://dev.mysql.com/doc/refman/8.0/en/year.html "13.2.4 The YEAR Type") column inserts the value
`1999`, `19.9921`,
`19.992100`, or `1999`,
respectively. The value stored in the
[`INT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT") and
[`YEAR`](https://dev.mysql.com/doc/refman/8.0/en/year.html "13.2.4 The YEAR Type") columns is
`1999` because the string-to-number
conversion looks only at as much of the initial part of the
string as may be considered a valid integer or year. For the
[`FLOAT`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE") and
[`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC") columns, the
string-to-number conversion considers the entire string a
valid numeric value.


- An expression _`expr`_ can refer to any
column that was set earlier in a value list. For example, you
can do this because the value for `col2`
refers to `col1`, which has previously been
assigned:



```sql
INSERT INTO tbl_name (col1,col2) VALUES(15,col1*2);
```



But the following is not legal, because the value for
`col1` refers to `col2`,
which is assigned after `col1`:



```sql
INSERT INTO tbl_name (col1,col2) VALUES(col2*2,15);
```



An exception occurs for columns that contain
`AUTO_INCREMENT` values. Because
`AUTO_INCREMENT` values are generated after
other value assignments, any reference to an
`AUTO_INCREMENT` column in the assignment
returns a `0`.


[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements that use
`VALUES` syntax can insert multiple rows. To do
this, include multiple lists of comma-separated column values,
with lists enclosed within parentheses and separated by commas.
Example:


```sql
INSERT INTO tbl_name (a,b,c)
    VALUES(1,2,3), (4,5,6), (7,8,9);
```

Each values list must contain exactly as many values as are to be
inserted per row. The following statement is invalid because it
contains one list of nine values, rather than three lists of three
values each:


```sql
INSERT INTO tbl_name (a,b,c) VALUES(1,2,3,4,5,6,7,8,9);
```

`VALUE` is a synonym for
`VALUES` in this context. Neither implies
anything about the number of values lists, nor about the number of
values per list. Either may be used whether there is a single
values list or multiple lists, and regardless of the number of
values per list.


[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements using
[`VALUES ROW()`](https://dev.mysql.com/doc/refman/8.0/en/values.html "15.2.19 VALUES Statement")
syntax can also insert multiple rows. In this case, each value
list must be contained within a `ROW()` (row
constructor), like this:


```sql
INSERT INTO tbl_name (a,b,c)
    VALUES ROW(1,2,3), ROW(4,5,6), ROW(7,8,9);
```

The affected-rows value for an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") can be obtained using the
[`ROW_COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_row-count) SQL function or the
[`mysql_affected_rows()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-affected-rows.html) C API
function. See [Section 14.15, “Information Functions”](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html "14.15 Information Functions"), and
[mysql\_affected\_rows()](https://dev.mysql.com/doc/c-api/8.0/en/mysql-affected-rows.html).


If you use [`INSERT ...\\
      VALUES`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") or `INSERT ... VALUES ROW()`
with multiple value lists, or
[`INSERT ...\\
      SELECT`](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement") or `INSERT ... TABLE`, the
statement returns an information string in this format:


```none
Records: N1 Duplicates: N2 Warnings: N3
```

If you are using the C API, the information string can be obtained
by invoking the [`mysql_info()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-info.html)
function. See [mysql\_info()](https://dev.mysql.com/doc/c-api/8.0/en/mysql-info.html).


`Records` indicates the number of rows processed
by the statement. (This is not necessarily the number of rows
actually inserted because `Duplicates` can be
nonzero.) `Duplicates` indicates the number of
rows that could not be inserted because they would duplicate some
existing unique index value. `Warnings` indicates
the number of attempts to insert column values that were
problematic in some way. Warnings can occur under any of the
following conditions:

- Inserting `NULL` into a column that has been
declared `NOT NULL`. For multiple-row
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements or
[`INSERT INTO ...\\
            SELECT`](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement") statements, the column is set to the implicit
default value for the column data type. This is
`0` for numeric types, the empty string
( `''`) for string types, and the
“zero” value for date and time types.
[`INSERT INTO ...\\
            SELECT`](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement") statements are handled the same way as
multiple-row inserts because the server does not examine the
result set from the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") to
see whether it returns a single row. (For a single-row
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"), no warning occurs when
`NULL` is inserted into a `NOT
            NULL` column. Instead, the statement fails with an
error.)


- Setting a numeric column to a value that lies outside the
column range. The value is clipped to the closest endpoint of
the range.


- Assigning a value such as `'10.34 a'` to a
numeric column. The trailing nonnumeric text is stripped off
and the remaining numeric part is inserted. If the string
value has no leading numeric part, the column is set to
`0`.


- Inserting a string into a string column
( [`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types"), or
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types")) that exceeds the column
maximum length. The value is truncated to the column maximum
length.


- Inserting a value into a date or time column that is illegal
for the data type. The column is set to the appropriate zero
value for the type.


- For [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") examples involving
`AUTO_INCREMENT` column values, see
[Section 5.6.9, “Using AUTO\_INCREMENT”](https://dev.mysql.com/doc/refman/8.0/en/example-auto-increment.html "5.6.9 Using AUTO_INCREMENT").



If [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") inserts a row into a
table that has an `AUTO_INCREMENT` column,
you can find the value used for that column by using the
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) SQL function
or the [`mysql_insert_id()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-insert-id.html) C API
function.





Note





These two functions do not always behave identically. The
behavior of [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements
with respect to `AUTO_INCREMENT` columns is
discussed further in
[Section 14.15, “Information Functions”](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html "14.15 Information Functions"), and
[mysql\_insert\_id()](https://dev.mysql.com/doc/c-api/8.0/en/mysql-insert-id.html).


The [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement supports the
following modifiers:

- If you use the `LOW_PRIORITY` modifier,
execution of the [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") is
delayed until no other clients are reading from the table.
This includes other clients that began reading while existing
clients are reading, and while the `INSERT
            LOW_PRIORITY` statement is waiting. It is possible,
therefore, for a client that issues an `INSERT
            LOW_PRIORITY` statement to wait for a very long time.


`LOW_PRIORITY` affects only storage engines
that use only table-level locking (such as
`MyISAM`, `MEMORY`, and
`MERGE`).





Note




`LOW_PRIORITY` should normally not be used
with `MyISAM` tables because doing so
disables concurrent inserts. See
[Section 10.11.3, “Concurrent Inserts”](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html "10.11.3 Concurrent Inserts").

- If you specify `HIGH_PRIORITY`, it overrides
the effect of the
[`--low-priority-updates`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_low_priority_updates) option
if the server was started with that option. It also causes
concurrent inserts not to be used. See
[Section 10.11.3, “Concurrent Inserts”](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html "10.11.3 Concurrent Inserts").


`HIGH_PRIORITY` affects only storage engines
that use only table-level locking (such as
`MyISAM`, `MEMORY`, and
`MERGE`).


- If you use the `IGNORE` modifier, ignorable
errors that occur while executing the
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement are ignored.
For example, without `IGNORE`, a row that
duplicates an existing `UNIQUE` index or
`PRIMARY KEY` value in the table causes a
duplicate-key error and the statement is aborted. With
`IGNORE`, the row is discarded and no error
occurs. Ignored errors generate warnings instead.


`IGNORE` has a similar effect on inserts into
partitioned tables where no partition matching a given value
is found. Without `IGNORE`, such
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements are aborted
with an error. When
[`INSERT\\
            IGNORE`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") is used, the insert operation fails silently
for rows containing the unmatched value, but inserts rows that
are matched. For an example, see
[Section 26.2.2, “LIST Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html "26.2.2 LIST Partitioning").



Data conversions that would trigger errors abort the statement
if `IGNORE` is not specified. With
`IGNORE`, invalid values are adjusted to the
closest values and inserted; warnings are produced but the
statement does not abort. You can determine with the
[`mysql_info()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-info.html) C API function
how many rows were actually inserted into the table.



For more information, see
[The Effect of IGNORE on Statement Execution](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#ignore-effect-on-execution "The Effect of IGNORE on Statement Execution").



You can use [`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") instead of
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") to overwrite old rows.
[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") is the counterpart to
[`INSERT\\
            IGNORE`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") in the treatment of new rows that contain
unique key values that duplicate old rows: The new rows
replace the old rows rather than being discarded. See
[Section 15.2.12, “REPLACE Statement”](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement").


- If you specify `ON DUPLICATE KEY UPDATE`, and
a row is inserted that would cause a duplicate value in a
`UNIQUE` index or `PRIMARY
            KEY`, an [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") of the
old row occurs. The affected-rows value per row is 1 if the
row is inserted as a new row, 2 if an existing row is updated,
and 0 if an existing row is set to its current values. If you
specify the `CLIENT_FOUND_ROWS` flag to the
[`mysql_real_connect()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-real-connect.html) C API
function when connecting to [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server"), the
affected-rows value is 1 (not 0) if an existing row is set to
its current values. See [Section 15.2.7.2, “INSERT ... ON DUPLICATE KEY UPDATE Statement”](https://dev.mysql.com/doc/refman/8.0/en/insert-on-duplicate.html "15.2.7.2 INSERT ... ON DUPLICATE KEY UPDATE Statement").


- [`INSERT DELAYED`](https://dev.mysql.com/doc/refman/8.0/en/insert-delayed.html "15.2.7.3 INSERT DELAYED Statement") was deprecated
in MySQL 5.6, and is scheduled for eventual removal. In MySQL
8.0, the `DELAYED` modifier is
accepted but ignored. Use `INSERT` (without
`DELAYED`) instead. See
[Section 15.2.7.3, “INSERT DELAYED Statement”](https://dev.mysql.com/doc/refman/8.0/en/insert-delayed.html "15.2.7.3 INSERT DELAYED Statement").


[PREV](https://dev.mysql.com/doc/refman/8.0/en/import-table.html "Previous: IMPORT TABLE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Up: Data Manipulation Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "Next: INSERT ... SELECT Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/insert.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/insert.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/insert.html)

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