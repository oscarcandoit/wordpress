---
url: https://dev.mysql.com/doc/refman/8.0/en/revoke.html
scraped_at: 2025-10-20T03:01:04.900Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/revoke.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/revoke.html "Hide Sidebar")

[Previous: RENAME USER Statement](https://dev.mysql.com/doc/refman/8.0/en/rename-user.html "Previous: RENAME USER Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Account Management Statements](https://dev.mysql.com/doc/refman/8.0/en/account-management-statements.html "Up: Account Management Statements")[Next: SET DEFAULT ROLE Statement](https://dev.mysql.com/doc/refman/8.0/en/set-default-role.html "Next: SET DEFAULT ROLE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/revoke.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/revoke.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/revoke.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/revoke.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/revoke.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/revoke.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/revoke.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/revoke.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/revoke.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/revoke.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/revoke.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/revoke.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/revoke.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/revoke.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[Account Management Statements](https://dev.mysql.com/doc/refman/8.0/en/account-management-statements.html)  /

REVOKE Statement


#### 15.7.1.8 REVOKE Statement

```sql
REVOKE [IF EXISTS]
    priv_type [(column_list)]
      [, priv_type [(column_list)]] ...
    ON [object_type] priv_level
    FROM user_or_role [, user_or_role] ...
    [IGNORE UNKNOWN USER]

REVOKE [IF EXISTS] ALL [PRIVILEGES], GRANT OPTION
    FROM user_or_role [, user_or_role] ...
    [IGNORE UNKNOWN USER]

REVOKE [IF EXISTS] PROXY ON user_or_role
    FROM user_or_role [, user_or_role] ...
    [IGNORE UNKNOWN USER]

REVOKE [IF EXISTS] role [, role ] ...
    FROM user_or_role [, user_or_role ] ...
    [IGNORE UNKNOWN USER]

user_or_role: {
    user (see Section 8.2.4, “Specifying Account Names”)
  | role (see Section 8.2.5, “Specifying Role Names”
}
```

The [`REVOKE`](https://dev.mysql.com/doc/refman/8.0/en/revoke.html "15.7.1.8 REVOKE Statement") statement enables
system administrators to revoke privileges and roles, which can
be revoked from user accounts and roles.


For details on the levels at which privileges exist, the
permissible _`priv_type`_,
_`priv_level`_, and
_`object_type`_ values, and the syntax
for specifying users and passwords, see [Section 15.7.1.6, “GRANT Statement”](https://dev.mysql.com/doc/refman/8.0/en/grant.html "15.7.1.6 GRANT Statement").


For information about roles, see [Section 8.2.10, “Using Roles”](https://dev.mysql.com/doc/refman/8.0/en/roles.html "8.2.10 Using Roles").


When the [`read_only`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_read_only) system
variable is enabled, [`REVOKE`](https://dev.mysql.com/doc/refman/8.0/en/revoke.html "15.7.1.8 REVOKE Statement")
requires the [`CONNECTION_ADMIN`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_connection-admin) or
privilege (or the deprecated
[`SUPER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_super) privilege), in addition to
any other required privileges described in the following
discussion.


Beginning with MySQL 8.0.30, all the forms shown for
`REVOKE` support an `IF
        EXISTS` option as well as an `IGNORE UNKNOWN
        USER` option. With neither of these modifications,
[`REVOKE`](https://dev.mysql.com/doc/refman/8.0/en/revoke.html "15.7.1.8 REVOKE Statement") either succeeds for all
named users and roles, or rolls back and has no effect if any
error occurs; the statement is written to the binary log only if
it succeeds for all named users and roles. The precise effects
of `IF EXISTS` and `IGNORE UNKNOWN
        USER` are discussed later in this section.


Each account name uses the format described in
[Section 8.2.4, “Specifying Account Names”](https://dev.mysql.com/doc/refman/8.0/en/account-names.html "8.2.4 Specifying Account Names"). Each role name uses the format
described in [Section 8.2.5, “Specifying Role Names”](https://dev.mysql.com/doc/refman/8.0/en/role-names.html "8.2.5 Specifying Role Names"). For example:


```sql
REVOKE INSERT ON *.* FROM 'jeffrey'@'localhost';
REVOKE 'role1', 'role2' FROM 'user1'@'localhost', 'user2'@'localhost';
REVOKE SELECT ON world.* FROM 'role3';
```

The host name part of the account or role name, if omitted,
defaults to `'%'`.


To use the first [`REVOKE`](https://dev.mysql.com/doc/refman/8.0/en/revoke.html "15.7.1.8 REVOKE Statement") syntax,
you must have the [`GRANT OPTION`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_grant-option)
privilege, and you must have the privileges that you are
revoking.


To revoke all privileges from a user, use one of the following
statements; either of these statements drops all global,
database, table, column, and routine privileges for the named
users or roles:


```sql
REVOKE ALL PRIVILEGES, GRANT OPTION
  FROM user_or_role [, user_or_role] ...

REVOKE ALL ON *.*
  FROM user_or_role [, user_or_role] ...
```

Neither of the two statements just shown revokes any roles.


To use these [`REVOKE`](https://dev.mysql.com/doc/refman/8.0/en/revoke.html "15.7.1.8 REVOKE Statement") statements,
you must have the global [`CREATE\\
        USER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_create-user) privilege, or the
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_update) privilege for the
`mysql` system schema.


The syntax for which the [`REVOKE`](https://dev.mysql.com/doc/refman/8.0/en/revoke.html "15.7.1.8 REVOKE Statement")
keyword is followed by one or more role names takes a
`FROM` clause indicating one or more users or
roles from which to revoke the roles.


The `IF EXISTS` and `IGNORE UNKNOWN
        USER` options (MySQL 8.0.30 and later) have the effects
listed here:

- `IF EXISTS` means that, if the target user
or role exists but no such privilege or role is found
assigned to the target for any reason, a warning is raised,
instead of an error; if no privilege or role named by the
statement is assigned to the target, the statement has no
(other) effect. Otherwise, `REVOKE`
executes normally; if the user does not exist, the statement
raises an error.


_Example_: Given table
`t1` in database `test`,
we execute the following statements, with the results shown.



```sql
mysql> CREATE USER jerry@localhost;
Query OK, 0 rows affected (0.01 sec)

mysql> REVOKE SELECT ON test.t1 FROM jerry@localhost;
ERROR 1147 (42000): There is no such grant defined for user 'jerry' on host
'localhost' on table 't1'
mysql> REVOKE IF EXISTS SELECT ON test.t1 FROM jerry@localhost;
Query OK, 0 rows affected, 1 warning (0.00 sec)

mysql> SHOW WARNINGS\G
*************************** 1. row ***************************
    Level: Warning
     Code: 1147
Message: There is no such grant defined for user 'jerry' on host 'localhost' on
table 't1'
1 row in set (0.00 sec)
```


`IF EXISTS` causes an error to be demoted
to a warning even if the privilege or role named does not
exist, or the statement attempts to assign it at the wrong
level.


- If the `REVOKE` statement includes
`IGNORE UNKNOWN USER`, the statement raises
a warning for any target user or role named in the statement
but not found; if no target named by the statement exists,
`REVOKE` succeeds but has no actual effect.
Otherwise, the statement executes as usual, and attempting
to revoke a privilege not assigned to the target for
whatever reason raises an error, as expected.


_Example_ (continuing from the previous
example):



```sql
mysql> DROP USER IF EXISTS jerry@localhost;
Query OK, 0 rows affected (0.01 sec)

mysql> REVOKE SELECT ON test.t1 FROM jerry@localhost;
ERROR 1147 (42000): There is no such grant defined for user 'jerry' on host
'localhost' on table 't1'
mysql> REVOKE SELECT ON test.t1 FROM jerry@localhost IGNORE UNKNOWN USER;
Query OK, 0 rows affected, 1 warning (0.01 sec)

mysql> SHOW WARNINGS\G
*************************** 1. row ***************************
    Level: Warning
     Code: 3162
Message: Authorization ID jerry does not exist.
1 row in set (0.00 sec)
```

- The combination of `IF EXISTS` and
`IGNORE UNKNOWN USER` means that
`REVOKE` never raises an error for an
unknown target user or role or for an unassigned or
unavailable privilege, and the statement as whole in such
cases succeeds; roles or privileges are removed from
existing target users or roles whenever possible, and any
revocation which is not possible raises a warning and
executes as a `NOOP`.


_Example_ (again continuing from example
in the previous item):



```sql
# No such user, no such role
mysql> DROP ROLE IF EXISTS Bogus;
Query OK, 0 rows affected, 1 warning (0.02 sec)

mysql> SHOW WARNINGS;
+-------+------+----------------------------------------------+
| Level | Code | Message                                      |
+-------+------+----------------------------------------------+
| Note  | 3162 | Authorization ID 'Bogus'@'%' does not exist. |
+-------+------+----------------------------------------------+
1 row in set (0.00 sec)

# This statement attempts to revoke a nonexistent role from a nonexistent user
mysql> REVOKE Bogus ON test FROM jerry@localhost;
ERROR 3619 (HY000): Illegal privilege level specified for test

# The same, with IF EXISTS
mysql> REVOKE IF EXISTS Bogus ON test FROM jerry@localhost;
ERROR 1147 (42000): There is no such grant defined for user 'jerry' on host
'localhost' on table 'test'

# The same, with IGNORE UNKNOWN USER
mysql> REVOKE Bogus ON test FROM jerry@localhost IGNORE UNKNOWN USER;
ERROR 3619 (HY000): Illegal privilege level specified for test

# The same, with both options
mysql> REVOKE IF EXISTS Bogus ON test FROM jerry@localhost IGNORE UNKNOWN USER;
Query OK, 0 rows affected, 2 warnings (0.01 sec)

mysql> SHOW WARNINGS;
+---------+------+--------------------------------------------+
| Level   | Code | Message                                    |
+---------+------+--------------------------------------------+
| Warning | 3619 | Illegal privilege level specified for test |
| Warning | 3162 | Authorization ID jerry does not exist.     |
+---------+------+--------------------------------------------+
2 rows in set (0.00 sec)
```


Roles named in the
[`mandatory_roles`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_mandatory_roles) system variable
value cannot be revoked. When `IF EXISTS` and
`IGNORE UNKNOWN USER` are used together in a
statement that tries to remove a mandatory privilege, the error
normally raised by attempting to do this is demoted to a
warning; the statement executes successfully, but does not make
any changes.


A revoked role immediately affects any user account from which
it was revoked, such that within any current session for the
account, its privileges are adjusted for the next statement
executed.


Revoking a role revokes the role itself, not the privileges that
it represents. Suppose that an account is granted a role that
includes a given privilege, and is also granted the privilege
explicitly or another role that includes the privilege. In this
case, the account still possesses that privilege if the first
role is revoked. For example, if an account is granted two roles
that each include [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select), the
account still can select after either role is revoked.


`REVOKE ALL ON *.*` (at the global level)
revokes all granted static global privileges and all granted
dynamic privileges.


A revoked privilege that is granted but not known to the server
is revoked with a warning. This situation can occur for dynamic
privileges. For example, a dynamic privilege can be granted
while the component that registers it is installed, but if that
component is subsequently uninstalled, the privilege becomes
unregistered, although accounts that possess the privilege still
possess it and it can be revoked from them.


[`REVOKE`](https://dev.mysql.com/doc/refman/8.0/en/revoke.html "15.7.1.8 REVOKE Statement") removes privileges, but
does not remove rows from the `mysql.user`
system table. To remove a user account entirely, use
[`DROP USER`](https://dev.mysql.com/doc/refman/8.0/en/drop-user.html "15.7.1.5 DROP USER Statement"). See
[Section 15.7.1.5, “DROP USER Statement”](https://dev.mysql.com/doc/refman/8.0/en/drop-user.html "15.7.1.5 DROP USER Statement").


If the grant tables hold privilege rows that contain mixed-case
database or table names and the
[`lower_case_table_names`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_lower_case_table_names) system
variable is set to a nonzero value,
[`REVOKE`](https://dev.mysql.com/doc/refman/8.0/en/revoke.html "15.7.1.8 REVOKE Statement") cannot be used to revoke
these privileges. It is necessary in such cases to manipulate
the grant tables directly. ( [`GRANT`](https://dev.mysql.com/doc/refman/8.0/en/grant.html "15.7.1.6 GRANT Statement")
does not create such rows when
[`lower_case_table_names`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_lower_case_table_names) is set,
but such rows might have been created prior to setting the
variable. The
[`lower_case_table_names`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_lower_case_table_names) setting
can only be configured when initializing the server.)


When successfully executed from the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client")
program, [`REVOKE`](https://dev.mysql.com/doc/refman/8.0/en/revoke.html "15.7.1.8 REVOKE Statement") responds with
`Query OK, 0 rows affected`. To determine what
privileges remain after the operation, use
[`SHOW GRANTS`](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement"). See
[Section 15.7.7.21, “SHOW GRANTS Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html "15.7.7.21 SHOW GRANTS Statement").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/rename-user.html "Previous: RENAME USER Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/account-management-statements.html "Up: Account Management Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/set-default-role.html "Next: SET DEFAULT ROLE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/revoke.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/revoke.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/revoke.html)

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