---
url: https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html
scraped_at: 2025-10-20T03:15:36.648Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html "Hide Sidebar")

[Previous: InnoDB Full-Text Indexes](https://dev.mysql.com/doc/refman/8.0/en/innodb-fulltext-index.html "Previous: InnoDB Full-Text Indexes")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: InnoDB On-Disk Structures](https://dev.mysql.com/doc/refman/8.0/en/innodb-on-disk-structures.html "Up: InnoDB On-Disk Structures")[Next: The System Tablespace](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html "Next: The System Tablespace")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/innodb-tablespace.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/innodb-tablespace.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/innodb-tablespace.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/innodb-tablespace.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/innodb-tablespace.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/innodb-tablespace.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/innodb-tablespace.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/innodb-tablespace.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)  / [The InnoDB Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html)  /
[InnoDB On-Disk Structures](https://dev.mysql.com/doc/refman/8.0/en/innodb-on-disk-structures.html)  /

Tablespaces


### 17.6.3 Tablespaces

[17.6.3.1 The System Tablespace](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html)[17.6.3.2 File-Per-Table Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-file-per-table-tablespaces.html)[17.6.3.3 General Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/general-tablespaces.html)[17.6.3.4 Undo Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-tablespaces.html)[17.6.3.5 Temporary Tablespaces](https://dev.mysql.com/doc/refman/8.0/en/innodb-temporary-tablespace.html)[17.6.3.6 Moving Tablespace Files While the Server is Offline](https://dev.mysql.com/doc/refman/8.0/en/innodb-moving-data-files-offline.html)[17.6.3.7 Disabling Tablespace Path Validation](https://dev.mysql.com/doc/refman/8.0/en/innodb-disabling-tablespace-path-validation.html)[17.6.3.8 Optimizing Tablespace Space Allocation on Linux](https://dev.mysql.com/doc/refman/8.0/en/innodb-optimize-tablespace-page-allocation.html)[17.6.3.9 Tablespace AUTOEXTEND\_SIZE Configuration](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace-autoextend-size.html)

This section covers topics related to `InnoDB`
tablespaces.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/innodb-fulltext-index.html "Previous: InnoDB Full-Text Indexes") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/innodb-on-disk-structures.html "Up: InnoDB On-Disk Structures") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/innodb-system-tablespace.html "Next: The System Tablespace")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/innodb-tablespace.html)

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