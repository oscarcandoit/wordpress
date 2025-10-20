---
url: https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html
scraped_at: 2025-10-20T03:03:09.902Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html "Hide Sidebar")

[Previous: Problems from Tables Not Being Closed Properly](https://dev.mysql.com/doc/refman/8.0/en/myisam-table-close.html "Previous: Problems from Tables Not Being Closed Properly")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Alternative Storage Engines](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html "Up: Alternative Storage Engines")[Next: The CSV Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html "Next: The CSV Storage Engine")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/memory-storage-engine.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/memory-storage-engine.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/memory-storage-engine.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/memory-storage-engine.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/memory-storage-engine.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/memory-storage-engine.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/memory-storage-engine.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/memory-storage-engine.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Alternative Storage Engines](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html)  /
The MEMORY Storage Engine


## 18.3 The MEMORY Storage Engine

The `MEMORY` storage engine (formerly known as
`HEAP`) creates special-purpose tables with
contents that are stored in memory. Because the data is vulnerable
to crashes, hardware issues, or power outages, only use these tables
as temporary work areas or read-only caches for data pulled from
other tables.

**Table 18.4 MEMORY Storage Engine Features**

| Feature | Support |
| --- | --- |
| **B-tree indexes** | Yes |
| **Backup/point-in-time recovery** (Implemented in the server, rather than in the storage engine.) | Yes |
| **Cluster database support** | No |
| **Clustered indexes** | No |
| **Compressed data** | No |
| **Data caches** | N/A |
| **Encrypted data** | Yes (Implemented in the server via encryption functions.) |
| **Foreign key support** | No |
| **Full-text search indexes** | No |
| **Geospatial data type support** | No |
| **Geospatial indexing support** | No |
| **Hash indexes** | Yes |
| **Index caches** | N/A |
| **Locking granularity** | Table |
| **MVCC** | No |
| **Replication support** (Implemented in the server, rather than in the storage engine.) | Limited (See the discussion later in this section.) |
| **Storage limits** | RAM |
| **T-tree indexes** | No |
| **Transactions** | No |
| **Update statistics for data dictionary** | Yes |

- [When to Use MEMORY or NDB Cluster](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html#memory-storage-engine-compared-cluster "When to Use MEMORY or NDB Cluster")

- [Partitioning](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html#memory-storage-engine-partitioning "Partitioning")

- [Performance Characteristics](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html#memory-storage-engine-performance-characteristics "Performance Characteristics")

- [Characteristics of MEMORY Tables](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html#memory-storage-engine-characteristics-of-memory-tables "Characteristics of MEMORY Tables")

- [DDL Operations for MEMORY Tables](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html#memory-storage-engine-ddl-operations-for-memory-tables "DDL Operations for MEMORY Tables")

- [Indexes](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html#memory-storage-engine-indexes "Indexes")

- [User-Created and Temporary Tables](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html#memory-storage-engine-user-created-and-temporary-tables "User-Created and Temporary Tables")

- [Loading Data](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html#memory-storage-engine-loading-data "Loading Data")

- [MEMORY Tables and Replication](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html#memory-tables-replication "MEMORY Tables and Replication")

- [Managing Memory Use](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html#memory-storage-engine-managing-memory-use "Managing Memory Use")

- [Additional Resources](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html#memory-storage-engine-additional-resources "Additional Resources")


### When to Use MEMORY or NDB Cluster

Developers looking to deploy applications that use the
`MEMORY` storage engine for important, highly
available, or frequently updated data should consider whether NDB
Cluster is a better choice. A typical use case for the
`MEMORY` engine involves these characteristics:

- Operations involving transient, non-critical data such as
session management or caching. When the MySQL server halts or
restarts, the data in `MEMORY` tables is
lost.


- In-memory storage for fast access and low latency. Data volume
can fit entirely in memory without causing the operating
system to swap out virtual memory pages.


- A read-only or read-mostly data access pattern (limited
updates).


NDB Cluster offers the same features as the
`MEMORY` engine with higher performance levels,
and provides additional features not available with
`MEMORY`:

- Row-level locking and multiple-thread operation for low
contention between clients.


- Scalability even with statement mixes that include writes.


- Optional disk-backed operation for data durability.


- Shared-nothing architecture and multiple-host operation with
no single point of failure, enabling 99.999% availability.


- Automatic data distribution across nodes; application
developers need not craft custom sharding or partitioning
solutions.


- Support for variable-length data types (including
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") and
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types")) not supported by
`MEMORY`.


### Partitioning

`MEMORY` tables cannot be partitioned.

### Performance Characteristics

`MEMORY` performance is constrained by contention
resulting from single-thread execution and table lock overhead
when processing updates. This limits scalability when load
increases, particularly for statement mixes that include writes.


Despite the in-memory processing for `MEMORY`
tables, they are not necessarily faster than
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") tables on a busy server, for
general-purpose queries, or under a read/write workload. In
particular, the table locking involved with performing updates can
slow down concurrent usage of `MEMORY` tables
from multiple sessions.


Depending on the kinds of queries performed on a
`MEMORY` table, you might create indexes as
either the default hash data structure (for looking up single
values based on a unique key), or a general-purpose B-tree data
structure (for all kinds of queries involving equality,
inequality, or range operators such as less than or greater than).
The following sections illustrate the syntax for creating both
kinds of indexes. A common performance issue is using the default
hash indexes in workloads where B-tree indexes are more efficient.

### Characteristics of MEMORY Tables

The `MEMORY` storage engine does not create any
files on disk. The table definition is stored in the MySQL data
dictionary.


`MEMORY` tables have the following
characteristics:

- Space for `MEMORY` tables is allocated in
small blocks. Tables use 100% dynamic hashing for inserts. No
overflow area or extra key space is needed. No extra space is
needed for free lists. Deleted rows are put in a linked list
and are reused when you insert new data into the table.
`MEMORY` tables also have none of the
problems commonly associated with deletes plus inserts in
hashed tables.


- `MEMORY` tables use a fixed-length
row-storage format. Variable-length types such as
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") are stored using a
fixed length.


- `MEMORY` tables cannot contain
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") or
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns.


- `MEMORY` includes support for
`AUTO_INCREMENT` columns.


- Non- `TEMPORARY` `MEMORY`
tables are shared among all clients, just like any other
non- `TEMPORARY` table.


### DDL Operations for MEMORY Tables

To create a `MEMORY` table, specify the clause
`ENGINE=MEMORY` on the
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement.


```sql
CREATE TABLE t (i INT) ENGINE = MEMORY;
```

As indicated by the engine name, `MEMORY` tables
are stored in memory. They use hash indexes by default, which
makes them very fast for single-value lookups, and very useful for
creating temporary tables. However, when the server shuts down,
all rows stored in `MEMORY` tables are lost. The
tables themselves continue to exist because their definitions are
stored in the MySQL data dictionary, but they are empty when the
server restarts.


This example shows how you might create, use, and remove a
`MEMORY` table:


```sql
mysql> CREATE TABLE test ENGINE=MEMORY
           SELECT ip,SUM(downloads) AS down
           FROM log_table GROUP BY ip;
mysql> SELECT COUNT(ip),AVG(down) FROM test;
mysql> DROP TABLE test;
```

The maximum size of `MEMORY` tables is limited by
the [`max_heap_table_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_heap_table_size) system
variable, which has a default value of 16MB. To enforce different
size limits for `MEMORY` tables, change the value
of this variable. The value in effect for
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"), or a subsequent
[`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") or
[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement"), is the value used
for the life of the table. A server restart also sets the maximum
size of existing `MEMORY` tables to the global
[`max_heap_table_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_heap_table_size) value. You
can set the size for individual tables as described later in this
section.

### Indexes

The `MEMORY` storage engine supports both
`HASH` and `BTREE` indexes. You
can specify one or the other for a given index by adding a
`USING` clause as shown here:


```sql
CREATE TABLE lookup
    (id INT, INDEX USING HASH (id))
    ENGINE = MEMORY;
CREATE TABLE lookup
    (id INT, INDEX USING BTREE (id))
    ENGINE = MEMORY;
```

For general characteristics of B-tree and hash indexes, see
[Section 10.3.1, “How MySQL Uses Indexes”](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html "10.3.1 How MySQL Uses Indexes").


`MEMORY` tables can have up to 64 indexes per
table, 16 columns per index and a maximum key length of 3072
bytes.


If a `MEMORY` table hash index has a high degree
of key duplication (many index entries containing the same value),
updates to the table that affect key values and all deletes are
significantly slower. The degree of this slowdown is proportional
to the degree of duplication (or, inversely proportional to the
index cardinality). You can use a `BTREE` index
to avoid this problem.


`MEMORY` tables can have nonunique keys. (This is
an uncommon feature for implementations of hash indexes.)


Columns that are indexed can contain `NULL`
values.

### User-Created and Temporary Tables

`MEMORY` table contents are stored in memory,
which is a property that `MEMORY` tables share
with internal temporary tables that the server creates on the fly
while processing queries. However, the two types of tables differ
in that `MEMORY` tables are not subject to
storage conversion, whereas internal temporary tables are:

- If an internal temporary table becomes too large, the server
automatically converts it to on-disk storage, as described in
[Section 10.4.4, “Internal Temporary Table Use in MySQL”](https://dev.mysql.com/doc/refman/8.0/en/internal-temporary-tables.html "10.4.4 Internal Temporary Table Use in MySQL").


- User-created `MEMORY` tables are never
converted to disk tables.


### Loading Data

To populate a `MEMORY` table when the MySQL
server starts, you can use the
[`init_file`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_init_file) system variable. For
example, you can put statements such as
[`INSERT INTO ...\\
      SELECT`](https://dev.mysql.com/doc/refman/8.0/en/insert-select.html "15.2.7.1 INSERT ... SELECT Statement") or [`LOAD DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement") into
a file to load the table from a persistent data source, and use
[`init_file`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_init_file) to name the file. See
[Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables"), and
[Section 15.2.9, “LOAD DATA Statement”](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement").

### MEMORY Tables and Replication

When a replication source server shuts down and restarts, its
[`MEMORY`](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html "18.3 The MEMORY Storage Engine") tables become empty. To
replicate this effect to replicas, the first time that the source
uses a given [`MEMORY`](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html "18.3 The MEMORY Storage Engine") table after
startup, it logs an event that notifies replicas that the table
must be emptied by writing a [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement")
or (from MySQL 8.0.22) [`TRUNCATE\\
      TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") statement for that table to the binary log. When a
replica server shuts down and restarts, its
[`MEMORY`](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html "18.3 The MEMORY Storage Engine") tables also become empty, and
it writes a [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") or (from MySQL
8.0.22) [`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") statement to
its own binary log, which is passed on to any downstream replicas.


When you use [`MEMORY`](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html "18.3 The MEMORY Storage Engine") tables in a
replication topology, in some situations, the table on the source
and the table on the replica can differ. For information on
handling each of these situations to prevent stale reads or
errors, see [Section 19.5.1.21, “Replication and MEMORY Tables”](https://dev.mysql.com/doc/refman/8.0/en/replication-features-memory.html "19.5.1.21 Replication and MEMORY Tables").

### Managing Memory Use

The server needs sufficient memory to maintain all
`MEMORY` tables that are in use at the same time.


Memory is not reclaimed if you delete individual rows from a
`MEMORY` table. Memory is reclaimed only when the
entire table is deleted. Memory that was previously used for
deleted rows is re-used for new rows within the same table. To
free all the memory used by a `MEMORY` table when
you no longer require its contents, execute
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") or
[`TRUNCATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html "15.1.37 TRUNCATE TABLE Statement") to remove all rows,
or remove the table altogether using [`DROP\\
      TABLE`](https://dev.mysql.com/doc/refman/8.0/en/drop-table.html "15.1.32 DROP TABLE Statement"). To free up the memory used by deleted rows, use
`ALTER TABLE ENGINE=MEMORY` to force a table
rebuild.


The memory needed for one row in a `MEMORY` table
is calculated using the following expression:


```sql
SUM_OVER_ALL_BTREE_KEYS(max_length_of_key + sizeof(char*) * 4)
+ SUM_OVER_ALL_HASH_KEYS(sizeof(char*) * 2)
+ ALIGN(length_of_row+1, sizeof(char*))
```

`ALIGN()` represents a round-up factor to cause
the row length to be an exact multiple of the
`char` pointer size.
`sizeof(char*)` is 4 on 32-bit machines and 8 on
64-bit machines.


As mentioned earlier, the
[`max_heap_table_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_heap_table_size) system
variable sets the limit on the maximum size of
`MEMORY` tables. To control the maximum size for
individual tables, set the session value of this variable before
creating each table. (Do not change the global
[`max_heap_table_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_heap_table_size) value unless
you intend the value to be used for `MEMORY`
tables created by all clients.) The following example creates two
`MEMORY` tables, with a maximum size of 1MB and
2MB, respectively:


```sql
mysql> SET max_heap_table_size = 1024*1024;
Query OK, 0 rows affected (0.00 sec)

mysql> CREATE TABLE t1 (id INT, UNIQUE(id)) ENGINE = MEMORY;
Query OK, 0 rows affected (0.01 sec)

mysql> SET max_heap_table_size = 1024*1024*2;
Query OK, 0 rows affected (0.00 sec)

mysql> CREATE TABLE t2 (id INT, UNIQUE(id)) ENGINE = MEMORY;
Query OK, 0 rows affected (0.00 sec)
```

Both tables revert to the server's global
[`max_heap_table_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_heap_table_size) value if the
server restarts.


You can also specify a `MAX_ROWS` table option in
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statements for
`MEMORY` tables to provide a hint about the
number of rows you plan to store in them. This does not enable the
table to grow beyond the
[`max_heap_table_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_heap_table_size) value, which
still acts as a constraint on maximum table size. For maximum
flexibility in being able to use `MAX_ROWS`, set
[`max_heap_table_size`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_heap_table_size) at least as
high as the value to which you want each `MEMORY`
table to be able to grow.

### Additional Resources

A forum dedicated to the `MEMORY` storage engine
is available at [https://forums.mysql.com/list.php?92](https://forums.mysql.com/list.php?92).

[PREV](https://dev.mysql.com/doc/refman/8.0/en/myisam-table-close.html "Previous: Problems from Tables Not Being Closed Properly") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html "Up: Alternative Storage Engines") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html "Next: The CSV Storage Engine")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html)

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