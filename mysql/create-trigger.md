---
url: https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html
scraped_at: 2025-10-20T03:05:37.004Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "Hide Sidebar")

[Previous: CREATE TABLESPACE Statement](https://dev.mysql.com/doc/refman/8.0/en/create-tablespace.html "Previous: CREATE TABLESPACE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements")[Next: CREATE VIEW Statement](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "Next: CREATE VIEW Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/create-trigger.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/create-trigger.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/create-trigger.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/create-trigger.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/create-trigger.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/create-trigger.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/create-trigger.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/create-trigger.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html)  /

CREATE TRIGGER Statement


### 15.1.22 CREATE TRIGGER Statement

```sql
CREATE
    [DEFINER = user]
    TRIGGER [IF NOT EXISTS] trigger_name
    trigger_time trigger_event
    ON tbl_name FOR EACH ROW
    [trigger_order]
    trigger_body

trigger_time: { BEFORE | AFTER }

trigger_event: { INSERT | UPDATE | DELETE }

trigger_order: { FOLLOWS | PRECEDES } other_trigger_name
```

This statement creates a new trigger. A trigger is a named
database object that is associated with a table, and that
activates when a particular event occurs for the table. The
trigger becomes associated with the table named
_`tbl_name`_, which must refer to a
permanent table. You cannot associate a trigger with a
`TEMPORARY` table or a view.


Trigger names exist in the schema namespace, meaning that all
triggers must have unique names within a schema. Triggers in
different schemas can have the same name.


`IF NOT EXISTS` prevents an error from occurring
if a trigger having the same name, on the same table, exists in
the same schema. This option is supported with `CREATE
      TRIGGER` beginning with MySQL 8.0.29.


This section describes [`CREATE\\
      TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "15.1.22 CREATE TRIGGER Statement") syntax. For additional discussion, see
[Section 27.3.1, “Trigger Syntax and Examples”](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html "27.3.1 Trigger Syntax and Examples").


[`CREATE TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "15.1.22 CREATE TRIGGER Statement") requires the
[`TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_trigger) privilege for the table
associated with the trigger. If the `DEFINER`
clause is present, the privileges required depend on the
_`user`_ value, as discussed in
[Section 27.6, “Stored Object Access Control”](https://dev.mysql.com/doc/refman/8.0/en/stored-objects-security.html "27.6 Stored Object Access Control"). If binary logging is
enabled, [`CREATE TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "15.1.22 CREATE TRIGGER Statement") might
require the [`SUPER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_super) privilege, as
discussed in [Section 27.7, “Stored Program Binary Logging”](https://dev.mysql.com/doc/refman/8.0/en/stored-programs-logging.html "27.7 Stored Program Binary Logging").


The `DEFINER` clause determines the security
context to be used when checking access privileges at trigger
activation time, as described later in this section.


_`trigger_time`_ is the trigger action
time. It can be `BEFORE` or
`AFTER` to indicate that the trigger activates
before or after each row to be modified.


Basic column value checks occur prior to trigger activation, so
you cannot use `BEFORE` triggers to convert
values inappropriate for the column type to valid values.


_`trigger_event`_ indicates the kind of
operation that activates the trigger. These
_`trigger_event`_ values are permitted:

- [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"): The trigger activates
whenever a new row is inserted into the table (for example,
through [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"),
[`LOAD DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement"), and
[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") statements).


- [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"): The trigger activates
whenever a row is modified (for example, through
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statements).


- [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"): The trigger activates
whenever a row is deleted from the table (for example, through
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") and
[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") statements).
[`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") and
[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") statements on
the table do _not_ activate this trigger,
because they do not use [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement").
Dropping a partition does not activate
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") triggers, either.


The _`trigger_event`_ does not represent a
literal type of SQL statement that activates the trigger so much
as it represents a type of table operation. For example, an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") trigger activates not only
for [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements but also
[`LOAD DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement") statements because both
statements insert rows into a table.


A potentially confusing example of this is the `INSERT
      INTO ... ON DUPLICATE KEY UPDATE ...` syntax: a
`BEFORE INSERT` trigger activates for every row,
followed by either an `AFTER INSERT` trigger or
both the `BEFORE UPDATE` and `AFTER
      UPDATE` triggers, depending on whether there was a
duplicate key for the row.

Note

Cascaded foreign key actions do not activate triggers.

It is possible to define multiple triggers for a given table that
have the same trigger event and action time. For example, you can
have two `BEFORE UPDATE` triggers for a table. By
default, triggers that have the same trigger event and action time
activate in the order they were created. To affect trigger order,
specify a _`trigger_order`_ clause that
indicates `FOLLOWS` or
`PRECEDES` and the name of an existing trigger
that also has the same trigger event and action time. With
`FOLLOWS`, the new trigger activates after the
existing trigger. With `PRECEDES`, the new
trigger activates before the existing trigger.


_`trigger_body`_ is the statement to
execute when the trigger activates. To execute multiple
statements, use the
[`BEGIN ... END`](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement")
compound statement construct. This also enables you to use the
same statements that are permitted within stored routines. See
[Section 15.6.1, “BEGIN ... END Compound Statement”](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement"). Some statements are not permitted in
triggers; see [Section 27.8, “Restrictions on Stored Programs”](https://dev.mysql.com/doc/refman/8.0/en/stored-program-restrictions.html "27.8 Restrictions on Stored Programs").


Within the trigger body, you can refer to columns in the subject
table (the table associated with the trigger) by using the aliases
`OLD` and `NEW`.
`OLD.col_name` refers
to a column of an existing row before it is updated or deleted.
`NEW.col_name` refers
to the column of a new row to be inserted or an existing row after
it is updated.


Triggers cannot use
`NEW.col_name` or use
`OLD.col_name` to
refer to generated columns. For information about generated
columns, see [Section 15.1.20.8, “CREATE TABLE and Generated Columns”](https://dev.mysql.com/doc/refman/8.0/en/create-table-generated-columns.html "15.1.20.8 CREATE TABLE and Generated Columns").


MySQL stores the [`sql_mode`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_sql_mode) system
variable setting in effect when a trigger is created, and always
executes the trigger body with this setting in force,
_regardless of the current server SQL mode when the_
_trigger begins executing_.


The `DEFINER` clause specifies the MySQL account
to be used when checking access privileges at trigger activation
time. If the `DEFINER` clause is present, the
_`user`_ value should be a MySQL account
specified as
`'user_name'@'host_name'`,
[`CURRENT_USER`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user), or
[`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user). The permitted
_`user`_ values depend on the privileges
you hold, as discussed in
[Section 27.6, “Stored Object Access Control”](https://dev.mysql.com/doc/refman/8.0/en/stored-objects-security.html "27.6 Stored Object Access Control"). Also see that section
for additional information about trigger security.


If the `DEFINER` clause is omitted, the default
definer is the user who executes the [`CREATE\\
      TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "15.1.22 CREATE TRIGGER Statement") statement. This is the same as specifying
`DEFINER = CURRENT_USER` explicitly.


MySQL takes the `DEFINER` user into account when
checking trigger privileges as follows:

- At [`CREATE TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "15.1.22 CREATE TRIGGER Statement") time, the
user who issues the statement must have the
[`TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_trigger) privilege.


- At trigger activation time, privileges are checked against the
`DEFINER` user. This user must have these
privileges:




- The [`TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_trigger) privilege for
the subject table.


- The [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege for
the subject table if references to table columns occur
using
`OLD.col_name`
or
`NEW.col_name`
in the trigger body.


- The [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_update) privilege for
the subject table if table columns are targets of
`SET NEW.col_name =
                value` assignments in
the trigger body.


- Whatever other privileges normally are required for the
statements executed by the trigger.


Within a trigger body, the
[`CURRENT_USER`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user) function returns the
account used to check privileges at trigger activation time. This
is the `DEFINER` user, not the user whose actions
caused the trigger to be activated. For information about user
auditing within triggers, see
[Section 8.2.23, “SQL-Based Account Activity Auditing”](https://dev.mysql.com/doc/refman/8.0/en/account-activity-auditing.html "8.2.23 SQL-Based Account Activity Auditing").


If you use [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") to lock a
table that has triggers, the tables used within the trigger are
also locked, as described in
[LOCK TABLES and Triggers](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html#lock-tables-and-triggers "LOCK TABLES and Triggers").


For additional discussion of trigger use, see
[Section 27.3.1, “Trigger Syntax and Examples”](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html "27.3.1 Trigger Syntax and Examples").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/create-tablespace.html "Previous: CREATE TABLESPACE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "Next: CREATE VIEW Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html)

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