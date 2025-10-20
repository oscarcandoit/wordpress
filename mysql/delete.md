---
url: https://dev.mysql.com/doc/refman/8.0/en/delete.html
scraped_at: 2025-10-20T02:58:40.487Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/delete.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/delete.html "Hide Sidebar")

[Previous: CALL Statement](https://dev.mysql.com/doc/refman/8.0/en/call.html "Previous: CALL Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Up: Data Manipulation Statements")[Next: DO Statement](https://dev.mysql.com/doc/refman/8.0/en/do.html "Next: DO Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/delete.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/delete.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/delete.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/delete.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/delete.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/delete.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/delete.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/delete.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/delete.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/delete.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/delete.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/delete.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/delete.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/delete.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html)  /

DELETE Statement


### 15.2.2 DELETE Statement

[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") is a DML statement that
removes rows from a table.


A [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statement can start with a
[`WITH`](https://dev.mysql.com/doc/refman/8.0/en/with.html "15.2.20 WITH (Common Table Expressions)") clause to define common table
expressions accessible within the
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"). See [Section 15.2.20, “WITH (Common Table Expressions)”](https://dev.mysql.com/doc/refman/8.0/en/with.html "15.2.20 WITH (Common Table Expressions)").

#### Single-Table Syntax

``` sql

DELETE [LOW_PRIORITY] [QUICK] [IGNORE] FROM tbl_name [[AS] tbl_alias]
    [PARTITION (partition_name [, partition_name] ...)]
    [WHERE where_condition]
    [ORDER BY ...]
    [LIMIT row_count]
```

The `DELETE` statement deletes rows from
_`tbl_name`_ and returns the number of
deleted rows. To check the number of deleted rows, call the
[`ROW_COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_row-count) function described in
[Section 14.15, “Information Functions”](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html "14.15 Information Functions").

#### Main Clauses

The conditions in the optional `WHERE` clause
identify which rows to delete. With no `WHERE`
clause, all rows are deleted.


_`where_condition`_ is an expression that
evaluates to true for each row to be deleted. It is specified as
described in [Section 15.2.13, “SELECT Statement”](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement").


If the `ORDER BY` clause is specified, the rows
are deleted in the order that is specified. The
`LIMIT` clause places a limit on the number of
rows that can be deleted. These clauses apply to single-table
deletes, but not multi-table deletes.

#### Multiple-Table Syntax

``` sql

DELETE [LOW_PRIORITY] [QUICK] [IGNORE]
    tbl_name[.*] [, tbl_name[.*]] ...
    FROM table_references
    [WHERE where_condition]

DELETE [LOW_PRIORITY] [QUICK] [IGNORE]
    FROM tbl_name[.*] [, tbl_name[.*]] ...
    USING table_references
    [WHERE where_condition]
```

#### Privileges

You need the [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_delete) privilege on a
table to delete rows from it. You need only the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege for any columns
that are only read, such as those named in the
`WHERE` clause.

#### Performance

When you do not need to know the number of deleted rows, the
[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") statement is a
faster way to empty a table than a
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statement with no
`WHERE` clause. Unlike
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"),
[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") cannot be used
within a transaction or if you have a lock on the table. See
[Section 15.1.37, “TRUNCATE TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") and
[Section 15.3.6, “LOCK TABLES and UNLOCK TABLES Statements”](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements").


The speed of delete operations may also be affected by factors
discussed in [Section 10.2.5.3, “Optimizing DELETE Statements”](https://dev.mysql.com/doc/refman/8.0/en/delete-optimization.html "10.2.5.3 Optimizing DELETE Statements").


To ensure that a given [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement")
statement does not take too much time, the MySQL-specific
`LIMIT row_count`
clause for [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") specifies the
maximum number of rows to be deleted. If the number of rows to
delete is larger than the limit, repeat the
`DELETE` statement until the number of affected
rows is less than the `LIMIT` value.

#### Subqueries

You cannot delete from a table and select from the same table in a
subquery.

#### Partitioned Table Support

`DELETE` supports explicit partition selection
using the `PARTITION` clause, which takes a list
of the comma-separated names of one or more partitions or
subpartitions (or both) from which to select rows to be dropped.
Partitions not included in the list are ignored. Given a
partitioned table `t` with a partition named
`p0`, executing the statement `DELETE
      FROM t PARTITION (p0)` has the same effect on the table
as executing [`ALTER\\
      TABLE t TRUNCATE PARTITION (p0)`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement"); in both cases, all rows
in partition `p0` are dropped.


`PARTITION` can be used along with a
`WHERE` condition, in which case the condition is
tested only on rows in the listed partitions. For example,
`DELETE FROM t PARTITION (p0) WHERE c < 5`
deletes rows only from partition `p0` for which
the condition `c < 5` is true; rows in any
other partitions are not checked and thus not affected by the
`DELETE`.


The `PARTITION` clause can also be used in
multiple-table `DELETE` statements. You can use
up to one such option per table named in the
`FROM` option.


For more information and examples, see
[Section 26.5, “Partition Selection”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-selection.html "26.5 Partition Selection").

#### Auto-Increment Columns

If you delete the row containing the maximum value for an
`AUTO_INCREMENT` column, the value is not reused
for a `MyISAM` or `InnoDB`
table. If you delete all rows in the table with `DELETE
      FROM tbl_name` (without a
`WHERE` clause) in
[`autocommit`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_autocommit) mode, the sequence
starts over for all storage engines except
`InnoDB` and `MyISAM`. There are
some exceptions to this behavior for `InnoDB`
tables, as discussed in
[Section 17.6.1.6, “AUTO\_INCREMENT Handling in InnoDB”](https://dev.mysql.com/doc/refman/8.0/en/innodb-auto-increment-handling.html "17.6.1.6 AUTO_INCREMENT Handling in InnoDB").


For `MyISAM` tables, you can specify an
`AUTO_INCREMENT` secondary column in a
multiple-column key. In this case, reuse of values deleted from
the top of the sequence occurs even for `MyISAM`
tables. See [Section 5.6.9, “Using AUTO\_INCREMENT”](https://dev.mysql.com/doc/refman/8.0/en/example-auto-increment.html "5.6.9 Using AUTO_INCREMENT").

#### Modifiers

The [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statement supports the
following modifiers:

- If you specify the `LOW_PRIORITY` modifier,
the server delays execution of the
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") until no other clients
are reading from the table. This affects only storage engines
that use only table-level locking (such as
`MyISAM`, `MEMORY`, and
`MERGE`).


- For `MyISAM` tables, if you use the
`QUICK` modifier, the storage engine does not
merge index leaves during delete, which may speed up some
kinds of delete operations.


- The `IGNORE` modifier causes MySQL to ignore
ignorable errors during the process of deleting rows. (Errors
encountered during the parsing stage are processed in the
usual manner.) Errors that are ignored due to the use of
`IGNORE` are returned as warnings. For more
information, see [The Effect of IGNORE on Statement Execution](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#ignore-effect-on-execution "The Effect of IGNORE on Statement Execution").


#### Order of Deletion

If the [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statement includes an
`ORDER BY` clause, rows are deleted in the order
specified by the clause. This is useful primarily in conjunction
with `LIMIT`. For example, the following
statement finds rows matching the `WHERE` clause,
sorts them by `timestamp_column`, and deletes the
first (oldest) one:


``` sql

DELETE FROM somelog WHERE user = 'jcole'
ORDER BY timestamp_column LIMIT 1;
```

`ORDER BY` also helps to delete rows in an order
required to avoid referential integrity violations.

#### InnoDB Tables

If you are deleting many rows from a large table, you may exceed
the lock table size for an `InnoDB` table. To
avoid this problem, or simply to minimize the time that the table
remains locked, the following strategy (which does not use
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") at all) might be helpful:

1. Select the rows _not_ to be deleted into an
    empty table that has the same structure as the original table:




``` sql

INSERT INTO t_copy SELECT * FROM t WHERE ... ;
```

2. Use [`RENAME TABLE`](https://dev.mysql.com/doc/refman/8.0/en/rename-table.html "15.1.36 RENAME TABLE Statement") to atomically
    move the original table out of the way and rename the copy to
    the original name:




``` sql

RENAME TABLE t TO t_old, t_copy TO t;
```

3. Drop the original table:




``` sql

DROP TABLE t_old;
```


No other sessions can access the tables involved while
[`RENAME TABLE`](https://dev.mysql.com/doc/refman/8.0/en/rename-table.html "15.1.36 RENAME TABLE Statement") executes, so the
rename operation is not subject to concurrency problems. See
[Section 15.1.36, “RENAME TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/rename-table.html "15.1.36 RENAME TABLE Statement").

#### MyISAM Tables

In `MyISAM` tables, deleted rows are maintained
in a linked list and subsequent
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") operations reuse old row
positions. To reclaim unused space and reduce file sizes, use the
[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") statement or the
[**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") utility to reorganize tables.
[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") is easier to use,
but [**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") is faster. See
[Section 15.7.3.4, “OPTIMIZE TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement"), and [Section 6.6.4, “myisamchk — MyISAM Table-Maintenance Utility”](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility").


The `QUICK` modifier affects whether index leaves
are merged for delete operations. `DELETE QUICK`
is most useful for applications where index values for deleted
rows are replaced by similar index values from rows inserted
later. In this case, the holes left by deleted values are reused.


`DELETE QUICK` is not useful when deleted values
lead to underfilled index blocks spanning a range of index values
for which new inserts occur again. In this case, use of
`QUICK` can lead to wasted space in the index
that remains unreclaimed. Here is an example of such a scenario:

1. Create a table that contains an indexed
    `AUTO_INCREMENT` column.


2. Insert many rows into the table. Each insert results in an
    index value that is added to the high end of the index.


3. Delete a block of rows at the low end of the column range
    using `DELETE QUICK`.


In this scenario, the index blocks associated with the deleted
index values become underfilled but are not merged with other
index blocks due to the use of `QUICK`. They
remain underfilled when new inserts occur, because new rows do not
have index values in the deleted range. Furthermore, they remain
underfilled even if you later use
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") without
`QUICK`, unless some of the deleted index values
happen to lie in index blocks within or adjacent to the
underfilled blocks. To reclaim unused index space under these
circumstances, use [`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement").


If you are going to delete many rows from a table, it might be
faster to use `DELETE QUICK` followed by
[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement"). This rebuilds the
index rather than performing many index block merge operations.

#### Multi-Table Deletes

You can specify multiple tables in a
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statement to delete rows
from one or more tables depending on the condition in the
`WHERE` clause. You cannot use `ORDER
      BY` or `LIMIT` in a multiple-table
`DELETE`. The
_`table_references`_ clause lists the
tables involved in the join, as described in
[Section 15.2.13.2, “JOIN Clause”](https://dev.mysql.com/doc/refman/8.0/en/join.html "15.2.13.2 JOIN Clause").


For the first multiple-table syntax, only matching rows from the
tables listed before the `FROM` clause are
deleted. For the second multiple-table syntax, only matching rows
from the tables listed in the `FROM` clause
(before the `USING` clause) are deleted. The
effect is that you can delete rows from many tables at the same
time and have additional tables that are used only for searching:


``` sql

DELETE t1, t2 FROM t1 INNER JOIN t2 INNER JOIN t3
WHERE t1.id=t2.id AND t2.id=t3.id;
```

Or:


``` sql

DELETE FROM t1, t2 USING t1 INNER JOIN t2 INNER JOIN t3
WHERE t1.id=t2.id AND t2.id=t3.id;
```

These statements use all three tables when searching for rows to
delete, but delete matching rows only from tables
`t1` and `t2`.


The preceding examples use `INNER JOIN`, but
multiple-table [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statements
can use other types of join permitted in
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements, such as
`LEFT JOIN`. For example, to delete rows that
exist in `t1` that have no match in
`t2`, use a `LEFT JOIN`:


``` sql

DELETE t1 FROM t1 LEFT JOIN t2 ON t1.id=t2.id WHERE t2.id IS NULL;
```

The syntax permits `.*` after each
_`tbl_name`_ for compatibility with
**Access**.


If you use a multiple-table [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement")
statement involving `InnoDB` tables for which
there are foreign key constraints, the MySQL optimizer might
process tables in an order that differs from that of their
parent/child relationship. In this case, the statement fails and
rolls back. Instead, you should delete from a single table and
rely on the `ON DELETE` capabilities that
`InnoDB` provides to cause the other tables to be
modified accordingly.

Note

If you declare an alias for a table, you must use the alias when
referring to the table:


``` sql

DELETE t1 FROM test AS t1, test2 WHERE ...
```

Table aliases in a multiple-table
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") should be declared only in
the _`table_references`_ part of the
statement. Elsewhere, alias references are permitted but not alias
declarations.


Correct:


``` sql

DELETE a1, a2 FROM t1 AS a1 INNER JOIN t2 AS a2
WHERE a1.id=a2.id;

DELETE FROM a1, a2 USING t1 AS a1 INNER JOIN t2 AS a2
WHERE a1.id=a2.id;
```

Incorrect:


``` sql

DELETE t1 AS a1, t2 AS a2 FROM t1 INNER JOIN t2
WHERE a1.id=a2.id;

DELETE FROM t1 AS a1, t2 AS a2 USING t1 INNER JOIN t2
WHERE a1.id=a2.id;
```

Table aliases are also supported for single-table
`DELETE` statements beginning with MySQL 8.0.16.
(Bug #89410,Bug #27455809)

[PREV](https://dev.mysql.com/doc/refman/8.0/en/call.html "Previous: CALL Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Up: Data Manipulation Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/do.html "Next: DO Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/delete.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/delete.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/delete.html)

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