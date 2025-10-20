---
url: https://dev.mysql.com/doc/refman/8.0/en/regexp.html
scraped_at: 2025-10-20T03:02:27.174Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/regexp.html "Hide Sidebar")

[Previous: String Comparison Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html "Previous: String Comparison Functions and Operators")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: String Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html "Up: String Functions and Operators")[Next: Character Set and Collation of Function Results](https://dev.mysql.com/doc/refman/8.0/en/string-functions-charset.html "Next: Character Set and Collation of Function Results")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/regexp.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/regexp.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/regexp.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/regexp.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/regexp.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/regexp.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/regexp.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/regexp.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/regexp.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/regexp.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/regexp.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/regexp.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/regexp.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/regexp.html)  / [Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html)  /
[String Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html)  /

Regular Expressions


### 14.8.2 Regular Expressions

**Table 14.14 Regular Expression Functions and**
**Operators**

| Name | Description |
| --- | --- |
| [`NOT REGEXP`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#operator_not-regexp) | Negation of REGEXP |
| [`REGEXP`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#operator_regexp) | Whether string matches regular expression |
| [`REGEXP_INSTR()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-instr) | Starting index of substring matching regular expression |
| [`REGEXP_LIKE()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-like) | Whether string matches regular expression |
| [`REGEXP_REPLACE()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-replace) | Replace substrings matching regular expression |
| [`REGEXP_SUBSTR()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-substr) | Return substring matching regular expression |
| [`RLIKE`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#operator_regexp) | Whether string matches regular expression |

A regular expression is a powerful way of specifying a pattern
for a complex search. This section discusses the functions and
operators available for regular expression matching and
illustrates, with examples, some of the special characters and
constructs that can be used for regular expression operations.
See also [Section 5.3.4.7, “Pattern Matching”](https://dev.mysql.com/doc/refman/8.0/en/pattern-matching.html "5.3.4.7 Pattern Matching").


MySQL implements regular expression support using International
Components for Unicode (ICU), which provides full Unicode
support and is multibyte safe. (Prior to MySQL 8.0.4, MySQL used
Henry Spencer's implementation of regular expressions,
which operates in byte-wise fashion and is not multibyte safe.
For information about ways in which applications that use
regular expressions may be affected by the implementation
change, see [Regular Expression Compatibility Considerations](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#regexp-compatibility "Regular Expression Compatibility Considerations").)


Prior to MySQL 8.0.22, it was possible to use binary string
arguments with these functions, but they yielded inconsistent
results. In MySQL 8.0.22 and later, use of a binary string with
any of the MySQL regular expression functions is rejected with
[`ER_CHARACTER_SET_MISMATCH`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_character_set_mismatch).

- [Regular Expression Function and Operator Descriptions](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#regexp-operator-descriptions "Regular Expression Function and Operator Descriptions")

- [Regular Expression Syntax](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#regexp-syntax "Regular Expression Syntax")

- [Regular Expression Resource Control](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#regexp-resource-control "Regular Expression Resource Control")

- [Regular Expression Compatibility Considerations](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#regexp-compatibility "Regular Expression Compatibility Considerations")


#### Regular Expression Function and Operator Descriptions

- [`expr\\
                NOT REGEXP pat`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#operator_not-regexp),
[`expr\\
                NOT RLIKE pat`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#operator_not-regexp)


This is the same as `NOT
                (expr REGEXP
                pat)`.


- [`expr\\
                REGEXP pat`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#operator_regexp),
[`expr\\
                RLIKE pat`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#operator_regexp)


Returns 1 if the string _`expr`_
matches the regular expression specified by the pattern
_`pat`_, 0 otherwise. If
_`expr`_ or
_`pat`_ is `NULL`,
the return value is `NULL`.


[`REGEXP`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#operator_regexp) and
[`RLIKE`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#operator_regexp) are
synonyms for [`REGEXP_LIKE()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-like).



For additional information about how matching occurs, see
the description for
[`REGEXP_LIKE()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-like).



```sql
mysql> SELECT 'Michael!' REGEXP '.*';
+------------------------+
| 'Michael!' REGEXP '.*' |
+------------------------+
|                      1 |
+------------------------+
mysql> SELECT 'new*\n*line' REGEXP 'new\\*.\\*line';
+---------------------------------------+
| 'new*\n*line' REGEXP 'new\\*.\\*line' |
+---------------------------------------+
|                                     0 |
+---------------------------------------+
mysql> SELECT 'a' REGEXP '^[a-d]';
+---------------------+
| 'a' REGEXP '^[a-d]' |
+---------------------+
|                   1 |
+---------------------+
```

- [`REGEXP_INSTR(expr,\\
                pat[,\\
                pos[,\\
                occurrence[,\\
                return_option[,\\
                match_type]]]])`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-instr)


Returns the starting index of the substring of the string
_`expr`_ that matches the regular
expression specified by the pattern
_`pat`_, 0 if there is no match. If
_`expr`_ or
_`pat`_ is `NULL`,
the return value is `NULL`. Character
indexes begin at 1.


[`REGEXP_INSTR()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-instr) takes these
optional arguments:




- _`pos`_: The position in
_`expr`_ at which to start the
search. If omitted, the default is 1.


- _`occurrence`_: Which
occurrence of a match to search for. If omitted, the
default is 1.


- _`return_option`_: Which type
of position to return. If this value is 0,
[`REGEXP_INSTR()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-instr) returns
the position of the matched substring's first
character. If this value is 1,
[`REGEXP_INSTR()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-instr) returns
the position following the matched substring. If
omitted, the default is 0.


- _`match_type`_: A string that
specifies how to perform matching. The meaning is as
described for
[`REGEXP_LIKE()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-like).


For additional information about how matching occurs, see
the description for
[`REGEXP_LIKE()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-like).


```sql
mysql> SELECT REGEXP_INSTR('dog cat dog', 'dog');
+------------------------------------+
| REGEXP_INSTR('dog cat dog', 'dog') |
+------------------------------------+
|                                  1 |
+------------------------------------+
mysql> SELECT REGEXP_INSTR('dog cat dog', 'dog', 2);
+---------------------------------------+
| REGEXP_INSTR('dog cat dog', 'dog', 2) |
+---------------------------------------+
|                                     9 |
+---------------------------------------+
mysql> SELECT REGEXP_INSTR('aa aaa aaaa', 'a{2}');
+-------------------------------------+
| REGEXP_INSTR('aa aaa aaaa', 'a{2}') |
+-------------------------------------+
|                                   1 |
+-------------------------------------+
mysql> SELECT REGEXP_INSTR('aa aaa aaaa', 'a{4}');
+-------------------------------------+
| REGEXP_INSTR('aa aaa aaaa', 'a{4}') |
+-------------------------------------+
|                                   8 |
+-------------------------------------+
```

- [`REGEXP_LIKE(expr,\\
                pat[,\\
                match_type])`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-like)


Returns 1 if the string _`expr`_
matches the regular expression specified by the pattern
_`pat`_, 0 otherwise. If
_`expr`_ or
_`pat`_ is `NULL`,
the return value is `NULL`.



The pattern can be an extended regular expression, the
syntax for which is discussed in
[Regular Expression Syntax](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#regexp-syntax "Regular Expression Syntax"). The pattern need not be a
literal string. For example, it can be specified as a
string expression or table column.



The optional _`match_type`_
argument is a string that may contain any or all the
following characters specifying how to perform matching:




- `c`: Case-sensitive matching.


- `i`: Case-insensitive matching.


- `m`: Multiple-line mode. Recognize
line terminators within the string. The default
behavior is to match line terminators only at the
start and end of the string expression.


- `n`: The `.`
character matches line terminators. The default is for
`.` matching to stop at the end of a
line.


- `u`: Unix-only line endings. Only the
newline character is recognized as a line ending by
the `.`, `^`, and
`$` match operators.


If characters specifying contradictory options are
specified within _`match_type`_,
the rightmost one takes precedence.


By default, regular expression operations use the
character set and collation of the
_`expr`_ and
_`pat`_ arguments when deciding the
type of a character and performing the comparison. If the
arguments have different character sets or collations,
coercibility rules apply as described in
[Section 12.8.4, “Collation Coercibility in Expressions”](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-coercibility.html "12.8.4 Collation Coercibility in Expressions").
Arguments may be specified with explicit collation
indicators to change comparison behavior.


```sql
mysql> SELECT REGEXP_LIKE('CamelCase', 'CAMELCASE');
+---------------------------------------+
| REGEXP_LIKE('CamelCase', 'CAMELCASE') |
+---------------------------------------+
|                                     1 |
+---------------------------------------+
mysql> SELECT REGEXP_LIKE('CamelCase', 'CAMELCASE' COLLATE utf8mb4_0900_as_cs);
+------------------------------------------------------------------+
| REGEXP_LIKE('CamelCase', 'CAMELCASE' COLLATE utf8mb4_0900_as_cs) |
+------------------------------------------------------------------+
|                                                                0 |
+------------------------------------------------------------------+
```

_`match_type`_ may be specified
with the `c` or `i`
characters to override the default case sensitivity.
Exception: If either argument is a binary string, the
arguments are handled in case-sensitive fashion as binary
strings, even if _`match_type`_
contains the `i` character.

Note

MySQL uses C escape syntax in strings (for example,
`\n` to represent the newline
character). If you want your
_`expr`_ or
_`pat`_ argument to contain a
literal `\`, you must double it.
(Unless the
[`NO_BACKSLASH_ESCAPES`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_no_backslash_escapes)
SQL mode is enabled, in which case no escape character
is used.)

```sql
mysql> SELECT REGEXP_LIKE('Michael!', '.*');
+-------------------------------+
| REGEXP_LIKE('Michael!', '.*') |
+-------------------------------+
|                             1 |
+-------------------------------+
mysql> SELECT REGEXP_LIKE('new*\n*line', 'new\\*.\\*line');
+----------------------------------------------+
| REGEXP_LIKE('new*\n*line', 'new\\*.\\*line') |
+----------------------------------------------+
|                                            0 |
+----------------------------------------------+
mysql> SELECT REGEXP_LIKE('a', '^[a-d]');
+----------------------------+
| REGEXP_LIKE('a', '^[a-d]') |
+----------------------------+
|                          1 |
+----------------------------+
```

```sql
mysql> SELECT REGEXP_LIKE('abc', 'ABC');
+---------------------------+
| REGEXP_LIKE('abc', 'ABC') |
+---------------------------+
|                         1 |
+---------------------------+
mysql> SELECT REGEXP_LIKE('abc', 'ABC', 'c');
+--------------------------------+
| REGEXP_LIKE('abc', 'ABC', 'c') |
+--------------------------------+
|                              0 |
+--------------------------------+
```

- [`REGEXP_REPLACE(expr,\\
                pat,\\
                repl[,\\
                pos[,\\
                occurrence[,\\
                match_type]]])`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-replace)


Replaces occurrences in the string
_`expr`_ that match the regular
expression specified by the pattern
_`pat`_ with the replacement string
_`repl`_, and returns the resulting
string. If _`expr`_,
_`pat`_, or
_`repl`_ is
`NULL`, the return value is
`NULL`.


[`REGEXP_REPLACE()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-replace) takes
these optional arguments:




- _`pos`_: The position in
_`expr`_ at which to start the
search. If omitted, the default is 1.


- _`occurrence`_: Which
occurrence of a match to replace. If omitted, the
default is 0 (which means “replace all
occurrences”).


- _`match_type`_: A string that
specifies how to perform matching. The meaning is as
described for
[`REGEXP_LIKE()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-like).


Prior to MySQL 8.0.17, the result returned by this
function used the `UTF-16` character set;
in MySQL 8.0.17 and later, the character set and collation
of the expression searched for matches is used. (Bug
#94203, Bug #29308212)


For additional information about how matching occurs, see
the description for
[`REGEXP_LIKE()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-like).


```sql
mysql> SELECT REGEXP_REPLACE('a b c', 'b', 'X');
+-----------------------------------+
| REGEXP_REPLACE('a b c', 'b', 'X') |
+-----------------------------------+
| a X c                             |
+-----------------------------------+
mysql> SELECT REGEXP_REPLACE('abc def ghi', '[a-z]+', 'X', 1, 3);
+----------------------------------------------------+
| REGEXP_REPLACE('abc def ghi', '[a-z]+', 'X', 1, 3) |
+----------------------------------------------------+
| abc def X                                          |
+----------------------------------------------------+
```

- [`REGEXP_SUBSTR(expr,\\
                pat[,\\
                pos[,\\
                occurrence[,\\
                match_type]]])`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-substr)


Returns the substring of the string
_`expr`_ that matches the regular
expression specified by the pattern
_`pat`_, `NULL` if
there is no match. If _`expr`_ or
_`pat`_ is `NULL`,
the return value is `NULL`.


[`REGEXP_SUBSTR()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-substr) takes these
optional arguments:




- _`pos`_: The position in
_`expr`_ at which to start the
search. If omitted, the default is 1.


- _`occurrence`_: Which
occurrence of a match to search for. If omitted, the
default is 1.


- _`match_type`_: A string that
specifies how to perform matching. The meaning is as
described for
[`REGEXP_LIKE()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-like).


Prior to MySQL 8.0.17, the result returned by this
function used the `UTF-16` character set;
in MySQL 8.0.17 and later, the character set and collation
of the expression searched for matches is used. (Bug
#94203, Bug #29308212)


For additional information about how matching occurs, see
the description for
[`REGEXP_LIKE()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-like).


```sql
mysql> SELECT REGEXP_SUBSTR('abc def ghi', '[a-z]+');
+----------------------------------------+
| REGEXP_SUBSTR('abc def ghi', '[a-z]+') |
+----------------------------------------+
| abc                                    |
+----------------------------------------+
mysql> SELECT REGEXP_SUBSTR('abc def ghi', '[a-z]+', 1, 3);
+----------------------------------------------+
| REGEXP_SUBSTR('abc def ghi', '[a-z]+', 1, 3) |
+----------------------------------------------+
| ghi                                          |
+----------------------------------------------+
```

#### Regular Expression Syntax

A regular expression describes a set of strings. The simplest
regular expression is one that has no special characters in
it. For example, the regular expression
`hello` matches `hello` and
nothing else.


Nontrivial regular expressions use certain special constructs
so that they can match more than one string. For example, the
regular expression `hello|world` contains the
`|` alternation operator and matches either
the `hello` or `world`.


As a more complex example, the regular expression
`B[an]*s` matches any of the strings
`Bananas`, `Baaaaas`,
`Bs`, and any other string starting with a
`B`, ending with an `s`, and
containing any number of `a` or
`n` characters in between.


The following list covers some of the basic special characters
and constructs that can be used in regular expressions. For
information about the full regular expression syntax supported
by the ICU library used to implement regular expression
support, visit the
[International Components for Unicode web site](https://unicode-org.github.io/icu/userguide/).

- `^`


Match the beginning of a string.



```sql
mysql> SELECT REGEXP_LIKE('fo\nfo', '^fo$');                   -> 0
mysql> SELECT REGEXP_LIKE('fofo', '^fo');                      -> 1
```

- `$`


Match the end of a string.



```sql
mysql> SELECT REGEXP_LIKE('fo\no', '^fo\no$');                 -> 1
mysql> SELECT REGEXP_LIKE('fo\no', '^fo$');                    -> 0
```

- `.`


Match any character (including carriage return and
newline, although to match these in the middle of a
string, the `m` (multiple line)
match-control character or the `(?m)`
within-pattern modifier must be given).



```sql
mysql> SELECT REGEXP_LIKE('fofo', '^f.*$');                    -> 1
mysql> SELECT REGEXP_LIKE('fo\r\nfo', '^f.*$');                -> 0
mysql> SELECT REGEXP_LIKE('fo\r\nfo', '^f.*$', 'm');           -> 1
mysql> SELECT REGEXP_LIKE('fo\r\nfo', '(?m)^f.*$');           -> 1
```

- `a*`


Match any sequence of zero or more `a`
characters.



```sql
mysql> SELECT REGEXP_LIKE('Ban', '^Ba*n');                     -> 1
mysql> SELECT REGEXP_LIKE('Baaan', '^Ba*n');                   -> 1
mysql> SELECT REGEXP_LIKE('Bn', '^Ba*n');                      -> 1
```

- `a+`


Match any sequence of one or more `a`
characters.



```sql
mysql> SELECT REGEXP_LIKE('Ban', '^Ba+n');                     -> 1
mysql> SELECT REGEXP_LIKE('Bn', '^Ba+n');                      -> 0
```

- `a?`


Match either zero or one `a` character.



```sql
mysql> SELECT REGEXP_LIKE('Bn', '^Ba?n');                      -> 1
mysql> SELECT REGEXP_LIKE('Ban', '^Ba?n');                     -> 1
mysql> SELECT REGEXP_LIKE('Baan', '^Ba?n');                    -> 0
```

- `de|abc`


Alternation; match either of the sequences
`de` or `abc`.



```sql
mysql> SELECT REGEXP_LIKE('pi', 'pi|apa');                     -> 1
mysql> SELECT REGEXP_LIKE('axe', 'pi|apa');                    -> 0
mysql> SELECT REGEXP_LIKE('apa', 'pi|apa');                    -> 1
mysql> SELECT REGEXP_LIKE('apa', '^(pi|apa)$');                -> 1
mysql> SELECT REGEXP_LIKE('pi', '^(pi|apa)$');                 -> 1
mysql> SELECT REGEXP_LIKE('pix', '^(pi|apa)$');                -> 0
```

- `(abc)*`


Match zero or more instances of the sequence
`abc`.



```sql
mysql> SELECT REGEXP_LIKE('pi', '^(pi)*$');                    -> 1
mysql> SELECT REGEXP_LIKE('pip', '^(pi)*$');                   -> 0
mysql> SELECT REGEXP_LIKE('pipi', '^(pi)*$');                  -> 1
```

- `{1}`, `{2,3}`


Repetition;
`{n}` and
`{m,n}`
notation provide a more general way of writing regular
expressions that match many occurrences of the previous
atom (or “piece”) of the pattern.
_`m`_ and
_`n`_ are integers.




- `a*`


Can be written as `a{0,}`.


- `a+`


Can be written as `a{1,}`.


- `a?`


Can be written as `a{0,1}`.


To be more precise,
`a{n}` matches
exactly _`n`_ instances of
`a`.
`a{n,}`
matches _`n`_ or more instances of
`a`.
`a{m,n}`
matches _`m`_ through
_`n`_ instances of
`a`, inclusive. If both
_`m`_ and
_`n`_ are given,
_`m`_ must be less than or equal to
_`n`_.


```sql
mysql> SELECT REGEXP_LIKE('abcde', 'a[bcd]{2}e');              -> 0
mysql> SELECT REGEXP_LIKE('abcde', 'a[bcd]{3}e');              -> 1
mysql> SELECT REGEXP_LIKE('abcde', 'a[bcd]{1,10}e');           -> 1
```

- `[a-dX]`, `[^a-dX]`


Matches any character that is (or is not, if
`^` is used) either `a`,
`b`, `c`,
`d` or `X`. A
`-` character between two other
characters forms a range that matches all characters from
the first character to the second. For example,
`[0-9]` matches any decimal digit. To
include a literal `]` character, it must
immediately follow the opening bracket
`[`. To include a literal\
`-` character, it must be written first\
or last. Any character that does not have a defined\
special meaning inside a `[]` pair\
matches only itself.\
\
\
\
```sql\
mysql> SELECT REGEXP_LIKE('aXbc', '[a-dXYZ]');                 -> 1\
mysql> SELECT REGEXP_LIKE('aXbc', '^[a-dXYZ]$');               -> 0\
mysql> SELECT REGEXP_LIKE('aXbc', '^[a-dXYZ]+$');              -> 1\
mysql> SELECT REGEXP_LIKE('aXbc', '^[^a-dXYZ]+$');             -> 0\
mysql> SELECT REGEXP_LIKE('gheis', '^[^a-dXYZ]+$');            -> 1\
mysql> SELECT REGEXP_LIKE('gheisa', '^[^a-dXYZ]+$');           -> 0\
```\
\
- `[=character_class=]`\
\
\
Within a bracket expression (written using\
`[` and `]`),\
`[=character_class=]` represents an\
equivalence class. It matches all characters with the same\
collation value, including itself. For example, if\
`o` and `(+)` are the\
members of an equivalence class,\
`[[=o=]]`, `[[=(+)=]]`,\
and `[o(+)]` are all synonymous. An\
equivalence class may not be used as an endpoint of a\
range.\
\
\
- `[:character_class:]`\
\
\
Within a bracket expression (written using\
`[` and `]`),\
`[:character_class:]` represents a\
character class that matches all characters belonging to\
that class. The following table lists the standard class\
names. These names stand for the character classes defined\
in the `ctype(3)` manual page. A\
particular locale may provide other class names. A\
character class may not be used as an endpoint of a range.\
\
\
\
\
\
| Character Class Name | Meaning |\
| --- | --- |\
| `alnum` | Alphanumeric characters |\
| `alpha` | Alphabetic characters |\
| `blank` | Whitespace characters |\
| `cntrl` | Control characters |\
| `digit` | Digit characters |\
| `graph` | Graphic characters |\
| `lower` | Lowercase alphabetic characters |\
| `print` | Graphic or space characters |\
| `punct` | Punctuation characters |\
| `space` | Space, tab, newline, and carriage return |\
| `upper` | Uppercase alphabetic characters |\
| `xdigit` | Hexadecimal digit characters |\
\
\
\
\
```sql\
mysql> SELECT REGEXP_LIKE('justalnums', '[[:alnum:]]+');       -> 1\
mysql> SELECT REGEXP_LIKE('!!', '[[:alnum:]]+');               -> 0\
```\
\
\
\
Because ICU is aware of all alphabetic characters in\
`utf16_general_ci`, some character\
classes may not perform as quickly as character ranges.\
For example, `[a-zA-Z]` is known to work\
much more quickly than `[[:alpha:]]`, and\
`[0-9]` is generally much faster than\
`[[:digit:]]`. If you are migrating\
applications using `[[:alpha:]]` or\
`[[:digit:]]` from an older version of\
MySQL, you should replace these with the equivalent ranges\
for use with MySQL 8.0.\
\
\
To use a literal instance of a special character in a regular\
expression, precede it by two backslash (\\) characters. The\
MySQL parser interprets one of the backslashes, and the\
regular expression library interprets the other. For example,\
to match the string `1+2` that contains the\
special `+` character, only the last of the\
following regular expressions is the correct one:\
\
\
```sql\
mysql> SELECT REGEXP_LIKE('1+2', '1+2');                       -> 0\
mysql> SELECT REGEXP_LIKE('1+2', '1\+2');                      -> 0\
mysql> SELECT REGEXP_LIKE('1+2', '1\\+2');                     -> 1\
```\
\
#### Regular Expression Resource Control\
\
[`REGEXP_LIKE()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-like) and similar\
functions use resources that can be controlled by setting\
system variables:\
\
- The match engine uses memory for its internal stack. To\
control the maximum available memory for the stack in\
bytes, set the\
[`regexp_stack_limit`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_regexp_stack_limit) system\
variable.\
\
\
- The match engine operates in steps. To control the maximum\
number of steps performed by the engine (and thus\
indirectly the execution time), set the\
[`regexp_time_limit`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_regexp_time_limit) system\
variable. Because this limit is expressed as number of\
steps, it affects execution time only indirectly.\
Typically, it is on the order of milliseconds.\
\
\
#### Regular Expression Compatibility Considerations\
\
Prior to MySQL 8.0.4, MySQL used the Henry Spencer regular\
expression library to support regular expression operations,\
rather than International Components for Unicode (ICU). The\
following discussion describes differences between the Spencer\
and ICU libraries that may affect applications:\
\
- With the Spencer library, the\
[`REGEXP`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#operator_regexp) and\
[`RLIKE`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#operator_regexp)\
operators work in byte-wise fashion, so they are not\
multibyte safe and may produce unexpected results with\
multibyte character sets. In addition, these operators\
compare characters by their byte values and accented\
characters may not compare as equal even if a given\
collation treats them as equal.\
\
\
\
ICU has full Unicode support and is multibyte safe. Its\
regular expression functions treat all strings as\
`UTF-16`. You should keep in mind that\
positional indexes are based on 16-bit chunks and not on\
code points. This means that, when passed to such\
functions, characters using more than one chunk may\
produce unanticipated results, such as those shown here:\
\
\
\
```sql\
mysql> SELECT REGEXP_INSTR('🍣🍣b', 'b');\
+--------------------------+\
| REGEXP_INSTR('??b', 'b') |\
+--------------------------+\
|                        5 |\
+--------------------------+\
1 row in set (0.00 sec)\
\
mysql> SELECT REGEXP_INSTR('🍣🍣bxxx', 'b', 4);\
+--------------------------------+\
| REGEXP_INSTR('??bxxx', 'b', 4) |\
+--------------------------------+\
|                              5 |\
+--------------------------------+\
1 row in set (0.00 sec)\
```\
\
\
\
Characters within the Unicode Basic Multilingual Plane,\
which includes characters used by most modern languages,\
are safe in this regard:\
\
\
\
```sql\
mysql> SELECT REGEXP_INSTR('бжb', 'b');\
+----------------------------+\
| REGEXP_INSTR('бжb', 'b')   |\
+----------------------------+\
|                          3 |\
+----------------------------+\
1 row in set (0.00 sec)\
\
mysql> SELECT REGEXP_INSTR('עבb', 'b');\
+----------------------------+\
| REGEXP_INSTR('עבb', 'b')   |\
+----------------------------+\
|                          3 |\
+----------------------------+\
1 row in set (0.00 sec)\
\
mysql> SELECT REGEXP_INSTR('µå周çб', '周');\
+------------------------------------+\
| REGEXP_INSTR('µå周çб', '周')       |\
+------------------------------------+\
|                                  3 |\
+------------------------------------+\
1 row in set (0.00 sec)\
```\
\
\
\
Emoji, such as the “sushi” character\
`🍣` (U+1F363) used in the first two\
examples, are not included in the Basic Multilingual\
Plane, but rather in Unicode's Supplementary\
Multilingual Plane. Another issue can arise with emoji and\
other 4-byte characters when\
[`REGEXP_SUBSTR()`](https://dev.mysql.com/doc/refman/8.0/en/regexp.html#function_regexp-substr) or a\
similar function begins searching in the middle of a\
character. Each of the two statements in the following\
example starts from the second 2-byte position in the\
first argument. The first statement works on a string\
consisting solely of 2-byte (BMP) characters. The second\
statement contains 4-byte characters which are incorrectly\
interpreted in the result because the first two bytes are\
stripped off and so the remainder of the character data is\
misaligned.\
\
\
\
```sql\
mysql> SELECT REGEXP_SUBSTR('周周周周', '.*', 2);\
+----------------------------------------+\
| REGEXP_SUBSTR('周周周周', '.*', 2)     |\
+----------------------------------------+\
| 周周周                                 |\
+----------------------------------------+\
1 row in set (0.00 sec)\
\
mysql> SELECT REGEXP_SUBSTR('🍣🍣🍣🍣', '.*', 2);\
+--------------------------------+\
| REGEXP_SUBSTR('????', '.*', 2) |\
+--------------------------------+\
| ?㳟揘㳟揘㳟揘                  |\
+--------------------------------+\
1 row in set (0.00 sec)\
```\
\
- For the `.` operator, the Spencer library\
matches line-terminator characters (carriage return,\
newline) anywhere in string expressions, including in the\
middle. To match line terminator characters in the middle\
of strings with ICU, specify the `m`\
match-control character.\
\
\
- The Spencer library supports word-beginning and word-end\
boundary markers ( `[[:<:]]` and\
`[[:>:]]` notation). ICU does not. For\
ICU, you can use `\b` to match word\
boundaries; double the backslash because MySQL interprets\
it as the escape character within strings.\
\
\
- The Spencer library supports collating element bracket\
expressions ( `[.characters.]` notation).\
ICU does not.\
\
\
- For repetition counts ( `{n}` and\
`{m,n}` notation), the Spencer library\
has a maximum of 255. ICU has no such limit, although the\
maximum number of match engine steps can be limited by\
setting the\
[`regexp_time_limit`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_regexp_time_limit) system\
variable.\
\
\
- ICU interprets parentheses as metacharacters. To specify a\
literal open `(` or close parenthesis\
`)` in a regular expression, it must be\
escaped:\
\
\
\
```sql\
mysql> SELECT REGEXP_LIKE('(', '(');\
ERROR 3692 (HY000): Mismatched parenthesis in regular expression.\
mysql> SELECT REGEXP_LIKE('(', '\\(');\
+-------------------------+\
| REGEXP_LIKE('(', '\\(') |\
+-------------------------+\
|                       1 |\
+-------------------------+\
mysql> SELECT REGEXP_LIKE(')', ')');\
ERROR 3692 (HY000): Mismatched parenthesis in regular expression.\
mysql> SELECT REGEXP_LIKE(')', '\\)');\
+-------------------------+\
| REGEXP_LIKE(')', '\\)') |\
+-------------------------+\
|                       1 |\
+-------------------------+\
```\
\
- ICU also interprets square brackets as metacharacters, but\
only the opening square bracket need be escaped to be used\
as a literal character:\
\
\
\
```sql\
mysql> SELECT REGEXP_LIKE('[', '[');\
ERROR 3696 (HY000): The regular expression contains an\
unclosed bracket expression.\
mysql> SELECT REGEXP_LIKE('[', '\\[');\
+-------------------------+\
| REGEXP_LIKE('[', '\\[') |\
+-------------------------+\
|                       1 |\
+-------------------------+\
mysql> SELECT REGEXP_LIKE(']', ']');\
+-----------------------+\
| REGEXP_LIKE(']', ']') |\
+-----------------------+\
|                     1 |\
+-----------------------+\
```\
\
\
[PREV](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html "Previous: String Comparison Functions and Operators") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html "Up: String Functions and Operators") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/string-functions-charset.html "Next: Character Set and Collation of Function Results")\
\
[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/regexp.html)\
\
[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)\
\
[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)\
\
[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/regexp.html)\
\
[PDF (US Ltr)](https://downloads.mysql.com/docs/refman-8.0-en.pdf)\
\- 43.3Mb\
\
[PDF (A4)](https://downloads.mysql.com/docs/refman-8.0-en.a4.pdf)\
\- 43.4Mb\
\
[Man Pages (TGZ)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.tar.gz)\
\- 297.2Kb\
\
[Man Pages (Zip)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.zip)\
\- 402.4Kb\
\
[Info (Gzip)](https://downloads.mysql.com/docs/mysql-8.0.info.gz)\
\- 4.3Mb\
\
[Info (Zip)](https://downloads.mysql.com/docs/mysql-8.0.info.zip)\
\- 4.3Mb\
\
[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/regexp.html)\
\
[MySQL Backup and Recovery](https://dev.mysql.com/doc/mysql-backup-excerpt/8.0/en/)\
\
[MySQL Globalization](https://dev.mysql.com/doc/mysql-g11n-excerpt/8.0/en/)\
\
[MySQL Information Schema](https://dev.mysql.com/doc/mysql-infoschema-excerpt/8.0/en/)\
\
[MySQL Installation Guide](https://dev.mysql.com/doc/mysql-installation-excerpt/8.0/en/)\
\
[Security in MySQL](https://dev.mysql.com/doc/mysql-security-excerpt/8.0/en/)\
\
[Starting and Stopping MySQL](https://dev.mysql.com/doc/mysql-startstop-excerpt/8.0/en/)\
\
[MySQL and Linux/Unix](https://dev.mysql.com/doc/mysql-linuxunix-excerpt/8.0/en/)\
\
[MySQL and Windows](https://dev.mysql.com/doc/mysql-windows-excerpt/8.0/en/)\
\
[MySQL and macOS](https://dev.mysql.com/doc/mysql-macos-excerpt/8.0/en/)\
\
[MySQL and Solaris](https://dev.mysql.com/doc/mysql-solaris-excerpt/8.0/en/)\
\
[Building MySQL from Source](https://dev.mysql.com/doc/mysql-sourcebuild-excerpt/8.0/en/)\
\
[MySQL Restrictions and Limitations](https://dev.mysql.com/doc/mysql-reslimits-excerpt/8.0/en/)\
\
[MySQL Partitioning](https://dev.mysql.com/doc/mysql-partitioning-excerpt/8.0/en/)\
\
[MySQL Tutorial](https://dev.mysql.com/doc/mysql-tutorial-excerpt/8.0/en/)\
\
[MySQL Performance Schema](https://dev.mysql.com/doc/mysql-perfschema-excerpt/8.0/en/)\
\
[MySQL Replication](https://dev.mysql.com/doc/mysql-replication-excerpt/8.0/en/)\
\
[Using the MySQL Yum Repository](https://dev.mysql.com/doc/mysql-repo-excerpt/8.0/en/)\
\
[MySQL NDB Cluster 8.0](https://dev.mysql.com/doc/mysql-cluster-excerpt/8.0/en/)