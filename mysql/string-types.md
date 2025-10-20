---
url: https://dev.mysql.com/doc/refman/8.0/en/string-types.html
scraped_at: 2025-10-20T02:59:32.785Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/string-types.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/string-types.html "Hide Sidebar")

[Previous: 2-Digit Years in Dates](https://dev.mysql.com/doc/refman/8.0/en/two-digit-years.html "Previous: 2-Digit Years in Dates")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Types](https://dev.mysql.com/doc/refman/8.0/en/data-types.html "Up: Data Types")[Next: String Data Type Syntax](https://dev.mysql.com/doc/refman/8.0/en/string-type-syntax.html "Next: String Data Type Syntax")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/string-types.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/string-types.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/string-types.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/string-types.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/string-types.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/string-types.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/string-types.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/string-types.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/string-types.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/string-types.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/string-types.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/string-types.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/string-types.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Data Types](https://dev.mysql.com/doc/refman/8.0/en/data-types.html)  /
String Data Types


## 13.3 String Data Types

[13.3.1 String Data Type Syntax](https://dev.mysql.com/doc/refman/8.0/en/string-type-syntax.html)[13.3.2 The CHAR and VARCHAR Types](https://dev.mysql.com/doc/refman/8.0/en/char.html)[13.3.3 The BINARY and VARBINARY Types](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html)[13.3.4 The BLOB and TEXT Types](https://dev.mysql.com/doc/refman/8.0/en/blob.html)[13.3.5 The ENUM Type](https://dev.mysql.com/doc/refman/8.0/en/enum.html)[13.3.6 The SET Type](https://dev.mysql.com/doc/refman/8.0/en/set.html)

The string data types are [`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`BINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"),
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types"),
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types"),
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types"),
[`ENUM`](https://dev.mysql.com/doc/refman/8.0/en/enum.html "13.3.5 The ENUM Type"), and
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set.html "13.3.6 The SET Type").


For information about storage requirements of the string data
types, see [Section 13.7, “Data Type Storage Requirements”](https://dev.mysql.com/doc/refman/8.0/en/storage-requirements.html "13.7 Data Type Storage Requirements").


For descriptions of functions that operate on string values, see
[Section 14.8, “String Functions and Operators”](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html "14.8 String Functions and Operators").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/two-digit-years.html "Previous: 2-Digit Years in Dates") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/data-types.html "Up: Data Types") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/string-type-syntax.html "Next: String Data Type Syntax")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/string-types.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/string-types.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/string-types.html)

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