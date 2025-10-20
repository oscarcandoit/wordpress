---
url: https://dev.mysql.com/doc/refman/8.0/en/update.html
scraped_at: 2025-10-20T02:58:37.402Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/update.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/update.html "Hide Sidebar")

[Previous: TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/table.html "Previous: TABLE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Up: Data Manipulation Statements")[Next: UNION Clause](https://dev.mysql.com/doc/refman/8.0/en/union.html "Next: UNION Clause")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/update.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/update.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/update.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/update.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/update.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/update.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/update.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/update.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/update.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/update.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/update.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/update.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/update.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/update.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html)  /

UPDATE Statement


### 15.2.17 UPDATE Statement

[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") is a DML statement that
modifies rows in a table.


An [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement can start with
a [`WITH`](https://dev.mysql.com/doc/refman/8.0/en/with.html "15.2.20 WITH (Common Table Expressions)") clause to define common
table expressions accessible within the
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"). See [Section 15.2.20, “WITH (Common Table Expressions)”](https://dev.mysql.com/doc/refman/8.0/en/with.html "15.2.20 WITH (Common Table Expressions)").


Single-table syntax:


```sql
UPDATE [LOW_PRIORITY] [IGNORE] table_reference
    SET assignment_list
    [WHERE where_condition]
    [ORDER BY ...]
    [LIMIT row_count]

value:
    {expr | DEFAULT}

assignment:
    col_name = value

assignment_list:
    assignment [, assignment] ...
```

Multiple-table syntax:


```sql
UPDATE [LOW_PRIORITY] [IGNORE] table_references
    SET assignment_list
    [WHERE where_condition]
```

For the single-table syntax, the
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement updates columns of
existing rows in the named table with new values. The
`SET` clause indicates which columns to modify
and the values they should be given. Each value can be given as an
expression, or the keyword `DEFAULT` to set a
column explicitly to its default value. The
`WHERE` clause, if given, specifies the
conditions that identify which rows to update. With no
`WHERE` clause, all rows are updated. If the
`ORDER BY` clause is specified, the rows are
updated in the order that is specified. The
`LIMIT` clause places a limit on the number of
rows that can be updated.


For the multiple-table syntax,
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") updates rows in each table
named in _`table_references`_ that satisfy
the conditions. Each matching row is updated once, even if it
matches the conditions multiple times. For multiple-table syntax,
`ORDER BY` and `LIMIT` cannot be
used.


For partitioned tables, both the single-single and multiple-table
forms of this statement support the use of a
`PARTITION` clause as part of a table reference.
This option takes a list of one or more partitions or
subpartitions (or both). Only the partitions (or subpartitions)
listed are checked for matches, and a row that is not in any of
these partitions or subpartitions is not updated, whether it
satisfies the _`where_condition`_ or not.

Note

Unlike the case when using `PARTITION` with an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") or
[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") statement, an otherwise
valid `UPDATE ... PARTITION` statement is
considered successful even if no rows in the listed partitions
(or subpartitions) match the
_`where_condition`_.

For more information and examples, see
[Section 26.5, “Partition Selection”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-selection.html "26.5 Partition Selection").


_`where_condition`_ is an expression that
evaluates to true for each row to be updated. For expression
syntax, see [Section 11.5, “Expressions”](https://dev.mysql.com/doc/refman/8.0/en/expressions.html "11.5 Expressions").


_`table_references`_ and
_`where_condition`_ are specified as
described in [Section 15.2.13, “SELECT Statement”](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement").


You need the [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_update) privilege only
for columns referenced in an [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement")
that are actually updated. You need only the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege for any columns
that are read but not modified.


The [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement supports the
following modifiers:

- With the `LOW_PRIORITY` modifier, execution
of the [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") is delayed until
no other clients are reading from the table. This affects only
storage engines that use only table-level locking (such as
`MyISAM`, `MEMORY`, and
`MERGE`).


- With the `IGNORE` modifier, the update
statement does not abort even if errors occur during the
update. Rows for which duplicate-key conflicts occur on a
unique key value are not updated. Rows updated to values that
would cause data conversion errors are updated to the closest
valid values instead. For more information, see
[The Effect of IGNORE on Statement Execution](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#ignore-effect-on-execution "The Effect of IGNORE on Statement Execution").


[`UPDATE IGNORE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement")
statements, including those having an `ORDER BY`
clause, are flagged as unsafe for statement-based replication.
(This is because the order in which the rows are updated
determines which rows are ignored.) Such statements produce a
warning in the error log when using statement-based mode and are
written to the binary log using the row-based format when using
`MIXED` mode. (Bug #11758262, Bug #50439) See
[Section 19.2.1.3, “Determination of Safe and Unsafe Statements in Binary Logging”](https://dev.mysql.com/doc/refman/8.0/en/replication-rbr-safe-unsafe.html "19.2.1.3 Determination of Safe and Unsafe Statements in Binary Logging"), for more
information.


If you access a column from the table to be updated in an
expression, [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") uses the current
value of the column. For example, the following statement sets
`col1` to one more than its current value:


```sql
UPDATE t1 SET col1 = col1 + 1;
```

The second assignment in the following statement sets
`col2` to the current (updated)
`col1` value, not the original
`col1` value. The result is that
`col1` and `col2` have the same
value. This behavior differs from standard SQL.


```sql
UPDATE t1 SET col1 = col1 + 1, col2 = col1;
```

Single-table [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") assignments are
generally evaluated from left to right. For multiple-table
updates, there is no guarantee that assignments are carried out in
any particular order.


If you set a column to the value it currently has, MySQL notices
this and does not update it.


If you update a column that has been declared `NOT
      NULL` by setting to `NULL`, an error
occurs if strict SQL mode is enabled; otherwise, the column is set
to the implicit default value for the column data type and the
warning count is incremented. The implicit default value is
`0` for numeric types, the empty string
( `''`) for string types, and the
“zero” value for date and time types. See
[Section 13.6, “Data Type Default Values”](https://dev.mysql.com/doc/refman/8.0/en/data-type-defaults.html "13.6 Data Type Default Values").


If a generated column is updated explicitly, the only permitted
value is `DEFAULT`. For information about
generated columns, see
[Section 15.1.20.8, “CREATE TABLE and Generated Columns”](https://dev.mysql.com/doc/refman/8.0/en/create-table-generated-columns.html "15.1.20.8 CREATE TABLE and Generated Columns").


[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") returns the number of rows
that were actually changed. The
[`mysql_info()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-info.html) C API function
returns the number of rows that were matched and updated and the
number of warnings that occurred during the
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement").


You can use `LIMIT
      row_count` to restrict the
scope of the [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"). A
`LIMIT` clause is a rows-matched restriction. The
statement stops as soon as it has found
_`row_count`_ rows that satisfy the
`WHERE` clause, whether or not they actually were
changed.


If an [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement includes an
`ORDER BY` clause, the rows are updated in the
order specified by the clause. This can be useful in certain
situations that might otherwise result in an error. Suppose that a
table `t` contains a column `id`
that has a unique index. The following statement could fail with a
duplicate-key error, depending on the order in which rows are
updated:


```sql
UPDATE t SET id = id + 1;
```

For example, if the table contains 1 and 2 in the
`id` column and 1 is updated to 2 before 2 is
updated to 3, an error occurs. To avoid this problem, add an
`ORDER BY` clause to cause the rows with larger
`id` values to be updated before those with
smaller values:


```sql
UPDATE t SET id = id + 1 ORDER BY id DESC;
```

You can also perform [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement")
operations covering multiple tables. However, you cannot use
`ORDER BY` or `LIMIT` with a
multiple-table [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"). The
_`table_references`_ clause lists the
tables involved in the join. Its syntax is described in
[Section 15.2.13.2, “JOIN Clause”](https://dev.mysql.com/doc/refman/8.0/en/join.html "15.2.13.2 JOIN Clause"). Here is an example:


```sql
UPDATE items,month SET items.price=month.price
WHERE items.id=month.id;
```

The preceding example shows an inner join that uses the comma
operator, but multiple-table [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement")
statements can use any type of join permitted in
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements, such as
`LEFT JOIN`.


If you use a multiple-table [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement")
statement involving `InnoDB` tables for which
there are foreign key constraints, the MySQL optimizer might
process tables in an order that differs from that of their
parent/child relationship. In this case, the statement fails and
rolls back. Instead, update a single table and rely on the
`ON UPDATE` capabilities that
`InnoDB` provides to cause the other tables to be
modified accordingly. See
[Section 15.1.20.5, “FOREIGN KEY Constraints”](https://dev.mysql.com/doc/refman/8.0/en/create-table-foreign-keys.html "15.1.20.5 FOREIGN KEY Constraints").


You cannot update a table and select directly from the same table
in a subquery. You can work around this by using a multi-table
update in which one of the tables is derived from the table that
you actually wish to update, and referring to the derived table
using an alias. Suppose you wish to update a table named
`items` which is defined using the statement
shown here:


```sql
CREATE TABLE items (
    id BIGINT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    wholesale DECIMAL(6,2) NOT NULL DEFAULT 0.00,
    retail DECIMAL(6,2) NOT NULL DEFAULT 0.00,
    quantity BIGINT NOT NULL DEFAULT 0
);
```

To reduce the retail price of any items for which the markup is
30% or greater and of which you have fewer than one hundred in
stock, you might try to use an `UPDATE` statement
such as the one following, which uses a subquery in the
`WHERE` clause. As shown here, this statement
does not work:


```sql
mysql> UPDATE items
     > SET retail = retail * 0.9
     > WHERE id IN
     >     (SELECT id FROM items
     >         WHERE retail / wholesale >= 1.3 AND quantity > 100);
ERROR 1093 (HY000): You can't specify target table 'items' for update in FROM clause
```

Instead, you can employ a multi-table update in which the subquery
is moved into the list of tables to be updated, using an alias to
reference it in the outermost `WHERE` clause,
like this:


```sql
UPDATE items,
       (SELECT id FROM items
        WHERE id IN
            (SELECT id FROM items
             WHERE retail / wholesale >= 1.3 AND quantity < 100))
        AS discounted
SET items.retail = items.retail * 0.9
WHERE items.id = discounted.id;
```

Because the optimizer tries by default to merge the derived table
`discounted` into the outermost query block, this
works only if you force materialization of the derived table. You
can do this by setting the
[`derived_merge`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_derived-merge) flag of the
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) system variable
to `off` before running the update, or by using
the [`NO_MERGE`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-table-level "Table-Level Optimizer Hints") optimizer hint, as
shown here:


```sql
UPDATE /*+ NO_MERGE(discounted) */ items,
       (SELECT id FROM items
        WHERE retail / wholesale >= 1.3 AND quantity < 100)
        AS discounted
    SET items.retail = items.retail * 0.9
    WHERE items.id = discounted.id;
```

The advantage of using the optimizer hint in such a case is that
it applies only within the query block where it is used, so that
it is not necessary to change the value of
`optimizer_switch` again after executing the
`UPDATE`.


Another possibility is to rewrite the subquery so that it does not
use `IN` or `EXISTS`, like this:


```sql
UPDATE items,
       (SELECT id, retail / wholesale AS markup, quantity FROM items)
       AS discounted
    SET items.retail = items.retail * 0.9
    WHERE discounted.markup >= 1.3
    AND discounted.quantity < 100
    AND items.id = discounted.id;
```

In this case, the subquery is materialized by default rather than
merged, so it is not necessary to disable merging of the derived
table.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/table.html "Previous: TABLE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Up: Data Manipulation Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/union.html "Next: UNION Clause")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/update.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/update.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/update.html)

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