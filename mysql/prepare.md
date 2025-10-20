---
url: https://dev.mysql.com/doc/refman/8.0/en/prepare.html
scraped_at: 2025-10-20T03:09:44.262Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/prepare.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "Hide Sidebar")

[Previous: Prepared Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html "Previous: Prepared Statements")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Prepared Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html "Up: Prepared Statements")[Next: EXECUTE Statement](https://dev.mysql.com/doc/refman/8.0/en/execute.html "Next: EXECUTE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/prepare.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/prepare.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/prepare.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/prepare.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/prepare.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/prepare.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/prepare.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/prepare.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/prepare.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/prepare.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/prepare.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/prepare.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/prepare.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Prepared Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html)  /

PREPARE Statement


### 15.5.1 PREPARE Statement

``` sql

PREPARE stmt_name FROM preparable_stmt
```

The [`PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "15.5.1 PREPARE Statement") statement prepares a
SQL statement and assigns it a name,
_`stmt_name`_, by which to refer to the
statement later. The prepared statement is executed with
[`EXECUTE`](https://dev.mysql.com/doc/refman/8.0/en/execute.html "15.5.2 EXECUTE Statement") and released with
[`DEALLOCATE PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/deallocate-prepare.html "15.5.3 DEALLOCATE PREPARE Statement"). For examples,
see [Section 15.5, “Prepared Statements”](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html "15.5 Prepared Statements").


Statement names are not case-sensitive.
_`preparable_stmt`_ is either a string
literal or a user variable that contains the text of the SQL
statement. The text must represent a single statement, not
multiple statements. Within the statement, `?`
characters can be used as parameter markers to indicate where data
values are to be bound to the query later when you execute it. The
`?` characters should not be enclosed within
quotation marks, even if you intend to bind them to string values.
Parameter markers can be used only where data values should
appear, not for SQL keywords, identifiers, and so forth.


If a prepared statement with the given name already exists, it is
deallocated implicitly before the new statement is prepared. This
means that if the new statement contains an error and cannot be
prepared, an error is returned and no statement with the given
name exists.


The scope of a prepared statement is the session within which it
is created, which as several implications:

- A prepared statement created in one session is not available
to other sessions.


- When a session ends, whether normally or abnormally, its
prepared statements no longer exist. If auto-reconnect is
enabled, the client is not notified that the connection was
lost. For this reason, clients may wish to disable
auto-reconnect. See [Automatic Reconnection Control](https://dev.mysql.com/doc/c-api/8.0/en/c-api-auto-reconnect.html).


- A prepared statement created within a stored program continues
to exist after the program finishes executing and can be
executed outside the program later.


- A statement prepared in stored program context cannot refer to
stored procedure or function parameters or local variables
because they go out of scope when the program ends and would
be unavailable were the statement to be executed later outside
the program. As a workaround, refer instead to user-defined
variables, which also have session scope; see
[Section 11.4, “User-Defined Variables”](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html "11.4 User-Defined Variables").


Beginning with MySQL 8.0.22, a parameter used in a prepared
statement has its type determined when the statement is first
prepared, and retains this type whenever
[`EXECUTE`](https://dev.mysql.com/doc/refman/8.0/en/execute.html "15.5.2 EXECUTE Statement") is invoked for this
prepared statement (unless the statement is reprepared, as
explained later in this section). Rules for determining a
parameter's type are listed here:

- A parameter which is an operand of a binary arithmetic
operator has the same data type as the other operand.


- If both operands of a binary arithmetic operator are
parameters, the type of the parameters is decided by the
context of the operator.


- If a parameter is the operand of a unary arithmetic operator,
the parameter's type is decided by the context of the
operator.


- If an arithmetic operator has no type-determining context, the
derived type for any parameters involved is
[`DOUBLE PRECISION`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE"). This can
happen, for example, when the parameter is a top-level node in
a [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") list, or when it is
part of a comparison operator.


- A parameter which is an operand of a character string operator
has the same derived type as the aggregated type of the other
operands. If all operands of the operator are parameters, the
derived type is [`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"); its
collation is determined by the value of
[`collation_connection`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_collation_connection).


- A parameter which is an operand of a temporal operator has
type [`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") if the operator
returns a `DATETIME`,
[`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type") if the operator returns a
`TIME`, and
[`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") if the operator returns a
`DATE`.


- A parameter which is an operand of a binary comparison
operator has the same derived type as the other operand of the
comparison.


- A parameter that is an operand of a ternary comparison
operator such as [`BETWEEN`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_between) has the
same derived type as the aggregated type of the other
operands.


- If all operands of a comparison operator are parameters, the
derived type for each of them is
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"), with collation
determined by the value of
[`collation_connection`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_collation_connection).


- A parameter that is an output operand of any of
[`CASE`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#operator_case),
[`COALESCE`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_coalesce),
[`IF`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#function_if),
[`IFNULL`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#function_ifnull), or
[`NULLIF`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#function_nullif) has the same derived
type as the aggregated type of the operator's other
output operands.


- If all output operands of any of
[`CASE`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#operator_case),
[`COALESCE`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_coalesce),
[`IF`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#function_if),
[`IFNULL`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#function_ifnull), or
[`NULLIF`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#function_nullif) are parameters, or they
are all `NULL`, the type of the parameter is
decided by the context of the operator.


- If the parameter is an operand of any of
[`CASE`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#operator_case),
[`COALESCE()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_coalesce),
[`IF`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#function_if), or
[`IFNULL`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#function_ifnull), and has no
type-determining context, the derived type for each of the
parameters involved is [`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
and its collation is determined by the value of
[`collation_connection`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_collation_connection).


- A parameter which is the operand of a
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) has the same type as
specified by the `CAST()`.


- If a parameter is an immediate member of a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") list that is not part of
an [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement, the
derived type of the parameter is
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"), and its collation is
determined by the value of
[`collation_connection`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_collation_connection).


- If a parameter is an immediate member of a
`SELECT` list that is part of an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement, the derived
type of the parameter is the type of the corresponding column
into which the parameter is inserted.


- If a parameter is used as source for an assignment in a
`SET` clause of an
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement or in the
`ON DUPLICATE KEY UPDATE` clause of an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement, the derived
type of the parameter is the type of the corresponding column
which is updated by the `SET` or `ON
            DUPLICATE KEY UPDATE` clause.


- If a parameter is an argument of a function, the derived type
depends on the function's return type.


For some combinations of actual type and derived type, an
automatic repreparation of the statement is triggered, to ensure
closer compatibility with previous versions of MySQL.
Repreparation does not occur if any of the following conditions
are true:

- `NULL` is used as the actual parameter value.


- A parameter is an operand of a
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast). (Instead, a cast to the
derived type is attempted, and an exception raised if the cast
fails.)


- A parameter is a string. (In this case, an implicit
`CAST(? AS
            derived_type)` is
performed.)


- The derived type and actual type of the parameter are both
[`INTEGER`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT") and have the same sign.


- The parameter's derived type is
[`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC") and its actual type is
either `DECIMAL` or
[`INTEGER`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT").


- The derived type is [`DOUBLE`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE") and
the actual type is any numeric type.


- Both the derived type and the actual type are string types.


- If the derived type is temporal and the actual type is
temporal. _Exceptions_: The derived type is
[`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type") and the actual type is not
`TIME`; the derived type is
[`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") and the actual type is not
`DATE`.


- The derived type is temporal and the actual type is numeric.


For cases other than those just listed, the statement is
reprepared and the actual parameter types are used instead of the
derived parameter types.


These rules also apply to a user variable referenced in a prepared
statement.


Using a different data type for a given parameter or user variable
within a prepared statement for executions of the statement
subsequent to the first execution causes the statement to be
reprepared. This is less efficient; it may also lead to the
parameter's (or variable's) actual type to vary, and
thus for results to be inconsistent, with subsequent executions of
the prepared statement. For these reasons, it is advisable to use
the same data type for a given parameter when re-executing a
prepared statement.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html "Previous: Prepared Statements") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html "Up: Prepared Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/execute.html "Next: EXECUTE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/prepare.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/prepare.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/prepare.html)

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