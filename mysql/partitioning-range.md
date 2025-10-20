---
url: https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html
scraped_at: 2025-10-20T03:04:37.860Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html "Hide Sidebar")

[Previous: Partitioning Types](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "Previous: Partitioning Types")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Partitioning Types](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "Up: Partitioning Types")[Next: LIST Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html "Next: LIST Partitioning")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/partitioning-range.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/partitioning-range.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/partitioning-range.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/partitioning-range.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/partitioning-range.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/partitioning-range.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/partitioning-range.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/partitioning-range.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html)  / [Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)  /
[Partitioning Types](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html)  /

RANGE Partitioning


### 26.2.1 RANGE Partitioning

A table that is partitioned by range is partitioned in such a
way that each partition contains rows for which the partitioning
expression value lies within a given range. Ranges should be
contiguous but not overlapping, and are defined using the
`VALUES LESS THAN` operator. For the next few
examples, suppose that you are creating a table such as the
following to hold personnel records for a chain of 20 video
stores, numbered 1 through 20:


```sql
CREATE TABLE employees (
    id INT NOT NULL,
    fname VARCHAR(30),
    lname VARCHAR(30),
    hired DATE NOT NULL DEFAULT '1970-01-01',
    separated DATE NOT NULL DEFAULT '9999-12-31',
    job_code INT NOT NULL,
    store_id INT NOT NULL
);
```

Note

The `employees` table used here has no
primary or unique keys. While the examples work as shown for
purposes of the present discussion, you should keep in mind
that tables are extremely likely in practice to have primary
keys, unique keys, or both, and that allowable choices for
partitioning columns depend on the columns used for these
keys, if any are present. For a discussion of these issues,
see
[Section 26.6.1, “Partitioning Keys, Primary Keys, and Unique Keys”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-limitations-partitioning-keys-unique-keys.html "26.6.1 Partitioning Keys, Primary Keys, and Unique Keys").

This table can be partitioned by range in a number of ways,
depending on your needs. One way would be to use the
`store_id` column. For instance, you might
decide to partition the table 4 ways by adding a
`PARTITION BY RANGE` clause as shown here:


```sql
CREATE TABLE employees (
    id INT NOT NULL,
    fname VARCHAR(30),
    lname VARCHAR(30),
    hired DATE NOT NULL DEFAULT '1970-01-01',
    separated DATE NOT NULL DEFAULT '9999-12-31',
    job_code INT NOT NULL,
    store_id INT NOT NULL
)
PARTITION BY RANGE (store_id) (
    PARTITION p0 VALUES LESS THAN (6),
    PARTITION p1 VALUES LESS THAN (11),
    PARTITION p2 VALUES LESS THAN (16),
    PARTITION p3 VALUES LESS THAN (21)
);
```

In this partitioning scheme, all rows corresponding to employees
working at stores 1 through 5 are stored in partition
`p0`, to those employed at stores 6 through 10
are stored in partition `p1`, and so on. Each
partition is defined in order, from lowest to highest. This is a
requirement of the `PARTITION BY RANGE` syntax;
you can think of it as being analogous to a series of
`if ... elseif ...` statements in C or Java in
this regard.


It is easy to determine that a new row containing the data
`(72, 'Mitchell', 'Wilson', '1998-06-25', DEFAULT, 7,
        13)` is inserted into partition `p2`,
but what happens when your chain adds a
21st store? Under this scheme, there
is no rule that covers a row whose `store_id`
is greater than 20, so an error results because the server does
not know where to place it. You can keep this from occurring by
using a “catchall” `VALUES LESS
        THAN` clause in the [`CREATE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement that provides for all values greater
than the highest value explicitly named:


```sql
CREATE TABLE employees (
    id INT NOT NULL,
    fname VARCHAR(30),
    lname VARCHAR(30),
    hired DATE NOT NULL DEFAULT '1970-01-01',
    separated DATE NOT NULL DEFAULT '9999-12-31',
    job_code INT NOT NULL,
    store_id INT NOT NULL
)
PARTITION BY RANGE (store_id) (
    PARTITION p0 VALUES LESS THAN (6),
    PARTITION p1 VALUES LESS THAN (11),
    PARTITION p2 VALUES LESS THAN (16),
    PARTITION p3 VALUES LESS THAN MAXVALUE
);
```

(As with the other examples in this chapter, we assume that the
default storage engine is `InnoDB`.)


Another way to avoid an error when no matching value is found is
to use the `IGNORE` keyword as part of the
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement. For an example,
see [Section 26.2.2, “LIST Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html "26.2.2 LIST Partitioning").


`MAXVALUE` represents an integer value that is
always greater than the largest possible integer value (in
mathematical language, it serves as a
least upper bound). Now,
any rows whose `store_id` column value is
greater than or equal to 16 (the highest value defined) are
stored in partition `p3`. At some point in the
future—when the number of stores has increased to 25, 30,
or more—you can use an
[`ALTER\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table-partition-operations.html "15.1.9.1 ALTER TABLE Partition Operations") statement to add new partitions for stores
21-25, 26-30, and so on (see
[Section 26.3, “Partition Management”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html "26.3 Partition Management"), for details of how to
do this).


In much the same fashion, you could partition the table based on
employee job codes—that is, based on ranges of
`job_code` column values. For
example—assuming that two-digit job codes are used for
regular (in-store) workers, three-digit codes are used for
office and support personnel, and four-digit codes are used for
management positions—you could create the partitioned
table using the following statement:


```sql
CREATE TABLE employees (
    id INT NOT NULL,
    fname VARCHAR(30),
    lname VARCHAR(30),
    hired DATE NOT NULL DEFAULT '1970-01-01',
    separated DATE NOT NULL DEFAULT '9999-12-31',
    job_code INT NOT NULL,
    store_id INT NOT NULL
)
PARTITION BY RANGE (job_code) (
    PARTITION p0 VALUES LESS THAN (100),
    PARTITION p1 VALUES LESS THAN (1000),
    PARTITION p2 VALUES LESS THAN (10000)
);
```

In this instance, all rows relating to in-store workers would be
stored in partition `p0`, those relating to
office and support staff in `p1`, and those
relating to managers in partition `p2`.


It is also possible to use an expression in `VALUES LESS
        THAN` clauses. However, MySQL must be able to evaluate
the expression's return value as part of a `LESS
        THAN` ( `<`) comparison.


Rather than splitting up the table data according to store
number, you can use an expression based on one of the two
[`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") columns instead. For
example, let us suppose that you wish to partition based on the
year that each employee left the company; that is, the value of
[`YEAR(separated)`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_year). An example of a
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement that
implements such a partitioning scheme is shown here:


```sql
CREATE TABLE employees (
    id INT NOT NULL,
    fname VARCHAR(30),
    lname VARCHAR(30),
    hired DATE NOT NULL DEFAULT '1970-01-01',
    separated DATE NOT NULL DEFAULT '9999-12-31',
    job_code INT,
    store_id INT
)
PARTITION BY RANGE ( YEAR(separated) ) (
    PARTITION p0 VALUES LESS THAN (1991),
    PARTITION p1 VALUES LESS THAN (1996),
    PARTITION p2 VALUES LESS THAN (2001),
    PARTITION p3 VALUES LESS THAN MAXVALUE
);
```

In this scheme, for all employees who left before 1991, the rows
are stored in partition `p0`; for those who
left in the years 1991 through 1995, in `p1`;
for those who left in the years 1996 through 2000, in
`p2`; and for any workers who left after the
year 2000, in `p3`.


It is also possible to partition a table by
`RANGE`, based on the value of a
[`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") column, using the
[`UNIX_TIMESTAMP()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_unix-timestamp) function, as
shown in this example:


```sql
CREATE TABLE quarterly_report_status (
    report_id INT NOT NULL,
    report_status VARCHAR(20) NOT NULL,
    report_updated TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
)
PARTITION BY RANGE ( UNIX_TIMESTAMP(report_updated) ) (
    PARTITION p0 VALUES LESS THAN ( UNIX_TIMESTAMP('2008-01-01 00:00:00') ),
    PARTITION p1 VALUES LESS THAN ( UNIX_TIMESTAMP('2008-04-01 00:00:00') ),
    PARTITION p2 VALUES LESS THAN ( UNIX_TIMESTAMP('2008-07-01 00:00:00') ),
    PARTITION p3 VALUES LESS THAN ( UNIX_TIMESTAMP('2008-10-01 00:00:00') ),
    PARTITION p4 VALUES LESS THAN ( UNIX_TIMESTAMP('2009-01-01 00:00:00') ),
    PARTITION p5 VALUES LESS THAN ( UNIX_TIMESTAMP('2009-04-01 00:00:00') ),
    PARTITION p6 VALUES LESS THAN ( UNIX_TIMESTAMP('2009-07-01 00:00:00') ),
    PARTITION p7 VALUES LESS THAN ( UNIX_TIMESTAMP('2009-10-01 00:00:00') ),
    PARTITION p8 VALUES LESS THAN ( UNIX_TIMESTAMP('2010-01-01 00:00:00') ),
    PARTITION p9 VALUES LESS THAN (MAXVALUE)
);
```

Any other expressions involving
[`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") values are not
permitted. (See Bug #42849.)


Range partitioning is particularly useful when one or more of
the following conditions is true:

- You want or need to delete “old” data. If you
are using the partitioning scheme shown previously for the
`employees` table, you can simply use
`ALTER TABLE employees DROP PARTITION p0;`
to delete all rows relating to employees who stopped working
for the firm prior to 1991. (See
[Section 15.1.9, “ALTER TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement"), and
[Section 26.3, “Partition Management”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html "26.3 Partition Management"), for more
information.) For a table with a great many rows, this can
be much more efficient than running a
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") query such as
`DELETE FROM employees WHERE YEAR(separated) <=
              1990;`.


- You want to use a column containing date or time values, or
containing values arising from some other series.


- You frequently run queries that depend directly on the
column used for partitioning the table. For example, when
executing a query such as
[`EXPLAIN SELECT\\
              COUNT(*) FROM employees WHERE separated BETWEEN '2000-01-01'\\
              AND '2000-12-31' GROUP BY store_id;`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement"), MySQL can
quickly determine that only partition `p2`
needs to be scanned because the remaining partitions cannot
contain any records satisfying the `WHERE`
clause. See [Section 26.4, “Partition Pruning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-pruning.html "26.4 Partition Pruning"), for more
information about how this is accomplished.


A variant on this type of partitioning is `RANGE
        COLUMNS` partitioning. Partitioning by `RANGE
        COLUMNS` makes it possible to employ multiple columns
for defining partitioning ranges that apply both to placement of
rows in partitions and for determining the inclusion or
exclusion of specific partitions when performing partition
pruning. See [Section 26.2.3.1, “RANGE COLUMNS partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-columns-range.html "26.2.3.1 RANGE COLUMNS partitioning"), for
more information.


**Partitioning schemes based on time intervals.**
If you wish to implement a partitioning scheme based on ranges
or intervals of time in MySQL 8.0, you have two
options:

1. Partition the table by `RANGE`, and for the
    partitioning expression, employ a function operating on a
    [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"),
    [`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type"), or
    [`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") column and returning
    an integer value, as shown here:



```sql
CREATE TABLE members (
       firstname VARCHAR(25) NOT NULL,
       lastname VARCHAR(25) NOT NULL,
       username VARCHAR(16) NOT NULL,
       email VARCHAR(35),
       joined DATE NOT NULL
)
PARTITION BY RANGE( YEAR(joined) ) (
       PARTITION p0 VALUES LESS THAN (1960),
       PARTITION p1 VALUES LESS THAN (1970),
       PARTITION p2 VALUES LESS THAN (1980),
       PARTITION p3 VALUES LESS THAN (1990),
       PARTITION p4 VALUES LESS THAN MAXVALUE
);
```



    In MySQL 8.0, it is also possible to partition
    a table by `RANGE` based on the value of a
    [`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") column, using the
    [`UNIX_TIMESTAMP()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_unix-timestamp) function, as
    shown in this example:



```sql
CREATE TABLE quarterly_report_status (
       report_id INT NOT NULL,
       report_status VARCHAR(20) NOT NULL,
       report_updated TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
)
PARTITION BY RANGE ( UNIX_TIMESTAMP(report_updated) ) (
       PARTITION p0 VALUES LESS THAN ( UNIX_TIMESTAMP('2008-01-01 00:00:00') ),
       PARTITION p1 VALUES LESS THAN ( UNIX_TIMESTAMP('2008-04-01 00:00:00') ),
       PARTITION p2 VALUES LESS THAN ( UNIX_TIMESTAMP('2008-07-01 00:00:00') ),
       PARTITION p3 VALUES LESS THAN ( UNIX_TIMESTAMP('2008-10-01 00:00:00') ),
       PARTITION p4 VALUES LESS THAN ( UNIX_TIMESTAMP('2009-01-01 00:00:00') ),
       PARTITION p5 VALUES LESS THAN ( UNIX_TIMESTAMP('2009-04-01 00:00:00') ),
       PARTITION p6 VALUES LESS THAN ( UNIX_TIMESTAMP('2009-07-01 00:00:00') ),
       PARTITION p7 VALUES LESS THAN ( UNIX_TIMESTAMP('2009-10-01 00:00:00') ),
       PARTITION p8 VALUES LESS THAN ( UNIX_TIMESTAMP('2010-01-01 00:00:00') ),
       PARTITION p9 VALUES LESS THAN (MAXVALUE)
);
```



    In MySQL 8.0, any other expressions involving
    [`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") values are not
    permitted. (See Bug #42849.)





Note





It is also possible in MySQL 8.0 to use
[`UNIX_TIMESTAMP(timestamp_column)`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_unix-timestamp)
as a partitioning expression for tables that are
partitioned by `LIST`. However, it is
usually not practical to do so.

2. Partition the table by `RANGE COLUMNS`,
    using a [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") or
    [`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") column as the
    partitioning column. For example, the
    `members` table could be defined using the
    `joined` column directly, as shown here:



```sql
CREATE TABLE members (
       firstname VARCHAR(25) NOT NULL,
       lastname VARCHAR(25) NOT NULL,
       username VARCHAR(16) NOT NULL,
       email VARCHAR(35),
       joined DATE NOT NULL
)
PARTITION BY RANGE COLUMNS(joined) (
       PARTITION p0 VALUES LESS THAN ('1960-01-01'),
       PARTITION p1 VALUES LESS THAN ('1970-01-01'),
       PARTITION p2 VALUES LESS THAN ('1980-01-01'),
       PARTITION p3 VALUES LESS THAN ('1990-01-01'),
       PARTITION p4 VALUES LESS THAN MAXVALUE
);
```


Note

The use of partitioning columns employing date or time types
other than [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") or
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") is not supported with
`RANGE COLUMNS`.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "Previous: Partitioning Types") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "Up: Partitioning Types") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html "Next: LIST Partitioning")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html)

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