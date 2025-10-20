---
url: https://dev.mysql.com/doc/refman/8.0/en/user-variables.html
scraped_at: 2025-10-20T03:09:03.236Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html "Hide Sidebar")

[Previous: Keywords and Reserved Words](https://dev.mysql.com/doc/refman/8.0/en/keywords.html "Previous: Keywords and Reserved Words")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Language Structure](https://dev.mysql.com/doc/refman/8.0/en/language-structure.html "Up: Language Structure")[Next: Expressions](https://dev.mysql.com/doc/refman/8.0/en/expressions.html "Next: Expressions")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/user-variables.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/user-variables.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/user-variables.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/user-variables.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/user-variables.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/user-variables.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/user-variables.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/user-variables.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Language Structure](https://dev.mysql.com/doc/refman/8.0/en/language-structure.html)  /
User-Defined Variables


## 11.4 User-Defined Variables

You can store a value in a user-defined variable in one statement
and refer to it later in another statement. This enables you to
pass values from one statement to another.


User variables are written as
`@var_name`, where the
variable name _`var_name`_ consists of
alphanumeric characters, `.`,
`_`, and `$`. A user variable
name can contain other characters if you quote it as a string or
identifier (for example, `@'my-var'`,
`@"my-var"`, or ``@`my-var` ``).


User-defined variables are session specific. A user variable
defined by one client cannot be seen or used by other clients.
(Exception: A user with access to the Performance Schema
[`user_variables_by_thread`](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-user-variable-tables.html "29.12.10 Performance Schema User-Defined Variable Tables") table can
see all user variables for all sessions.) All variables for a
given client session are automatically freed when that client
exits.


User variable names are not case-sensitive. Names have a maximum
length of 64 characters.


One way to set a user-defined variable is by issuing a
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statement:


``` sql

SET @var_name = expr [, @var_name = expr] ...
```

For [`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment"),
either [`=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-equal) or
[`:=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-value) can be
used as the assignment operator.


User variables can be assigned a value from a limited set of data
types: integer, decimal, floating-point, binary or nonbinary
string, or `NULL` value. Assignment of decimal
and real values does not preserve the precision or scale of the
value. A value of a type other than one of the permissible types
is converted to a permissible type. For example, a value having a
temporal or spatial data type is converted to a binary string. A
value having the [`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type") data type is
converted to a string with a character set of
`utf8mb4` and a collation of
`utf8mb4_bin`.


If a user variable is assigned a nonbinary (character) string
value, it has the same character set and collation as the string.
The coercibility of user variables is implicit. (This is the same
coercibility as for table column values.)


Hexadecimal or bit values assigned to user variables are treated
as binary strings. To assign a hexadecimal or bit value as a
number to a user variable, use it in numeric context. For example,
add 0 or use [`CAST(... AS UNSIGNED)`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast):


``` sql

mysql> SET @v1 = X'41';
mysql> SET @v2 = X'41'+0;
mysql> SET @v3 = CAST(X'41' AS UNSIGNED);
mysql> SELECT @v1, @v2, @v3;
+------+------+------+
| @v1  | @v2  | @v3  |
+------+------+------+
| A    |   65 |   65 |
+------+------+------+
mysql> SET @v1 = b'1000001';
mysql> SET @v2 = b'1000001'+0;
mysql> SET @v3 = CAST(b'1000001' AS UNSIGNED);
mysql> SELECT @v1, @v2, @v3;
+------+------+------+
| @v1  | @v2  | @v3  |
+------+------+------+
| A    |   65 |   65 |
+------+------+------+
```

If the value of a user variable is selected in a result set, it is
returned to the client as a string.


If you refer to a variable that has not been initialized, it has a
value of `NULL` and a type of string.


Beginning with MySQL 8.0.22, a reference to a user variable in a
prepared statement has its type determined when the statement is
first prepared, and retains this type each time the statement is
executed thereafter. Similarly, the type of a user variable
employed in a statement within a stored procedure is determined
the first time the stored procedure is invoked, and retains this
type with each subsequent invocation.


User variables may be used in most contexts where expressions are
permitted. This does not currently include contexts that
explicitly require a literal value, such as in the
`LIMIT` clause of a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement, or the
`IGNORE N LINES`
clause of a [`LOAD DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement") statement.


Previous releases of MySQL made it possible to assign a value to a
user variable in statements other than
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment"). This
functionality is supported in MySQL 8.0 for backward
compatibility but is subject to removal in a future release of
MySQL.


When making an assignment in this way, you must use
[`:=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-value) as the
assignment operator; `=` is treated as the
comparison operator in statements other than
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment").


The order of evaluation for expressions involving user variables
is undefined. For example, there is no guarantee that
`SELECT @a, @a:=@a+1` evaluates
`@a` first and then performs the assignment.


In addition, the default result type of a variable is based on its
type at the beginning of the statement. This may have unintended
effects if a variable holds a value of one type at the beginning
of a statement in which it is also assigned a new value of a
different type.


To avoid problems with this behavior, either do not assign a value
to and read the value of the same variable within a single
statement, or else set the variable to `0`,
`0.0`, or `''` to define its
type before you use it.


`HAVING`, `GROUP BY`, and
`ORDER BY`, when referring to a variable that is
assigned a value in the select expression list do not work as
expected because the expression is evaluated on the client and
thus can use stale column values from a previous row.


User variables are intended to provide data values. They cannot be
used directly in an SQL statement as an identifier or as part of
an identifier, such as in contexts where a table or database name
is expected, or as a reserved word such as
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"). This is true even if the
variable is quoted, as shown in the following example:


``` sql

mysql> SELECT c1 FROM t;
+----+
| c1 |
+----+
|  0 |
+----+
|  1 |
+----+
2 rows in set (0.00 sec)

mysql> SET @col = "c1";
Query OK, 0 rows affected (0.00 sec)

mysql> SELECT @col FROM t;
+------+
| @col |
+------+
| c1   |
+------+
1 row in set (0.00 sec)

mysql> SELECT `@col` FROM t;
ERROR 1054 (42S22): Unknown column '@col' in 'field list'

mysql> SET @col = "`c1`";
Query OK, 0 rows affected (0.00 sec)

mysql> SELECT @col FROM t;
+------+
| @col |
+------+
| `c1` |
+------+
1 row in set (0.00 sec)
```

An exception to this principle that user variables cannot be used
to provide identifiers, is when you are constructing a string for
use as a prepared statement to execute later. In this case, user
variables can be used to provide any part of the statement. The
following example illustrates how this can be done:


``` sql

mysql> SET @c = "c1";
Query OK, 0 rows affected (0.00 sec)

mysql> SET @s = CONCAT("SELECT ", @c, " FROM t");
Query OK, 0 rows affected (0.00 sec)

mysql> PREPARE stmt FROM @s;
Query OK, 0 rows affected (0.04 sec)
Statement prepared

mysql> EXECUTE stmt;
+----+
| c1 |
+----+
|  0 |
+----+
|  1 |
+----+
2 rows in set (0.00 sec)

mysql> DEALLOCATE PREPARE stmt;
Query OK, 0 rows affected (0.00 sec)
```

See [Section 15.5, “Prepared Statements”](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html "15.5 Prepared Statements"), for more
information.


A similar technique can be used in application programs to
construct SQL statements using program variables, as shown here
using PHP 5:


``` php

<?php
  $mysqli = new mysqli("localhost", "user", "pass", "test");

  if( mysqli_connect_errno() )
    die("Connection failed: %s\n", mysqli_connect_error());

  $col = "c1";

  $query = "SELECT $col FROM t";

  $result = $mysqli->query($query);

  while($row = $result->fetch_assoc())
  {
    echo "<p>" . $row["$col"] . "</p>\n";
  }

  $result->close();

  $mysqli->close();
?>
```

Assembling an SQL statement in this fashion is sometimes known as
“Dynamic SQL”.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/keywords.html "Previous: Keywords and Reserved Words") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/language-structure.html "Up: Language Structure") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/expressions.html "Next: Expressions")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html)

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