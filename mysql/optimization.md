---
url: https://dev.mysql.com/doc/refman/8.0/en/optimization.html
scraped_at: 2025-10-20T03:03:55.924Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/optimization.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/optimization.html "Hide Sidebar")

[Previous: Setting Up a MyISAM Table Maintenance Schedule](https://dev.mysql.com/doc/refman/8.0/en/myisam-maintenance-schedule.html "Previous: Setting Up a MyISAM Table Maintenance Schedule")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up")[Next: Optimization Overview](https://dev.mysql.com/doc/refman/8.0/en/optimize-overview.html "Next: Optimization Overview")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/optimization.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/optimization.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/optimization.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/optimization.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/optimization.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/optimization.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/optimization.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/optimization.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/optimization.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
Optimization


# Chapter 10 Optimization

**Table of Contents**

[10.1 Optimization Overview](https://dev.mysql.com/doc/refman/8.0/en/optimize-overview.html)[10.2 Optimizing SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)[10.2.1 Optimizing SELECT Statements](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html)[10.2.2 Optimizing Subqueries, Derived Tables, View References, and Common Table\\
Expressions](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization.html)[10.2.3 Optimizing INFORMATION\_SCHEMA Queries](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html)[10.2.4 Optimizing Performance Schema Queries](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-optimization.html)[10.2.5 Optimizing Data Change Statements](https://dev.mysql.com/doc/refman/8.0/en/data-change-optimization.html)[10.2.6 Optimizing Database Privileges](https://dev.mysql.com/doc/refman/8.0/en/permission-optimization.html)[10.2.7 Other Optimization Tips](https://dev.mysql.com/doc/refman/8.0/en/miscellaneous-optimization-tips.html)[10.3 Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)[10.3.1 How MySQL Uses Indexes](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html)[10.3.2 Primary Key Optimization](https://dev.mysql.com/doc/refman/8.0/en/primary-key-optimization.html)[10.3.3 SPATIAL Index Optimization](https://dev.mysql.com/doc/refman/8.0/en/spatial-index-optimization.html)[10.3.4 Foreign Key Optimization](https://dev.mysql.com/doc/refman/8.0/en/foreign-key-optimization.html)[10.3.5 Column Indexes](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html)[10.3.6 Multiple-Column Indexes](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html)[10.3.7 Verifying Index Usage](https://dev.mysql.com/doc/refman/8.0/en/verifying-index-usage.html)[10.3.8 InnoDB and MyISAM Index Statistics Collection](https://dev.mysql.com/doc/refman/8.0/en/index-statistics.html)[10.3.9 Comparison of B-Tree and Hash Indexes](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html)[10.3.10 Use of Index Extensions](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html)[10.3.11 Optimizer Use of Generated Column Indexes](https://dev.mysql.com/doc/refman/8.0/en/generated-column-index-optimizations.html)[10.3.12 Invisible Indexes](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html)[10.3.13 Descending Indexes](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html)[10.3.14 Indexed Lookups from TIMESTAMP Columns](https://dev.mysql.com/doc/refman/8.0/en/timestamp-lookups.html)[10.4 Optimizing Database Structure](https://dev.mysql.com/doc/refman/8.0/en/optimizing-database-structure.html)[10.4.1 Optimizing Data Size](https://dev.mysql.com/doc/refman/8.0/en/data-size.html)[10.4.2 Optimizing MySQL Data Types](https://dev.mysql.com/doc/refman/8.0/en/optimize-data-types.html)[10.4.3 Optimizing for Many Tables](https://dev.mysql.com/doc/refman/8.0/en/optimize-multi-tables.html)[10.4.4 Internal Temporary Table Use in MySQL](https://dev.mysql.com/doc/refman/8.0/en/internal-temporary-tables.html)[10.4.5 Limits on Number of Databases and Tables](https://dev.mysql.com/doc/refman/8.0/en/database-count-limit.html)[10.4.6 Limits on Table Size](https://dev.mysql.com/doc/refman/8.0/en/table-size-limit.html)[10.4.7 Limits on Table Column Count and Row Size](https://dev.mysql.com/doc/refman/8.0/en/column-count-limit.html)[10.5 Optimizing for InnoDB Tables](https://dev.mysql.com/doc/refman/8.0/en/optimizing-innodb.html)[10.5.1 Optimizing Storage Layout for InnoDB Tables](https://dev.mysql.com/doc/refman/8.0/en/optimizing-innodb-storage-layout.html)[10.5.2 Optimizing InnoDB Transaction Management](https://dev.mysql.com/doc/refman/8.0/en/optimizing-innodb-transaction-management.html)[10.5.3 Optimizing InnoDB Read-Only Transactions](https://dev.mysql.com/doc/refman/8.0/en/innodb-performance-ro-txn.html)[10.5.4 Optimizing InnoDB Redo Logging](https://dev.mysql.com/doc/refman/8.0/en/optimizing-innodb-logging.html)[10.5.5 Bulk Data Loading for InnoDB Tables](https://dev.mysql.com/doc/refman/8.0/en/optimizing-innodb-bulk-data-loading.html)[10.5.6 Optimizing InnoDB Queries](https://dev.mysql.com/doc/refman/8.0/en/optimizing-innodb-queries.html)[10.5.7 Optimizing InnoDB DDL Operations](https://dev.mysql.com/doc/refman/8.0/en/optimizing-innodb-ddl-operations.html)[10.5.8 Optimizing InnoDB Disk I/O](https://dev.mysql.com/doc/refman/8.0/en/optimizing-innodb-diskio.html)[10.5.9 Optimizing InnoDB Configuration Variables](https://dev.mysql.com/doc/refman/8.0/en/optimizing-innodb-configuration-variables.html)[10.5.10 Optimizing InnoDB for Systems with Many Tables](https://dev.mysql.com/doc/refman/8.0/en/optimizing-innodb-many-tables.html)[10.6 Optimizing for MyISAM Tables](https://dev.mysql.com/doc/refman/8.0/en/optimizing-myisam.html)[10.6.1 Optimizing MyISAM Queries](https://dev.mysql.com/doc/refman/8.0/en/optimizing-queries-myisam.html)[10.6.2 Bulk Data Loading for MyISAM Tables](https://dev.mysql.com/doc/refman/8.0/en/optimizing-myisam-bulk-data-loading.html)[10.6.3 Optimizing REPAIR TABLE Statements](https://dev.mysql.com/doc/refman/8.0/en/repair-table-optimization.html)[10.7 Optimizing for MEMORY Tables](https://dev.mysql.com/doc/refman/8.0/en/optimizing-memory-tables.html)[10.8 Understanding the Query Execution Plan](https://dev.mysql.com/doc/refman/8.0/en/execution-plan-information.html)[10.8.1 Optimizing Queries with EXPLAIN](https://dev.mysql.com/doc/refman/8.0/en/using-explain.html)[10.8.2 EXPLAIN Output Format](https://dev.mysql.com/doc/refman/8.0/en/explain-output.html)[10.8.3 Extended EXPLAIN Output Format](https://dev.mysql.com/doc/refman/8.0/en/explain-extended.html)[10.8.4 Obtaining Execution Plan Information for a Named Connection](https://dev.mysql.com/doc/refman/8.0/en/explain-for-connection.html)[10.8.5 Estimating Query Performance](https://dev.mysql.com/doc/refman/8.0/en/estimating-performance.html)[10.9 Controlling the Query Optimizer](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html)[10.9.1 Controlling Query Plan Evaluation](https://dev.mysql.com/doc/refman/8.0/en/controlling-query-plan-evaluation.html)[10.9.2 Switchable Optimizations](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html)[10.9.3 Optimizer Hints](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html)[10.9.4 Index Hints](https://dev.mysql.com/doc/refman/8.0/en/index-hints.html)[10.9.5 The Optimizer Cost Model](https://dev.mysql.com/doc/refman/8.0/en/cost-model.html)[10.9.6 Optimizer Statistics](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html)[10.10 Buffering and Caching](https://dev.mysql.com/doc/refman/8.0/en/buffering-caching.html)[10.10.1 InnoDB Buffer Pool Optimization](https://dev.mysql.com/doc/refman/8.0/en/innodb-buffer-pool-optimization.html)[10.10.2 The MyISAM Key Cache](https://dev.mysql.com/doc/refman/8.0/en/myisam-key-cache.html)[10.10.3 Caching of Prepared Statements and Stored Programs](https://dev.mysql.com/doc/refman/8.0/en/statement-caching.html)[10.11 Optimizing Locking Operations](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html)[10.11.1 Internal Locking Methods](https://dev.mysql.com/doc/refman/8.0/en/internal-locking.html)[10.11.2 Table Locking Issues](https://dev.mysql.com/doc/refman/8.0/en/table-locking.html)[10.11.3 Concurrent Inserts](https://dev.mysql.com/doc/refman/8.0/en/concurrent-inserts.html)[10.11.4 Metadata Locking](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html)[10.11.5 External Locking](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html)[10.12 Optimizing the MySQL Server](https://dev.mysql.com/doc/refman/8.0/en/optimizing-server.html)[10.12.1 Optimizing Disk I/O](https://dev.mysql.com/doc/refman/8.0/en/disk-issues.html)[10.12.2 Using Symbolic Links](https://dev.mysql.com/doc/refman/8.0/en/symbolic-links.html)[10.12.3 Optimizing Memory Use](https://dev.mysql.com/doc/refman/8.0/en/optimizing-memory.html)[10.13 Measuring Performance (Benchmarking)](https://dev.mysql.com/doc/refman/8.0/en/optimize-benchmarking.html)[10.13.1 Measuring the Speed of Expressions and Functions](https://dev.mysql.com/doc/refman/8.0/en/select-benchmarking.html)[10.13.2 Using Your Own Benchmarks](https://dev.mysql.com/doc/refman/8.0/en/custom-benchmarks.html)[10.13.3 Measuring Performance with performance\_schema](https://dev.mysql.com/doc/refman/8.0/en/monitoring-performance-schema.html)[10.14 Examining Server Thread (Process) Information](https://dev.mysql.com/doc/refman/8.0/en/thread-information.html)[10.14.1 Accessing the Process List](https://dev.mysql.com/doc/refman/8.0/en/processlist-access.html)[10.14.2 Thread Command Values](https://dev.mysql.com/doc/refman/8.0/en/thread-commands.html)[10.14.3 General Thread States](https://dev.mysql.com/doc/refman/8.0/en/general-thread-states.html)[10.14.4 Replication Source Thread States](https://dev.mysql.com/doc/refman/8.0/en/source-thread-states.html)[10.14.5 Replication I/O (Receiver) Thread States](https://dev.mysql.com/doc/refman/8.0/en/replica-io-thread-states.html)[10.14.6 Replication SQL Thread States](https://dev.mysql.com/doc/refman/8.0/en/replica-sql-thread-states.html)[10.14.7 Replication Connection Thread States](https://dev.mysql.com/doc/refman/8.0/en/replica-connection-thread-states.html)[10.14.8 NDB Cluster Thread States](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster-thread-states.html)[10.14.9 Event Scheduler Thread States](https://dev.mysql.com/doc/refman/8.0/en/event-scheduler-thread-states.html)[10.15 Tracing the Optimizer](https://dev.mysql.com/doc/refman/8.0/en/optimizer-tracing.html)[10.15.1 Typical Usage](https://dev.mysql.com/doc/refman/8.0/en/optimizer-tracing-typical-usage.html)[10.15.2 System Variables Controlling Tracing](https://dev.mysql.com/doc/refman/8.0/en/system-variables-controlling-tracing.html)[10.15.3 Traceable Statements](https://dev.mysql.com/doc/refman/8.0/en/traceable-statements.html)[10.15.4 Tuning Trace Purging](https://dev.mysql.com/doc/refman/8.0/en/tuning-trace-purging.html)[10.15.5 Tracing Memory Usage](https://dev.mysql.com/doc/refman/8.0/en/tracing-memory-usage.html)[10.15.6 Privilege Checking](https://dev.mysql.com/doc/refman/8.0/en/privilege-checking.html)[10.15.7 Interaction with the --debug Option](https://dev.mysql.com/doc/refman/8.0/en/interaction-with-debug-option.html)[10.15.8 The optimizer\_trace System Variable](https://dev.mysql.com/doc/refman/8.0/en/optimizer-trace-system-variable.html)[10.15.9 The end\_markers\_in\_json System Variable](https://dev.mysql.com/doc/refman/8.0/en/end-markers-in-json-system-variable.html)[10.15.10 Selecting Optimizer Features to Trace](https://dev.mysql.com/doc/refman/8.0/en/optimizer-features-to-trace.html)[10.15.11 Trace General Structure](https://dev.mysql.com/doc/refman/8.0/en/trace-general-structure.html)[10.15.12 Example](https://dev.mysql.com/doc/refman/8.0/en/tracing-example.html)[10.15.13 Displaying Traces in Other Applications](https://dev.mysql.com/doc/refman/8.0/en/displaying-traces.html)[10.15.14 Preventing the Use of Optimizer Trace](https://dev.mysql.com/doc/refman/8.0/en/preventing-use-of-optimizer-trace.html)[10.15.15 Testing Optimizer Trace](https://dev.mysql.com/doc/refman/8.0/en/optimizer-trace-testing.html)[10.15.16 Optimizer Trace Implementation](https://dev.mysql.com/doc/refman/8.0/en/optimizer-trace-implementation.html)

This chapter explains how to optimize MySQL performance and provides
examples. Optimization involves configuring, tuning, and measuring
performance, at several levels. Depending on your job role
(developer, DBA, or a combination of both), you might optimize at
the level of individual SQL statements, entire applications, a
single database server, or multiple networked database servers.
Sometimes you can be proactive and plan in advance for performance,
while other times you might troubleshoot a configuration or code
issue after a problem occurs. Optimizing CPU and memory usage can
also improve scalability, allowing the database to handle more load
without slowing down.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/myisam-maintenance-schedule.html "Previous: Setting Up a MyISAM Table Maintenance Schedule") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/optimize-overview.html "Next: Optimization Overview")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)

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