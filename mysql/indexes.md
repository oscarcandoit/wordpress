---
url: https://dev.mysql.com/doc/refman/8.0/en/indexes.html
scraped_at: 2025-10-20T02:59:02.648Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/indexes.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/indexes.html "Hide Sidebar")

[Previous: Known Issues in MySQL](https://dev.mysql.com/doc/refman/8.0/en/known-issues.html "Previous: Known Issues in MySQL")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up")[Next: General Index](https://dev.mysql.com/doc/refman/8.0/en/ix01.html "Next: General Index")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/indexes.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/indexes.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/indexes.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/indexes.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/indexes.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/indexes.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/indexes.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/indexes.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/indexes.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/indexes.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/indexes.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
Indexes


# Appendix C Indexes

**Table of Contents**

[General Index](https://dev.mysql.com/doc/refman/8.0/en/ix01.html)[C Function Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-cfunc.html)[Command Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-command.html)[Function Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-function.html)[INFORMATION\_SCHEMA Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-is.html)[Join Types Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-jointype.html)[Operator Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-operator.html)[Option Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-option.html)[Privileges Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-priv.html)[SQL Modes Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-sqlmode.html)[Statement/Syntax Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-statement.html)[Status Variable Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-statvar.html)[System Variable Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-sysvar.html)[Transaction Isolation Level Index](https://dev.mysql.com/doc/refman/8.0/en/dynindex-isolevel.html)

[PREV](https://dev.mysql.com/doc/refman/8.0/en/known-issues.html "Previous: Known Issues in MySQL") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/ix01.html "Next: General Index")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/indexes.html)

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