---
url: https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html
scraped_at: 2025-10-20T03:03:44.046Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html "Hide Sidebar")

[Previous: Binary Log File Position Based Replication Configuration Overview](https://dev.mysql.com/doc/refman/8.0/en/binlog-replication-configuration-overview.html "Previous: Binary Log File Position Based Replication Configuration Overview")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Configuring Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html "Up: Configuring Replication")[Next: Setting the Replication Source Configuration](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-masterbaseconfig.html "Next: Setting the Replication Source Configuration")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/replication-howto.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/replication-howto.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/replication-howto.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/replication-howto.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/replication-howto.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/replication-howto.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/replication-howto.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/replication-howto.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html)  / [Replication](https://dev.mysql.com/doc/refman/8.0/en/replication.html)  /
[Configuring Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html)  /

Setting Up Binary Log File Position Based Replication


### 19.1.2 Setting Up Binary Log File Position Based Replication

[19.1.2.1 Setting the Replication Source Configuration](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-masterbaseconfig.html)[19.1.2.2 Setting the Replica Configuration](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-slavebaseconfig.html)[19.1.2.3 Creating a User for Replication](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-repuser.html)[19.1.2.4 Obtaining the Replication Source Binary Log Coordinates](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-masterstatus.html)[19.1.2.5 Choosing a Method for Data Snapshots](https://dev.mysql.com/doc/refman/8.0/en/replication-snapshot-method.html)[19.1.2.6 Setting Up Replicas](https://dev.mysql.com/doc/refman/8.0/en/replication-setup-replicas.html)[19.1.2.7 Setting the Source Configuration on the Replica](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-slaveinit.html)[19.1.2.8 Adding Replicas to a Replication Environment](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-additionalslaves.html)

This section describes how to set up a MySQL server to use binary
log file position based replication. There are a number of
different methods for setting up replication, and the exact method
to use depends on how you are setting up replication, and whether
you already have data in the database on the source that you want
to replicate.

Tip

To deploy multiple instances of MySQL, you can use [InnoDB Cluster](https://dev.mysql.com/doc/mysql-shell/8.0/en/mysql-innodb-cluster.html) which enables you to easily administer a group of MySQL server instances in [MySQL Shell](https://dev.mysql.com/doc/mysql-shell/8.0/en/). InnoDB Cluster wraps MySQL Group Replication in a programmatic environment that enables you easily deploy a cluster of MySQL instances to achieve high availability. In addition, InnoDB Cluster interfaces seamlessly with [MySQL Router](https://dev.mysql.com/doc/mysql-router/8.0/en/), which enables your applications to connect to the cluster without writing your own failover process. For similar use cases that do not require high availability, however, you can use [InnoDB ReplicaSet](https://dev.mysql.com/doc/mysql-shell/8.0/en/mysql-innodb-replicaset.html). Installation instructions for MySQL Shell can be found [here](https://dev.mysql.com/doc/mysql-shell/8.0/en/mysql-shell-install.html).

There are some generic tasks that are common to all setups:

- On the source, you must ensure that binary logging is enabled,
and configure a unique server ID. This might require a server
restart. See
[Section 19.1.2.1, “Setting the Replication Source Configuration”](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-masterbaseconfig.html "19.1.2.1 Setting the Replication Source Configuration").


- On each replica that you want to connect to the source, you
must configure a unique server ID. This might require a server
restart. See
[Section 19.1.2.2, “Setting the Replica Configuration”](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-slavebaseconfig.html "19.1.2.2 Setting the Replica Configuration").


- Optionally, create a separate user for your replicas to use
during authentication with the source when reading the binary
log for replication. See
[Section 19.1.2.3, “Creating a User for Replication”](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-repuser.html "19.1.2.3 Creating a User for Replication").


- Before creating a data snapshot or starting the replication
process, on the source you should record the current position
in the binary log. You need this information when configuring
the replica so that the replica knows where within the binary
log to start executing events. See
[Section 19.1.2.4, “Obtaining the Replication Source Binary Log Coordinates”](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-masterstatus.html "19.1.2.4 Obtaining the Replication Source Binary Log Coordinates").


- If you already have data on the source and want to use it to
synchronize the replica, you need to create a data snapshot to
copy the data to the replica. The storage engine you are using
has an impact on how you create the snapshot. When you are
using [`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine"), you must stop
processing statements on the source to obtain a read-lock,
then obtain its current binary log coordinates and dump its
data, before permitting the source to continue executing
statements. If you do not stop the execution of statements,
the data dump and the source status information become
mismatched, resulting in inconsistent or corrupted databases
on the replicas. For more information on replicating a
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine") source, see
[Section 19.1.2.4, “Obtaining the Replication Source Binary Log Coordinates”](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-masterstatus.html "19.1.2.4 Obtaining the Replication Source Binary Log Coordinates"). If you are
using [`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine"), you do not need a
read-lock and a transaction that is long enough to transfer
the data snapshot is sufficient. For more information, see
[Section 17.19, “InnoDB and MySQL Replication”](https://dev.mysql.com/doc/refman/8.0/en/innodb-and-mysql-replication.html "17.19 InnoDB and MySQL Replication").


- Configure the replica with settings for connecting to the
source, such as the host name, login credentials, and binary
log file name and position. See
[Section 19.1.2.7, “Setting the Source Configuration on the Replica”](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-slaveinit.html "19.1.2.7 Setting the Source Configuration on the Replica").


- Implement replication-specific security measures on the
sources and replicas as appropriate for your system. See
[Section 19.3, “Replication Security”](https://dev.mysql.com/doc/refman/8.0/en/replication-security.html "19.3 Replication Security").


Note

Certain steps within the setup process require the
[`SUPER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_super) privilege. If you do not
have this privilege, it might not be possible to enable
replication.

After configuring the basic options, select your scenario:

- To set up replication for a fresh installation of a source and
replicas that contain no data, see
[Section 19.1.2.6.1, “Setting Up Replication with New Source and Replicas”](https://dev.mysql.com/doc/refman/8.0/en/replication-setup-replicas.html#replication-howto-newservers "19.1.2.6.1 Setting Up Replication with New Source and Replicas").


- To set up replication of a new source using the data from an
existing MySQL server, see
[Section 19.1.2.6.2, “Setting Up Replication with Existing Data”](https://dev.mysql.com/doc/refman/8.0/en/replication-setup-replicas.html#replication-howto-existingdata "19.1.2.6.2 Setting Up Replication with Existing Data").


- To add replicas to an existing replication environment, see
[Section 19.1.2.8, “Adding Replicas to a Replication Environment”](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-additionalslaves.html "19.1.2.8 Adding Replicas to a Replication Environment").


Before administering MySQL replication servers, read this entire
chapter and try all statements mentioned in
[Section 15.4.1, “SQL Statements for Controlling Source Servers”](https://dev.mysql.com/doc/refman/8.0/en/replication-statements-master.html "15.4.1 SQL Statements for Controlling Source Servers"), and
[Section 15.4.2, “SQL Statements for Controlling Replica Servers”](https://dev.mysql.com/doc/refman/8.0/en/replication-statements-replica.html "15.4.2 SQL Statements for Controlling Replica Servers"). Also familiarize
yourself with the replication startup options described in
[Section 19.1.6, “Replication and Binary Logging Options and Variables”](https://dev.mysql.com/doc/refman/8.0/en/replication-options.html "19.1.6 Replication and Binary Logging Options and Variables").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/binlog-replication-configuration-overview.html "Previous: Binary Log File Position Based Replication Configuration Overview") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/replication-configuration.html "Up: Configuring Replication") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/replication-howto-masterbaseconfig.html "Next: Setting the Replication Source Configuration")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/replication-howto.html)

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