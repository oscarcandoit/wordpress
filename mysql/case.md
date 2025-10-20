---
url: https://dev.mysql.com/doc/refman/8.0/en/case.html
scraped_at: 2025-10-20T03:09:13.934Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/case.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/case.html "Hide Sidebar")

[Previous: Flow Control Statements](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html "Previous: Flow Control Statements")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Flow Control Statements](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html "Up: Flow Control Statements")[Next: IF Statement](https://dev.mysql.com/doc/refman/8.0/en/if.html "Next: IF Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/case.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/case.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/case.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/case.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/case.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/case.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/case.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/case.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/case.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/case.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/case.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/case.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/case.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/case.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Compound Statement Syntax](https://dev.mysql.com/doc/refman/8.0/en/sql-compound-statements.html)  /
[Flow Control Statements](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html)  /

CASE Statement


#### 15.6.5.1 CASE Statement

```sql
CASE case_value
    WHEN when_value THEN statement_list
    [WHEN when_value THEN statement_list] ...
    [ELSE statement_list]
END CASE
```

Or:


```sql
CASE
    WHEN search_condition THEN statement_list
    [WHEN search_condition THEN statement_list] ...
    [ELSE statement_list]
END CASE
```

The [`CASE`](https://dev.mysql.com/doc/refman/8.0/en/case.html "15.6.5.1 CASE Statement") statement for stored
programs implements a complex conditional construct.

Note

There is also a [`CASE`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#operator_case) _operator_, which differs from the
[`CASE`](https://dev.mysql.com/doc/refman/8.0/en/case.html "15.6.5.1 CASE Statement") _statement_ described here. See
[Section 14.5, “Flow Control Functions”](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html "14.5 Flow Control Functions"). The
[`CASE`](https://dev.mysql.com/doc/refman/8.0/en/case.html "15.6.5.1 CASE Statement") statement cannot have an
`ELSE NULL` clause, and it is terminated with
`END CASE` instead of `END`.

For the first syntax, _`case_value`_ is
an expression. This value is compared to the
_`when_value`_ expression in each
`WHEN` clause until one of them is equal. When
an equal _`when_value`_ is found, the
corresponding `THEN` clause
_`statement_list`_ executes. If no
_`when_value`_ is equal, the
`ELSE` clause
_`statement_list`_ executes, if there is
one.


This syntax cannot be used to test for equality with
`NULL` because `NULL = NULL`
is false. See [Section 5.3.4.6, “Working with NULL Values”](https://dev.mysql.com/doc/refman/8.0/en/working-with-null.html "5.3.4.6 Working with NULL Values").


For the second syntax, each `WHEN` clause
_`search_condition`_ expression is
evaluated until one is true, at which point its corresponding
`THEN` clause
_`statement_list`_ executes. If no
_`search_condition`_ is equal, the
`ELSE` clause
_`statement_list`_ executes, if there is
one.


If no _`when_value`_ or
_`search_condition`_ matches the value
tested and the [`CASE`](https://dev.mysql.com/doc/refman/8.0/en/case.html "15.6.5.1 CASE Statement") statement
contains no `ELSE` clause, a Case
not found for CASE statement error results.


Each _`statement_list`_ consists of one
or more SQL statements; an empty
_`statement_list`_ is not permitted.


To handle situations where no value is matched by any
`WHEN` clause, use an `ELSE`
containing an empty
[`BEGIN ...\\
        END`](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement") block, as shown in this example. (The indentation
used here in the `ELSE` clause is for purposes
of clarity only, and is not otherwise significant.)


```sql
DELIMITER |

CREATE PROCEDURE p()
  BEGIN
    DECLARE v INT DEFAULT 1;

    CASE v
      WHEN 2 THEN SELECT v;
      WHEN 3 THEN SELECT 0;
      ELSE
        BEGIN
        END;
    END CASE;
  END;
  |
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html "Previous: Flow Control Statements") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html "Up: Flow Control Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/if.html "Next: IF Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/case.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/case.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/case.html)

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