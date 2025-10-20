---
url: https://dev.mysql.com/doc/refman/8.0/en/blob.html
scraped_at: 2025-10-20T02:59:41.203Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/blob.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/blob.html "Hide Sidebar")

[Previous: The BINARY and VARBINARY Types](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "Previous: The BINARY and VARBINARY Types")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: String Data Types](https://dev.mysql.com/doc/refman/8.0/en/string-types.html "Up: String Data Types")[Next: The ENUM Type](https://dev.mysql.com/doc/refman/8.0/en/enum.html "Next: The ENUM Type")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/blob.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/blob.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/blob.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/blob.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/blob.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/blob.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/blob.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/blob.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/blob.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/blob.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/blob.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/blob.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/blob.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/blob.html)  / [Data Types](https://dev.mysql.com/doc/refman/8.0/en/data-types.html)  /
[String Data Types](https://dev.mysql.com/doc/refman/8.0/en/string-types.html)  /

The BLOB and TEXT Types


### 13.3.4 The BLOB and TEXT Types

A `BLOB` is a binary large object that can hold
a variable amount of data. The four `BLOB`
types are `TINYBLOB`, `BLOB`,
`MEDIUMBLOB`, and `LONGBLOB`.
These differ only in the maximum length of the values they can
hold. The four `TEXT` types are
`TINYTEXT`, `TEXT`,
`MEDIUMTEXT`, and `LONGTEXT`.
These correspond to the four `BLOB` types and
have the same maximum lengths and storage requirements. See
[Section 13.7, “Data Type Storage Requirements”](https://dev.mysql.com/doc/refman/8.0/en/storage-requirements.html "13.7 Data Type Storage Requirements").


`BLOB` values are treated as binary strings
(byte strings). They have the `binary`
character set and collation, and comparison and sorting are
based on the numeric values of the bytes in column values.
`TEXT` values are treated as nonbinary strings
(character strings). They have a character set other than
`binary`, and values are sorted and compared
based on the collation of the character set.


If strict SQL mode is not enabled and you assign a value to a
`BLOB` or `TEXT` column that
exceeds the column's maximum length, the value is truncated to
fit and a warning is generated. For truncation of nonspace
characters, you can cause an error to occur (rather than a
warning) and suppress insertion of the value by using strict SQL
mode. See [Section 7.1.11, “Server SQL Modes”](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html "7.1.11 Server SQL Modes").


Truncation of excess trailing spaces from values to be inserted
into [`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns always
generates a warning, regardless of the SQL mode.


For `TEXT` and `BLOB` columns,
there is no padding on insert and no bytes are stripped on
select.


If a `TEXT` column is indexed, index entry
comparisons are space-padded at the end. This means that, if the
index requires unique values, duplicate-key errors occur for
values that differ only in the number of trailing spaces. For
example, if a table contains `'a'`, an attempt
to store `'a '` causes a duplicate-key
error. This is not true for `BLOB` columns.


In most respects, you can regard a `BLOB`
column as a [`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types") column that
can be as large as you like. Similarly, you can regard a
`TEXT` column as a
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") column.
`BLOB` and `TEXT` differ from
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types") and
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") in the following ways:

- For indexes on `BLOB` and
`TEXT` columns, you must specify an index
prefix length. For [`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") and
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"), a prefix length is
optional. See [Section 10.3.5, “Column Indexes”](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html "10.3.5 Column Indexes").


- `BLOB` and `TEXT` columns
cannot have `DEFAULT` values.


If you use the `BINARY` attribute with a
`TEXT` data type, the column is assigned the
binary ( `_bin`) collation of the column
character set.


`LONG` and `LONG VARCHAR` map
to the `MEDIUMTEXT` data type. This is a
compatibility feature.


MySQL Connector/ODBC defines `BLOB` values as
`LONGVARBINARY` and `TEXT`
values as `LONGVARCHAR`.


Because `BLOB` and `TEXT`
values can be extremely long, you might encounter some
constraints in using them:

- Only the first
[`max_sort_length`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_sort_length) bytes of
the column are used when sorting. The default value of
[`max_sort_length`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_sort_length) is 1024.
You can make more bytes significant in sorting or grouping
by increasing the value of
[`max_sort_length`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_sort_length) at server
startup or runtime. Any client can change the value of its
session [`max_sort_length`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_sort_length)
variable:




```sql

mysql> SET max_sort_length = 2000;
mysql> SELECT id, comment FROM t
      -> ORDER BY comment;
```

- Instances of `BLOB` or
`TEXT` columns in the result of a query
that is processed using a temporary table causes the server
to use a table on disk rather than in memory because the
`MEMORY` storage engine does not support
those data types (see
[Section 10.4.4, “Internal Temporary Table Use in MySQL”](https://dev.mysql.com/doc/refman/8.0/en/internal-temporary-tables.html "10.4.4 Internal Temporary Table Use in MySQL")). Use of disk
incurs a performance penalty, so include
`BLOB` or `TEXT` columns
in the query result only if they are really needed. For
example, avoid using
[`SELECT *`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"),
which selects all columns.


- The maximum size of a `BLOB` or
`TEXT` object is determined by its type,
but the largest value you actually can transmit between the
client and server is determined by the amount of available
memory and the size of the communications buffers. You can
change the message buffer size by changing the value of the
[`max_allowed_packet`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_allowed_packet)
variable, but you must do so for both the server and your
client program. For example, both [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client")
and [**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program") enable you to change the
client-side
[`max_allowed_packet`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_allowed_packet) value.
See [Section 7.1.1, “Configuring the Server”](https://dev.mysql.com/doc/refman/8.0/en/server-configuration.html "7.1.1 Configuring the Server"),
[Section 6.5.1, “mysql — The MySQL Command-Line Client”](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client"), and [Section 6.5.4, “mysqldump — A Database Backup Program”](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program").
You may also want to compare the packet sizes and the size
of the data objects you are storing with the storage
requirements, see [Section 13.7, “Data Type Storage Requirements”](https://dev.mysql.com/doc/refman/8.0/en/storage-requirements.html "13.7 Data Type Storage Requirements")


Each `BLOB` or `TEXT` value is
represented internally by a separately allocated object. This is
in contrast to all other data types, for which storage is
allocated once per column when the table is opened.


In some cases, it may be desirable to store binary data such as
media files in `BLOB` or
`TEXT` columns. You may find MySQL's string
handling functions useful for working with such data. See
[Section 14.8, “String Functions and Operators”](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html "14.8 String Functions and Operators"). For security and other
reasons, it is usually preferable to do so using application
code rather than giving application users the
[`FILE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_file) privilege. You can discuss
specifics for various languages and platforms in the MySQL
Forums ( [http://forums.mysql.com/](http://forums.mysql.com/)).

Note

Within the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client, binary strings
display using hexadecimal notation, depending on the value of
the [`--binary-as-hex`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_binary-as-hex). For more
information about that option, see [Section 6.5.1, “mysql — The MySQL Command-Line Client”](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "Previous: The BINARY and VARBINARY Types") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/string-types.html "Up: String Data Types") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/enum.html "Next: The ENUM Type")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/blob.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/blob.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/blob.html)

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