---
url: https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html
scraped_at: 2025-10-20T03:03:50.747Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html "Hide Sidebar")

[Previous: Restrictions on Performance Schema](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-restrictions.html "Previous: Restrictions on Performance Schema")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up")[Next: Prerequisites for Using the sys Schema](https://dev.mysql.com/doc/refman/8.0/en/sys-schema-prerequisites.html "Next: Prerequisites for Using the sys Schema")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/sys-schema.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/sys-schema.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/sys-schema.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/sys-schema.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/sys-schema.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/sys-schema.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/sys-schema.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/sys-schema.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
MySQL sys Schema


# Chapter 30 MySQL sys Schema

**Table of Contents**

[30.1 Prerequisites for Using the sys Schema](https://dev.mysql.com/doc/refman/8.0/en/sys-schema-prerequisites.html)[30.2 Using the sys Schema](https://dev.mysql.com/doc/refman/8.0/en/sys-schema-usage.html)[30.3 sys Schema Progress Reporting](https://dev.mysql.com/doc/refman/8.0/en/sys-schema-progress-reporting.html)[30.4 sys Schema Object Reference](https://dev.mysql.com/doc/refman/8.0/en/sys-schema-reference.html)[30.4.1 sys Schema Object Index](https://dev.mysql.com/doc/refman/8.0/en/sys-schema-object-index.html)[30.4.2 sys Schema Tables and Triggers](https://dev.mysql.com/doc/refman/8.0/en/sys-schema-tables.html)[30.4.3 sys Schema Views](https://dev.mysql.com/doc/refman/8.0/en/sys-schema-views.html)[30.4.4 sys Schema Stored Procedures](https://dev.mysql.com/doc/refman/8.0/en/sys-schema-procedures.html)[30.4.5 sys Schema Stored Functions](https://dev.mysql.com/doc/refman/8.0/en/sys-schema-functions.html)

MySQL 8.0 includes the
[`sys`](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html "Chapter 30 MySQL sys Schema") schema, a set of objects that
helps DBAs and developers interpret data collected by the
Performance Schema. [`sys`](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html "Chapter 30 MySQL sys Schema") schema objects
can be used for typical tuning and diagnosis use cases. Objects in
this schema include:

- Views that summarize Performance Schema data into more easily
understandable form.


- Stored procedures that perform operations such as Performance
Schema configuration and generating diagnostic reports.


- Stored functions that query Performance Schema configuration and
provide formatting services.


For new installations, the [`sys`](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html "Chapter 30 MySQL sys Schema") schema
is installed by default during data directory initialization if you
use [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server") with the
[`--initialize`](https://dev.mysql.com/doc/refman/8.0/en/server-options.html#option_mysqld_initialize) or
[`--initialize-insecure`](https://dev.mysql.com/doc/refman/8.0/en/server-options.html#option_mysqld_initialize-insecure) option. If this
is not desired, you can drop the [`sys`](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html "Chapter 30 MySQL sys Schema")
schema manually after initialization if it is unneeded.


The MySQL upgrade procedure produces an error if a
[`sys`](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html "Chapter 30 MySQL sys Schema") schema exists but has no
[`version`](https://dev.mysql.com/doc/refman/8.0/en/sys-version.html "30.4.3.47 The version View") view, on the assumption that
absence of this view indicates a user-created `sys`
schema. To upgrade in this case, remove or rename the existing
[`sys`](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html "Chapter 30 MySQL sys Schema") schema first.


[`sys`](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html "Chapter 30 MySQL sys Schema") schema objects have a
`DEFINER` of
`'mysql.sys'@'localhost'`. Use of the dedicated
`mysql.sys` account avoids problems that occur if a
DBA renames or removes the `root` account.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-restrictions.html "Previous: Restrictions on Performance Schema") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/sys-schema-prerequisites.html "Next: Prerequisites for Using the sys Schema")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/sys-schema.html)

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