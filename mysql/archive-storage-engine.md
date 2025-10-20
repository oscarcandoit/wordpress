---
url: https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html
scraped_at: 2025-10-20T03:03:16.180Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html "Hide Sidebar")

[Previous: CSV Limitations](https://dev.mysql.com/doc/refman/8.0/en/se-csv-limitations.html "Previous: CSV Limitations")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Alternative Storage Engines](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html "Up: Alternative Storage Engines")[Next: The BLACKHOLE Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/blackhole-storage-engine.html "Next: The BLACKHOLE Storage Engine")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/archive-storage-engine.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/archive-storage-engine.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/archive-storage-engine.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/archive-storage-engine.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/archive-storage-engine.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/archive-storage-engine.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/archive-storage-engine.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/archive-storage-engine.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Alternative Storage Engines](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html)  /
The ARCHIVE Storage Engine


## 18.5 The ARCHIVE Storage Engine

The `ARCHIVE` storage engine produces
special-purpose tables that store large amounts of unindexed data in
a very small footprint.

**Table 18.5 ARCHIVE Storage Engine Features**

| Feature | Support |
| --- | --- |
| **B-tree indexes** | No |
| **Backup/point-in-time recovery** (Implemented in the server, rather than in the storage engine.) | Yes |
| **Cluster database support** | No |
| **Clustered indexes** | No |
| **Compressed data** | Yes |
| **Data caches** | No |
| **Encrypted data** | Yes (Implemented in the server via encryption functions.) |
| **Foreign key support** | No |
| **Full-text search indexes** | No |
| **Geospatial data type support** | Yes |
| **Geospatial indexing support** | No |
| **Hash indexes** | No |
| **Index caches** | No |
| **Locking granularity** | Row |
| **MVCC** | No |
| **Replication support** (Implemented in the server, rather than in the storage engine.) | Yes |
| **Storage limits** | None |
| **T-tree indexes** | No |
| **Transactions** | No |
| **Update statistics for data dictionary** | Yes |

The `ARCHIVE` storage engine is included in MySQL
binary distributions. To enable this storage engine if you build
MySQL from source, invoke **CMake** with the
[`-DWITH_ARCHIVE_STORAGE_ENGINE`](https://dev.mysql.com/doc/refman/8.0/en/source-configuration-options.html#option_cmake_storage_engine_options "Storage Engine Options")
option.


To examine the source for the `ARCHIVE` engine,
look in the `storage/archive` directory of a
MySQL source distribution.


You can check whether the `ARCHIVE` storage engine
is available with the [`SHOW ENGINES`](https://dev.mysql.com/doc/refman/8.0/en/show-engines.html "15.7.7.16 SHOW ENGINES Statement")
statement.


When you create an `ARCHIVE` table, the storage
engine creates files with names that begin with the table name. The
data file has an extension of `.ARZ`. An
`.ARN` file may appear during optimization
operations.


The `ARCHIVE` engine supports
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"),
[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement"), and
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"), but not
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") or
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement"). It does support
`ORDER BY` operations,
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns, and spatial data types
(see [Section 13.4.1, “Spatial Data Types”](https://dev.mysql.com/doc/refman/8.0/en/spatial-type-overview.html "13.4.1 Spatial Data Types")). Geographic spatial
reference systems are not supported. The `ARCHIVE`
engine uses row-level locking.


The `ARCHIVE` engine supports the
`AUTO_INCREMENT` column attribute. The
`AUTO_INCREMENT` column can have either a unique or
nonunique index. Attempting to create an index on any other column
results in an error. The `ARCHIVE` engine also
supports the `AUTO_INCREMENT` table option in
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statements to specify
the initial sequence value for a new table or reset the sequence
value for an existing table, respectively.


`ARCHIVE` does not support inserting a value into
an `AUTO_INCREMENT` column less than the current
maximum column value. Attempts to do so result in an
[`ER_DUP_KEY`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_dup_key) error.


The `ARCHIVE` engine ignores
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns if they are not
requested and scans past them while reading.


The `ARCHIVE` storage engine does not support
partitioning.


**Storage:** Rows are compressed as
they are inserted. The `ARCHIVE` engine uses
`zlib` lossless data compression (see
[http://www.zlib.net/](http://www.zlib.net/)). You can use
[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") to analyze the table
and pack it into a smaller format (for a reason to use
[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement"), see later in this
section). The engine also supports [`CHECK\\
    TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement"). There are several types of insertions that are
used:

- An [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement just pushes
rows into a compression buffer, and that buffer flushes as
necessary. The insertion into the buffer is protected by a lock.
A [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") forces a flush to occur.


- A bulk insert is visible only after it completes, unless other
inserts occur at the same time, in which case it can be seen
partially. A [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") never causes
a flush of a bulk insert unless a normal insert occurs while it
is loading.


**Retrieval**: On retrieval, rows are
uncompressed on demand; there is no row cache. A
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") operation performs a complete
table scan: When a [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") occurs, it
finds out how many rows are currently available and reads that
number of rows. [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") is performed
as a consistent read. Note that lots of
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements during insertion
can deteriorate the compression, unless only bulk inserts are used.
To achieve better compression, you can use
[`OPTIMIZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement") or
[`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement"). The number of rows in
`ARCHIVE` tables reported by
[`SHOW TABLE STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement") is always accurate.
See [Section 15.7.3.4, “OPTIMIZE TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html "15.7.3.4 OPTIMIZE TABLE Statement"),
[Section 15.7.3.5, “REPAIR TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement"), and
[Section 15.7.7.38, “SHOW TABLE STATUS Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement").

### Additional Resources

- A forum dedicated to the `ARCHIVE` storage
engine is available at [https://forums.mysql.com/list.php?112](https://forums.mysql.com/list.php?112).


[PREV](https://dev.mysql.com/doc/refman/8.0/en/se-csv-limitations.html "Previous: CSV Limitations") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html "Up: Alternative Storage Engines") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/blackhole-storage-engine.html "Next: The BLACKHOLE Storage Engine")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/archive-storage-engine.html)

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