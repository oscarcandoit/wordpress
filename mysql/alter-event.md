---
url: https://dev.mysql.com/doc/refman/8.0/en/alter-event.html
scraped_at: 2025-10-20T03:06:03.864Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "Hide Sidebar")

[Previous: ALTER DATABASE Statement](https://dev.mysql.com/doc/refman/8.0/en/alter-database.html "Previous: ALTER DATABASE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements")[Next: ALTER FUNCTION Statement](https://dev.mysql.com/doc/refman/8.0/en/alter-function.html "Next: ALTER FUNCTION Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/alter-event.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/alter-event.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/alter-event.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/alter-event.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/alter-event.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/alter-event.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/alter-event.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/alter-event.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Definition Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html)  /

ALTER EVENT Statement


### 15.1.3 ALTER EVENT Statement

``` sql

ALTER
    [DEFINER = user]
    EVENT event_name
    [ON SCHEDULE schedule]
    [ON COMPLETION [NOT] PRESERVE]
    [RENAME TO new_event_name]
    [ENABLE | DISABLE | DISABLE ON SLAVE]
    [COMMENT 'string']
    [DO event_body]
```

The [`ALTER EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") statement changes
one or more of the characteristics of an existing event without
the need to drop and recreate it. The syntax for each of the
`DEFINER`, `ON SCHEDULE`,
`ON COMPLETION`, `COMMENT`,
`ENABLE` / `DISABLE`, and
[`DO`](https://dev.mysql.com/doc/refman/8.0/en/do.html "15.2.3 DO Statement") clauses is exactly the same as
when used with [`CREATE EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement"). (See
[Section 15.1.13, “CREATE EVENT Statement”](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement").)


Any user can alter an event defined on a database for which that
user has the [`EVENT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_event) privilege. When
a user executes a successful [`ALTER\\
      EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") statement, that user becomes the definer for the
affected event.


[`ALTER EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") works only with an
existing event:


``` sql

mysql> ALTER EVENT no_such_event
     >     ON SCHEDULE
     >       EVERY '2:3' DAY_HOUR;
ERROR 1517 (HY000): Unknown event 'no_such_event'
```

In each of the following examples, assume that the event named
`myevent` is defined as shown here:


``` sql

CREATE EVENT myevent
    ON SCHEDULE
      EVERY 6 HOUR
    COMMENT 'A sample comment.'
    DO
      UPDATE myschema.mytable SET mycol = mycol + 1;
```

The following statement changes the schedule for
`myevent` from once every six hours starting
immediately to once every twelve hours, starting four hours from
the time the statement is run:


``` sql

ALTER EVENT myevent
    ON SCHEDULE
      EVERY 12 HOUR
    STARTS CURRENT_TIMESTAMP + INTERVAL 4 HOUR;
```

It is possible to change multiple characteristics of an event in a
single statement. This example changes the SQL statement executed
by `myevent` to one that deletes all records from
`mytable`; it also changes the schedule for the
event such that it executes once, one day after this
[`ALTER EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") statement is run.


``` sql

ALTER EVENT myevent
    ON SCHEDULE
      AT CURRENT_TIMESTAMP + INTERVAL 1 DAY
    DO
      TRUNCATE TABLE myschema.mytable;
```

Specify the options in an [`ALTER\\
      EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") statement only for those characteristics that you
want to change; omitted options keep their existing values. This
includes any default values for [`CREATE\\
      EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement") such as `ENABLE`.


To disable `myevent`, use this
[`ALTER EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") statement:


``` sql

ALTER EVENT myevent
    DISABLE;
```

The `ON SCHEDULE` clause may use expressions
involving built-in MySQL functions and user variables to obtain
any of the _`timestamp`_ or
_`interval`_ values which it contains. You
cannot use stored routines or loadable functions in such
expressions, and you cannot use any table references; however, you
can use `SELECT FROM DUAL`. This is true for both
[`ALTER EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") and
[`CREATE EVENT`](https://dev.mysql.com/doc/refman/8.0/en/create-event.html "15.1.13 CREATE EVENT Statement") statements. References
to stored routines, loadable functions, and tables in such cases
are specifically not permitted, and fail with an error (see Bug
#22830).


Although an [`ALTER EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") statement
that contains another [`ALTER EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement")
statement in its [`DO`](https://dev.mysql.com/doc/refman/8.0/en/do.html "15.2.3 DO Statement") clause appears
to succeed, when the server attempts to execute the resulting
scheduled event, the execution fails with an error.


To rename an event, use the [`ALTER\\
      EVENT`](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html "15.1.3 ALTER EVENT Statement") statement's `RENAME TO` clause.
This statement renames the event `myevent` to
`yourevent`:


``` sql

ALTER EVENT myevent
    RENAME TO yourevent;
```

You can also move an event to a different database using
`ALTER EVENT ... RENAME TO ...` and
`db_name.event_name`
notation, as shown here:


``` sql

ALTER EVENT olddb.myevent
    RENAME TO newdb.myevent;
```

To execute the previous statement, the user executing it must have
the [`EVENT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_event) privilege on both the
`olddb` and `newdb` databases.

Note

There is no `RENAME EVENT` statement.

The value `DISABLE ON SLAVE` is used on a replica
instead of `ENABLE` or `DISABLE`
to indicate an event that was created on the replication source
server and replicated to the replica, but that is not executed on
the replica. Normally, `DISABLE ON SLAVE` is set
automatically as required; however, there are some circumstances
under which you may want or need to change it manually. See
[Section 19.5.1.16, “Replication of Invoked Features”](https://dev.mysql.com/doc/refman/8.0/en/replication-features-invoked.html "19.5.1.16 Replication of Invoked Features"), for more
information.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/alter-database.html "Previous: ALTER DATABASE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html "Up: Data Definition Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/alter-function.html "Next: ALTER FUNCTION Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/alter-event.html)

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