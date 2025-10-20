---
url: https://dev.mysql.com/doc/refman/8.0/en/create-event.html
scraped_at: 2025-10-20T03:05:55.245Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/create-event.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "Hide Sidebar")

[Previous: CREATE DATABASE Statement](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "Previous: CREATE DATABASE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements")[Next: CREATE FUNCTION Statement](https://dev.mysql.com/doc/refman/8.0/en/create-function.html "Next: CREATE FUNCTION Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/create-event.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-event.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-event.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/create-event.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/create-event.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/create-event.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/create-event.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/create-event.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/create-event.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/create-event.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/create-event.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/create-event.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/create-event.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html)  /

CREATE EVENT Statement


### 15.1.13 CREATE EVENT Statement

```sql
CREATE
    [DEFINER = user]
    EVENT
    [IF NOT EXISTS]
    event_name
    ON SCHEDULE schedule
    [ON COMPLETION [NOT] PRESERVE]
    [ENABLE | DISABLE | DISABLE ON SLAVE]
    [COMMENT 'string']
    DO event_body;

schedule: {
    AT timestamp [+ INTERVAL interval] ...
  | EVERY interval
    [STARTS timestamp [+ INTERVAL interval] ...]
    [ENDS timestamp [+ INTERVAL interval] ...]
}

interval:
    quantity {YEAR | QUARTER | MONTH | DAY | HOUR | MINUTE |
              WEEK | SECOND | YEAR_MONTH | DAY_HOUR | DAY_MINUTE |
              DAY_SECOND | HOUR_MINUTE | HOUR_SECOND | MINUTE_SECOND}
```

This statement creates and schedules a new event. The event does
not run unless the Event Scheduler is enabled. For information
about checking Event Scheduler status and enabling it if
necessary, see [Section 27.4.2, “Event Scheduler Configuration”](https://dev.mysql.com/doc/refman/8.0/en/events-configuration.html "27.4.2 Event Scheduler Configuration").


[`CREATE EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement") requires the
[`EVENT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_event) privilege for the schema in
which the event is to be created. If the
`DEFINER` clause is present, the privileges
required depend on the _`user`_ value, as
discussed in [Section 27.6, “Stored Object Access Control”](https://dev.mysql.com/doc/refman/8.0/en/stored-objects-security.html "27.6 Stored Object Access Control").


The minimum requirements for a valid [`CREATE\\
      EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement") statement are as follows:

- The keywords [`CREATE EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement") plus
an event name, which uniquely identifies the event in a
database schema.


- An `ON SCHEDULE` clause, which determines
when and how often the event executes.


- A [`DO`](https://dev.mysql.com/doc/refman/8.0/en/do.html "15.2.3 DO Statement") clause, which contains the
SQL statement to be executed by an event.


This is an example of a minimal [`CREATE\\
      EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement") statement:


```sql
CREATE EVENT myevent
    ON SCHEDULE AT CURRENT_TIMESTAMP + INTERVAL 1 HOUR
    DO
      UPDATE myschema.mytable SET mycol = mycol + 1;
```

The previous statement creates an event named
`myevent`. This event executes once—one
hour following its creation—by running an SQL statement that
increments the value of the `myschema.mytable`
table's `mycol` column by 1.


The _`event_name`_ must be a valid MySQL
identifier with a maximum length of 64 characters. Event names are
not case-sensitive, so you cannot have two events named
`myevent` and `MyEvent` in the
same schema. In general, the rules governing event names are the
same as those for names of stored routines. See
[Section 11.2, “Schema Object Names”](https://dev.mysql.com/doc/refman/8.0/en/identifiers.html "11.2 Schema Object Names").


An event is associated with a schema. If no schema is indicated as
part of _`event_name`_, the default
(current) schema is assumed. To create an event in a specific
schema, qualify the event name with a schema using
`schema_name.event_name`
syntax.


The `DEFINER` clause specifies the MySQL account
to be used when checking access privileges at event execution
time. If the `DEFINER` clause is present, the
_`user`_ value should be a MySQL account
specified as
`'user_name'@'host_name'`,
[`CURRENT_USER`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user), or
[`CURRENT_USER()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user). The permitted
_`user`_ values depend on the privileges
you hold, as discussed in
[Section 27.6, “Stored Object Access Control”](https://dev.mysql.com/doc/refman/8.0/en/stored-objects-security.html "27.6 Stored Object Access Control"). Also see that section
for additional information about event security.


If the `DEFINER` clause is omitted, the default
definer is the user who executes the [`CREATE\\
      EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement") statement. This is the same as specifying
`DEFINER = CURRENT_USER` explicitly.


Within an event body, the
[`CURRENT_USER`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_current-user) function returns the
account used to check privileges at event execution time, which is
the `DEFINER` user. For information about user
auditing within events, see
[Section 8.2.23, “SQL-Based Account Activity Auditing”](https://dev.mysql.com/doc/refman/8.0/en/account-activity-auditing.html "8.2.23 SQL-Based Account Activity Auditing").


`IF NOT EXISTS` has the same meaning for
[`CREATE EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement") as for
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"): If an event named
_`event_name`_ already exists in the same
schema, no action is taken, and no error results. (However, a
warning is generated in such cases.)


The `ON SCHEDULE` clause determines when, how
often, and for how long the _`event_body`_
defined for the event repeats. This clause takes one of two forms:

- `AT timestamp` is
used for a one-time event. It specifies that the event
executes one time only at the date and time given by
_`timestamp`_, which must include both
the date and time, or must be an expression that resolves to a
datetime value. You may use a value of either the
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") or
[`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") type for this
purpose. If the date is in the past, a warning occurs, as
shown here:



```sql
mysql> SELECT NOW();
+---------------------+
| NOW()               |
+---------------------+
| 2006-02-10 23:59:01 |
+---------------------+
1 row in set (0.04 sec)

mysql> CREATE EVENT e_totals
      ->     ON SCHEDULE AT '2006-02-10 23:59:00'
      ->     DO INSERT INTO test.totals VALUES (NOW());
Query OK, 0 rows affected, 1 warning (0.00 sec)

mysql> SHOW WARNINGS\G
*************************** 1. row ***************************
    Level: Note
     Code: 1588
Message: Event execution time is in the past and ON COMPLETION NOT
           PRESERVE is set. The event was dropped immediately after
           creation.
```


[`CREATE EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement") statements which
are themselves invalid—for whatever reason—fail
with an error.



You may use [`CURRENT_TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_current-timestamp)
to specify the current date and time. In such a case, the
event acts as soon as it is created.



To create an event which occurs at some point in the future
relative to the current date and time—such as that
expressed by the phrase “three weeks from
now”—you can use the optional clause `+
            INTERVAL interval`. The
_`interval`_ portion consists of two
parts, a quantity and a unit of time, and follows the syntax
rules described in [Temporal Intervals](https://dev.mysql.com/doc/refman/8.0/en/expressions.html#temporal-intervals "Temporal Intervals"),
except that you cannot use any units keywords that involving
microseconds when defining an event. With some interval types,
complex time units may be used. For example, “two
minutes and ten seconds” can be expressed as `+
            INTERVAL '2:10' MINUTE_SECOND`.



You can also combine intervals. For example, `AT
            CURRENT_TIMESTAMP + INTERVAL 3 WEEK + INTERVAL 2 DAY`
is equivalent to “three weeks and two days from
now”. Each portion of such a clause must begin with
`+ INTERVAL`.


- To repeat actions at a regular interval, use an
`EVERY` clause. The `EVERY`
keyword is followed by an _`interval`_
as described in the previous discussion of the
`AT` keyword. ( `+ INTERVAL`
is _not_ used with
`EVERY`.) For example, `EVERY 6
            WEEK` means “every six weeks”.



Although `+ INTERVAL` clauses are not
permitted in an `EVERY` clause, you can use
the same complex time units permitted in a `+
            INTERVAL`.



An `EVERY` clause may contain an optional
`STARTS` clause. `STARTS` is
followed by a _`timestamp`_ value that
indicates when the action should begin repeating, and may also
use `+ INTERVAL
            interval` to specify an
amount of time “from now”. For example,
`EVERY 3 MONTH STARTS CURRENT_TIMESTAMP + INTERVAL 1
            WEEK` means “every three months, beginning one
week from now”. Similarly, you can express “every
two weeks, beginning six hours and fifteen minutes from
now” as `EVERY 2 WEEK STARTS CURRENT_TIMESTAMP
            + INTERVAL '6:15' HOUR_MINUTE`. Not specifying
`STARTS` is the same as using `STARTS
            CURRENT_TIMESTAMP`—that is, the action
specified for the event begins repeating immediately upon
creation of the event.



An `EVERY` clause may contain an optional
`ENDS` clause. The `ENDS`
keyword is followed by a _`timestamp`_
value that tells MySQL when the event should stop repeating.
You may also use `+ INTERVAL
            interval` with
`ENDS`; for instance, `EVERY 12 HOUR
            STARTS CURRENT_TIMESTAMP + INTERVAL 30 MINUTE ENDS
            CURRENT_TIMESTAMP + INTERVAL 4 WEEK` is equivalent to
“every twelve hours, beginning thirty minutes from now,
and ending four weeks from now”. Not using
`ENDS` means that the event continues
executing indefinitely.


`ENDS` supports the same syntax for complex
time units as `STARTS` does.



You may use `STARTS`,
`ENDS`, both, or neither in an
`EVERY` clause.



If a repeating event does not terminate within its scheduling
interval, the result may be multiple instances of the event
executing simultaneously. If this is undesirable, you should
institute a mechanism to prevent simultaneous instances. For
example, you could use the
[`GET_LOCK()`](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html#function_get-lock) function, or row or
table locking.


The `ON SCHEDULE` clause may use expressions
involving built-in MySQL functions and user variables to obtain
any of the _`timestamp`_ or
_`interval`_ values which it contains. You
may not use stored functions or loadable functions in such
expressions, nor may you use any table references; however, you
may use `SELECT FROM DUAL`. This is true for both
[`CREATE EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement") and
[`ALTER EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") statements. References
to stored functions, loadable functions, and tables in such cases
are specifically not permitted, and fail with an error (see Bug
#22830).


Times in the `ON SCHEDULE` clause are interpreted
using the current session
[`time_zone`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_time_zone) value. This becomes the
event time zone; that is, the time zone that is used for event
scheduling and is in effect within the event as it executes. These
times are converted to UTC and stored along with the event time
zone internally. This enables event execution to proceed as
defined regardless of any subsequent changes to the server time
zone or daylight saving time effects. For additional information
about representation of event times, see
[Section 27.4.4, “Event Metadata”](https://dev.mysql.com/doc/refman/8.0/en/events-metadata.html "27.4.4 Event Metadata"). See also
[Section 15.7.7.18, “SHOW EVENTS Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-events.html "15.7.7.18 SHOW EVENTS Statement"), and
[Section 28.3.14, “The INFORMATION\_SCHEMA EVENTS Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-events-table.html "28.3.14 The INFORMATION_SCHEMA EVENTS Table").


Normally, once an event has expired, it is immediately dropped.
You can override this behavior by specifying `ON
      COMPLETION PRESERVE`. Using `ON COMPLETION NOT
      PRESERVE` merely makes the default nonpersistent behavior
explicit.


You can create an event but prevent it from being active using the
`DISABLE` keyword. Alternatively, you can use
`ENABLE` to make explicit the default status,
which is active. This is most useful in conjunction with
[`ALTER EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") (see
[Section 15.1.3, “ALTER EVENT Statement”](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement")).


A third value may also appear in place of
`ENABLE` or `DISABLE`;
`DISABLE ON SLAVE` is set for the status of an
event on a replica to indicate that the event was created on the
replication source server and replicated to the replica, but is
not executed on the replica. See
[Section 19.5.1.16, “Replication of Invoked Features”](https://dev.mysql.com/doc/refman/8.0/en/replication-features-invoked.html "19.5.1.16 Replication of Invoked Features").


You may supply a comment for an event using a
`COMMENT` clause.
_`comment`_ may be any string of up to 64
characters that you wish to use for describing the event. The
comment text, being a string literal, must be surrounded by
quotation marks.


The [`DO`](https://dev.mysql.com/doc/refman/8.0/en/do.html "15.2.3 DO Statement") clause specifies an action
carried by the event, and consists of an SQL statement. Nearly any
valid MySQL statement that can be used in a stored routine can
also be used as the action statement for a scheduled event. (See
[Section 27.8, “Restrictions on Stored Programs”](https://dev.mysql.com/doc/refman/8.0/en/stored-program-restrictions.html "27.8 Restrictions on Stored Programs").) For example, the
following event `e_hourly` deletes all rows from
the `sessions` table once per hour, where this
table is part of the `site_activity` schema:


```sql
CREATE EVENT e_hourly
    ON SCHEDULE
      EVERY 1 HOUR
    COMMENT 'Clears out sessions table each hour.'
    DO
      DELETE FROM site_activity.sessions;
```

MySQL stores the [`sql_mode`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_sql_mode) system
variable setting in effect when an event is created or altered,
and always executes the event with this setting in force,
_regardless of the current server SQL mode when the event_
_begins executing_.


A [`CREATE EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement") statement that
contains an [`ALTER EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") statement
in its [`DO`](https://dev.mysql.com/doc/refman/8.0/en/do.html "15.2.3 DO Statement") clause appears to
succeed; however, when the server attempts to execute the
resulting scheduled event, the execution fails with an error.

Note

Statements such as [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") or
[`SHOW`](https://dev.mysql.com/doc/refman/8.0/en/show.html "15.7.7 SHOW Statements") that merely return a result
set have no effect when used in an event; the output from these
is not sent to the MySQL Monitor, nor is it stored anywhere.
However, you can use statements such as
[`SELECT ...\\
        INTO`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") and
[`INSERT INTO ...\\
        SELECT`](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement") that store a result. (See the next example in
this section for an instance of the latter.)

The schema to which an event belongs is the default schema for
table references in the [`DO`](https://dev.mysql.com/doc/refman/8.0/en/do.html "15.2.3 DO Statement") clause.
Any references to tables in other schemas must be qualified with
the proper schema name.


As with stored routines, you can use compound-statement syntax in
the [`DO`](https://dev.mysql.com/doc/refman/8.0/en/do.html "15.2.3 DO Statement") clause by using the
`BEGIN` and `END` keywords, as
shown here:


```sql
delimiter |

CREATE EVENT e_daily
    ON SCHEDULE
      EVERY 1 DAY
    COMMENT 'Saves total number of sessions then clears the table each day'
    DO
      BEGIN
        INSERT INTO site_activity.totals (time, total)
          SELECT CURRENT_TIMESTAMP, COUNT(*)
            FROM site_activity.sessions;
        DELETE FROM site_activity.sessions;
      END |

delimiter ;
```

This example uses the `delimiter` command to
change the statement delimiter. See
[Section 27.1, “Defining Stored Programs”](https://dev.mysql.com/doc/refman/8.0/en/stored-programs-defining.html "27.1 Defining Stored Programs").


More complex compound statements, such as those used in stored
routines, are possible in an event. This example uses local
variables, an error handler, and a flow control construct:


```sql
delimiter |

CREATE EVENT e
    ON SCHEDULE
      EVERY 5 SECOND
    DO
      BEGIN
        DECLARE v INTEGER;
        DECLARE CONTINUE HANDLER FOR SQLEXCEPTION BEGIN END;

        SET v = 0;

        WHILE v < 5 DO
          INSERT INTO t1 VALUES (0);
          UPDATE t2 SET s1 = s1 + 1;
          SET v = v + 1;
        END WHILE;
    END |

delimiter ;
```

There is no way to pass parameters directly to or from events;
however, it is possible to invoke a stored routine with parameters
within an event:


```sql
CREATE EVENT e_call_myproc
    ON SCHEDULE
      AT CURRENT_TIMESTAMP + INTERVAL 1 DAY
    DO CALL myproc(5, 27);
```

If an event's definer has privileges sufficient to set global
system variables (see
[Section 7.1.9.1, “System Variable Privileges”](https://dev.mysql.com/doc/refman/8.0/en/system-variable-privileges.html "7.1.9.1 System Variable Privileges")), the event can read
and write global variables. As granting such privileges entails a
potential for abuse, extreme care must be taken in doing so.


Generally, any statements that are valid in stored routines may be
used for action statements executed by events. For more
information about statements permissible within stored routines,
see [Section 27.2.1, “Stored Routine Syntax”](https://dev.mysql.com/doc/refman/8.0/en/stored-routines-syntax.html "27.2.1 Stored Routine Syntax"). It is not possible
to create an event as part of a stored routine or to create an
event by another event.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "Previous: CREATE DATABASE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/create-function.html "Next: CREATE FUNCTION Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/create-event.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-event.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-event.html)

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