---
url: https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html
scraped_at: 2025-10-20T03:11:18.773Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "Hide Sidebar")

[Previous: SHOW VARIABLES Statement](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html "Previous: SHOW VARIABLES Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements")[Next: Other Administrative Statements](https://dev.mysql.com/doc/refman/8.0/en/other-administrative-statements.html "Next: Other Administrative Statements")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/show-warnings.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/show-warnings.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/show-warnings.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/show-warnings.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/show-warnings.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/show-warnings.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/show-warnings.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/show-warnings.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)  /

SHOW WARNINGS Statement


#### 15.7.7.42 SHOW WARNINGS Statement

``` sql

SHOW WARNINGS [LIMIT [offset,] row_count]
SHOW COUNT(*) WARNINGS
```

[`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") is a diagnostic
statement that displays information about the conditions
(errors, warnings, and notes) resulting from executing a
statement in the current session. Warnings are generated for DML
statements such as [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"),
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"), and
[`LOAD DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement") as well as DDL
statements such as [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement")
and [`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement").


The `LIMIT` clause has the same syntax as for
the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement. See
[Section 15.2.13, “SELECT Statement”](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement").


[`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") is also used
following [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement"), to display the
extended information generated by
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement"). See
[Section 10.8.3, “Extended EXPLAIN Output Format”](https://dev.mysql.com/doc/refman/8.0/en/explain-extended.html "10.8.3 Extended EXPLAIN Output Format").


[`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") displays
information about the conditions resulting from execution of the
most recent nondiagnostic statement in the current session. If
the most recent statement resulted in an error during parsing,
[`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") shows the resulting
conditions, regardless of statement type (diagnostic or
nondiagnostic).


The [`SHOW COUNT(*)\\
        WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") diagnostic statement displays the total
number of errors, warnings, and notes. You can also retrieve
this number from the
[`warning_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_warning_count) system variable:


``` sql

SHOW COUNT(*) WARNINGS;
SELECT @@warning_count;
```

A difference in these statements is that the first is a
diagnostic statement that does not clear the message list. The
second, because it is a [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statement is considered nondiagnostic and does clear the message
list.


A related diagnostic statement, [`SHOW\\
        ERRORS`](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html "15.7.7.17 SHOW ERRORS Statement"), shows only error conditions (it excludes
warnings and notes), and
[`SHOW COUNT(*)\\
        ERRORS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") statement displays the total number of errors.
See [Section 15.7.7.17, “SHOW ERRORS Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-errors.html "15.7.7.17 SHOW ERRORS Statement"). [`GET\\
        DIAGNOSTICS`](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement") can be used to examine information for
individual conditions. See [Section 15.6.7.3, “GET DIAGNOSTICS Statement”](https://dev.mysql.com/doc/refman/8.0/en/get-diagnostics.html "15.6.7.3 GET DIAGNOSTICS Statement").


Here is a simple example that shows data-conversion warnings for
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"). The example assumes that
strict SQL mode is disabled. With strict mode enabled, the
warnings would become errors and terminate the
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement").


``` sql

mysql> CREATE TABLE t1 (a TINYINT NOT NULL, b CHAR(4));
Query OK, 0 rows affected (0.05 sec)

mysql> INSERT INTO t1 VALUES(10,'mysql'), (NULL,'test'), (300,'xyz');
Query OK, 3 rows affected, 3 warnings (0.00 sec)
Records: 3  Duplicates: 0  Warnings: 3

mysql> SHOW WARNINGS\G
*************************** 1. row ***************************
  Level: Warning
   Code: 1265
Message: Data truncated for column 'b' at row 1
*************************** 2. row ***************************
  Level: Warning
   Code: 1048
Message: Column 'a' cannot be null
*************************** 3. row ***************************
  Level: Warning
   Code: 1264
Message: Out of range value for column 'a' at row 3
3 rows in set (0.00 sec)
```

The [`max_error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_error_count) system
variable controls the maximum number of error, warning, and note
messages for which the server stores information, and thus the
number of messages that [`SHOW\\
        WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") displays. To change the number of messages
the server can store, change the value of
[`max_error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_error_count).


[`max_error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_error_count) controls only
how many messages are stored, not how many are counted. The
value of [`warning_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_warning_count) is not
limited by [`max_error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_error_count),
even if the number of messages generated exceeds
[`max_error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_error_count). The following
example demonstrates this. The [`ALTER\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") statement produces three warning messages
(strict SQL mode is disabled for the example to prevent an error
from occurring after a single conversion issue). Only one
message is stored and displayed because
[`max_error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_error_count) has been set to
1, but all three are counted (as shown by the value of
[`warning_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_warning_count)):


``` sql

mysql> SHOW VARIABLES LIKE 'max_error_count';
+-----------------+-------+
| Variable_name   | Value |
+-----------------+-------+
| max_error_count | 1024  |
+-----------------+-------+
1 row in set (0.00 sec)

mysql> SET max_error_count=1, sql_mode = '';
Query OK, 0 rows affected (0.00 sec)

mysql> ALTER TABLE t1 MODIFY b CHAR;
Query OK, 3 rows affected, 3 warnings (0.00 sec)
Records: 3  Duplicates: 0  Warnings: 3

mysql> SHOW WARNINGS;
+---------+------+----------------------------------------+
| Level   | Code | Message                                |
+---------+------+----------------------------------------+
| Warning | 1263 | Data truncated for column 'b' at row 1 |
+---------+------+----------------------------------------+
1 row in set (0.00 sec)

mysql> SELECT @@warning_count;
+-----------------+
| @@warning_count |
+-----------------+
|               3 |
+-----------------+
1 row in set (0.01 sec)
```

To disable message storage, set
[`max_error_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_error_count) to 0. In this
case, [`warning_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_warning_count) still
indicates how many warnings occurred, but messages are not
stored and cannot be displayed.


The [`sql_notes`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_sql_notes) system variable
controls whether note messages increment
[`warning_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_warning_count) and whether the
server stores them. By default,
[`sql_notes`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_sql_notes) is 1, but if set to
0, notes do not increment
[`warning_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_warning_count) and the server
does not store them:


``` sql

mysql> SET sql_notes = 1;
mysql> DROP TABLE IF EXISTS test.no_such_table;
Query OK, 0 rows affected, 1 warning (0.00 sec)
mysql> SHOW WARNINGS;
+-------+------+------------------------------------+
| Level | Code | Message                            |
+-------+------+------------------------------------+
| Note  | 1051 | Unknown table 'test.no_such_table' |
+-------+------+------------------------------------+
1 row in set (0.00 sec)

mysql> SET sql_notes = 0;
mysql> DROP TABLE IF EXISTS test.no_such_table;
Query OK, 0 rows affected (0.00 sec)
mysql> SHOW WARNINGS;
Empty set (0.00 sec)
```

The MySQL server sends to each client a count indicating the
total number of errors, warnings, and notes resulting from the
most recent statement executed by that client. From the C API,
this value can be obtained by calling
[`mysql_warning_count()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-warning-count.html). See
[mysql\_warning\_count()](https://dev.mysql.com/doc/c-api/8.0/en/mysql-warning-count.html).


In the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client, you can enable and
disable automatic warnings display using the
`warnings` and `nowarning`
commands, respectively, or their shortcuts,
`\W` and `\w` (see
[Section 6.5.1.2, “mysql Client Commands”](https://dev.mysql.com/doc/refman/8.0/en/mysql-commands.html "6.5.1.2 mysql Client Commands")). For example:


``` sql

mysql> \W
Show warnings enabled.
mysql> SELECT 1/0;
+------+
| 1/0  |
+------+
| NULL |
+------+
1 row in set, 1 warning (0.03 sec)

Warning (Code 1365): Division by 0
mysql> \w
Show warnings disabled.
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html "Previous: SHOW VARIABLES Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/other-administrative-statements.html "Next: Other Administrative Statements")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html)

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