---
url: https://dev.mysql.com/doc/refman/8.0/en/query-issues.html
scraped_at: 2025-10-20T03:11:53.254Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/query-issues.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/query-issues.html "Hide Sidebar")

[Previous: Time Zone Problems](https://dev.mysql.com/doc/refman/8.0/en/timezone-problems.html "Previous: Time Zone Problems")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Problems and Common Errors](https://dev.mysql.com/doc/refman/8.0/en/problems.html "Up: Problems and Common Errors")[Next: Case Sensitivity in String Searches](https://dev.mysql.com/doc/refman/8.0/en/case-sensitivity.html "Next: Case Sensitivity in String Searches")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/query-issues.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/query-issues.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/query-issues.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/query-issues.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/query-issues.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/query-issues.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/query-issues.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/query-issues.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/query-issues.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/query-issues.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/query-issues.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/query-issues.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/query-issues.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/query-issues.html)  / [Error Messages and Common Problems](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html)  /
[Problems and Common Errors](https://dev.mysql.com/doc/refman/8.0/en/problems.html)  /

Query-Related Issues


### B.3.4 Query-Related Issues

[B.3.4.1 Case Sensitivity in String Searches](https://dev.mysql.com/doc/refman/8.0/en/case-sensitivity.html)[B.3.4.2 Problems Using DATE Columns](https://dev.mysql.com/doc/refman/8.0/en/using-date.html)[B.3.4.3 Problems with NULL Values](https://dev.mysql.com/doc/refman/8.0/en/problems-with-null.html)[B.3.4.4 Problems with Column Aliases](https://dev.mysql.com/doc/refman/8.0/en/problems-with-alias.html)[B.3.4.5 Rollback Failure for Nontransactional Tables](https://dev.mysql.com/doc/refman/8.0/en/nontransactional-tables.html)[B.3.4.6 Deleting Rows from Related Tables](https://dev.mysql.com/doc/refman/8.0/en/deleting-from-related-tables.html)[B.3.4.7 Solving Problems with No Matching Rows](https://dev.mysql.com/doc/refman/8.0/en/no-matching-rows.html)[B.3.4.8 Problems with Floating-Point Values](https://dev.mysql.com/doc/refman/8.0/en/problems-with-float.html)

[PREV](https://dev.mysql.com/doc/refman/8.0/en/timezone-problems.html "Previous: Time Zone Problems") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/problems.html "Up: Problems and Common Errors") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/case-sensitivity.html "Next: Case Sensitivity in String Searches")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/query-issues.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/query-issues.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/query-issues.html)

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