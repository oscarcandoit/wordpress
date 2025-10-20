---
url: https://dev.mysql.com/doc/refman/8.0/en/show-grants.html
scraped_at: 2025-10-20T03:01:16.084Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "Hide Sidebar")

[Previous: SHOW FUNCTION STATUS Statement](https://dev.mysql.com/doc/refman/8.0/en/show-function-status.html "Previous: SHOW FUNCTION STATUS Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements")[Next: SHOW INDEX Statement](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "Next: SHOW INDEX Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/show-grants.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/show-grants.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/show-grants.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/show-grants.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/show-grants.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/show-grants.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/show-grants.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/show-grants.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)  /

SHOW GRANTS Statement


#### 15.7.7.21 SHOW GRANTS Statement

``` sql

SHOW GRANTS
    [FOR user_or_role\
        [USING role [, role] ...]]

user_or_role: {
    user (see Section 8.2.4, “Specifying Account Names”)
  | role (see Section 8.2.5, “Specifying Role Names”.
}
```

This statement displays the privileges and roles that are
assigned to a MySQL user account or role, in the form of
[`GRANT`](https://dev.mysql.com/doc/refman/8.0/en/grant.html "15.7.1.6 GRANT Statement") statements that must be
executed to duplicate the privilege and role assignments.

Note

To display nonprivilege information for MySQL accounts, use
the [`SHOW CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/show-create-user.html "15.7.7.12 SHOW CREATE USER Statement") statement.
See [Section 15.7.7.12, “SHOW CREATE USER Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-create-user.html "15.7.7.12 SHOW CREATE USER Statement").

[`SHOW GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") requires the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege for the
`mysql` system schema, except to display
privileges and roles for the current user.


To name the account or role for [`SHOW\\
        GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement"), use the same format as for the
[`GRANT`](https://dev.mysql.com/doc/refman/8.0/en/grant.html "15.7.1.6 GRANT Statement") statement (for example,
`'jeffrey'@'localhost'`):


``` sql

mysql> SHOW GRANTS FOR 'jeffrey'@'localhost';
+------------------------------------------------------------------+
| Grants for jeffrey@localhost                                     |
+------------------------------------------------------------------+
| GRANT USAGE ON *.* TO `jeffrey`@`localhost`                      |
| GRANT SELECT, INSERT, UPDATE ON `db1`.* TO `jeffrey`@`localhost` |
+------------------------------------------------------------------+
```

The host part, if omitted, defaults to `'%'`.
For additional information about specifying account and role
names, see [Section 8.2.4, “Specifying Account Names”](https://dev.mysql.com/doc/refman/8.0/en/account-names.html "8.2.4 Specifying Account Names"), and
[Section 8.2.5, “Specifying Role Names”](https://dev.mysql.com/doc/refman/8.0/en/role-names.html "8.2.5 Specifying Role Names").


To display the privileges granted to the current user (the
account you are using to connect to the server), you can use any
of the following statements:


``` sql

SHOW GRANTS;
SHOW GRANTS FOR CURRENT_USER;
SHOW GRANTS FOR CURRENT_USER();
```

If `SHOW GRANTS FOR CURRENT_USER` (or any
equivalent syntax) is used in definer context, such as within a
stored procedure that executes with definer rather than invoker
privileges, the grants displayed are those of the definer and
not the invoker.


In MySQL 8.0 compared to previous series,
[`SHOW GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") no longer displays
[`ALL PRIVILEGES`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_all) in
its global-privileges output because the meaning of
[`ALL PRIVILEGES`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_all) at
the global level varies depending on which dynamic privileges
are defined. Instead, [`SHOW GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement")
explicitly lists each granted global privilege:


``` sql

mysql> SHOW GRANTS FOR 'root'@'localhost';
+---------------------------------------------------------------------+
| Grants for root@localhost                                           |
+---------------------------------------------------------------------+
| GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, RELOAD,         |
| SHUTDOWN, PROCESS, FILE, REFERENCES, INDEX, ALTER, SHOW DATABASES,  |
| SUPER, CREATE TEMPORARY TABLES, LOCK TABLES, EXECUTE, REPLICATION   |
| SLAVE, REPLICATION CLIENT, CREATE VIEW, SHOW VIEW, CREATE ROUTINE,  |
| ALTER ROUTINE, CREATE USER, EVENT, TRIGGER, CREATE TABLESPACE,      |
| CREATE ROLE, DROP ROLE ON *.* TO `root`@`localhost` WITH GRANT      |
| OPTION                                                              |
| GRANT PROXY ON ''@'' TO `root`@`localhost` WITH GRANT OPTION        |
+---------------------------------------------------------------------+
```

Applications that process [`SHOW\\
        GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") output should be adjusted accordingly.


At the global level, [`GRANT OPTION`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_grant-option)
applies to all granted static global privileges if granted for
any of them, but applies individually to granted dynamic
privileges. [`SHOW GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") displays
global privileges this way:

- One line listing all granted static privileges, if there are
any, including `WITH GRANT OPTION` if
appropriate.


- One line listing all granted dynamic privileges for which
[`GRANT OPTION`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_grant-option) is granted, if
there are any, including `WITH GRANT
              OPTION`.


- One line listing all granted dynamic privileges for which
[`GRANT OPTION`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_grant-option) is not granted,
if there are any, without `WITH GRANT
              OPTION`.


With the optional `USING` clause,
[`SHOW GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") enables you to
examine the privileges associated with roles for the user. Each
role named in the `USING` clause must be
granted to the user.


Suppose that user `u1` is assigned roles
`r1` and `r2`, as follows:


``` sql

CREATE ROLE 'r1', 'r2';
GRANT SELECT ON db1.* TO 'r1';
GRANT INSERT, UPDATE, DELETE ON db1.* TO 'r2';
CREATE USER 'u1'@'localhost' IDENTIFIED BY 'u1pass';
GRANT 'r1', 'r2' TO 'u1'@'localhost';
```

[`SHOW GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") without
`USING` shows the granted roles:


``` sql

mysql> SHOW GRANTS FOR 'u1'@'localhost';
+---------------------------------------------+
| Grants for u1@localhost                     |
+---------------------------------------------+
| GRANT USAGE ON *.* TO `u1`@`localhost`      |
| GRANT `r1`@`%`,`r2`@`%` TO `u1`@`localhost` |
+---------------------------------------------+
```

Adding a `USING` clause causes the statement to
also display the privileges associated with each role named in
the clause:


``` sql

mysql> SHOW GRANTS FOR 'u1'@'localhost' USING 'r1';
+---------------------------------------------+
| Grants for u1@localhost                     |
+---------------------------------------------+
| GRANT USAGE ON *.* TO `u1`@`localhost`      |
| GRANT SELECT ON `db1`.* TO `u1`@`localhost` |
| GRANT `r1`@`%`,`r2`@`%` TO `u1`@`localhost` |
+---------------------------------------------+
mysql> SHOW GRANTS FOR 'u1'@'localhost' USING 'r2';
+-------------------------------------------------------------+
| Grants for u1@localhost                                     |
+-------------------------------------------------------------+
| GRANT USAGE ON *.* TO `u1`@`localhost`                      |
| GRANT INSERT, UPDATE, DELETE ON `db1`.* TO `u1`@`localhost` |
| GRANT `r1`@`%`,`r2`@`%` TO `u1`@`localhost`                 |
+-------------------------------------------------------------+
mysql> SHOW GRANTS FOR 'u1'@'localhost' USING 'r1', 'r2';
+---------------------------------------------------------------------+
| Grants for u1@localhost                                             |
+---------------------------------------------------------------------+
| GRANT USAGE ON *.* TO `u1`@`localhost`                              |
| GRANT SELECT, INSERT, UPDATE, DELETE ON `db1`.* TO `u1`@`localhost` |
| GRANT `r1`@`%`,`r2`@`%` TO `u1`@`localhost`                         |
+---------------------------------------------------------------------+
```

Note

A privilege granted to an account is always in effect, but a
role is not. The active roles for an account can differ across
and within sessions, depending on the value of the
[`activate_all_roles_on_login`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_activate_all_roles_on_login)
system variable, the account default roles, and whether
[`SET ROLE`](https://dev.mysql.com/doc/refman/8.0/en/set-role.html "15.7.1.11 SET ROLE Statement") has been executed
within a session.

MySQL 8.0.16 and higher supports partial revokes of global
privileges, such that a global privilege can be restricted from
applying to particular schemas (see
[Section 8.2.12, “Privilege Restriction Using Partial Revokes”](https://dev.mysql.com/doc/refman/8.0/en/partial-revokes.html "8.2.12 Privilege Restriction Using Partial Revokes")). To indicate which global
schema privileges have been revoked for particular schemas,
`SHOW GRANTS` output includes
`REVOKE` statements:


``` sql

mysql> SET PERSIST partial_revokes = ON;
mysql> CREATE USER u1;
mysql> GRANT SELECT, INSERT, DELETE ON *.* TO u1;
mysql> REVOKE SELECT, INSERT ON mysql.* FROM u1;
mysql> REVOKE DELETE ON world.* FROM u1;
mysql> SHOW GRANTS FOR u1;
+--------------------------------------------------+
| Grants for u1@%                                  |
+--------------------------------------------------+
| GRANT SELECT, INSERT, DELETE ON *.* TO `u1`@`%`  |
| REVOKE SELECT, INSERT ON `mysql`.* FROM `u1`@`%` |
| REVOKE DELETE ON `world`.* FROM `u1`@`%`         |
+--------------------------------------------------+
```

[`SHOW GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") does not display
privileges that are available to the named account but are
granted to a different account. For example, if an anonymous
account exists, the named account might be able to use its
privileges, but [`SHOW GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") does
not display them.


[`SHOW GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") displays mandatory
roles named in the
[`mandatory_roles`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_mandatory_roles) system variable
value as follows:

- [`SHOW GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") without a
`FOR` clause displays privileges for the
current user, and includes mandatory roles.


- [`SHOW GRANTS FOR\\
              user`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") displays
privileges for the named user, and does not include
mandatory roles.


This behavior is for the benefit of applications that use the
output of [`SHOW\\
        GRANTS FOR user`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") to
determine which privileges are granted explicitly to the named
user. Were that output to include mandatory roles, it would be
difficult to distinguish roles granted explicitly to the user
from mandatory roles.


For the current user, applications can determine privileges with
or without mandatory roles by using [`SHOW\\
        GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement") or
[`SHOW GRANTS FOR\\
        CURRENT_USER`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement"), respectively.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/show-function-status.html "Previous: SHOW FUNCTION STATUS Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "Next: SHOW INDEX Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html)

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