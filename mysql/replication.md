---
url: https://dev.mysql.com/doc/refman/8.0/en/replication.html
scraped_at: 2025-10-20T03:03:38.108Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/replication.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/replication.html "Hide Sidebar")

[Previous: The Common Database Server Layer](https://dev.mysql.com/doc/refman/8.0/en/pluggable-storage-common-layer.html "Previous: The Common Database Server Layer")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up")[Next: Configuring Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html "Next: Configuring Replication")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/replication.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/replication.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/replication.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/replication.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/replication.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/replication.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/replication.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/replication.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/replication.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/replication.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/replication.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/replication.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/replication.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
Replication


# Chapter 19 Replication

**Table of Contents**

[19.1 Configuring Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html)[19.1.1 Binary Log File Position Based Replication Configuration Overview](https://dev.mysql.com/doc/refman/8.0/en/binlog-replication-configuration-overview.html)[19.1.2 Setting Up Binary Log File Position Based Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html)[19.1.3 Replication with Global Transaction Identifiers](https://dev.mysql.com/doc/refman/8.0/en/replication-gtids.html)[19.1.4 Changing GTID Mode on Online Servers](https://dev.mysql.com/doc/refman/8.0/en/replication-mode-change-online.html)[19.1.5 MySQL Multi-Source Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-multi-source.html)[19.1.6 Replication and Binary Logging Options and Variables](https://dev.mysql.com/doc/refman/8.0/en/replication-options.html)[19.1.7 Common Replication Administration Tasks](https://dev.mysql.com/doc/refman/8.0/en/replication-administration.html)[19.2 Replication Implementation](https://dev.mysql.com/doc/refman/8.0/en/replication-implementation.html)[19.2.1 Replication Formats](https://dev.mysql.com/doc/refman/8.0/en/replication-formats.html)[19.2.2 Replication Channels](https://dev.mysql.com/doc/refman/8.0/en/replication-channels.html)[19.2.3 Replication Threads](https://dev.mysql.com/doc/refman/8.0/en/replication-threads.html)[19.2.4 Relay Log and Replication Metadata Repositories](https://dev.mysql.com/doc/refman/8.0/en/replica-logs.html)[19.2.5 How Servers Evaluate Replication Filtering Rules](https://dev.mysql.com/doc/refman/8.0/en/replication-rules.html)[19.3 Replication Security](https://dev.mysql.com/doc/refman/8.0/en/replication-security.html)[19.3.1 Setting Up Replication to Use Encrypted Connections](https://dev.mysql.com/doc/refman/8.0/en/replication-encrypted-connections.html)[19.3.2 Encrypting Binary Log Files and Relay Log Files](https://dev.mysql.com/doc/refman/8.0/en/replication-binlog-encryption.html)[19.3.3 Replication Privilege Checks](https://dev.mysql.com/doc/refman/8.0/en/replication-privilege-checks.html)[19.4 Replication Solutions](https://dev.mysql.com/doc/refman/8.0/en/replication-solutions.html)[19.4.1 Using Replication for Backups](https://dev.mysql.com/doc/refman/8.0/en/replication-solutions-backups.html)[19.4.2 Handling an Unexpected Halt of a Replica](https://dev.mysql.com/doc/refman/8.0/en/replication-solutions-unexpected-replica-halt.html)[19.4.3 Monitoring Row-based Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-solutions-rbr-monitoring.html)[19.4.4 Using Replication with Different Source and Replica Storage Engines](https://dev.mysql.com/doc/refman/8.0/en/replication-solutions-diffengines.html)[19.4.5 Using Replication for Scale-Out](https://dev.mysql.com/doc/refman/8.0/en/replication-solutions-scaleout.html)[19.4.6 Replicating Different Databases to Different Replicas](https://dev.mysql.com/doc/refman/8.0/en/replication-solutions-partitioning.html)[19.4.7 Improving Replication Performance](https://dev.mysql.com/doc/refman/8.0/en/replication-solutions-performance.html)[19.4.8 Switching Sources During Failover](https://dev.mysql.com/doc/refman/8.0/en/replication-solutions-switch.html)[19.4.9 Switching Sources and Replicas with Asynchronous Connection Failover](https://dev.mysql.com/doc/refman/8.0/en/replication-asynchronous-connection-failover.html)[19.4.10 Semisynchronous Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-semisync.html)[19.4.11 Delayed Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-delayed.html)[19.5 Replication Notes and Tips](https://dev.mysql.com/doc/refman/8.0/en/replication-notes.html)[19.5.1 Replication Features and Issues](https://dev.mysql.com/doc/refman/8.0/en/replication-features.html)[19.5.2 Replication Compatibility Between MySQL Versions](https://dev.mysql.com/doc/refman/8.0/en/replication-compatibility.html)[19.5.3 Upgrading a Replication Topology](https://dev.mysql.com/doc/refman/8.0/en/replication-upgrade.html)[19.5.4 Troubleshooting Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-problems.html)[19.5.5 How to Report Replication Bugs or Problems](https://dev.mysql.com/doc/refman/8.0/en/replication-bugs.html)

Replication enables data from one MySQL database server (known as a
source) to be copied to one or more MySQL database servers (known as
replicas). Replication is asynchronous by default; replicas do not
need to be connected permanently to receive updates from a source.
Depending on the configuration, you can replicate all databases,
selected databases, or even selected tables within a database.


Advantages of replication in MySQL include:

- Scale-out solutions - spreading the load among multiple replicas
to improve performance. In this environment, all writes and
updates must take place on the source server. Reads, however,
may take place on one or more replicas. This model can improve
the performance of writes (since the source is dedicated to
updates), while dramatically increasing read speed across an
increasing number of replicas.


- Data security - because the replica can pause the replication
process, it is possible to run backup services on the replica
without corrupting the corresponding source data.


- Analytics - live data can be created on the source, while the
analysis of the information can take place on the replica
without affecting the performance of the source.


- Long-distance data distribution - you can use replication to
create a local copy of data for a remote site to use, without
permanent access to the source.


For information on how to use replication in such scenarios, see
[Section 19.4, “Replication Solutions”](https://dev.mysql.com/doc/refman/8.0/en/replication-solutions.html "19.4 Replication Solutions").


MySQL 8.0 supports different methods of replication.
The traditional method is based on replicating events from the
source's binary log, and requires the log files and positions in
them to be synchronized between source and replica. The newer method
based on global transaction
identifiers (GTIDs) is transactional and therefore does
not require working with log files or positions within these files,
which greatly simplifies many common replication tasks. Replication
using GTIDs guarantees consistency between source and replica as
long as all transactions committed on the source have also been
applied on the replica. For more information about GTIDs and
GTID-based replication in MySQL, see
[Section 19.1.3, “Replication with Global Transaction Identifiers”](https://dev.mysql.com/doc/refman/8.0/en/replication-gtids.html "19.1.3 Replication with Global Transaction Identifiers"). For information on using binary
log file position based replication, see
[Section 19.1, “Configuring Replication”](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html "19.1 Configuring Replication").


Replication in MySQL supports different types of synchronization.
The original type of synchronization is one-way, asynchronous
replication, in which one server acts as the source, while one or
more other servers act as replicas. This is in contrast to the
_synchronous_ replication which is a
characteristic of NDB Cluster (see [Chapter 25, _MySQL NDB Cluster 8.0_](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0")).
In MySQL 8.0, semisynchronous replication is supported
in addition to the built-in asynchronous replication. With
semisynchronous replication, a commit performed on the source blocks
before returning to the session that performed the transaction until
at least one replica acknowledges that it has received and logged
the events for the transaction; see
[Section 19.4.10, “Semisynchronous Replication”](https://dev.mysql.com/doc/refman/8.0/en/replication-semisync.html "19.4.10 Semisynchronous Replication"). MySQL 8.0 also
supports delayed replication such that a replica deliberately lags
behind the source by at least a specified amount of time; see
[Section 19.4.11, “Delayed Replication”](https://dev.mysql.com/doc/refman/8.0/en/replication-delayed.html "19.4.11 Delayed Replication"). For scenarios where
_synchronous_ replication is required, use NDB
Cluster (see [Chapter 25, _MySQL NDB Cluster 8.0_](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0")).


There are a number of solutions available for setting up replication
between servers, and the best method to use depends on the presence
of data and the engine types you are using. For more information on
the available options, see [Section 19.1.2, “Setting Up Binary Log File Position Based Replication”](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html "19.1.2 Setting Up Binary Log File Position Based Replication").


There are two core types of replication format, Statement Based
Replication (SBR), which replicates entire SQL statements, and Row
Based Replication (RBR), which replicates only the changed rows. You
can also use a third variety, Mixed Based Replication (MBR). For
more information on the different replication formats, see
[Section 19.2.1, “Replication Formats”](https://dev.mysql.com/doc/refman/8.0/en/replication-formats.html "19.2.1 Replication Formats").


Replication is controlled through a number of different options and
variables. For more information, see
[Section 19.1.6, “Replication and Binary Logging Options and Variables”](https://dev.mysql.com/doc/refman/8.0/en/replication-options.html "19.1.6 Replication and Binary Logging Options and Variables"). Additional security measures
can be applied to a replication topology, as described in
[Section 19.3, “Replication Security”](https://dev.mysql.com/doc/refman/8.0/en/replication-security.html "19.3 Replication Security").


You can use replication to solve a number of different problems,
including performance, supporting the backup of different databases,
and as part of a larger solution to alleviate system failures. For
information on how to address these issues, see
[Section 19.4, “Replication Solutions”](https://dev.mysql.com/doc/refman/8.0/en/replication-solutions.html "19.4 Replication Solutions").


For notes and tips on how different data types and statements are
treated during replication, including details of replication
features, version compatibility, upgrades, and potential problems
and their resolution, see [Section 19.5, “Replication Notes and Tips”](https://dev.mysql.com/doc/refman/8.0/en/replication-notes.html "19.5 Replication Notes and Tips"). For
answers to some questions often asked by those who are new to MySQL
Replication, see [Section A.14, “MySQL 8.0 FAQ: Replication”](https://dev.mysql.com/doc/refman/8.0/en/faqs-replication.html "A.14 MySQL 8.0 FAQ: Replication").


For detailed information on the implementation of replication, how
replication works, the process and contents of the binary log,
background threads and the rules used to decide how statements are
recorded and replicated, see
[Section 19.2, “Replication Implementation”](https://dev.mysql.com/doc/refman/8.0/en/replication-implementation.html "19.2 Replication Implementation").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/pluggable-storage-common-layer.html "Previous: The Common Database Server Layer") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html "Next: Configuring Replication")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/replication.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/replication.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/replication.html)

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