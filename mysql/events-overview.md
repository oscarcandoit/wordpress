---
url: https://dev.mysql.com/doc/refman/8.0/en/events-overview.html
scraped_at: 2025-10-20T03:06:17.376Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/events-overview.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/events-overview.html "Hide Sidebar")

[Previous: Using the Event Scheduler](https://dev.mysql.com/doc/refman/8.0/en/event-scheduler.html "Previous: Using the Event Scheduler")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Using the Event Scheduler](https://dev.mysql.com/doc/refman/8.0/en/event-scheduler.html "Up: Using the Event Scheduler")[Next: Event Scheduler Configuration](https://dev.mysql.com/doc/refman/8.0/en/events-configuration.html "Next: Event Scheduler Configuration")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/events-overview.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/events-overview.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/events-overview.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/events-overview.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/events-overview.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/events-overview.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/events-overview.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/events-overview.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/events-overview.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/events-overview.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/events-overview.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/events-overview.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/events-overview.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/events-overview.html)  / [Stored Objects](https://dev.mysql.com/doc/refman/8.0/en/stored-objects.html)  /
[Using the Event Scheduler](https://dev.mysql.com/doc/refman/8.0/en/event-scheduler.html)  /

Event Scheduler Overview


### 27.4.1 Event Scheduler Overview

MySQL Events are tasks that run according to a schedule.
Therefore, we sometimes refer to them as
_scheduled_ events. When you create an event,
you are creating a named database object containing one or more
SQL statements to be executed at one or more regular intervals,
beginning and ending at a specific date and time. Conceptually,
this is similar to the idea of the Unix `crontab`
(also known as a “cron job”) or the Windows Task
Scheduler.


Scheduled tasks of this type are also sometimes known as
“temporal triggers”, implying that these are objects
that are triggered by the passage of time. While this is
essentially correct, we prefer to use the term
_events_ to avoid confusion with triggers of
the type discussed in [Section 27.3, “Using Triggers”](https://dev.mysql.com/doc/refman/8.0/en/triggers.html "27.3 Using Triggers"). Events should
more specifically not be confused with “temporary
triggers”. Whereas a trigger is a database object whose
statements are executed in response to a specific type of event
that occurs on a given table, a (scheduled) event is an object
whose statements are executed in response to the passage of a
specified time interval.


While there is no provision in the SQL Standard for event
scheduling, there are precedents in other database systems, and
you may notice some similarities between these implementations and
that found in the MySQL Server.


MySQL Events have the following major features and properties:

- In MySQL, an event is uniquely identified by its name and the
schema to which it is assigned.


- An event performs a specific action according to a schedule.
This action consists of an SQL statement, which can be a
compound statement in a
[`BEGIN ...\\
            END`](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement") block if desired (see
[Section 15.6, “Compound Statement Syntax”](https://dev.mysql.com/doc/refman/8.0/en/sql-compound-statements.html "15.6 Compound Statement Syntax")). An event's timing
can be either one-time
or recurrent. A one-time
event executes one time only. A recurrent event repeats its
action at a regular interval, and the schedule for a recurring
event can be assigned a specific start day and time, end day
and time, both, or neither. (By default, a recurring event's
schedule begins as soon as it is created, and continues
indefinitely, until it is disabled or dropped.)



If a repeating event does not terminate within its scheduling
interval, the result may be multiple instances of the event
executing simultaneously. If this is undesirable, you should
institute a mechanism to prevent simultaneous instances. For
example, you could use the
[`GET_LOCK()`](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html#function_get-lock) function, or row or
table locking.


- Users can create, modify, and drop scheduled events using SQL
statements intended for these purposes. Syntactically invalid
event creation and modification statements fail with an
appropriate error message. _A user may include_
_statements in an event's action which require privileges that_
_the user does not actually have_. The event creation
or modification statement succeeds but the event's action
fails. See [Section 27.4.6, “The Event Scheduler and MySQL Privileges”](https://dev.mysql.com/doc/refman/8.0/en/events-privileges.html "27.4.6 The Event Scheduler and MySQL Privileges") for details.


- Many of the properties of an event can be set or modified
using SQL statements. These properties include the event's
name, timing, persistence (that is, whether it is preserved
following the expiration of its schedule), status (enabled or
disabled), action to be performed, and the schema to which it
is assigned. See [Section 15.1.3, “ALTER EVENT Statement”](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement").



The default definer of an event is the user who created the
event, unless the event has been altered, in which case the
definer is the user who issued the last
[`ALTER EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") statement affecting
that event. An event can be modified by any user having the
[`EVENT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_event) privilege on the database
for which the event is defined. See
[Section 27.4.6, “The Event Scheduler and MySQL Privileges”](https://dev.mysql.com/doc/refman/8.0/en/events-privileges.html "27.4.6 The Event Scheduler and MySQL Privileges").


- An event's action statement may include most SQL statements
permitted within stored routines. For restrictions, see
[Section 27.8, “Restrictions on Stored Programs”](https://dev.mysql.com/doc/refman/8.0/en/stored-program-restrictions.html "27.8 Restrictions on Stored Programs").


[PREV](https://dev.mysql.com/doc/refman/8.0/en/event-scheduler.html "Previous: Using the Event Scheduler") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/event-scheduler.html "Up: Using the Event Scheduler") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/events-configuration.html "Next: Event Scheduler Configuration")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/events-overview.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/events-overview.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/events-overview.html)

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