---
url: https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html
scraped_at: 2025-10-20T03:14:18.866Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html "Hide Sidebar")

[Previous: Derived Condition Pushdown Optimization](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html "Previous: Derived Condition Pushdown Optimization")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimizing SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html "Up: Optimizing SQL Statements")[Next: Optimizing Performance Schema Queries](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-optimization.html "Next: Optimizing Performance Schema Queries")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/information-schema-optimization.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/information-schema-optimization.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/information-schema-optimization.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/information-schema-optimization.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/information-schema-optimization.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/information-schema-optimization.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/information-schema-optimization.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/information-schema-optimization.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimizing SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html)  /

Optimizing INFORMATION\_SCHEMA Queries


### 10.2.3 Optimizing INFORMATION\_SCHEMA Queries

Applications that monitor databases may make frequent use of
`INFORMATION_SCHEMA` tables. To write queries
for these tables most efficiently, use the following general
guidelines:

- Try to query only `INFORMATION_SCHEMA`
tables that are views on data dictionary tables.


- Try to query only for static metadata. Selecting columns or
using retrieval conditions for dynamic metadata along with
static metadata adds overhead to process the dynamic
metadata.


Note

Comparison behavior for database and table names in
`INFORMATION_SCHEMA` queries might differ
from what you expect. For details, see
[Section 12.8.7, “Using Collation in INFORMATION\_SCHEMA Searches”](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-information-schema.html "12.8.7 Using Collation in INFORMATION_SCHEMA Searches").

These `INFORMATION_SCHEMA` tables are
implemented as views on data dictionary tables, so queries on
them retrieve information from the data dictionary:


``` none

CHARACTER_SETS
CHECK_CONSTRAINTS
COLLATIONS
COLLATION_CHARACTER_SET_APPLICABILITY
COLUMNS
EVENTS
FILES
INNODB_COLUMNS
INNODB_DATAFILES
INNODB_FIELDS
INNODB_FOREIGN
INNODB_FOREIGN_COLS
INNODB_INDEXES
INNODB_TABLES
INNODB_TABLESPACES
INNODB_TABLESPACES_BRIEF
INNODB_TABLESTATS
KEY_COLUMN_USAGE
PARAMETERS
PARTITIONS
REFERENTIAL_CONSTRAINTS
RESOURCE_GROUPS
ROUTINES
SCHEMATA
STATISTICS
TABLES
TABLE_CONSTRAINTS
TRIGGERS
VIEWS
VIEW_ROUTINE_USAGE
VIEW_TABLE_USAGE
```

Some types of values, even for a non-view
`INFORMATION_SCHEMA` table, are retrieved by
lookups from the data dictionary. This includes values such as
database and table names, table types, and storage engines.


Some `INFORMATION_SCHEMA` tables contain
columns that provide table statistics:


``` none

STATISTICS.CARDINALITY
TABLES.AUTO_INCREMENT
TABLES.AVG_ROW_LENGTH
TABLES.CHECKSUM
TABLES.CHECK_TIME
TABLES.CREATE_TIME
TABLES.DATA_FREE
TABLES.DATA_LENGTH
TABLES.INDEX_LENGTH
TABLES.MAX_DATA_LENGTH
TABLES.TABLE_ROWS
TABLES.UPDATE_TIME
```

Those columns represent dynamic table metadata; that is,
information that changes as table contents change.


By default, MySQL retrieves cached values for those columns from
the `mysql.index_stats` and
`mysql.innodb_table_stats` dictionary tables
when the columns are queried, which is more efficient than
retrieving statistics directly from the storage engine. If
cached statistics are not available or have expired, MySQL
retrieves the latest statistics from the storage engine and
caches them in the `mysql.index_stats` and
`mysql.innodb_table_stats` dictionary tables.
Subsequent queries retrieve the cached statistics until the
cached statistics expire. A server restart or the first opening
of the `mysql.index_stats` and
`mysql.innodb_table_stats` tables do not update
cached statistics automatically.


The
[`information_schema_stats_expiry`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_information_schema_stats_expiry)
session variable defines the period of time before cached
statistics expire. The default is 86400 seconds (24 hours), but
the time period can be extended to as much as one year.


To update cached values at any time for a given table, use
[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement").


Querying statistics columns does not store or update statistics
in the `mysql.index_stats` and
`mysql.innodb_table_stats` dictionary tables
under these circumstances:

- When cached statistics have not expired.


- When
[`information_schema_stats_expiry`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_information_schema_stats_expiry)
is set to 0.


- When the server is in
[`read_only`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_read_only),
[`super_read_only`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_super_read_only),
[`transaction_read_only`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_transaction_read_only), or
[`innodb_read_only`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_read_only) mode.


- When the query also fetches Performance Schema data.


[`information_schema_stats_expiry`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_information_schema_stats_expiry)
is a session variable, and each client session can define its
own expiration value. Statistics that are retrieved from the
storage engine and cached by one session are available to other
sessions.

Note

If the [`innodb_read_only`](https://dev.mysql.com/doc/refman/8.0/en/innodb-parameters.html#sysvar_innodb_read_only)
system variable is enabled, [`ANALYZE\\
          TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") may fail because it cannot update statistics
tables in the data dictionary, which use
`InnoDB`. For [`ANALYZE\\
          TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") operations that update the key distribution,
failure may occur even if the operation updates the table
itself (for example, if it is a `MyISAM`
table). To obtain the updated distribution statistics, set
[`information_schema_stats_expiry=0`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_information_schema_stats_expiry).

For `INFORMATION_SCHEMA` tables implemented as
views on data dictionary tables, indexes on the underlying data
dictionary tables permit the optimizer to construct efficient
query execution plans. To see the choices made by the optimizer,
use [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement"). To also see the
query used by the server to execute an
`INFORMATION_SCHEMA` query, use
[`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement") immediately
following [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement").


Consider this statement, which identifies collations for the
`utf8mb4` character set:


``` sql

mysql> SELECT COLLATION_NAME
       FROM INFORMATION_SCHEMA.COLLATION_CHARACTER_SET_APPLICABILITY
       WHERE CHARACTER_SET_NAME = 'utf8mb4';
+----------------------------+
| COLLATION_NAME             |
+----------------------------+
| utf8mb4_general_ci         |
| utf8mb4_bin                |
| utf8mb4_unicode_ci         |
| utf8mb4_icelandic_ci       |
| utf8mb4_latvian_ci         |
| utf8mb4_romanian_ci        |
| utf8mb4_slovenian_ci       |
...
```

How does the server process that statement? To find out, use
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement"):


``` sql

mysql> EXPLAIN SELECT COLLATION_NAME
       FROM INFORMATION_SCHEMA.COLLATION_CHARACTER_SET_APPLICABILITY
       WHERE CHARACTER_SET_NAME = 'utf8mb4'\G
*************************** 1. row ***************************
           id: 1
  select_type: SIMPLE
        table: cs
   partitions: NULL
         type: const
possible_keys: PRIMARY,name
          key: name
      key_len: 194
          ref: const
         rows: 1
     filtered: 100.00
        Extra: Using index
*************************** 2. row ***************************
           id: 1
  select_type: SIMPLE
        table: col
   partitions: NULL
         type: ref
possible_keys: character_set_id
          key: character_set_id
      key_len: 8
          ref: const
         rows: 68
     filtered: 100.00
        Extra: NULL
2 rows in set, 1 warning (0.01 sec)
```

To see the query used to satisfy that statement, use
[`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement"):


``` sql

mysql> SHOW WARNINGS\G
*************************** 1. row ***************************
  Level: Note
   Code: 1003
Message: /* select#1 */ select `mysql`.`col`.`name` AS `COLLATION_NAME`
         from `mysql`.`character_sets` `cs`
         join `mysql`.`collations` `col`
         where ((`mysql`.`col`.`character_set_id` = '45')
         and ('utf8mb4' = 'utf8mb4'))
```

As indicated by [`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement"),
the server handles the query on
[`COLLATION_CHARACTER_SET_APPLICABILITY`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-collation-character-set-applicability-table.html "28.3.7 The INFORMATION_SCHEMA COLLATION_CHARACTER_SET_APPLICABILITY Table")
as a query on the `character_sets` and
`collations` data dictionary tables in the
`mysql` system database.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/derived-condition-pushdown-optimization.html "Previous: Derived Condition Pushdown Optimization") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/statement-optimization.html "Up: Optimizing SQL Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-optimization.html "Next: Optimizing Performance Schema Queries")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimization.html)

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