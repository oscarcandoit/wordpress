---
url: https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html
scraped_at: 2025-10-20T03:02:13.319Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html "Hide Sidebar")

[Previous: Operator Precedence](https://dev.mysql.com/doc/refman/8.0/en/operator-precedence.html "Previous: Operator Precedence")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Operators](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html "Up: Operators")[Next: Logical Operators](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html "Next: Logical Operators")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/comparison-operators.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/comparison-operators.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/comparison-operators.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/comparison-operators.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/comparison-operators.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/comparison-operators.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/comparison-operators.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/comparison-operators.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html)  / [Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html)  /
[Operators](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html)  /

Comparison Functions and Operators


### 14.4.2 Comparison Functions and Operators

**Table 14.4 Comparison Operators**

| Name | Description |
| --- | --- |
| [`>`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_greater-than) | Greater than operator |
| [`>=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_greater-than-or-equal) | Greater than or equal operator |
| [`<`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_less-than) | Less than operator |
| [`<>`, `!=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_not-equal) | Not equal operator |
| [`<=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_less-than-or-equal) | Less than or equal operator |
| [`<=>`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_equal-to) | NULL-safe equal to operator |
| [`=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_equal) | Equal operator |
| [`BETWEEN ... AND ...`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_between) | Whether a value is within a range of values |
| [`COALESCE()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_coalesce) | Return the first non-NULL argument |
| [`EXISTS()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_exists) | Whether the result of a query contains any rows |
| [`GREATEST()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_greatest) | Return the largest argument |
| [`IN()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_in) | Whether a value is within a set of values |
| [`INTERVAL()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_interval) | Return the index of the argument that is less than the first<br> argument |
| [`IS`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_is) | Test a value against a boolean |
| [`IS NOT`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_is-not) | Test a value against a boolean |
| [`IS NOT NULL`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_is-not-null) | NOT NULL value test |
| [`IS NULL`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_is-null) | NULL value test |
| [`ISNULL()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_isnull) | Test whether the argument is NULL |
| [`LEAST()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_least) | Return the smallest argument |
| [`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) | Simple pattern matching |
| [`NOT BETWEEN ... AND ...`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_not-between) | Whether a value is not within a range of values |
| [`NOT EXISTS()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_not-exists) | Whether the result of a query contains no rows |
| [`NOT IN()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_not-in) | Whether a value is not within a set of values |
| [`NOT LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_not-like) | Negation of simple pattern matching |
| [`STRCMP()`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#function_strcmp) | Compare two strings |

Comparison operations result in a value of `1`
( `TRUE`), `0`
( `FALSE`), or `NULL`. These
operations work for both numbers and strings. Strings are
automatically converted to numbers and numbers to strings as
necessary.


The following relational comparison operators can be used to
compare not only scalar operands, but row operands:


```sql
=  >  <  >=  <=  <>  !=
```

The descriptions for those operators later in this section
detail how they work with row operands. For additional examples
of row comparisons in the context of row subqueries, see
[Section 15.2.15.5, “Row Subqueries”](https://dev.mysql.com/doc/refman/8.0/en/row-subqueries.html "15.2.15.5 Row Subqueries").


Some of the functions in this section return values other than
`1` ( `TRUE`),
`0` ( `FALSE`), or
`NULL`. [`LEAST()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_least)
and [`GREATEST()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_greatest) are examples of
such functions; [Section 14.3, “Type Conversion in Expression Evaluation”](https://dev.mysql.com/doc/refman/8.0/en/type-conversion.html "14.3 Type Conversion in Expression Evaluation"), describes the
rules for comparison operations performed by these and similar
functions for determining their return values.

Note

In previous versions of MySQL, when evaluating an expression
containing `LEAST()` or
`GREATEST()`, the server attempted to guess
the context in which the function was used, and to coerce the
function's arguments to the data type of the expression
as a whole. For example, the arguments to `LEAST("11",
          "45", "2")` are evaluated and sorted as strings, so
that this expression returns `"11"`. In MySQL
8.0.3 and earlier, when evaluating the expression
`LEAST("11", "45", "2") + 0`, the server
converted the arguments to integers (anticipating the addition
of integer 0 to the result) before sorting them, thus
returning 2.


Beginning with MySQL 8.0.4, the server no longer attempts to
infer context in this fashion. Instead, the function is
executed using the arguments as provided, performing data type
conversions to one or more of the arguments if and only if
they are not all of the same type. Any type coercion mandated
by an expression that makes use of the return value is now
performed following function execution. This means that, in
MySQL 8.0.4 and later, `LEAST("11", "45", "2") +
          0` evaluates to `"11" + 0` and thus
to integer 11. (Bug #83895, Bug #25123839)

To convert a value to a specific type for comparison purposes,
you can use the [`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) function.
String values can be converted to a different character set
using [`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert). See
[Section 14.10, “Cast Functions and Operators”](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html "14.10 Cast Functions and Operators").


By default, string comparisons are not case-sensitive and use
the current character set. The default is
`utf8mb4`.

- [`=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_equal)


Equal:



```sql
mysql> SELECT 1 = 0;
          -> 0
mysql> SELECT '0' = 0;
          -> 1
mysql> SELECT '0.0' = 0;
          -> 1
mysql> SELECT '0.01' = 0;
          -> 0
mysql> SELECT '.01' = 0.01;
          -> 1
```



For row comparisons, `(a, b) = (x, y)` is
equivalent to:



```sql
(a = x) AND (b = y)
```

- [`<=>`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_equal-to)

`NULL`-safe equal. This operator performs
an equality comparison like the
[`=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_equal) operator,
but returns `1` rather than
`NULL` if both operands are
`NULL`, and `0` rather
than `NULL` if one operand is
`NULL`.



The
[`<=>`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_equal-to)
operator is equivalent to the standard SQL `IS NOT
              DISTINCT FROM` operator.



```sql
mysql> SELECT 1 <=> 1, NULL <=> NULL, 1 <=> NULL;
          -> 1, 1, 0
mysql> SELECT 1 = 1, NULL = NULL, 1 = NULL;
          -> 1, NULL, NULL
```



For row comparisons, `(a, b) <=> (x,
              y)` is equivalent to:



```sql
(a <=> x) AND (b <=> y)
```

- [`<>`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_not-equal),
[`!=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_not-equal)


Not equal:



```sql
mysql> SELECT '.01' <> '0.01';
          -> 1
mysql> SELECT .01 <> '0.01';
          -> 0
mysql> SELECT 'zapp' <> 'zappp';
          -> 1
```



For row comparisons, `(a, b) <> (x,
              y)` and `(a, b) != (x, y)` are
equivalent to:



```sql
(a <> x) OR (b <> y)
```

- [`<=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_less-than-or-equal)


Less than or equal:



```sql
mysql> SELECT 0.1 <= 2;
          -> 1
```



For row comparisons, `(a, b) <= (x, y)`
is equivalent to:



```sql
(a < x) OR ((a = x) AND (b <= y))
```

- [`<`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_less-than)


Less than:



```sql
mysql> SELECT 2 < 2;
          -> 0
```



For row comparisons, `(a, b) < (x, y)`
is equivalent to:



```sql
(a < x) OR ((a = x) AND (b < y))
```

- [`>=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_greater-than-or-equal)


Greater than or equal:



```sql
mysql> SELECT 2 >= 2;
          -> 1
```



For row comparisons, `(a, b) >= (x, y)`
is equivalent to:



```sql
(a > x) OR ((a = x) AND (b >= y))
```

- [`>`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_greater-than)


Greater than:



```sql
mysql> SELECT 2 > 2;
          -> 0
```



For row comparisons, `(a, b) > (x, y)`
is equivalent to:



```sql
(a > x) OR ((a = x) AND (b > y))
```

- [`expr\\
              BETWEEN min AND\\
              max`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_between)


If _`expr`_ is greater than or equal
to _`min`_ and
_`expr`_ is less than or equal to
_`max`_,
[`BETWEEN`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_between) returns
`1`, otherwise it returns
`0`. This is equivalent to the expression
`(min <=
              expr AND
              expr <=
              max)` if all the
arguments are of the same type. Otherwise type conversion
takes place according to the rules described in
[Section 14.3, “Type Conversion in Expression Evaluation”](https://dev.mysql.com/doc/refman/8.0/en/type-conversion.html "14.3 Type Conversion in Expression Evaluation"), but applied to all the
three arguments.



```sql
mysql> SELECT 2 BETWEEN 1 AND 3, 2 BETWEEN 3 and 1;
          -> 1, 0
mysql> SELECT 1 BETWEEN 2 AND 3;
          -> 0
mysql> SELECT 'b' BETWEEN 'a' AND 'c';
          -> 1
mysql> SELECT 2 BETWEEN 2 AND '3';
          -> 1
mysql> SELECT 2 BETWEEN 2 AND 'x-3';
          -> 0
```



For best results when using
[`BETWEEN`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_between) with date or time
values, use [`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) to
explicitly convert the values to the desired data type.
Examples: If you compare a
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") to two
[`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") values, convert the
[`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") values to
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") values. If you use a
string constant such as `'2001-1-1'` in a
comparison to a [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"), cast
the string to a [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types").


- [`expr\\
              NOT BETWEEN min AND\\
              max`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_not-between)


This is the same as `NOT
              (expr BETWEEN
              min AND
              max)`.


- [`COALESCE(value,...)`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_coalesce)


Returns the first non- `NULL` value in the
list, or `NULL` if there are no
non- `NULL` values.



The return type of [`COALESCE()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_coalesce)
is the aggregated type of the argument types.



```sql
mysql> SELECT COALESCE(NULL,1);
          -> 1
mysql> SELECT COALESCE(NULL,NULL,NULL);
          -> NULL
```

- [`EXISTS(query)`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_exists)


Whether the result of a query contains any rows.



```sql
CREATE TABLE t (col VARCHAR(3));
INSERT INTO t VALUES ('aaa', 'bbb', 'ccc', 'eee');

SELECT EXISTS (SELECT * FROM t WHERE col LIKE 'c%');
          -> 1

SELECT EXISTS (SELECT * FROM t WHERE col LIKE 'd%');
          -> 0
```

- [`NOT\\
              EXISTS(query)`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_not-exists)


Whether the result of a query contains no rows:



```sql
SELECT NOT EXISTS (SELECT * FROM t WHERE col LIKE 'c%');
          -> 0

SELECT NOT EXISTS (SELECT * FROM t WHERE col LIKE 'd%');
          -> 1
```

- [`GREATEST(value1,value2,...)`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_greatest)


With two or more arguments, returns the largest
(maximum-valued) argument. The arguments are compared using
the same rules as for
[`LEAST()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_least).



```sql
mysql> SELECT GREATEST(2,0);
          -> 2
mysql> SELECT GREATEST(34.0,3.0,5.0,767.0);
          -> 767.0
mysql> SELECT GREATEST('B','A','C');
          -> 'C'
```


[`GREATEST()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_greatest) returns
`NULL` if any argument is
`NULL`.


- [`expr\\
              IN (value,...)`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_in)


Returns `1` (true) if
_`expr`_ is equal to any of the
values in the `IN()` list, else returns
`0` (false).



Type conversion takes place according to the rules described
in [Section 14.3, “Type Conversion in Expression Evaluation”](https://dev.mysql.com/doc/refman/8.0/en/type-conversion.html "14.3 Type Conversion in Expression Evaluation"), applied to all the
arguments. If no type conversion is needed for the values in
the `IN()` list, they are all
non- `JSON` constants of the same type, and
_`expr`_ can be compared to each of
them as a value of the same type (possibly after type
conversion), an optimization takes place. The values the
list are sorted and the search for
_`expr`_ is done using a binary
search, which makes the `IN()` operation
very quick.



```sql
mysql> SELECT 2 IN (0,3,5,7);
          -> 0
mysql> SELECT 'wefwf' IN ('wee','wefwf','weg');
          -> 1
```


`IN()` can be used to compare row
constructors:



```sql
mysql> SELECT (3,4) IN ((1,2), (3,4));
          -> 1
mysql> SELECT (3,4) IN ((1,2), (3,5));
          -> 0
```



You should never mix quoted and unquoted values in an
`IN()` list because the comparison rules
for quoted values (such as strings) and unquoted values
(such as numbers) differ. Mixing types may therefore lead to
inconsistent results. For example, do not write an
`IN()` expression like this:



```sql
SELECT val1 FROM tbl1 WHERE val1 IN (1,2,'a');
```



Instead, write it like this:



```sql
SELECT val1 FROM tbl1 WHERE val1 IN ('1','2','a');
```



Implicit type conversion may produce nonintuitive results:



```sql
mysql> SELECT 'a' IN (0), 0 IN ('b');
          -> 1, 1
```



In both cases, the comparison values are converted to
floating-point values, yielding 0.0 in each case, and a
comparison result of 1 (true).



The number of values in the `IN()` list is
only limited by the
[`max_allowed_packet`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_allowed_packet) value.



To comply with the SQL standard, `IN()`
returns `NULL` not only if the expression
on the left hand side is `NULL`, but also
if no match is found in the list and one of the expressions
in the list is `NULL`.


`IN()` syntax can also be used to write
certain types of subqueries. See
[Section 15.2.15.3, “Subqueries with ANY, IN, or SOME”](https://dev.mysql.com/doc/refman/8.0/en/any-in-some-subqueries.html "15.2.15.3 Subqueries with ANY, IN, or SOME").


- [`expr\\
              NOT IN (value,...)`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_not-in)


This is the same as `NOT
              (expr IN
              (value,...))`.


- [`INTERVAL(N,N1,N2,N3,...)`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_interval)


Returns `0` if _`N`_
≤ _`N1`_, `1` if
_`N`_ ≤
_`N2`_ and so on, or
`-1` if _`N`_ is
`NULL`. All arguments are treated as
integers. It is required that _`N1`_
≤ _`N2`_ ≤
_`N3`_ ≤ `...`
≤ _`Nn`_ for this function to work
correctly. This is because a binary search is used (very
fast).



```sql
mysql> SELECT INTERVAL(23, 1, 15, 17, 30, 44, 200);
          -> 3
mysql> SELECT INTERVAL(10, 1, 10, 100, 1000);
          -> 2
mysql> SELECT INTERVAL(22, 23, 30, 44, 200);
          -> 0
```

- [`IS\\
              boolean_value`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_is)


Tests a value against a boolean value, where
_`boolean_value`_ can be
`TRUE`, `FALSE`, or
`UNKNOWN`.



```sql
mysql> SELECT 1 IS TRUE, 0 IS FALSE, NULL IS UNKNOWN;
          -> 1, 1, 1
```

- [`IS NOT\\
              boolean_value`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_is-not)


Tests a value against a boolean value, where
_`boolean_value`_ can be
`TRUE`, `FALSE`, or
`UNKNOWN`.



```sql
mysql> SELECT 1 IS NOT UNKNOWN, 0 IS NOT UNKNOWN, NULL IS NOT UNKNOWN;
          -> 1, 1, 0
```

- [`IS NULL`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_is-null)


Tests whether a value is `NULL`.



```sql
mysql> SELECT 1 IS NULL, 0 IS NULL, NULL IS NULL;
          -> 0, 0, 1
```



To work well with ODBC programs, MySQL supports the
following extra features when using [`IS\\
              NULL`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_is-null):




- If [`sql_auto_is_null`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_sql_auto_is_null)
variable is set to 1, then after a statement that
successfully inserts an automatically generated
`AUTO_INCREMENT` value, you can find
that value by issuing a statement of the following form:



```sql
SELECT * FROM tbl_name WHERE auto_col IS NULL
```



If the statement returns a row, the value returned is
the same as if you invoked the
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id)
function. For details, including the return value after
a multiple-row insert, see
[Section 14.15, “Information Functions”](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html "14.15 Information Functions"). If no
`AUTO_INCREMENT` value was successfully
inserted, the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statement returns no row.



The behavior of retrieving an
`AUTO_INCREMENT` value by using an
[`IS NULL`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_is-null) comparison can be
disabled by setting
[`sql_auto_is_null = 0`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_sql_auto_is_null).
See [Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables").



The default value of
[`sql_auto_is_null`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_sql_auto_is_null) is 0.


- For [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") and
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") columns that are
declared as `NOT NULL`, you can find
the special date `'0000-00-00'` by
using a statement like this:



```sql
SELECT * FROM tbl_name WHERE date_column IS NULL
```



This is needed to get some ODBC applications to work
because ODBC does not support a
`'0000-00-00'` date value.



See
[Obtaining Auto-Increment Values](https://dev.mysql.com/doc/connector-odbc/en/connector-odbc-usagenotes-functionality-last-insert-id.html),
and the description for the
`FLAG_AUTO_IS_NULL` option at
[Connector/ODBC Connection Parameters](https://dev.mysql.com/doc/connector-odbc/en/connector-odbc-configuration-connection-parameters.html).


- [`IS NOT NULL`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_is-null)


Tests whether a value is not `NULL`.



```sql
mysql> SELECT 1 IS NOT NULL, 0 IS NOT NULL, NULL IS NOT NULL;
          -> 1, 1, 0
```

- [`ISNULL(expr)`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_isnull)


If _`expr`_ is
`NULL`,
[`ISNULL()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_isnull) returns
`1`, otherwise it returns
`0`.



```sql
mysql> SELECT ISNULL(1+1);
          -> 0
mysql> SELECT ISNULL(1/0);
          -> 1
```


[`ISNULL()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_isnull) can be used instead
of [`=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_equal) to test
whether a value is `NULL`. (Comparing a
value to `NULL` using
[`=`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_equal) always
yields `NULL`.)



The [`ISNULL()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_isnull) function shares
some special behaviors with the
[`IS NULL`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_is-null)
comparison operator. See the description of
[`IS NULL`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#operator_is-null).


- [`LEAST(value1,value2,...)`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_least)


With two or more arguments, returns the smallest
(minimum-valued) argument. The arguments are compared using
the following rules:




- If any argument is `NULL`, the result
is `NULL`. No comparison is needed.


- If all arguments are integer-valued, they are compared
as integers.


- If at least one argument is double precision, they are
compared as double-precision values. Otherwise, if at
least one argument is a
[`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC") value, they are
compared as [`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC")
values.


- If the arguments comprise a mix of numbers and strings,
they are compared as strings.


- If any argument is a nonbinary (character) string, the
arguments are compared as nonbinary strings.


- In all other cases, the arguments are compared as binary
strings.


The return type of [`LEAST()`](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html#function_least) is
the aggregated type of the comparison argument types.


```sql
mysql> SELECT LEAST(2,0);
        -> 0
mysql> SELECT LEAST(34.0,3.0,5.0,767.0);
        -> 3.0
mysql> SELECT LEAST('B','A','C');
        -> 'A'
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/operator-precedence.html "Previous: Operator Precedence") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html "Up: Operators") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/logical-operators.html "Next: Logical Operators")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/comparison-operators.html)

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