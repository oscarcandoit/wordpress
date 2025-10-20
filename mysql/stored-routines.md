---
url: https://dev.mysql.com/doc/refman/8.0/en/stored-routines.html
scraped_at: 2025-10-20T03:05:29.561Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/stored-routines.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/stored-routines.html "Hide Sidebar")

[Previous: Defining Stored Programs](https://dev.mysql.com/doc/refman/8.0/en/stored-programs-defining.html "Previous: Defining Stored Programs")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Stored Objects](https://dev.mysql.com/doc/refman/8.0/en/stored-objects.html "Up: Stored Objects")[Next: Stored Routine Syntax](https://dev.mysql.com/doc/refman/8.0/en/stored-routines-syntax.html "Next: Stored Routine Syntax")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/stored-routines.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/stored-routines.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/stored-routines.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/stored-routines.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/stored-routines.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/stored-routines.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/stored-routines.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/stored-routines.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/stored-routines.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/stored-routines.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/stored-routines.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/stored-routines.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/stored-routines.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Stored Objects](https://dev.mysql.com/doc/refman/8.0/en/stored-objects.html)  /
Using Stored Routines


## 27.2 Using Stored Routines

[27.2.1 Stored Routine Syntax](https://dev.mysql.com/doc/refman/8.0/en/stored-routines-syntax.html)[27.2.2 Stored Routines and MySQL Privileges](https://dev.mysql.com/doc/refman/8.0/en/stored-routines-privileges.html)[27.2.3 Stored Routine Metadata](https://dev.mysql.com/doc/refman/8.0/en/stored-routines-metadata.html)[27.2.4 Stored Procedures, Functions, Triggers, and LAST\_INSERT\_ID()](https://dev.mysql.com/doc/refman/8.0/en/stored-routines-last-insert-id.html)

MySQL supports stored routines (procedures and functions). A stored
routine is a set of SQL statements that can be stored in the server.
Once this has been done, clients don't need to keep reissuing the
individual statements but can refer to the stored routine instead.


Stored routines can be particularly useful in certain situations:

- When multiple client applications are written in different
languages or work on different platforms, but need to perform
the same database operations.


- When security is paramount. Banks, for example, use stored
procedures and functions for all common operations. This
provides a consistent and secure environment, and routines can
ensure that each operation is properly logged. In such a setup,
applications and users would have no access to the database
tables directly, but can only execute specific stored routines.


Stored routines can provide improved performance because less
information needs to be sent between the server and the client. The
tradeoff is that this does increase the load on the database server
because more of the work is done on the server side and less is done
on the client (application) side. Consider this if many client
machines (such as Web servers) are serviced by only one or a few
database servers.


Stored routines also enable you to have libraries of functions in
the database server. This is a feature shared by modern application
languages that enable such design internally (for example, by using
classes). Using these client application language features is
beneficial for the programmer even outside the scope of database
use.


MySQL follows the SQL:2003 syntax for stored routines, which is also
used by IBM's DB2. All syntax described here is supported and any
limitations and extensions are documented where appropriate.

### Additional Resources

- You may find the [Stored\\
Procedures User Forum](https://forums.mysql.com/list.php?98) of use when working with stored
procedures and functions.


- For answers to some commonly asked questions regarding stored
routines in MySQL, see [Section A.4, “MySQL 8.0 FAQ: Stored Procedures and Functions”](https://dev.mysql.com/doc/refman/8.0/en/faqs-stored-procs.html "A.4 MySQL 8.0 FAQ: Stored Procedures and Functions").


- There are some restrictions on the use of stored routines. See
[Section 27.8, “Restrictions on Stored Programs”](https://dev.mysql.com/doc/refman/8.0/en/stored-program-restrictions.html "27.8 Restrictions on Stored Programs").


- Binary logging for stored routines takes place as described in
[Section 27.7, “Stored Program Binary Logging”](https://dev.mysql.com/doc/refman/8.0/en/stored-programs-logging.html "27.7 Stored Program Binary Logging").


[PREV](https://dev.mysql.com/doc/refman/8.0/en/stored-programs-defining.html "Previous: Defining Stored Programs") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/stored-objects.html "Up: Stored Objects") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/stored-routines-syntax.html "Next: Stored Routine Syntax")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/stored-routines.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/stored-routines.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/stored-routines.html)

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