---
url: https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html
scraped_at: 2025-10-20T03:02:20.446Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html "Hide Sidebar")

[Previous: Logical Operators](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html "Previous: Logical Operators")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Operators](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html "Up: Operators")[Next: Flow Control Functions](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html "Next: Flow Control Functions")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/assignment-operators.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/assignment-operators.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/assignment-operators.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/assignment-operators.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/assignment-operators.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/assignment-operators.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/assignment-operators.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/assignment-operators.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html)  / [Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html)  /
[Operators](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html)  /

Assignment Operators


### 14.4.4 Assignment Operators

**Table 14.6 Assignment Operators**

| Name | Description |
| --- | --- |
| [`:=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-value) | Assign a value |
| [`=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-equal) | Assign a value (as part of a<br> [`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")<br> statement, or as part of the `SET` clause in an<br> [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement) |

- [`:=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-value)


Assignment operator. Causes the user variable on the left
hand side of the operator to take on the value to its right.
The value on the right hand side may be a literal value,
another variable storing a value, or any legal expression
that yields a scalar value, including the result of a query
(provided that this value is a scalar value). You can
perform multiple assignments in the same
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statement. You can perform multiple assignments in the same
statement.



Unlike
[`=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-equal), the
[`:=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-value)
operator is never interpreted as a comparison operator. This
means you can use
[`:=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-value) in
any valid SQL statement (not just in
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statements) to assign a value to a variable.



```sql
mysql> SELECT @var1, @var2;
          -> NULL, NULL
mysql> SELECT @var1 := 1, @var2;
          -> 1, NULL
mysql> SELECT @var1, @var2;
          -> 1, NULL
mysql> SELECT @var1, @var2 := @var1;
          -> 1, 1
mysql> SELECT @var1, @var2;
          -> 1, 1

mysql> SELECT @var1:=COUNT(*) FROM t1;
          -> 4
mysql> SELECT @var1;
          -> 4
```



You can make value assignments using
[`:=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-value) in
other statements besides
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"), such as
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"), as shown here:



```sql
mysql> SELECT @var1;
          -> 4
mysql> SELECT * FROM t1;
          -> 1, 3, 5, 7

mysql> UPDATE t1 SET c1 = 2 WHERE c1 = @var1:= 1;
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> SELECT @var1;
          -> 1
mysql> SELECT * FROM t1;
          -> 2, 3, 5, 7
```



While it is also possible both to set and to read the value
of the same variable in a single SQL statement using the
[`:=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-value)
operator, this is not recommended.
[Section 11.4, “User-Defined Variables”](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html "11.4 User-Defined Variables"), explains why you should
avoid doing this.


- [`=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-equal)


This operator is used to perform value assignments in two
cases, described in the next two paragraphs.



Within a
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statement, `=` is treated as an assignment
operator that causes the user variable on the left hand side
of the operator to take on the value to its right. (In other
words, when used in a
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statement, `=` is treated identically to
[`:=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-value).)
The value on the right hand side may be a literal value,
another variable storing a value, or any legal expression
that yields a scalar value, including the result of a query
(provided that this value is a scalar value). You can
perform multiple assignments in the same
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statement.



In the `SET` clause of an
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement,
`=` also acts as an assignment operator; in
this case, however, it causes the column named on the left
hand side of the operator to assume the value given to the
right, provided any `WHERE` conditions that
are part of the [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") are
met. You can make multiple assignments in the same
`SET` clause of an
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement.



In any other context, `=` is treated as a
[comparison operator](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_equal).



```sql
mysql> SELECT @var1, @var2;
          -> NULL, NULL
mysql> SELECT @var1 := 1, @var2;
          -> 1, NULL
mysql> SELECT @var1, @var2;
          -> 1, NULL
mysql> SELECT @var1, @var2 := @var1;
          -> 1, 1
mysql> SELECT @var1, @var2;
          -> 1, 1
```



For more information, see [Section 15.7.6.1, “SET Syntax for Variable Assignment”](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment"),
[Section 15.2.17, “UPDATE Statement”](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"), and [Section 15.2.15, “Subqueries”](https://dev.mysql.com/doc/refman/8.0/en/subqueries.html "15.2.15 Subqueries").


[PREV](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html "Previous: Logical Operators") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html "Up: Operators") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html "Next: Flow Control Functions")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html)

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