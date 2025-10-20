---
url: https://dev.mysql.com/doc/refman/8.0/en/loop.html
scraped_at: 2025-10-20T03:09:26.350Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/loop.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/loop.html "Hide Sidebar")

[Previous: LEAVE Statement](https://dev.mysql.com/doc/refman/8.0/en/leave.html "Previous: LEAVE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Flow Control Statements](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html "Up: Flow Control Statements")[Next: REPEAT Statement](https://dev.mysql.com/doc/refman/8.0/en/repeat.html "Next: REPEAT Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/loop.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/loop.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/loop.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/loop.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/loop.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/loop.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/loop.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/loop.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/loop.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/loop.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/loop.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/loop.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/loop.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/loop.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Compound Statement Syntax](https://dev.mysql.com/doc/refman/8.0/en/sql-compound-statements.html)  /
[Flow Control Statements](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html)  /

LOOP Statement


#### 15.6.5.5 LOOP Statement

```sql
[begin_label:] LOOP
    statement_list
END LOOP [end_label]
```

[`LOOP`](https://dev.mysql.com/doc/refman/8.0/en/loop.html "15.6.5.5 LOOP Statement") implements a simple loop
construct, enabling repeated execution of the statement list,
which consists of one or more statements, each terminated by a
semicolon ( `;`) statement delimiter. The
statements within the loop are repeated until the loop is
terminated. Usually, this is accomplished with a
[`LEAVE`](https://dev.mysql.com/doc/refman/8.0/en/leave.html "15.6.5.4 LEAVE Statement") statement. Within a stored
function, [`RETURN`](https://dev.mysql.com/doc/refman/8.0/en/return.html "15.6.5.7 RETURN Statement") can also be
used, which exits the function entirely.


Neglecting to include a loop-termination statement results in an
infinite loop.


A [`LOOP`](https://dev.mysql.com/doc/refman/8.0/en/loop.html "15.6.5.5 LOOP Statement") statement can be labeled.
For the rules regarding label use, see
[Section 15.6.2, “Statement Labels”](https://dev.mysql.com/doc/refman/8.0/en/statement-labels.html "15.6.2 Statement Labels").


Example:


```sql
CREATE PROCEDURE doiterate(p1 INT)
BEGIN
  label1: LOOP
    SET p1 = p1 + 1;
    IF p1 < 10 THEN
      ITERATE label1;
    END IF;
    LEAVE label1;
  END LOOP label1;
  SET @x = p1;
END;
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/leave.html "Previous: LEAVE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html "Up: Flow Control Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/repeat.html "Next: REPEAT Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/loop.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/loop.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/loop.html)

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