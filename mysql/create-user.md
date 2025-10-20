---
url: https://dev.mysql.com/doc/refman/8.0/en/create-user.html
scraped_at: 2025-10-20T03:00:56.676Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/create-user.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "Hide Sidebar")

[Previous: CREATE ROLE Statement](https://dev.mysql.com/doc/refman/8.0/en/create-role.html "Previous: CREATE ROLE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Account Management Statements](https://dev.mysql.com/doc/refman/8.0/en/account-management-statements.html "Up: Account Management Statements")[Next: DROP ROLE Statement](https://dev.mysql.com/doc/refman/8.0/en/drop-role.html "Next: DROP ROLE Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/create-user.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-user.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-user.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/create-user.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/create-user.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/create-user.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/create-user.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/create-user.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/create-user.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/create-user.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/create-user.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/create-user.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/create-user.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[Account Management Statements](https://dev.mysql.com/doc/refman/8.0/en/account-management-statements.html)  /

CREATE USER Statement


#### 15.7.1.3 CREATE USER Statement

``` sql

CREATE USER [IF NOT EXISTS]
    user [auth_option] [, user [auth_option]] ...
    DEFAULT ROLE role [, role ] ...
    [REQUIRE {NONE | tls_option [[AND] tls_option] ...}]
    [WITH resource_option [resource_option] ...]
    [password_option | lock_option] ...
    [COMMENT 'comment_string' | ATTRIBUTE 'json_object']

user:
    (see Section 8.2.4, “Specifying Account Names”)

auth_option: {
    IDENTIFIED BY 'auth_string' [AND 2fa_auth_option]
  | IDENTIFIED BY RANDOM PASSWORD [AND 2fa_auth_option]
  | IDENTIFIED WITH auth_plugin [AND 2fa_auth_option]
  | IDENTIFIED WITH auth_plugin BY 'auth_string' [AND 2fa_auth_option]
  | IDENTIFIED WITH auth_plugin BY RANDOM PASSWORD [AND 2fa_auth_option]
  | IDENTIFIED WITH auth_plugin AS 'auth_string' [AND 2fa_auth_option]
  | IDENTIFIED WITH auth_plugin [initial_auth_option]
}

2fa_auth_option: {
    IDENTIFIED BY 'auth_string' [AND 3fa_auth_option]
  | IDENTIFIED BY RANDOM PASSWORD [AND 3fa_auth_option]
  | IDENTIFIED WITH auth_plugin [AND 3fa_auth_option]
  | IDENTIFIED WITH auth_plugin BY 'auth_string' [AND 3fa_auth_option]
  | IDENTIFIED WITH auth_plugin BY RANDOM PASSWORD [AND 3fa_auth_option]
  | IDENTIFIED WITH auth_plugin AS 'auth_string' [AND 3fa_auth_option]
}

3fa_auth_option: {
    IDENTIFIED BY 'auth_string'
  | IDENTIFIED BY RANDOM PASSWORD
  | IDENTIFIED WITH auth_plugin
  | IDENTIFIED WITH auth_plugin BY 'auth_string'
  | IDENTIFIED WITH auth_plugin BY RANDOM PASSWORD
  | IDENTIFIED WITH auth_plugin AS 'auth_string'
}

initial_auth_option: {
    INITIAL AUTHENTICATION IDENTIFIED BY {RANDOM PASSWORD | 'auth_string'}
  | INITIAL AUTHENTICATION IDENTIFIED WITH auth_plugin AS 'auth_string'
}

tls_option: {
   SSL
 | X509
 | CIPHER 'cipher'
 | ISSUER 'issuer'
 | SUBJECT 'subject'
}

resource_option: {
    MAX_QUERIES_PER_HOUR count
  | MAX_UPDATES_PER_HOUR count
  | MAX_CONNECTIONS_PER_HOUR count
  | MAX_USER_CONNECTIONS count
}

password_option: {
    PASSWORD EXPIRE [DEFAULT | NEVER | INTERVAL N DAY]
  | PASSWORD HISTORY {DEFAULT | N}
  | PASSWORD REUSE INTERVAL {DEFAULT | N DAY}
  | PASSWORD REQUIRE CURRENT [DEFAULT | OPTIONAL]
  | FAILED_LOGIN_ATTEMPTS N
  | PASSWORD_LOCK_TIME {N | UNBOUNDED}
}

lock_option: {
    ACCOUNT LOCK
  | ACCOUNT UNLOCK
}
```

The [`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") statement creates
new MySQL accounts. It enables authentication, role, SSL/TLS,
resource-limit, password-management, comment, and attribute
properties to be established for new accounts. It also controls
whether accounts are initially locked or unlocked.


To use [`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement"), you must have
the global [`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_create-user) privilege,
or the [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_insert) privilege for the
`mysql` system schema. When the
[`read_only`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_read_only) system variable is
enabled, [`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") additionally
requires the [`CONNECTION_ADMIN`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_connection-admin)
privilege (or the deprecated
[`SUPER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_super) privilege).


As of MySQL 8.0.27, these additional privilege considerations
apply:

- The [`authentication_policy`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_authentication_policy)
system variable places certain constraints on how the
authentication-related clauses of
[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") statements may be
used; for details, see the description of that variable.
These constraints do not apply if you have the
[`AUTHENTICATION_POLICY_ADMIN`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_authentication-policy-admin)
privilege.


- To create an account that uses passwordless authentication,
you must have the
[`PASSWORDLESS_USER_ADMIN`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_passwordless-user-admin)
privilege.


As of MySQL 8.0.22, [`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement")
fails with an error if any account to be created is named as the
`DEFINER` attribute for any stored object.
(That is, the statement fails if creating an account would cause
the account to adopt a currently orphaned stored object.) To
perform the operation anyway, you must have the
[`SET_USER_ID`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_set-user-id) privilege; in this
case, the statement succeeds with a warning rather than failing
with an error. Without
[`SET_USER_ID`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_set-user-id), to perform the
user-creation operation, drop the orphan objects, create the
account and grant its privileges, and then re-create the dropped
objects. For additional information, including how to identify
which objects name a given account as the
`DEFINER` attribute, see
[Orphan Stored Objects](https://dev.mysql.com/doc/refman/8.0/en/stored-objects-security.html#stored-objects-security-orphan-objects "Orphan Stored Objects").


[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") either succeeds for
all named users or rolls back and has no effect if any error
occurs. By default, an error occurs if you try to create a user
that already exists. If the `IF NOT EXISTS`
clause is given, the statement produces a warning for each named
user that already exists, rather than an error.

Important

Under some circumstances, [`CREATE\\
          USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") may be recorded in server logs or on the client
side in a history file such as
`~/.mysql_history`, which means that
cleartext passwords may be read by anyone having read access
to that information. For information about the conditions
under which this occurs for the server logs and how to control
it, see [Section 8.1.2.3, “Passwords and Logging”](https://dev.mysql.com/doc/refman/8.0/en/password-logging.html "8.1.2.3 Passwords and Logging"). For similar
information about client-side logging, see
[Section 6.5.1.3, “mysql Client Logging”](https://dev.mysql.com/doc/refman/8.0/en/mysql-logging.html "6.5.1.3 mysql Client Logging").

There are several aspects to the [`CREATE\\
        USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") statement, described under the following topics:

- [CREATE USER Overview](https://dev.mysql.com/doc/refman/8.0/en/create-user.html#create-user-overview "CREATE USER Overview")

- [CREATE USER Authentication Options](https://dev.mysql.com/doc/refman/8.0/en/create-user.html#create-user-authentication "CREATE USER Authentication Options")

- [CREATE USER Multifactor Authentication Options](https://dev.mysql.com/doc/refman/8.0/en/create-user.html#create-user-multifactor-authentication "CREATE USER Multifactor Authentication Options")

- [CREATE USER Role Options](https://dev.mysql.com/doc/refman/8.0/en/create-user.html#create-user-role "CREATE USER Role Options")

- [CREATE USER SSL/TLS Options](https://dev.mysql.com/doc/refman/8.0/en/create-user.html#create-user-tls "CREATE USER SSL/TLS Options")

- [CREATE USER Resource-Limit Options](https://dev.mysql.com/doc/refman/8.0/en/create-user.html#create-user-resource-limits "CREATE USER Resource-Limit Options")

- [CREATE USER Password-Management Options](https://dev.mysql.com/doc/refman/8.0/en/create-user.html#create-user-password-management "CREATE USER Password-Management Options")

- [CREATE USER Comment and Attribute Options](https://dev.mysql.com/doc/refman/8.0/en/create-user.html#create-user-comments-attributes "CREATE USER Comment and Attribute Options")

- [CREATE USER Account-Locking Options](https://dev.mysql.com/doc/refman/8.0/en/create-user.html#create-user-account-locking "CREATE USER Account-Locking Options")

- [CREATE USER Binary Logging](https://dev.mysql.com/doc/refman/8.0/en/create-user.html#create-user-binary-logging "CREATE USER Binary Logging")


##### CREATE USER Overview

For each account, [`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement")
creates a new row in the `mysql.user` system
table. The account row reflects the properties specified in
the statement. Unspecified properties are set to their default
values:

- Authentication: The default authentication plugin
(determined as described in
[The Default Authentication Plugin](https://dev.mysql.com/doc/refman/8.0/en/pluggable-authentication.html#pluggable-authentication-default-plugin "The Default Authentication Plugin")),
and empty credentials


- Default role: `NONE`

- SSL/TLS: `NONE`

- Resource limits: Unlimited


- Password management: `PASSWORD EXPIRE DEFAULT
                PASSWORD HISTORY DEFAULT PASSWORD REUSE INTERVAL DEFAULT
                PASSWORD REQUIRE CURRENT DEFAULT`; failed-login
tracking and temporary account locking are disabled


- Account locking: `ACCOUNT UNLOCK`


An account when first created has no privileges and the
default role `NONE`. To assign privileges or
roles to this account, use one or more
[`GRANT`](https://dev.mysql.com/doc/refman/8.0/en/grant.html "15.7.1.6 GRANT Statement") statements.


Each account name uses the format described in
[Section 8.2.4, “Specifying Account Names”](https://dev.mysql.com/doc/refman/8.0/en/account-names.html "8.2.4 Specifying Account Names"). For example:


``` sql

CREATE USER 'jeffrey'@'localhost' IDENTIFIED BY 'password';
```

The host name part of the account name, if omitted, defaults
to `'%'`. You should be aware that, while
MySQL 8.0 treats grants made to such a user as
though they had been granted to
`'user'@'localhost'`,
this behavior is deprecated as of MySQL 8.0.35, and thus
subject to removal in a future version of MySQL.


Each _`user`_ value naming an account
may be followed by an optional
_`auth_option`_ value that indicates
how the account authenticates. These values enable account
authentication plugins and credentials (for example, a
password) to be specified. Each
_`auth_option`_ value applies
_only_ to the account named immediately
preceding it.


Following the _`user`_ specifications,
the statement may include options for SSL/TLS, resource-limit,
password-management, and locking properties. All such options
are _global_ to the statement and apply to
_all_ accounts named in the statement.


Example: Create an account that uses the default
authentication plugin and the given password. Mark the
password expired so that the user must choose a new one at the
first connection to the server:


``` sql

CREATE USER 'jeffrey'@'localhost'
  IDENTIFIED BY 'new_password' PASSWORD EXPIRE;
```

Example: Create an account that uses the
`caching_sha2_password` authentication plugin
and the given password. Require that a new password be chosen
every 180 days, and enable failed-login tracking, such that
three consecutive incorrect passwords cause temporary account
locking for two days:


``` sql

CREATE USER 'jeffrey'@'localhost'
  IDENTIFIED WITH caching_sha2_password BY 'new_password'
  PASSWORD EXPIRE INTERVAL 180 DAY
  FAILED_LOGIN_ATTEMPTS 3 PASSWORD_LOCK_TIME 2;
```

Example: Create multiple accounts, specifying some per-account
properties and some global properties:


``` sql

CREATE USER
  'jeffrey'@'localhost' IDENTIFIED WITH mysql_native_password
                                   BY 'new_password1',
  'jeanne'@'localhost' IDENTIFIED WITH caching_sha2_password
                                  BY 'new_password2'
  REQUIRE X509 WITH MAX_QUERIES_PER_HOUR 60
  PASSWORD HISTORY 5
  ACCOUNT LOCK;
```

Each _`auth_option`_ value
( `IDENTIFIED WITH ... BY` in this case)
applies only to the account named immediately preceding it, so
each account uses the immediately following authentication
plugin and password.


The remaining properties apply globally to all accounts named
in the statement, so for both accounts:

- Connections must be made using a valid X.509 certificate.


- Up to 60 queries per hour are permitted.


- Password changes cannot reuse any of the five most recent
passwords.


- The account is locked initially, so effectively it is a
placeholder and cannot be used until an administrator
unlocks it.


##### CREATE USER Authentication Options

An account name may be followed by an
_`auth_option`_ authentication option
that specifies the account authentication plugin, credentials,
or both.

Note

Prior to MySQL 8.0.27,
_`auth_option`_ defines the sole
method by which an account authenticates. That is, all
accounts use one-factor/single-factor authentication
(1FA/SFA). MySQL 8.0.27 and higher supports multifactor
authentication (MFA), such that accounts can have up to
three authentication methods. That is, accounts can use
two-factor authentication (2FA) or three-factor
authentication (3FA). The syntax and semantics of
_`auth_option`_ remain unchanged, but
_`auth_option`_ may be followed by
specifications for additional authentication methods. This
section describes _`auth_option`_.
For details about the optional MFA-related following
clauses, see
[CREATE USER Multifactor Authentication Options](https://dev.mysql.com/doc/refman/8.0/en/create-user.html#create-user-multifactor-authentication "CREATE USER Multifactor Authentication Options").

Note

Clauses for random password generation apply only to
accounts that use an authentication plugin that stores
credentials internally to MySQL. For accounts that use a
plugin that performs authentication against a credentials
system that is external to MySQL, password management must
be handled externally against that system as well. For more
information about internal credentials storage, see
[Section 8.2.15, “Password Management”](https://dev.mysql.com/doc/refman/8.0/en/password-management.html "8.2.15 Password Management").

- _`auth_plugin`_ names an
authentication plugin. The plugin name can be a quoted
string literal or an unquoted name. Plugin names are
stored in the `plugin` column of the
`mysql.user` system table.



For _`auth_option`_ syntax that
does not specify an authentication plugin, the server
assigns the default plugin, determined as described in
[The Default Authentication Plugin](https://dev.mysql.com/doc/refman/8.0/en/pluggable-authentication.html#pluggable-authentication-default-plugin "The Default Authentication Plugin").
For descriptions of each plugin, see
[Section 8.4.1, “Authentication Plugins”](https://dev.mysql.com/doc/refman/8.0/en/authentication-plugins.html "8.4.1 Authentication Plugins").


- Credentials that are stored internally are stored in the
`mysql.user` system table. An
`'auth_string'`
value or `RANDOM PASSWORD` specifies
account credentials, either as a cleartext (unencrypted)
string or hashed in the format expected by the
authentication plugin associated with the account,
respectively:




- For syntax that uses `BY
                    'auth_string'`,
the string is cleartext and is passed to the
authentication plugin for possible hashing. The result
returned by the plugin is stored in the
`mysql.user` table. A plugin may use
the value as specified, in which case no hashing
occurs.


- For syntax that uses `BY RANDOM
                    PASSWORD`, MySQL generates a random password
and as cleartext and passes it to the authentication
plugin for possible hashing. The result returned by
the plugin is stored in the
`mysql.user` table. A plugin may use
the value as specified, in which case no hashing
occurs.



Randomly generated passwords are available as of MySQL
8.0.18 and have the characteristics described in
[Random Password Generation](https://dev.mysql.com/doc/refman/8.0/en/password-management.html#random-password-generation "Random Password Generation").


- For syntax that uses `AS
                    'auth_string'`,
the string is assumed to be already in the format the
authentication plugin requires, and is stored as is in
the `mysql.user` table. If a plugin
requires a hashed value, the value must be already
hashed in a format appropriate for the plugin;
otherwise, the value cannot be used by the plugin and
correct authentication of client connections does not
occur.



As of MySQL 8.0.17, a hashed string can be either a
string literal or a hexadecimal value. The latter
corresponds to the type of value displayed by
[`SHOW CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/show-create-user.html "15.7.7.12 SHOW CREATE USER Statement") for
password hashes containing unprintable characters when
the
[`print_identified_with_as_hex`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_print_identified_with_as_hex)
system variable is enabled.





Important





Although we show
`'auth_string'`
with quotation marks, a hexadecimal value used for
this purpose must _not_ be
quoted.

- If an authentication plugin performs no hashing of the
authentication string, the `BY
                    'auth_string'` and
`AS
                    'auth_string'`
clauses have the same effect: The authentication
string is stored as is in the
`mysql.user` system table.


[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") permits these
_`auth_option`_ syntaxes:

- `IDENTIFIED BY
                'auth_string'`


Sets the account authentication plugin to the default
plugin, passes the cleartext
`'auth_string'`
value to the plugin for possible hashing, and stores the
result in the account row in the
`mysql.user` system table.


- `IDENTIFIED BY RANDOM PASSWORD`


Sets the account authentication plugin to the default
plugin, generates a random password, passes the cleartext
password value to the plugin for possible hashing, and
stores the result in the account row in the
`mysql.user` system table. The statement
also returns the cleartext password in a result set to
make it available to the user or application executing the
statement. For details about the result set and
characteristics of randomly generated passwords, see
[Random Password Generation](https://dev.mysql.com/doc/refman/8.0/en/password-management.html#random-password-generation "Random Password Generation").


- `IDENTIFIED WITH
                auth_plugin`


Sets the account authentication plugin to
_`auth_plugin`_, clears the
credentials to the empty string, and stores the result in
the account row in the `mysql.user`
system table.


- `IDENTIFIED WITH
                auth_plugin BY
                'auth_string'`


Sets the account authentication plugin to
_`auth_plugin`_, passes the
cleartext
`'auth_string'`
value to the plugin for possible hashing, and stores the
result in the account row in the
`mysql.user` system table.


- `IDENTIFIED WITH
                auth_plugin BY RANDOM
                PASSWORD`


Sets the account authentication plugin to
_`auth_plugin`_, generates a random
password, passes the cleartext password value to the
plugin for possible hashing, and stores the result in the
account row in the `mysql.user` system
table. The statement also returns the cleartext password
in a result set to make it available to the user or
application executing the statement. For details about the
result set and characteristics of randomly generated
passwords, see
[Random Password Generation](https://dev.mysql.com/doc/refman/8.0/en/password-management.html#random-password-generation "Random Password Generation").


- `IDENTIFIED WITH
                auth_plugin AS
                'auth_string'`


Sets the account authentication plugin to
_`auth_plugin`_ and stores the
`'auth_string'`
value as is in the `mysql.user` account
row. If the plugin requires a hashed string, the string is
assumed to be already hashed in the format the plugin
requires.


Example: Specify the password as cleartext; the default plugin
is used:


``` sql

CREATE USER 'jeffrey'@'localhost'
  IDENTIFIED BY 'password';
```

Example: Specify the authentication plugin, along with a
cleartext password value:


``` sql

CREATE USER 'jeffrey'@'localhost'
  IDENTIFIED WITH mysql_native_password BY 'password';
```

In each case, the password value stored in the account row is
the cleartext value
`'password'` after
it has been hashed by the authentication plugin associated
with the account.


For additional information about setting passwords and
authentication plugins, see
[Section 8.2.14, “Assigning Account Passwords”](https://dev.mysql.com/doc/refman/8.0/en/assigning-passwords.html "8.2.14 Assigning Account Passwords"), and
[Section 8.2.17, “Pluggable Authentication”](https://dev.mysql.com/doc/refman/8.0/en/pluggable-authentication.html "8.2.17 Pluggable Authentication").

##### CREATE USER Multifactor Authentication Options

The _`auth_option`_ part of
[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") defines an
authentication method for one-factor/single-factor
authentication (1FA/SFA). As of MySQL 8.0.27,
[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") has clauses that
support multifactor authentication (MFA), such that accounts
can have up to three authentication methods. That is, accounts
can use two-factor authentication (2FA) or three-factor
authentication (3FA).


The [`authentication_policy`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_authentication_policy)
system variable defines constraints for
[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") statements with
multifactor authentication (MFA) clauses. For example, the
[`authentication_policy`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_authentication_policy) setting
controls the number of authentication factors that accounts
may have, and for each factor, which authentication methods
are permitted. See
[Configuring the Multifactor Authentication Policy](https://dev.mysql.com/doc/refman/8.0/en/multifactor-authentication.html#multifactor-authentication-policy "Configuring the Multifactor Authentication Policy").


For information about factor-specific rules that determine the
default authentication plugin for authentication clauses that
name no plugin, see
[The Default Authentication Plugin](https://dev.mysql.com/doc/refman/8.0/en/pluggable-authentication.html#pluggable-authentication-default-plugin "The Default Authentication Plugin").


Following _`auth_option`_, there may
appear different optional MFA clauses:

- _`2fa_auth_option`_: Specifies a
factor 2 authentication method. The following example
defines `caching_sha2_password` as the
factor 1 authentication method, and
`authentication_ldap_sasl` as the factor
2 authentication method.




``` sql

CREATE USER 'u1'@'localhost'
    IDENTIFIED WITH caching_sha2_password
      BY 'sha2_password'
    AND IDENTIFIED WITH authentication_ldap_sasl
      AS 'uid=u1_ldap,ou=People,dc=example,dc=com';
```

- _`3fa_auth_option`_: Following
_`2fa_auth_option`_, there may
appear a _`3fa_auth_option`_ clause
to specify a factor 3 authentication method. The following
example defines `caching_sha2_password`
as the factor 1 authentication method,
`authentication_ldap_sasl` as the factor
2 authentication method, and
`authentication_fido` as the factor 3
authentication method




``` sql

CREATE USER 'u1'@'localhost'
    IDENTIFIED WITH caching_sha2_password
      BY 'sha2_password'
    AND IDENTIFIED WITH authentication_ldap_sasl
      AS 'uid=u1_ldap,ou=People,dc=example,dc=com'
    AND IDENTIFIED WITH authentication_fido;
```

- _`initial_auth_option`_: Specifies
an initial authentication method for configuring FIDO
passwordless authentication. As shown in the following,
temporary authentication using either a generated random
password or a user-specified
_`auth-string`_ is required to
enable FIDO passwordless authentication.




``` sql

CREATE USER user
    IDENTIFIED WITH authentication_fido
    INITIAL AUTHENTICATION IDENTIFIED BY {RANDOM PASSWORD | 'auth_string'};
```




For information about configuring passwordless
authentication using FIDO pluggable authentication, See
[FIDO Passwordless Authentication](https://dev.mysql.com/doc/refman/8.0/en/fido-pluggable-authentication.html#fido-pluggable-authentication-passwordless "FIDO Passwordless Authentication").


##### CREATE USER Role Options

The `DEFAULT ROLE` clause defines which roles
become active when the user connects to the server and
authenticates, or when the user executes the
[`SET ROLE\\
          DEFAULT`](https://dev.mysql.com/doc/refman/8.0/en/set-role.html "15.7.1.11 SET ROLE Statement") statement during a session.


Each role name uses the format described in
[Section 8.2.5, “Specifying Role Names”](https://dev.mysql.com/doc/refman/8.0/en/role-names.html "8.2.5 Specifying Role Names"). For example:


``` sql

CREATE USER 'joe'@'10.0.0.1' DEFAULT ROLE administrator, developer;
```

The host name part of the role name, if omitted, defaults to
`'%'`.


The `DEFAULT ROLE` clause permits a list of
one or more comma-separated role names. These roles must exist
at the time [`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") is
executed; otherwise the statement raises an error
( [`ER_USER_DOES_NOT_EXIST`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_user_does_not_exist)), and
the user is not created.

##### CREATE USER SSL/TLS Options

MySQL can check X.509 certificate attributes in addition to
the usual authentication that is based on the user name and
credentials. For background information on the use of SSL/TLS
with MySQL, see [Section 8.3, “Using Encrypted Connections”](https://dev.mysql.com/doc/refman/8.0/en/encrypted-connections.html "8.3 Using Encrypted Connections").


To specify SSL/TLS-related options for a MySQL account, use a
`REQUIRE` clause that specifies one or more
_`tls_option`_ values.


Order of `REQUIRE` options does not matter,
but no option can be specified twice. The
`AND` keyword is optional between
`REQUIRE` options.


[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") permits these
_`tls_option`_ values:

- `NONE`


Indicates that all accounts named by the statement have no
SSL or X.509 requirements. Unencrypted connections are
permitted if the user name and password are valid.
Encrypted connections can be used, at the client's option,
if the client has the proper certificate and key files.




``` sql

CREATE USER 'jeffrey'@'localhost' REQUIRE NONE;
```




Clients attempt to establish a secure connection by
default. For clients that have `REQUIRE
                NONE`, the connection attempt falls back to an
unencrypted connection if a secure connection cannot be
established. To require an encrypted connection, a client
need specify only the
[`--ssl-mode=REQUIRED`](https://dev.mysql.com/doc/refman/8.0/en/connection-options.html#option_general_ssl-mode)
option; the connection attempt fails if a secure
connection cannot be established.


`NONE` is the default if no SSL-related
`REQUIRE` options are specified.


- `SSL`


Tells the server to permit only encrypted connections for
all accounts named by the statement.




``` sql

CREATE USER 'jeffrey'@'localhost' REQUIRE SSL;
```




Clients attempt to establish a secure connection by
default. For accounts that have `REQUIRE
                SSL`, the connection attempt fails if a secure
connection cannot be established.


- `X509`


For all accounts named by the statement, requires that
clients present a valid certificate, but the exact
certificate, issuer, and subject do not matter. The only
requirement is that it should be possible to verify its
signature with one of the CA certificates. Use of X.509
certificates always implies encryption, so the
`SSL` option is unnecessary in this case.




``` sql

CREATE USER 'jeffrey'@'localhost' REQUIRE X509;
```




For accounts with `REQUIRE X509`, clients
must specify the [`--ssl-key`](https://dev.mysql.com/doc/refman/8.0/en/connection-options.html#option_general_ssl-key)
and [`--ssl-cert`](https://dev.mysql.com/doc/refman/8.0/en/connection-options.html#option_general_ssl-cert) options to
connect. (It is recommended but not required that
[`--ssl-ca`](https://dev.mysql.com/doc/refman/8.0/en/connection-options.html#option_general_ssl-ca) also be specified
so that the public certificate provided by the server can
be verified.) This is true for `ISSUER`
and `SUBJECT` as well because those
`REQUIRE` options imply the requirements
of `X509`.


- `ISSUER
                'issuer'`


For all accounts named by the statement, requires that
clients present a valid X.509 certificate issued by CA
`'issuer'`. If
a client presents a certificate that is valid but has a
different issuer, the server rejects the connection. Use
of X.509 certificates always implies encryption, so the
`SSL` option is unnecessary in this case.




``` sql

CREATE USER 'jeffrey'@'localhost'
    REQUIRE ISSUER '/C=SE/ST=Stockholm/L=Stockholm/
      O=MySQL/CN=CA/emailAddress=ca@example.com';
```




Because `ISSUER` implies the requirements
of `X509`, clients must specify the
[`--ssl-key`](https://dev.mysql.com/doc/refman/8.0/en/connection-options.html#option_general_ssl-key) and
[`--ssl-cert`](https://dev.mysql.com/doc/refman/8.0/en/connection-options.html#option_general_ssl-cert) options to
connect. (It is recommended but not required that
[`--ssl-ca`](https://dev.mysql.com/doc/refman/8.0/en/connection-options.html#option_general_ssl-ca) also be specified
so that the public certificate provided by the server can
be verified.)


- `SUBJECT
                'subject'`


For all accounts named by the statement, requires that
clients present a valid X.509 certificate containing the
subject _`subject`_. If a client
presents a certificate that is valid but has a different
subject, the server rejects the connection. Use of X.509
certificates always implies encryption, so the
`SSL` option is unnecessary in this case.




``` sql

CREATE USER 'jeffrey'@'localhost'
    REQUIRE SUBJECT '/C=SE/ST=Stockholm/L=Stockholm/
      O=MySQL demo client certificate/
      CN=client/emailAddress=client@example.com';
```




MySQL does a simple string comparison of the
`'subject'`
value to the value in the certificate, so lettercase and
component ordering must be given exactly as present in the
certificate.



Because `SUBJECT` implies the
requirements of `X509`, clients must
specify the [`--ssl-key`](https://dev.mysql.com/doc/refman/8.0/en/connection-options.html#option_general_ssl-key) and
[`--ssl-cert`](https://dev.mysql.com/doc/refman/8.0/en/connection-options.html#option_general_ssl-cert) options to
connect. (It is recommended but not required that
[`--ssl-ca`](https://dev.mysql.com/doc/refman/8.0/en/connection-options.html#option_general_ssl-ca) also be specified
so that the public certificate provided by the server can
be verified.)


- `CIPHER
                'cipher'`


For all accounts named by the statement, requires a
specific cipher method for encrypting connections. This
option is needed to ensure that ciphers and key lengths of
sufficient strength are used. Encryption can be weak if
old algorithms using short encryption keys are used.




``` sql

CREATE USER 'jeffrey'@'localhost'
    REQUIRE CIPHER 'EDH-RSA-DES-CBC3-SHA';
```


The `SUBJECT`, `ISSUER`, and
`CIPHER` options can be combined in the
`REQUIRE` clause:


``` sql

CREATE USER 'jeffrey'@'localhost'
  REQUIRE SUBJECT '/C=SE/ST=Stockholm/L=Stockholm/
    O=MySQL demo client certificate/
    CN=client/emailAddress=client@example.com'
  AND ISSUER '/C=SE/ST=Stockholm/L=Stockholm/
    O=MySQL/CN=CA/emailAddress=ca@example.com'
  AND CIPHER 'EDH-RSA-DES-CBC3-SHA';
```

##### CREATE USER Resource-Limit Options

It is possible to place limits on use of server resources by
an account, as discussed in [Section 8.2.21, “Setting Account Resource Limits”](https://dev.mysql.com/doc/refman/8.0/en/user-resources.html "8.2.21 Setting Account Resource Limits").
To do so, use a `WITH` clause that specifies
one or more _`resource_option`_ values.


Order of `WITH` options does not matter,
except that if a given resource limit is specified multiple
times, the last instance takes precedence.


[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") permits these
_`resource_option`_ values:

- `MAX_QUERIES_PER_HOUR
                count`,
`MAX_UPDATES_PER_HOUR
                count`,
`MAX_CONNECTIONS_PER_HOUR
                count`


For all accounts named by the statement, these options
restrict how many queries, updates, and connections to the
server are permitted to each account during any given
one-hour period. If _`count`_ is
`0` (the default), this means that there
is no limitation for the account.


- `MAX_USER_CONNECTIONS
                count`


For all accounts named by the statement, restricts the
maximum number of simultaneous connections to the server
by each account. A nonzero
_`count`_ specifies the limit for
the account explicitly. If
_`count`_ is `0`
(the default), the server determines the number of
simultaneous connections for the account from the global
value of the
[`max_user_connections`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_user_connections)
system variable. If
[`max_user_connections`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_user_connections) is
also zero, there is no limit for the account.


Example:


``` sql

CREATE USER 'jeffrey'@'localhost'
  WITH MAX_QUERIES_PER_HOUR 500 MAX_UPDATES_PER_HOUR 100;
```

##### CREATE USER Password-Management Options

[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") supports several
_`password_option`_ values for password
management:

- Password expiration options: You can expire an account
password manually and establish its password expiration
policy. Policy options do not expire the password.
Instead, they determine how the server applies automatic
expiration to the account based on password age, which is
assessed from the date and time of the most recent account
password change.


- Password reuse options: You can restrict password reuse
based on number of password changes, time elapsed, or
both.


- Password verification-required options: You can indicate
whether attempts to change an account password must
specify the current password, as verification that the
user attempting to make the change actually knows the
current password.


- Incorrect-password failed-login tracking options: You can
cause the server to track failed login attempts and
temporarily lock accounts for which too many consecutive
incorrect passwords are given. The required number of
failures and the lock time are configurable.


This section describes the syntax for password-management
options. For information about establishing policy for
password management, see
[Section 8.2.15, “Password Management”](https://dev.mysql.com/doc/refman/8.0/en/password-management.html "8.2.15 Password Management").


If multiple password-management options of a given type are
specified, the last one takes precedence. For example,
`PASSWORD EXPIRE DEFAULT PASSWORD EXPIRE
          NEVER` is the same as `PASSWORD EXPIRE
          NEVER`.

Note

Except for the options that pertain to failed-login
tracking, password-management options apply only to accounts
that use an authentication plugin that stores credentials
internally to MySQL. For accounts that use a plugin that
performs authentication against a credentials system that is
external to MySQL, password management must be handled
externally against that system as well. For more information
about internal credentials storage, see
[Section 8.2.15, “Password Management”](https://dev.mysql.com/doc/refman/8.0/en/password-management.html "8.2.15 Password Management").

A client has an expired password if the account password was
expired manually or the password age is considered greater
than its permitted lifetime per the automatic expiration
policy. In this case, the server either disconnects the client
or restricts the operations permitted to it (see
[Section 8.2.16, “Server Handling of Expired Passwords”](https://dev.mysql.com/doc/refman/8.0/en/expired-password-handling.html "8.2.16 Server Handling of Expired Passwords")). Operations
performed by a restricted client result in an error until the
user establishes a new account password.


[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") permits these
_`password_option`_ values for
controlling password expiration:

- `PASSWORD EXPIRE`


Immediately marks the password expired for all accounts
named by the statement.




``` sql

CREATE USER 'jeffrey'@'localhost' PASSWORD EXPIRE;
```

- `PASSWORD EXPIRE DEFAULT`


Sets all accounts named by the statement so that the
global expiration policy applies, as specified by the
[`default_password_lifetime`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_default_password_lifetime)
system variable.




``` sql

CREATE USER 'jeffrey'@'localhost' PASSWORD EXPIRE DEFAULT;
```

- `PASSWORD EXPIRE NEVER`


This expiration option overrides the global policy for all
accounts named by the statement. For each, it disables
password expiration so that the password never expires.




``` sql

CREATE USER 'jeffrey'@'localhost' PASSWORD EXPIRE NEVER;
```

- `PASSWORD EXPIRE INTERVAL
                N DAY`


This expiration option overrides the global policy for all
accounts named by the statement. For each, it sets the
password lifetime to _`N`_ days.
The following statement requires the password to be
changed every 180 days:




``` sql

CREATE USER 'jeffrey'@'localhost' PASSWORD EXPIRE INTERVAL 180 DAY;
```


[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") permits these
_`password_option`_ values for
controlling reuse of previous passwords based on required
minimum number of password changes:

- `PASSWORD HISTORY DEFAULT`


Sets all accounts named by the statement so that the
global policy about password history length applies, to
prohibit reuse of passwords before the number of changes
specified by the
[`password_history`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_password_history) system
variable.




``` sql

CREATE USER 'jeffrey'@'localhost' PASSWORD HISTORY DEFAULT;
```

- `PASSWORD HISTORY
                N`


This history-length option overrides the global policy for
all accounts named by the statement. For each, it sets the
password history length to _`N`_
passwords, to prohibit reusing any of the
_`N`_ most recently chosen
passwords. The following statement prohibits reuse of any
of the previous 6 passwords:




``` sql

CREATE USER 'jeffrey'@'localhost' PASSWORD HISTORY 6;
```


[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") permits these
_`password_option`_ values for
controlling reuse of previous passwords based on time elapsed:

- `PASSWORD REUSE INTERVAL DEFAULT`


Sets all statements named by the account so that the
global policy about time elapsed applies, to prohibit
reuse of passwords newer than the number of days specified
by the
[`password_reuse_interval`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_password_reuse_interval)
system variable.




``` sql

CREATE USER 'jeffrey'@'localhost' PASSWORD REUSE INTERVAL DEFAULT;
```

- `PASSWORD REUSE INTERVAL
                N DAY`


This time-elapsed option overrides the global policy for
all accounts named by the statement. For each, it sets the
password reuse interval to _`N`_
days, to prohibit reuse of passwords newer than that many
days. The following statement prohibits password reuse for
360 days:




``` sql

CREATE USER 'jeffrey'@'localhost' PASSWORD REUSE INTERVAL 360 DAY;
```


[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") permits these
_`password_option`_ values for
controlling whether attempts to change an account password
must specify the current password, as verification that the
user attempting to make the change actually knows the current
password:

- `PASSWORD REQUIRE CURRENT`


This verification option overrides the global policy for
all accounts named by the statement. For each, it requires
that password changes specify the current password.




``` sql

CREATE USER 'jeffrey'@'localhost' PASSWORD REQUIRE CURRENT;
```

- `PASSWORD REQUIRE CURRENT OPTIONAL`


This verification option overrides the global policy for
all accounts named by the statement. For each, it does not
require that password changes specify the current
password. (The current password may but need not be
given.)




``` sql

CREATE USER 'jeffrey'@'localhost' PASSWORD REQUIRE CURRENT OPTIONAL;
```

- `PASSWORD REQUIRE CURRENT DEFAULT`


Sets all statements named by the account so that the
global policy about password verification applies, as
specified by the
[`password_require_current`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_password_require_current)
system variable.




``` sql

CREATE USER 'jeffrey'@'localhost' PASSWORD REQUIRE CURRENT DEFAULT;
```


As of MySQL 8.0.19, [`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement")
permits these _`password_option`_
values for controlling failed-login tracking:

- `FAILED_LOGIN_ATTEMPTS
                N`


Whether to track account login attempts that specify an
incorrect password. _`N`_ must be a
number from 0 to 32767. A value of 0 disables failed-login
tracking. Values greater than 0 indicate how many
consecutive password failures cause temporary account
locking (if `PASSWORD_LOCK_TIME` is also
nonzero).


- `PASSWORD_LOCK_TIME {N
                | UNBOUNDED}`


How long to lock the account after too many consecutive
login attempts provide an incorrect password.
_`N`_ must be a number from 0 to
32767, or `UNBOUNDED`. A value of 0
disables temporary account locking. Values greater than 0
indicate how long to lock the account in days. A value of
`UNBOUNDED` causes the account locking
duration to be unbounded; once locked, the account remains
in a locked state until unlocked. For information about
the conditions under which unlocking occurs, see
[Failed-Login Tracking and Temporary Account Locking](https://dev.mysql.com/doc/refman/8.0/en/password-management.html#failed-login-tracking "Failed-Login Tracking and Temporary Account Locking").


For failed-login tracking and temporary locking to occur, an
account's `FAILED_LOGIN_ATTEMPTS` and
`PASSWORD_LOCK_TIME` options both must be
nonzero. The following statement creates an account that
remains locked for two days after four consecutive password
failures:


``` sql

CREATE USER 'jeffrey'@'localhost'
  FAILED_LOGIN_ATTEMPTS 4 PASSWORD_LOCK_TIME 2;
```

##### CREATE USER Comment and Attribute Options

As of MySQL 8.0.21, you can create an account with an optional
comment or attribute, as described here:

- **User comment**


To set a user comment, add `COMMENT
                'user_comment'` to the
`CREATE USER` statement, where
_`user_comment`_ is the text of the
user comment.



Example (omitting any other options):




``` sql

CREATE USER 'jon'@'localhost' COMMENT 'Some information about Jon';
```

- **User attribute**


A user attribute is a JSON object made up of one or more
key-value pairs, and is set by including
`ATTRIBUTE
                'json_object'` as part
of `CREATE USER`.
_`json_object`_ must be a valid
JSON object.



Example (omitting any other options):




``` sql

CREATE USER 'jim'@'localhost'
      ATTRIBUTE '{"fname": "James", "lname": "Scott", "phone": "123-456-7890"}';
```


User comments and user attributes are stored together in the
`ATTRIBUTE` column of the Information Schema
[`USER_ATTRIBUTES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-user-attributes-table.html "28.3.46 The INFORMATION_SCHEMA USER_ATTRIBUTES Table") table. This query
displays the row in this table inserted by the statement just
shown for creating the user `jim@localhost`:


``` sql

mysql> SELECT * FROM INFORMATION_SCHEMA.USER_ATTRIBUTES
    ->    WHERE USER = 'jim' AND HOST = 'localhost'\G
*************************** 1. row ***************************
     USER: jim
     HOST: localhost
ATTRIBUTE: {"fname": "James", "lname": "Scott", "phone": "123-456-7890"}
1 row in set (0.00 sec)
```

The `COMMENT` option in actuality provides a
shortcut for setting a user attribute whose only element has
`comment` as its key and whose value is the
argument supplied for the option. You can see this by
executing the statement `CREATE USER 'jon'@'localhost'
          COMMENT 'Some information about Jon'`, and observing
the row which it inserts into the
[`USER_ATTRIBUTES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-user-attributes-table.html "28.3.46 The INFORMATION_SCHEMA USER_ATTRIBUTES Table") table:


``` sql

mysql> CREATE USER 'jon'@'localhost' COMMENT 'Some information about Jon';
Query OK, 0 rows affected (0.06 sec)

mysql> SELECT * FROM INFORMATION_SCHEMA.USER_ATTRIBUTES
    ->    WHERE USER = 'jon' AND HOST = 'localhost';
+------+-----------+-------------------------------------------+
| USER | HOST      | ATTRIBUTE                                 |
+------+-----------+-------------------------------------------+
| jon  | localhost | {"comment": "Some information about Jon"} |
+------+-----------+-------------------------------------------+
1 row in set (0.00 sec)
```

You cannot use `COMMENT` and
`ATTRIBUTE` together in the same
`CREATE USER` statement; attempting to do so
causes a syntax error. To set a user comment concurrently with
setting a user attribute, use `ATTRIBUTE` and
include in its argument a value with a
`comment` key, like this:


``` sql

mysql> CREATE USER 'bill'@'localhost'
    ->        ATTRIBUTE '{"fname":"William", "lname":"Schmidt",
    ->        "comment":"Website developer"}';
Query OK, 0 rows affected (0.16 sec)
```

Since the content of the `ATTRIBUTE` row is a
JSON object, you can employ any appropriate MySQL JSON
functions or operators to manipulate it, as shown here:


``` sql

mysql> SELECT
    ->   USER AS User,
    ->   HOST AS Host,
    ->   CONCAT(ATTRIBUTE->>"$.fname"," ",ATTRIBUTE->>"$.lname") AS 'Full Name',
    ->   ATTRIBUTE->>"$.comment" AS Comment
    -> FROM INFORMATION_SCHEMA.USER_ATTRIBUTES
    -> WHERE USER='bill' AND HOST='localhost';
+------+-----------+-----------------+-------------------+
| User | Host      | Full Name       | Comment           |
+------+-----------+-----------------+-------------------+
| bill | localhost | William Schmidt | Website developer |
+------+-----------+-----------------+-------------------+
1 row in set (0.00 sec)
```

To set or to make changes in the user comment or user
attribute for an existing user, you can use a
`COMMENT` or `ATTRIBUTE`
option with an [`ALTER USER`](https://dev.mysql.com/doc/refman/8.0/en/alter-user.html "15.7.1.1 ALTER USER Statement")
statement.


Because the user comment and user attribute are stored
together internally in a single
[`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type") column, this sets an upper
limit on their maximum combined size; see
[JSON Storage Requirements](https://dev.mysql.com/doc/refman/8.0/en/storage-requirements.html#data-types-storage-reqs-json "JSON Storage Requirements"), for more
information.


See also the description of the Information Schema
[`USER_ATTRIBUTES`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-user-attributes-table.html "28.3.46 The INFORMATION_SCHEMA USER_ATTRIBUTES Table") table for more
information and examples.

##### CREATE USER Account-Locking Options

MySQL supports account locking and unlocking using the
`ACCOUNT LOCK` and `ACCOUNT
          UNLOCK` options, which specify the locking state for
an account. For additional discussion, see
[Section 8.2.20, “Account Locking”](https://dev.mysql.com/doc/refman/8.0/en/account-locking.html "8.2.20 Account Locking").


If multiple account-locking options are specified, the last
one takes precedence.

##### CREATE USER Binary Logging

[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") is written to the
binary log if it succeeds, but not if it fails; in that case,
rollback occurs and no changes are made. A statement written
to the binary log includes all named users. If the `IF
          NOT EXISTS` clause is given, this includes even users
that already exist and were not created.


The statement written to the binary log specifies an
authentication plugin for each user, determined as follows:

- The plugin named in the original statement, if one was
specified.


- Otherwise, the default authentication plugin. In
particular, if a user `u1` already exists
and uses a nondefault authentication plugin, the statement
written to the binary log for `CREATE USER IF NOT
                EXISTS u1` names the default authentication
plugin. (If the statement written to the binary log must
specify a nondefault authentication plugin for a user,
include it in the original statement.)


If the server adds the default authentication plugin for any
nonexisting users in the statement written to the binary log,
it writes a warning to the error log naming those users.


If the original statement specifies the
`FAILED_LOGIN_ATTEMPTS` or
`PASSWORD_LOCK_TIME` option, the statement
written to the binary log includes the option.


[`CREATE USER`](https://dev.mysql.com/doc/refman/8.0/en/create-user.html "15.7.1.3 CREATE USER Statement") statements with
clauses that support multifactor authentication (MFA) are
written to the binary log.

- `CREATE USER ... IDENTIFIED WITH .. INITIAL
                AUTHENTICATION IDENTIFIED WITH ...` statements
are written to the binary log as `CREATE USER ..
                IDENTIFIED WITH .. INITIAL AUTHENTICATION IDENTIFIED WITH
                .. AS
                'password-hash'`,
where the _`password-hash`_ is the
user-specified _`auth-string`_ or
the random password generated by server when the
`RANDOM PASSWORD` clause is specified.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/create-role.html "Previous: CREATE ROLE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/account-management-statements.html "Up: Account Management Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/drop-role.html "Next: DROP ROLE Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/create-user.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-user.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/create-user.html)

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