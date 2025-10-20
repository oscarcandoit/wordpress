---
url: https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html
scraped_at: 2025-10-20T03:04:45.850Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html "Hide Sidebar")

[Previous: LIST COLUMNS partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-columns-list.html "Previous: LIST COLUMNS partitioning")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Partitioning Types](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "Up: Partitioning Types")[Next: LINEAR HASH Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-linear-hash.html "Next: LINEAR HASH Partitioning")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/partitioning-hash.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/partitioning-hash.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/partitioning-hash.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/partitioning-hash.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/partitioning-hash.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/partitioning-hash.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/partitioning-hash.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/partitioning-hash.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html)  / [Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)  /
[Partitioning Types](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html)  /

HASH Partitioning


### 26.2.4 HASH Partitioning

[26.2.4.1 LINEAR HASH Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-linear-hash.html)

Partitioning by `HASH` is used primarily to
ensure an even distribution of data among a predetermined number
of partitions. With range or list partitioning, you must specify
explicitly which partition a given column value or set of column
values should be stored in; with hash partitioning, this
decision is taken care of for you, and you need only specify a
column value or expression based on a column value to be hashed
and the number of partitions into which the partitioned table is
to be divided.


To partition a table using `HASH` partitioning,
it is necessary to append to the [`CREATE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement a `PARTITION BY HASH
        (expr)` clause, where
_`expr`_ is an expression that returns an
integer. This can simply be the name of a column whose type is
one of MySQL's integer types. In addition, you most likely
want to follow this with `PARTITIONS
        num`, where
_`num`_ is a positive integer
representing the number of partitions into which the table is to
be divided.

Note

For simplicity, the tables in the examples that follow do not
use any keys. You should be aware that, if a table has any
unique keys, every column used in the partitioning expression
for this table must be part of every unique key, including the
primary key. See
[Section 26.6.1, “Partitioning Keys, Primary Keys, and Unique Keys”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-limitations-partitioning-keys-unique-keys.html "26.6.1 Partitioning Keys, Primary Keys, and Unique Keys"),
for more information.

The following statement creates a table that uses hashing on the
`store_id` column and is divided into 4
partitions:


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
PARTITION BY HASH(store_id)
PARTITIONS 4;
```

If you do not include a `PARTITIONS` clause,
the number of partitions defaults to `1`; using
the `PARTITIONS` keyword without a number
following it results in a syntax error.


You can also use an SQL expression that returns an integer for
_`expr`_. For instance, you might want to
partition based on the year in which an employee was hired. This
can be done as shown here:


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
PARTITION BY HASH( YEAR(hired) )
PARTITIONS 4;
```

_`expr`_ must return a nonconstant,
nonrandom integer value (in other words, it should be varying
but deterministic), and must not contain any prohibited
constructs as described in
[Section 26.6, “Restrictions and Limitations on Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-limitations.html "26.6 Restrictions and Limitations on Partitioning"). You should also keep
in mind that this expression is evaluated each time a row is
inserted or updated (or possibly deleted); this means that very
complex expressions may give rise to performance issues,
particularly when performing operations (such as batch inserts)
that affect a great many rows at one time.


The most efficient hashing function is one which operates upon a
single table column and whose value increases or decreases
consistently with the column value, as this allows for
“pruning” on ranges of partitions. That is, the
more closely that the expression varies with the value of the
column on which it is based, the more efficiently MySQL can use
the expression for hash partitioning.


For example, where `date_col` is a column of
type [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"), then the expression
[`TO_DAYS(date_col)`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_to-days) is said to vary
directly with the value of `date_col`, because
for every change in the value of `date_col`,
the value of the expression changes in a consistent manner. The
variance of the expression
[`YEAR(date_col)`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_year) with respect to
`date_col` is not quite as direct as that of
[`TO_DAYS(date_col)`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_to-days), because not
every possible change in `date_col` produces an
equivalent change in
[`YEAR(date_col)`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_year). Even so,
[`YEAR(date_col)`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_year) is a good
candidate for a hashing function, because it varies directly
with a portion of `date_col` and there is no
possible change in `date_col` that produces a
disproportionate change in
[`YEAR(date_col)`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_year).


By way of contrast, suppose that you have a column named
`int_col` whose type is
[`INT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT"). Now consider the expression
[`POW(5-int_col,3) + 6`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_pow). This would
be a poor choice for a hashing function because a change in the
value of `int_col` is not guaranteed to produce
a proportional change in the value of the expression. Changing
the value of `int_col` by a given amount can
produce widely differing changes in the value of the expression.
For example, changing `int_col` from
`5` to `6` produces a change
of `-1` in the value of the expression, but
changing the value of `int_col` from
`6` to `7` produces a change
of `-7` in the expression value.


In other words, the more closely the graph of the column value
versus the value of the expression follows a straight line as
traced by the equation
`y=cx` where
_`c`_ is some nonzero constant, the
better the expression is suited to hashing. This has to do with
the fact that the more nonlinear an expression is, the more
uneven the distribution of data among the partitions it tends to
produce.


In theory, pruning is also possible for expressions involving
more than one column value, but determining which of such
expressions are suitable can be quite difficult and
time-consuming. For this reason, the use of hashing expressions
involving multiple columns is not particularly recommended.


When `PARTITION BY HASH` is used, the storage
engine determines which partition of
_`num`_ partitions to use based on the
modulus of the result of the expression. In other words, for a
given expression _`expr`_, the partition
in which the record is stored is partition number
_`N`_, where
`N =
        MOD(expr,
        num)`. Suppose that table
`t1` is defined as follows, so that it has 4
partitions:


```sql
CREATE TABLE t1 (col1 INT, col2 CHAR(5), col3 DATE)
    PARTITION BY HASH( YEAR(col3) )
    PARTITIONS 4;
```

If you insert a record into `t1` whose
`col3` value is
`'2005-09-15'`, then the partition in which it
is stored is determined as follows:


```sql
MOD(YEAR('2005-09-01'),4)
=  MOD(2005,4)
=  1
```

MySQL 8.0 also supports a variant of
`HASH` partitioning known as
linear hashing which
employs a more complex algorithm for determining the placement
of new rows inserted into the partitioned table. See
[Section 26.2.4.1, “LINEAR HASH Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-linear-hash.html "26.2.4.1 LINEAR HASH Partitioning"), for a description of
this algorithm.


The user-supplied expression is evaluated each time a record is
inserted or updated. It may also—depending on the
circumstances—be evaluated when records are deleted.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/partitioning-columns-list.html "Previous: LIST COLUMNS partitioning") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "Up: Partitioning Types") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/partitioning-linear-hash.html "Next: LINEAR HASH Partitioning")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html)

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