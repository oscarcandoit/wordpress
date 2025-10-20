---
url: https://dev.mysql.com/doc/refman/8.0/en/mysql-batch-commands.html
scraped_at: 2025-10-20T03:02:36.193Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/mysql-batch-commands.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/mysql-batch-commands.html "Hide Sidebar")

[Previous: mysql Client Server-Side Help](https://dev.mysql.com/doc/refman/8.0/en/mysql-server-side-help.html "Previous: mysql Client Server-Side Help")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: mysql — The MySQL Command-Line Client](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "Up: mysql — The MySQL Command-Line Client")[Next: mysql Client Tips](https://dev.mysql.com/doc/refman/8.0/en/mysql-tips.html "Next: mysql Client Tips")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/mysql-batch-commands.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysql-batch-commands.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysql-batch-commands.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/mysql-batch-commands.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/mysql-batch-commands.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/mysql-batch-commands.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/mysql-batch-commands.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/mysql-batch-commands.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/mysql-batch-commands.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/mysql-batch-commands.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/mysql-batch-commands.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/mysql-batch-commands.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/mysql-batch-commands.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/mysql-batch-commands.html)  / [MySQL Programs](https://dev.mysql.com/doc/refman/8.0/en/programs.html)  /
[Client Programs](https://dev.mysql.com/doc/refman/8.0/en/programs-client.html)  /
[mysql — The MySQL Command-Line Client](https://dev.mysql.com/doc/refman/8.0/en/mysql.html)  /

Executing SQL Statements from a Text File


#### 6.5.1.5 Executing SQL Statements from a Text File

The [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client typically is used
interactively, like this:


```terminal
mysql db_name
```

However, it is also possible to put your SQL statements in a
file and then tell [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") to read its input
from that file. To do so, create a text file
_`text_file`_ that contains the
statements you wish to execute. Then invoke
[**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") as shown here:


```terminal
mysql db_name < text_file
```

If you place a `USE
        db_name` statement as the
first statement in the file, it is unnecessary to specify the
database name on the command line:


```terminal
mysql < text_file
```

If you are already running [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client"), you can
execute an SQL script file using the `source`
command or `\.` command:


```sql
mysql> source file_name
mysql> \. file_name
```

Sometimes you may want your script to display progress
information to the user. For this you can insert statements like
this:


```sql
SELECT '<info_to_display>' AS ' ';
```

The statement shown outputs
`<info_to_display>`.


You can also invoke [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") with the
[`--verbose`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_verbose) option, which causes
each statement to be displayed before the result that it
produces.


[**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") ignores Unicode byte order mark (BOM)
characters at the beginning of input files. Previously, it read
them and sent them to the server, resulting in a syntax error.
Presence of a BOM does not cause [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") to
change its default character set. To do that, invoke
[**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") with an option such as
[`--default-character-set=utf8mb4`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_default-character-set).


For more information about batch mode, see
[Section 5.5, “Using mysql in Batch Mode”](https://dev.mysql.com/doc/refman/8.0/en/batch-mode.html "5.5 Using mysql in Batch Mode").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/mysql-server-side-help.html "Previous: mysql Client Server-Side Help") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "Up: mysql — The MySQL Command-Line Client") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/mysql-tips.html "Next: mysql Client Tips")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/mysql-batch-commands.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysql-batch-commands.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/mysql-batch-commands.html)

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