---
url: https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html
scraped_at: 2025-10-20T03:08:13.172Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html "Hide Sidebar")

[Previous: DECLARE ... CONDITION Statement](https://dev.mysql.com/doc/refman/8.0/en/declare-condition.html "Previous: DECLARE ... CONDITION Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Condition Handling](https://dev.mysql.com/doc/refman/8.0/en/condition-handling.html "Up: Condition Handling")[Next: GET DIAGNOSTICS Statement](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "Next: GET DIAGNOSTICS Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/declare-handler.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/declare-handler.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/declare-handler.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/declare-handler.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/declare-handler.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/declare-handler.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/declare-handler.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/declare-handler.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Compound Statement Syntax](https://dev.mysql.com/doc/refman/8.0/en/sql-compound-statements.html)  /
[Condition Handling](https://dev.mysql.com/doc/refman/8.0/en/condition-handling.html)  /

DECLARE ... HANDLER Statement


#### 15.6.7.2 DECLARE ... HANDLER Statement

``` sql

DECLARE handler_action HANDLER
    FOR condition_value [, condition_value] ...
    statement

handler_action: {
    CONTINUE
  | EXIT
  | UNDO
}

condition_value: {
    mysql_error_code
  | SQLSTATE [VALUE] sqlstate_value
  | condition_name
  | SQLWARNING
  | NOT FOUND
  | SQLEXCEPTION
}
```

The [`DECLARE ...\\
        HANDLER`](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html "15.6.7.2 DECLARE ... HANDLER Statement") statement specifies a handler that deals with
one or more conditions. If one of these conditions occurs, the
specified _`statement`_ executes.
_`statement`_ can be a simple statement
such as `SET var_name =
        value`, or a compound
statement written using `BEGIN` and
`END` (see [Section 15.6.1, “BEGIN ... END Compound Statement”](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement")).


Handler declarations must appear after variable or condition
declarations.


The _`handler_action`_ value indicates
what action the handler takes after execution of the handler
statement:

- `CONTINUE`: Execution of the current
program continues.


- `EXIT`: Execution terminates for the
[`BEGIN ...\\
              END`](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement") compound statement in which the handler is
declared. This is true even if the condition occurs in an
inner block.


- `UNDO`: Not supported.


The _`condition_value`_ for
[`DECLARE ...\\
        HANDLER`](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html "15.6.7.2 DECLARE ... HANDLER Statement") indicates the specific condition or class of
conditions that activates the handler. It can take the following
forms:

- _`mysql_error_code`_: An integer
literal indicating a MySQL error code, such as 1051 to
specify “unknown table”:




``` sql

DECLARE CONTINUE HANDLER FOR 1051
    BEGIN
      -- body of handler
    END;
```




Do not use MySQL error code 0 because that indicates success
rather than an error condition. For a list of MySQL error
codes, see [Server Error Message Reference](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html).


- SQLSTATE \[VALUE\] _`sqlstate_value`_:
A 5-character string literal indicating an SQLSTATE value,
such as `'42S01'` to specify “unknown
table”:




``` sql

DECLARE CONTINUE HANDLER FOR SQLSTATE '42S02'
    BEGIN
      -- body of handler
    END;
```




Do not use SQLSTATE values that begin with
`'00'` because those indicate success
rather than an error condition. For a list of SQLSTATE
values, see [Server Error Message Reference](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html).


- _`condition_name`_: A condition name
previously specified with
[`DECLARE\\
              ... CONDITION`](https://dev.mysql.com/doc/refman/8.0/en/declare-condition.html "15.6.7.1 DECLARE ... CONDITION Statement"). A condition name can be associated
with a MySQL error code or SQLSTATE value. See
[Section 15.6.7.1, “DECLARE ... CONDITION Statement”](https://dev.mysql.com/doc/refman/8.0/en/declare-condition.html "15.6.7.1 DECLARE ... CONDITION Statement").


- `SQLWARNING`: Shorthand for the class of
SQLSTATE values that begin with `'01'`.




``` sql

DECLARE CONTINUE HANDLER FOR SQLWARNING
    BEGIN
      -- body of handler
    END;
```

- `NOT FOUND`: Shorthand for the class of
SQLSTATE values that begin with `'02'`.
This is relevant within the context of cursors and is used
to control what happens when a cursor reaches the end of a
data set. If no more rows are available, a No Data condition
occurs with SQLSTATE value `'02000'`. To
detect this condition, you can set up a handler for it or
for a `NOT FOUND` condition.




``` sql

DECLARE CONTINUE HANDLER FOR NOT FOUND
    BEGIN
      -- body of handler
    END;
```




For another example, see [Section 15.6.6, “Cursors”](https://dev.mysql.com/doc/refman/8.0/en/cursors.html "15.6.6 Cursors"). The
`NOT FOUND` condition also occurs for
`SELECT ... INTO
              var_list` statements
that retrieve no rows.


- `SQLEXCEPTION`: Shorthand for the class of
SQLSTATE values that do not begin with
`'00'`, `'01'`, or
`'02'`.




``` sql

DECLARE CONTINUE HANDLER FOR SQLEXCEPTION
    BEGIN
      -- body of handler
    END;
```


For information about how the server chooses handlers when a
condition occurs, see [Section 15.6.7.6, “Scope Rules for Handlers”](https://dev.mysql.com/doc/refman/8.0/en/handler-scope.html "15.6.7.6 Scope Rules for Handlers").


If a condition occurs for which no handler has been declared,
the action taken depends on the condition class:

- For `SQLEXCEPTION` conditions, the stored
program terminates at the statement that raised the
condition, as if there were an `EXIT`
handler. If the program was called by another stored
program, the calling program handles the condition using the
handler selection rules applied to its own handlers.


- For `SQLWARNING` conditions, the program
continues executing, as if there were a
`CONTINUE` handler.


- For `NOT FOUND` conditions, if the
condition was raised normally, the action is
`CONTINUE`. If it was raised by
[`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") or
[`RESIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/resignal.html "15.6.7.4 RESIGNAL Statement"), the action is
`EXIT`.


The following example uses a handler for `SQLSTATE
        '23000'`, which occurs for a duplicate-key error:


``` sql

mysql> CREATE TABLE test.t (s1 INT, PRIMARY KEY (s1));
Query OK, 0 rows affected (0.00 sec)

mysql> delimiter //

mysql> CREATE PROCEDURE handlerdemo ()
       BEGIN
         DECLARE CONTINUE HANDLER FOR SQLSTATE '23000' SET @x2 = 1;
         SET @x = 1;
         INSERT INTO test.t VALUES (1);
         SET @x = 2;
         INSERT INTO test.t VALUES (1);
         SET @x = 3;
       END;
       //
Query OK, 0 rows affected (0.00 sec)

mysql> CALL handlerdemo()//
Query OK, 0 rows affected (0.00 sec)

mysql> SELECT @x//
    +------+
    | @x   |
    +------+
    | 3    |
    +------+
    1 row in set (0.00 sec)
```

Notice that `@x` is `3` after
the procedure executes, which shows that execution continued to
the end of the procedure after the error occurred. If the
[`DECLARE ...\\
        HANDLER`](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html "15.6.7.2 DECLARE ... HANDLER Statement") statement had not been present, MySQL would
have taken the default action ( `EXIT`) after
the second [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") failed due to
the `PRIMARY KEY` constraint, and
`SELECT @x` would have returned
`2`.


To ignore a condition, declare a `CONTINUE`
handler for it and associate it with an empty block. For
example:


``` sql

DECLARE CONTINUE HANDLER FOR SQLWARNING BEGIN END;
```

The scope of a block label does not include the code for
handlers declared within the block. Therefore, the statement
associated with a handler cannot use
[`ITERATE`](https://dev.mysql.com/doc/refman/8.0/en/iterate.html "15.6.5.3 ITERATE Statement") or
[`LEAVE`](https://dev.mysql.com/doc/refman/8.0/en/leave.html "15.6.5.4 LEAVE Statement") to refer to labels for
blocks that enclose the handler declaration. Consider the
following example, where the
[`REPEAT`](https://dev.mysql.com/doc/refman/8.0/en/repeat.html "15.6.5.6 REPEAT Statement") block has a label of
`retry`:


``` sql

CREATE PROCEDURE p ()
BEGIN
  DECLARE i INT DEFAULT 3;
  retry:
    REPEAT
      BEGIN
        DECLARE CONTINUE HANDLER FOR SQLWARNING
          BEGIN
            ITERATE retry;    # illegal
          END;
        IF i < 0 THEN
          LEAVE retry;        # legal
        END IF;
        SET i = i - 1;
      END;
    UNTIL FALSE END REPEAT;
END;
```

The `retry` label is in scope for the
[`IF`](https://dev.mysql.com/doc/refman/8.0/en/if.html "15.6.5.2 IF Statement") statement within the block. It
is not in scope for the `CONTINUE` handler, so
the reference there is invalid and results in an error:


``` none

ERROR 1308 (42000): LEAVE with no matching label: retry
```

To avoid references to outer labels in handlers, use one of
these strategies:

- To leave the block, use an `EXIT` handler.
If no block cleanup is required, the
[`BEGIN ...\\
              END`](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement") handler body can be empty:




``` sql

DECLARE EXIT HANDLER FOR SQLWARNING BEGIN END;
```




Otherwise, put the cleanup statements in the handler body:




``` sql

DECLARE EXIT HANDLER FOR SQLWARNING
    BEGIN
      block cleanup statements
    END;
```

- To continue execution, set a status variable in a
`CONTINUE` handler that can be checked in
the enclosing block to determine whether the handler was
invoked. The following example uses the variable
`done` for this purpose:




``` sql

CREATE PROCEDURE p ()
BEGIN
    DECLARE i INT DEFAULT 3;
    DECLARE done INT DEFAULT FALSE;
    retry:
      REPEAT
        BEGIN
          DECLARE CONTINUE HANDLER FOR SQLWARNING
            BEGIN
              SET done = TRUE;
            END;
          IF done OR i < 0 THEN
            LEAVE retry;
          END IF;
          SET i = i - 1;
        END;
      UNTIL FALSE END REPEAT;
END;
```


[PREV](https://dev.mysql.com/doc/refman/8.0/en/declare-condition.html "Previous: DECLARE ... CONDITION Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/condition-handling.html "Up: Condition Handling") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "Next: GET DIAGNOSTICS Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/declare-handler.html)

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