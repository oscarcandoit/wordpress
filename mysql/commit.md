---
url: https://dev.mysql.com/doc/refman/8.0/en/commit.html
scraped_at: 2025-10-20T03:02:40.488Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/commit.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/commit.html "Hide Sidebar")

[Previous: Transactional and Locking Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-transactional-statements.html "Previous: Transactional and Locking Statements")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Transactional and Locking Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-transactional-statements.html "Up: Transactional and Locking Statements")[Next: Statements That Cannot Be Rolled Back](https://dev.mysql.com/doc/refman/8.0/en/cannot-roll-back.html "Next: Statements That Cannot Be Rolled Back")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/commit.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/commit.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/commit.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/commit.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/commit.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/commit.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/commit.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/commit.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/commit.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/commit.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/commit.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/commit.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/commit.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/commit.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Transactional and Locking Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-transactional-statements.html)  /

START TRANSACTION, COMMIT, and ROLLBACK Statements


### 15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements

```sql
START TRANSACTION
    [transaction_characteristic [, transaction_characteristic] ...]

transaction_characteristic: {
    WITH CONSISTENT SNAPSHOT
  | READ WRITE
  | READ ONLY
}

BEGIN [WORK]
COMMIT [WORK] [AND [NO] CHAIN] [[NO] RELEASE]
ROLLBACK [WORK] [AND [NO] CHAIN] [[NO] RELEASE]
SET autocommit = {0 | 1}
```

These statements provide control over use of
[transactions](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_transaction "transaction"):

- `START TRANSACTION` or
`BEGIN` start a new transaction.


- `COMMIT` commits the current transaction,
making its changes permanent.


- `ROLLBACK` rolls back the current
transaction, canceling its changes.


- `SET autocommit` disables or enables the
default autocommit mode for the current session.


By default, MySQL runs with
[autocommit](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_autocommit "autocommit") mode enabled.
This means that, when not otherwise inside a transaction, each
statement is atomic, as if it were surrounded by `START
      TRANSACTION` and `COMMIT`. You cannot
use `ROLLBACK` to undo the effect; however, if an
error occurs during statement execution, the statement is rolled
back.


To disable autocommit mode implicitly for a single series of
statements, use the `START TRANSACTION`
statement:


```sql
START TRANSACTION;
SELECT @A:=SUM(salary) FROM table1 WHERE type=1;
UPDATE table2 SET summary=@A WHERE type=1;
COMMIT;
```

With `START TRANSACTION`, autocommit remains
disabled until you end the transaction with
`COMMIT` or `ROLLBACK`. The
autocommit mode then reverts to its previous state.


`START TRANSACTION` permits several modifiers
that control transaction characteristics. To specify multiple
modifiers, separate them by commas.

- The `WITH CONSISTENT SNAPSHOT` modifier
starts a [consistent\\
read](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_consistent_read "consistent read") for storage engines that are capable of it. This
applies only to `InnoDB`. The effect is the
same as issuing a `START TRANSACTION`
followed by a [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") from any
`InnoDB` table. See
[Section 17.7.2.3, “Consistent Nonlocking Reads”](https://dev.mysql.com/doc/refman/8.0/en/innodb-consistent-read.html "17.7.2.3 Consistent Nonlocking Reads"). The `WITH
            CONSISTENT SNAPSHOT` modifier does not change the
current transaction
[isolation level](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_isolation_level "isolation level"),
so it provides a consistent snapshot only if the current
isolation level is one that permits a consistent read. The
only isolation level that permits a consistent read is
[`REPEATABLE READ`](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html#isolevel_repeatable-read). For all
other isolation levels, the `WITH CONSISTENT
            SNAPSHOT` clause is ignored. A warning is generated
when the `WITH CONSISTENT SNAPSHOT` clause is
ignored.


- The `READ WRITE` and `READ
            ONLY` modifiers set the transaction access mode. They
permit or prohibit changes to tables used in the transaction.
The `READ ONLY` restriction prevents the
transaction from modifying or locking both transactional and
nontransactional tables that are visible to other
transactions; the transaction can still modify or lock
temporary tables.



MySQL enables extra optimizations for queries on
`InnoDB` tables when the transaction is known
to be read-only. Specifying `READ ONLY`
ensures these optimizations are applied in cases where the
read-only status cannot be determined automatically. See
[Section 10.5.3, “Optimizing InnoDB Read-Only Transactions”](https://dev.mysql.com/doc/refman/8.0/en/innodb-performance-ro-txn.html "10.5.3 Optimizing InnoDB Read-Only Transactions") for more
information.



If no access mode is specified, the default mode applies.
Unless the default has been changed, it is read/write. It is
not permitted to specify both `READ WRITE`
and `READ ONLY` in the same statement.



In read-only mode, it remains possible to change tables
created with the `TEMPORARY` keyword using
DML statements. Changes made with DDL statements are not
permitted, just as with permanent tables.



For additional information about transaction access mode,
including ways to change the default mode, see
[Section 15.3.7, “SET TRANSACTION Statement”](https://dev.mysql.com/doc/refman/8.0/en/set-transaction.html "15.3.7 SET TRANSACTION Statement").



If the [`read_only`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_read_only) system
variable is enabled, explicitly starting a transaction with
`START TRANSACTION READ WRITE` requires the
[`CONNECTION_ADMIN`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_connection-admin) privilege (or
the deprecated [`SUPER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_super)
privilege).


Important

Many APIs used for writing MySQL client applications (such as
JDBC) provide their own methods for starting transactions that
can (and sometimes should) be used instead of sending a
`START TRANSACTION` statement from the client.
See [Chapter 31, _Connectors and APIs_](https://dev.mysql.com/doc/refman/8.0/en/connectors-apis.html "Chapter 31 Connectors and APIs"), or the documentation for
your API, for more information.

To disable autocommit mode explicitly, use the following
statement:


```sql
SET autocommit=0;
```

After disabling autocommit mode by setting the
[`autocommit`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_autocommit) variable to zero,
changes to transaction-safe tables (such as those for
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") or
[`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0")) are not made permanent
immediately. You must use [`COMMIT`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements") to
store your changes to disk or `ROLLBACK` to
ignore the changes.


[`autocommit`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_autocommit) is a session variable
and must be set for each session. To disable autocommit mode for
each new connection, see the description of the
[`autocommit`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_autocommit) system variable at
[Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables").


`BEGIN` and `BEGIN WORK` are
supported as aliases of `START TRANSACTION` for
initiating a transaction. `START TRANSACTION` is
standard SQL syntax, is the recommended way to start an ad-hoc
transaction, and permits modifiers that `BEGIN`
does not.


The `BEGIN` statement differs from the use of the
`BEGIN` keyword that starts a
[`BEGIN ... END`](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement")
compound statement. The latter does not begin a transaction. See
[Section 15.6.1, “BEGIN ... END Compound Statement”](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement").

Note

Within all stored programs (stored procedures and functions,
triggers, and events), the parser treats `BEGIN
        [WORK]` as the beginning of a
[`BEGIN ...\\
        END`](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement") block. Begin a transaction in this context with
[`START\\
        TRANSACTION`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements") instead.

The optional `WORK` keyword is supported for
`COMMIT` and `ROLLBACK`, as are
the `CHAIN` and `RELEASE`
clauses. `CHAIN` and `RELEASE`
can be used for additional control over transaction completion.
The value of the [`completion_type`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_completion_type)
system variable determines the default completion behavior. See
[Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables").


The `AND CHAIN` clause causes a new transaction
to begin as soon as the current one ends, and the new transaction
has the same isolation level as the just-terminated transaction.
The new transaction also uses the same access mode ( `READ
      WRITE` or `READ ONLY`) as the
just-terminated transaction. The `RELEASE` clause
causes the server to disconnect the current client session after
terminating the current transaction. Including the
`NO` keyword suppresses `CHAIN`
or `RELEASE` completion, which can be useful if
the [`completion_type`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_completion_type) system
variable is set to cause chaining or release completion by
default.


Beginning a transaction causes any pending transaction to be
committed. See [Section 15.3.3, “Statements That Cause an Implicit Commit”](https://dev.mysql.com/doc/refman/8.0/en/implicit-commit.html "15.3.3 Statements That Cause an Implicit Commit"), for more
information.


Beginning a transaction also causes table locks acquired with
[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") to be released, as
though you had executed
[`UNLOCK\\
      TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"). Beginning a transaction does not release a
global read lock acquired with [`FLUSH TABLES\\
      WITH READ LOCK`](https://dev.mysql.com/doc/refman/8.0/en/flush.html#flush-tables-with-read-lock).


For best results, transactions should be performed using only
tables managed by a single transaction-safe storage engine.
Otherwise, the following problems can occur:

- If you use tables from more than one transaction-safe storage
engine (such as `InnoDB`), and the
transaction isolation level is not
[`SERIALIZABLE`](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html#isolevel_serializable), it is
possible that when one transaction commits, another ongoing
transaction that uses the same tables sees only some of the
changes made by the first transaction. That is, the atomicity
of transactions is not guaranteed with mixed engines and
inconsistencies can result. (If mixed-engine transactions are
infrequent, you can use
[`SET\\
            TRANSACTION ISOLATION LEVEL`](https://dev.mysql.com/doc/refman/8.0/en/set-transaction.html "15.3.7 SET TRANSACTION Statement") to set the isolation
level to [`SERIALIZABLE`](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html#isolevel_serializable) on a
per-transaction basis as necessary.)


- If you use tables that are not transaction-safe within a
transaction, changes to those tables are stored at once,
regardless of the status of autocommit mode.


- If you issue a
[`ROLLBACK`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements")
statement after updating a nontransactional table within a
transaction, an
[`ER_WARNING_NOT_COMPLETE_ROLLBACK`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_warning_not_complete_rollback)
warning occurs. Changes to transaction-safe tables are rolled
back, but not changes to nontransaction-safe tables.


Each transaction is stored in the binary log in one chunk, upon
[`COMMIT`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements"). Transactions that are
rolled back are not logged.
(**Exception**: Modifications to
nontransactional tables cannot be rolled back. If a transaction
that is rolled back includes modifications to nontransactional
tables, the entire transaction is logged with a
[`ROLLBACK`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements")
statement at the end to ensure that modifications to the
nontransactional tables are replicated.) See
[Section 7.4.4, “The Binary Log”](https://dev.mysql.com/doc/refman/8.0/en/binary-log.html "7.4.4 The Binary Log").


You can change the isolation level or access mode for transactions
with the [`SET TRANSACTION`](https://dev.mysql.com/doc/refman/8.0/en/set-transaction.html "15.3.7 SET TRANSACTION Statement") statement.
See [Section 15.3.7, “SET TRANSACTION Statement”](https://dev.mysql.com/doc/refman/8.0/en/set-transaction.html "15.3.7 SET TRANSACTION Statement").


Rolling back can be a slow operation that may occur implicitly
without the user having explicitly asked for it (for example, when
an error occurs). Because of this, [`SHOW\\
      PROCESSLIST`](https://dev.mysql.com/doc/refman/8.0/en/show-processlist.html "15.7.7.29 SHOW PROCESSLIST Statement") displays `Rolling back` in
the `State` column for the session, not only for
explicit rollbacks performed with the
[`ROLLBACK`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements")
statement but also for implicit rollbacks.

Note

In MySQL 8.0, `BEGIN`,
`COMMIT`, and `ROLLBACK` are
not affected by [`--replicate-do-db`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-replica.html#option_mysqld_replicate-do-db)
or [`--replicate-ignore-db`](https://dev.mysql.com/doc/refman/8.0/en/replication-options-replica.html#option_mysqld_replicate-ignore-db) rules.

When `InnoDB` performs a complete rollback of a
transaction, all locks set by the transaction are released. If a
single SQL statement within a transaction rolls back as a result
of an error, such as a duplicate key error, locks set by the
statement are preserved while the transaction remains active. This
happens because `InnoDB` stores row locks in a
format such that it cannot know afterward which lock was set by
which statement.


If a [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement within a
transaction calls a stored function, and a statement within the
stored function fails, that statement rolls back. If
[`ROLLBACK`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements") is
executed for the transaction subsequently, the entire transaction
rolls back.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/sql-transactional-statements.html "Previous: Transactional and Locking Statements") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-transactional-statements.html "Up: Transactional and Locking Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/cannot-roll-back.html "Next: Statements That Cannot Be Rolled Back")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/commit.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/commit.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/commit.html)

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