---
url: https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html
scraped_at: 2025-10-20T03:05:51.577Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html "Hide Sidebar")

[Previous: Trigger Syntax and Examples](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html "Previous: Trigger Syntax and Examples")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Using Triggers](https://dev.mysql.com/doc/refman/8.0/en/triggers.html "Up: Using Triggers")[Next: Using the Event Scheduler](https://dev.mysql.com/doc/refman/8.0/en/event-scheduler.html "Next: Using the Event Scheduler")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/trigger-metadata.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/trigger-metadata.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/trigger-metadata.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/trigger-metadata.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/trigger-metadata.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/trigger-metadata.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/trigger-metadata.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/trigger-metadata.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html)  / [Stored Objects](https://dev.mysql.com/doc/refman/8.0/en/stored-objects.html)  /
[Using Triggers](https://dev.mysql.com/doc/refman/8.0/en/triggers.html)  /

Trigger Metadata


### 27.3.2 Trigger Metadata

To obtain metadata about triggers:

- Query the [`TRIGGERS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-triggers-table.html "28.3.45 The INFORMATION_SCHEMA TRIGGERS Table") table of the
`INFORMATION_SCHEMA` database. See
[Section 28.3.45, “The INFORMATION\_SCHEMA TRIGGERS Table”](https://dev.mysql.com/doc/refman/8.0/en/information-schema-triggers-table.html "28.3.45 The INFORMATION_SCHEMA TRIGGERS Table").


- Use the [`SHOW CREATE TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/show-create-trigger.html "15.7.7.11 SHOW CREATE TRIGGER Statement")
statement. See [Section 15.7.7.11, “SHOW CREATE TRIGGER Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-create-trigger.html "15.7.7.11 SHOW CREATE TRIGGER Statement").


- Use the [`SHOW TRIGGERS`](https://dev.mysql.com/doc/refman/8.0/en/show-triggers.html "15.7.7.40 SHOW TRIGGERS Statement")
statement. See [Section 15.7.7.40, “SHOW TRIGGERS Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-triggers.html "15.7.7.40 SHOW TRIGGERS Statement").


[PREV](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html "Previous: Trigger Syntax and Examples") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/triggers.html "Up: Using Triggers") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/event-scheduler.html "Next: Using the Event Scheduler")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html)

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