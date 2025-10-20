---
url: https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html
scraped_at: 2025-10-20T03:02:17.096Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html "Hide Sidebar")

[Previous: Comparison Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html "Previous: Comparison Functions and Operators")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Operators](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html "Up: Operators")[Next: Assignment Operators](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html "Next: Assignment Operators")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/logical-operators.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/logical-operators.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/logical-operators.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/logical-operators.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/logical-operators.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/logical-operators.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/logical-operators.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/logical-operators.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html)  / [Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html)  /
[Operators](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html)  /

Logical Operators


### 14.4.3 Logical Operators

**Table 14.5 Logical Operators**

| Name | Description |
| --- | --- |
| [`AND`, `&&`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_and) | Logical AND |
| [`NOT`, `!`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_not) | Negates value |
| [`OR`, `||`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_or) | Logical OR |
| [`XOR`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_xor) | Logical XOR |

In SQL, all logical operators evaluate to
`TRUE`, `FALSE`, or
`NULL` ( `UNKNOWN`). In MySQL,
these are implemented as 1 ( `TRUE`), 0
( `FALSE`), and `NULL`. Most of
this is common to different SQL database servers, although some
servers may return any nonzero value for
`TRUE`.


MySQL evaluates any nonzero, non- `NULL` value
to `TRUE`. For example, the following
statements all assess to `TRUE`:


```sql
mysql> SELECT 10 IS TRUE;
-> 1
mysql> SELECT -10 IS TRUE;
-> 1
mysql> SELECT 'string' IS NOT NULL;
-> 1
```

- [`NOT`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_not),
[`!`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_not)


Logical NOT. Evaluates to `1` if the
operand is `0`, to `0` if
the operand is nonzero, and `NOT NULL`
returns `NULL`.



```sql
mysql> SELECT NOT 10;
          -> 0
mysql> SELECT NOT 0;
          -> 1
mysql> SELECT NOT NULL;
          -> NULL
mysql> SELECT ! (1+1);
          -> 0
mysql> SELECT ! 1+1;
          -> 1
```



The last example produces `1` because the
expression evaluates the same way as
`(!1)+1`.



The [`!`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_not), operator
is a nonstandard MySQL extension. As of MySQL 8.0.17, this
operator is deprecated; expect it to be removed in a future
version of MySQL. Applications should be adjusted to use the
standard SQL [`NOT`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_not) operator.


- [`AND`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_and),
[`&&`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_and)


Logical AND. Evaluates to `1` if all
operands are nonzero and not `NULL`, to
`0` if one or more operands are
`0`, otherwise `NULL` is
returned.



```sql
mysql> SELECT 1 AND 1;
          -> 1
mysql> SELECT 1 AND 0;
          -> 0
mysql> SELECT 1 AND NULL;
          -> NULL
mysql> SELECT 0 AND NULL;
          -> 0
mysql> SELECT NULL AND 0;
          -> 0
```



The [`&&`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_and),
operator is a nonstandard MySQL extension. As of MySQL
8.0.17, this operator is deprecated; expect support for it
to be removed in a future version of MySQL. Applications
should be adjusted to use the standard SQL
[`AND`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_and) operator.


- [`OR`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_or),
[`||`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_or)


Logical OR. When both operands are
non- `NULL`, the result is
`1` if any operand is nonzero, and
`0` otherwise. With a
`NULL` operand, the result is
`1` if the other operand is nonzero, and
`NULL` otherwise. If both operands are
`NULL`, the result is
`NULL`.



```sql
mysql> SELECT 1 OR 1;
          -> 1
mysql> SELECT 1 OR 0;
          -> 1
mysql> SELECT 0 OR 0;
          -> 0
mysql> SELECT 0 OR NULL;
          -> NULL
mysql> SELECT 1 OR NULL;
          -> 1
```





Note





If the [`PIPES_AS_CONCAT`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_pipes_as_concat)
SQL mode is enabled,
[`||`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_or) signifies
the SQL-standard string concatenation operator (like
[`CONCAT()`](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html#function_concat)).





The [`||`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_or), operator
is a nonstandard MySQL extension. As of MySQL 8.0.17, this
operator is deprecated; expect support for it to be removed
in a future version of MySQL. Applications should be
adjusted to use the standard SQL
[`OR`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_or) operator. Exception:
Deprecation does not apply if
[`PIPES_AS_CONCAT`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_pipes_as_concat) is enabled
because, in that case,
[`||`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_or) signifies
string concatenation.


- [`XOR`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_xor)


Logical XOR. Returns `NULL` if either
operand is `NULL`. For
non- `NULL` operands, evaluates to
`1` if an odd number of operands is
nonzero, otherwise `0` is returned.



```sql
mysql> SELECT 1 XOR 1;
          -> 0
mysql> SELECT 1 XOR 0;
          -> 1
mysql> SELECT 1 XOR NULL;
          -> NULL
mysql> SELECT 1 XOR 1 XOR 1;
          -> 1
```


`a XOR b` is mathematically equal to
`(a AND (NOT b)) OR ((NOT a) and b)`.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html "Previous: Comparison Functions and Operators") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html "Up: Operators") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html "Next: Assignment Operators")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html)

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