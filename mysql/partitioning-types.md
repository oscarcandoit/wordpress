---
url: https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html
scraped_at: 2025-10-20T03:04:34.673Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "Hide Sidebar")

[Previous: Overview of Partitioning in MySQL](https://dev.mysql.com/doc/refman/8.0/en/partitioning-overview.html "Previous: Overview of Partitioning in MySQL")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html "Up: Partitioning")[Next: RANGE Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html "Next: RANGE Partitioning")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/partitioning-types.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/partitioning-types.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/partitioning-types.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/partitioning-types.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/partitioning-types.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/partitioning-types.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/partitioning-types.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/partitioning-types.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)  /
Partitioning Types


## 26.2 Partitioning Types

[26.2.1 RANGE Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html)[26.2.2 LIST Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html)[26.2.3 COLUMNS Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-columns.html)[26.2.4 HASH Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html)[26.2.5 KEY Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html)[26.2.6 Subpartitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-subpartitions.html)[26.2.7 How MySQL Partitioning Handles NULL](https://dev.mysql.com/doc/refman/8.0/en/partitioning-handling-nulls.html)

This section discusses the types of partitioning which are
available in MySQL 8.0. These include the types
listed here:

- **RANGE partitioning.**
This type of partitioning assigns rows to partitions based
on column values falling within a given range. See
[Section 26.2.1, “RANGE Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html "26.2.1 RANGE Partitioning"). For information about
an extension to this type, `RANGE COLUMNS`,
see [Section 26.2.3.1, “RANGE COLUMNS partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-columns-range.html "26.2.3.1 RANGE COLUMNS partitioning").


- **LIST partitioning.**
Similar to partitioning by `RANGE`, except
that the partition is selected based on columns matching one
of a set of discrete values. See
[Section 26.2.2, “LIST Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html "26.2.2 LIST Partitioning"). For information about
an extension to this type, `LIST COLUMNS`,
see [Section 26.2.3.2, “LIST COLUMNS partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-columns-list.html "26.2.3.2 LIST COLUMNS partitioning").


- **HASH partitioning.**
With this type of partitioning, a partition is selected
based on the value returned by a user-defined expression
that operates on column values in rows to be inserted into
the table. The function may consist of any expression valid
in MySQL that yields an integer value. See
[Section 26.2.4, “HASH Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html "26.2.4 HASH Partitioning").



An extension to this type, `LINEAR HASH`, is
also available, see
[Section 26.2.4.1, “LINEAR HASH Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-linear-hash.html "26.2.4.1 LINEAR HASH Partitioning").


- **KEY partitioning.**
This type of partitioning is similar to partitioning by
`HASH`, except that only one or more
columns to be evaluated are supplied, and the MySQL server
provides its own hashing function. These columns can contain
other than integer values, since the hashing function
supplied by MySQL guarantees an integer result regardless of
the column data type. An extension to this type,
`LINEAR KEY`, is also available. See
[Section 26.2.5, “KEY Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html "26.2.5 KEY Partitioning").


A very common use of database partitioning is to segregate data by
date. Some database systems support explicit date partitioning,
which MySQL does not implement in 8.0. However, it is
not difficult in MySQL to create partitioning schemes based on
[`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"),
[`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type"), or
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") columns, or based on
expressions making use of such columns.


When partitioning by `KEY` or `LINEAR
      KEY`, you can use a [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"),
[`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type"), or
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") column as the partitioning
column without performing any modification of the column value.
For example, this table creation statement is perfectly valid in
MySQL:


``` sql

CREATE TABLE members (
    firstname VARCHAR(25) NOT NULL,
    lastname VARCHAR(25) NOT NULL,
    username VARCHAR(16) NOT NULL,
    email VARCHAR(35),
    joined DATE NOT NULL
)
PARTITION BY KEY(joined)
PARTITIONS 6;
```

In MySQL 8.0, it is also possible to use a
[`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") or
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") column as the partitioning
column using `RANGE COLUMNS` and `LIST
      COLUMNS` partitioning.


Other partitioning types require a partitioning expression that
yields an integer value or `NULL`. If you wish to
use date-based partitioning by `RANGE`,
`LIST`, `HASH`, or
`LINEAR HASH`, you can simply employ a function
that operates on a [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"),
[`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type"), or
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") column and returns such a
value, as shown here:


``` sql

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

Additional examples of partitioning using dates may be found in
the following sections of this chapter:

- [Section 26.2.1, “RANGE Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html "26.2.1 RANGE Partitioning")

- [Section 26.2.4, “HASH Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html "26.2.4 HASH Partitioning")

- [Section 26.2.4.1, “LINEAR HASH Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-linear-hash.html "26.2.4.1 LINEAR HASH Partitioning")


For more complex examples of date-based partitioning, see the
following sections:

- [Section 26.4, “Partition Pruning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-pruning.html "26.4 Partition Pruning")

- [Section 26.2.6, “Subpartitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-subpartitions.html "26.2.6 Subpartitioning")


MySQL partitioning is optimized for use with the
[`TO_DAYS()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_to-days),
[`YEAR()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_year), and
[`TO_SECONDS()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_to-seconds) functions. However,
you can use other date and time functions that return an integer
or `NULL`, such as
[`WEEKDAY()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_weekday),
[`DAYOFYEAR()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_dayofyear), or
[`MONTH()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_month). See
[Section 14.7, “Date and Time Functions”](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html "14.7 Date and Time Functions"), for more information
about such functions.


It is important to remember—regardless of the type of
partitioning that you use—that partitions are always
numbered automatically and in sequence when created, starting with
`0`. When a new row is inserted into a
partitioned table, it is these partition numbers that are used in
identifying the correct partition. For example, if your table uses
4 partitions, these partitions are numbered `0`,
`1`, `2`, and
`3`. For the `RANGE` and
`LIST` partitioning types, it is necessary to
ensure that there is a partition defined for each partition
number. For `HASH` partitioning, the
user-supplied expression must evaluate to an integer value. For
`KEY` partitioning, this issue is taken care of
automatically by the hashing function which the MySQL server
employs internally.


Names of partitions generally follow the rules governing other
MySQL identifiers, such as those for tables and databases.
However, you should note that partition names are not
case-sensitive. For example, the following
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement fails as
shown:


``` sql

mysql> CREATE TABLE t2 (val INT)
    -> PARTITION BY LIST(val)(
    ->     PARTITION mypart VALUES IN (1,3,5),
    ->     PARTITION MyPart VALUES IN (2,4,6)
    -> );
ERROR 1488 (HY000): Duplicate partition name mypart
```

Failure occurs because MySQL sees no difference between the
partition names `mypart` and
`MyPart`.


When you specify the number of partitions for the table, this must
be expressed as a positive, nonzero integer literal with no
leading zeros, and may not be an expression such as
`0.8E+01` or `6-2`, even if it
evaluates to an integer value. Decimal fractions are not
permitted.


In the sections that follow, we do not necessarily provide all
possible forms for the syntax that can be used for creating each
partition type; for this information, see
[Section 15.1.20, “CREATE TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/partitioning-overview.html "Previous: Overview of Partitioning in MySQL") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html "Up: Partitioning") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html "Next: RANGE Partitioning")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html)

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