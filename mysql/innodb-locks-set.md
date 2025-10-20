---
url: https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html
scraped_at: 2025-10-20T03:12:43.128Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html "Hide Sidebar")

[Previous: Locking Reads](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-reads.html "Previous: Locking Reads")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: InnoDB Locking and Transaction Model](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html "Up: InnoDB Locking and Transaction Model")[Next: Phantom Rows](https://dev.mysql.com/doc/refman/8.0/en/innodb-next-key-locking.html "Next: Phantom Rows")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/innodb-locks-set.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/innodb-locks-set.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/innodb-locks-set.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/innodb-locks-set.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/innodb-locks-set.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/innodb-locks-set.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/innodb-locks-set.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/innodb-locks-set.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html)  / [The InnoDB Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)  /
[InnoDB Locking and Transaction Model](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html)  /

Locks Set by Different SQL Statements in InnoDB


### 17.7.3 Locks Set by Different SQL Statements in InnoDB

A [locking read](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_locking_read "locking read"), an
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"), or a
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") generally set record locks
on every index record that is scanned in the processing of an SQL
statement. It does not matter whether there are
`WHERE` conditions in the statement that would
exclude the row. `InnoDB` does not remember the
exact `WHERE` condition, but only knows which
index ranges were scanned. The locks are normally
[next-key locks](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_next_key_lock "next-key lock") that also
block inserts into the “gap” immediately before the
record. However, [gap locking](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_gap_lock "gap lock")
can be disabled explicitly, which causes next-key locking not to
be used. For more information, see
[Section 17.7.1, “InnoDB Locking”](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html "17.7.1 InnoDB Locking"). The transaction isolation level
can also affect which locks are set; see
[Section 17.7.2.1, “Transaction Isolation Levels”](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html "17.7.2.1 Transaction Isolation Levels").


If a secondary index is used in a search and the index record
locks to be set are exclusive, `InnoDB` also
retrieves the corresponding clustered index records and sets locks
on them.


If you have no indexes suitable for your statement and MySQL must
scan the entire table to process the statement, every row of the
table becomes locked, which in turn blocks all inserts by other
users to the table. It is important to create good indexes so that
your queries do not scan more rows than necessary.


`InnoDB` sets specific types of locks as follows.

- [`SELECT ...\\
            FROM`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") is a consistent read, reading a snapshot of the
database and setting no locks unless the transaction isolation
level is set to
[`SERIALIZABLE`](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html#isolevel_serializable). For
[`SERIALIZABLE`](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html#isolevel_serializable) level, the
search sets shared next-key locks on the index records it
encounters. However, only an index record lock is required for
statements that lock rows using a unique index to search for a
unique row.


- [`SELECT ... FOR\\
            UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") and
[`SELECT ... FOR\\
            SHARE`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements that use a unique index acquire
locks for scanned rows, and release the locks for rows that do
not qualify for inclusion in the result set (for example, if
they do not meet the criteria given in the
`WHERE` clause). However, in some cases, rows
might not be unlocked immediately because the relationship
between a result row and its original source is lost during
query execution. For example, in a
[`UNION`](https://dev.mysql.com/doc/refman/8.0/en/union.html "15.2.18 UNION Clause"), scanned (and locked)
rows from a table might be inserted into a temporary table
before evaluating whether they qualify for the result set. In
this circumstance, the relationship of the rows in the
temporary table to the rows in the original table is lost and
the latter rows are not unlocked until the end of query
execution.


- For [locking reads](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_locking_read "locking read")
( [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") with `FOR
            UPDATE` or `FOR SHARE`),
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"), and
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statements, the locks
that are taken depend on whether the statement uses a unique
index with a unique search condition or a range-type search
condition.




- For a unique index with a unique search condition,
`InnoDB` locks only the index record
found, not the [gap](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_gap "gap") before
it.


- For other search conditions, and for non-unique indexes,
`InnoDB` locks the index range scanned,
using [gap locks](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_gap_lock "gap lock") or
[next-key locks](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_next_key_lock "next-key lock")
to block insertions by other sessions into the gaps
covered by the range. For information about gap locks and
next-key locks, see [Section 17.7.1, “InnoDB Locking”](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html "17.7.1 InnoDB Locking").


- For index records the search encounters,
[`SELECT ... FOR\\
            UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") blocks other sessions from doing
[`SELECT ... FOR\\
            SHARE`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") or from reading in certain transaction
isolation levels. Consistent reads ignore any locks set on the
records that exist in the read view.


- [`UPDATE ... WHERE\\
            ...`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") sets an exclusive next-key lock on every record
the search encounters. However, only an index record lock is
required for statements that lock rows using a unique index to
search for a unique row.


- When [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") modifies a
clustered index record, implicit locks are taken on affected
secondary index records. The
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") operation also takes
shared locks on affected secondary index records when
performing duplicate check scans prior to inserting new
secondary index records, and when inserting new secondary
index records.


- [`DELETE FROM ... WHERE\\
            ...`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") sets an exclusive next-key lock on every record
the search encounters. However, only an index record lock is
required for statements that lock rows using a unique index to
search for a unique row.


- [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") sets an exclusive lock
on the inserted row. This lock is an index-record lock, not a
next-key lock (that is, there is no gap lock) and does not
prevent other sessions from inserting into the gap before the
inserted row.



Prior to inserting the row, a type of gap lock called an
insert intention gap lock is set. This lock signals the intent
to insert in such a way that multiple transactions inserting
into the same index gap need not wait for each other if they
are not inserting at the same position within the gap. Suppose
that there are index records with values of 4 and 7. Separate
transactions that attempt to insert values of 5 and 6 each
lock the gap between 4 and 7 with insert intention locks prior
to obtaining the exclusive lock on the inserted row, but do
not block each other because the rows are nonconflicting.



If a duplicate-key error occurs, a shared lock on the
duplicate index record is set. This use of a shared lock can
result in deadlock should there be multiple sessions trying to
insert the same row if another session already has an
exclusive lock. This can occur if another session deletes the
row. Suppose that an `InnoDB` table
`t1` has the following structure:



```sql
CREATE TABLE t1 (i INT, PRIMARY KEY (i)) ENGINE = InnoDB;
```



Now suppose that three sessions perform the following
operations in order:



Session 1:



```sql
START TRANSACTION;
INSERT INTO t1 VALUES(1);
```



Session 2:



```sql
START TRANSACTION;
INSERT INTO t1 VALUES(1);
```



Session 3:



```sql
START TRANSACTION;
INSERT INTO t1 VALUES(1);
```



Session 1:



```sql
ROLLBACK;
```



The first operation by session 1 acquires an exclusive lock
for the row. The operations by sessions 2 and 3 both result in
a duplicate-key error and they both request a shared lock for
the row. When session 1 rolls back, it releases its exclusive
lock on the row and the queued shared lock requests for
sessions 2 and 3 are granted. At this point, sessions 2 and 3
deadlock: Neither can acquire an exclusive lock for the row
because of the shared lock held by the other.



A similar situation occurs if the table already contains a row
with key value 1 and three sessions perform the following
operations in order:



Session 1:



```sql
START TRANSACTION;
DELETE FROM t1 WHERE i = 1;
```



Session 2:



```sql
START TRANSACTION;
INSERT INTO t1 VALUES(1);
```



Session 3:



```sql
START TRANSACTION;
INSERT INTO t1 VALUES(1);
```



Session 1:



```sql
COMMIT;
```



The first operation by session 1 acquires an exclusive lock
for the row. The operations by sessions 2 and 3 both result in
a duplicate-key error and they both request a shared lock for
the row. When session 1 commits, it releases its exclusive
lock on the row and the queued shared lock requests for
sessions 2 and 3 are granted. At this point, sessions 2 and 3
deadlock: Neither can acquire an exclusive lock for the row
because of the shared lock held by the other.


- [`INSERT\\
            ... ON DUPLICATE KEY UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/insert-on-duplicate.html "15.2.7.2 INSERT ... ON DUPLICATE KEY UPDATE Statement") differs from a simple
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") in that an exclusive
lock rather than a shared lock is placed on the row to be
updated when a duplicate-key error occurs. An exclusive
index-record lock is taken for a duplicate primary key value.
An exclusive next-key lock is taken for a duplicate unique key
value.


- [`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement") is done like an
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") if there is no collision
on a unique key. Otherwise, an exclusive next-key lock is
placed on the row to be replaced.


- `INSERT INTO T SELECT ... FROM S WHERE ...`
sets an exclusive index record lock (without a gap lock) on
each row inserted into `T`. If the
transaction isolation level is [`READ\\
            COMMITTED`](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html#isolevel_read-committed), `InnoDB` does the search
on `S` as a consistent read (no locks).
Otherwise, `InnoDB` sets shared next-key
locks on rows from `S`.
`InnoDB` has to set locks in the latter case:
During roll-forward recovery using a statement-based binary
log, every SQL statement must be executed in exactly the same
way it was done originally.


[`CREATE TABLE ...\\
            SELECT ...`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") performs the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") with shared next-key
locks or as a consistent read, as for
[`INSERT ...\\
            SELECT`](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement").



When a `SELECT` is used in the constructs
`REPLACE INTO t SELECT ... FROM s WHERE ...`
or `UPDATE t ... WHERE col IN (SELECT ... FROM s
            ...)`, `InnoDB` sets shared next-key
locks on rows from table `s`.


- `InnoDB` sets an exclusive lock on the end of
the index associated with the
`AUTO_INCREMENT` column while initializing a
previously specified `AUTO_INCREMENT` column
on a table.



With
[`innodb_autoinc_lock_mode=0`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_autoinc_lock_mode),
`InnoDB` uses a special
`AUTO-INC` table lock mode where the lock is
obtained and held to the end of the current SQL statement (not
to the end of the entire transaction) while accessing the
auto-increment counter. Other clients cannot insert into the
table while the `AUTO-INC` table lock is
held. The same behavior occurs for “bulk inserts”
with
[`innodb_autoinc_lock_mode=1`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_autoinc_lock_mode).
Table-level `AUTO-INC` locks are not used
with
[`innodb_autoinc_lock_mode=2`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_autoinc_lock_mode).
For more information, See
[Section 17.6.1.6, “AUTO\_INCREMENT Handling in InnoDB”](https://dev.mysql.com/doc/refman/8.0/en/innodb-auto-increment-handling.html "17.6.1.6 AUTO_INCREMENT Handling in InnoDB").


`InnoDB` fetches the value of a previously
initialized `AUTO_INCREMENT` column without
setting any locks.


- If a `FOREIGN KEY` constraint is defined on a
table, any insert, update, or delete that requires the
constraint condition to be checked sets shared record-level
locks on the records that it looks at to check the constraint.
`InnoDB` also sets these locks in the case
where the constraint fails.


- [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") sets table locks,
but it is the higher MySQL layer above the
`InnoDB` layer that sets these locks.
`InnoDB` is aware of table locks if
`innodb_table_locks = 1` (the default) and
[`autocommit = 0`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_autocommit), and the MySQL
layer above `InnoDB` knows about row-level
locks.



Otherwise, `InnoDB`'s automatic deadlock
detection cannot detect deadlocks where such table locks are
involved. Also, because in this case the higher MySQL layer
does not know about row-level locks, it is possible to get a
table lock on a table where another session currently has
row-level locks. However, this does not endanger transaction
integrity, as discussed in
[Section 17.7.5.2, “Deadlock Detection”](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlock-detection.html "17.7.5.2 Deadlock Detection").


- [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") acquires two locks
on each table if `innodb_table_locks=1` (the
default). In addition to a table lock on the MySQL layer, it
also acquires an `InnoDB` table lock. To
avoid acquiring `InnoDB` table locks, set
`innodb_table_locks=0`. If no
`InnoDB` table lock is acquired,
[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") completes even if
some records of the tables are being locked by other
transactions.



In MySQL 8.0,
[`innodb_table_locks=0`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_table_locks) has no
effect for tables locked explicitly with
[`LOCK TABLES ...\\
            WRITE`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements"). It does have an effect for tables locked for
read or write by
[`LOCK TABLES ...\\
            WRITE`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") implicitly (for example, through triggers) or
by [`LOCK TABLES\\
            ... READ`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements").


- All `InnoDB` locks held by a transaction are
released when the transaction is committed or aborted. Thus,
it does not make much sense to invoke
[`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") on
`InnoDB` tables in
[`autocommit=1`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_autocommit) mode because the
acquired `InnoDB` table locks would be
released immediately.


- You cannot lock additional tables in the middle of a
transaction because [`LOCK TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements")
performs an implicit [`COMMIT`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements") and
[`UNLOCK\\
            TABLES`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements").


[PREV](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-reads.html "Previous: Locking Reads") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html "Up: InnoDB Locking and Transaction Model") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/innodb-next-key-locking.html "Next: Phantom Rows")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html)

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