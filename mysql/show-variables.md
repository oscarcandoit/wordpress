---
url: https://dev.mysql.com/doc/refman/8.0/en/show-variables.html
scraped_at: 2025-10-20T03:07:00.233Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html "Hide Sidebar")

[Previous: SHOW TRIGGERS Statement](https://dev.mysql.com/doc/refman/8.0/en/show-triggers.html "Previous: SHOW TRIGGERS Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements")[Next: SHOW WARNINGS Statement](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "Next: SHOW WARNINGS Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/show-variables.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/show-variables.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/show-variables.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/show-variables.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/show-variables.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/show-variables.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/show-variables.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/show-variables.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Database Administration Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-server-administration-statements.html)  /
[SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/show.html)  /

SHOW VARIABLES Statement


#### 15.7.7.41 SHOW VARIABLES Statement

``` sql

SHOW [GLOBAL | SESSION] VARIABLES
    [LIKE 'pattern' | WHERE expr]
```

[`SHOW VARIABLES`](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html "15.7.7.41 SHOW VARIABLES Statement") shows the values
of MySQL system variables (see
[Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables")). This statement does
not require any privilege. It requires only the ability to
connect to the server.


System variable information is also available from these
sources:

- Performance Schema tables. See
[Section 29.12.14, “Performance Schema System Variable Tables”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-system-variable-tables.html "29.12.14 Performance Schema System Variable Tables").


- The [**mysqladmin variables**](https://dev.mysql.com/doc/refman/8.0/en/mysqladmin.html "6.5.2 mysqladmin — A MySQL Server Administration Program") command. See
[Section 6.5.2, “mysqladmin — A MySQL Server Administration Program”](https://dev.mysql.com/doc/refman/8.0/en/mysqladmin.html "6.5.2 mysqladmin — A MySQL Server Administration Program").


For [`SHOW VARIABLES`](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html "15.7.7.41 SHOW VARIABLES Statement"), a
[`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) clause, if present, indicates
which variable names to match. A `WHERE` clause
can be given to select rows using more general conditions, as
discussed in [Section 28.8, “Extensions to SHOW Statements”](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html "28.8 Extensions to SHOW Statements").


[`SHOW VARIABLES`](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html "15.7.7.41 SHOW VARIABLES Statement") accepts an
optional `GLOBAL` or `SESSION`
variable scope modifier:

- With a `GLOBAL` modifier, the statement
displays global system variable values. These are the values
used to initialize the corresponding session variables for
new connections to MySQL. If a variable has no global value,
no value is displayed.


- With a `SESSION` modifier, the statement
displays the system variable values that are in effect for
the current connection. If a variable has no session value,
the global value is displayed. `LOCAL` is a
synonym for `SESSION`.


- If no modifier is present, the default is
`SESSION`.


The scope for each system variable is listed at
[Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables").


[`SHOW VARIABLES`](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html "15.7.7.41 SHOW VARIABLES Statement") is subject to a
version-dependent display-width limit. For variables with very
long values that are not completely displayed, use
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") as a workaround. For
example:


``` sql

SELECT @@GLOBAL.innodb_data_file_path;
```

Most system variables can be set at server startup (read-only
variables such as
[`version_comment`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_version_comment) are
exceptions). Many can be changed at runtime with the
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
statement. See [Section 7.1.9, “Using System Variables”](https://dev.mysql.com/doc/refman/8.0/en/using-system-variables.html "7.1.9 Using System Variables"), and
[Section 15.7.6.1, “SET Syntax for Variable Assignment”](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment").


Partial output is shown here. The list of names and values may
differ for your server.
[Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables"), describes the meaning
of each variable, and [Section 7.1.1, “Configuring the Server”](https://dev.mysql.com/doc/refman/8.0/en/server-configuration.html "7.1.1 Configuring the Server"),
provides information about tuning them.


``` sql

mysql> SHOW VARIABLES;
+--------------------------------------------+------------------------------+
| Variable_name                              | Value                        |
+--------------------------------------------+------------------------------+
| activate_all_roles_on_login                | OFF                          |
| auto_generate_certs                        | ON                           |
| auto_increment_increment                   | 1                            |
| auto_increment_offset                      | 1                            |
| autocommit                                 | ON                           |
| automatic_sp_privileges                    | ON                           |
| avoid_temporal_upgrade                     | OFF                          |
| back_log                                   | 151                          |
| basedir                                    | /usr/                        |
| big_tables                                 | OFF                          |
| bind_address                               | *                            |
| binlog_cache_size                          | 32768                        |
| binlog_checksum                            | CRC32                        |
| binlog_direct_non_transactional_updates    | OFF                          |
| binlog_error_action                        | ABORT_SERVER                 |
| binlog_expire_logs_seconds                 | 2592000                      |
| binlog_format                              | ROW                          |
| binlog_group_commit_sync_delay             | 0                            |
| binlog_group_commit_sync_no_delay_count    | 0                            |
| binlog_gtid_simple_recovery                | ON                           |
| binlog_max_flush_queue_time                | 0                            |
| binlog_order_commits                       | ON                           |
| binlog_row_image                           | FULL                         |
| binlog_row_metadata                        | MINIMAL                      |
| binlog_row_value_options                   |                              |
| binlog_rows_query_log_events               | OFF                          |
| binlog_stmt_cache_size                     | 32768                        |
| binlog_transaction_dependency_history_size | 25000                        |
| binlog_transaction_dependency_tracking     | COMMIT_ORDER                 |
| block_encryption_mode                      | aes-128-ecb                  |
| bulk_insert_buffer_size                    | 8388608                      |

...

| max_allowed_packet                         | 67108864                     |
| max_binlog_cache_size                      | 18446744073709547520         |
| max_binlog_size                            | 1073741824                   |
| max_binlog_stmt_cache_size                 | 18446744073709547520         |
| max_connect_errors                         | 100                          |
| max_connections                            | 151                          |
| max_delayed_threads                        | 20                           |
| max_digest_length                          | 1024                         |
| max_error_count                            | 1024                         |
| max_execution_time                         | 0                            |
| max_heap_table_size                        | 16777216                     |
| max_insert_delayed_threads                 | 20                           |
| max_join_size                              | 18446744073709551615         |

...

| thread_handling                            | one-thread-per-connection    |
| thread_stack                               | 286720                       |
| time_zone                                  | SYSTEM                       |
| timestamp                                  | 1530906638.765316            |
| tls_version                                | TLSv1.2,TLSv1.3              |
| tmp_table_size                             | 16777216                     |
| tmpdir                                     | /tmp                         |
| transaction_alloc_block_size               | 8192                         |
| transaction_allow_batching                 | OFF                          |
| transaction_isolation                      | REPEATABLE-READ              |
| transaction_prealloc_size                  | 4096                         |
| transaction_read_only                      | OFF                          |
| transaction_write_set_extraction           | XXHASH64                     |
| unique_checks                              | ON                           |
| updatable_views_with_limit                 | YES                          |
| version                                    | 8.0.43                       |
| version_comment                            | MySQL Community Server - GPL |
| version_compile_machine                    | x86_64                       |
| version_compile_os                         | Linux                        |
| version_compile_zlib                       | 1.2.11                       |
| wait_timeout                               | 28800                        |
| warning_count                              | 0                            |
| windowing_use_high_precision               | ON                           |
+--------------------------------------------+------------------------------+
```

With a [`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) clause, the statement
displays only rows for those variables with names that match the
pattern. To obtain the row for a specific variable, use a
[`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) clause as shown:


``` sql

SHOW VARIABLES LIKE 'max_join_size';
SHOW SESSION VARIABLES LIKE 'max_join_size';
```

To get a list of variables whose name match a pattern, use the
`%` wildcard character in a
[`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) clause:


``` sql

SHOW VARIABLES LIKE '%size%';
SHOW GLOBAL VARIABLES LIKE '%size%';
```

Wildcard characters can be used in any position within the
pattern to be matched. Strictly speaking, because
`_` is a wildcard that matches any single
character, you should escape it as `\_` to
match it literally. In practice, this is rarely necessary.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/show-triggers.html "Previous: SHOW TRIGGERS Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/show.html "Up: SHOW Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "Next: SHOW WARNINGS Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/show-variables.html)

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