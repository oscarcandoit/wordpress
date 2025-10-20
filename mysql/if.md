---
url: https://dev.mysql.com/doc/refman/8.0/en/if.html
scraped_at: 2025-10-20T03:09:10.796Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/if.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/if.html "Hide Sidebar")

[Previous: CASE Statement](https://dev.mysql.com/doc/refman/8.0/en/case.html "Previous: CASE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Flow Control Statements](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html "Up: Flow Control Statements")[Next: ITERATE Statement](https://dev.mysql.com/doc/refman/8.0/en/iterate.html "Next: ITERATE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/if.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/if.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/if.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/if.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/if.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/if.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/if.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/if.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/if.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/if.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/if.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/if.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/if.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/if.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Compound Statement Syntax](https://dev.mysql.com/doc/refman/8.0/en/sql-compound-statements.html)  /
[Flow Control Statements](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html)  /

IF Statement


#### 15.6.5.2 IF Statement

```sql
IF search_condition THEN statement_list
    [ELSEIF search_condition THEN statement_list] ...
    [ELSE statement_list]
END IF
```

The [`IF`](https://dev.mysql.com/doc/refman/8.0/en/if.html "15.6.5.2 IF Statement") statement for stored
programs implements a basic conditional construct.

Note

There is also an [`IF()`](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html#function_if) _function_, which differs from the
[`IF`](https://dev.mysql.com/doc/refman/8.0/en/if.html "15.6.5.2 IF Statement") _statement_ described here. See
[Section 14.5, “Flow Control Functions”](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html "14.5 Flow Control Functions"). The
[`IF`](https://dev.mysql.com/doc/refman/8.0/en/if.html "15.6.5.2 IF Statement") statement can have
`THEN`, `ELSE`, and
`ELSEIF` clauses, and it is terminated with
`END IF`.

If a given _`search_condition`_ evaluates
to true, the corresponding `THEN` or
`ELSEIF` clause
_`statement_list`_ executes. If no
_`search_condition`_ matches, the
`ELSE` clause
_`statement_list`_ executes.


Each _`statement_list`_ consists of one
or more SQL statements; an empty
_`statement_list`_ is not permitted.


An `IF ... END IF` block, like all other
flow-control blocks used within stored programs, must be
terminated with a semicolon, as shown in this example:


```sql
DELIMITER //

CREATE FUNCTION SimpleCompare(n INT, m INT)
  RETURNS VARCHAR(20)

  BEGIN
    DECLARE s VARCHAR(20);

    IF n > m THEN SET s = '>';
    ELSEIF n = m THEN SET s = '=';
    ELSE SET s = '<';
    END IF;

    SET s = CONCAT(n, ' ', s, ' ', m);

    RETURN s;
  END //

DELIMITER ;
```

As with other flow-control constructs, `IF ... END
        IF` blocks may be nested within other flow-control
constructs, including other [`IF`](https://dev.mysql.com/doc/refman/8.0/en/if.html "15.6.5.2 IF Statement")
statements. Each [`IF`](https://dev.mysql.com/doc/refman/8.0/en/if.html "15.6.5.2 IF Statement") must be
terminated by its own `END IF` followed by a
semicolon. You can use indentation to make nested flow-control
blocks more easily readable by humans (although this is not
required by MySQL), as shown here:


```sql
DELIMITER //

CREATE FUNCTION VerboseCompare (n INT, m INT)
  RETURNS VARCHAR(50)

  BEGIN
    DECLARE s VARCHAR(50);

    IF n = m THEN SET s = 'equals';
    ELSE
      IF n > m THEN SET s = 'greater';
      ELSE SET s = 'less';
      END IF;

      SET s = CONCAT('is ', s, ' than');
    END IF;

    SET s = CONCAT(n, ' ', s, ' ', m, '.');

    RETURN s;
  END //

DELIMITER ;
```

In this example, the inner [`IF`](https://dev.mysql.com/doc/refman/8.0/en/if.html "15.6.5.2 IF Statement") is
evaluated only if `n` is not equal to
`m`.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/case.html "Previous: CASE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/flow-control-statements.html "Up: Flow Control Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/iterate.html "Next: ITERATE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/if.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/if.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/if.html)

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