---
url: https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html
scraped_at: 2025-10-20T03:15:08.265Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html "Hide Sidebar")

[Previous: Change Buffer](https://dev.mysql.com/doc/refman/8.0/en/innodb-change-buffer.html "Previous: Change Buffer")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: InnoDB In-Memory Structures](https://dev.mysql.com/doc/refman/8.0/en/innodb-in-memory-structures.html "Up: InnoDB In-Memory Structures")[Next: Log Buffer](https://dev.mysql.com/doc/refman/8.0/en/innodb-redo-log-buffer.html "Next: Log Buffer")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/innodb-adaptive-hash.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/innodb-adaptive-hash.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/innodb-adaptive-hash.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/innodb-adaptive-hash.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/innodb-adaptive-hash.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/innodb-adaptive-hash.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/innodb-adaptive-hash.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/innodb-adaptive-hash.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html)  / [The InnoDB Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)  /
[InnoDB In-Memory Structures](https://dev.mysql.com/doc/refman/8.0/en/innodb-in-memory-structures.html)  /

Adaptive Hash Index


### 17.5.3 Adaptive Hash Index

The adaptive hash index enables `InnoDB` to
perform more like an in-memory database on systems with
appropriate combinations of workload and sufficient memory for the
buffer pool without sacrificing transactional features or
reliability. The adaptive hash index is enabled by the
[`innodb_adaptive_hash_index`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_adaptive_hash_index)
variable, or turned off at server startup by
`--skip-innodb-adaptive-hash-index`.


Based on the observed pattern of searches, a hash index is built
using a prefix of the index key. The prefix can be any length, and
it may be that only some values in the B-tree appear in the hash
index. Hash indexes are built on demand for the pages of the index
that are accessed often.


If a table fits almost entirely in main memory, a hash index
speeds up queries by enabling direct lookup of any element,
turning the index value into a sort of pointer.
`InnoDB` has a mechanism that monitors index
searches. If `InnoDB` notices that queries could
benefit from building a hash index, it does so automatically.


With some workloads, the speedup from hash index lookups greatly
outweighs the extra work to monitor index lookups and maintain the
hash index structure. Access to the adaptive hash index can
sometimes become a source of contention under heavy workloads,
such as multiple concurrent joins. Queries with
`LIKE` operators and `%`
wildcards also tend not to benefit. For workloads that do not
benefit from the adaptive hash index, turning it off reduces
unnecessary performance overhead. Because it is difficult to
predict in advance whether the adaptive hash index is appropriate
for a particular system and workload, consider running benchmarks
with it enabled and disabled.


The adaptive hash index feature is partitioned. Each index is
bound to a specific partition, and each partition is protected by
a separate latch. Partitioning is controlled by the
[`innodb_adaptive_hash_index_parts`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_adaptive_hash_index_parts)
variable. The
[`innodb_adaptive_hash_index_parts`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_adaptive_hash_index_parts)
variable is set to 8 by default. The maximum setting is 512.


You can monitor adaptive hash index use and contention in the
`SEMAPHORES` section of
[`SHOW ENGINE INNODB\\
      STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-engine.html "15.7.7.15 SHOW ENGINE Statement") output. If there are numerous threads waiting on
rw-latches created in `btr0sea.c`, consider
increasing the number of adaptive hash index partitions or
disabling the adaptive hash index.


For information about the performance characteristics of hash
indexes, see [Section 10.3.9, “Comparison of B-Tree and Hash Indexes”](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html "10.3.9 Comparison of B-Tree and Hash Indexes").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/innodb-change-buffer.html "Previous: Change Buffer") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/innodb-in-memory-structures.html "Up: InnoDB In-Memory Structures") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/innodb-redo-log-buffer.html "Next: Log Buffer")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html)

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