---
url: https://dev.mysql.com/doc/refman/8.0/en/common-errors.html
scraped_at: 2025-10-20T03:11:44.434Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/common-errors.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/common-errors.html "Hide Sidebar")

[Previous: How to Determine What Is Causing a Problem](https://dev.mysql.com/doc/refman/8.0/en/what-is-crashing.html "Previous: How to Determine What Is Causing a Problem")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Problems and Common Errors](https://dev.mysql.com/doc/refman/8.0/en/problems.html "Up: Problems and Common Errors")[Next: Access denied](https://dev.mysql.com/doc/refman/8.0/en/error-access-denied.html "Next: Access denied")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/common-errors.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/common-errors.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/common-errors.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/common-errors.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/common-errors.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/common-errors.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/common-errors.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/common-errors.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/common-errors.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/common-errors.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/common-errors.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/common-errors.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/common-errors.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/common-errors.html)  / [Error Messages and Common Problems](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html)  /
[Problems and Common Errors](https://dev.mysql.com/doc/refman/8.0/en/problems.html)  /

Common Errors When Using MySQL Programs


### B.3.2 Common Errors When Using MySQL Programs

[B.3.2.1 Access denied](https://dev.mysql.com/doc/refman/8.0/en/error-access-denied.html)[B.3.2.2 Can't connect to \[local\] MySQL server](https://dev.mysql.com/doc/refman/8.0/en/can-not-connect-to-server.html)[B.3.2.3 Lost connection to MySQL server](https://dev.mysql.com/doc/refman/8.0/en/error-lost-connection.html)[B.3.2.4 Password Fails When Entered Interactively](https://dev.mysql.com/doc/refman/8.0/en/password-too-long.html)[B.3.2.5 Too many connections](https://dev.mysql.com/doc/refman/8.0/en/too-many-connections.html)[B.3.2.6 Out of memory](https://dev.mysql.com/doc/refman/8.0/en/out-of-memory.html)[B.3.2.7 MySQL server has gone away](https://dev.mysql.com/doc/refman/8.0/en/gone-away.html)[B.3.2.8 Packet Too Large](https://dev.mysql.com/doc/refman/8.0/en/packet-too-large.html)[B.3.2.9 Communication Errors and Aborted Connections](https://dev.mysql.com/doc/refman/8.0/en/communication-errors.html)[B.3.2.10 The table is full](https://dev.mysql.com/doc/refman/8.0/en/full-table.html)[B.3.2.11 Can't create/write to file](https://dev.mysql.com/doc/refman/8.0/en/cannot-create.html)[B.3.2.12 Commands out of sync](https://dev.mysql.com/doc/refman/8.0/en/commands-out-of-sync.html)[B.3.2.13 Ignoring user](https://dev.mysql.com/doc/refman/8.0/en/ignoring-user.html)[B.3.2.14 Table 'tbl\_name' doesn't exist](https://dev.mysql.com/doc/refman/8.0/en/cannot-find-table.html)[B.3.2.15 Can't initialize character set](https://dev.mysql.com/doc/refman/8.0/en/cannot-initialize-character-set.html)[B.3.2.16 File Not Found and Similar Errors](https://dev.mysql.com/doc/refman/8.0/en/not-enough-file-handles.html)[B.3.2.17 Table-Corruption Issues](https://dev.mysql.com/doc/refman/8.0/en/table-corruption.html)

This section lists some errors that users frequently encounter
when running MySQL programs. Although the problems show up when
you try to run client programs, the solutions to many of the
problems involves changing the configuration of the MySQL
server.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/what-is-crashing.html "Previous: How to Determine What Is Causing a Problem") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/problems.html "Up: Problems and Common Errors") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/error-access-denied.html "Next: Access denied")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/common-errors.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/common-errors.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/common-errors.html)

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