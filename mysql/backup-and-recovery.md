---
url: https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html
scraped_at: 2025-10-20T03:03:24.941Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html "Hide Sidebar")

[Previous: FIPS Support](https://dev.mysql.com/doc/refman/8.0/en/fips-mode.html "Previous: FIPS Support")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up")[Next: Backup and Recovery Types](https://dev.mysql.com/doc/refman/8.0/en/backup-types.html "Next: Backup and Recovery Types")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/backup-and-recovery.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/backup-and-recovery.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/backup-and-recovery.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/backup-and-recovery.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/backup-and-recovery.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/backup-and-recovery.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/backup-and-recovery.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/backup-and-recovery.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
Backup and Recovery


# Chapter 9 Backup and Recovery

**Table of Contents**

[9.1 Backup and Recovery Types](https://dev.mysql.com/doc/refman/8.0/en/backup-types.html)[9.2 Database Backup Methods](https://dev.mysql.com/doc/refman/8.0/en/backup-methods.html)[9.3 Example Backup and Recovery Strategy](https://dev.mysql.com/doc/refman/8.0/en/backup-strategy-example.html)[9.3.1 Establishing a Backup Policy](https://dev.mysql.com/doc/refman/8.0/en/backup-policy.html)[9.3.2 Using Backups for Recovery](https://dev.mysql.com/doc/refman/8.0/en/recovery-from-backups.html)[9.3.3 Backup Strategy Summary](https://dev.mysql.com/doc/refman/8.0/en/backup-strategy-summary.html)[9.4 Using mysqldump for Backups](https://dev.mysql.com/doc/refman/8.0/en/using-mysqldump.html)[9.4.1 Dumping Data in SQL Format with mysqldump](https://dev.mysql.com/doc/refman/8.0/en/mysqldump-sql-format.html)[9.4.2 Reloading SQL-Format Backups](https://dev.mysql.com/doc/refman/8.0/en/reloading-sql-format-dumps.html)[9.4.3 Dumping Data in Delimited-Text Format with mysqldump](https://dev.mysql.com/doc/refman/8.0/en/mysqldump-delimited-text.html)[9.4.4 Reloading Delimited-Text Format Backups](https://dev.mysql.com/doc/refman/8.0/en/reloading-delimited-text-dumps.html)[9.4.5 mysqldump Tips](https://dev.mysql.com/doc/refman/8.0/en/mysqldump-tips.html)[9.5 Point-in-Time (Incremental) Recovery](https://dev.mysql.com/doc/refman/8.0/en/point-in-time-recovery.html)[9.5.1 Point-in-Time Recovery Using Binary Log](https://dev.mysql.com/doc/refman/8.0/en/point-in-time-recovery-binlog.html)[9.5.2 Point-in-Time Recovery Using Event Positions](https://dev.mysql.com/doc/refman/8.0/en/point-in-time-recovery-positions.html)[9.6 MyISAM Table Maintenance and Crash Recovery](https://dev.mysql.com/doc/refman/8.0/en/myisam-table-maintenance.html)[9.6.1 Using myisamchk for Crash Recovery](https://dev.mysql.com/doc/refman/8.0/en/myisam-crash-recovery.html)[9.6.2 How to Check MyISAM Tables for Errors](https://dev.mysql.com/doc/refman/8.0/en/myisam-check.html)[9.6.3 How to Repair MyISAM Tables](https://dev.mysql.com/doc/refman/8.0/en/myisam-repair.html)[9.6.4 MyISAM Table Optimization](https://dev.mysql.com/doc/refman/8.0/en/myisam-optimization.html)[9.6.5 Setting Up a MyISAM Table Maintenance Schedule](https://dev.mysql.com/doc/refman/8.0/en/myisam-maintenance-schedule.html)

It is important to back up your databases so that you can recover
your data and be up and running again in case problems occur, such
as system crashes, hardware failures, or users deleting data by
mistake. Backups are also essential as a safeguard before upgrading
a MySQL installation, and they can be used to transfer a MySQL
installation to another system or to set up replica servers.


MySQL offers a variety of backup strategies from which you can
choose the methods that best suit the requirements for your
installation. This chapter discusses several backup and recovery
topics with which you should be familiar:

- Types of backups: Logical versus physical, full versus
incremental, and so forth.


- Methods for creating backups.


- Recovery methods, including point-in-time recovery.


- Backup scheduling, compression, and encryption.


- Table maintenance, to enable recovery of corrupt tables.


## Additional Resources

Resources related to backup or to maintaining data availability
include the following:

- Customers of MySQL Enterprise Edition can use the MySQL Enterprise Backup product for backups. For an
overview of the MySQL Enterprise Backup product, see
[Section 32.1, “MySQL Enterprise Backup Overview”](https://dev.mysql.com/doc/refman/8.0/en/mysql-enterprise-backup.html "32.1 MySQL Enterprise Backup Overview").


- A forum dedicated to backup issues is available at
[https://forums.mysql.com/list.php?28](https://forums.mysql.com/list.php?28).


- Details for [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") can be found in
[Chapter 6, _MySQL Programs_](https://dev.mysql.com/doc/refman/8.0/en/programs.html "Chapter 6 MySQL Programs").


- The syntax of the SQL statements described here is given in
[Chapter 15, _SQL Statements_](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html "Chapter 15 SQL Statements").


- For additional information about `InnoDB`
backup procedures, see [Section 17.18.1, “InnoDB Backup”](https://dev.mysql.com/doc/refman/8.0/en/innodb-backup.html "17.18.1 InnoDB Backup").


- Replication enables you to maintain identical data on multiple
servers. This has several benefits, such as enabling client
query load to be distributed over servers, availability of data
even if a given server is taken offline or fails, and the
ability to make backups with no impact on the source by using a
replica. See [Chapter 19, _Replication_](https://dev.mysql.com/doc/refman/8.0/en/replication.html "Chapter 19 Replication").


- MySQL InnoDB Cluster is a collection of products that work
together to provide a high availability solution. A group of
MySQL servers can be configured to create a cluster using
MySQL Shell. The cluster of servers has a single source, called
the primary, which acts as the read-write source. Multiple
secondary servers are replicas of the source. A minimum of three
servers are required to create a high availability cluster. A
client application is connected to the primary via MySQL Router. If
the primary fails, a secondary is automatically promoted to the
role of primary, and MySQL Router routes requests to the new
primary.


- NDB Cluster provides a high-availability, high-redundancy
version of MySQL adapted for the distributed computing
environment. See [Chapter 25, _MySQL NDB Cluster 8.0_](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0"), which provides
information about MySQL NDB Cluster 8.0.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/fips-mode.html "Previous: FIPS Support") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/backup-types.html "Next: Backup and Recovery Types")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html)

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