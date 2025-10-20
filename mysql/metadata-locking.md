---
url: https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html
scraped_at: 2025-10-20T03:12:21.423Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html "Hide Sidebar")

[Previous: Concurrent Inserts](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html "Previous: Concurrent Inserts")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimizing Locking Operations](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html "Up: Optimizing Locking Operations")[Next: External Locking](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html "Next: External Locking")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/metadata-locking.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/metadata-locking.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/metadata-locking.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/metadata-locking.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/metadata-locking.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/metadata-locking.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/metadata-locking.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/metadata-locking.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimizing Locking Operations](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html)  /

Metadata Locking


### 10.11.4 Metadata Locking

MySQL uses metadata locking to manage concurrent access to
database objects and to ensure data consistency. Metadata
locking applies not just to tables, but also to schemas, stored
programs (procedures, functions, triggers, scheduled events),
tablespaces, user locks acquired with the
[`GET_LOCK()`](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html#function_get-lock) function (see
[Section 14.14, “Locking Functions”](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html "14.14 Locking Functions")), and locks acquired with
the locking service described in
[Section 7.6.9.1, “The Locking Service”](https://dev.mysql.com/doc/refman/8.0/en/locking-service.html "7.6.9.1 The Locking Service").


The Performance Schema
[`metadata_locks`](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-metadata-locks-table.html "29.12.13.3 The metadata_locks Table") table exposes
metadata lock information, which can be useful for seeing which
sessions hold locks, are blocked waiting for locks, and so
forth. For details, see
[Section 29.12.13.3, “The metadata\_locks Table”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-metadata-locks-table.html "29.12.13.3 The metadata_locks Table").


Metadata locking does involve some overhead, which increases as
query volume increases. Metadata contention increases the more
that multiple queries attempt to access the same objects.


Metadata locking is not a replacement for the table definition
cache, and its mutexes and locks differ from the
`LOCK_open` mutex. The following discussion
provides some information about how metadata locking works.

- [Metadata Lock Acquisition](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html#metadata-lock-acquisition "Metadata Lock Acquisition")

- [Metadata Lock Release](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html#metadata-lock-release "Metadata Lock Release")


#### Metadata Lock Acquisition

If there are multiple waiters for a given lock, the
highest-priority lock request is satisfied first, with an
exception related to the
[`max_write_lock_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_write_lock_count) system
variable. Write lock requests have higher priority than read
lock requests. However, if
[`max_write_lock_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_write_lock_count) is set
to some low value (say, 10), read lock requests may be
preferred over pending write lock requests if the read lock
requests have already been passed over in favor of 10 write
lock requests. Normally this behavior does not occur because
[`max_write_lock_count`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_write_lock_count) by
default has a very large value.


Statements acquire metadata locks one by one, not
simultaneously, and perform deadlock detection in the process.


DML statements normally acquire locks in the order in which
tables are mentioned in the statement.


DDL statements, [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"),
and other similar statements try to reduce the number of
possible deadlocks between concurrent DDL statements by
acquiring locks on explicitly named tables in name order.
Locks might be acquired in a different order for implicitly
used tables (such as tables in foreign key relationships that
also must be locked).


For example, [`RENAME TABLE`](https://dev.mysql.com/doc/refman/8.0/en/rename-table.html "15.1.36 RENAME TABLE Statement") is a
DDL statement that acquires locks in name order:

- This [`RENAME TABLE`](https://dev.mysql.com/doc/refman/8.0/en/rename-table.html "15.1.36 RENAME TABLE Statement") statement
renames `tbla` to something else, and
renames `tblc` to
`tbla`:




``` sql

RENAME TABLE tbla TO tbld, tblc TO tbla;
```




The statement acquires metadata locks, in order, on
`tbla`, `tblc`, and
`tbld` (because `tbld`
follows `tblc` in name order):


- This slightly different statement also renames
`tbla` to something else, and renames
`tblc` to `tbla`:




``` sql

RENAME TABLE tbla TO tblb, tblc TO tbla;
```




In this case, the statement acquires metadata locks, in
order, on `tbla`,
`tblb`, and `tblc`
(because `tblb` precedes
`tblc` in name order):


Both statements acquire locks on `tbla` and
`tblc`, in that order, but differ in whether
the lock on the remaining table name is acquired before or
after `tblc`.


Metadata lock acquisition order can make a difference in
operation outcome when multiple transactions execute
concurrently, as the following example illustrates.


Begin with two tables `x` and
`x_new` that have identical structure. Three
clients issue statements that involve these tables:


Client 1:


``` sql

LOCK TABLE x WRITE, x_new WRITE;
```

The statement requests and acquires write locks in name order
on `x` and `x_new`.


Client 2:


``` sql

INSERT INTO x VALUES(1);
```

The statement requests and blocks waiting for a write lock on
`x`.


Client 3:


``` sql

RENAME TABLE x TO x_old, x_new TO x;
```

The statement requests exclusive locks in name order on
`x`, `x_new`, and
`x_old`, but blocks waiting for the lock on
`x`.


Client 1:


``` sql

UNLOCK TABLES;
```

The statement releases the write locks on `x`
and `x_new`. The exclusive lock request for
`x` by Client 3 has higher priority than the
write lock request by Client 2, so Client 3 acquires its lock
on `x`, then also on `x_new`
and `x_old`, performs the renaming, and
releases its locks. Client 2 then acquires its lock on
`x`, performs the insert, and releases its
lock.


Lock acquisition order results in the
[`RENAME TABLE`](https://dev.mysql.com/doc/refman/8.0/en/rename-table.html "15.1.36 RENAME TABLE Statement") executing before
the [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"). The
`x` into which the insert occurs is the table
that was named `x_new` when Client 2 issued
the insert and was renamed to `x` by Client
3:


``` sql

mysql> SELECT * FROM x;
+------+
| i    |
+------+
|    1 |
+------+

mysql> SELECT * FROM x_old;
Empty set (0.01 sec)
```

Now begin instead with tables named `x` and
`new_x` that have identical structure. Again,
three clients issue statements that involve these tables:


Client 1:


``` sql

LOCK TABLE x WRITE, new_x WRITE;
```

The statement requests and acquires write locks in name order
on `new_x` and `x`.


Client 2:


``` sql

INSERT INTO x VALUES(1);
```

The statement requests and blocks waiting for a write lock on
`x`.


Client 3:


``` sql

RENAME TABLE x TO old_x, new_x TO x;
```

The statement requests exclusive locks in name order on
`new_x`, `old_x`, and
`x`, but blocks waiting for the lock on
`new_x`.


Client 1:


``` sql

UNLOCK TABLES;
```

The statement releases the write locks on `x`
and `new_x`. For `x`, the
only pending request is by Client 2, so Client 2 acquires its
lock, performs the insert, and releases the lock. For
`new_x`, the only pending request is by
Client 3, which is permitted to acquire that lock (and also
the lock on `old_x`). The rename operation
still blocks for the lock on `x` until the
Client 2 insert finishes and releases its lock. Then Client 3
acquires the lock on `x`, performs the
rename, and releases its lock.


In this case, lock acquisition order results in the
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") executing before the
[`RENAME TABLE`](https://dev.mysql.com/doc/refman/8.0/en/rename-table.html "15.1.36 RENAME TABLE Statement"). The
`x` into which the insert occurs is the
original `x`, now renamed to
`old_x` by the rename operation:


``` sql

mysql> SELECT * FROM x;
Empty set (0.01 sec)

mysql> SELECT * FROM old_x;
+------+
| i    |
+------+
|    1 |
+------+
```

If order of lock acquisition in concurrent statements makes a
difference to an application in operation outcome, as in the
preceding example, you may be able to adjust the table names
to affect the order of lock acquisition.


Metadata locks are extended, as necessary, to tables related
by a foreign key constraint to prevent conflicting DML and DDL
operations from executing concurrently on the related tables.
When updating a parent table, a metadata lock is taken on the
child table while updating foreign key metadata. Foreign key
metadata is owned by the child table.

#### Metadata Lock Release

To ensure transaction serializability, the server must not
permit one session to perform a data definition language (DDL)
statement on a table that is used in an uncompleted explicitly
or implicitly started transaction in another session. The
server achieves this by acquiring metadata locks on tables
used within a transaction and deferring release of those locks
until the transaction ends. A metadata lock on a table
prevents changes to the table's structure. This locking
approach has the implication that a table that is being used
by a transaction within one session cannot be used in DDL
statements by other sessions until the transaction ends.


This principle applies not only to transactional tables, but
also to nontransactional tables. Suppose that a session begins
a transaction that uses transactional table
`t` and nontransactional table
`nt` as follows:


``` sql

START TRANSACTION;
SELECT * FROM t;
SELECT * FROM nt;
```

The server holds metadata locks on both `t`
and `nt` until the transaction ends. If
another session attempts a DDL or write lock operation on
either table, it blocks until metadata lock release at
transaction end. For example, a second session blocks if it
attempts any of these operations:


``` sql

DROP TABLE t;
ALTER TABLE t ...;
DROP TABLE nt;
ALTER TABLE nt ...;
LOCK TABLE t ... WRITE;
```

The same behavior applies for The
[`LOCK TABLES ...\\
          READ`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"). That is, explicitly or implicitly started
transactions that update any table (transactional or
nontransactional) block and are blocked by `LOCK
          TABLES ... READ` for that table.


If the server acquires metadata locks for a statement that is
syntactically valid but fails during execution, it does not
release the locks early. Lock release is still deferred to the
end of the transaction because the failed statement is written
to the binary log and the locks protect log consistency.


In autocommit mode, each statement is in effect a complete
transaction, so metadata locks acquired for the statement are
held only to the end of the statement.


Metadata locks acquired during a
[`PREPARE`](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "15.5.1 PREPARE Statement") statement are released
once the statement has been prepared, even if preparation
occurs within a multiple-statement transaction.


As of MySQL 8.0.13, for XA transactions in
`PREPARED` state, metadata locks are
maintained across client disconnects and server restarts,
until an [`XA\\
          COMMIT`](https://dev.mysql.com/doc/refman/8.0/en/xa.html "15.3.8 XA Transactions") or [`XA\\
          ROLLBACK`](https://dev.mysql.com/doc/refman/8.0/en/xa.html "15.3.8 XA Transactions") is executed.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html "Previous: Concurrent Inserts") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html "Up: Optimizing Locking Operations") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html "Next: External Locking")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html)

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