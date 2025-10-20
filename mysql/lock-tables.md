---
url: https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html
scraped_at: 2025-10-20T03:02:50.517Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "Hide Sidebar")

[Previous: LOCK INSTANCE FOR BACKUP and UNLOCK INSTANCE Statements](https://dev.mysql.com/doc/refman/8.0/en/lock-instance-for-backup.html "Previous: LOCK INSTANCE FOR BACKUP and UNLOCK INSTANCE Statements")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Transactional and Locking Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-transactional-statements.html "Up: Transactional and Locking Statements")[Next: SET TRANSACTION Statement](https://dev.mysql.com/doc/refman/8.0/en/set-transaction.html "Next: SET TRANSACTION Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/lock-tables.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/lock-tables.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/lock-tables.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/lock-tables.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/lock-tables.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/lock-tables.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/lock-tables.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/lock-tables.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Transactional and Locking Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-transactional-statements.html)  /

LOCK TABLES and UNLOCK TABLES Statements


### 15.3.6 LOCK TABLES and UNLOCK TABLES Statements

``` sql

LOCK {TABLE | TABLES}
    tbl_name [[AS] alias] lock_type
    [, tbl_name [[AS] alias] lock_type] ...

lock_type: {
    READ [LOCAL]
  | [LOW_PRIORITY] WRITE
}

UNLOCK {TABLE | TABLES}
```

MySQL enables client sessions to acquire table locks explicitly
for the purpose of cooperating with other sessions for access to
tables, or to prevent other sessions from modifying tables during
periods when a session requires exclusive access to them. A
session can acquire or release locks only for itself. One session
cannot acquire locks for another session or release locks held by
another session.


Locks may be used to emulate transactions or to get more speed
when updating tables. This is explained in more detail in
[Table-Locking Restrictions and Conditions](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html#lock-tables-restrictions "Table-Locking Restrictions and Conditions").


[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") explicitly acquires
table locks for the current client session. Table locks can be
acquired for base tables or views. You must have the
[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_lock-tables) privilege, and the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege for each object to
be locked.


For view locking, [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") adds
all base tables used in the view to the set of tables to be locked
and locks them automatically. For tables underlying any view being
locked, [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") checks that the
view definer (for `SQL SECURITY DEFINER` views)
or invoker (for all views) has the proper privileges on the
tables.


If you lock a table explicitly with [`LOCK\\
      TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"), any tables used in triggers are also locked
implicitly, as described in
[LOCK TABLES and Triggers](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html#lock-tables-and-triggers "LOCK TABLES and Triggers").


If you lock a table explicitly with [`LOCK\\
      TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"), any tables related by a foreign key constraint
are opened and locked implicitly. For foreign key checks, a shared
read-only lock ( [`LOCK\\
      TABLES READ`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements")) is taken on related tables. For cascading
updates, a shared-nothing write lock
( [`LOCK TABLES\\
      WRITE`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements")) is taken on related tables that are involved in
the operation.


[`UNLOCK\\
      TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") explicitly releases any table locks held by the
current session. [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements")
implicitly releases any table locks held by the current session
before acquiring new locks.


Another use for
[`UNLOCK\\
      TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") is to release the global read lock acquired with
the [`FLUSH TABLES WITH READ LOCK`](https://dev.mysql.com/doc/refman/8.0/en/flush.html#flush-tables-with-read-lock)
statement, which enables you to lock all tables in all databases.
See [Section 15.7.8.3, “FLUSH Statement”](https://dev.mysql.com/doc/refman/8.0/en/flush.html "15.7.8.3 FLUSH Statement"). (This is a very convenient way to get
backups if you have a file system such as Veritas that can take
snapshots in time.)


`LOCK TABLE` is a synonym for `LOCK
      TABLES`; `UNLOCK TABLE` is a synonym for
`UNLOCK TABLES`.


A table lock protects only against inappropriate reads or writes
by other sessions. A session holding a `WRITE`
lock can perform table-level operations such as
[`DROP TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") or
[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement"). For sessions
holding a `READ` lock, [`DROP\\
      TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement") and [`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement")
operations are not permitted.


The following discussion applies only to
non- `TEMPORARY` tables. [`LOCK\\
      TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") is permitted (but ignored) for a
`TEMPORARY` table. The table can be accessed
freely by the session within which it was created, regardless of
what other locking may be in effect. No lock is necessary because
no other session can see the table.

- [Table Lock Acquisition](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html#table-lock-acquisition "Table Lock Acquisition")

- [Table Lock Release](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html#table-lock-release "Table Lock Release")

- [Interaction of Table Locking and Transactions](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html#lock-tables-and-transactions "Interaction of Table Locking and Transactions")

- [LOCK TABLES and Triggers](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html#lock-tables-and-triggers "LOCK TABLES and Triggers")

- [Table-Locking Restrictions and Conditions](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html#lock-tables-restrictions "Table-Locking Restrictions and Conditions")


#### Table Lock Acquisition

To acquire table locks within the current session, use the
[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") statement, which
acquires metadata locks (see
[Section 10.11.4, “Metadata Locking”](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html "10.11.4 Metadata Locking")).


The following lock types are available:


`READ [LOCAL]` lock:

- The session that holds the lock can read the table (but not
write it).


- Multiple sessions can acquire a `READ` lock
for the table at the same time.


- Other sessions can read the table without explicitly
acquiring a `READ` lock.


- The `LOCAL` modifier enables nonconflicting
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statements (concurrent
inserts) by other sessions to execute while the lock is
held. (See [Section 10.11.3, “Concurrent Inserts”](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html "10.11.3 Concurrent Inserts").) However,
`READ LOCAL` cannot be used if you are
going to manipulate the database using processes external to
the server while you hold the lock. For
`InnoDB` tables, `READ
              LOCAL` is the same as `READ`.


`[LOW_PRIORITY] WRITE` lock:

- The session that holds the lock can read and write the
table.


- Only the session that holds the lock can access the table.
No other session can access it until the lock is released.


- Lock requests for the table by other sessions block while
the `WRITE` lock is held.


- The `LOW_PRIORITY` modifier has no effect.
In previous versions of MySQL, it affected locking behavior,
but this is no longer true. It is now deprecated and its use
produces a warning. Use `WRITE` without
`LOW_PRIORITY` instead.


`WRITE` locks normally have higher priority
than `READ` locks to ensure that updates are
processed as soon as possible. This means that if one session
obtains a `READ` lock and then another session
requests a `WRITE` lock, subsequent
`READ` lock requests wait until the session
that requested the `WRITE` lock has obtained
the lock and released it. (An exception to this policy can occur
for small values of the
[`max_write_lock_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_write_lock_count) system
variable; see [Section 10.11.4, “Metadata Locking”](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html "10.11.4 Metadata Locking").)


If the [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") statement must
wait due to locks held by other sessions on any of the tables,
it blocks until all locks can be acquired.


A session that requires locks must acquire all the locks that it
needs in a single [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements")
statement. While the locks thus obtained are held, the session
can access only the locked tables. For example, in the following
sequence of statements, an error occurs for the attempt to
access `t2` because it was not locked in the
[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") statement:


``` sql

mysql> LOCK TABLES t1 READ;
mysql> SELECT COUNT(*) FROM t1;
+----------+
| COUNT(*) |
+----------+
|        3 |
+----------+
mysql> SELECT COUNT(*) FROM t2;
ERROR 1100 (HY000): Table 't2' was not locked with LOCK TABLES
```

Tables in the `INFORMATION_SCHEMA` database are
an exception. They can be accessed without being locked
explicitly even while a session holds table locks obtained with
[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements").


You cannot refer to a locked table multiple times in a single
query using the same name. Use aliases instead, and obtain a
separate lock for the table and each alias:


``` sql

mysql> LOCK TABLE t WRITE, t AS t1 READ;
mysql> INSERT INTO t SELECT * FROM t;
ERROR 1100: Table 't' was not locked with LOCK TABLES
mysql> INSERT INTO t SELECT * FROM t AS t1;
```

The error occurs for the first
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") because there are two
references to the same name for a locked table. The second
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") succeeds because the
references to the table use different names.


If your statements refer to a table by means of an alias, you
must lock the table using that same alias. It does not work to
lock the table without specifying the alias:


``` sql

mysql> LOCK TABLE t READ;
mysql> SELECT * FROM t AS myalias;
ERROR 1100: Table 'myalias' was not locked with LOCK TABLES
```

Conversely, if you lock a table using an alias, you must refer
to it in your statements using that alias:


``` sql

mysql> LOCK TABLE t AS myalias READ;
mysql> SELECT * FROM t;
ERROR 1100: Table 't' was not locked with LOCK TABLES
mysql> SELECT * FROM t AS myalias;
```

#### Table Lock Release

When the table locks held by a session are released, they are
all released at the same time. A session can release its locks
explicitly, or locks may be released implicitly under certain
conditions.

- A session can release its locks explicitly with
[`UNLOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements").


- If a session issues a [`LOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") statement to acquire a lock while already
holding locks, its existing locks are released implicitly
before the new locks are granted.


- If a session begins a transaction (for example, with
[`START\\
              TRANSACTION`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements")), an implicit
[`UNLOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") is performed, which causes existing locks
to be released. (For additional information about the
interaction between table locking and transactions, see
[Interaction of Table Locking and Transactions](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html#lock-tables-and-transactions "Interaction of Table Locking and Transactions").)


If the connection for a client session terminates, whether
normally or abnormally, the server implicitly releases all table
locks held by the session (transactional and nontransactional).
If the client reconnects, the locks are no longer in effect. In
addition, if the client had an active transaction, the server
rolls back the transaction upon disconnect, and if reconnect
occurs, the new session begins with autocommit enabled. For this
reason, clients may wish to disable auto-reconnect. With
auto-reconnect in effect, the client is not notified if
reconnect occurs but any table locks or current transaction are
lost. With auto-reconnect disabled, if the connection drops, an
error occurs for the next statement issued. The client can
detect the error and take appropriate action such as reacquiring
the locks or redoing the transaction. See
[Automatic Reconnection Control](https://dev.mysql.com/doc/c-api/8.0/en/c-api-auto-reconnect.html).

Note

If you use [`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") on a
locked table, it may become unlocked. For example, if you
attempt a second [`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement")
operation, the result may be an error `Table
          'tbl_name' was not locked with LOCK
          TABLES`. To handle this, lock the table again prior
to the second alteration. See also
[Section B.3.6.1, “Problems with ALTER TABLE”](https://dev.mysql.com/doc/refman/8.0/en/alter-table-problems.html "B.3.6.1 Problems with ALTER TABLE").

#### Interaction of Table Locking and Transactions

[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") and
[`UNLOCK\\
        TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") interact with the use of transactions as
follows:

- [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") is not
transaction-safe and implicitly commits any active
transaction before attempting to lock the tables.


- [`UNLOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") implicitly commits any active transaction,
but only if [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") has
been used to acquire table locks. For example, in the
following set of statements,
[`UNLOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") releases the global read lock but does not
commit the transaction because no table locks are in effect:




``` sql

FLUSH TABLES WITH READ LOCK;
START TRANSACTION;
SELECT ... ;
UNLOCK TABLES;
```

- Beginning a transaction (for example, with
[`START\\
              TRANSACTION`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements")) implicitly commits any current
transaction and releases existing table locks.


- [`FLUSH TABLES WITH READ LOCK`](https://dev.mysql.com/doc/refman/8.0/en/flush.html#flush-tables-with-read-lock)
acquires a global read lock and not table locks, so it is
not subject to the same behavior as
[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") and
[`UNLOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") with respect to table locking and implicit
commits. For example,
[`START\\
              TRANSACTION`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements") does not release the global read lock.
See [Section 15.7.8.3, “FLUSH Statement”](https://dev.mysql.com/doc/refman/8.0/en/flush.html "15.7.8.3 FLUSH Statement").


- Other statements that implicitly cause transactions to be
committed do not release existing table locks. For a list of
such statements, see [Section 15.3.3, “Statements That Cause an Implicit Commit”](https://dev.mysql.com/doc/refman/8.0/en/implicit-commit.html "15.3.3 Statements That Cause an Implicit Commit").


- The correct way to use [`LOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") and
[`UNLOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") with transactional tables, such as
`InnoDB` tables, is to begin a transaction
with `SET autocommit = 0` (not
[`START\\
              TRANSACTION`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements")) followed by [`LOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"), and to not call
[`UNLOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") until you commit the transaction
explicitly. For example, if you need to write to table
`t1` and read from table
`t2`, you can do this:




``` sql

SET autocommit=0;
LOCK TABLES t1 WRITE, t2 READ, ...;
... do something with tables t1 and t2 here ...
COMMIT;
UNLOCK TABLES;
```




When you call [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"),
`InnoDB` internally takes its own table
lock, and MySQL takes its own table lock.
`InnoDB` releases its internal table lock
at the next commit, but for MySQL to release its table lock,
you have to call
[`UNLOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"). You should not have
[`autocommit = 1`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_autocommit), because
then `InnoDB` releases its internal table
lock immediately after the call of [`LOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"), and deadlocks can very easily happen.
`InnoDB` does not acquire the internal
table lock at all if [`autocommit =\\
              1`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_autocommit), to help old applications avoid unnecessary
deadlocks.


- [`ROLLBACK`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements")
does not release table locks.


#### LOCK TABLES and Triggers

If you lock a table explicitly with [`LOCK\\
        TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"), any tables used in triggers are also locked
implicitly:

- The locks are taken as the same time as those acquired
explicitly with the [`LOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") statement.


- The lock on a table used in a trigger depends on whether the
table is used only for reading. If so, a read lock suffices.
Otherwise, a write lock is used.


- If a table is locked explicitly for reading with
[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"), but needs to be
locked for writing because it might be modified within a
trigger, a write lock is taken rather than a read lock.
(That is, an implicit write lock needed due to the table's
appearance within a trigger causes an explicit read lock
request for the table to be converted to a write lock
request.)


Suppose that you lock two tables, `t1` and
`t2`, using this statement:


``` sql

LOCK TABLES t1 WRITE, t2 READ;
```

If `t1` or `t2` have any
triggers, tables used within the triggers are also locked.
Suppose that `t1` has a trigger defined like
this:


``` sql

CREATE TRIGGER t1_a_ins AFTER INSERT ON t1 FOR EACH ROW
BEGIN
  UPDATE t4 SET count = count+1
      WHERE id = NEW.id AND EXISTS (SELECT a FROM t3);
  INSERT INTO t2 VALUES(1, 2);
END;
```

The result of the [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements")
statement is that `t1` and
`t2` are locked because they appear in the
statement, and `t3` and `t4`
are locked because they are used within the trigger:

- `t1` is locked for writing per the
`WRITE` lock request.


- `t2` is locked for writing, even though the
request is for a `READ` lock. This occurs
because `t2` is inserted into within the
trigger, so the `READ` request is converted
to a `WRITE` request.


- `t3` is locked for reading because it is
only read from within the trigger.


- `t4` is locked for writing because it might
be updated within the trigger.


#### Table-Locking Restrictions and Conditions

You can safely use [`KILL`](https://dev.mysql.com/doc/refman/8.0/en/kill.html "15.7.8.4 KILL Statement") to
terminate a session that is waiting for a table lock. See
[Section 15.7.8.4, “KILL Statement”](https://dev.mysql.com/doc/refman/8.0/en/kill.html "15.7.8.4 KILL Statement").


[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") and
[`UNLOCK\\
        TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") cannot be used within stored programs.


Tables in the `performance_schema` database
cannot be locked with [`LOCK\\
        TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"), except the
`setup_xxx` tables.


The scope of a lock generated by `LOCK TABLES`
is a single MySQL server. It is not compatible with NDB Cluster,
which has no way of enforcing an SQL-level lock across multiple
instances of [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server"). You can enforce locking
in an API application instead. See
[Section 25.2.7.10, “Limitations Relating to Multiple NDB Cluster Nodes”](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster-limitations-multiple-nodes.html "25.2.7.10 Limitations Relating to Multiple NDB Cluster Nodes"), for
more information.


The following statements are prohibited while a
[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") statement is in
effect: [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"),
[`CREATE TABLE ...\\
        LIKE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"), [`CREATE VIEW`](https://dev.mysql.com/doc/refman/8.0/en/create-view.html "15.1.23 CREATE VIEW Statement"),
[`DROP VIEW`](https://dev.mysql.com/doc/refman/8.0/en/drop-view.html "15.1.35 DROP VIEW Statement"), and DDL statements on
stored functions and procedures and events.


For some operations, system tables in the
`mysql` database must be accessed. For example,
the [`HELP`](https://dev.mysql.com/doc/refman/8.0/en/help.html "15.8.3 HELP Statement") statement requires the
contents of the server-side help tables, and
[`CONVERT_TZ()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_convert-tz) might need to read
the time zone tables. The server implicitly locks the system
tables for reading as necessary so that you need not lock them
explicitly. These tables are treated as just described:


``` none

mysql.help_category
mysql.help_keyword
mysql.help_relation
mysql.help_topic
mysql.time_zone
mysql.time_zone_leap_second
mysql.time_zone_name
mysql.time_zone_transition
mysql.time_zone_transition_type
```

If you want to explicitly place a `WRITE` lock
on any of those tables with a [`LOCK\\
        TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") statement, the table must be the only one
locked; no other table can be locked with the same statement.


Normally, you do not need to lock tables, because all single
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statements are atomic; no
other session can interfere with any other currently executing
SQL statement. However, there are a few cases when locking
tables may provide an advantage:

- If you are going to run many operations on a set of
`MyISAM` tables, it is much faster to lock
the tables you are going to use. Locking
`MyISAM` tables speeds up inserting,
updating, or deleting on them because MySQL does not flush
the key cache for the locked tables until
[`UNLOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") is called. Normally, the key cache is
flushed after each SQL statement.



The downside to locking the tables is that no session can
update a `READ`-locked table (including the
one holding the lock) and no session can access a
`WRITE`-locked table other than the one
holding the lock.


- If you are using tables for a nontransactional storage
engine, you must use [`LOCK\\
              TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") if you want to ensure that no other session
modifies the tables between a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") and an
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"). The example shown
here requires [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") to
execute safely:




``` sql

LOCK TABLES trans READ, customer WRITE;
SELECT SUM(value) FROM trans WHERE customer_id=some_id;
UPDATE customer
    SET total_value=sum_from_previous_statement
    WHERE customer_id=some_id;
UNLOCK TABLES;
```




Without [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"), it is
possible that another session might insert a new row in the
`trans` table between execution of the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") and
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statements.


You can avoid using [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements")
in many cases by using relative updates ( `UPDATE
        customer SET
        value=value+new_value`)
or the [`LAST_INSERT_ID()`](https://dev.mysql.com/doc/refman/8.0/en/information-functions.html#function_last-insert-id) function.


You can also avoid locking tables in some cases by using the
user-level advisory lock functions
[`GET_LOCK()`](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html#function_get-lock) and
[`RELEASE_LOCK()`](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html#function_release-lock). These locks are
saved in a hash table in the server and implemented with
`pthread_mutex_lock()` and
`pthread_mutex_unlock()` for high speed. See
[Section 14.14, “Locking Functions”](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html "14.14 Locking Functions").


See [Section 10.11.1, “Internal Locking Methods”](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html "10.11.1 Internal Locking Methods"), for more information on
locking policy.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/lock-instance-for-backup.html "Previous: LOCK INSTANCE FOR BACKUP and UNLOCK INSTANCE Statements") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-transactional-statements.html "Up: Transactional and Locking Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/set-transaction.html "Next: SET TRANSACTION Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html)

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