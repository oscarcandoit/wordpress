---
url: https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html
scraped_at: 2025-10-20T03:12:27.972Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html "Hide Sidebar")

[Previous: InnoDB Locking and Transaction Model](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html "Previous: InnoDB Locking and Transaction Model")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: InnoDB Locking and Transaction Model](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html "Up: InnoDB Locking and Transaction Model")[Next: InnoDB Transaction Model](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-model.html "Next: InnoDB Transaction Model")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/innodb-locking.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/innodb-locking.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/innodb-locking.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/innodb-locking.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/innodb-locking.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/innodb-locking.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/innodb-locking.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/innodb-locking.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html)  / [The InnoDB Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)  /
[InnoDB Locking and Transaction Model](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html)  /

InnoDB Locking


### 17.7.1 InnoDB Locking

This section describes lock types used by
`InnoDB`.

- [Shared and Exclusive Locks](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html#innodb-shared-exclusive-locks "Shared and Exclusive Locks")

- [Intention Locks](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html#innodb-intention-locks "Intention Locks")

- [Record Locks](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html#innodb-record-locks "Record Locks")

- [Gap Locks](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html#innodb-gap-locks "Gap Locks")

- [Next-Key Locks](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html#innodb-next-key-locks "Next-Key Locks")

- [Insert Intention Locks](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html#innodb-insert-intention-locks "Insert Intention Locks")

- [AUTO-INC Locks](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html#innodb-auto-inc-locks "AUTO-INC Locks")

- [Predicate Locks for Spatial Indexes](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html#innodb-predicate-locks "Predicate Locks for Spatial Indexes")


#### Shared and Exclusive Locks

`InnoDB` implements standard row-level locking
where there are two types of locks,
[shared ( `S`)\\
locks](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_shared_lock "shared lock") and [exclusive\\
( `X`) locks](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_exclusive_lock "exclusive lock").

- A [shared\\
( `S`) lock](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_shared_lock "shared lock") permits the transaction
that holds the lock to read a row.


- An [exclusive\\
( `X`) lock](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_exclusive_lock "exclusive lock") permits the transaction
that holds the lock to update or delete a row.


If transaction `T1` holds a shared
( `S`) lock on row `r`, then
requests from some distinct transaction `T2`
for a lock on row `r` are handled as follows:

- A request by `T2` for an
`S` lock can be granted immediately. As a
result, both `T1` and `T2`
hold an `S` lock on `r`.


- A request by `T2` for an
`X` lock cannot be granted immediately.


If a transaction `T1` holds an exclusive
( `X`) lock on row `r`, a
request from some distinct transaction `T2` for
a lock of either type on `r` cannot be granted
immediately. Instead, transaction `T2` has to
wait for transaction `T1` to release its lock
on row `r`.

#### Intention Locks

`InnoDB` supports _multiple_
_granularity locking_ which permits coexistence of row
locks and table locks. For example, a statement such as
[`LOCK TABLES ...\\
        WRITE`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements") takes an exclusive lock (an `X`
lock) on the specified table. To make locking at multiple
granularity levels practical, `InnoDB` uses
[intention locks](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_intention_lock "intention lock").
Intention locks are table-level locks that indicate which type
of lock (shared or exclusive) a transaction requires later for a
row in a table. There are two types of intention locks:

- An [intention\\
shared lock](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_intention_shared_lock "intention shared lock") ( `IS`) indicates that a
transaction intends to set a _shared_
lock on individual rows in a table.


- An [intention\\
exclusive lock](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_intention_exclusive_lock "intention exclusive lock") ( `IX`) indicates that
a transaction intends to set an exclusive lock on individual
rows in a table.


For example, [`SELECT ...\\
        FOR SHARE`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") sets an `IS` lock, and
[`SELECT ... FOR\\
        UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") sets an `IX` lock.


The intention locking protocol is as follows:

- Before a transaction can acquire a shared lock on a row in a
table, it must first acquire an `IS` lock
or stronger on the table.


- Before a transaction can acquire an exclusive lock on a row
in a table, it must first acquire an `IX`
lock on the table.


Table-level lock type compatibility is summarized in the
following matrix.

|  | `X` | `IX` | `S` | `IS` |
| --- | --- | --- | --- | --- |
| `X` | Conflict | Conflict | Conflict | Conflict |
| `IX` | Conflict | Compatible | Conflict | Compatible |
| `S` | Conflict | Conflict | Compatible | Compatible |
| `IS` | Conflict | Compatible | Compatible | Compatible |

A lock is granted to a requesting transaction if it is
compatible with existing locks, but not if it conflicts with
existing locks. A transaction waits until the conflicting
existing lock is released. If a lock request conflicts with an
existing lock and cannot be granted because it would cause
[deadlock](https://dev.mysql.com/doc/refman/8.0/en/glossary.html#glos_deadlock "deadlock"), an error occurs.


Intention locks do not block anything except full table requests
(for example, [`LOCK\\
        TABLES ... WRITE`](https://dev.mysql.com/doc/refman/8.0/en/lock-tables.html "15.3.6 LOCK TABLES and UNLOCK TABLES Statements")). The main purpose of intention locks
is to show that someone is locking a row, or going to lock a row
in the table.


Transaction data for an intention lock appears similar to the
following in [`SHOW\\
        ENGINE INNODB STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-engine.html "15.7.7.15 SHOW ENGINE Statement") and
[InnoDB monitor](https://dev.mysql.com/doc/refman/8.0/en/innodb-standard-monitor.html "17.17.3 InnoDB Standard Monitor and Lock Monitor Output")
output:


```sql
TABLE LOCK table `test`.`t` trx id 10080 lock mode IX
```

#### Record Locks

A record lock is a lock on an index record. For example,
`SELECT c1 FROM t WHERE c1 = 10 FOR UPDATE;`
prevents any other transaction from inserting, updating, or
deleting rows where the value of `t.c1` is
`10`.


Record locks always lock index records, even if a table is
defined with no indexes. For such cases,
`InnoDB` creates a hidden clustered index and
uses this index for record locking. See
[Section 17.6.2.1, “Clustered and Secondary Indexes”](https://dev.mysql.com/doc/refman/8.0/en/innodb-index-types.html "17.6.2.1 Clustered and Secondary Indexes").


Transaction data for a record lock appears similar to the
following in [`SHOW\\
        ENGINE INNODB STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-engine.html "15.7.7.15 SHOW ENGINE Statement") and
[InnoDB monitor](https://dev.mysql.com/doc/refman/8.0/en/innodb-standard-monitor.html "17.17.3 InnoDB Standard Monitor and Lock Monitor Output")
output:


```sql
RECORD LOCKS space id 58 page no 3 n bits 72 index `PRIMARY` of table `test`.`t`
trx id 10078 lock_mode X locks rec but not gap
Record lock, heap no 2 PHYSICAL RECORD: n_fields 3; compact format; info bits 0
 0: len 4; hex 8000000a; asc     ;;
 1: len 6; hex 00000000274f; asc     'O;;
 2: len 7; hex b60000019d0110; asc        ;;
```

#### Gap Locks

A gap lock is a lock on a gap between index records, or a lock
on the gap before the first or after the last index record. For
example, `SELECT c1 FROM t WHERE c1 BETWEEN 10 and 20
        FOR UPDATE;` prevents other transactions from inserting
a value of `15` into column
`t.c1`, whether or not there was already any
such value in the column, because the gaps between all existing
values in the range are locked.


A gap might span a single index value, multiple index values, or
even be empty.


Gap locks are part of the tradeoff between performance and
concurrency, and are used in some transaction isolation levels
and not others.


Gap locking is not needed for statements that lock rows using a
unique index to search for a unique row. (This does not include
the case that the search condition includes only some columns of
a multiple-column unique index; in that case, gap locking does
occur.) For example, if the `id` column has a
unique index, the following statement uses only an index-record
lock for the row having `id` value 100 and it
does not matter whether other sessions insert rows in the
preceding gap:


```sql
SELECT * FROM child WHERE id = 100;
```

If `id` is not indexed or has a nonunique
index, the statement does lock the preceding gap.


It is also worth noting here that conflicting locks can be held
on a gap by different transactions. For example, transaction A
can hold a shared gap lock (gap S-lock) on a gap while
transaction B holds an exclusive gap lock (gap X-lock) on the
same gap. The reason conflicting gap locks are allowed is that
if a record is purged from an index, the gap locks held on the
record by different transactions must be merged.


Gap locks in `InnoDB` are “purely
inhibitive”, which means that their only purpose is to
prevent other transactions from inserting to the gap. Gap locks
can co-exist. A gap lock taken by one transaction does not
prevent another transaction from taking a gap lock on the same
gap. There is no difference between shared and exclusive gap
locks. They do not conflict with each other, and they perform
the same function.


Gap locking can be disabled explicitly. This occurs if you
change the transaction isolation level to
[`READ COMMITTED`](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html#isolevel_read-committed). In this case,
gap locking is disabled for searches and index scans and is used
only for foreign-key constraint checking and duplicate-key
checking.


There are also other effects of using the
[`READ COMMITTED`](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html#isolevel_read-committed) isolation
level. Record locks for nonmatching rows are released after
MySQL has evaluated the `WHERE` condition. For
`UPDATE` statements, `InnoDB`
does a “semi-consistent” read, such that it returns
the latest committed version to MySQL so that MySQL can
determine whether the row matches the `WHERE`
condition of the [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement").

#### Next-Key Locks

A next-key lock is a combination of a record lock on the index
record and a gap lock on the gap before the index record.


`InnoDB` performs row-level locking in such a
way that when it searches or scans a table index, it sets shared
or exclusive locks on the index records it encounters. Thus, the
row-level locks are actually index-record locks. A next-key lock
on an index record also affects the “gap” before
that index record. That is, a next-key lock is an index-record
lock plus a gap lock on the gap preceding the index record. If
one session has a shared or exclusive lock on record
`R` in an index, another session cannot insert
a new index record in the gap immediately before
`R` in the index order.


Suppose that an index contains the values 10, 11, 13, and 20.
The possible next-key locks for this index cover the following
intervals, where a round bracket denotes exclusion of the
interval endpoint and a square bracket denotes inclusion of the
endpoint:


```none
(negative infinity, 10]
(10, 11]
(11, 13]
(13, 20]
(20, positive infinity)
```

For the last interval, the next-key lock locks the gap above the
largest value in the index and the “supremum”
pseudo-record having a value higher than any value actually in
the index. The supremum is not a real index record, so, in
effect, this next-key lock locks only the gap following the
largest index value.


By default, `InnoDB` operates in
[`REPEATABLE READ`](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html#isolevel_repeatable-read) transaction
isolation level. In this case, `InnoDB` uses
next-key locks for searches and index scans, which prevents
phantom rows (see [Section 17.7.4, “Phantom Rows”](https://dev.mysql.com/doc/refman/8.0/en/innodb-next-key-locking.html "17.7.4 Phantom Rows")).


Transaction data for a next-key lock appears similar to the
following in [`SHOW\\
        ENGINE INNODB STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-engine.html "15.7.7.15 SHOW ENGINE Statement") and
[InnoDB monitor](https://dev.mysql.com/doc/refman/8.0/en/innodb-standard-monitor.html "17.17.3 InnoDB Standard Monitor and Lock Monitor Output")
output:


```sql
RECORD LOCKS space id 58 page no 3 n bits 72 index `PRIMARY` of table `test`.`t`
trx id 10080 lock_mode X
Record lock, heap no 1 PHYSICAL RECORD: n_fields 1; compact format; info bits 0
 0: len 8; hex 73757072656d756d; asc supremum;;

Record lock, heap no 2 PHYSICAL RECORD: n_fields 3; compact format; info bits 0
 0: len 4; hex 8000000a; asc     ;;
 1: len 6; hex 00000000274f; asc     'O;;
 2: len 7; hex b60000019d0110; asc        ;;
```

#### Insert Intention Locks

An insert intention lock is a type of gap lock set by
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") operations prior to row
insertion. This lock signals the intent to insert in such a way
that multiple transactions inserting into the same index gap
need not wait for each other if they are not inserting at the
same position within the gap. Suppose that there are index
records with values of 4 and 7. Separate transactions that
attempt to insert values of 5 and 6, respectively, each lock the
gap between 4 and 7 with insert intention locks prior to
obtaining the exclusive lock on the inserted row, but do not
block each other because the rows are nonconflicting.


The following example demonstrates a transaction taking an
insert intention lock prior to obtaining an exclusive lock on
the inserted record. The example involves two clients, A and B.


Client A creates a table containing two index records (90 and
102) and then starts a transaction that places an exclusive lock
on index records with an ID greater than 100. The exclusive lock
includes a gap lock before record 102:


```sql
mysql> CREATE TABLE child (id int(11) NOT NULL, PRIMARY KEY(id)) ENGINE=InnoDB;
mysql> INSERT INTO child (id) values (90),(102);

mysql> START TRANSACTION;
mysql> SELECT * FROM child WHERE id > 100 FOR UPDATE;
+-----+
| id  |
+-----+
| 102 |
+-----+
```

Client B begins a transaction to insert a record into the gap.
The transaction takes an insert intention lock while it waits to
obtain an exclusive lock.


```sql
mysql> START TRANSACTION;
mysql> INSERT INTO child (id) VALUES (101);
```

Transaction data for an insert intention lock appears similar to
the following in
[`SHOW ENGINE INNODB\\
        STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-engine.html "15.7.7.15 SHOW ENGINE Statement") and
[InnoDB monitor](https://dev.mysql.com/doc/refman/8.0/en/innodb-standard-monitor.html "17.17.3 InnoDB Standard Monitor and Lock Monitor Output")
output:


```sql
RECORD LOCKS space id 31 page no 3 n bits 72 index `PRIMARY` of table `test`.`child`
trx id 8731 lock_mode X locks gap before rec insert intention waiting
Record lock, heap no 3 PHYSICAL RECORD: n_fields 3; compact format; info bits 0
 0: len 4; hex 80000066; asc    f;;
 1: len 6; hex 000000002215; asc     " ;;
 2: len 7; hex 9000000172011c; asc     r  ;;...
```

#### AUTO-INC Locks

An `AUTO-INC` lock is a special table-level
lock taken by transactions inserting into tables with
`AUTO_INCREMENT` columns. In the simplest case,
if one transaction is inserting values into the table, any other
transactions must wait to do their own inserts into that table,
so that rows inserted by the first transaction receive
consecutive primary key values.


The [`innodb_autoinc_lock_mode`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_autoinc_lock_mode)
variable controls the algorithm used for auto-increment locking.
It allows you to choose how to trade off between predictable
sequences of auto-increment values and maximum concurrency for
insert operations.


For more information, see
[Section 17.6.1.6, “AUTO\_INCREMENT Handling in InnoDB”](https://dev.mysql.com/doc/refman/8.0/en/innodb-auto-increment-handling.html "17.6.1.6 AUTO_INCREMENT Handling in InnoDB").

#### Predicate Locks for Spatial Indexes

`InnoDB` supports `SPATIAL`
indexing of columns containing spatial data (see
[Section 13.4.9, “Optimizing Spatial Analysis”](https://dev.mysql.com/doc/refman/8.0/en/optimizing-spatial-analysis.html "13.4.9 Optimizing Spatial Analysis")).


To handle locking for operations involving
`SPATIAL` indexes, next-key locking does not
work well to support [`REPEATABLE\\
        READ`](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html#isolevel_repeatable-read) or
[`SERIALIZABLE`](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html#isolevel_serializable) transaction
isolation levels. There is no absolute ordering concept in
multidimensional data, so it is not clear which is the
“next” key.


To enable support of isolation levels for tables with
`SPATIAL` indexes, `InnoDB`
uses predicate locks. A `SPATIAL` index
contains minimum bounding rectangle (MBR) values, so
`InnoDB` enforces consistent read on the index
by setting a predicate lock on the MBR value used for a query.
Other transactions cannot insert or modify a row that would
match the query condition.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html "Previous: InnoDB Locking and Transaction Model") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html "Up: InnoDB Locking and Transaction Model") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-model.html "Next: InnoDB Transaction Model")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html)

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