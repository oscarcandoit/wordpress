---
url: https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html
scraped_at: 2025-10-20T03:05:08.293Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html "Hide Sidebar")

[Previous: View Processing Algorithms](https://dev.mysql.com/doc/refman/8.0/en/view-algorithms.html "Previous: View Processing Algorithms")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Using Views](https://dev.mysql.com/doc/refman/8.0/en/views.html "Up: Using Views")[Next: The View WITH CHECK OPTION Clause](https://dev.mysql.com/doc/refman/8.0/en/view-check-option.html "Next: The View WITH CHECK OPTION Clause")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/view-updatability.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/view-updatability.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/view-updatability.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/view-updatability.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/view-updatability.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/view-updatability.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/view-updatability.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/view-updatability.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html)  / [Stored Objects](https://dev.mysql.com/doc/refman/8.0/en/stored-objects.html)  /
[Using Views](https://dev.mysql.com/doc/refman/8.0/en/views.html)  /

Updatable and Insertable Views


### 27.5.3 Updatable and Insertable Views

Some views are updatable and references to them can be used to
specify tables to be updated in data change statements. That is,
you can use them in statements such as
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"),
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"), or
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") to update the contents of
the underlying table. Derived tables and common table expressions
can also be specified in multiple-table
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") and
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statements, but can only be
used for reading data to specify rows to be updated or deleted.
Generally, the view references must be updatable, meaning that
they may be merged and not materialized. Composite views have more
complex rules.


For a view to be updatable, there must be a one-to-one
relationship between the rows in the view and the rows in the
underlying table. There are also certain other constructs that
make a view nonupdatable. To be more specific, a view is not
updatable if it contains any of the following:

- Aggregate functions or window functions
( [`SUM()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_sum),
[`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min),
[`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max),
[`COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count), and so forth)


- `DISTINCT`

- `GROUP BY`

- `HAVING`

- [`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause") or
[`UNION ALL`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause")

- Subquery in the select list



Nondependent subqueries in the select list fail for
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"), but are okay for
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"),
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"). For dependent
subqueries in the select list, no data change statements are
permitted.


- Certain joins (see additional join discussion later in this
section)


- Reference to nonupdatable view in the `FROM`
clause


- Subquery in the `WHERE` clause that refers to
a table in the `FROM` clause


- Refers only to literal values (in this case, there is no
underlying table to update)


- `ALGORITHM = TEMPTABLE` (use of a temporary
table always makes a view nonupdatable)


- Multiple references to any column of a base table (fails for
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"), okay for
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"),
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"))


A generated column in a view is considered updatable because it is
possible to assign to it. However, if such a column is updated
explicitly, the only permitted value is
`DEFAULT`. For information about generated
columns, see [Section 15.1.20.8, “CREATE TABLE and Generated Columns”](https://dev.mysql.com/doc/refman/8.0/en/create-table-generated-columns.html "15.1.20.8 CREATE TABLE and Generated Columns").


It is sometimes possible for a multiple-table view to be
updatable, assuming that it can be processed with the
`MERGE` algorithm. For this to work, the view
must use an inner join (not an outer join or a
[`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause")). Also, only a single table
in the view definition can be updated, so the
`SET` clause must name only columns from one of
the tables in the view. Views that use
[`UNION ALL`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause") are not
permitted even though they might be theoretically updatable.


With respect to insertability (being updatable with
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements), an updatable
view is insertable if it also satisfies these additional
requirements for the view columns:

- There must be no duplicate view column names.


- The view must contain all columns in the base table that do
not have a default value.


- The view columns must be simple column references. They must
not be expressions, such as these:



```sql
3.14159
col1 + 3
UPPER(col2)
col3 / col4
(subquery)
```


MySQL sets a flag, called the view updatability flag, at
[`CREATE VIEW`](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "15.1.23 CREATE VIEW Statement") time. The flag is set
to `YES` (true) if
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") and
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") (and similar operations) are
legal for the view. Otherwise, the flag is set to
`NO` (false). The `IS_UPDATABLE`
column in the Information Schema
[`VIEWS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-views-table.html "28.3.48 The INFORMATION_SCHEMA VIEWS Table") table displays the status of
this flag. It means that the server always knows whether a view is
updatable.


If a view is not updatable, statements such
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"),
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"), and
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") are illegal and are
rejected. (Even if a view is updatable, it might not be possible
to insert into it, as described elsewhere in this section.)


The updatability of views may be affected by the value of the
[`updatable_views_with_limit`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_updatable_views_with_limit) system
variable. See [Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables").


For the following discussion, suppose that these tables and views
exist:


```sql
CREATE TABLE t1 (x INTEGER);
CREATE TABLE t2 (c INTEGER);
CREATE VIEW vmat AS SELECT SUM(x) AS s FROM t1;
CREATE VIEW vup AS SELECT * FROM t2;
CREATE VIEW vjoin AS SELECT * FROM vmat JOIN vup ON vmat.s=vup.c;
```

[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"),
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"), and
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statements are permitted as
follows:

- [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"): The insert table of an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement may be a view
reference that is merged. If the view is a join view, all
components of the view must be updatable (not materialized).
For a multiple-table updatable view,
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") can work if it inserts
into a single table.



This statement is invalid because one component of the join
view is nonupdatable:



```sql
INSERT INTO vjoin (c) VALUES (1);
```



This statement is valid; the view contains no materialized
components:



```sql
INSERT INTO vup (c) VALUES (1);
```

- [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"): The table or tables to
be updated in an [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement")
statement may be view references that are merged. If a view is
a join view, at least one component of the view must be
updatable (this differs from
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement")).



In a multiple-table [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement")
statement, the updated table references of the statement must
be base tables or updatable view references. Nonupdated table
references may be materialized views or derived tables.



This statement is valid; column `c` is from
the updatable part of the join view:



```sql
UPDATE vjoin SET c=c+1;
```



This statement is invalid; column `x` is from
the nonupdatable part:



```sql
UPDATE vjoin SET x=x+1;
```



This statement is valid; the updated table reference of the
multiple-table [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") is an
updatable view ( `vup`):



```sql
UPDATE vup JOIN (SELECT SUM(x) AS s FROM t1) AS dt ON ...
SET c=c+1;
```



This statement is invalid; it tries to update a materialized
derived table:



```sql
UPDATE vup JOIN (SELECT SUM(x) AS s FROM t1) AS dt ON ...
SET s=s+1;
```

- [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"): The table or tables to
be deleted from in a [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement")
statement must be merged views. Join views are not allowed
(this differs from [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") and
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement")).



This statement is invalid because the view is a join view:



```sql
DELETE vjoin WHERE ...;
```



This statement is valid because the view is a merged
(updatable) view:



```sql
DELETE vup WHERE ...;
```



This statement is valid because it deletes from a merged
(updatable) view:



```sql
DELETE vup FROM vup JOIN (SELECT SUM(x) AS s FROM t1) AS dt ON ...;
```


Additional discussion and examples follow.


Earlier discussion in this section pointed out that a view is not
insertable if not all columns are simple column references (for
example, if it contains columns that are expressions or composite
expressions). Although such a view is not insertable, it can be
updatable if you update only columns that are not expressions.
Consider this view:


```sql
CREATE VIEW v AS SELECT col1, 1 AS col2 FROM t;
```

This view is not insertable because `col2` is an
expression. But it is updatable if the update does not try to
update `col2`. This update is permissible:


```sql
UPDATE v SET col1 = 0;
```

This update is not permissible because it attempts to update an
expression column:


```sql
UPDATE v SET col2 = 0;
```

If a table contains an `AUTO_INCREMENT` column,
inserting into an insertable view on the table that does not
include the `AUTO_INCREMENT` column does not
change the value of
[`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id), because the side
effects of inserting default values into columns not part of the
view should not be visible.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/view-algorithms.html "Previous: View Processing Algorithms") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/views.html "Up: Using Views") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/view-check-option.html "Next: The View WITH CHECK OPTION Clause")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/view-updatability.html)

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