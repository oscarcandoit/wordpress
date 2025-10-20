---
url: https://dev.mysql.com/doc/refman/8.0/en/subqueries.html
scraped_at: 2025-10-20T02:58:54.258Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/subqueries.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/subqueries.html "Hide Sidebar")

[Previous: Set Operations with UNION, INTERSECT, and EXCEPT](https://dev.mysql.com/doc/refman/8.0/en/set-operations.html "Previous: Set Operations with UNION, INTERSECT, and EXCEPT")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Up: Data Manipulation Statements")[Next: The Subquery as Scalar Operand](https://dev.mysql.com/doc/refman/8.0/en/scalar-subqueries.html "Next: The Subquery as Scalar Operand")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/subqueries.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/subqueries.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/subqueries.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/subqueries.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/subqueries.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/subqueries.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/subqueries.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/subqueries.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/subqueries.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/subqueries.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/subqueries.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/subqueries.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/subqueries.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/subqueries.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html)  /

Subqueries


### 15.2.15 Subqueries

[15.2.15.1 The Subquery as Scalar Operand](https://dev.mysql.com/doc/refman/8.0/en/scalar-subqueries.html)[15.2.15.2 Comparisons Using Subqueries](https://dev.mysql.com/doc/refman/8.0/en/comparisons-using-subqueries.html)[15.2.15.3 Subqueries with ANY, IN, or SOME](https://dev.mysql.com/doc/refman/8.0/en/any-in-some-subqueries.html)[15.2.15.4 Subqueries with ALL](https://dev.mysql.com/doc/refman/8.0/en/all-subqueries.html)[15.2.15.5 Row Subqueries](https://dev.mysql.com/doc/refman/8.0/en/row-subqueries.html)[15.2.15.6 Subqueries with EXISTS or NOT EXISTS](https://dev.mysql.com/doc/refman/8.0/en/exists-and-not-exists-subqueries.html)[15.2.15.7 Correlated Subqueries](https://dev.mysql.com/doc/refman/8.0/en/correlated-subqueries.html)[15.2.15.8 Derived Tables](https://dev.mysql.com/doc/refman/8.0/en/derived-tables.html)[15.2.15.9 Lateral Derived Tables](https://dev.mysql.com/doc/refman/8.0/en/lateral-derived-tables.html)[15.2.15.10 Subquery Errors](https://dev.mysql.com/doc/refman/8.0/en/subquery-errors.html)[15.2.15.11 Optimizing Subqueries](https://dev.mysql.com/doc/refman/8.0/en/optimizing-subqueries.html)[15.2.15.12 Restrictions on Subqueries](https://dev.mysql.com/doc/refman/8.0/en/subquery-restrictions.html)

A subquery is a [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement
within another statement.


All subquery forms and operations that the SQL standard requires
are supported, as well as a few features that are MySQL-specific.


Here is an example of a subquery:


``` sql

SELECT * FROM t1 WHERE column1 = (SELECT column1 FROM t2);
```

In this example, `SELECT * FROM t1 ...` is the
_outer query_ (or _outer_
_statement_), and `(SELECT column1 FROM
      t2)` is the _subquery_. We say that
the subquery is _nested_ within the outer
query, and in fact it is possible to nest subqueries within other
subqueries, to a considerable depth. A subquery must always appear
within parentheses.


The main advantages of subqueries are:

- They allow queries that are _structured_ so
that it is possible to isolate each part of a statement.


- They provide alternative ways to perform operations that would
otherwise require complex joins and unions.


- Many people find subqueries more readable than complex joins
or unions. Indeed, it was the innovation of subqueries that
gave people the original idea of calling the early SQL
“Structured Query Language.”


Here is an example statement that shows the major points about
subquery syntax as specified by the SQL standard and supported in
MySQL:


``` sql

DELETE FROM t1
WHERE s11 > ANY
 (SELECT COUNT(*) /* no hint */ FROM t2
  WHERE NOT EXISTS
   (SELECT * FROM t3
    WHERE ROW(5*t2.s1,77)=
     (SELECT 50,11*s1 FROM t4 UNION SELECT 50,77 FROM
      (SELECT * FROM t5) AS t5)));
```

A subquery can return a scalar (a single value), a single row, a
single column, or a table (one or more rows of one or more
columns). These are called scalar, column, row, and table
subqueries. Subqueries that return a particular kind of result
often can be used only in certain contexts, as described in the
following sections.


There are few restrictions on the type of statements in which
subqueries can be used. A subquery can contain many of the
keywords or clauses that an ordinary
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") can contain:
`DISTINCT`, `GROUP BY`,
`ORDER BY`, `LIMIT`, joins,
index hints, [`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause") constructs,
comments, functions, and so on.


Beginning with MySQL 8.0.19, [`TABLE`](https://dev.mysql.com/doc/refman/8.0/en/table.html "15.2.16 TABLE Statement")
and [`VALUES`](https://dev.mysql.com/doc/refman/8.0/en/values.html "15.2.19 VALUES Statement") statements can be used
in subqueries. Subqueries using
[`VALUES`](https://dev.mysql.com/doc/refman/8.0/en/values.html "15.2.19 VALUES Statement") are generally more verbose
versions of subqueries that can be rewritten more compactly using
set notation, or with [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") or
[`TABLE`](https://dev.mysql.com/doc/refman/8.0/en/table.html "15.2.16 TABLE Statement") syntax; assuming that table
`ts` is created using the statement
[`CREATE TABLE\\
      ts VALUES ROW(2), ROW(4), ROW(6)`](https://dev.mysql.com/doc/refman/8.0/en/create-table-select.html "15.1.20.4 CREATE TABLE ... SELECT Statement"), the statements shown
here are all equivalent:


``` sql

SELECT * FROM tt
    WHERE b > ANY (VALUES ROW(2), ROW(4), ROW(6));

SELECT * FROM tt
    WHERE b > ANY (SELECT * FROM ts);

SELECT * FROM tt
    WHERE b > ANY (TABLE ts);
```

Examples of [`TABLE`](https://dev.mysql.com/doc/refman/8.0/en/table.html "15.2.16 TABLE Statement") subqueries are
shown in the sections that follow.


A subquery's outer statement can be any one of:
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"),
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"),
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"),
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"),
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment"), or
[`DO`](https://dev.mysql.com/doc/refman/8.0/en/do.html "15.2.3 DO Statement").


For information about how the optimizer handles subqueries, see
[Section 10.2.2, “Optimizing Subqueries, Derived Tables, View References, and Common Table\\
Expressions”](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization.html "10.2.2 Optimizing Subqueries, Derived Tables, View References, and Common Table Expressions"). For a discussion of
restrictions on subquery use, including performance issues for
certain forms of subquery syntax, see
[Section 15.2.15.12, “Restrictions on Subqueries”](https://dev.mysql.com/doc/refman/8.0/en/subquery-restrictions.html "15.2.15.12 Restrictions on Subqueries").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/set-operations.html "Previous: Set Operations with UNION, INTERSECT, and EXCEPT") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Up: Data Manipulation Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/scalar-subqueries.html "Next: The Subquery as Scalar Operand")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/subqueries.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/subqueries.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/subqueries.html)

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