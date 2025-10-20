---
url: https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html
scraped_at: 2025-10-20T03:01:55.241Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html "Hide Sidebar")

[Previous: MeCab Full-Text Parser Plugin](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search-mecab.html "Previous: MeCab Full-Text Parser Plugin")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html "Up: Functions and Operators")[Next: XML Functions](https://dev.mysql.com/doc/refman/8.0/en/xml-functions.html "Next: XML Functions")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/cast-functions.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/cast-functions.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/cast-functions.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/cast-functions.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/cast-functions.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/cast-functions.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/cast-functions.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/cast-functions.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html)  /
Cast Functions and Operators


## 14.10 Cast Functions and Operators

**Table 14.15 Cast Functions and Operators**

| Name | Description | Deprecated |
| --- | --- | --- |
| [`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#operator_binary) | Cast a string to a binary string | 8.0.27 |
| [`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) | Cast a value as a certain type |  |
| [`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) | Cast a value as a certain type |  |

Cast functions and operators enable conversion of values from one
data type to another.

- [Cast Function and Operator Descriptions](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#cast-function-descriptions "Cast Function and Operator Descriptions")

- [Character Set Conversions](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#cast-character-set-conversions "Character Set Conversions")

- [Character Set Conversions for String Comparisons](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#cast-string-comparisons "Character Set Conversions for String Comparisons")

- [Cast Operations on Spatial Types](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#cast-spatial-types "Cast Operations on Spatial Types")

- [Other Uses for Cast Operations](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#cast-other-uses "Other Uses for Cast Operations")


### Cast Function and Operator Descriptions

- [`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#operator_binary) _`expr`_


The [`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#operator_binary) operator converts
the expression to a binary string (a string that has the
`binary` character set and
`binary` collation). A common use for
[`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#operator_binary) is to force a character
string comparison to be done byte by byte using numeric byte
values rather than character by character. The
[`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#operator_binary) operator also causes
trailing spaces in comparisons to be significant. For
information about the differences between the
`binary` collation of the
`binary` character set and the
`_bin` collations of nonbinary character
sets, see [Section 12.8.5, “The binary Collation Compared to \_bin Collations”](https://dev.mysql.com/doc/refman/8.0/en/charset-binary-collations.html "12.8.5 The binary Collation Compared to _bin Collations").



The `BINARY` operator is deprecated as of
MySQL 8.0.27, and you should expect its removal in a future
version of MySQL. Use [`CAST(... AS\\
              BINARY)`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) instead.



```sql
mysql> SET NAMES utf8mb4 COLLATE utf8mb4_general_ci;
          -> OK
mysql> SELECT 'a' = 'A';
          -> 1
mysql> SELECT BINARY 'a' = 'A';
          -> 0
mysql> SELECT 'a' = 'a ';
          -> 1
mysql> SELECT BINARY 'a' = 'a ';
          -> 0
```



In a comparison, [`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#operator_binary) affects
the entire operation; it can be given before either operand
with the same result.



To convert a string expression to a binary string, these
constructs are equivalent:



```sql
CONVERT(expr USING BINARY)
CAST(expr AS BINARY)
BINARY expr
```



If a value is a string literal, it can be designated as a
binary string without converting it by using the
`_binary` character set introducer:



```sql
mysql> SELECT 'a' = 'A';
          -> 1
mysql> SELECT _binary 'a' = 'A';
          -> 0
```



For information about introducers, see
[Section 12.3.8, “Character Set Introducers”](https://dev.mysql.com/doc/refman/8.0/en/charset-introducer.html "12.3.8 Character Set Introducers").



The [`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#operator_binary) operator in
expressions differs in effect from the
`BINARY` attribute in character column
definitions. For a character column defined with the
`BINARY` attribute, MySQL assigns the table
default character set and the binary
( `_bin`) collation of that character set.
Every nonbinary character set has a `_bin`
collation. For example, if the table default character set
is `utf8mb4`, these two column definitions
are equivalent:



```sql
CHAR(10) BINARY
CHAR(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_bin
```



The use of `CHARACTER SET binary` in the
definition of a [`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"), or
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") column causes the column
to be treated as the corresponding binary string data type.
For example, the following pairs of definitions are
equivalent:



```sql
CHAR(10) CHARACTER SET binary
BINARY(10)

VARCHAR(10) CHARACTER SET binary
VARBINARY(10)

TEXT CHARACTER SET binary
BLOB
```



If [`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#operator_binary) is invoked from
within the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client, binary strings
display using hexadecimal notation, depending on the value
of the [`--binary-as-hex`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_binary-as-hex). For
more information about that option, see
[Section 6.5.1, “mysql — The MySQL Command-Line Client”](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client").


- [`CAST(expr AS\\
              type [ARRAY])`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast)

[`CAST(timestamp_value\\
              AT TIME ZONE timezone_specifier\\
              AS\\
              DATETIME[(precision)])`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast)

_`timezone_specifier`_: \[INTERVAL\]
'+00:00' \| 'UTC'



With
[`CAST(expr AS\\
              type`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) syntax, the
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) function takes an
expression of any type and produces a result value of the
specified type. This operation may also be expressed as
[`CONVERT(expr,\\
              type)`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert), which is
equivalent. If _`expr`_ is
`NULL`, `CAST()` returns
`NULL`.



These _`type`_ values are permitted:




- `BINARY[(N)]`


Produces a string with the
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types") data type,
except that when the expression
_`expr`_ is empty (zero length),
the result type is `BINARY(0)`. If the
optional length _`N`_ is given,
`BINARY(N)`
causes the cast to use no more than
_`N`_ bytes of the argument.
Values shorter than _`N`_ bytes
are padded with `0x00` bytes to a
length of _`N`_. If the optional
length _`N`_ is not given, MySQL
calculates the maximum length from the expression. If
the supplied or calculated length is greater than an
internal threshold, the result type is
`BLOB`. If the length is still too
long, the result type is `LONGBLOB`.



For a description of how casting to
`BINARY` affects comparisons, see
[Section 13.3.3, “The BINARY and VARBINARY Types”](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types").


- `CHAR[(N)]
                  [charset_info]`


Produces a string with the
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") data type, unless
the expression _`expr`_ is empty
(zero length), in which case the result type is
`CHAR(0)`. If the optional length
_`N`_ is given,
`CHAR(N)`
causes the cast to use no more than
_`N`_ characters of the argument.
No padding occurs for values shorter than
_`N`_ characters. If the optional
length _`N`_ is not given, MySQL
calculates the maximum length from the expression. If
the supplied or calculated length is greater than an
internal threshold, the result type is
`TEXT`. If the length is still too
long, the result type is `LONGTEXT`.



With no _`charset_info`_ clause,
`CHAR` produces a string with the
default character set. To specify the character set
explicitly, these
_`charset_info`_ values are
permitted:




- `CHARACTER SET
                      charset_name`:
Produces a string with the given character set.


- `ASCII`: Shorthand for
`CHARACTER SET latin1`.


- `UNICODE`: Shorthand for
`CHARACTER SET ucs2`.


In all cases, the string has the character set default
collation.


- `DATE`


Produces a [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") value.


- `DATETIME[(M)]`


Produces a [`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types")
value. If the optional _`M`_
value is given, it specifies the fractional seconds
precision.


- `DECIMAL[(M[,D])]`


Produces a [`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC") value.
If the optional _`M`_ and
_`D`_ values are given, they
specify the maximum number of digits (the precision) and
the number of digits following the decimal point (the
scale). If _`D`_ is omitted, 0 is
assumed. If _`M`_ is omitted, 10
is assumed.


- `DOUBLE`


Produces a [`DOUBLE`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE") result.
Added in MySQL 8.0.17.


- `FLOAT[(p)]`


If the precision _`p`_ is not
specified, produces a result of type
[`FLOAT`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE"). If
_`p`_ is provided and 0 <=
< _`p`_ <= 24, the result
is of type `FLOAT`. If 25 <=
_`p`_ <= 53, the result is of
type [`DOUBLE`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE"). If
_`p`_ < 0 or
_`p`_ \> 53, an error is
returned. Added in MySQL 8.0.17.


- `JSON`


Produces a [`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type") value.
For details on the rules for conversion of values
between [`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type") and other
types, see [Comparison and Ordering of JSON Values](https://dev.mysql.com/doc/refman/8.0/en/json.html#json-comparison "Comparison and Ordering of JSON Values").


- `NCHAR[(N)]`


Like `CHAR`, but produces a string with
the national character set. See
[Section 12.3.7, “The National Character Set”](https://dev.mysql.com/doc/refman/8.0/en/charset-national.html "12.3.7 The National Character Set").



Unlike `CHAR`, `NCHAR`
does not permit trailing character set information to be
specified.


- `REAL`


Produces a result of type
[`REAL`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE"). This is actually
`FLOAT` if the
[`REAL_AS_FLOAT`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_real_as_float) SQL mode
is enabled; otherwise the result is of type
`DOUBLE`.


- `SIGNED [INTEGER]`


Produces a signed [`BIGINT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT")
value.


- _`spatial_type`_


As of MySQL 8.0.24,
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) and
[`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) support casting
geometry values from one spatial type to another, for
certain combinations of spatial types. For details, see
[Cast Operations on Spatial Types](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#cast-spatial-types "Cast Operations on Spatial Types").


- `TIME[(M)]`


Produces a [`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type") value. If
the optional _`M`_ value is
given, it specifies the fractional seconds precision.


- `UNSIGNED [INTEGER]`


Produces an unsigned
[`BIGINT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT") value.


- `YEAR`


Produces a [`YEAR`](https://dev.mysql.com/doc/refman/8.0/en/year.html "13.2.4 The YEAR Type") value.
Added in MySQL 8.0.22. These rules govern conversion to
`YEAR`:




- For a four-digit number in the range 1901-2155
inclusive, or for a string which can be interpreted
as a four-digit number in this range, return the
corresponding `YEAR` value.


- For a number consisting of one or two digits, or for
a string which can be interpreted as such a number,
return a `YEAR` value as follows:




- If the number is in the range 1-69 inclusive,
add 2000 and return the sum.


- If the number is in the range 70-99 inclusive,
add 1900 and return the sum.


- For a string which evaluates to 0, return 2000.


- For the number 0, return 0.


- For a [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"),
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"), or
[`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") value,
return the `YEAR` portion of the
value. For a [`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type")
value, return the current year.



If you do not specify the type of a
`TIME` argument, you may get a
different result from what you expect, as shown
here:



```sql
mysql> SELECT CAST("11:35:00" AS YEAR), CAST(TIME "11:35:00" AS YEAR);
+--------------------------+-------------------------------+
| CAST("11:35:00" AS YEAR) | CAST(TIME "11:35:00" AS YEAR) |
+--------------------------+-------------------------------+
|                     2011 |                          2021 |
+--------------------------+-------------------------------+
```

- If the argument is of type
[`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC"),
[`DOUBLE`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE"),
[`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC"), or
[`REAL`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE"), round the value
to the nearest integer, then attempt to cast the
value to `YEAR` using the rules for
integer values, as shown here:



```sql
mysql> SELECT CAST(1944.35 AS YEAR), CAST(1944.50 AS YEAR);
+-----------------------+-----------------------+
| CAST(1944.35 AS YEAR) | CAST(1944.50 AS YEAR) |
+-----------------------+-----------------------+
|                  1944 |                  1945 |
+-----------------------+-----------------------+

mysql> SELECT CAST(66.35 AS YEAR), CAST(66.50 AS YEAR);
+---------------------+---------------------+
| CAST(66.35 AS YEAR) | CAST(66.50 AS YEAR) |
+---------------------+---------------------+
|                2066 |                2067 |
+---------------------+---------------------+
```

- An argument of type
[`GEOMETRY`](https://dev.mysql.com/doc/refman/8.0/en/spatial-type-overview.html "13.4.1 Spatial Data Types") cannot be
converted to [`YEAR`](https://dev.mysql.com/doc/refman/8.0/en/year.html "13.2.4 The YEAR Type").


- For a value that cannot be successfully converted to
`YEAR`, return
`NULL`.


A string value containing non-numeric characters which
must be truncated prior to conversion raises a warning,
as shown here:


```sql
mysql> SELECT CAST("1979aaa" AS YEAR);
+-------------------------+
| CAST("1979aaa" AS YEAR) |
+-------------------------+
|                    1979 |
+-------------------------+
1 row in set, 1 warning (0.00 sec)

mysql> SHOW WARNINGS;
+---------+------+-------------------------------------------+
| Level   | Code | Message                                   |
+---------+------+-------------------------------------------+
| Warning | 1292 | Truncated incorrect YEAR value: '1979aaa' |
+---------+------+-------------------------------------------+
```

In MySQL 8.0.17 and higher,
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") allows the use of an
additional `ARRAY` keyword for creating a
multi-valued index on a [`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type")
array as part of [`CREATE\\
            INDEX`](https://dev.mysql.com/doc/refman/8.0/en/create-index.html "15.1.15 CREATE INDEX Statement"), [`CREATE\\
            TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"), and [`ALTER\\
            TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") statements. `ARRAY` is not
supported except when used to create a multi-valued index in
one of these statements, in which case it is required. The
column being indexed must be a column of type
`JSON`. With `ARRAY`, the
_`type`_ following the
`AS` keyword may specify any of the types
supported by `CAST()`, with the exceptions
of `BINARY`, `JSON`, and
`YEAR`. For syntax information and
examples, as well as other relevant information, see
[Multi-Valued Indexes](https://dev.mysql.com/doc/refman/8.0/en/create-index.html#create-index-multi-valued "Multi-Valued Indexes").

Note

[`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert), unlike
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast), does
_not_ support multi-valued index
creation or the `ARRAY` keyword.

Beginning with MySQL 8.0.22, `CAST()`
supports retrieval of a
[`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") value as being in
UTC, using the `AT TIMEZONE` operator. The
only supported time zone is UTC; this can be specified as
either of `'+00:00'` or
`'UTC'`. The only return type supported by
this syntax is `DATETIME`, with an optional
precision specifier in the range of 0 to 6, inclusive.


`TIMESTAMP` values that use timezone
offsets are also supported.


```sql
mysql> SELECT @@system_time_zone;
+--------------------+
| @@system_time_zone |
+--------------------+
| EDT                |
+--------------------+
1 row in set (0.00 sec)

mysql> CREATE TABLE tz (c TIMESTAMP);
Query OK, 0 rows affected (0.41 sec)

mysql> INSERT INTO tz VALUES
    ->     ROW(CURRENT_TIMESTAMP),
    ->     ROW('2020-07-28 14:50:15+1:00');
Query OK, 1 row affected (0.08 sec)

mysql> TABLE tz;
+---------------------+
| c                   |
+---------------------+
| 2020-07-28 09:22:41 |
| 2020-07-28 09:50:15 |
+---------------------+
2 rows in set (0.00 sec)

mysql> SELECT CAST(c AT TIME ZONE '+00:00' AS DATETIME) AS u FROM tz;
+---------------------+
| u                   |
+---------------------+
| 2020-07-28 13:22:41 |
| 2020-07-28 13:50:15 |
+---------------------+
2 rows in set (0.00 sec)

mysql> SELECT CAST(c AT TIME ZONE 'UTC' AS DATETIME(2)) AS u FROM tz;
+------------------------+
| u                      |
+------------------------+
| 2020-07-28 13:22:41.00 |
| 2020-07-28 13:50:15.00 |
+------------------------+
2 rows in set (0.00 sec)
```

If you use `'UTC'` as the time zone
specifier with this form of `CAST()`, and
the server raises an error such as Unknown or
incorrect time zone: 'UTC', you may need to
install the MySQL time zone tables (see
[Populating the Time Zone Tables](https://dev.mysql.com/doc/refman/8.0/en/time-zone-support.html#time-zone-installation "Populating the Time Zone Tables")).


`AT TIME ZONE` does not support the
`ARRAY` keyword, and is not supported by
the [`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) function.


- [`CONVERT(expr\\
              USING transcoding_name)`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert)

[`CONVERT(expr,type)`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert)

[`CONVERT(expr\\
              USING transcoding_name)`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert)
is standard SQL syntax. The non- `USING`
form of [`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) is ODBC
syntax. Regardless of the syntax used, the function returns
`NULL` if _`expr`_
is `NULL`.


[`CONVERT(expr\\
              USING transcoding_name)`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert)
converts data between different character sets. In MySQL,
transcoding names are the same as the corresponding
character set names. For example, this statement converts
the string `'abc'` in the default character
set to the corresponding string in the
`utf8mb4` character set:



```sql
SELECT CONVERT('abc' USING utf8mb4);
```


[`CONVERT(expr,\\
              type)`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) syntax (without
`USING`) takes an expression and a
_`type`_ value specifying a result
type, and produces a result value of the specified type.
This operation may also be expressed as
[`CAST(expr AS\\
              type)`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast), which is
equivalent. For more information, see the description of
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast).





Note





Prior to MySQL 8.0.28, this function sometimes allowed
invalid conversions of
[`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types") values to a
nonbinary character set. When `CONVERT()`
was used as part of the expression for an indexed
generated column, this could lead to index corruption
following an upgrade from a previous version of MySQL. See
[SQL Changes](https://dev.mysql.com/doc/refman/8.0/en/upgrading-from-previous-series.html#upgrade-sql-changes "SQL Changes"), for information
about how to handle this situation.


### Character Set Conversions

[`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) with a
`USING` clause converts data between character
sets:


```sql
CONVERT(expr USING transcoding_name)
```

In MySQL, transcoding names are the same as the corresponding
character set names.


Examples:


```sql
SELECT CONVERT('test' USING utf8mb4);
SELECT CONVERT(_latin1'Müller' USING utf8mb4);
INSERT INTO utf8mb4_table (utf8mb4_column)
    SELECT CONVERT(latin1_column USING utf8mb4) FROM latin1_table;
```

To convert strings between character sets, you can also use
[`CONVERT(expr,\\
        type)`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) syntax (without
`USING`), or
[`CAST(expr AS\\
        type)`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast), which is equivalent:


```sql
CONVERT(string, CHAR[(N)] CHARACTER SET charset_name)
CAST(string AS CHAR[(N)] CHARACTER SET charset_name)
```

Examples:


```sql
SELECT CONVERT('test', CHAR CHARACTER SET utf8mb4);
SELECT CAST('test' AS CHAR CHARACTER SET utf8mb4);
```

If you specify `CHARACTER SET
        charset_name` as just shown,
the character set and collation of the result are
_`charset_name`_ and the default
collation of _`charset_name`_. If you
omit `CHARACTER SET
        charset_name`, the character
set and collation of the result are defined by the
[`character_set_connection`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_character_set_connection) and
[`collation_connection`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_collation_connection) system
variables that determine the default connection character set
and collation (see [Section 12.4, “Connection Character Sets and Collations”](https://dev.mysql.com/doc/refman/8.0/en/charset-connection.html "12.4 Connection Character Sets and Collations")).


A `COLLATE` clause is not permitted within a
[`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) or
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) call, but you can apply it
to the function result. For example, these are legal:


```sql
SELECT CONVERT('test' USING utf8mb4) COLLATE utf8mb4_bin;
SELECT CONVERT('test', CHAR CHARACTER SET utf8mb4) COLLATE utf8mb4_bin;
SELECT CAST('test' AS CHAR CHARACTER SET utf8mb4) COLLATE utf8mb4_bin;
```

But these are illegal:


```sql
SELECT CONVERT('test' USING utf8mb4 COLLATE utf8mb4_bin);
SELECT CONVERT('test', CHAR CHARACTER SET utf8mb4 COLLATE utf8mb4_bin);
SELECT CAST('test' AS CHAR CHARACTER SET utf8mb4 COLLATE utf8mb4_bin);
```

For string literals, another way to specify the character set is
to use a character set introducer. `_latin1`
and `_latin2` in the preceding example are
instances of introducers. Unlike conversion functions such as
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast), or
[`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert), which convert a string
from one character set to another, an introducer designates a
string literal as having a particular character set, with no
conversion involved. For more information, see
[Section 12.3.8, “Character Set Introducers”](https://dev.mysql.com/doc/refman/8.0/en/charset-introducer.html "12.3.8 Character Set Introducers").

### Character Set Conversions for String Comparisons

Normally, you cannot compare a
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") value or other binary string
in case-insensitive fashion because binary strings use the
`binary` character set, which has no collation
with the concept of lettercase. To perform a case-insensitive
comparison, first use the
[`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) or
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) function to convert the
value to a nonbinary string. Comparisons of the resulting string
use its collation. For example, if the conversion result
collation is not case-sensitive, a
[`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) operation is not
case-sensitive. That is true for the following operation because
the default `utf8mb4` collation
( `utf8mb4_0900_ai_ci`) is not case-sensitive:


```sql
SELECT 'A' LIKE CONVERT(blob_col USING utf8mb4)
  FROM tbl_name;
```

To specify a particular collation for the converted string, use
a `COLLATE` clause following the
[`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) call:


```sql
SELECT 'A' LIKE CONVERT(blob_col USING utf8mb4) COLLATE utf8mb4_unicode_ci
  FROM tbl_name;
```

To use a different character set, substitute its name for
`utf8mb4` in the preceding statements (and
similarly to use a different collation).


[`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) and
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) can be used more generally
for comparing strings represented in different character sets.
For example, a comparison of these strings results in an error
because they have different character sets:


```sql
mysql> SET @s1 = _latin1 'abc', @s2 = _latin2 'abc';
mysql> SELECT @s1 = @s2;
ERROR 1267 (HY000): Illegal mix of collations (latin1_swedish_ci,IMPLICIT)
and (latin2_general_ci,IMPLICIT) for operation '='
```

Converting one of the strings to a character set compatible with
the other enables the comparison to occur without error:


```sql
mysql> SELECT @s1 = CONVERT(@s2 USING latin1);
+---------------------------------+
| @s1 = CONVERT(@s2 USING latin1) |
+---------------------------------+
|                               1 |
+---------------------------------+
```

Character set conversion is also useful preceding lettercase
conversion of binary strings.
[`LOWER()`](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html#function_lower) and
[`UPPER()`](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html#function_upper) are ineffective when
applied directly to binary strings because the concept of
lettercase does not apply. To perform lettercase conversion of a
binary string, first convert it to a nonbinary string using a
character set appropriate for the data stored in the string:


```sql
mysql> SET @str = BINARY 'New York';
mysql> SELECT LOWER(@str), LOWER(CONVERT(@str USING utf8mb4));
+-------------+------------------------------------+
| LOWER(@str) | LOWER(CONVERT(@str USING utf8mb4)) |
+-------------+------------------------------------+
| New York    | new york                           |
+-------------+------------------------------------+
```

Be aware that if you apply [`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#operator_binary),
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast), or
[`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) to an indexed column,
MySQL may not be able to use the index efficiently.

### Cast Operations on Spatial Types

As of MySQL 8.0.24, [`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) and
[`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) support casting
geometry values from one spatial type to another, for certain
combinations of spatial types. The following list shows the
permitted type combinations, where “MySQL
extension” designates casts implemented in MySQL beyond
those defined in the [SQL/MM\\
standard](https://dev.mysql.com/doc/refman/8.0/en/spatial-types.html "13.4 Spatial Data Types"):

- From `Point` to:




- `MultiPoint`

- `GeometryCollection`


- From `LineString` to:




- `Polygon` (MySQL extension)


- `MultiPoint` (MySQL extension)


- `MultiLineString`

- `GeometryCollection`


- From `Polygon` to:




- `LineString` (MySQL extension)


- `MultiLineString` (MySQL extension)


- `MultiPolygon`

- `GeometryCollection`


- From `MultiPoint` to:




- `Point`

- `LineString` (MySQL extension)


- `GeometryCollection`


- From `MultiLineString` to:




- `LineString`

- `Polygon` (MySQL extension)


- `MultiPolygon` (MySQL extension)


- `GeometryCollection`


- From `MultiPolygon` to:




- `Polygon`

- `MultiLineString` (MySQL extension)


- `GeometryCollection`


- From `GeometryCollection` to:




- `Point`

- `LineString`

- `Polygon`

- `MultiPoint`

- `MultiLineString`

- `MultiPolygon`


In spatial casts, `GeometryCollection` and
`GeomCollection` are synonyms for the same
result type.


Some conditions apply to all spatial type casts, and some
conditions apply only when the cast result is to have a
particular spatial type. For information about terms such as
“well-formed geometry,” see
[Section 13.4.4, “Geometry Well-Formedness and Validity”](https://dev.mysql.com/doc/refman/8.0/en/geometry-well-formedness-validity.html "13.4.4 Geometry Well-Formedness and Validity").

- [General Conditions for Spatial Casts](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#spatial-cast-general-conditions "General Conditions for Spatial Casts")

- [Conditions for Casts to Point](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#spatial-cast-point-conditions "Conditions for Casts to Point")

- [Conditions for Casts to LineString](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#spatial-cast-linestring-conditions "Conditions for Casts to LineString")

- [Conditions for Casts to Polygon](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#spatial-cast-polygon-conditions "Conditions for Casts to Polygon")

- [Conditions for Casts to MultiPoint](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#spatial-cast-multipoint-conditions "Conditions for Casts to MultiPoint")

- [Conditions for Casts to MultiLineString](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#spatial-cast-multilinestring-conditions "Conditions for Casts to MultiLineString")

- [Conditions for Casts to MultiPolygon](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#spatial-cast-multipolygon-conditions "Conditions for Casts to MultiPolygon")

- [Conditions for Casts to GeometryCollection](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#spatial-cast-geometrycollection-conditions "Conditions for Casts to GeometryCollection")


#### General Conditions for Spatial Casts

These conditions apply to all spatial casts regardless of the
result type:

- The result of a cast is in the same SRS as that of the
expression to cast.


- Casting between spatial types does not change coordinate
values or order.


- If the expression to cast is `NULL`, the
function result is `NULL`.


- Casting to spatial types using the
[`JSON_VALUE()`](https://dev.mysql.com/doc/refman/8.0/en/json-search-functions.html#function_json-value) function with a
`RETURNING` clause specifying a spatial
type is not permitted.


- Casting to an `ARRAY` of spatial types is
not permitted.


- If the spatial type combination is permitted but the
expression to cast is not a syntactically well-formed
geometry, an
[`ER_GIS_INVALID_DATA`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_gis_invalid_data) error
occurs.


- If the spatial type combination is permitted but the
expression to cast is a syntactically well-formed geometry
in an undefined spatial reference system (SRS), an
[`ER_SRS_NOT_FOUND`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_srs_not_found) error
occurs.


- If the expression to cast has a geographic SRS but has a
longitude or latitude that is out of range, an error occurs:




- If a longitude value is not in the range (−180,
180\], an
[`ER_GEOMETRY_PARAM_LONGITUDE_OUT_OF_RANGE`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_geometry_param_longitude_out_of_range)
error occurs.


- If a latitude value is not in the range \[−90, 90\],
an
[`ER_GEOMETRY_PARAM_LATITUDE_OUT_OF_RANGE`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_geometry_param_latitude_out_of_range)
error occurs.


Ranges shown are in degrees. If an SRS uses another unit,
the range uses the corresponding values in its unit. The
exact range limits deviate slightly due to floating-point
arithmetic.

#### Conditions for Casts to Point

When the cast result type is `Point`, these
conditions apply:

- If the expression to cast is a well-formed geometry of type
`Point`, the function result is that
`Point`.


- If the expression to cast is a well-formed geometry of type
`MultiPoint` containing a single
`Point`, the function result is that
`Point`. If the expression contains more
than one `Point`, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


- If the expression to cast is a well-formed geometry of type
`GeometryCollection` containing only a
single `Point`, the function result is that
`Point`. If the expression is empty,
contains more than one `Point`, or contains
other geometry types, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


- If the expression to cast is a well-formed geometry of type
other than `Point`,
`MultiPoint`,
`GeometryCollection`, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


#### Conditions for Casts to LineString

When the cast result type is `LineString`,
these conditions apply:

- If the expression to cast is a well-formed geometry of type
`LineString`, the function result is that
`LineString`.


- If the expression to cast is a well-formed geometry of type
`Polygon` that has no inner rings, the
function result is a `LineString`
containing the points of the outer ring in the same order.
If the expression has inner rings, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


- If the expression to cast is a well-formed geometry of type
`MultiPoint` containing at least two
points, the function result is a
`LineString` containing the points of the
`MultiPoint` in the order they appear in
the expression. If the expression contains only one
`Point`, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


- If the expression to cast is a well-formed geometry of type
`MultiLineString` containing a single
`LineString`, the function result is that
`LineString`. If the expression contains
more than one `LineString`, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


- If the expression to cast is a well-formed geometry of type
`GeometryCollection`, containing only a
single `LineString`, the function result is
that `LineString`. If the expression is
empty, contains more than one `LineString`,
or contains other geometry types, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


- If the expression to cast is a well-formed geometry of type
other than `LineString`,
`Polygon`, `MultiPoint`,
`MultiLineString`, or
`GeometryCollection`, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


#### Conditions for Casts to Polygon

When the cast result type is `Polygon`, these
conditions apply:

- If the expression to cast is a well-formed geometry of type
`LineString` that is a ring (that is, the
start and end points are the same), the function result is a
`Polygon` with an outer ring consisting of
the points of the `LineString` in the same
order. If the expression is not a ring, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs. If the ring is not in the correct order (the
exterior ring must be counter-clockwise), an
[`ER_INVALID_CAST_POLYGON_RING_DIRECTION`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_polygon_ring_direction)
error occurs.


- If the expression to cast is a well-formed geometry of type
`Polygon`, the function result is that
`Polygon`.


- If the expression to cast is a well-formed geometry of type
`MultiLineString` where all elements are
rings, the function result is a `Polygon`
with the first `LineString` as outer ring
and any additional `LineString` values as
inner rings. If any element of the expression is not a ring,
an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs. If any ring is not in the correct order (the
exterior ring must be counter-clockwise, interior rings must
be clockwise), an
[`ER_INVALID_CAST_POLYGON_RING_DIRECTION`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_polygon_ring_direction)
error occurs.


- If the expression to cast is a well-formed geometry of type
`MultiPolygon` containing a single
`Polygon`, the function result is that
`Polygon`. If the expression contains more
than one `Polygon`, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


- If the expression to cast is a well-formed geometry of type
`GeometryCollection` containing only a
single `Polygon`, the function result is
that `Polygon`. If the expression is empty,
contains more than one `Polygon`, or
contains other geometry types, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


- If the expression to cast is a well-formed geometry of type
other than `LineString`,
`Polygon`,
`MultiLineString`,
`MultiPolygon`, or
`GeometryCollection`, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


#### Conditions for Casts to MultiPoint

When the cast result type is `MultiPoint`,
these conditions apply:

- If the expression to cast is a well-formed geometry of type
`Point`, the function result is a
`MultiPoint` containing that
`Point` as its sole element.


- If the expression to cast is a well-formed geometry of type
`LineString`, the function result is a
`MultiPoint` containing the points of the
`LineString` in the same order.


- If the expression to cast is a well-formed geometry of type
`MultiPoint`, the function result is that
`MultiPoint`.


- If the expression to cast is a well-formed geometry of type
`GeometryCollection` containing only
points, the function result is a
`MultiPoint` containing those points. If
the `GeometryCollection` is empty or
contains other geometry types, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


- If the expression to cast is a well-formed geometry of type
other than `Point`,
`LineString`,
`MultiPoint`, or
`GeometryCollection`, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


#### Conditions for Casts to MultiLineString

When the cast result type is `MultiLineString`,
these conditions apply:

- If the expression to cast is a well-formed geometry of type
`LineString`, the function result is a
`MultiLineString` containing that
`LineString` as its sole element.


- If the expression to cast is a well-formed geometry of type
`Polygon`, the function result is a
`MultiLineString` containing the outer ring
of the `Polygon` as its first element and
any inner rings as additional elements in the order they
appear in the expression.


- If the expression to cast is a well-formed geometry of type
`MultiLineString`, the function result is
that `MultiLineString`.


- If the expression to cast is a well-formed geometry of type
`MultiPolygon` containing only polygons
without inner rings, the function result is a
`MultiLineString` containing the polygon
rings in the order they appear in the expression. If the
expression contains any polygons with inner rings, an
[`ER_WRONG_PARAMETERS_TO_STORED_FCT`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_wrong_parameters_to_stored_fct)
error occurs.


- If the expression to cast is a well-formed geometry of type
`GeometryCollection` containing only
linestrings, the function result is a
`MultiLineString` containing those
linestrings. If the expression is empty or contains other
geometry types, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


- If the expression to cast is a well-formed geometry of type
other than `LineString`,
`Polygon`,
`MultiLineString`,
`MultiPolygon`, or
`GeometryCollection`, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


#### Conditions for Casts to MultiPolygon

When the cast result type is `MultiPolygon`,
these conditions apply:

- If the expression to cast is a well-formed geometry of type
`Polygon`, the function result is a
`MultiPolygon` containing the
`Polygon` as its sole element.


- If the expression to cast is a well-formed geometry of type
`MultiLineString` where all elements are
rings, the function result is a
`MultiPolygon` containing a
`Polygon` with only an outer ring for each
element of the expression. If any element is not a ring, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs. If any ring is not in the correct order
(exterior ring must be counter-clockwise), an
[`ER_INVALID_CAST_POLYGON_RING_DIRECTION`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_polygon_ring_direction)
error occurs.


- If the expression to cast is a well-formed geometry of type
`MultiPolygon`, the function result is that
`MultiPolygon`.


- If the expression to cast is a well-formed geometry of type
`GeometryCollection` containing only
polygons, the function result is a
`MultiPolygon` containing those polygons.
If the expression is empty or contains other geometry types,
an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


- If the expression to cast is a well-formed geometry of type
other than `Polygon`,
`MultiLineString`,
`MultiPolygon`, or
`GeometryCollection`, an
[`ER_INVALID_CAST_TO_GEOMETRY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_invalid_cast_to_geometry)
error occurs.


#### Conditions for Casts to GeometryCollection

When the cast result type is
`GeometryCollection`, these conditions apply:

- `GeometryCollection` and
`GeomCollection` are synonyms for the same
result type.


- If the expression to cast is a well-formed geometry of type
`Point`, the function result is a
`GeometryCollection` containing that
`Point` as its sole element.


- If the expression to cast is a well-formed geometry of type
`LineString`, the function result is a
`GeometryCollection` containing that
`LineString` as its sole element.


- If the expression to cast is a well-formed geometry of type
`Polygon`, the function result is a
`GeometryCollection` containing that
`Polygon` as its sole element.


- If the expression to cast is a well-formed geometry of type
`MultiPoint`, the function result is a
`GeometryCollection` containing the points
in the order they appear in the expression.


- If the expression to cast is a well-formed geometry of type
`MultiLineString`, the function result is a
`GeometryCollection` containing the
linestrings in the order they appear in the expression.


- If the expression to cast is a well-formed geometry of type
`MultiPolygon`, the function result is a
`GeometryCollection` containing the
elements of the `MultiPolygon` in the order
they appear in the expression.


- If the expression to cast is a well-formed geometry of type
`GeometryCollection`, the function result
is that `GeometryCollection`.


### Other Uses for Cast Operations

The cast functions are useful for creating a column with a
specific type in a
[`CREATE TABLE ...\\
        SELECT`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement:


```sql
mysql> CREATE TABLE new_table SELECT CAST('2000-01-01' AS DATE) AS c1;
mysql> SHOW CREATE TABLE new_table\G
*************************** 1. row ***************************
       Table: new_table
Create Table: CREATE TABLE `new_table` (
  `c1` date DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```

The cast functions are useful for sorting
[`ENUM`](https://dev.mysql.com/doc/refman/8.0/en/enum.html "13.3.5 The ENUM Type") columns in lexical order.
Normally, sorting of [`ENUM`](https://dev.mysql.com/doc/refman/8.0/en/enum.html "13.3.5 The ENUM Type") columns
occurs using the internal numeric values. Casting the values to
[`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") results in a lexical sort:


```sql
SELECT enum_col FROM tbl_name
  ORDER BY CAST(enum_col AS CHAR);
```

[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) also changes the result if
you use it as part of a more complex expression such as
[`CONCAT('Date: ',CAST(NOW() AS\\
        DATE))`](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html#function_concat).


For temporal values, there is little need to use
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) to extract data in
different formats. Instead, use a function such as
[`EXTRACT()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_extract),
[`DATE_FORMAT()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_date-format), or
[`TIME_FORMAT()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_time-format). See
[Section 14.7, “Date and Time Functions”](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html "14.7 Date and Time Functions").


To cast a string to a number, it normally suffices to use the
string value in numeric context:


```sql
mysql> SELECT 1+'1';
       -> 2
```

That is also true for hexadecimal and bit literals, which are
binary strings by default:


```sql
mysql> SELECT X'41', X'41'+0;
        -> 'A', 65
mysql> SELECT b'1100001', b'1100001'+0;
        -> 'a', 97
```

A string used in an arithmetic operation is converted to a
floating-point number during expression evaluation.


A number used in string context is converted to a string:


```sql
mysql> SELECT CONCAT('hello you ',2);
        -> 'hello you 2'
```

For information about implicit conversion of numbers to strings,
see [Section 14.3, “Type Conversion in Expression Evaluation”](https://dev.mysql.com/doc/refman/8.0/en/type-conversion.html "14.3 Type Conversion in Expression Evaluation").


MySQL supports arithmetic with both signed and unsigned 64-bit
values. For numeric operators (such as
[`+`](https://dev.mysql.com/doc/refman/8.0/en/arithmetic-functions.html#operator_plus) or
[`-`](https://dev.mysql.com/doc/refman/8.0/en/arithmetic-functions.html#operator_minus)) where one of
the operands is an unsigned integer, the result is unsigned by
default (see [Section 14.6.1, “Arithmetic Operators”](https://dev.mysql.com/doc/refman/8.0/en/arithmetic-functions.html "14.6.1 Arithmetic Operators")). To
override this, use the `SIGNED` or
`UNSIGNED` cast operator to cast a value to a
signed or unsigned 64-bit integer, respectively.


```sql
mysql> SELECT 1 - 2;
        -> -1
mysql> SELECT CAST(1 - 2 AS UNSIGNED);
        -> 18446744073709551615
mysql> SELECT CAST(CAST(1 - 2 AS UNSIGNED) AS SIGNED);
        -> -1
```

If either operand is a floating-point value, the result is a
floating-point value and is not affected by the preceding rule.
(In this context, [`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC") column
values are regarded as floating-point values.)


```sql
mysql> SELECT CAST(1 AS UNSIGNED) - 2.0;
        -> -1.0
```

The SQL mode affects the result of conversion operations (see
[Section 7.1.11, “Server SQL Modes”](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html "7.1.11 Server SQL Modes")). Examples:

- For conversion of a “zero” date string to a
date, [`CONVERT()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_convert) and
[`CAST()`](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#function_cast) return
`NULL` and produce a warning when the
[`NO_ZERO_DATE`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_no_zero_date) SQL mode is
enabled.


- For integer subtraction, if the
[`NO_UNSIGNED_SUBTRACTION`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_no_unsigned_subtraction)
SQL mode is enabled, the subtraction result is signed even
if any operand is unsigned.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search-mecab.html "Previous: MeCab Full-Text Parser Plugin") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/functions.html "Up: Functions and Operators") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/xml-functions.html "Next: XML Functions")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html)

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