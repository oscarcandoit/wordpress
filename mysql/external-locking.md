---
url: https://dev.mysql.com/doc/refman/8.0/en/external-locking.html
scraped_at: 2025-10-20T03:12:24.857Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html "Hide Sidebar")

[Previous: Metadata Locking](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html "Previous: Metadata Locking")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimizing Locking Operations](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html "Up: Optimizing Locking Operations")[Next: Optimizing the MySQL Server](https://dev.mysql.com/doc/refman/8.0/en/optimizing-server.html "Next: Optimizing the MySQL Server")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/external-locking.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/external-locking.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/external-locking.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/external-locking.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/external-locking.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/external-locking.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/external-locking.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/external-locking.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimizing Locking Operations](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html)  /

External Locking


### 10.11.5 External Locking

External locking is the use of file system locking to manage
contention for [`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine") database
tables by multiple processes. External locking is used in
situations where a single process such as the MySQL server
cannot be assumed to be the only process that requires access to
tables. Here are some examples:

- If you run multiple servers that use the same database
directory (not recommended), each server must have external
locking enabled.


- If you use [**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") to perform table
maintenance operations on
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine") tables, you must either
ensure that the server is not running, or that the server
has external locking enabled so that it locks table files as
necessary to coordinate with [**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility")
for access to the tables. The same is true for use of
[**myisampack**](https://dev.mysql.com/doc/refman/8.0/en/myisampack.html "6.6.6 myisampack — Generate Compressed, Read-Only MyISAM Tables") to pack
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine") tables.



If the server is run with external locking enabled, you can
use [**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") at any time for read
operations such a checking tables. In this case, if the
server tries to update a table that
[**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") is using, the server waits for
[**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") to finish before it continues.



If you use [**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") for write operations
such as repairing or optimizing tables, or if you use
[**myisampack**](https://dev.mysql.com/doc/refman/8.0/en/myisampack.html "6.6.6 myisampack — Generate Compressed, Read-Only MyISAM Tables") to pack tables, you
_must_ always ensure that the
[**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server") server is not using the table. If
you do not stop [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server"), at least do a
[**mysqladmin flush-tables**](https://dev.mysql.com/doc/refman/8.0/en/mysqladmin.html "6.5.2 mysqladmin — A MySQL Server Administration Program") before you run
[**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility"). Your tables _may_
_become corrupted_ if the server and
[**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") access the tables
simultaneously.


With external locking in effect, each process that requires
access to a table acquires a file system lock for the table
files before proceeding to access the table. If all necessary
locks cannot be acquired, the process is blocked from accessing
the table until the locks can be obtained (after the process
that currently holds the locks releases them).


External locking affects server performance because the server
must sometimes wait for other processes before it can access
tables.


External locking is unnecessary if you run a single server to
access a given data directory (which is the usual case) and if
no other programs such as [**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") need to
modify tables while the server is running. If you only
_read_ tables with other programs, external
locking is not required, although [**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility")
might report warnings if the server changes tables while
[**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") is reading them.


With external locking disabled, to use
[**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility"), you must either stop the server
while [**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility") executes or else lock and
flush the tables before running [**myisamchk**](https://dev.mysql.com/doc/refman/8.0/en/myisamchk.html "6.6.4 myisamchk — MyISAM Table-Maintenance Utility"). To
avoid this requirement, use the [`CHECK\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/check-table.html "15.7.3.2 CHECK TABLE Statement") and [`REPAIR TABLE`](https://dev.mysql.com/doc/refman/8.0/en/repair-table.html "15.7.3.5 REPAIR TABLE Statement")
statements to check and repair
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine") tables.


For [**mysqld**](https://dev.mysql.com/doc/refman/8.0/en/mysqld.html "6.3.1 mysqld — The MySQL Server"), external locking is controlled by
the value of the
[`skip_external_locking`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_skip_external_locking) system
variable. When this variable is enabled, external locking is
disabled, and vice versa. External locking is disabled by
default.


Use of external locking can be controlled at server startup by
using the [`--external-locking`](https://dev.mysql.com/doc/refman/8.0/en/server-options.html#option_mysqld_external-locking) or
[`--skip-external-locking`](https://dev.mysql.com/doc/refman/8.0/en/server-options.html#option_mysqld_external-locking)
option.


If you do use external locking option to enable updates to
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine") tables from many MySQL
processes, do not start the server with the
[`delay_key_write`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_delay_key_write) system variable
set to `ALL` or use the
`DELAY_KEY_WRITE=1` table option for any shared
tables. Otherwise, index corruption can occur.


The easiest way to satisfy this condition is to always use
[`--external-locking`](https://dev.mysql.com/doc/refman/8.0/en/server-options.html#option_mysqld_external-locking) together with
[`--delay-key-write=OFF`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_delay_key_write). (This is
not done by default because in many setups it is useful to have
a mixture of the preceding options.)

[PREV](https://dev.mysql.com/doc/refman/8.0/en/metadata-locking.html "Previous: Metadata Locking") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/locking-issues.html "Up: Optimizing Locking Operations") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/optimizing-server.html "Next: Optimizing the MySQL Server")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/external-locking.html)

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