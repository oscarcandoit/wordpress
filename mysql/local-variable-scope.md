---
url: https://dev.mysql.com/doc/refman/8.0/en/local-variable-scope.html
scraped_at: 2025-10-20T03:09:07.275Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/local-variable-scope.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/local-variable-scope.html "Hide Sidebar")

[Previous: Local Variable DECLARE Statement](https://dev.mysql.com/doc/refman/8.0/en/declare-local-variable.html "Previous: Local Variable DECLARE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Variables in Stored Programs](https://dev.mysql.com/doc/refman/8.0/en/stored-program-variables.html "Up: Variables in Stored Programs")[Next: Flow Control Statements](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html "Next: Flow Control Statements")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/local-variable-scope.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/local-variable-scope.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/local-variable-scope.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/local-variable-scope.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/local-variable-scope.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/local-variable-scope.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/local-variable-scope.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/local-variable-scope.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/local-variable-scope.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/local-variable-scope.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/local-variable-scope.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/local-variable-scope.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/local-variable-scope.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/local-variable-scope.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Compound Statement Syntax](https://dev.mysql.com/doc/refman/8.0/en/sql-compound-statements.html)  /
[Variables in Stored Programs](https://dev.mysql.com/doc/refman/8.0/en/stored-program-variables.html)  /

Local Variable Scope and Resolution


#### 15.6.4.2 Local Variable Scope and Resolution

The scope of a local variable is the
[`BEGIN ...\\
        END`](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement") block within which it is declared. The variable
can be referred to in blocks nested within the declaring block,
except those blocks that declare a variable with the same name.


Because local variables are in scope only during stored program
execution, references to them are not permitted in prepared
statements created within a stored program. Prepared statement
scope is the current session, not the stored program, so the
statement could be executed after the program ends, at which
point the variables would no longer be in scope. For example,
`SELECT ... INTO
        local_var` cannot be used as
a prepared statement. This restriction also applies to stored
procedure and function parameters. See
[Section 15.5.1, “PREPARE Statement”](https://dev.mysql.com/doc/refman/8.0/en/prepare.html "15.5.1 PREPARE Statement").


A local variable should not have the same name as a table
column. If an SQL statement, such as a
[`SELECT ...\\
        INTO`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement, contains a reference to a column and a
declared local variable with the same name, MySQL currently
interprets the reference as the name of a variable. Consider the
following procedure definition:


``` sql

CREATE PROCEDURE sp1 (x VARCHAR(5))
BEGIN
  DECLARE xname VARCHAR(5) DEFAULT 'bob';
  DECLARE newname VARCHAR(5);
  DECLARE xid INT;

  SELECT xname, id INTO newname, xid
    FROM table1 WHERE xname = xname;
  SELECT newname;
END;
```

MySQL interprets `xname` in the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement as a reference
to the `xname` _variable_
rather than the `xname` _column_. Consequently, when the procedure
`sp1()` is called, the
`newname` variable returns the value
`'bob'` regardless of the value of the
`table1.xname` column.


Similarly, the cursor definition in the following procedure
contains a [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement that
refers to `xname`. MySQL interprets this as a
reference to the variable of that name rather than a column
reference.


``` sql

CREATE PROCEDURE sp2 (x VARCHAR(5))
BEGIN
  DECLARE xname VARCHAR(5) DEFAULT 'bob';
  DECLARE newname VARCHAR(5);
  DECLARE xid INT;
  DECLARE done TINYINT DEFAULT 0;
  DECLARE cur1 CURSOR FOR SELECT xname, id FROM table1;
  DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = 1;

  OPEN cur1;
  read_loop: LOOP
    FETCH FROM cur1 INTO newname, xid;
    IF done THEN LEAVE read_loop; END IF;
    SELECT newname;
  END LOOP;
  CLOSE cur1;
END;
```

See also [Section 27.8, “Restrictions on Stored Programs”](https://dev.mysql.com/doc/refman/8.0/en/stored-program-restrictions.html "27.8 Restrictions on Stored Programs").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/declare-local-variable.html "Previous: Local Variable DECLARE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/stored-program-variables.html "Up: Variables in Stored Programs") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html "Next: Flow Control Statements")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/local-variable-scope.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/local-variable-scope.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/local-variable-scope.html)

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