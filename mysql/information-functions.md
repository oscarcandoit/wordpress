---
url: https://dev.mysql.com/doc/refman/8.0/en/information-functions.html
scraped_at: 2025-10-20T03:02:09.552Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html "Hide Sidebar")

[Previous: Locking Functions](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html "Previous: Locking Functions")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html "Up: Functions and Operators")[Next: Spatial Analysis Functions](https://dev.mysql.com/doc/refman/8.0/en/spatial-analysis-functions.html "Next: Spatial Analysis Functions")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/information-functions.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/information-functions.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/information-functions.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/information-functions.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/information-functions.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/information-functions.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/information-functions.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/information-functions.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html)  /
Information Functions


## 14.15 Information Functions

**Table 14.20 Information Functions**

| Name | Description |
| --- | --- |
| [`BENCHMARK()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_benchmark) | Repeatedly execute an expression |
| [`CHARSET()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_charset) | Return the character set of the argument |
| [`COERCIBILITY()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_coercibility) | Return the collation coercibility value of the string argument |
| [`COLLATION()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_collation) | Return the collation of the string argument |
| [`CONNECTION_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_connection-id) | Return the connection ID (thread ID) for the connection |
| [`CURRENT_ROLE()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-role) | Return the current active roles |
| [`CURRENT_USER()`, `CURRENT_USER`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user) | The authenticated user name and host name |
| [`DATABASE()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_database) | Return the default (current) database name |
| [`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows) | For a SELECT with a LIMIT clause, the number of rows that would be<br> returned were there no LIMIT clause |
| [`ICU_VERSION()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_icu-version) | ICU library version |
| [`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) | Value of the AUTOINCREMENT column for the last INSERT |
| [`ROLES_GRAPHML()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_roles-graphml) | Return a GraphML document representing memory role subgraphs |
| [`ROW_COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_row-count) | The number of rows updated |
| [`SCHEMA()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_schema) | Synonym for DATABASE() |
| [`SESSION_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_session-user) | Synonym for USER() |
| [`SYSTEM_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_system-user) | Synonym for USER() |
| [`USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_user) | The user name and host name provided by the client |
| [`VERSION()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_version) | Return a string that indicates the MySQL server version |

| Name | Description |
| --- | --- |

- [`BENCHMARK(count,expr)`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_benchmark)


The [`BENCHMARK()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_benchmark) function
executes the expression _`expr`_
repeatedly _`count`_ times. It may be
used to time how quickly MySQL processes the expression. The
result value is `0`, or
`NULL` for inappropriate arguments such as a
`NULL` or negative repeat count.



The intended use is from within the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client")
client, which reports query execution times:




``` sql

mysql> SELECT BENCHMARK(1000000,AES_ENCRYPT('hello','goodbye'));
+---------------------------------------------------+
| BENCHMARK(1000000,AES_ENCRYPT('hello','goodbye')) |
+---------------------------------------------------+
|                                                 0 |
+---------------------------------------------------+
1 row in set (4.74 sec)
```




The time reported is elapsed time on the client end, not CPU
time on the server end. It is advisable to execute
[`BENCHMARK()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_benchmark) several times, and
to interpret the result with regard to how heavily loaded the
server machine is.


[`BENCHMARK()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_benchmark) is intended for
measuring the runtime performance of scalar expressions, which
has some significant implications for the way that you use it
and interpret the results:




- Only scalar expressions can be used. Although the
expression can be a subquery, it must return a single
column and at most a single row. For example,
[`BENCHMARK(10, (SELECT * FROM\\
                t))`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_benchmark) fails if the table `t` has
more than one column or more than one row.


- Executing a `SELECT
                expr` statement
_`N`_ times differs from executing
`SELECT BENCHMARK(N,
                expr)` in terms of the
amount of overhead involved. The two have very different
execution profiles and you should not expect them to take
the same amount of time. The former involves the parser,
optimizer, table locking, and runtime evaluation
_`N`_ times each. The latter
involves only runtime evaluation
_`N`_ times, and all the other
components just once. Memory structures already allocated
are reused, and runtime optimizations such as local
caching of results already evaluated for aggregate
functions can alter the results. Use of
[`BENCHMARK()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_benchmark) thus measures
performance of the runtime component by giving more weight
to that component and removing the “noise”
introduced by the network, parser, optimizer, and so
forth.


- [`CHARSET(str)`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_charset)


Returns the character set of the string argument, or
`NULL` if the argument is
`NULL`.




``` sql

mysql> SELECT CHARSET('abc');
          -> 'utf8mb3'
mysql> SELECT CHARSET(CONVERT('abc' USING latin1));
          -> 'latin1'
mysql> SELECT CHARSET(USER());
          -> 'utf8mb3'
```

- [`COERCIBILITY(str)`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_coercibility)


Returns the collation coercibility value of the string
argument.




``` sql

mysql> SELECT COERCIBILITY('abc' COLLATE utf8mb4_swedish_ci);
          -> 0
mysql> SELECT COERCIBILITY(USER());
          -> 3
mysql> SELECT COERCIBILITY('abc');
          -> 4
mysql> SELECT COERCIBILITY(1000);
          -> 5
```




The return values have the meanings shown in the following
table. Lower values have higher precedence.





| Coercibility | Meaning | Example |
| --- | --- | --- |
| `0` | Explicit collation | Value with `COLLATE` clause |
| `1` | No collation | Concatenation of strings with different collations |
| `2` | Implicit collation | Column value, stored routine parameter or local variable |
| `3` | System constant | [`USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_user) return value |
| `4` | Coercible | Literal string |
| `5` | Numeric | Numeric or temporal value |
| `6` | Ignorable | `NULL` or an expression derived from<br> `NULL` |




For more information, see
[Section 12.8.4, “Collation Coercibility in Expressions”](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-coercibility.html "12.8.4 Collation Coercibility in Expressions").


- [`COLLATION(str)`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_collation)


Returns the collation of the string argument.




``` sql

mysql> SELECT COLLATION('abc');
          -> 'utf8mb4_0900_ai_ci'
mysql> SELECT COLLATION(_utf8mb4'abc');
          -> 'utf8mb4_0900_ai_ci'
mysql> SELECT COLLATION(_latin1'abc');
          -> 'latin1_swedish_ci'
```

- [`CONNECTION_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_connection-id)


Returns the connection ID (thread ID) for the connection.
Every connection has an ID that is unique among the set of
currently connected clients.



The value returned by
[`CONNECTION_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_connection-id) is the same
type of value as displayed in the `ID` column
of the Information Schema
[`PROCESSLIST`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-processlist-table.html "28.3.23 The INFORMATION_SCHEMA PROCESSLIST Table") table, the
`Id` column of [`SHOW\\
            PROCESSLIST`](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html "15.7.7.29 SHOW PROCESSLIST Statement") output, and the
`PROCESSLIST_ID` column of the Performance
Schema [`threads`](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-threads-table.html "29.12.21.8 The threads Table") table.




``` sql

mysql> SELECT CONNECTION_ID();
          -> 23786
```






Warning





Changing the session value of the
[`pseudo_thread_id`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_pseudo_thread_id) system
variable changes the value returned by the
[`CONNECTION_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_connection-id) function.

- [`CURRENT_ROLE()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-role)


Returns a `utf8mb3` string containing the
current active roles for the current session, separated by
commas, or `NONE` if there are none. The
value reflects the setting of the
[`sql_quote_show_create`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_sql_quote_show_create) system
variable.



Suppose that an account is granted roles as follows:




``` sql

GRANT 'r1', 'r2' TO 'u1'@'localhost';
SET DEFAULT ROLE ALL TO 'u1'@'localhost';
```




In sessions for `u1`, the initial
[`CURRENT_ROLE()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-role) value names the
default account roles. Using [`SET\\
            ROLE`](https://dev.mysql.com/doc/refman/8.0/en/set-role.html "15.7.1.11 SET ROLE Statement") changes that:




``` sql

mysql> SELECT CURRENT_ROLE();
+-------------------+
| CURRENT_ROLE()    |
+-------------------+
| `r1`@`%`,`r2`@`%` |
+-------------------+
mysql> SET ROLE 'r1'; SELECT CURRENT_ROLE();
+----------------+
| CURRENT_ROLE() |
+----------------+
| `r1`@`%`       |
+----------------+
```

- [`CURRENT_USER`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user),
[`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user)


Returns the user name and host name combination for the MySQL
account that the server used to authenticate the current
client. This account determines your access privileges. The
return value is a string in the `utf8mb3`
character set.



The value of [`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user) can
differ from the value of
[`USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_user).




``` sql

mysql> SELECT USER();
          -> 'davida@localhost'
mysql> SELECT * FROM mysql.user;
ERROR 1044: Access denied for user ''@'localhost' to
database 'mysql'
mysql> SELECT CURRENT_USER();
          -> '@localhost'
```




The example illustrates that although the client specified a
user name of `davida` (as indicated by the
value of the [`USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_user) function),
the server authenticated the client using an anonymous user
account (as seen by the empty user name part of the
[`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user) value). One way
this might occur is that there is no account listed in the
grant tables for `davida`.



Within a stored program or view,
[`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user) returns the
account for the user who defined the object (as given by its
`DEFINER` value) unless defined with the
`SQL SECURITY INVOKER` characteristic. In the
latter case, [`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user)
returns the object's invoker.



Triggers and events have no option to define the `SQL
            SECURITY` characteristic, so for these objects,
[`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user) returns the
account for the user who defined the object. To return the
invoker, use [`USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_user) or
[`SESSION_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_session-user).



The following statements support use of the
[`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user) function to take
the place of the name of (and, possibly, a host for) an
affected user or a definer; in such cases,
[`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user) is expanded
where and as needed:




- [`DROP USER`](https://dev.mysql.com/doc/refman/8.0/en/drop-user.html "15.7.1.5 DROP USER Statement")

- [`RENAME USER`](https://dev.mysql.com/doc/refman/8.0/en/rename-user.html "15.7.1.7 RENAME USER Statement")

- [`GRANT`](https://dev.mysql.com/doc/refman/8.0/en/grant.html "15.7.1.6 GRANT Statement")

- [`REVOKE`](https://dev.mysql.com/doc/refman/8.0/en/revoke.html "15.7.1.8 REVOKE Statement")

- [`CREATE FUNCTION`](https://dev.mysql.com/doc/refman/8.0/en/create-function.html "15.1.14 CREATE FUNCTION Statement")

- [`CREATE PROCEDURE`](https://dev.mysql.com/doc/refman/8.0/en/create-procedure.html "15.1.17 CREATE PROCEDURE and CREATE FUNCTION Statements")

- [`CREATE TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "15.1.22 CREATE TRIGGER Statement")

- [`CREATE EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement")

- [`CREATE VIEW`](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "15.1.23 CREATE VIEW Statement")

- [`ALTER EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement")

- [`ALTER VIEW`](https://dev.mysql.com/doc/refman/8.0/en/alter-view.html "15.1.11 ALTER VIEW Statement")

- [`SET PASSWORD`](https://dev.mysql.com/doc/refman/8.0/en/set-password.html "15.7.1.10 SET PASSWORD Statement")


For information about the implications that this expansion of
[`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user) has for
replication, see
[Section 19.5.1.8, “Replication of CURRENT\_USER()”](https://dev.mysql.com/doc/refman/8.0/en/replication-features-current-user.html "19.5.1.8 Replication of CURRENT_USER()").


Beginning with MySQL 8.0.34, this function can be used for the
default value of a [`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") or
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") column, as shown in the
following [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement")
statement:


``` sql

CREATE TABLE t (c VARCHAR(288) DEFAULT (CURRENT_USER()));
```

- [`DATABASE()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_database)


Returns the default (current) database name as a string in the
`utf8mb3` character set. If there is no
default database, [`DATABASE()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_database)
returns `NULL`. Within a stored routine, the
default database is the database that the routine is
associated with, which is not necessarily the same as the
database that is the default in the calling context.




``` sql

mysql> SELECT DATABASE();
          -> 'test'
```




If there is no default database,
[`DATABASE()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_database) returns
`NULL`.


- [`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows)




Note





The `SQL_CALC_FOUND_ROWS` query modifier
and accompanying [`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows)
function are deprecated as of MySQL 8.0.17; expect them to
be removed in a future version of MySQL. As a replacement,
considering executing your query with
`LIMIT`, and then a second query with
[`COUNT(*)`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count) and without
`LIMIT` to determine whether there are
additional rows. For example, instead of these queries:






``` sql

SELECT SQL_CALC_FOUND_ROWS * FROM tbl_name WHERE id > 100 LIMIT 10;
SELECT FOUND_ROWS();
```






Use these queries instead:






``` sql

SELECT * FROM tbl_name WHERE id > 100 LIMIT 10;
SELECT COUNT(*) FROM tbl_name WHERE id > 100;
```





[`COUNT(*)`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count) is subject to
certain optimizations.
`SQL_CALC_FOUND_ROWS` causes some
optimizations to be disabled.





A [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement may include
a `LIMIT` clause to restrict the number of
rows the server returns to the client. In some cases, it is
desirable to know how many rows the statement would have
returned without the `LIMIT`, but without
running the statement again. To obtain this row count, include
an `SQL_CALC_FOUND_ROWS` option in the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement, and then
invoke [`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows) afterward:




``` sql

mysql> SELECT SQL_CALC_FOUND_ROWS * FROM tbl_name
      -> WHERE id > 100 LIMIT 10;
mysql> SELECT FOUND_ROWS();
```




The second [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") returns a
number indicating how many rows the first
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") would have returned had
it been written without the `LIMIT` clause.



In the absence of the `SQL_CALC_FOUND_ROWS`
option in the most recent successful
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement,
[`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows) returns the number
of rows in the result set returned by that statement. If the
statement includes a `LIMIT` clause,
[`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows) returns the number
of rows up to the limit. For example,
[`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows) returns 10 or 60,
respectively, if the statement includes `LIMIT
            10` or `LIMIT 50, 10`.



The row count available through
[`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows) is transient and
not intended to be available past the statement following the
`SELECT SQL_CALC_FOUND_ROWS` statement. If
you need to refer to the value later, save it:




``` sql

mysql> SELECT SQL_CALC_FOUND_ROWS * FROM ... ;
mysql> SET @rows = FOUND_ROWS();
```




If you are using `SELECT
            SQL_CALC_FOUND_ROWS`, MySQL must calculate how many
rows are in the full result set. However, this is faster than
running the query again without `LIMIT`,
because the result set need not be sent to the client.


`SQL_CALC_FOUND_ROWS` and
[`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows) can be useful in
situations when you want to restrict the number of rows that a
query returns, but also determine the number of rows in the
full result set without running the query again. An example is
a Web script that presents a paged display containing links to
the pages that show other sections of a search result. Using
[`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows) enables you to
determine how many other pages are needed for the rest of the
result.



The use of `SQL_CALC_FOUND_ROWS` and
[`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows) is more complex
for [`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause") statements than for
simple [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements,
because `LIMIT` may occur at multiple places
in a [`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause"). It may be applied
to individual [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements
in the [`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause"), or global to the
[`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause") result as a whole.



The intent of `SQL_CALC_FOUND_ROWS` for
[`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause") is that it should return
the row count that would be returned without a global
`LIMIT`. The conditions for use of
`SQL_CALC_FOUND_ROWS` with
[`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause") are:




- The `SQL_CALC_FOUND_ROWS` keyword must
appear in the first [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
of the [`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause").


- The value of [`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows)
is exact only if
[`UNION ALL`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause")
is used. If [`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause") without
`ALL` is used, duplicate removal occurs
and the value of
[`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows) is only
approximate.


- If no `LIMIT` is present in the
[`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause"),
`SQL_CALC_FOUND_ROWS` is ignored and
returns the number of rows in the temporary table that is
created to process the
[`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause").


Beyond the cases described here, the behavior of
[`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows) is undefined (for
example, its value following a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement that fails
with an error).

Important

[`FOUND_ROWS()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_found-rows) is not
replicated reliably using statement-based replication. This
function is automatically replicated using row-based
replication.

- [`ICU_VERSION()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_icu-version)


The version of the International Components for Unicode (ICU)
library used to support regular expression operations (see
[Section 14.8.2, “Regular Expressions”](https://dev.mysql.com/doc/refman/8.0/en/regexp.html "14.8.2 Regular Expressions")). This function is primarily intended
for use in test cases.


- [`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id),
[`LAST_INSERT_ID(expr)`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id)


With no argument,
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) returns a
`BIGINT UNSIGNED` (64-bit) value representing
the first automatically generated value successfully inserted
for an `AUTO_INCREMENT` column as a result of
the most recently executed
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement. The value of
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) remains
unchanged if no rows are successfully inserted.



With an argument,
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) returns an
unsigned integer, or `NULL` if the argument
is `NULL`.



For example, after inserting a row that generates an
`AUTO_INCREMENT` value, you can get the value
like this:




``` sql

mysql> SELECT LAST_INSERT_ID();
          -> 195
```




The currently executing statement does not affect the value of
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id). Suppose that
you generate an `AUTO_INCREMENT` value with
one statement, and then refer to
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) in a
multiple-row [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement
that inserts rows into a table with its own
`AUTO_INCREMENT` column. The value of
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) remains stable
in the second statement; its value for the second and later
rows is not affected by the earlier row insertions. (You
should be aware that, if you mix references to
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) and
[`LAST_INSERT_ID(expr)`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id),
the effect is undefined.)



If the previous statement returned an error, the value of
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) is undefined.
For transactional tables, if the statement is rolled back due
to an error, the value of
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) is left
undefined. For manual
[`ROLLBACK`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements"),
the value of [`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id)
is not restored to that before the transaction; it remains as
it was at the point of the
[`ROLLBACK`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements").



Within the body of a stored routine (procedure or function) or
a trigger, the value of
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) changes the
same way as for statements executed outside the body of these
kinds of objects. The effect of a stored routine or trigger
upon the value of
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) that is seen
by following statements depends on the kind of routine:




- If a stored procedure executes statements that change the
value of [`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id),
the changed value is seen by statements that follow the
procedure call.


- For stored functions and triggers that change the value,
the value is restored when the function or trigger ends,
so statements coming after it do not see a changed value.


The ID that was generated is maintained in the server on a
_per-connection basis_. This means that the
value returned by the function to a given client is the first
`AUTO_INCREMENT` value generated for most
recent statement affecting an
`AUTO_INCREMENT` column _by that_
_client_. This value cannot be affected by other
clients, even if they generate
`AUTO_INCREMENT` values of their own. This
behavior ensures that each client can retrieve its own ID
without concern for the activity of other clients, and without
the need for locks or transactions.


The value of [`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id)
is not changed if you set the
`AUTO_INCREMENT` column of a row to a
non-“magic” value (that is, a value that is not
`NULL` and not `0`).

Important

If you insert multiple rows using a single
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement,
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) returns the
value generated for the _first_ inserted
row _only_. The reason for this is to
make it possible to reproduce easily the same
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement against some
other server.

For example:


``` sql

mysql> USE test;

mysql> CREATE TABLE t (
       id INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
       name VARCHAR(10) NOT NULL
       );

mysql> INSERT INTO t VALUES (NULL, 'Bob');

mysql> SELECT * FROM t;
+----+------+
| id | name |
+----+------+
|  1 | Bob  |
+----+------+

mysql> SELECT LAST_INSERT_ID();
+------------------+
| LAST_INSERT_ID() |
+------------------+
|                1 |
+------------------+

mysql> INSERT INTO t VALUES
       (NULL, 'Mary'), (NULL, 'Jane'), (NULL, 'Lisa');

mysql> SELECT * FROM t;
+----+------+
| id | name |
+----+------+
|  1 | Bob  |
|  2 | Mary |
|  3 | Jane |
|  4 | Lisa |
+----+------+

mysql> SELECT LAST_INSERT_ID();
+------------------+
| LAST_INSERT_ID() |
+------------------+
|                2 |
+------------------+
```

Although the second [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement")
statement inserted three new rows into `t`,
the ID generated for the first of these rows was
`2`, and it is this value that is returned by
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) for the
following [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement.


If you use [`INSERT\\
          IGNORE`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") and the row is ignored, the
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) remains
unchanged from the current value (or 0 is returned if the
connection has not yet performed a successful
`INSERT`) and, for non-transactional tables,
the `AUTO_INCREMENT` counter is not
incremented. For `InnoDB` tables, the
`AUTO_INCREMENT` counter is incremented if
[`innodb_autoinc_lock_mode`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_autoinc_lock_mode) is
set to `1` or `2`, as
demonstrated in the following example:


``` sql

mysql> USE test;

mysql> SELECT @@innodb_autoinc_lock_mode;
+----------------------------+
| @@innodb_autoinc_lock_mode |
+----------------------------+
|                          1 |
+----------------------------+

mysql> CREATE TABLE `t` (
       `id` INT(11) NOT NULL AUTO_INCREMENT,
       `val` INT(11) DEFAULT NULL,
       PRIMARY KEY (`id`),
       UNIQUE KEY `i1` (`val`)
       ) ENGINE=InnoDB;

# Insert two rows

mysql> INSERT INTO t (val) VALUES (1),(2);

# With auto_increment_offset=1, the inserted rows
# result in an AUTO_INCREMENT value of 3

mysql> SHOW CREATE TABLE t\G
*************************** 1. row ***************************
       Table: t
Create Table: CREATE TABLE `t` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `val` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `i1` (`val`)
) ENGINE=InnoDB AUTO_INCREMENT=3 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci

# LAST_INSERT_ID() returns the first automatically generated
# value that is successfully inserted for the AUTO_INCREMENT column

mysql> SELECT LAST_INSERT_ID();
+------------------+
| LAST_INSERT_ID() |
+------------------+
|                1 |
+------------------+

# The attempted insertion of duplicate rows fail but errors are ignored

mysql> INSERT IGNORE INTO t (val) VALUES (1),(2);
Query OK, 0 rows affected (0.00 sec)
Records: 2  Duplicates: 2  Warnings: 0

# With innodb_autoinc_lock_mode=1, the AUTO_INCREMENT counter
# is incremented for the ignored rows

mysql> SHOW CREATE TABLE t\G
*************************** 1. row ***************************
       Table: t
Create Table: CREATE TABLE `t` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `val` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `i1` (`val`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci

# The LAST_INSERT_ID is unchanged because the previous insert was unsuccessful

mysql> SELECT LAST_INSERT_ID();
+------------------+
| LAST_INSERT_ID() |
+------------------+
|                1 |
+------------------+
```

For more information, see
[Section 17.6.1.6, “AUTO\_INCREMENT Handling in InnoDB”](https://dev.mysql.com/doc/refman/8.0/en/innodb-auto-increment-handling.html "17.6.1.6 AUTO_INCREMENT Handling in InnoDB").


If _`expr`_ is given as an argument to
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id), the value of
the argument is returned by the function and is remembered as
the next value to be returned by
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id). This can be
used to simulate sequences:

1. Create a table to hold the sequence counter and initialize
    it:




``` sql

mysql> CREATE TABLE sequence (id INT NOT NULL);
mysql> INSERT INTO sequence VALUES (0);
```

2. Use the table to generate sequence numbers like this:




``` sql

mysql> UPDATE sequence SET id=LAST_INSERT_ID(id+1);
mysql> SELECT LAST_INSERT_ID();
```




    The [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement
    increments the sequence counter and causes the next call
    to [`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) to
    return the updated value. The
    [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement retrieves
    that value. The
    [`mysql_insert_id()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-insert-id.html) C API
    function can also be used to get the value. See
    [mysql\_insert\_id()](https://dev.mysql.com/doc/c-api/8.0/en/mysql-insert-id.html).


You can generate sequences without calling
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id), but the
utility of using the function this way is that the ID value is
maintained in the server as the last automatically generated
value. It is multi-user safe because multiple clients can
issue the [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statement and
get their own sequence value with the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement (or
[`mysql_insert_id()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-insert-id.html)), without
affecting or being affected by other clients that generate
their own sequence values.


Note that [`mysql_insert_id()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-insert-id.html) is
only updated after [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") and
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statements, so you
cannot use the C API function to retrieve the value for
[`LAST_INSERT_ID(expr)`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id)
after executing other SQL statements like
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") or
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment").


- [`ROLES_GRAPHML()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_roles-graphml)


Returns a `utf8mb3` string containing a
GraphML document representing memory role subgraphs. The
[`ROLE_ADMIN`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_role-admin) privilege (or the
deprecated [`SUPER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_super) privilege) is
required to see content in the
`<graphml>` element. Otherwise, the
result shows only an empty element:




``` sql

mysql> SELECT ROLES_GRAPHML();
+---------------------------------------------------+
| ROLES_GRAPHML()                                   |
+---------------------------------------------------+
| <?xml version="1.0" encoding="UTF-8"?><graphml /> |
+---------------------------------------------------+
```

- [`ROW_COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_row-count)

`ROW_COUNT()` returns a value as follows:




- DDL statements: 0. This applies to statements such as
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") or
[`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement").


- DML statements other than
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"): The number of
affected rows. This applies to statements such as
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"),
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"), or
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") (as before), but now
also to statements such as [`ALTER\\
                TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") and [`LOAD\\
                DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement").


- [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"): -1 if the statement
returns a result set, or the number of rows
“affected” if it does not. For example, for
`SELECT * FROM t1`,
[`ROW_COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_row-count) returns -1. For
`SELECT * FROM t1 INTO OUTFILE
                'file_name'`,
[`ROW_COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_row-count) returns the
number of rows written to the file.


- [`SIGNAL`](https://dev.mysql.com/doc/refman/8.0/en/signal.html "15.6.7.5 SIGNAL Statement") statements: 0.


For [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statements, the
affected-rows value by default is the number of rows actually
changed. If you specify the
`CLIENT_FOUND_ROWS` flag to
[`mysql_real_connect()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-real-connect.html) when
connecting to [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server"), the affected-rows
value is the number of rows “found”; that is,
matched by the `WHERE` clause.


For [`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") statements, the
affected-rows value is 2 if the new row replaced an old row,
because in this case, one row was inserted after the duplicate
was deleted.


For
[`INSERT\\
          ... ON DUPLICATE KEY UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/insert-on-duplicate.html "15.2.7.2 INSERT ... ON DUPLICATE KEY UPDATE Statement") statements, the
affected-rows value per row is 1 if the row is inserted as a
new row, 2 if an existing row is updated, and 0 if an existing
row is set to its current values. If you specify the
`CLIENT_FOUND_ROWS` flag, the affected-rows
value is 1 (not 0) if an existing row is set to its current
values.


The [`ROW_COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_row-count) value is
similar to the value from the
[`mysql_affected_rows()`](https://dev.mysql.com/doc/c-api/8.0/en/mysql-affected-rows.html) C API
function and the row count that the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client")
client displays following statement execution.


``` sql

mysql> INSERT INTO t VALUES(1),(2),(3);
Query OK, 3 rows affected (0.00 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> SELECT ROW_COUNT();
+-------------+
| ROW_COUNT() |
+-------------+
|           3 |
+-------------+
1 row in set (0.00 sec)

mysql> DELETE FROM t WHERE i IN(1,2);
Query OK, 2 rows affected (0.00 sec)

mysql> SELECT ROW_COUNT();
+-------------+
| ROW_COUNT() |
+-------------+
|           2 |
+-------------+
1 row in set (0.00 sec)
```

Important

[`ROW_COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_row-count) is not replicated
reliably using statement-based replication. This function is
automatically replicated using row-based replication.

- [`SCHEMA()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_schema)


This function is a synonym for
[`DATABASE()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_database).


- [`SESSION_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_session-user)

[`SESSION_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_session-user) is a synonym for
[`USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_user).



Beginning with MySQL 8.0.34, like
[`USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_user), this function can be
used for the default value of a
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") or
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") column, as shown in the
following [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement")
statement:




``` sql

CREATE TABLE t (c VARCHAR(288) DEFAULT (SESSION_USER()));
```

- [`SYSTEM_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_system-user)

[`SYSTEM_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_system-user) is a synonym for
[`USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_user).





Note





The [`SYSTEM_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_system-user) function is
distinct from the [`SYSTEM_USER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_system-user)
privilege. The former returns the current MySQL account
name. The latter distinguishes the system user and regular
user account categories (see
[Section 8.2.11, “Account Categories”](https://dev.mysql.com/doc/refman/8.0/en/account-categories.html "8.2.11 Account Categories")).





Beginning with MySQL 8.0.34, like
[`USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_user), this function can be
used for the default value of a
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") or
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") column, as shown in the
following [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement")
statement:




``` sql

CREATE TABLE t (c VARCHAR(288) DEFAULT (SYSTEM_USER()));
```

- [`USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_user)


Returns the current MySQL user name and host name as a string
in the `utf8mb3` character set.




``` sql

mysql> SELECT USER();
          -> 'davida@localhost'
```




The value indicates the user name you specified when
connecting to the server, and the client host from which you
connected. The value can be different from that of
[`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user).



Beginning with MySQL 8.0.34, this function can be used for the
default value of a [`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") or
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") column, as shown in the
following [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement")
statement:




``` sql

CREATE TABLE t (c VARCHAR(288) DEFAULT (USER()));
```

- [`VERSION()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_version)


Returns a string that indicates the MySQL server version. The
string uses the `utf8mb3` character set. The
value might have a suffix in addition to the version number.
See the description of the
[`version`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_version) system variable in
[Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables").



This function is unsafe for statement-based replication. A
warning is logged if you use this function when
[`binlog_format`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-binary-log.html#sysvar_binlog_format) is set to
`STATEMENT`.




``` sql

mysql> SELECT VERSION();
          -> '8.0.43-standard'
```


[PREV](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html "Previous: Locking Functions") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/functions.html "Up: Functions and Operators") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/spatial-analysis-functions.html "Next: Spatial Analysis Functions")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html)

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