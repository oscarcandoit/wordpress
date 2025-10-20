---
url: https://dev.mysql.com/doc/refman/8.0/en/error-handling.html
scraped_at: 2025-10-20T03:07:50.986Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html "Hide Sidebar")

[Previous: MySQL 8.0 FAQ: Virtualization Support](https://dev.mysql.com/doc/refman/8.0/en/faqs-virtualization.html "Previous: MySQL 8.0 FAQ: Virtualization Support")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up")[Next: Error Message Sources and Elements](https://dev.mysql.com/doc/refman/8.0/en/error-message-elements.html "Next: Error Message Sources and Elements")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/error-handling.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/error-handling.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/error-handling.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/error-handling.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/error-handling.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/error-handling.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/error-handling.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/error-handling.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
Error Messages and Common Problems


# Appendix B Error Messages and Common Problems

**Table of Contents**

[B.1 Error Message Sources and Elements](https://dev.mysql.com/doc/refman/8.0/en/error-message-elements.html)[B.2 Error Information Interfaces](https://dev.mysql.com/doc/refman/8.0/en/error-interfaces.html)[B.3 Problems and Common Errors](https://dev.mysql.com/doc/refman/8.0/en/problems.html)[B.3.1 How to Determine What Is Causing a Problem](https://dev.mysql.com/doc/refman/8.0/en/what-is-crashing.html)[B.3.2 Common Errors When Using MySQL Programs](https://dev.mysql.com/doc/refman/8.0/en/common-errors.html)[B.3.3 Administration-Related Issues](https://dev.mysql.com/doc/refman/8.0/en/administration-issues.html)[B.3.4 Query-Related Issues](https://dev.mysql.com/doc/refman/8.0/en/query-issues.html)[B.3.5 Optimizer-Related Issues](https://dev.mysql.com/doc/refman/8.0/en/optimizer-issues.html)[B.3.6 Table Definition-Related Issues](https://dev.mysql.com/doc/refman/8.0/en/table-definition-issues.html)[B.3.7 Known Issues in MySQL](https://dev.mysql.com/doc/refman/8.0/en/known-issues.html)

This appendix describes the types of error information MySQL
provides and how to obtain information about them. The final section
is for troubleshooting. It describes common problems and errors that
may occur and potential resolutions.

## Additional Resources

Other error-related documentation includes:

- Information about configuring where and how the server writes
the error log: [Section 7.4.2, “The Error Log”](https://dev.mysql.com/doc/refman/8.0/en/error-log.html "7.4.2 The Error Log")

- Information about the character set used for error messages:
[Section 12.6, “Error Message Character Set”](https://dev.mysql.com/doc/refman/8.0/en/charset-errors.html "12.6 Error Message Character Set")

- Information about the language used for error messages:
[Section 12.12, “Setting the Error Message Language”](https://dev.mysql.com/doc/refman/8.0/en/error-message-language.html "12.12 Setting the Error Message Language")

- Information about errors related to
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine"):
[Section 17.21.5, “InnoDB Error Handling”](https://dev.mysql.com/doc/refman/8.0/en/innodb-error-handling.html "17.21.5 InnoDB Error Handling")

- Information about errors specific to NDB Cluster:
[NDB Cluster API Errors](https://dev.mysql.com/doc/ndb-internals/en/ndb-errors.html); see also
[NDB API Errors and Error Handling](https://dev.mysql.com/doc/ndbapi/en/ndb-api-errors.html), and
[MGM API Errors](https://dev.mysql.com/doc/ndbapi/en/mgm-errors.html)

- Descriptions of the error messages that the MySQL server and
client programs generate: [MySQL 8.0 Error Message Reference](https://dev.mysql.com/doc/mysql-errors/8.0/en/)


[PREV](https://dev.mysql.com/doc/refman/8.0/en/faqs-virtualization.html "Previous: MySQL 8.0 FAQ: Virtualization Support") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/error-message-elements.html "Next: Error Message Sources and Elements")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/error-handling.html)

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