---
url: https://dev.mysql.com/doc/refman/8.0/en/set-variable.html
scraped_at: 2025-10-20T03:08:56.026Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "Hide Sidebar")

[Previous: SET Statements](https://dev.mysql.com/doc/refman/8.0/en/set-statement.html "Previous: SET Statements")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SET Statements](https://dev.mysql.com/doc/refman/8.0/en/set-statement.html "Up: SET Statements")[Next: SET CHARACTER SET Statement](https://dev.mysql.com/doc/refman/8.0/en/set-character-set.html "Next: SET CHARACTER SET Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/set-variable.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/set-variable.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/set-variable.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/set-variable.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/set-variable.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/set-variable.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/set-variable.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/set-variable.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SET Statements](https://dev.mysql.com/doc/refman/8.0/en/set-statement.html)  /

SET Syntax for Variable Assignment


#### 15.7.6.1 SET Syntax for Variable Assignment

``` sql

SET variable = expr [, variable = expr] ...

variable: {
    user_var_name
  | param_name
  | local_var_name
  | {GLOBAL | @@GLOBAL.} system_var_name
  | {PERSIST | @@PERSIST.} system_var_name
  | {PERSIST_ONLY | @@PERSIST_ONLY.} system_var_name
  | [SESSION | @@SESSION. | @@] system_var_name
}
```

[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
syntax for variable assignment enables you to assign values to
different types of variables that affect the operation of the
server or clients:

- User-defined variables. See
[Section 11.4, “User-Defined Variables”](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html "11.4 User-Defined Variables").


- Stored procedure and function parameters, and stored program
local variables. See
[Section 15.6.4, “Variables in Stored Programs”](https://dev.mysql.com/doc/refman/8.0/en/stored-program-variables.html "15.6.4 Variables in Stored Programs").


- System variables. See
[Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables"). System variables
also can be set at server startup, as described in
[Section 7.1.9, “Using System Variables”](https://dev.mysql.com/doc/refman/8.0/en/using-system-variables.html "7.1.9 Using System Variables").


A [`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statement that assigns variable values is not written to the
binary log, so in replication scenarios it affects only the host
on which you execute it. To affect all replication hosts,
execute the statement on each host.


The following sections describe
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
syntax for setting variables. They use the
[`=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-equal)
assignment operator, but the
[`:=`](https://dev.mysql.com/doc/refman/8.0/en/assignment-operators.html#operator_assign-value)
assignment operator is also permitted for this purpose.

- [User-Defined Variable Assignment](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html#set-variable-user-variables "User-Defined Variable Assignment")

- [Parameter and Local Variable Assignment](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html#set-variable-parameters-local-variables "Parameter and Local Variable Assignment")

- [System Variable Assignment](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html#set-variable-system-variables "System Variable Assignment")

- [SET Error Handling](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html#set-variable-error-handling "SET Error Handling")

- [Multiple Variable Assignment](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html#set-variable-multiple-assignments "Multiple Variable Assignment")

- [System Variable References in Expressions](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html#variable-references-in-expressions "System Variable References in Expressions")


##### User-Defined Variable Assignment

User-defined variables are created locally within a session
and exist only within the context of that session; see
[Section 11.4, “User-Defined Variables”](https://dev.mysql.com/doc/refman/8.0/en/user-variables.html "11.4 User-Defined Variables").


A user-defined variable is written as
`@var_name` and is
assigned an expression value as follows:


``` sql

SET @var_name = expr;
```

Examples:


``` sql

SET @name = 43;
SET @total_tax = (SELECT SUM(tax) FROM taxable_transactions);
```

As demonstrated by those statements,
_`expr`_ can range from simple (a
literal value) to more complex (the value returned by a scalar
subquery).


The Performance Schema
[`user_variables_by_thread`](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-user-variable-tables.html "29.12.10 Performance Schema User-Defined Variable Tables") table
contains information about user-defined variables. See
[Section 29.12.10, “Performance Schema User-Defined Variable Tables”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-user-variable-tables.html "29.12.10 Performance Schema User-Defined Variable Tables").

##### Parameter and Local Variable Assignment

[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
applies to parameters and local variables in the context of
the stored object within which they are defined. The following
procedure uses the `increment` procedure
parameter and `counter` local variable:


``` sql

CREATE PROCEDURE p(increment INT)
BEGIN
  DECLARE counter INT DEFAULT 0;
  WHILE counter < 10 DO
    -- ... do work ...
    SET counter = counter + increment;
  END WHILE;
END;
```

##### System Variable Assignment

The MySQL server maintains system variables that configure its
operation. A system variable can have a global value that
affects server operation as a whole, a session value that
affects the current session, or both. Many system variables
are dynamic and can be changed at runtime using the
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statement to affect operation of the current server instance.
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
can also be used to persist certain system variables to the
`mysqld-auto.cnf` file in the data
directory, to affect server operation for subsequent startups.


If a `SET` statement is issued for a
sensitive system variable, the query is rewritten to replace
the value with “`<redacted>`”
before it is logged to the general log and audit log. This
takes place even if secure storage through a keyring component
is not available on the server instance.


If you change a session system variable, the value remains in
effect within your session until you change the variable to a
different value or the session ends. The change has no effect
on other sessions.


If you change a global system variable, the value is
remembered and used to initialize the session value for new
sessions until you change the variable to a different value or
the server exits. The change is visible to any client that
accesses the global value. However, the change affects the
corresponding session value only for clients that connect
after the change. The global variable change does not affect
the session value for any current client sessions (not even
the session within which the global value change occurs).


To make a global system variable setting permanent so that it
applies across server restarts, you can persist it to the
`mysqld-auto.cnf` file in the data
directory. It is also possible to make persistent
configuration changes by manually modifying a
`my.cnf` option file, but that is more
cumbersome, and an error in a manually entered setting might
not be discovered until much later.
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statements that persist system variables are more convenient
and avoid the possibility of malformed settings because
settings with syntax errors do not succeed and do not change
server configuration. For more information about persisting
system variables and the `mysqld-auto.cnf`
file, see [Section 7.1.9.3, “Persisted System Variables”](https://dev.mysql.com/doc/refman/8.0/en/persisted-system-variables.html "7.1.9.3 Persisted System Variables").

Note

Setting or persisting a global system variable value always
requires special privileges. Setting a session system
variable value normally requires no special privileges and
can be done by any user, although there are exceptions. For
more information, see
[Section 7.1.9.1, “System Variable Privileges”](https://dev.mysql.com/doc/refman/8.0/en/system-variable-privileges.html "7.1.9.1 System Variable Privileges").

The following discussion describes the syntax options for
setting and persisting system variables:

- To assign a value to a global system variable, precede the
variable name by the `GLOBAL` keyword or
the `@@GLOBAL.` qualifier:




``` sql

SET GLOBAL max_connections = 1000;
SET @@GLOBAL.max_connections = 1000;
```

- To assign a value to a session system variable, precede
the variable name by the `SESSION` or
`LOCAL` keyword, by the
`@@SESSION.`,
`@@LOCAL.`, or `@@`
qualifier, or by no keyword or no modifier at all:




``` sql

SET SESSION sql_mode = 'TRADITIONAL';
SET LOCAL sql_mode = 'TRADITIONAL';
SET @@SESSION.sql_mode = 'TRADITIONAL';
SET @@LOCAL.sql_mode = 'TRADITIONAL';
SET @@sql_mode = 'TRADITIONAL';
SET sql_mode = 'TRADITIONAL';
```




A client can change its own session variables, but not
those of any other client.


- To persist a global system variable to the
`mysqld-auto.cnf` option file in the
data directory, precede the variable name by the
`PERSIST` keyword or the
`@@PERSIST.` qualifier:




``` sql

SET PERSIST max_connections = 1000;
SET @@PERSIST.max_connections = 1000;
```




This
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
syntax enables you to make configuration changes at
runtime that also persist across server restarts. Like
[`SET\\
                GLOBAL`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment"),
[`SET\\
                PERSIST`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment") sets the global variable runtime value,
but also writes the variable setting to the
`mysqld-auto.cnf` file (replacing any
existing variable setting if there is one).


- To persist a global system variable to the
`mysqld-auto.cnf` file without setting
the global variable runtime value, precede the variable
name by the `PERSIST_ONLY` keyword or the
`@@PERSIST_ONLY.` qualifier:




``` sql

SET PERSIST_ONLY back_log = 100;
SET @@PERSIST_ONLY.back_log = 100;
```




Like `PERSIST`,
`PERSIST_ONLY` writes the variable
setting to `mysqld-auto.cnf`. However,
unlike `PERSIST`,
`PERSIST_ONLY` does not modify the global
variable runtime value. This makes
`PERSIST_ONLY` suitable for configuring
read-only system variables that can be set only at server
startup.


To set a global system variable value to the compiled-in MySQL
default value or a session system variable to the current
corresponding global value, set the variable to the value
`DEFAULT`. For example, the following two
statements are identical in setting the session value of
[`max_join_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_join_size) to the current
global value:


``` sql

SET @@SESSION.max_join_size = DEFAULT;
SET @@SESSION.max_join_size = @@GLOBAL.max_join_size;
```

Using
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment") to
persist a global system variable to a value of
`DEFAULT` or to its literal default value
assigns the variable its default value and adds a setting for
the variable to `mysqld-auto.cnf`. To
remove the variable from the file, use
[`RESET PERSIST`](https://dev.mysql.com/doc/refman/8.0/en/reset-persist.html "15.7.8.7 RESET PERSIST Statement").


Some system variables cannot be persisted or are
persist-restricted. See
[Section 7.1.9.4, “Nonpersistible and Persist-Restricted System Variables”](https://dev.mysql.com/doc/refman/8.0/en/nonpersistible-system-variables.html "7.1.9.4 Nonpersistible and Persist-Restricted System Variables").


A system variable implemented by a plugin can be persisted if
the plugin is installed when the
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statement is executed. Assignment of the persisted plugin
variable takes effect for subsequent server restarts if the
plugin is still installed. If the plugin is no longer
installed, the plugin variable no longer exists when the
server reads the `mysqld-auto.cnf` file. In
this case, the server writes a warning to the error log and
continues:


``` simple

currently unknown variable 'var_name'
was read from the persisted config file
```

To display system variable names and values:

- Use the [`SHOW VARIABLES`](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html "15.7.7.41 SHOW VARIABLES Statement")
statement; see [Section 15.7.7.41, “SHOW VARIABLES Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html "15.7.7.41 SHOW VARIABLES Statement").


- Several Performance Schema tables provide system variable
information. See
[Section 29.12.14, “Performance Schema System Variable Tables”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-system-variable-tables.html "29.12.14 Performance Schema System Variable Tables").


- The Performance Schema
[`variables_info`](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-variables-info-table.html "29.12.14.2 Performance Schema variables_info Table") table contains
information showing when and by which user each system
variable was most recently set. See
[Section 29.12.14.2, “Performance Schema variables\_info Table”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-variables-info-table.html "29.12.14.2 Performance Schema variables_info Table").


- The Performance Schema
[`persisted_variables`](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-persisted-variables-table.html "29.12.14.1 Performance Schema persisted_variables Table") table
provides an SQL interface to the
`mysqld-auto.cnf` file, enabling its
contents to be inspected at runtime using
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements. See
[Section 29.12.14.1, “Performance Schema persisted\_variables Table”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-persisted-variables-table.html "29.12.14.1 Performance Schema persisted_variables Table").


##### SET Error Handling

If any variable assignment in a
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statement fails, the entire statement fails and no variables
are changed, nor is the `mysqld-auto.cnf`
file changed.


[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
produces an error under the circumstances described here. Most
of the examples show
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statements that use keyword syntax (for example,
`GLOBAL` or `SESSION`), but
the principles are also true for statements that use the
corresponding modifiers (for example,
`@@GLOBAL.` or
`@@SESSION.`).

- Use of
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
(any variant) to set a read-only variable:




``` sql

mysql> SET GLOBAL version = 'abc';
ERROR 1238 (HY000): Variable 'version' is a read only variable
```

- Use of `GLOBAL`,
`PERSIST`, or
`PERSIST_ONLY` to set a variable that has
only a session value:




``` sql

mysql> SET GLOBAL sql_log_bin = ON;
ERROR 1228 (HY000): Variable 'sql_log_bin' is a SESSION
variable and can't be used with SET GLOBAL
```

- Use of `SESSION` to set a variable that
has only a global value:




``` sql

mysql> SET SESSION max_connections = 1000;
ERROR 1229 (HY000): Variable 'max_connections' is a
GLOBAL variable and should be set with SET GLOBAL
```

- Omission of `GLOBAL`,
`PERSIST`, or
`PERSIST_ONLY` to set a variable that has
only a global value:




``` sql

mysql> SET max_connections = 1000;
ERROR 1229 (HY000): Variable 'max_connections' is a
GLOBAL variable and should be set with SET GLOBAL
```

- Use of `PERSIST` or
`PERSIST_ONLY` to set a variable that
cannot be persisted:




``` sql

mysql> SET PERSIST port = 3307;
ERROR 1238 (HY000): Variable 'port' is a read only variable
mysql> SET PERSIST_ONLY port = 3307;
ERROR 1238 (HY000): Variable 'port' is a non persistent read only variable
```

- The `@@GLOBAL.`,
`@@PERSIST.`,
`@@PERSIST_ONLY.`,
`@@SESSION.`, and `@@`
modifiers apply only to system variables. An error occurs
for attempts to apply them to user-defined variables,
stored procedure or function parameters, or stored program
local variables.


- Not all system variables can be set to
`DEFAULT`. In such cases, assigning
`DEFAULT` results in an error.


- An error occurs for attempts to assign
`DEFAULT` to user-defined variables,
stored procedure or function parameters, or stored program
local variables.


##### Multiple Variable Assignment

A [`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statement can contain multiple variable assignments, separated
by commas. This statement assigns values to a user-defined
variable and a system variable:


``` sql

SET @x = 1, SESSION sql_mode = '';
```

If you set multiple system variables in a single statement,
the most recent `GLOBAL`,
`PERSIST`, `PERSIST_ONLY`,
or `SESSION` keyword in the statement is used
for following assignments that have no keyword specified.


Examples of multiple-variable assignment:


``` sql

SET GLOBAL sort_buffer_size = 1000000, SESSION sort_buffer_size = 1000000;
SET @@GLOBAL.sort_buffer_size = 1000000, @@LOCAL.sort_buffer_size = 1000000;
SET GLOBAL max_connections = 1000, sort_buffer_size = 1000000;
```

The `@@GLOBAL.`,
`@@PERSIST.`,
`@@PERSIST_ONLY.`,
`@@SESSION.`, and `@@`
modifiers apply only to the immediately following system
variable, not any remaining system variables. This statement
sets the [`sort_buffer_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_sort_buffer_size)
global value to 50000 and the session value to 1000000:


``` sql

SET @@GLOBAL.sort_buffer_size = 50000, sort_buffer_size = 1000000;
```

##### System Variable References in Expressions

To refer to the value of a system variable in expressions, use
one of the `@@`-modifiers (except
`@@PERSIST.` and
`@@PERSIST_ONLY.`, which are not permitted in
expressions). For example, you can retrieve system variable
values in a [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement
like this:


``` sql

SELECT @@GLOBAL.sql_mode, @@SESSION.sql_mode, @@sql_mode;
```

Note

A reference to a system variable in an expression as
`@@var_name`
(with `@@` rather than
`@@GLOBAL.` or
`@@SESSION.`) returns the session value if
it exists and the global value otherwise. This differs from
`SET @@var_name =
            expr`, which always
refers to the session value.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/set-statement.html "Previous: SET Statements") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/set-statement.html "Up: SET Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/set-character-set.html "Next: SET CHARACTER SET Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html)

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