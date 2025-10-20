---
url: https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html
scraped_at: 2025-10-20T03:03:01.217Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Hide Sidebar")

[Previous: Data Dictionary Limitations](https://dev.mysql.com/doc/refman/8.0/en/data-dictionary-limitations.html "Previous: Data Dictionary Limitations")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up")[Next: Introduction to InnoDB](https://dev.mysql.com/doc/refman/8.0/en/innodb-introduction.html "Next: Introduction to InnoDB")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/innodb-storage-engine.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/innodb-storage-engine.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/innodb-storage-engine.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/innodb-storage-engine.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/innodb-storage-engine.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/innodb-storage-engine.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/innodb-storage-engine.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/innodb-storage-engine.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
The InnoDB Storage Engine


# Chapter 17 The InnoDB Storage Engine

**Table of Contents**

[17.1 Introduction to InnoDB](https://dev.mysql.com/doc/refman/8.0/en/innodb-introduction.html)[17.1.1 Benefits of Using InnoDB Tables](https://dev.mysql.com/doc/refman/8.0/en/innodb-benefits.html)[17.1.2 Best Practices for InnoDB Tables](https://dev.mysql.com/doc/refman/8.0/en/innodb-best-practices.html)[17.1.3 Verifying that InnoDB is the Default Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-check-availability.html)[17.1.4 Testing and Benchmarking with InnoDB](https://dev.mysql.com/doc/refman/8.0/en/innodb-benchmarking.html)[17.2 InnoDB and the ACID Model](https://dev.mysql.com/doc/refman/8.0/en/mysql-acid.html)[17.3 InnoDB Multi-Versioning](https://dev.mysql.com/doc/refman/8.0/en/innodb-multi-versioning.html)[17.4 InnoDB Architecture](https://dev.mysql.com/doc/refman/8.0/en/innodb-architecture.html)[17.5 InnoDB In-Memory Structures](https://dev.mysql.com/doc/refman/8.0/en/innodb-in-memory-structures.html)[17.5.1 Buffer Pool](https://dev.mysql.com/doc/refman/8.0/en/innodb-buffer-pool.html)[17.5.2 Change Buffer](https://dev.mysql.com/doc/refman/8.0/en/innodb-change-buffer.html)[17.5.3 Adaptive Hash Index](https://dev.mysql.com/doc/refman/8.0/en/innodb-adaptive-hash.html)[17.5.4 Log Buffer](https://dev.mysql.com/doc/refman/8.0/en/innodb-redo-log-buffer.html)[17.6 InnoDB On-Disk Structures](https://dev.mysql.com/doc/refman/8.0/en/innodb-on-disk-structures.html)[17.6.1 Tables](https://dev.mysql.com/doc/refman/8.0/en/innodb-tables.html)[17.6.2 Indexes](https://dev.mysql.com/doc/refman/8.0/en/innodb-indexes.html)[17.6.3 Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)[17.6.4 Doublewrite Buffer](https://dev.mysql.com/doc/refman/8.0/en/innodb-doublewrite-buffer.html)[17.6.5 Redo Log](https://dev.mysql.com/doc/refman/8.0/en/innodb-redo-log.html)[17.6.6 Undo Logs](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html)[17.7 InnoDB Locking and Transaction Model](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-transaction-model.html)[17.7.1 InnoDB Locking](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html)[17.7.2 InnoDB Transaction Model](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-model.html)[17.7.3 Locks Set by Different SQL Statements in InnoDB](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html)[17.7.4 Phantom Rows](https://dev.mysql.com/doc/refman/8.0/en/innodb-next-key-locking.html)[17.7.5 Deadlocks in InnoDB](https://dev.mysql.com/doc/refman/8.0/en/innodb-deadlocks.html)[17.7.6 Transaction Scheduling](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-scheduling.html)[17.8 InnoDB Configuration](https://dev.mysql.com/doc/refman/8.0/en/innodb-configuration.html)[17.8.1 InnoDB Startup Configuration](https://dev.mysql.com/doc/refman/8.0/en/innodb-init-startup-configuration.html)[17.8.2 Configuring InnoDB for Read-Only Operation](https://dev.mysql.com/doc/refman/8.0/en/innodb-read-only-instance.html)[17.8.3 InnoDB Buffer Pool Configuration](https://dev.mysql.com/doc/refman/8.0/en/innodb-performance-buffer-pool.html)[17.8.4 Configuring Thread Concurrency for InnoDB](https://dev.mysql.com/doc/refman/8.0/en/innodb-performance-thread_concurrency.html)[17.8.5 Configuring the Number of Background InnoDB I/O Threads](https://dev.mysql.com/doc/refman/8.0/en/innodb-performance-multiple_io_threads.html)[17.8.6 Using Asynchronous I/O on Linux](https://dev.mysql.com/doc/refman/8.0/en/innodb-linux-native-aio.html)[17.8.7 Configuring InnoDB I/O Capacity](https://dev.mysql.com/doc/refman/8.0/en/innodb-configuring-io-capacity.html)[17.8.8 Configuring Spin Lock Polling](https://dev.mysql.com/doc/refman/8.0/en/innodb-performance-spin_lock_polling.html)[17.8.9 Purge Configuration](https://dev.mysql.com/doc/refman/8.0/en/innodb-purge-configuration.html)[17.8.10 Configuring Optimizer Statistics for InnoDB](https://dev.mysql.com/doc/refman/8.0/en/innodb-performance-optimizer-statistics.html)[17.8.11 Configuring the Merge Threshold for Index Pages](https://dev.mysql.com/doc/refman/8.0/en/index-page-merge-threshold.html)[17.8.12 Enabling Automatic InnoDB Configuration for a Dedicated MySQL Server](https://dev.mysql.com/doc/refman/8.0/en/innodb-dedicated-server.html)[17.9 InnoDB Table and Page Compression](https://dev.mysql.com/doc/refman/8.0/en/innodb-compression.html)[17.9.1 InnoDB Table Compression](https://dev.mysql.com/doc/refman/8.0/en/innodb-table-compression.html)[17.9.2 InnoDB Page Compression](https://dev.mysql.com/doc/refman/8.0/en/innodb-page-compression.html)[17.10 InnoDB Row Formats](https://dev.mysql.com/doc/refman/8.0/en/innodb-row-format.html)[17.11 InnoDB Disk I/O and File Space Management](https://dev.mysql.com/doc/refman/8.0/en/innodb-disk-management.html)[17.11.1 InnoDB Disk I/O](https://dev.mysql.com/doc/refman/8.0/en/innodb-disk-io.html)[17.11.2 File Space Management](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-space.html)[17.11.3 InnoDB Checkpoints](https://dev.mysql.com/doc/refman/8.0/en/innodb-checkpoints.html)[17.11.4 Defragmenting a Table](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-defragmenting.html)[17.11.5 Reclaiming Disk Space with TRUNCATE TABLE](https://dev.mysql.com/doc/refman/8.0/en/innodb-truncate-table-reclaim-space.html)[17.12 InnoDB and Online DDL](https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl.html)[17.12.1 Online DDL Operations](https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl-operations.html)[17.12.2 Online DDL Performance and Concurrency](https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl-performance.html)[17.12.3 Online DDL Space Requirements](https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl-space-requirements.html)[17.12.4 Online DDL Memory Management](https://dev.mysql.com/doc/refman/8.0/en/online-ddl-memory-management.html)[17.12.5 Configuring Parallel Threads for Online DDL Operations](https://dev.mysql.com/doc/refman/8.0/en/online-ddl-parallel-thread-configuration.html)[17.12.6 Simplifying DDL Statements with Online DDL](https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl-single-multi.html)[17.12.7 Online DDL Failure Conditions](https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl-failure-conditions.html)[17.12.8 Online DDL Limitations](https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl-limitations.html)[17.13 InnoDB Data-at-Rest Encryption](https://dev.mysql.com/doc/refman/8.0/en/innodb-data-encryption.html)[17.14 InnoDB Startup Options and System Variables](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html)[17.15 InnoDB INFORMATION\_SCHEMA Tables](https://dev.mysql.com/doc/refman/8.0/en/innodb-information-schema.html)[17.15.1 InnoDB INFORMATION\_SCHEMA Tables about Compression](https://dev.mysql.com/doc/refman/8.0/en/innodb-information-schema-compression-tables.html)[17.15.2 InnoDB INFORMATION\_SCHEMA Transaction and Locking Information](https://dev.mysql.com/doc/refman/8.0/en/innodb-information-schema-transactions.html)[17.15.3 InnoDB INFORMATION\_SCHEMA Schema Object Tables](https://dev.mysql.com/doc/refman/8.0/en/innodb-information-schema-system-tables.html)[17.15.4 InnoDB INFORMATION\_SCHEMA FULLTEXT Index Tables](https://dev.mysql.com/doc/refman/8.0/en/innodb-information-schema-fulltext_index-tables.html)[17.15.5 InnoDB INFORMATION\_SCHEMA Buffer Pool Tables](https://dev.mysql.com/doc/refman/8.0/en/innodb-information-schema-buffer-pool-tables.html)[17.15.6 InnoDB INFORMATION\_SCHEMA Metrics Table](https://dev.mysql.com/doc/refman/8.0/en/innodb-information-schema-metrics-table.html)[17.15.7 InnoDB INFORMATION\_SCHEMA Temporary Table Info Table](https://dev.mysql.com/doc/refman/8.0/en/innodb-information-schema-temp-table-info.html)[17.15.8 Retrieving InnoDB Tablespace Metadata from INFORMATION\_SCHEMA.FILES](https://dev.mysql.com/doc/refman/8.0/en/innodb-information-schema-files-table.html)[17.16 InnoDB Integration with MySQL Performance Schema](https://dev.mysql.com/doc/refman/8.0/en/innodb-performance-schema.html)[17.16.1 Monitoring ALTER TABLE Progress for InnoDB Tables Using Performance\\
Schema](https://dev.mysql.com/doc/refman/8.0/en/monitor-alter-table-performance-schema.html)[17.16.2 Monitoring InnoDB Mutex Waits Using Performance Schema](https://dev.mysql.com/doc/refman/8.0/en/monitor-innodb-mutex-waits-performance-schema.html)[17.17 InnoDB Monitors](https://dev.mysql.com/doc/refman/8.0/en/innodb-monitors.html)[17.17.1 InnoDB Monitor Types](https://dev.mysql.com/doc/refman/8.0/en/innodb-monitor-types.html)[17.17.2 Enabling InnoDB Monitors](https://dev.mysql.com/doc/refman/8.0/en/innodb-enabling-monitors.html)[17.17.3 InnoDB Standard Monitor and Lock Monitor Output](https://dev.mysql.com/doc/refman/8.0/en/innodb-standard-monitor.html)[17.18 InnoDB Backup and Recovery](https://dev.mysql.com/doc/refman/8.0/en/innodb-backup-recovery.html)[17.18.1 InnoDB Backup](https://dev.mysql.com/doc/refman/8.0/en/innodb-backup.html)[17.18.2 InnoDB Recovery](https://dev.mysql.com/doc/refman/8.0/en/innodb-recovery.html)[17.19 InnoDB and MySQL Replication](https://dev.mysql.com/doc/refman/8.0/en/innodb-and-mysql-replication.html)[17.20 InnoDB memcached Plugin](https://dev.mysql.com/doc/refman/8.0/en/innodb-memcached.html)[17.20.1 Benefits of the InnoDB memcached Plugin](https://dev.mysql.com/doc/refman/8.0/en/innodb-memcached-benefits.html)[17.20.2 InnoDB memcached Architecture](https://dev.mysql.com/doc/refman/8.0/en/innodb-memcached-intro.html)[17.20.3 Setting Up the InnoDB memcached Plugin](https://dev.mysql.com/doc/refman/8.0/en/innodb-memcached-setup.html)[17.20.4 InnoDB memcached Multiple get and Range Query Support](https://dev.mysql.com/doc/refman/8.0/en/innodb-memcached-multiple-get-range-query.html)[17.20.5 Security Considerations for the InnoDB memcached Plugin](https://dev.mysql.com/doc/refman/8.0/en/innodb-memcached-security.html)[17.20.6 Writing Applications for the InnoDB memcached Plugin](https://dev.mysql.com/doc/refman/8.0/en/innodb-memcached-developing.html)[17.20.7 The InnoDB memcached Plugin and Replication](https://dev.mysql.com/doc/refman/8.0/en/innodb-memcached-replication.html)[17.20.8 InnoDB memcached Plugin Internals](https://dev.mysql.com/doc/refman/8.0/en/innodb-memcached-internals.html)[17.20.9 Troubleshooting the InnoDB memcached Plugin](https://dev.mysql.com/doc/refman/8.0/en/innodb-memcached-troubleshoot.html)[17.21 InnoDB Troubleshooting](https://dev.mysql.com/doc/refman/8.0/en/innodb-troubleshooting.html)[17.21.1 Troubleshooting InnoDB I/O Problems](https://dev.mysql.com/doc/refman/8.0/en/error-creating-innodb.html)[17.21.2 Troubleshooting Recovery Failures](https://dev.mysql.com/doc/refman/8.0/en/innodb-troubleshooting-recovery.html)[17.21.3 Forcing InnoDB Recovery](https://dev.mysql.com/doc/refman/8.0/en/forcing-innodb-recovery.html)[17.21.4 Troubleshooting InnoDB Data Dictionary Operations](https://dev.mysql.com/doc/refman/8.0/en/innodb-troubleshooting-datadict.html)[17.21.5 InnoDB Error Handling](https://dev.mysql.com/doc/refman/8.0/en/innodb-error-handling.html)[17.22 InnoDB Limits](https://dev.mysql.com/doc/refman/8.0/en/innodb-limits.html)[17.23 InnoDB Restrictions and Limitations](https://dev.mysql.com/doc/refman/8.0/en/innodb-restrictions-limitations.html)

[PREV](https://dev.mysql.com/doc/refman/8.0/en/data-dictionary-limitations.html "Previous: Data Dictionary Limitations") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/innodb-introduction.html "Next: Introduction to InnoDB")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)

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