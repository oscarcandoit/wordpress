---
url: https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html
scraped_at: 2025-10-20T03:03:59.111Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html "Hide Sidebar")

[Previous: Optimization Overview](https://dev.mysql.com/doc/refman/8.0/en/optimize-overview.html "Previous: Optimization Overview")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html "Up: Optimization")[Next: Optimizing SELECT Statements](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html "Next: Optimizing SELECT Statements")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/statement-optimization.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/statement-optimization.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/statement-optimization.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/statement-optimization.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/statement-optimization.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/statement-optimization.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/statement-optimization.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/statement-optimization.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
Optimizing SQL Statements


## 10.2 Optimizing SQL Statements

[10.2.1 Optimizing SELECT Statements](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html)[10.2.2 Optimizing Subqueries, Derived Tables, View References, and Common Table\\
Expressions](https://dev.mysql.com/doc/refman/8.0/en/subquery-optimization.html)[10.2.3 Optimizing INFORMATION\_SCHEMA Queries](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html)[10.2.4 Optimizing Performance Schema Queries](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-optimization.html)[10.2.5 Optimizing Data Change Statements](https://dev.mysql.com/doc/refman/8.0/en/data-change-optimization.html)[10.2.6 Optimizing Database Privileges](https://dev.mysql.com/doc/refman/8.0/en/permission-optimization.html)[10.2.7 Other Optimization Tips](https://dev.mysql.com/doc/refman/8.0/en/miscellaneous-optimization-tips.html)

The core logic of a database application is performed through SQL
statements, whether issued directly through an interpreter or
submitted behind the scenes through an API. The tuning guidelines
in this section help to speed up all kinds of MySQL applications.
The guidelines cover SQL operations that read and write data, the
behind-the-scenes overhead for SQL operations in general, and
operations used in specific scenarios such as database monitoring.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/optimize-overview.html "Previous: Optimization Overview") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/optimization.html "Up: Optimization") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/select-optimization.html "Next: Optimizing SELECT Statements")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)

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