---
url: https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html
scraped_at: 2025-10-20T03:03:40.996Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html "Hide Sidebar")

[Previous: Replication](https://dev.mysql.com/doc/refman/8.0/en/replication.html "Previous: Replication")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Replication](https://dev.mysql.com/doc/refman/8.0/en/replication.html "Up: Replication")[Next: Binary Log File Position Based Replication Configuration Overview](https://dev.mysql.com/doc/refman/8.0/en/binlog-replication-configuration-overview.html "Next: Binary Log File Position Based Replication Configuration Overview")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/replication-configuration.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/replication-configuration.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/replication-configuration.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/replication-configuration.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/replication-configuration.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/replication-configuration.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/replication-configuration.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/replication-configuration.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Replication](https://dev.mysql.com/doc/refman/8.0/en/replication.html)  /
Configuring Replication


## 19.1 Configuring Replication

[19.1.1 Binary Log File Position Based Replication Configuration Overview](https://dev.mysql.com/doc/refman/8.0/en/binlog-replication-configuration-overview.html)[19.1.2 Setting Up Binary Log File Position Based Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html)[19.1.3 Replication with Global Transaction Identifiers](https://dev.mysql.com/doc/refman/8.0/en/replication-gtids.html)[19.1.4 Changing GTID Mode on Online Servers](https://dev.mysql.com/doc/refman/8.0/en/replication-mode-change-online.html)[19.1.5 MySQL Multi-Source Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-multi-source.html)[19.1.6 Replication and Binary Logging Options and Variables](https://dev.mysql.com/doc/refman/8.0/en/replication-options.html)[19.1.7 Common Replication Administration Tasks](https://dev.mysql.com/doc/refman/8.0/en/replication-administration.html)

This section describes how to configure the different types of
replication available in MySQL and includes the setup and
configuration required for a replication environment, including
step-by-step instructions for creating a new replication
environment. The major components of this section are:

- For a guide to setting up two or more servers for replication
using binary log file positions,
[Section 19.1.2, “Setting Up Binary Log File Position Based Replication”](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html "19.1.2 Setting Up Binary Log File Position Based Replication"), deals with the
configuration of the servers and provides methods for copying
data between the source and replicas.


- For a guide to setting up two or more servers for replication
using GTID transactions, [Section 19.1.3, “Replication with Global Transaction Identifiers”](https://dev.mysql.com/doc/refman/8.0/en/replication-gtids.html "19.1.3 Replication with Global Transaction Identifiers"),
deals with the configuration of the servers.


- Events in the binary log are recorded using a number of formats.
These are referred to as statement-based replication (SBR) or
row-based replication (RBR). A third type, mixed-format
replication (MIXED), uses SBR or RBR replication automatically
to take advantage of the benefits of both SBR and RBR formats
when appropriate. The different formats are discussed in
[Section 19.2.1, “Replication Formats”](https://dev.mysql.com/doc/refman/8.0/en/replication-formats.html "19.2.1 Replication Formats").


- Detailed information on the different configuration options and
variables that apply to replication is provided in
[Section 19.1.6, “Replication and Binary Logging Options and Variables”](https://dev.mysql.com/doc/refman/8.0/en/replication-options.html "19.1.6 Replication and Binary Logging Options and Variables").


- Once started, the replication process should require little
administration or monitoring. However, for advice on common
tasks that you may want to execute, see
[Section 19.1.7, “Common Replication Administration Tasks”](https://dev.mysql.com/doc/refman/8.0/en/replication-administration.html "19.1.7 Common Replication Administration Tasks").


[PREV](https://dev.mysql.com/doc/refman/8.0/en/replication.html "Previous: Replication") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/replication.html "Up: Replication") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/binlog-replication-configuration-overview.html "Next: Binary Log File Position Based Replication Configuration Overview")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html)

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