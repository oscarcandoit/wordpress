---
url: https://dev.mysql.com/doc/refman/8.0/en/partitioning.html
scraped_at: 2025-10-20T03:04:28.782Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html "Hide Sidebar")

[Previous: NDB Cluster Release Notes](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster-news.html "Previous: NDB Cluster Release Notes")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up")[Next: Overview of Partitioning in MySQL](https://dev.mysql.com/doc/refman/8.0/en/partitioning-overview.html "Next: Overview of Partitioning in MySQL")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/partitioning.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/partitioning.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/partitioning.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/partitioning.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/partitioning.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/partitioning.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/partitioning.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/partitioning.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
Partitioning


# Chapter 26 Partitioning

**Table of Contents**

[26.1 Overview of Partitioning in MySQL](https://dev.mysql.com/doc/refman/8.0/en/partitioning-overview.html)[26.2 Partitioning Types](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html)[26.2.1 RANGE Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-range.html)[26.2.2 LIST Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-list.html)[26.2.3 COLUMNS Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-columns.html)[26.2.4 HASH Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-hash.html)[26.2.5 KEY Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-key.html)[26.2.6 Subpartitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-subpartitions.html)[26.2.7 How MySQL Partitioning Handles NULL](https://dev.mysql.com/doc/refman/8.0/en/partitioning-handling-nulls.html)[26.3 Partition Management](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html)[26.3.1 Management of RANGE and LIST Partitions](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management-range-list.html)[26.3.2 Management of HASH and KEY Partitions](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management-hash-key.html)[26.3.3 Exchanging Partitions and Subpartitions with Tables](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management-exchange.html)[26.3.4 Maintenance of Partitions](https://dev.mysql.com/doc/refman/8.0/en/partitioning-maintenance.html)[26.3.5 Obtaining Information About Partitions](https://dev.mysql.com/doc/refman/8.0/en/partitioning-info.html)[26.4 Partition Pruning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-pruning.html)[26.5 Partition Selection](https://dev.mysql.com/doc/refman/8.0/en/partitioning-selection.html)[26.6 Restrictions and Limitations on Partitioning](https://dev.mysql.com/doc/refman/8.0/en/partitioning-limitations.html)[26.6.1 Partitioning Keys, Primary Keys, and Unique Keys](https://dev.mysql.com/doc/refman/8.0/en/partitioning-limitations-partitioning-keys-unique-keys.html)[26.6.2 Partitioning Limitations Relating to Storage Engines](https://dev.mysql.com/doc/refman/8.0/en/partitioning-limitations-storage-engines.html)[26.6.3 Partitioning Limitations Relating to Functions](https://dev.mysql.com/doc/refman/8.0/en/partitioning-limitations-functions.html)

This chapter discusses user-defined
partitioning.

Note

Table partitioning differs from partitioning as used by window
functions. For information about window functions, see
[Section 14.20, “Window Functions”](https://dev.mysql.com/doc/refman/8.0/en/window-functions.html "14.20 Window Functions").

In MySQL 8.0, partitioning support is provided by the
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") and
[`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0") storage engines.


MySQL 8.0 does not currently support partitioning of
tables using any storage engine other than `InnoDB`
or `NDB`, such as
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine"). An attempt to create a
partitioned tables using a storage engine that does not supply
native partitioning support fails with
[`ER_CHECK_NOT_IMPLEMENTED`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_check_not_implemented).


MySQL 8.0 Community binaries provided by Oracle include
partitioning support provided by the `InnoDB` and
`NDB` storage engines. For information about
partitioning support offered in MySQL Enterprise Edition binaries, see
[Chapter 32, _MySQL Enterprise Edition_](https://dev.mysql.com/doc/refman/8.0/en/mysql-enterprise.html "Chapter 32 MySQL Enterprise Edition").


If you are compiling MySQL 8.0 from source, configuring
the build with `InnoDB` support is sufficient to
produce binaries with partition support for
`InnoDB` tables. For more information, see
[Section 2.8, “Installing MySQL from Source”](https://dev.mysql.com/doc/refman/8.0/en/source-installation.html "2.8 Installing MySQL from Source").


Nothing further needs to be done to enable partitioning support by
`InnoDB` (for example, no special entries are
required in the `my.cnf` file).


It is not possible to disable partitioning support by the
`InnoDB` storage engine.


See [Section 26.1, “Overview of Partitioning in MySQL”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-overview.html "26.1 Overview of Partitioning in MySQL"), for an introduction to
partitioning and partitioning concepts.


Several types of partitioning are supported, as well as
subpartitioning; see [Section 26.2, “Partitioning Types”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-types.html "26.2 Partitioning Types"), and
[Section 26.2.6, “Subpartitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-subpartitions.html "26.2.6 Subpartitioning").


[Section 26.3, “Partition Management”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-management.html "26.3 Partition Management"), covers methods of adding,
removing, and altering partitions in existing partitioned tables.


[Section 26.3.4, “Maintenance of Partitions”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-maintenance.html "26.3.4 Maintenance of Partitions"), discusses table
maintenance commands for use with partitioned tables.


The [`PARTITIONS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-partitions-table.html "28.3.21 The INFORMATION_SCHEMA PARTITIONS Table") table in the
`INFORMATION_SCHEMA` database provides information
about partitions and partitioned tables. See
[Section 28.3.21, “The INFORMATION\_SCHEMA PARTITIONS Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-partitions-table.html "28.3.21 The INFORMATION_SCHEMA PARTITIONS Table"), for more
information; for some examples of queries against this table, see
[Section 26.2.7, “How MySQL Partitioning Handles NULL”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-handling-nulls.html "26.2.7 How MySQL Partitioning Handles NULL").


For known issues with partitioning in MySQL 8.0, see
[Section 26.6, “Restrictions and Limitations on Partitioning”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-limitations.html "26.6 Restrictions and Limitations on Partitioning").


You may also find the following resources to be useful when working
with partitioned tables.


**Additional Resources.**
Other sources of information about user-defined partitioning in
MySQL include the following:

- [MySQL Partitioning\\
Forum](https://forums.mysql.com/list.php?106)


This is the official discussion forum for those interested in or
experimenting with MySQL Partitioning technology. It features
announcements and updates from MySQL developers and others. It
is monitored by members of the Partitioning Development and
Documentation Teams.


- [PlanetMySQL](http://www.planetmysql.org/)


A MySQL news site featuring MySQL-related blogs, which should be
of interest to anyone using my MySQL. We encourage you to check
here for links to blogs kept by those working with MySQL
Partitioning, or to have your own blog added to those covered.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster-news.html "Previous: NDB Cluster Release Notes") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/partitioning-overview.html "Next: Overview of Partitioning in MySQL")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)

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