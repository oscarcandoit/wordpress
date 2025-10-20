---
url: https://dev.mysql.com/doc/refman/8.0/en/signal.html
scraped_at: 2025-10-20T03:07:54.936Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/signal.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/signal.html "Hide Sidebar")

[Previous: RESIGNAL Statement](https://dev.mysql.com/doc/refman/8.0/en/resignal.html "Previous: RESIGNAL Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Condition Handling](https://dev.mysql.com/doc/refman/8.0/en/condition-handling.html "Up: Condition Handling")[Next: Scope Rules for Handlers](https://dev.mysql.com/doc/refman/8.0/en/handler-scope.html "Next: Scope Rules for Handlers")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/signal.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/signal.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/signal.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/signal.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/signal.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/signal.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/signal.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/signal.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/signal.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/signal.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/signal.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/signal.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/signal.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/signal.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Compound Statement Syntax](https://dev.mysql.com/doc/refman/8.0/en/sql-compound-statements.html)  /
[Condition Handling](https://dev.mysql.com/doc/refman/8.0/en/condition-handling.html)  /

SIGNAL Statement


#### 15.6.7.5 SIGNAL Statement

``` sql

SIGNAL condition_value
    [SET signal_information_item\
    [, signal_information_item] ...]

condition_value: {
    SQLSTATE [VALUE] sqlstate_value
  | condition_name
}

signal_information_item:
    condition_information_item_name = simple_value_specification

condition_information_item_name: {
    CLASS_ORIGIN
  | SUBCLASS_ORIGIN
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

condition_name, simple_value_specification:
    (see following discussion)
```

[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") is the way to
“return” an error.
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") provides error information
to a handler, to an outer portion of the application, or to the
client. Also, it provides control over the error's
characteristics (error number, `SQLSTATE`
value, message). Without [`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement"),
it is necessary to resort to workarounds such as deliberately
referring to a nonexistent table to cause a routine to return an
error.


No privileges are required to execute the
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statement.


To retrieve information from the diagnostics area, use the
[`GET DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") statement (see
[Section 15.6.7.3, “GET DIAGNOSTICS Statement”](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement")). For information about the
diagnostics area, see [Section 15.6.7.7, “The MySQL Diagnostics Area”](https://dev.mysql.com/doc/refman/8.0/en/diagnostics-area.html "15.6.7.7 The MySQL Diagnostics Area").

- [SIGNAL Overview](https://dev.mysql.com/doc/refman/8.0/en/signal.html#signal-overview "SIGNAL Overview")

- [Signal Condition Information Items](https://dev.mysql.com/doc/refman/8.0/en/signal.html#signal-condition-information-items "Signal Condition Information Items")

- [Effect of Signals on Handlers, Cursors, and Statements](https://dev.mysql.com/doc/refman/8.0/en/signal.html#signal-effects "Effect of Signals on Handlers, Cursors, and Statements")


##### SIGNAL Overview

The _`condition_value`_ in a
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statement indicates the
error value to be returned. It can be an
`SQLSTATE` value (a 5-character string
literal) or a _`condition_name`_ that
refers to a named condition previously defined with
[`DECLARE ...\\
          CONDITION`](https://dev.mysql.com/doc/refman/8.0/en/declare-condition.html "15.6.7.1 DECLARE ... CONDITION Statement") (see [Section 15.6.7.1, “DECLARE ... CONDITION Statement”](https://dev.mysql.com/doc/refman/8.0/en/declare-condition.html "15.6.7.1 DECLARE ... CONDITION Statement")).


An `SQLSTATE` value can indicate errors,
warnings, or “not found.” The first two
characters of the value indicate its error class, as discussed
in [Signal Condition Information Items](https://dev.mysql.com/doc/refman/8.0/en/signal.html#signal-condition-information-items "Signal Condition Information Items"). Some
signal values cause statement termination; see
[Effect of Signals on Handlers, Cursors, and Statements](https://dev.mysql.com/doc/refman/8.0/en/signal.html#signal-effects "Effect of Signals on Handlers, Cursors, and Statements").


The `SQLSTATE` value for a
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statement should not
start with `'00'` because such values
indicate success and are not valid for signaling an error.
This is true whether the `SQLSTATE` value is
specified directly in the
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statement or in a named
condition referred to in the statement. If the value is
invalid, a `Bad SQLSTATE` error occurs.


To signal a generic `SQLSTATE` value, use
`'45000'`, which means “unhandled
user-defined exception.”

The [`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statement optionally
includes a `SET` clause that contains
multiple signal items, in a list of
_`condition_information_item_name`_ =
_`simple_value_specification`_
assignments, separated by commas.


Each
_`condition_information_item_name`_ may
be specified only once in the `SET` clause.
Otherwise, a `Duplicate condition information
          item` error occurs.


Valid _`simple_value_specification`_
designators can be specified using stored procedure or
function parameters, stored program local variables declared
with [`DECLARE`](https://dev.mysql.com/doc/refman/8.0/en/declare.html "15.6.3 DECLARE Statement"), user-defined
variables, system variables, or literals. A character literal
may include a _`_charset`_ introducer.


For information about permissible
_`condition_information_item_name`_
values, see
[Signal Condition Information Items](https://dev.mysql.com/doc/refman/8.0/en/signal.html#signal-condition-information-items "Signal Condition Information Items").


The following procedure signals an error or warning depending
on the value of `pval`, its input parameter:


``` sql

CREATE PROCEDURE p (pval INT)
BEGIN
  DECLARE specialty CONDITION FOR SQLSTATE '45000';
  IF pval = 0 THEN
    SIGNAL SQLSTATE '01000';
  ELSEIF pval = 1 THEN
    SIGNAL SQLSTATE '45000'
      SET MESSAGE_TEXT = 'An error occurred';
  ELSEIF pval = 2 THEN
    SIGNAL specialty
      SET MESSAGE_TEXT = 'An error occurred';
  ELSE
    SIGNAL SQLSTATE '01000'
      SET MESSAGE_TEXT = 'A warning occurred', MYSQL_ERRNO = 1000;
    SIGNAL SQLSTATE '45000'
      SET MESSAGE_TEXT = 'An error occurred', MYSQL_ERRNO = 1001;
  END IF;
END;
```

If `pval` is 0, `p()`
signals a warning because `SQLSTATE` values
that begin with `'01'` are signals in the
warning class. The warning does not terminate the procedure,
and can be seen with [`SHOW\\
          WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") after the procedure returns.


If `pval` is 1, `p()`
signals an error and sets the `MESSAGE_TEXT`
condition information item. The error terminates the
procedure, and the text is returned with the error
information.


If `pval` is 2, the same error is signaled,
although the `SQLSTATE` value is specified
using a named condition in this case.


If `pval` is anything else,
`p()` first signals a warning and sets the
message text and error number condition information items.
This warning does not terminate the procedure, so execution
continues and `p()` then signals an error.
The error does terminate the procedure. The message text and
error number set by the warning are replaced by the values set
by the error, which are returned with the error information.


[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") is typically used within
stored programs, but it is a MySQL extension that it is
permitted outside handler context. For example, if you invoke
the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client program, you can enter any
of these statements at the prompt:


``` sql

SIGNAL SQLSTATE '77777';

CREATE TRIGGER t_bi BEFORE INSERT ON t
  FOR EACH ROW SIGNAL SQLSTATE '77777';

CREATE EVENT e ON SCHEDULE EVERY 1 SECOND
  DO SIGNAL SQLSTATE '77777';
```

[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") executes according to
the following rules:


If the [`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statement
indicates a particular `SQLSTATE` value, that
value is used to signal the condition specified. Example:


``` sql

CREATE PROCEDURE p (divisor INT)
BEGIN
  IF divisor = 0 THEN
    SIGNAL SQLSTATE '22012';
  END IF;
END;
```

If the [`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statement uses a
named condition, the condition must be declared in some scope
that applies to the [`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement")
statement, and must be defined using an
`SQLSTATE` value, not a MySQL error number.
Example:


``` sql

CREATE PROCEDURE p (divisor INT)
BEGIN
  DECLARE divide_by_zero CONDITION FOR SQLSTATE '22012';
  IF divisor = 0 THEN
    SIGNAL divide_by_zero;
  END IF;
END;
```

If the named condition does not exist in the scope of the
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statement, an
`Undefined CONDITION` error occurs.


If [`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") refers to a named
condition that is defined with a MySQL error number rather
than an `SQLSTATE` value, a
`SIGNAL/RESIGNAL can only use a CONDITION defined with
          SQLSTATE` error occurs. The following statements
cause that error because the named condition is associated
with a MySQL error number:


``` sql

DECLARE no_such_table CONDITION FOR 1051;
SIGNAL no_such_table;
```

If a condition with a given name is declared multiple times in
different scopes, the declaration with the most local scope
applies. Consider the following procedure:


``` sql

CREATE PROCEDURE p (divisor INT)
BEGIN
  DECLARE my_error CONDITION FOR SQLSTATE '45000';
  IF divisor = 0 THEN
    BEGIN
      DECLARE my_error CONDITION FOR SQLSTATE '22012';
      SIGNAL my_error;
    END;
  END IF;
  SIGNAL my_error;
END;
```

If `divisor` is 0, the first
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statement executes. The
innermost `my_error` condition declaration
applies, raising `SQLSTATE` `'22012'`.


If `divisor` is not 0, the second
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statement executes. The
outermost `my_error` condition declaration
applies, raising `SQLSTATE` `'45000'`.


For information about how the server chooses handlers when a
condition occurs, see [Section 15.6.7.6, “Scope Rules for Handlers”](https://dev.mysql.com/doc/refman/8.0/en/handler-scope.html "15.6.7.6 Scope Rules for Handlers").


Signals can be raised within exception handlers:


``` sql

CREATE PROCEDURE p ()
BEGIN
  DECLARE EXIT HANDLER FOR SQLEXCEPTION
  BEGIN
    SIGNAL SQLSTATE VALUE '99999'
      SET MESSAGE_TEXT = 'An error occurred';
  END;
  DROP TABLE no_such_table;
END;
```

`CALL p()` reaches the
[`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") statement. There is
no table named `no_such_table`, so the error
handler is activated. The error handler destroys the original
error (“no such table”) and makes a new error
with `SQLSTATE` `'99999'`
and message `An error occurred`.

##### Signal Condition Information Items

The following table lists the names of diagnostics area
condition information items that can be set in a
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") (or
[`RESIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/resignal.html "15.6.7.4 RESIGNAL Statement")) statement. All items
are standard SQL except `MYSQL_ERRNO`, which
is a MySQL extension. For more information about these items
see [Section 15.6.7.7, “The MySQL Diagnostics Area”](https://dev.mysql.com/doc/refman/8.0/en/diagnostics-area.html "15.6.7.7 The MySQL Diagnostics Area").


``` none

Item Name             Definition
---------             ----------
CLASS_ORIGIN          VARCHAR(64)
SUBCLASS_ORIGIN       VARCHAR(64)
CONSTRAINT_CATALOG    VARCHAR(64)
CONSTRAINT_SCHEMA     VARCHAR(64)
CONSTRAINT_NAME       VARCHAR(64)
CATALOG_NAME          VARCHAR(64)
SCHEMA_NAME           VARCHAR(64)
TABLE_NAME            VARCHAR(64)
COLUMN_NAME           VARCHAR(64)
CURSOR_NAME           VARCHAR(64)
MESSAGE_TEXT          VARCHAR(128)
MYSQL_ERRNO           SMALLINT UNSIGNED
```

The character set for character items is UTF-8.


It is illegal to assign `NULL` to a condition
information item in a [`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement")
statement.


A [`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statement always
specifies an `SQLSTATE` value, either
directly, or indirectly by referring to a named condition
defined with an `SQLSTATE` value. The first
two characters of an `SQLSTATE` value are its
class, and the class determines the default value for the
condition information items:

- Class = `'00'` (success)



Illegal. `SQLSTATE` values that begin
with `'00'` indicate success and are not
valid for [`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement").


- Class = `'01'` (warning)




``` sql

MESSAGE_TEXT = 'Unhandled user-defined warning condition';
MYSQL_ERRNO = ER_SIGNAL_WARN
```

- Class = `'02'` (not found)




``` sql

MESSAGE_TEXT = 'Unhandled user-defined not found condition';
MYSQL_ERRNO = ER_SIGNAL_NOT_FOUND
```

- Class > `'02'` (exception)




``` sql

MESSAGE_TEXT = 'Unhandled user-defined exception condition';
MYSQL_ERRNO = ER_SIGNAL_EXCEPTION
```


For legal classes, the other condition information items are
set as follows:


``` sql

CLASS_ORIGIN = SUBCLASS_ORIGIN = '';
CONSTRAINT_CATALOG = CONSTRAINT_SCHEMA = CONSTRAINT_NAME = '';
CATALOG_NAME = SCHEMA_NAME = TABLE_NAME = COLUMN_NAME = '';
CURSOR_NAME = '';
```

The error values that are accessible after
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") executes are the
`SQLSTATE` value raised by the
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statement and the
`MESSAGE_TEXT` and
`MYSQL_ERRNO` items. These values are
available from the C API:

- [`mysql_sqlstate()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-sqlstate.html) returns
the `SQLSTATE` value.


- [`mysql_errno()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-errno.html) returns the
`MYSQL_ERRNO` value.


- [`mysql_error()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-error.html) returns the
`MESSAGE_TEXT` value.


At the SQL level, the output from [`SHOW\\
          WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") and [`SHOW\\
          ERRORS`](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html "15.7.7.17 SHOW ERRORS Statement") indicates the `MYSQL_ERRNO`
and `MESSAGE_TEXT` values in the
`Code` and `Message`
columns.


To retrieve information from the diagnostics area, use the
[`GET DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") statement (see
[Section 15.6.7.3, “GET DIAGNOSTICS Statement”](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement")). For information about the
diagnostics area, see [Section 15.6.7.7, “The MySQL Diagnostics Area”](https://dev.mysql.com/doc/refman/8.0/en/diagnostics-area.html "15.6.7.7 The MySQL Diagnostics Area").

##### Effect of Signals on Handlers, Cursors, and Statements

Signals have different effects on statement execution
depending on the signal class. The class determines how severe
an error is. MySQL ignores the value of the
[`sql_mode`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_sql_mode) system variable; in
particular, strict SQL mode does not matter. MySQL also
ignores `IGNORE`: The intent of
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") is to raise a
user-generated error explicitly, so a signal is never ignored.


In the following descriptions, “unhandled” means
that no handler for the signaled `SQLSTATE`
value has been defined with
[`DECLARE ...\\
          HANDLER`](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html "15.6.7.2 DECLARE ... HANDLER Statement").

- Class = `'00'` (success)



Illegal. `SQLSTATE` values that begin
with `'00'` indicate success and are not
valid for [`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement").


- Class = `'01'` (warning)



The value of the
[`warning_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_warning_count) system
variable goes up. [`SHOW\\
                WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") shows the signal.
`SQLWARNING` handlers catch the signal.



Warnings cannot be returned from stored functions because
the [`RETURN`](https://dev.mysql.com/doc/refman/8.0/en/return.html "15.6.5.7 RETURN Statement") statement that
causes the function to return clears the diagnostic area.
The statement thus clears any warnings that may have been
present there (and resets
[`warning_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_warning_count) to 0).


- Class = `'02'` (not found)


`NOT FOUND` handlers catch the signal.
There is no effect on cursors. If the signal is unhandled
in a stored function, statements end.


- Class > `'02'` (exception)


`SQLEXCEPTION` handlers catch the signal.
If the signal is unhandled in a stored function,
statements end.


- Class = `'40'`


Treated as an ordinary exception.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/resignal.html "Previous: RESIGNAL Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/condition-handling.html "Up: Condition Handling") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/handler-scope.html "Next: Scope Rules for Handlers")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/signal.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/signal.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/signal.html)

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