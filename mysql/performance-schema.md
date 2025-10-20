---
url: https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html
scraped_at: 2025-10-20T03:03:47.801Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html "Hide Sidebar")

[Previous: Extensions to SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html "Previous: Extensions to SHOW Statements")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up")[Next: Performance Schema Quick Start](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-quick-start.html "Next: Performance Schema Quick Start")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/performance-schema.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/performance-schema.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/performance-schema.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/performance-schema.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/performance-schema.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/performance-schema.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/performance-schema.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/performance-schema.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
MySQL Performance Schema


# Chapter 29 MySQL Performance Schema

**Table of Contents**

[29.1 Performance Schema Quick Start](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-quick-start.html)[29.2 Performance Schema Build Configuration](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-build-configuration.html)[29.3 Performance Schema Startup Configuration](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-startup-configuration.html)[29.4 Performance Schema Runtime Configuration](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-runtime-configuration.html)[29.4.1 Performance Schema Event Timing](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-timing.html)[29.4.2 Performance Schema Event Filtering](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-filtering.html)[29.4.3 Event Pre-Filtering](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-pre-filtering.html)[29.4.4 Pre-Filtering by Instrument](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-instrument-filtering.html)[29.4.5 Pre-Filtering by Object](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-object-filtering.html)[29.4.6 Pre-Filtering by Thread](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-thread-filtering.html)[29.4.7 Pre-Filtering by Consumer](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-consumer-filtering.html)[29.4.8 Example Consumer Configurations](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-consumer-configurations.html)[29.4.9 Naming Instruments or Consumers for Filtering Operations](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-filtering-names.html)[29.4.10 Determining What Is Instrumented](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-instrumentation-checking.html)[29.5 Performance Schema Queries](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-queries.html)[29.6 Performance Schema Instrument Naming Conventions](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-instrument-naming.html)[29.7 Performance Schema Status Monitoring](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-status-monitoring.html)[29.8 Performance Schema Atom and Molecule Events](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-atom-molecule-events.html)[29.9 Performance Schema Tables for Current and Historical Events](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-event-tables.html)[29.10 Performance Schema Statement Digests and Sampling](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-statement-digests.html)[29.11 Performance Schema General Table Characteristics](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-table-characteristics.html)[29.12 Performance Schema Table Descriptions](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-table-descriptions.html)[29.12.1 Performance Schema Table Reference](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-table-reference.html)[29.12.2 Performance Schema Setup Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-setup-tables.html)[29.12.3 Performance Schema Instance Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-instance-tables.html)[29.12.4 Performance Schema Wait Event Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-wait-tables.html)[29.12.5 Performance Schema Stage Event Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-stage-tables.html)[29.12.6 Performance Schema Statement Event Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-statement-tables.html)[29.12.7 Performance Schema Transaction Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-transaction-tables.html)[29.12.8 Performance Schema Connection Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-connection-tables.html)[29.12.9 Performance Schema Connection Attribute Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-connection-attribute-tables.html)[29.12.10 Performance Schema User-Defined Variable Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-user-variable-tables.html)[29.12.11 Performance Schema Replication Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-replication-tables.html)[29.12.12 Performance Schema NDB Cluster Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-ndb-cluster-tables.html)[29.12.13 Performance Schema Lock Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-lock-tables.html)[29.12.14 Performance Schema System Variable Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-system-variable-tables.html)[29.12.15 Performance Schema Status Variable Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-status-variable-tables.html)[29.12.16 Performance Schema Thread Pool Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-thread-pool-tables.html)[29.12.17 Performance Schema Firewall Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-firewall-tables.html)[29.12.18 Performance Schema Keyring Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-keyring-tables.html)[29.12.19 Performance Schema Clone Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-clone-tables.html)[29.12.20 Performance Schema Summary Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-summary-tables.html)[29.12.21 Performance Schema Miscellaneous Tables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-miscellaneous-tables.html)[29.13 Performance Schema Option and Variable Reference](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-option-variable-reference.html)[29.14 Performance Schema Command Options](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-options.html)[29.15 Performance Schema System Variables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-system-variables.html)[29.16 Performance Schema Status Variables](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-status-variables.html)[29.17 The Performance Schema Memory-Allocation Model](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-memory-model.html)[29.18 Performance Schema and Plugins](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-and-plugins.html)[29.19 Using the Performance Schema to Diagnose Problems](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-examples.html)[29.19.1 Query Profiling Using Performance Schema](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-query-profiling.html)[29.19.2 Obtaining Parent Event Information](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-obtaining-parent-events.html)[29.20 Restrictions on Performance Schema](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-restrictions.html)

The MySQL Performance Schema is a feature for monitoring MySQL
Server execution at a low level. The Performance Schema has these
characteristics:

- The Performance Schema provides a way to inspect internal
execution of the server at runtime. It is implemented using the
[`PERFORMANCE_SCHEMA`](https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html "Chapter 29 MySQL Performance Schema") storage engine
and the `performance_schema` database. The
Performance Schema focuses primarily on performance data. This
differs from `INFORMATION_SCHEMA`, which serves
for inspection of metadata.


- The Performance Schema monitors server events. An
“event” is anything the server does that takes time
and has been instrumented so that timing information can be
collected. In general, an event could be a function call, a wait
for the operating system, a stage of an SQL statement execution
such as parsing or sorting, or an entire statement or group of
statements. Event collection provides access to information
about synchronization calls (such as for mutexes) file and table
I/O, table locks, and so forth for the server and for several
storage engines.


- Performance Schema events are distinct from events written to
the server's binary log (which describe data modifications) and
Event Scheduler events (which are a type of stored program).


- Performance Schema events are specific to a given instance of
the MySQL Server. Performance Schema tables are considered local
to the server, and changes to them are not replicated or written
to the binary log.


- Current events are available, as well as event histories and
summaries. This enables you to determine how many times
instrumented activities were performed and how much time they
took. Event information is available to show the activities of
specific threads, or activity associated with particular objects
such as a mutex or file.


- The [`PERFORMANCE_SCHEMA`](https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html "Chapter 29 MySQL Performance Schema") storage
engine collects event data using “instrumentation
points” in server source code.


- Collected events are stored in tables in the
`performance_schema` database. These tables can
be queried using [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statements like other tables.


- Performance Schema configuration can be modified dynamically by
updating tables in the `performance_schema`
database through SQL statements. Configuration changes affect
data collection immediately.


- Tables in the Performance Schema are in-memory tables that use
no persistent on-disk storage. The contents are repopulated
beginning at server startup and discarded at server shutdown.


- Monitoring is available on all platforms supported by MySQL.



Some limitations might apply: The types of timers might vary per
platform. Instruments that apply to storage engines might not be
implemented for all storage engines. Instrumentation of each
third-party engine is the responsibility of the engine
maintainer. See also
[Section 29.20, “Restrictions on Performance Schema”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-restrictions.html "29.20 Restrictions on Performance Schema").


- Data collection is implemented by modifying the server source
code to add instrumentation. There are no separate threads
associated with the Performance Schema, unlike other features
such as replication or the Event Scheduler.


The Performance Schema is intended to provide access to useful
information about server execution while having minimal impact on
server performance. The implementation follows these design goals:

- Activating the Performance Schema causes no changes in server
behavior. For example, it does not cause thread scheduling to
change, and it does not cause query execution plans (as shown by
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement")) to change.


- Server monitoring occurs continuously and unobtrusively with
very little overhead. Activating the Performance Schema does not
make the server unusable.


- The parser is unchanged. There are no new keywords or
statements.


- Execution of server code proceeds normally even if the
Performance Schema fails internally.


- When there is a choice between performing processing during
event collection initially or during event retrieval later,
priority is given to making collection faster. This is because
collection is ongoing whereas retrieval is on demand and might
never happen at all.


- Most Performance Schema tables have indexes, which gives the
optimizer access to execution plans other than full table scans.
For more information, see
[Section 10.2.4, “Optimizing Performance Schema Queries”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-optimization.html "10.2.4 Optimizing Performance Schema Queries").


- It is easy to add new instrumentation points.


- Instrumentation is versioned. If the instrumentation
implementation changes, previously instrumented code continues
to work. This benefits developers of third-party plugins because
it is not necessary to upgrade each plugin to stay synchronized
with the latest Performance Schema changes.


Note

The MySQL `sys` schema is a set of objects that
provides convenient access to data collected by the Performance
Schema. The `sys` schema is installed by default.
For usage instructions, see [Chapter 30, _MySQL sys Schema_](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html "Chapter 30 MySQL sys Schema").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html "Previous: Extensions to SHOW Statements") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-quick-start.html "Next: Performance Schema Quick Start")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/performance-schema.html)

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