---
url: https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html
scraped_at: 2025-10-20T03:08:09.449Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "Hide Sidebar")

[Previous: DECLARE ... HANDLER Statement](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html "Previous: DECLARE ... HANDLER Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Condition Handling](https://dev.mysql.com/doc/refman/8.0/en/condition-handling.html "Up: Condition Handling")[Next: RESIGNAL Statement](https://dev.mysql.com/doc/refman/8.0/en/resignal.html "Next: RESIGNAL Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/get-diagnostics.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/get-diagnostics.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/get-diagnostics.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/get-diagnostics.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/get-diagnostics.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/get-diagnostics.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/get-diagnostics.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/get-diagnostics.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Compound Statement Syntax](https://dev.mysql.com/doc/refman/8.0/en/sql-compound-statements.html)  /
[Condition Handling](https://dev.mysql.com/doc/refman/8.0/en/condition-handling.html)  /

GET DIAGNOSTICS Statement


#### 15.6.7.3 GET DIAGNOSTICS Statement

``` sql

GET [CURRENT | STACKED] DIAGNOSTICS {
    statement_information_item
    [, statement_information_item] ...
  | CONDITION condition_number
    condition_information_item
    [, condition_information_item] ...
}

statement_information_item:
    target = statement_information_item_name

condition_information_item:
    target = condition_information_item_name

statement_information_item_name: {
    NUMBER
  | ROW_COUNT
}

condition_information_item_name: {
    CLASS_ORIGIN
  | SUBCLASS_ORIGIN
  | RETURNED_SQLSTATE
  | MESSAGE_TEXT
  | MYSQL_ERRNO
  | CONSTRAINT_CATALOG
  | CONSTRAINT_SCHEMA
  | CONSTRAINT_NAME
  | CATALOG_NAME
  | SCHEMA_NAME
  | TABLE_NAME
  | COLUMN_NAME
  | CURSOR_NAME
}

condition_number, target:
    (see following discussion)
```

SQL statements produce diagnostic information that populates the
diagnostics area. The [`GET\\
        DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") statement enables applications to inspect
this information. (You can also use [`SHOW\\
        WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") or [`SHOW ERRORS`](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html "15.7.7.17 SHOW ERRORS Statement")
to see conditions or errors.)


No special privileges are required to execute
[`GET DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement").


The keyword `CURRENT` means to retrieve
information from the current diagnostics area. The keyword
`STACKED` means to retrieve information from
the second diagnostics area, which is available only if the
current context is a condition handler. If neither keyword is
given, the default is to use the current diagnostics area.


The [`GET DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") statement is
typically used in a handler within a stored program. It is a
MySQL extension that
[`GET [CURRENT]\\
        DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") is permitted outside handler context to
check the execution of any SQL statement. For example, if you
invoke the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client program, you can
enter these statements at the prompt:


``` sql

mysql> DROP TABLE test.no_such_table;
ERROR 1051 (42S02): Unknown table 'test.no_such_table'
mysql> GET DIAGNOSTICS CONDITION 1
         @p1 = RETURNED_SQLSTATE, @p2 = MESSAGE_TEXT;
mysql> SELECT @p1, @p2;
+-------+------------------------------------+
| @p1   | @p2                                |
+-------+------------------------------------+
| 42S02 | Unknown table 'test.no_such_table' |
+-------+------------------------------------+
```

This extension applies only to the current diagnostics area. It
does not apply to the second diagnostics area because
`GET STACKED DIAGNOSTICS` is permitted only if
the current context is a condition handler. If that is not the
case, a `GET STACKED DIAGNOSTICS when handler not
        active` error occurs.


For a description of the diagnostics area, see
[Section 15.6.7.7, “The MySQL Diagnostics Area”](https://dev.mysql.com/doc/refman/8.0/en/diagnostics-area.html "15.6.7.7 The MySQL Diagnostics Area"). Briefly, it contains two
kinds of information:

- Statement information, such as the number of conditions that
occurred or the affected-rows count.


- Condition information, such as the error code and message.
If a statement raises multiple conditions, this part of the
diagnostics area has a condition area for each one. If a
statement raises no conditions, this part of the diagnostics
area is empty.


For a statement that produces three conditions, the diagnostics
area contains statement and condition information like this:


``` none

Statement information:
  row count
  ... other statement information items ...
Condition area list:
  Condition area 1:
    error code for condition 1
    error message for condition 1
    ... other condition information items ...
  Condition area 2:
    error code for condition 2:
    error message for condition 2
    ... other condition information items ...
  Condition area 3:
    error code for condition 3
    error message for condition 3
    ... other condition information items ...
```

[`GET DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") can obtain either
statement or condition information, but not both in the same
statement:

- To obtain statement information, retrieve the desired
statement items into target variables. This instance of
[`GET DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") assigns the
number of available conditions and the rows-affected count
to the user variables `@p1` and
`@p2`:




``` sql

GET DIAGNOSTICS @p1 = NUMBER, @p2 = ROW_COUNT;
```

- To obtain condition information, specify the condition
number and retrieve the desired condition items into target
variables. This instance of [`GET\\
              DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") assigns the SQLSTATE value and error
message to the user variables `@p3` and
`@p4`:




``` sql

GET DIAGNOSTICS CONDITION 1
    @p3 = RETURNED_SQLSTATE, @p4 = MESSAGE_TEXT;
```


The retrieval list specifies one or more
`target =
        item_name` assignments,
separated by commas. Each assignment names a target variable and
either a
_`statement_information_item_name`_ or
_`condition_information_item_name`_
designator, depending on whether the statement retrieves
statement or condition information.


Valid _`target`_ designators for storing
item information can be stored procedure or function parameters,
stored program local variables declared with
[`DECLARE`](https://dev.mysql.com/doc/refman/8.0/en/declare.html "15.6.3 DECLARE Statement"), or user-defined
variables.


Valid _`condition_number`_ designators
can be stored procedure or function parameters, stored program
local variables declared with
[`DECLARE`](https://dev.mysql.com/doc/refman/8.0/en/declare.html "15.6.3 DECLARE Statement"), user-defined variables,
system variables, or literals. A character literal may include a
_`_charset`_ introducer. A warning occurs
if the condition number is not in the range from 1 to the number
of condition areas that have information. In this case, the
warning is added to the diagnostics area without clearing it.


When a condition occurs, MySQL does not populate all condition
items recognized by [`GET\\
        DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement"). For example:


``` sql

mysql> GET DIAGNOSTICS CONDITION 1
         @p5 = SCHEMA_NAME, @p6 = TABLE_NAME;
mysql> SELECT @p5, @p6;
+------+------+
| @p5  | @p6  |
+------+------+
|      |      |
+------+------+
```

In standard SQL, if there are multiple conditions, the first
condition relates to the `SQLSTATE` value
returned for the previous SQL statement. In MySQL, this is not
guaranteed. To get the main error, you cannot do this:


``` sql

GET DIAGNOSTICS CONDITION 1 @errno = MYSQL_ERRNO;
```

Instead, retrieve the condition count first, then use it to
specify which condition number to inspect:


``` sql

GET DIAGNOSTICS @cno = NUMBER;
GET DIAGNOSTICS CONDITION @cno @errno = MYSQL_ERRNO;
```

For information about permissible statement and condition
information items, and which ones are populated when a condition
occurs, see
[Diagnostics Area Information Items](https://dev.mysql.com/doc/refman/8.0/en/diagnostics-area.html#diagnostics-area-information-items "Diagnostics Area Information Items").


Here is an example that uses [`GET\\
        DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") and an exception handler in stored
procedure context to assess the outcome of an insert operation.
If the insert was successful, the procedure uses
[`GET DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") to get the
rows-affected count. This shows that you can use
[`GET DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") multiple times to
retrieve information about a statement as long as the current
diagnostics area has not been cleared.


``` sql

CREATE PROCEDURE do_insert(value INT)
BEGIN
  -- Declare variables to hold diagnostics area information
  DECLARE code CHAR(5) DEFAULT '00000';
  DECLARE msg TEXT;
  DECLARE nrows INT;
  DECLARE result TEXT;
  -- Declare exception handler for failed insert
  DECLARE CONTINUE HANDLER FOR SQLEXCEPTION
    BEGIN
      GET DIAGNOSTICS CONDITION 1
        code = RETURNED_SQLSTATE, msg = MESSAGE_TEXT;
    END;

  -- Perform the insert
  INSERT INTO t1 (int_col) VALUES(value);
  -- Check whether the insert was successful
  IF code = '00000' THEN
    GET DIAGNOSTICS nrows = ROW_COUNT;
    SET result = CONCAT('insert succeeded, row count = ',nrows);
  ELSE
    SET result = CONCAT('insert failed, error = ',code,', message = ',msg);
  END IF;
  -- Say what happened
  SELECT result;
END;
```

Suppose that `t1.int_col` is an integer column
that is declared as `NOT NULL`. The procedure
produces these results when invoked to insert
non- `NULL` and `NULL` values,
respectively:


``` sql

mysql> CALL do_insert(1);
+---------------------------------+
| result                          |
+---------------------------------+
| insert succeeded, row count = 1 |
+---------------------------------+

mysql> CALL do_insert(NULL);
+-------------------------------------------------------------------------+
| result                                                                  |
+-------------------------------------------------------------------------+
| insert failed, error = 23000, message = Column 'int_col' cannot be null |
+-------------------------------------------------------------------------+
```

When a condition handler activates, a push to the diagnostics
area stack occurs:

- The first (current) diagnostics area becomes the second
(stacked) diagnostics area and a new current diagnostics
area is created as a copy of it.


- [`GET\\
              [CURRENT] DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") and
[`GET STACKED\\
              DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") can be used within the handler to
access the contents of the current and stacked diagnostics
areas.


- Initially, both diagnostics areas return the same result, so
it is possible to get information from the current
diagnostics area about the condition that activated the
handler, _as long as_ you execute no
statements within the handler that change its current
diagnostics area.


- However, statements executing within the handler can modify
the current diagnostics area, clearing and setting its
contents according to the normal rules (see
[How the Diagnostics Area is Cleared and Populated](https://dev.mysql.com/doc/refman/8.0/en/diagnostics-area.html#diagnostics-area-populating "How the Diagnostics Area is Cleared and Populated")).



A more reliable way to obtain information about the
handler-activating condition is to use the stacked
diagnostics area, which cannot be modified by statements
executing within the handler except
[`RESIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/resignal.html "15.6.7.4 RESIGNAL Statement"). For information
about when the current diagnostics area is set and cleared,
see [Section 15.6.7.7, “The MySQL Diagnostics Area”](https://dev.mysql.com/doc/refman/8.0/en/diagnostics-area.html "15.6.7.7 The MySQL Diagnostics Area").


The next example shows how `GET STACKED
        DIAGNOSTICS` can be used within a handler to obtain
information about the handled exception, even after the current
diagnostics area has been modified by handler statements.


Within a stored procedure `p()`, we attempt to
insert two values into a table that contains a `TEXT NOT
        NULL` column. The first value is a
non- `NULL` string and the second is
`NULL`. The column prohibits
`NULL` values, so the first insert succeeds but
the second causes an exception. The procedure includes an
exception handler that maps attempts to insert
`NULL` into inserts of the empty string:


``` sql

DROP TABLE IF EXISTS t1;
CREATE TABLE t1 (c1 TEXT NOT NULL);
DROP PROCEDURE IF EXISTS p;
delimiter //
CREATE PROCEDURE p ()
BEGIN
  -- Declare variables to hold diagnostics area information
  DECLARE errcount INT;
  DECLARE errno INT;
  DECLARE msg TEXT;
  DECLARE EXIT HANDLER FOR SQLEXCEPTION
  BEGIN
    -- Here the current DA is nonempty because no prior statements
    -- executing within the handler have cleared it
    GET CURRENT DIAGNOSTICS CONDITION 1
      errno = MYSQL_ERRNO, msg = MESSAGE_TEXT;
    SELECT 'current DA before mapped insert' AS op, errno, msg;
    GET STACKED DIAGNOSTICS CONDITION 1
      errno = MYSQL_ERRNO, msg = MESSAGE_TEXT;
    SELECT 'stacked DA before mapped insert' AS op, errno, msg;

    -- Map attempted NULL insert to empty string insert
    INSERT INTO t1 (c1) VALUES('');

    -- Here the current DA should be empty (if the INSERT succeeded),
    -- so check whether there are conditions before attempting to
    -- obtain condition information
    GET CURRENT DIAGNOSTICS errcount = NUMBER;
    IF errcount = 0
    THEN
      SELECT 'mapped insert succeeded, current DA is empty' AS op;
    ELSE
      GET CURRENT DIAGNOSTICS CONDITION 1
        errno = MYSQL_ERRNO, msg = MESSAGE_TEXT;
      SELECT 'current DA after mapped insert' AS op, errno, msg;
    END IF ;
    GET STACKED DIAGNOSTICS CONDITION 1
      errno = MYSQL_ERRNO, msg = MESSAGE_TEXT;
    SELECT 'stacked DA after mapped insert' AS op, errno, msg;
  END;
  INSERT INTO t1 (c1) VALUES('string 1');
  INSERT INTO t1 (c1) VALUES(NULL);
END;
//
delimiter ;
CALL p();
SELECT * FROM t1;
```

When the handler activates, a copy of the current diagnostics
area is pushed to the diagnostics area stack. The handler first
displays the contents of the current and stacked diagnostics
areas, which are both the same initially:


``` none

+---------------------------------+-------+----------------------------+
| op                              | errno | msg                        |
+---------------------------------+-------+----------------------------+
| current DA before mapped insert |  1048 | Column 'c1' cannot be null |
+---------------------------------+-------+----------------------------+

+---------------------------------+-------+----------------------------+
| op                              | errno | msg                        |
+---------------------------------+-------+----------------------------+
| stacked DA before mapped insert |  1048 | Column 'c1' cannot be null |
+---------------------------------+-------+----------------------------+
```

Statements executing after the [`GET\\
        DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") statements may reset the current
diagnostics area. statements may reset the current diagnostics
area. For example, the handler maps the `NULL`
insert to an empty-string insert and displays the result. The
new insert succeeds and clears the current diagnostics area, but
the stacked diagnostics area remains unchanged and still
contains information about the condition that activated the
handler:


``` none

+----------------------------------------------+
| op                                           |
+----------------------------------------------+
| mapped insert succeeded, current DA is empty |
+----------------------------------------------+

+--------------------------------+-------+----------------------------+
| op                             | errno | msg                        |
+--------------------------------+-------+----------------------------+
| stacked DA after mapped insert |  1048 | Column 'c1' cannot be null |
+--------------------------------+-------+----------------------------+
```

When the condition handler ends, its current diagnostics area is
popped from the stack and the stacked diagnostics area becomes
the current diagnostics area in the stored procedure.


After the procedure returns, the table contains two rows. The
empty row results from the attempt to insert
`NULL` that was mapped to an empty-string
insert:


``` none

+----------+
| c1       |
+----------+
| string 1 |
|          |
+----------+
```

In the preceding example, the first two [`GET\\
        DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") statements within the condition handler
that retrieve information from the current and stacked
diagnostics areas return the same values. This is not the case
if statements that reset the current diagnostics area execute
earlier within the handler. Suppose that `p()`
is rewritten to place the [`DECLARE`](https://dev.mysql.com/doc/refman/8.0/en/declare.html "15.6.3 DECLARE Statement")
statements within the handler definition rather than preceding
it:


``` sql

CREATE PROCEDURE p ()
BEGIN
  DECLARE EXIT HANDLER FOR SQLEXCEPTION
  BEGIN
    -- Declare variables to hold diagnostics area information
    DECLARE errcount INT;
    DECLARE errno INT;
    DECLARE msg TEXT;
    GET CURRENT DIAGNOSTICS CONDITION 1
      errno = MYSQL_ERRNO, msg = MESSAGE_TEXT;
    SELECT 'current DA before mapped insert' AS op, errno, msg;
    GET STACKED DIAGNOSTICS CONDITION 1
      errno = MYSQL_ERRNO, msg = MESSAGE_TEXT;
    SELECT 'stacked DA before mapped insert' AS op, errno, msg;
...
```

In this case, the result is version dependent:

- Before MySQL 5.7.2, [`DECLARE`](https://dev.mysql.com/doc/refman/8.0/en/declare.html "15.6.3 DECLARE Statement")
does not change the current diagnostics area, so the first
two [`GET DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement")
statements return the same result, just as in the original
version of `p()`.



In MySQL 5.7.2, work was done to ensure that all
nondiagnostic statements populate the diagnostics area, per
the SQL standard. [`DECLARE`](https://dev.mysql.com/doc/refman/8.0/en/declare.html "15.6.3 DECLARE Statement") is
one of them, so in 5.7.2 and higher,
[`DECLARE`](https://dev.mysql.com/doc/refman/8.0/en/declare.html "15.6.3 DECLARE Statement") statements executing
at the beginning of the handler clear the current
diagnostics area and the [`GET\\
              DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") statements produce different results:




``` none

+---------------------------------+-------+------+
| op                              | errno | msg  |
+---------------------------------+-------+------+
| current DA before mapped insert |  NULL | NULL |
+---------------------------------+-------+------+

+---------------------------------+-------+----------------------------+
| op                              | errno | msg                        |
+---------------------------------+-------+----------------------------+
| stacked DA before mapped insert |  1048 | Column 'c1' cannot be null |
+---------------------------------+-------+----------------------------+
```


To avoid this issue within a condition handler when seeking to
obtain information about the condition that activated the
handler, be sure to access the stacked diagnostics area, not the
current diagnostics area.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html "Previous: DECLARE ... HANDLER Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/condition-handling.html "Up: Condition Handling") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/resignal.html "Next: RESIGNAL Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html)

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