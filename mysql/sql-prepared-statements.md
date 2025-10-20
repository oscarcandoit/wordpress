---
url: https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html
scraped_at: 2025-10-20T03:10:03.646Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html "Hide Sidebar")

[Previous: STOP GROUP_REPLICATION Statement](https://dev.mysql.com/doc/refman/8.0/en/stop-group-replication.html "Previous: STOP GROUP_REPLICATION Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html "Up: SQL Statements")[Next: PREPARE Statement](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "Next: PREPARE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/sql-prepared-statements.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/sql-prepared-statements.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/sql-prepared-statements.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/sql-prepared-statements.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/sql-prepared-statements.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/sql-prepared-statements.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/sql-prepared-statements.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/sql-prepared-statements.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
Prepared Statements


## 15.5 Prepared Statements

[15.5.1 PREPARE Statement](https://dev.mysql.com/doc/refman/8.0/en/prepare.html)[15.5.2 EXECUTE Statement](https://dev.mysql.com/doc/refman/8.0/en/execute.html)[15.5.3 DEALLOCATE PREPARE Statement](https://dev.mysql.com/doc/refman/8.0/en/deallocate-prepare.html)

MySQL 8.0 provides support for server-side prepared
statements. This support takes advantage of the efficient
client/server binary protocol. Using prepared statements with
placeholders for parameter values has the following benefits:

- Less overhead for parsing the statement each time it is
executed. Typically, database applications process large volumes
of almost-identical statements, with only changes to literal or
variable values in clauses such as `WHERE` for
queries and deletes, `SET` for updates, and
`VALUES` for inserts.


- Protection against SQL injection attacks. The parameter values
can contain unescaped SQL quote and delimiter characters.


The following sections provide an overview of the characteristics of
prepared statements:

- [Prepared Statements in Application Programs](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html#prepared-statements-in-applications "Prepared Statements in Application Programs")

- [Prepared Statements in SQL Scripts](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html#prepared-statements-in-scripts "Prepared Statements in SQL Scripts")

- [PREPARE, EXECUTE, and DEALLOCATE PREPARE Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html#prepared-statement-types "PREPARE, EXECUTE, and DEALLOCATE PREPARE Statements")

- [SQL Syntax Permitted in Prepared Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html#prepared-statements-permitted "SQL Syntax Permitted in Prepared Statements")


### Prepared Statements in Application Programs

You can use server-side prepared statements through client
programming interfaces, including the [MySQL C\\
API client library](https://dev.mysql.com/doc/c-api/8.0/en/) for C programs,
[MySQL Connector/J](https://dev.mysql.com/doc/connector-j/en/) for Java
programs, and [MySQL Connector/NET](https://dev.mysql.com/doc/connector-net/en/) for
programs using .NET technologies. For example, the C API provides a
set of function calls that make up its prepared statement API. See
[C API Prepared Statement Interface](https://dev.mysql.com/doc/c-api/8.0/en/c-api-prepared-statement-interface.html). Other language
interfaces can provide support for prepared statements that use the
binary protocol by linking in the C client library, one example
being the
[`mysqli`\\
extension](http://php.net/mysqli), available in PHP 5.0 and higher.

### Prepared Statements in SQL Scripts

An alternative SQL interface to prepared statements is available.
This interface is not as efficient as using the binary protocol
through a prepared statement API, but requires no programming
because it is available directly at the SQL level:

- You can use it when no programming interface is available to
you.


- You can use it from any program that can send SQL statements to
the server to be executed, such as the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client")
client program.


- You can use it even if the client is using an old version of the
client library.


SQL syntax for prepared statements is intended to be used for
situations such as these:

- To test how prepared statements work in your application before
coding it.


- To use prepared statements when you do not have access to a
programming API that supports them.


- To interactively troubleshoot application issues with prepared
statements.


- To create a test case that reproduces a problem with prepared
statements, so that you can file a bug report.


### PREPARE, EXECUTE, and DEALLOCATE PREPARE Statements

SQL syntax for prepared statements is based on three SQL statements:

- [`PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "15.5.1 PREPARE Statement") prepares a statement for
execution (see [Section 15.5.1, “PREPARE Statement”](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "15.5.1 PREPARE Statement")).


- [`EXECUTE`](https://dev.mysql.com/doc/refman/8.0/en/execute.html "15.5.2 EXECUTE Statement") executes a prepared
statement (see [Section 15.5.2, “EXECUTE Statement”](https://dev.mysql.com/doc/refman/8.0/en/execute.html "15.5.2 EXECUTE Statement")).


- [`DEALLOCATE PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/deallocate-prepare.html "15.5.3 DEALLOCATE PREPARE Statement") releases a
prepared statement (see [Section 15.5.3, “DEALLOCATE PREPARE Statement”](https://dev.mysql.com/doc/refman/8.0/en/deallocate-prepare.html "15.5.3 DEALLOCATE PREPARE Statement")).


The following examples show two equivalent ways of preparing a
statement that computes the hypotenuse of a triangle given the
lengths of the two sides.


The first example shows how to create a prepared statement by using
a string literal to supply the text of the statement:


``` sql

mysql> PREPARE stmt1 FROM 'SELECT SQRT(POW(?,2) + POW(?,2)) AS hypotenuse';
mysql> SET @a = 3;
mysql> SET @b = 4;
mysql> EXECUTE stmt1 USING @a, @b;
+------------+
| hypotenuse |
+------------+
|          5 |
+------------+
mysql> DEALLOCATE PREPARE stmt1;
```

The second example is similar, but supplies the text of the
statement as a user variable:


``` sql

mysql> SET @s = 'SELECT SQRT(POW(?,2) + POW(?,2)) AS hypotenuse';
mysql> PREPARE stmt2 FROM @s;
mysql> SET @a = 6;
mysql> SET @b = 8;
mysql> EXECUTE stmt2 USING @a, @b;
+------------+
| hypotenuse |
+------------+
|         10 |
+------------+
mysql> DEALLOCATE PREPARE stmt2;
```

Here is an additional example that demonstrates how to choose the
table on which to perform a query at runtime, by storing the name of
the table as a user variable:


``` sql

mysql> USE test;
mysql> CREATE TABLE t1 (a INT NOT NULL);
mysql> INSERT INTO t1 VALUES (4), (8), (11), (32), (80);

mysql> SET @table = 't1';
mysql> SET @s = CONCAT('SELECT * FROM ', @table);

mysql> PREPARE stmt3 FROM @s;
mysql> EXECUTE stmt3;
+----+
| a  |
+----+
|  4 |
|  8 |
| 11 |
| 32 |
| 80 |
+----+

mysql> DEALLOCATE PREPARE stmt3;
```

A prepared statement is specific to the session in which it was
created. If you terminate a session without deallocating a
previously prepared statement, the server deallocates it
automatically.


A prepared statement is also global to the session. If you create a
prepared statement within a stored routine, it is not deallocated
when the stored routine ends.


To guard against too many prepared statements being created
simultaneously, set the
[`max_prepared_stmt_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_prepared_stmt_count) system
variable. To prevent the use of prepared statements, set the value
to 0.

### SQL Syntax Permitted in Prepared Statements

The following SQL statements can be used as prepared statements:


``` sql

ALTER TABLE
ALTER USER {DEFAULT ROLE}
ANALYZE TABLE
CACHE INDEX
CALL
CHANGE {MASTER | REPLICATION FILTER}
CHECKSUM
COMMIT
{CREATE | DROP} INDEX
{CREATE | RENAME | DROP} DATABASE
{CREATE | DROP} TABLE
{CREATE | RENAME | DROP} USER
{CREATE | DROP} VIEW
DELETE
DO
FLUSH
GRANT {ROLE}
INSERT
INSERT ... SELECT
INSTALL PLUGIN
KILL
LOAD INDEX INTO CACHE
OPTIMIZE TABLE
RENAME TABLE
REPAIR TABLE
REPLACE
RESET {MASTER | REPLICA}
REVOKE {ALL | ROLE}
SELECT
SET {PASSWORD | RESOURCE GROUP | ROLE | VARIABLE}
SHOW {BINLOG EVENTS | BINARY LOGS | CHARACTER SETS | COLLATIONS | DATABASES | ENGINE |
      ERRORS | EVENTS | FIELDS | FUNCTION CODE | FUNCTION STATUS | GRANTS | KEYS | OPEN TABLES |
      PLUGINS | PRIVILEGES | PROCEDURE CODE | PROCEDURE STATUS | PROCESSLIST | PROFILE | PROFILES |
      RELAYLOG EVENTS | REPLICAS | REPLICA STATUS | STATUS | PROCEDURE STATUS | TABLE STATUS | TABLES |
      TRIGGERS | VARIABLES | WARNINGS}
SHOW CREATE { DATABASE | EVENT | FUNCTION | PROCEDURE | TABLE | TRIGGER | USER | VIEW}
REPLICA {START | STOP}
TRUNCATE
UNINSTALL PLUGIN
UPDATE
```

Other statements are not supported.


For compliance with the SQL standard, which states that diagnostics
statements are not preparable, MySQL does not support the following
as prepared statements:

- `SHOW WARNINGS`, `SHOW COUNT(*)
          WARNINGS`

- `SHOW ERRORS`, `SHOW COUNT(*)
          ERRORS`

- Statements containing any reference to the
[`warning_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_warning_count) or
[`error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_error_count) system variable.


Generally, statements not permitted in SQL prepared statements are
also not permitted in stored programs. Exceptions are noted in
[Section 27.8, “Restrictions on Stored Programs”](https://dev.mysql.com/doc/refman/8.0/en/stored-program-restrictions.html "27.8 Restrictions on Stored Programs").


Metadata changes to tables or views referred to by prepared
statements are detected and cause automatic repreparation of the
statement when it is next executed. For more information, see
[Section 10.10.3, “Caching of Prepared Statements and Stored Programs”](https://dev.mysql.com/doc/refman/8.0/en/statement-caching.html "10.10.3 Caching of Prepared Statements and Stored Programs").


Placeholders can be used for the arguments of the
`LIMIT` clause when using prepared statements. See
[Section 15.2.13, “SELECT Statement”](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement").


In prepared [`CALL`](https://dev.mysql.com/doc/refman/8.0/en/call.html "15.2.1 CALL Statement") statements used with
[`PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "15.5.1 PREPARE Statement") and
[`EXECUTE`](https://dev.mysql.com/doc/refman/8.0/en/execute.html "15.5.2 EXECUTE Statement"), placeholder support for
`OUT` and `INOUT` parameters is
available beginning with MySQL 8.0. See
[Section 15.2.1, “CALL Statement”](https://dev.mysql.com/doc/refman/8.0/en/call.html "15.2.1 CALL Statement"), for an example and a workaround for earlier
versions. Placeholders can be used for `IN`
parameters regardless of version.


SQL syntax for prepared statements cannot be used in nested fashion.
That is, a statement passed to
[`PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "15.5.1 PREPARE Statement") cannot itself be a
[`PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "15.5.1 PREPARE Statement"),
[`EXECUTE`](https://dev.mysql.com/doc/refman/8.0/en/execute.html "15.5.2 EXECUTE Statement"), or
[`DEALLOCATE PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/deallocate-prepare.html "15.5.3 DEALLOCATE PREPARE Statement") statement.


SQL syntax for prepared statements is distinct from using prepared
statement API calls. For example, you cannot use the
[`mysql_stmt_prepare()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-stmt-prepare.html) C API function
to prepare a [`PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "15.5.1 PREPARE Statement"),
[`EXECUTE`](https://dev.mysql.com/doc/refman/8.0/en/execute.html "15.5.2 EXECUTE Statement"), or
[`DEALLOCATE PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/deallocate-prepare.html "15.5.3 DEALLOCATE PREPARE Statement") statement.


SQL syntax for prepared statements can be used within stored
procedures, but not in stored functions or triggers. However, a
cursor cannot be used for a dynamic statement that is prepared and
executed with [`PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "15.5.1 PREPARE Statement") and
[`EXECUTE`](https://dev.mysql.com/doc/refman/8.0/en/execute.html "15.5.2 EXECUTE Statement"). The statement for a cursor
is checked at cursor creation time, so the statement cannot be
dynamic.


SQL syntax for prepared statements does not support multi-statements
(that is, multiple statements within a single string separated by
`;` characters).


To write C programs that use the [`CALL`](https://dev.mysql.com/doc/refman/8.0/en/call.html "15.2.1 CALL Statement")
SQL statement to execute stored procedures that contain prepared
statements, the `CLIENT_MULTI_RESULTS` flag must be
enabled. This is because each [`CALL`](https://dev.mysql.com/doc/refman/8.0/en/call.html "15.2.1 CALL Statement")
returns a result to indicate the call status, in addition to any
result sets that might be returned by statements executed within the
procedure.


`CLIENT_MULTI_RESULTS` can be enabled when you call
[`mysql_real_connect()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-real-connect.html), either
explicitly by passing the `CLIENT_MULTI_RESULTS`
flag itself, or implicitly by passing
`CLIENT_MULTI_STATEMENTS` (which also enables
`CLIENT_MULTI_RESULTS`). For additional
information, see [Section 15.2.1, “CALL Statement”](https://dev.mysql.com/doc/refman/8.0/en/call.html "15.2.1 CALL Statement").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/stop-group-replication.html "Previous: STOP GROUP_REPLICATION Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html "Up: SQL Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "Next: PREPARE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/sql-prepared-statements.html)

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