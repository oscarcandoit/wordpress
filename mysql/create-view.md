---
url: https://dev.mysql.com/doc/refman/8.0/en/create-view.html
scraped_at: 2025-10-20T03:04:56.311Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/create-view.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "Hide Sidebar")

[Previous: CREATE TRIGGER Statement](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "Previous: CREATE TRIGGER Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements")[Next: DROP DATABASE Statement](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "Next: DROP DATABASE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/create-view.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-view.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-view.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/create-view.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/create-view.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/create-view.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/create-view.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/create-view.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/create-view.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/create-view.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/create-view.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/create-view.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/create-view.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html)  /

CREATE VIEW Statement


### 15.1.23 CREATE VIEW Statement

```sql
CREATE
    [OR REPLACE]
    [ALGORITHM = {UNDEFINED | MERGE | TEMPTABLE}]
    [DEFINER = user]
    [SQL SECURITY { DEFINER | INVOKER }]
    VIEW view_name [(column_list)]
    AS select_statement
    [WITH [CASCADED | LOCAL] CHECK OPTION]
```

The [`CREATE VIEW`](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "15.1.23 CREATE VIEW Statement") statement creates a
new view, or replaces an existing view if the `OR
      REPLACE` clause is given. If the view does not exist,
[`CREATE OR REPLACE\\
      VIEW`](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "15.1.23 CREATE VIEW Statement") is the same as [`CREATE\\
      VIEW`](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "15.1.23 CREATE VIEW Statement"). If the view does exist,
[`CREATE OR REPLACE\\
      VIEW`](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "15.1.23 CREATE VIEW Statement") replaces it.


For information about restrictions on view use, see
[Section 27.9, “Restrictions on Views”](https://dev.mysql.com/doc/refman/8.0/en/view-restrictions.html "27.9 Restrictions on Views").


The _`select_statement`_ is a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement that provides the
definition of the view. (Selecting from the view selects, in
effect, using the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statement.) The _`select_statement`_ can
select from base tables or from other views. Beginning with MySQL
8.0.19, the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement can
use a [`VALUES`](https://dev.mysql.com/doc/refman/8.0/en/values.html "15.2.19 VALUES Statement") statement as its
source, or can be replaced with a
[`TABLE`](https://dev.mysql.com/doc/refman/8.0/en/table.html "15.2.16 TABLE Statement") statement, as with
[`CREATE TABLE\\
      ... SELECT`](https://dev.mysql.com/doc/refman/8.0/en/create-table-select.html "15.1.20.4 CREATE TABLE ... SELECT Statement").


The view definition is “frozen” at creation time and
is not affected by subsequent changes to the definitions of the
underlying tables. For example, if a view is defined as
`SELECT *` on a table, new columns added to the
table later do not become part of the view, and columns dropped
from the table result in an error when selecting from the view.


The `ALGORITHM` clause affects how MySQL
processes the view. The `DEFINER` and
`SQL SECURITY` clauses specify the security
context to be used when checking access privileges at view
invocation time. The `WITH CHECK OPTION` clause
can be given to constrain inserts or updates to rows in tables
referenced by the view. These clauses are described later in this
section.


The [`CREATE VIEW`](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "15.1.23 CREATE VIEW Statement") statement requires
the [`CREATE VIEW`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_create-view) privilege for the
view, and some privilege for each column selected by the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement. For columns used
elsewhere in the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement,
you must have the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege.
If the `OR REPLACE` clause is present, you must
also have the [`DROP`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_drop) privilege for
the view. If the `DEFINER` clause is present, the
privileges required depend on the _`user`_
value, as discussed in [Section 27.6, “Stored Object Access Control”](https://dev.mysql.com/doc/refman/8.0/en/stored-objects-security.html "27.6 Stored Object Access Control").


When a view is referenced, privilege checking occurs as described
later in this section.


A view belongs to a database. By default, a new view is created in
the default database. To create the view explicitly in a given
database, use _`db_name.view_name`_ syntax
to qualify the view name with the database name:


```sql
CREATE VIEW test.v AS SELECT * FROM t;
```

Unqualified table or view names in the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement are also
interpreted with respect to the default database. A view can refer
to tables or views in other databases by qualifying the table or
view name with the appropriate database name.


Within a database, base tables and views share the same namespace,
so a base table and a view cannot have the same name.


Columns retrieved by the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statement can be simple references to table columns, or
expressions that use functions, constant values, operators, and so
forth.


A view must have unique column names with no duplicates, just like
a base table. By default, the names of the columns retrieved by
the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement are used for
the view column names. To define explicit names for the view
columns, specify the optional
_`column_list`_ clause as a list of
comma-separated identifiers. The number of names in
_`column_list`_ must be the same as the
number of columns retrieved by the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement.


A view can be created from many kinds of
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements. It can refer to
base tables or other views. It can use joins,
[`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause"), and subqueries. The
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") need not even refer to any
tables:


```sql
CREATE VIEW v_today (today) AS SELECT CURRENT_DATE;
```

The following example defines a view that selects two columns from
another table as well as an expression calculated from those
columns:


```sql
mysql> CREATE TABLE t (qty INT, price INT);
mysql> INSERT INTO t VALUES(3, 50);
mysql> CREATE VIEW v AS SELECT qty, price, qty*price AS value FROM t;
mysql> SELECT * FROM v;
+------+-------+-------+
| qty  | price | value |
+------+-------+-------+
|    3 |    50 |   150 |
+------+-------+-------+
```

A view definition is subject to the following restrictions:

- The [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement cannot
refer to system variables or user-defined variables.


- Within a stored program, the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement cannot refer
to program parameters or local variables.


- The [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement cannot
refer to prepared statement parameters.


- Any table or view referred to in the definition must exist.
If, after the view has been created, a table or view that the
definition refers to is dropped, use of the view results in an
error. To check a view definition for problems of this kind,
use the [`CHECK TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") statement.


- The definition cannot refer to a `TEMPORARY`
table, and you cannot create a `TEMPORARY`
view.


- You cannot associate a trigger with a view.


- Aliases for column names in the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement are checked
against the maximum column length of 64 characters (not the
maximum alias length of 256 characters).


`ORDER BY` is permitted in a view definition, but
it is ignored if you select from a view using a statement that has
its own `ORDER BY`.


For other options or clauses in the definition, they are added to
the options or clauses of the statement that references the view,
but the effect is undefined. For example, if a view definition
includes a `LIMIT` clause, and you select from
the view using a statement that has its own
`LIMIT` clause, it is undefined which limit
applies. This same principle applies to options such as
`ALL`, `DISTINCT`, or
`SQL_SMALL_RESULT` that follow the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") keyword, and to clauses such
as `INTO`, `FOR UPDATE`,
`FOR SHARE`, `LOCK IN SHARE
      MODE`, and `PROCEDURE`.


The results obtained from a view may be affected if you change the
query processing environment by changing system variables:


```sql
mysql> CREATE VIEW v (mycol) AS SELECT 'abc';
Query OK, 0 rows affected (0.01 sec)

mysql> SET sql_mode = '';
Query OK, 0 rows affected (0.00 sec)

mysql> SELECT "mycol" FROM v;
+-------+
| mycol |
+-------+
| mycol |
+-------+
1 row in set (0.01 sec)

mysql> SET sql_mode = 'ANSI_QUOTES';
Query OK, 0 rows affected (0.00 sec)

mysql> SELECT "mycol" FROM v;
+-------+
| mycol |
+-------+
| abc   |
+-------+
1 row in set (0.00 sec)
```

The `DEFINER` and `SQL SECURITY`
clauses determine which MySQL account to use when checking access
privileges for the view when a statement is executed that
references the view. The valid `SQL SECURITY`
characteristic values are `DEFINER` (the default)
and `INVOKER`. These indicate that the required
privileges must be held by the user who defined or invoked the
view, respectively.


If the `DEFINER` clause is present, the
_`user`_ value should be a MySQL account
specified as
`'user_name'@'host_name'`,
[`CURRENT_USER`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user), or
[`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user). The permitted
_`user`_ values depend on the privileges
you hold, as discussed in
[Section 27.6, “Stored Object Access Control”](https://dev.mysql.com/doc/refman/8.0/en/stored-objects-security.html "27.6 Stored Object Access Control"). Also see that section
for additional information about view security.


If the `DEFINER` clause is omitted, the default
definer is the user who executes the [`CREATE\\
      VIEW`](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "15.1.23 CREATE VIEW Statement") statement. This is the same as specifying
`DEFINER = CURRENT_USER` explicitly.


Within a view definition, the
[`CURRENT_USER`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user) function returns the
view's `DEFINER` value by default. For views
defined with the `SQL SECURITY INVOKER`
characteristic, [`CURRENT_USER`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user)
returns the account for the view's invoker. For information about
user auditing within views, see
[Section 8.2.23, “SQL-Based Account Activity Auditing”](https://dev.mysql.com/doc/refman/8.0/en/account-activity-auditing.html "8.2.23 SQL-Based Account Activity Auditing").


Within a stored routine that is defined with the `SQL
      SECURITY DEFINER` characteristic,
[`CURRENT_USER`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user) returns the routine's
`DEFINER` value. This also affects a view defined
within such a routine, if the view definition contains a
`DEFINER` value of
[`CURRENT_USER`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user).


MySQL checks view privileges like this:

- At view definition time, the view creator must have the
privileges needed to use the top-level objects accessed by the
view. For example, if the view definition refers to table
columns, the creator must have some privilege for each column
in the select list of the definition, and the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege for each
column used elsewhere in the definition. If the definition
refers to a stored function, only the privileges needed to
invoke the function can be checked. The privileges required at
function invocation time can be checked only as it executes:
For different invocations, different execution paths within
the function might be taken.


- The user who references a view must have appropriate
privileges to access it ( [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select)
to select from it, [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_insert) to
insert into it, and so forth.)


- When a view has been referenced, privileges for objects
accessed by the view are checked against the privileges held
by the view `DEFINER` account or invoker,
depending on whether the `SQL SECURITY`
characteristic is `DEFINER` or
`INVOKER`, respectively.


- If reference to a view causes execution of a stored function,
privilege checking for statements executed within the function
depend on whether the function `SQL SECURITY`
characteristic is `DEFINER` or
`INVOKER`. If the security characteristic is
`DEFINER`, the function runs with the
privileges of the `DEFINER` account. If the
characteristic is `INVOKER`, the function
runs with the privileges determined by the view's `SQL
            SECURITY` characteristic.


Example: A view might depend on a stored function, and that
function might invoke other stored routines. For example, the
following view invokes a stored function `f()`:


```sql
CREATE VIEW v AS SELECT * FROM t WHERE t.id = f(t.name);
```

Suppose that `f()` contains a statement such as
this:


```sql
IF name IS NULL then
  CALL p1();
ELSE
  CALL p2();
END IF;
```

The privileges required for executing statements within
`f()` need to be checked when
`f()` executes. This might mean that privileges
are needed for `p1()` or `p2()`,
depending on the execution path within `f()`.
Those privileges must be checked at runtime, and the user who must
possess the privileges is determined by the `SQL
      SECURITY` values of the view `v` and the
function `f()`.


The `DEFINER` and `SQL SECURITY`
clauses for views are extensions to standard SQL. In standard SQL,
views are handled using the rules for `SQL SECURITY
      DEFINER`. The standard says that the definer of the view,
which is the same as the owner of the view's schema, gets
applicable privileges on the view (for example,
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select)) and may grant them. MySQL
has no concept of a schema “owner”, so MySQL adds a
clause to identify the definer. The `DEFINER`
clause is an extension where the intent is to have what the
standard has; that is, a permanent record of who defined the view.
This is why the default `DEFINER` value is the
account of the view creator.


The optional `ALGORITHM` clause is a MySQL
extension to standard SQL. It affects how MySQL processes the
view. `ALGORITHM` takes three values:
`MERGE`, `TEMPTABLE`, or
`UNDEFINED`. For more information, see
[Section 27.5.2, “View Processing Algorithms”](https://dev.mysql.com/doc/refman/8.0/en/view-algorithms.html "27.5.2 View Processing Algorithms"), as well as
[Section 10.2.2.4, “Optimizing Derived Tables, View References, and Common Table Expressions\\
with Merging or Materialization”](https://dev.mysql.com/doc/refman/8.0/en/derived-table-optimization.html "10.2.2.4 Optimizing Derived Tables, View References, and Common Table Expressions with Merging or Materialization").


Some views are updatable. That is, you can use them in statements
such as [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"),
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"), or
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") to update the contents of
the underlying table. For a view to be updatable, there must be a
one-to-one relationship between the rows in the view and the rows
in the underlying table. There are also certain other constructs
that make a view nonupdatable.


A generated column in a view is considered updatable because it is
possible to assign to it. However, if such a column is updated
explicitly, the only permitted value is
`DEFAULT`. For information about generated
columns, see [Section 15.1.20.8, “CREATE TABLE and Generated Columns”](https://dev.mysql.com/doc/refman/8.0/en/create-table-generated-columns.html "15.1.20.8 CREATE TABLE and Generated Columns").


The `WITH CHECK OPTION` clause can be given for
an updatable view to prevent inserts or updates to rows except
those for which the `WHERE` clause in the
_`select_statement`_ is true.


In a `WITH CHECK OPTION` clause for an updatable
view, the `LOCAL` and `CASCADED`
keywords determine the scope of check testing when the view is
defined in terms of another view. The `LOCAL`
keyword restricts the `CHECK OPTION` only to the
view being defined. `CASCADED` causes the checks
for underlying views to be evaluated as well. When neither keyword
is given, the default is `CASCADED`.


For more information about updatable views and the `WITH
      CHECK OPTION` clause, see
[Section 27.5.3, “Updatable and Insertable Views”](https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html "27.5.3 Updatable and Insertable Views"), and
[Section 27.5.4, “The View WITH CHECK OPTION Clause”](https://dev.mysql.com/doc/refman/8.0/en/view-check-option.html "27.5.4 The View WITH CHECK OPTION Clause").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "Previous: CREATE TRIGGER Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "Next: DROP DATABASE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/create-view.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-view.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-view.html)

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