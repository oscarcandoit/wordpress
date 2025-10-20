---
url: https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html
scraped_at: 2025-10-20T03:04:41.413Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html "Hide Sidebar")

[Previous: RANGE Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html "Previous: RANGE Partitioning")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Partitioning Types](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "Up: Partitioning Types")[Next: COLUMNS Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-columns.html "Next: COLUMNS Partitioning")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/partitioning-list.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/partitioning-list.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/partitioning-list.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/partitioning-list.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/partitioning-list.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/partitioning-list.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/partitioning-list.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/partitioning-list.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html)  / [Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)  /
[Partitioning Types](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html)  /

LIST Partitioning


### 26.2.2 LIST Partitioning

List partitioning in MySQL is similar to range partitioning in
many ways. As in partitioning by `RANGE`, each
partition must be explicitly defined. The chief difference
between the two types of partitioning is that, in list
partitioning, each partition is defined and selected based on
the membership of a column value in one of a set of value lists,
rather than in one of a set of contiguous ranges of values. This
is done by using `PARTITION BY
        LIST(expr)` where
_`expr`_ is a column value or an
expression based on a column value and returning an integer
value, and then defining each partition by means of a
`VALUES IN
        (value_list)`, where
_`value_list`_ is a comma-separated list
of integers.

Note

In MySQL 8.0, it is possible to match against
only a list of integers (and possibly
`NULL`—see
[Section 26.2.7, “How MySQL Partitioning Handles NULL”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-handling-nulls.html "26.2.7 How MySQL Partitioning Handles NULL")) when
partitioning by `LIST`.


However, other column types may be used in value lists when
employing `LIST COLUMN` partitioning, which
is described later in this section.

Unlike the case with partitions defined by range, list
partitions do not need to be declared in any particular order.
For more detailed syntactical information, see
[Section 15.1.20, “CREATE TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement").


For the examples that follow, we assume that the basic
definition of the table to be partitioned is provided by the
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement shown
here:


``` sql

CREATE TABLE employees (
    id INT NOT NULL,
    fname VARCHAR(30),
    lname VARCHAR(30),
    hired DATE NOT NULL DEFAULT '1970-01-01',
    separated DATE NOT NULL DEFAULT '9999-12-31',
    job_code INT,
    store_id INT
);
```

(This is the same table used as a basis for the examples in
[Section 26.2.1, “RANGE Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html "26.2.1 RANGE Partitioning"). As with the other
partitioning examples, we assume that the
[`default_storage_engine`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_default_storage_engine) is
`InnoDB`.)


Suppose that there are 20 video stores distributed among 4
franchises as shown in the following table.

| Region | Store ID Numbers |
| --- | --- |
| North | 3, 5, 6, 9, 17 |
| East | 1, 2, 10, 11, 19, 20 |
| West | 4, 12, 13, 14, 18 |
| Central | 7, 8, 15, 16 |

To partition this table in such a way that rows for stores
belonging to the same region are stored in the same partition,
you could use the [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement")
statement shown here:


``` sql

CREATE TABLE employees (
    id INT NOT NULL,
    fname VARCHAR(30),
    lname VARCHAR(30),
    hired DATE NOT NULL DEFAULT '1970-01-01',
    separated DATE NOT NULL DEFAULT '9999-12-31',
    job_code INT,
    store_id INT
)
PARTITION BY LIST(store_id) (
    PARTITION pNorth VALUES IN (3,5,6,9,17),
    PARTITION pEast VALUES IN (1,2,10,11,19,20),
    PARTITION pWest VALUES IN (4,12,13,14,18),
    PARTITION pCentral VALUES IN (7,8,15,16)
);
```

This makes it easy to add or drop employee records relating to
specific regions to or from the table. For instance, suppose
that all stores in the West region are sold to another company.
In MySQL 8.0, all rows relating to employees
working at stores in that region can be deleted with the query
`ALTER TABLE employees TRUNCATE PARTITION
        pWest`, which can be executed much more efficiently
than the equivalent [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement")
statement `DELETE FROM employees WHERE store_id IN
        (4,12,13,14,18);`. (Using `ALTER TABLE
        employees DROP PARTITION pWest` would also delete all
of these rows, but would also remove the partition
`pWest` from the definition of the table; you
would need to use an `ALTER TABLE ... ADD
        PARTITION` statement to restore the table's
original partitioning scheme.)


As with `RANGE` partitioning, it is possible to
combine `LIST` partitioning with partitioning
by hash or key to produce a composite partitioning
(subpartitioning). See
[Section 26.2.6, “Subpartitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-subpartitions.html "26.2.6 Subpartitioning").


Unlike the case with `RANGE` partitioning,
there is no “catch-all” such as
`MAXVALUE`; all expected values for the
partitioning expression should be covered in `PARTITION
        ... VALUES IN (...)` clauses. An
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement containing an
unmatched partitioning column value fails with an error, as
shown in this example:


``` sql

mysql> CREATE TABLE h2 (
    ->   c1 INT,
    ->   c2 INT
    -> )
    -> PARTITION BY LIST(c1) (
    ->   PARTITION p0 VALUES IN (1, 4, 7),
    ->   PARTITION p1 VALUES IN (2, 5, 8)
    -> );
Query OK, 0 rows affected (0.11 sec)

mysql> INSERT INTO h2 VALUES (3, 5);
ERROR 1525 (HY000): Table has no partition for value 3
```

When inserting multiple rows using a single
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement into a single
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") table,
`InnoDB` considers the statement a single
transaction, so that the presence of any unmatched values causes
the statement to fail completely, and so no rows are inserted.


You can cause this type of error to be ignored by using the
`IGNORE` keyword, although a warning is issued
for each row containing unmatched partitioning column values, as
shown here.


``` sql

mysql> TRUNCATE h2;
Query OK, 1 row affected (0.00 sec)

mysql> TABLE h2;
Empty set (0.00 sec)

mysql> INSERT IGNORE INTO h2 VALUES (2, 5), (6, 10), (7, 5), (3, 1), (1, 9);
Query OK, 3 rows affected, 2 warnings (0.01 sec)
Records: 5  Duplicates: 2  Warnings: 2

mysql> SHOW WARNINGS;
+---------+------+------------------------------------+
| Level   | Code | Message                            |
+---------+------+------------------------------------+
| Warning | 1526 | Table has no partition for value 6 |
| Warning | 1526 | Table has no partition for value 3 |
+---------+------+------------------------------------+
2 rows in set (0.00 sec)
```

You can see in the output of the following
[`TABLE`](https://dev.mysql.com/doc/refman/8.0/en/table.html "15.2.16 TABLE Statement") statement that rows
containing unmatched partitioning column values were silently
rejected, while rows containing no unmatched values were
inserted into the table:


``` sql

mysql> TABLE h2;
+------+------+
| c1   | c2   |
+------+------+
|    7 |    5 |
|    1 |    9 |
|    2 |    5 |
+------+------+
3 rows in set (0.00 sec)
```

MySQL also provides support for `LIST COLUMNS`
partitioning, a variant of `LIST` partitioning
that enables you to use columns of types other than integer for
partitioning columns, and to use multiple columns as
partitioning keys. For more information, see
[Section 26.2.3.2, “LIST COLUMNS partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-columns-list.html "26.2.3.2 LIST COLUMNS partitioning").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html "Previous: RANGE Partitioning") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "Up: Partitioning Types") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/partitioning-columns.html "Next: COLUMNS Partitioning")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html)

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