---
url: https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html
scraped_at: 2025-10-20T03:01:46.869Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html "Hide Sidebar")

[Previous: Aggregate Functions](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions-and-modifiers.html "Previous: Aggregate Functions")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Aggregate Functions](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions-and-modifiers.html "Up: Aggregate Functions")[Next: GROUP BY Modifiers](https://dev.mysql.com/doc/refman/8.0/en/group-by-modifiers.html "Next: GROUP BY Modifiers")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/aggregate-functions.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/aggregate-functions.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/aggregate-functions.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/aggregate-functions.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/aggregate-functions.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/aggregate-functions.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/aggregate-functions.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/aggregate-functions.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html)  / [Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html)  /
[Aggregate Functions](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions-and-modifiers.html)  /

Aggregate Function Descriptions


### 14.19.1 Aggregate Function Descriptions

This section describes aggregate functions that operate on sets
of values. They are often used with a `GROUP
        BY` clause to group values into subsets.

**Table 14.29 Aggregate Functions**

| Name | Description |
| --- | --- |
| [`AVG()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_avg) | Return the average value of the argument |
| [`BIT_AND()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-and) | Return bitwise AND |
| [`BIT_OR()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-or) | Return bitwise OR |
| [`BIT_XOR()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-xor) | Return bitwise XOR |
| [`COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count) | Return a count of the number of rows returned |
| [`COUNT(DISTINCT)`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count-distinct) | Return the count of a number of different values |
| [`GROUP_CONCAT()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_group-concat) | Return a concatenated string |
| [`JSON_ARRAYAGG()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_json-arrayagg) | Return result set as a single JSON array |
| [`JSON_OBJECTAGG()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_json-objectagg) | Return result set as a single JSON object |
| [`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max) | Return the maximum value |
| [`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min) | Return the minimum value |
| [`STD()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_std) | Return the population standard deviation |
| [`STDDEV()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev) | Return the population standard deviation |
| [`STDDEV_POP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev-pop) | Return the population standard deviation |
| [`STDDEV_SAMP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev-samp) | Return the sample standard deviation |
| [`SUM()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_sum) | Return the sum |
| [`VAR_POP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_var-pop) | Return the population standard variance |
| [`VAR_SAMP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_var-samp) | Return the sample variance |
| [`VARIANCE()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_variance) | Return the population standard variance |

| Name | Description |
| --- | --- |

Unless otherwise stated, aggregate functions ignore
`NULL` values.


If you use an aggregate function in a statement containing no
`GROUP BY` clause, it is equivalent to grouping
on all rows. For more information, see
[Section 14.19.3, “MySQL Handling of GROUP BY”](https://dev.mysql.com/doc/refman/8.0/en/group-by-handling.html "14.19.3 MySQL Handling of GROUP BY").


Most aggregate functions can be used as window functions. Those
that can be used this way are signified in their syntax
description by
`[over_clause]`,
representing an optional `OVER` clause.
_`over_clause`_ is described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax"), which also includes
other information about window function usage.


For numeric arguments, the variance and standard deviation
functions return a [`DOUBLE`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE") value.
The [`SUM()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_sum) and
[`AVG()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_avg) functions return a
[`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC") value for exact-value
arguments (integer or [`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC")),
and a [`DOUBLE`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE") value for
approximate-value arguments
( [`FLOAT`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE") or
[`DOUBLE`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE")).


The [`SUM()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_sum) and
[`AVG()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_avg) aggregate functions do not
work with temporal values. (They convert the values to numbers,
losing everything after the first nonnumeric character.) To work
around this problem, convert to numeric units, perform the
aggregate operation, and convert back to a temporal value.
Examples:


``` sql

SELECT SEC_TO_TIME(SUM(TIME_TO_SEC(time_col))) FROM tbl_name;
SELECT FROM_DAYS(SUM(TO_DAYS(date_col))) FROM tbl_name;
```

Functions such as [`SUM()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_sum) or
[`AVG()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_avg) that expect a numeric
argument cast the argument to a number if necessary. For
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set.html "13.3.6 The SET Type") or
[`ENUM`](https://dev.mysql.com/doc/refman/8.0/en/enum.html "13.3.5 The ENUM Type") values, the cast operation
causes the underlying numeric value to be used.


The [`BIT_AND()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-and),
[`BIT_OR()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-or), and
[`BIT_XOR()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-xor) aggregate functions
perform bit operations. Prior to MySQL 8.0, bit functions and
operators required [`BIGINT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT") (64-bit
integer) arguments and returned
[`BIGINT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT") values, so they had a
maximum range of 64 bits.
Non- [`BIGINT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT") arguments were
converted to [`BIGINT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT") prior to
performing the operation and truncation could occur.


In MySQL 8.0, bit functions and operators permit binary string
type arguments ( [`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"),
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"), and the
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") types) and return a value of
like type, which enables them to take arguments and produce
return values larger than 64 bits. For discussion about argument
evaluation and result types for bit operations, see the
introductory discussion in [Section 14.12, “Bit Functions and Operators”](https://dev.mysql.com/doc/refman/8.0/en/bit-functions.html "14.12 Bit Functions and Operators").

- [`AVG([DISTINCT]\\
              expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_avg)


Returns the average value of
`expr`. The
`DISTINCT` option can be used to return the
average of the distinct values of
_`expr`_.



If there are no matching rows,
[`AVG()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_avg) returns
`NULL`. The function also returns
`NULL` if _`expr`_
is `NULL`.



This function executes as a window function if
_`over_clause`_ is present.
_`over_clause`_ is as described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax"); it cannot be used
with `DISTINCT`.




``` sql

mysql> SELECT student_name, AVG(test_score)
         FROM student
         GROUP BY student_name;
```

- [`BIT_AND(expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-and)


Returns the bitwise `AND` of all bits in
_`expr`_.



The result type depends on whether the function argument
values are evaluated as binary strings or numbers:




- Binary-string evaluation occurs when the argument values
have a binary string type, and the argument is not a
hexadecimal literal, bit literal, or
`NULL` literal. Numeric evaluation
occurs otherwise, with argument value conversion to
unsigned 64-bit integers as necessary.


- Binary-string evaluation produces a binary string of the
same length as the argument values. If argument values
have unequal lengths, an
[`ER_INVALID_BITWISE_OPERANDS_SIZE`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_bitwise_operands_size)
error occurs. If the argument size exceeds 511 bytes, an
[`ER_INVALID_BITWISE_AGGREGATE_OPERANDS_SIZE`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_bitwise_aggregate_operands_size)
error occurs. Numeric evaluation produces an unsigned
64-bit integer.


If there are no matching rows,
[`BIT_AND()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-and) returns a neutral
value (all bits set to 1) having the same length as the
argument values.


`NULL` values do not affect the result
unless all values are `NULL`. In that case,
the result is a neutral value having the same length as the
argument values.


For more information discussion about argument evaluation
and result types, see the introductory discussion in
[Section 14.12, “Bit Functions and Operators”](https://dev.mysql.com/doc/refman/8.0/en/bit-functions.html "14.12 Bit Functions and Operators").


If [`BIT_AND()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-and) is invoked from
within the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client, binary string
results display using hexadecimal notation, depending on the
value of the [`--binary-as-hex`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_binary-as-hex).
For more information about that option, see
[Section 6.5.1, “mysql — The MySQL Command-Line Client”](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client").


As of MySQL 8.0.12, this function executes as a window
function if _`over_clause`_ is
present. _`over_clause`_ is as
described in [Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").


- [`BIT_OR(expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-or)


Returns the bitwise `OR` of all bits in
_`expr`_.



The result type depends on whether the function argument
values are evaluated as binary strings or numbers:




- Binary-string evaluation occurs when the argument values
have a binary string type, and the argument is not a
hexadecimal literal, bit literal, or
`NULL` literal. Numeric evaluation
occurs otherwise, with argument value conversion to
unsigned 64-bit integers as necessary.


- Binary-string evaluation produces a binary string of the
same length as the argument values. If argument values
have unequal lengths, an
[`ER_INVALID_BITWISE_OPERANDS_SIZE`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_bitwise_operands_size)
error occurs. If the argument size exceeds 511 bytes, an
[`ER_INVALID_BITWISE_AGGREGATE_OPERANDS_SIZE`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_bitwise_aggregate_operands_size)
error occurs. Numeric evaluation produces an unsigned
64-bit integer.


If there are no matching rows,
[`BIT_OR()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-or) returns a neutral
value (all bits set to 0) having the same length as the
argument values.


`NULL` values do not affect the result
unless all values are `NULL`. In that case,
the result is a neutral value having the same length as the
argument values.


For more information discussion about argument evaluation
and result types, see the introductory discussion in
[Section 14.12, “Bit Functions and Operators”](https://dev.mysql.com/doc/refman/8.0/en/bit-functions.html "14.12 Bit Functions and Operators").


If [`BIT_OR()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-or) is invoked from
within the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client, binary string
results display using hexadecimal notation, depending on the
value of the [`--binary-as-hex`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_binary-as-hex).
For more information about that option, see
[Section 6.5.1, “mysql — The MySQL Command-Line Client”](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client").


As of MySQL 8.0.12, this function executes as a window
function if _`over_clause`_ is
present. _`over_clause`_ is as
described in [Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").


- [`BIT_XOR(expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-xor)


Returns the bitwise [`XOR`](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html#operator_xor) of all
bits in _`expr`_.



The result type depends on whether the function argument
values are evaluated as binary strings or numbers:




- Binary-string evaluation occurs when the argument values
have a binary string type, and the argument is not a
hexadecimal literal, bit literal, or
`NULL` literal. Numeric evaluation
occurs otherwise, with argument value conversion to
unsigned 64-bit integers as necessary.


- Binary-string evaluation produces a binary string of the
same length as the argument values. If argument values
have unequal lengths, an
[`ER_INVALID_BITWISE_OPERANDS_SIZE`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_bitwise_operands_size)
error occurs. If the argument size exceeds 511 bytes, an
[`ER_INVALID_BITWISE_AGGREGATE_OPERANDS_SIZE`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_bitwise_aggregate_operands_size)
error occurs. Numeric evaluation produces an unsigned
64-bit integer.


If there are no matching rows,
[`BIT_XOR()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-xor) returns a neutral
value (all bits set to 0) having the same length as the
argument values.


`NULL` values do not affect the result
unless all values are `NULL`. In that case,
the result is a neutral value having the same length as the
argument values.


For more information discussion about argument evaluation
and result types, see the introductory discussion in
[Section 14.12, “Bit Functions and Operators”](https://dev.mysql.com/doc/refman/8.0/en/bit-functions.html "14.12 Bit Functions and Operators").


If [`BIT_XOR()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_bit-xor) is invoked from
within the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client, binary string
results display using hexadecimal notation, depending on the
value of the [`--binary-as-hex`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_binary-as-hex).
For more information about that option, see
[Section 6.5.1, “mysql — The MySQL Command-Line Client”](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client").


As of MySQL 8.0.12, this function executes as a window
function if _`over_clause`_ is
present. _`over_clause`_ is as
described in [Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").


- [`COUNT(expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count)


Returns a count of the number of non- `NULL`
values of _`expr`_ in the rows
retrieved by a [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statement. The result is a
[`BIGINT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT") value.



If there are no matching rows,
[`COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count) returns
`0`. `COUNT(NULL)` returns
0.



This function executes as a window function if
_`over_clause`_ is present.
_`over_clause`_ is as described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").




``` sql

mysql> SELECT student.student_name,COUNT(*)
         FROM student,course
         WHERE student.student_id=course.student_id
         GROUP BY student_name;
```



[`COUNT(*)`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count) is somewhat
different in that it returns a count of the number of rows
retrieved, whether or not they contain
`NULL` values.



For transactional storage engines such as
`InnoDB`, storing an exact row count is
problematic. Multiple transactions may be occurring at the
same time, each of which may affect the count.


`InnoDB` does not keep an internal count of
rows in a table because concurrent transactions might
“see” different numbers of rows at the same
time. Consequently, `SELECT COUNT(*)`
statements only count rows visible to the current
transaction.



As of MySQL 8.0.13, `SELECT COUNT(*) FROM
              tbl_name` query
performance for `InnoDB` tables is
optimized for single-threaded workloads if there are no
extra clauses such as `WHERE` or
`GROUP BY`.


`InnoDB` processes `SELECT
              COUNT(*)` statements by traversing the smallest
available secondary index unless an index or optimizer hint
directs the optimizer to use a different index. If a
secondary index is not present, `InnoDB`
processes `SELECT COUNT(*)` statements by
scanning the clustered index.



Processing of `SELECT COUNT(*)` statements
takes some time if index records are not entirely in the
buffer pool. For a faster count, create a counter table and
let your application update it according to the inserts and
deletes it does. However, this method may not scale well in
situations where thousands of concurrent transactions are
initiating updates to the same counter table. If an
approximate row count is sufficient, use
[`SHOW TABLE STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement").


`InnoDB` handles `SELECT
              COUNT(*)` and `SELECT COUNT(1)`
operations in the same way. There is no performance
difference.



For `MyISAM` tables,
[`COUNT(*)`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count) is optimized to
return very quickly if the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") retrieves from one
table, no other columns are retrieved, and there is no
`WHERE` clause. For example:




``` sql

mysql> SELECT COUNT(*) FROM student;
```




This optimization only applies to `MyISAM`
tables, because an exact row count is stored for this
storage engine and can be accessed very quickly.
`COUNT(1)` is only subject to the same
optimization if the first column is defined as `NOT
              NULL`.


- [`COUNT(DISTINCT\\
              expr,[expr...])`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count)


Returns a count of the number of rows with different
non- `NULL` _`expr`_
values.



If there are no matching rows,
[`COUNT(DISTINCT)`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count) returns
`0`.




``` sql

mysql> SELECT COUNT(DISTINCT results) FROM student;
```




In MySQL, you can obtain the number of distinct expression
combinations that do not contain `NULL` by
giving a list of expressions. In standard SQL, you would
have to do a concatenation of all expressions inside
[`COUNT(DISTINCT ...)`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count).


- [`GROUP_CONCAT(expr)`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_group-concat)


This function returns a string result with the concatenated
non- `NULL` values from a group. It returns
`NULL` if there are no
non- `NULL` values. The full syntax is as
follows:




``` sql

GROUP_CONCAT([DISTINCT] expr [,expr ...]
               [ORDER BY {unsigned_integer | col_name | expr}\
                   [ASC | DESC] [,col_name ...]]
               [SEPARATOR str_val])
```





``` sql

mysql> SELECT student_name,
           GROUP_CONCAT(test_score)
         FROM student
         GROUP BY student_name;
```




Or:




``` sql

mysql> SELECT student_name,
           GROUP_CONCAT(DISTINCT test_score
                        ORDER BY test_score DESC SEPARATOR ' ')
         FROM student
         GROUP BY student_name;
```




In MySQL, you can get the concatenated values of expression
combinations. To eliminate duplicate values, use the
`DISTINCT` clause. To sort values in the
result, use the `ORDER BY` clause. To sort
in reverse order, add the `DESC`
(descending) keyword to the name of the column you are
sorting by in the `ORDER BY` clause. The
default is ascending order; this may be specified explicitly
using the `ASC` keyword. The default
separator between values in a group is comma
( `,`). To specify a separator explicitly,
use `SEPARATOR` followed by the string
literal value that should be inserted between group values.
To eliminate the separator altogether, specify
`SEPARATOR ''`.



The result is truncated to the maximum length that is given
by the [`group_concat_max_len`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_group_concat_max_len)
system variable, which has a default value of 1024. The
value can be set higher, although the effective maximum
length of the return value is constrained by the value of
[`max_allowed_packet`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_allowed_packet). The
syntax to change the value of
[`group_concat_max_len`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_group_concat_max_len) at
runtime is as follows, where _`val`_
is an unsigned integer:




``` sql

SET [GLOBAL | SESSION] group_concat_max_len = val;
```




The return value is a nonbinary or binary string, depending
on whether the arguments are nonbinary or binary strings.
The result type is [`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") or
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") unless
[`group_concat_max_len`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_group_concat_max_len) is
less than or equal to 512, in which case the result type is
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") or
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types").



If [`GROUP_CONCAT()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_group-concat) is invoked
from within the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client, binary
string results display using hexadecimal notation, depending
on the value of the
[`--binary-as-hex`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_binary-as-hex). For more
information about that option, see [Section 6.5.1, “mysql — The MySQL Command-Line Client”](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client").



See also [`CONCAT()`](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html#function_concat) and
[`CONCAT_WS()`](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html#function_concat-ws):
[Section 14.8, “String Functions and Operators”](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html "14.8 String Functions and Operators").


- [`JSON_ARRAYAGG(col_or_expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_json-arrayagg)


Aggregates a result set as a single
[`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type") array whose elements
consist of the rows. The order of elements in this array is
undefined. The function acts on a column or an expression
that evaluates to a single value. Returns
`NULL` if the result contains no rows, or
in the event of an error. If
_`col_or_expr`_ is
`NULL`, the function returns an array of
JSON `[null]` elements.



As of MySQL 8.0.14, this function executes as a window
function if _`over_clause`_ is
present. _`over_clause`_ is as
described in [Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").




``` sql

mysql> SELECT o_id, attribute, value FROM t3;
+------+-----------+-------+
| o_id | attribute | value |
+------+-----------+-------+
|    2 | color     | red   |
|    2 | fabric    | silk  |
|    3 | color     | green |
|    3 | shape     | square|
+------+-----------+-------+
4 rows in set (0.00 sec)

mysql> SELECT o_id, JSON_ARRAYAGG(attribute) AS attributes
      -> FROM t3 GROUP BY o_id;
+------+---------------------+
| o_id | attributes          |
+------+---------------------+
|    2 | ["color", "fabric"] |
|    3 | ["color", "shape"]  |
+------+---------------------+
2 rows in set (0.00 sec)
```

- [`JSON_OBJECTAGG(key,\\
              value)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_json-objectagg)


Takes two column names or expressions as arguments, the
first of these being used as a key and the second as a
value, and returns a JSON object containing key-value pairs.
Returns `NULL` if the result contains no
rows, or in the event of an error. An error occurs if any
key name is `NULL` or the number of
arguments is not equal to 2.



As of MySQL 8.0.14, this function executes as a window
function if _`over_clause`_ is
present. _`over_clause`_ is as
described in [Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").




``` sql

mysql> SELECT o_id, attribute, value FROM t3;
+------+-----------+-------+
| o_id | attribute | value |
+------+-----------+-------+
|    2 | color     | red   |
|    2 | fabric    | silk  |
|    3 | color     | green |
|    3 | shape     | square|
+------+-----------+-------+
4 rows in set (0.00 sec)

mysql> SELECT o_id, JSON_OBJECTAGG(attribute, value)
      -> FROM t3 GROUP BY o_id;
+------+---------------------------------------+
| o_id | JSON_OBJECTAGG(attribute, value)      |
+------+---------------------------------------+
|    2 | {"color": "red", "fabric": "silk"}    |
|    3 | {"color": "green", "shape": "square"} |
+------+---------------------------------------+
2 rows in set (0.00 sec)
```



**Duplicate key handling.**
When the result of this function is normalized, values
having duplicate keys are discarded. In keeping with the
MySQL [`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type") data type
specification that does not permit duplicate keys, only
the last value encountered is used with that key in the
returned object (“last duplicate key wins”).
This means that the result of using this function on
columns from a `SELECT` can depend on the
order in which the rows are returned, which is not
guaranteed.



When used as a window function, if there are duplicate keys
within a frame, only the last value for the key is present
in the result. The value for the key from the last row in
the frame is deterministic if the `ORDER
              BY` specification guarantees that the values have a
specific order. If not, the resulting value of the key is
nondeterministic.



Consider the following:




``` sql

mysql> CREATE TABLE t(c VARCHAR(10), i INT);
Query OK, 0 rows affected (0.33 sec)

mysql> INSERT INTO t VALUES ('key', 3), ('key', 4), ('key', 5);
Query OK, 3 rows affected (0.10 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> SELECT c, i FROM t;
+------+------+
| c    | i    |
+------+------+
| key  |    3 |
| key  |    4 |
| key  |    5 |
+------+------+
3 rows in set (0.00 sec)

mysql> SELECT JSON_OBJECTAGG(c, i) FROM t;
+----------------------+
| JSON_OBJECTAGG(c, i) |
+----------------------+
| {"key": 5}           |
+----------------------+
1 row in set (0.00 sec)

mysql> DELETE FROM t;
Query OK, 3 rows affected (0.08 sec)

mysql> INSERT INTO t VALUES ('key', 3), ('key', 5), ('key', 4);
Query OK, 3 rows affected (0.06 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> SELECT c, i FROM t;
+------+------+
| c    | i    |
+------+------+
| key  |    3 |
| key  |    5 |
| key  |    4 |
+------+------+
3 rows in set (0.00 sec)

mysql> SELECT JSON_OBJECTAGG(c, i) FROM t;
+----------------------+
| JSON_OBJECTAGG(c, i) |
+----------------------+
| {"key": 4}           |
+----------------------+
1 row in set (0.00 sec)
```




The key chosen from the last query is nondeterministic. If
the query does not use `GROUP BY` (which
usually imposes its own ordering regardless) and you prefer
a particular key ordering, you can invoke
`JSON_OBJECTAGG()` as a window function by
including an `OVER` clause with an
`ORDER BY` specification to impose a
particular order on frame rows. The following examples show
what happens with and without `ORDER BY`
for a few different frame specifications.



Without `ORDER BY`, the frame is the entire
partition:




``` sql

mysql> SELECT JSON_OBJECTAGG(c, i)
         OVER () AS json_object FROM t;
+-------------+
| json_object |
+-------------+
| {"key": 4}  |
| {"key": 4}  |
| {"key": 4}  |
+-------------+
```




With `ORDER BY`, where the frame is the
default of `RANGE BETWEEN UNBOUNDED PRECEDING AND
              CURRENT ROW` (in both ascending and descending
order):




``` sql

mysql> SELECT JSON_OBJECTAGG(c, i)
         OVER (ORDER BY i) AS json_object FROM t;
+-------------+
| json_object |
+-------------+
| {"key": 3}  |
| {"key": 4}  |
| {"key": 5}  |
+-------------+
mysql> SELECT JSON_OBJECTAGG(c, i)
         OVER (ORDER BY i DESC) AS json_object FROM t;
+-------------+
| json_object |
+-------------+
| {"key": 5}  |
| {"key": 4}  |
| {"key": 3}  |
+-------------+
```




With `ORDER BY` and an explicit frame of
the entire partition:




``` sql

mysql> SELECT JSON_OBJECTAGG(c, i)
         OVER (ORDER BY i
              ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING)
          AS json_object
         FROM t;
+-------------+
| json_object |
+-------------+
| {"key": 5}  |
| {"key": 5}  |
| {"key": 5}  |
+-------------+
```




To return a particular key value (such as the smallest or
largest), include a `LIMIT` clause in the
appropriate query. For example:




``` sql

mysql> SELECT JSON_OBJECTAGG(c, i)
         OVER (ORDER BY i) AS json_object FROM t LIMIT 1;
+-------------+
| json_object |
+-------------+
| {"key": 3}  |
+-------------+
mysql> SELECT JSON_OBJECTAGG(c, i)
         OVER (ORDER BY i DESC) AS json_object FROM t LIMIT 1;
+-------------+
| json_object |
+-------------+
| {"key": 5}  |
+-------------+
```




See [Normalization, Merging, and Autowrapping of JSON Values](https://dev.mysql.com/doc/refman/8.0/en/json.html#json-normalization "Normalization, Merging, and Autowrapping of JSON Values"), for additional
information and examples.


- [`MAX([DISTINCT]\\
              expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max)


Returns the maximum value of
_`expr`_.
[`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max) may take a string
argument; in such cases, it returns the maximum string
value. See [Section 10.3.1, “How MySQL Uses Indexes”](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html "10.3.1 How MySQL Uses Indexes"). The
`DISTINCT` keyword can be used to find the
maximum of the distinct values of
_`expr`_, however, this produces the
same result as omitting `DISTINCT`.



If there are no matching rows, or if
_`expr`_ is `NULL`,
[`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max) returns
`NULL`.



This function executes as a window function if
_`over_clause`_ is present.
_`over_clause`_ is as described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax"); it cannot be used
with `DISTINCT`.




``` sql

mysql> SELECT student_name, MIN(test_score), MAX(test_score)
         FROM student
         GROUP BY student_name;
```




For [`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max), MySQL currently
compares [`ENUM`](https://dev.mysql.com/doc/refman/8.0/en/enum.html "13.3.5 The ENUM Type") and
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set.html "13.3.6 The SET Type") columns by their string
value rather than by the string's relative position in the
set. This differs from how `ORDER BY`
compares them.


- [`MIN([DISTINCT]\\
              expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min)


Returns the minimum value of
_`expr`_.
[`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min) may take a string
argument; in such cases, it returns the minimum string
value. See [Section 10.3.1, “How MySQL Uses Indexes”](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html "10.3.1 How MySQL Uses Indexes"). The
`DISTINCT` keyword can be used to find the
minimum of the distinct values of
_`expr`_, however, this produces the
same result as omitting `DISTINCT`.



If there are no matching rows, or if
_`expr`_ is `NULL`,
[`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min) returns
`NULL`.



This function executes as a window function if
_`over_clause`_ is present.
_`over_clause`_ is as described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax"); it cannot be used
with `DISTINCT`.




``` sql

mysql> SELECT student_name, MIN(test_score), MAX(test_score)
         FROM student
         GROUP BY student_name;
```




For [`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min), MySQL currently
compares [`ENUM`](https://dev.mysql.com/doc/refman/8.0/en/enum.html "13.3.5 The ENUM Type") and
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set.html "13.3.6 The SET Type") columns by their string
value rather than by the string's relative position in the
set. This differs from how `ORDER BY`
compares them.


- [`STD(expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_std)


Returns the population standard deviation of
_`expr`_.
[`STD()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_std) is a synonym for the
standard SQL function
[`STDDEV_POP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev-pop), provided as a
MySQL extension.



If there are no matching rows, or if
_`expr`_ is `NULL`,
[`STD()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_std) returns
`NULL`.



This function executes as a window function if
_`over_clause`_ is present.
_`over_clause`_ is as described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").


- [`STDDEV(expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev)


Returns the population standard deviation of
_`expr`_.
[`STDDEV()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev) is a synonym for the
standard SQL function
[`STDDEV_POP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev-pop), provided for
compatibility with Oracle.



If there are no matching rows, or if
_`expr`_ is `NULL`,
[`STDDEV()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev) returns
`NULL`.



This function executes as a window function if
_`over_clause`_ is present.
_`over_clause`_ is as described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").


- [`STDDEV_POP(expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev-pop)


Returns the population standard deviation of
_`expr`_ (the square root of
[`VAR_POP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_var-pop)). You can also use
[`STD()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_std) or
[`STDDEV()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev), which are
equivalent but not standard SQL.



If there are no matching rows, or if
_`expr`_ is `NULL`,
[`STDDEV_POP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev-pop) returns
`NULL`.



This function executes as a window function if
_`over_clause`_ is present.
_`over_clause`_ is as described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").


- [`STDDEV_SAMP(expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev-samp)


Returns the sample standard deviation of
_`expr`_ (the square root of
[`VAR_SAMP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_var-samp).



If there are no matching rows, or if
_`expr`_ is `NULL`,
[`STDDEV_SAMP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_stddev-samp) returns
`NULL`.



This function executes as a window function if
_`over_clause`_ is present.
_`over_clause`_ is as described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").


- [`SUM([DISTINCT]\\
              expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_sum)


Returns the sum of _`expr`_. If the
return set has no rows, [`SUM()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_sum)
returns `NULL`. The
`DISTINCT` keyword can be used to sum only
the distinct values of _`expr`_.



If there are no matching rows, or if
_`expr`_ is `NULL`,
[`SUM()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_sum) returns
`NULL`.



This function executes as a window function if
_`over_clause`_ is present.
_`over_clause`_ is as described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax"); it cannot be used
with `DISTINCT`.


- [`VAR_POP(expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_var-pop)


Returns the population standard variance of
_`expr`_. It considers rows as the
whole population, not as a sample, so it has the number of
rows as the denominator. You can also use
[`VARIANCE()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_variance), which is
equivalent but is not standard SQL.



If there are no matching rows, or if
_`expr`_ is `NULL`,
[`VAR_POP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_var-pop) returns
`NULL`.



This function executes as a window function if
_`over_clause`_ is present.
_`over_clause`_ is as described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").


- [`VAR_SAMP(expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_var-samp)


Returns the sample variance of
_`expr`_. That is, the denominator is
the number of rows minus one.



If there are no matching rows, or if
_`expr`_ is `NULL`,
[`VAR_SAMP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_var-samp) returns
`NULL`.



This function executes as a window function if
_`over_clause`_ is present.
_`over_clause`_ is as described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").


- [`VARIANCE(expr)\\
              [over_clause]`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_variance)


Returns the population standard variance of
_`expr`_.
[`VARIANCE()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_variance) is a synonym for
the standard SQL function
[`VAR_POP()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_var-pop), provided as a
MySQL extension.



If there are no matching rows, or if
_`expr`_ is `NULL`,
[`VARIANCE()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_variance) returns
`NULL`.



This function executes as a window function if
_`over_clause`_ is present.
_`over_clause`_ is as described in
[Section 14.20.2, “Window Function Concepts and Syntax”](https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html "14.20.2 Window Function Concepts and Syntax").


[PREV](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions-and-modifiers.html "Previous: Aggregate Functions") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions-and-modifiers.html "Up: Aggregate Functions") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/group-by-modifiers.html "Next: GROUP BY Modifiers")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html)

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