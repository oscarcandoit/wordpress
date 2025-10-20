---
url: https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html
scraped_at: 2025-10-20T03:13:06.895Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html "Hide Sidebar")

[Previous: Optimizer Use of Generated Column Indexes](https://dev.mysql.com/doc/refman/8.0/en/generated-column-index-optimizations.html "Previous: Optimizer Use of Generated Column Indexes")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes")[Next: Descending Indexes](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html "Next: Descending Indexes")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/invisible-indexes.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/invisible-indexes.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/invisible-indexes.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/invisible-indexes.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/invisible-indexes.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/invisible-indexes.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/invisible-indexes.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)  /

Invisible Indexes


### 10.3.12 Invisible Indexes

MySQL supports invisible indexes; that is, indexes that are not
used by the optimizer. The feature applies to indexes other than
primary keys (either explicit or implicit).


Indexes are visible by default. To control visibility explicitly
for a new index, use a `VISIBLE` or
`INVISIBLE` keyword as part of the index
definition for [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement"),
[`CREATE INDEX`](https://dev.mysql.com/doc/refman/8.0/en/create-index.html "15.1.15 CREATE INDEX Statement"), or
[`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement"):


```sql
CREATE TABLE t1 (
  i INT,
  j INT,
  k INT,
  INDEX i_idx (i) INVISIBLE
) ENGINE = InnoDB;
CREATE INDEX j_idx ON t1 (j) INVISIBLE;
ALTER TABLE t1 ADD INDEX k_idx (k) INVISIBLE;
```

To alter the visibility of an existing index, use a
`VISIBLE` or `INVISIBLE`
keyword with the `ALTER TABLE ... ALTER INDEX`
operation:


```sql
ALTER TABLE t1 ALTER INDEX i_idx INVISIBLE;
ALTER TABLE t1 ALTER INDEX i_idx VISIBLE;
```

Information about whether an index is visible or invisible is
available from the Information Schema
[`STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html "28.3.34 The INFORMATION_SCHEMA STATISTICS Table") table or
[`SHOW INDEX`](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "15.7.7.22 SHOW INDEX Statement") output. For example:


```sql
mysql> SELECT INDEX_NAME, IS_VISIBLE
       FROM INFORMATION_SCHEMA.STATISTICS
       WHERE TABLE_SCHEMA = 'db1' AND TABLE_NAME = 't1';
+------------+------------+
| INDEX_NAME | IS_VISIBLE |
+------------+------------+
| i_idx      | YES        |
| j_idx      | NO         |
| k_idx      | NO         |
+------------+------------+
```

Invisible indexes make it possible to test the effect of
removing an index on query performance, without making a
destructive change that must be undone should the index turn out
to be required. Dropping and re-adding an index can be expensive
for a large table, whereas making it invisible and visible are
fast, in-place operations.


If an index made invisible actually is needed or used by the
optimizer, there are several ways to notice the effect of its
absence on queries for the table:

- Errors occur for queries that include index hints that refer
to the invisible index.


- Performance Schema data shows an increase in workload for
affected queries.


- Queries have different
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") execution plans.


- Queries appear in the slow query log that did not appear
there previously.


The [`use_invisible_indexes`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_use-invisible-indexes) flag
of the [`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) system
variable controls whether the optimizer uses invisible indexes
for query execution plan construction. If the flag is
`off` (the default), the optimizer ignores
invisible indexes (the same behavior as prior to the
introduction of this flag). If the flag is
`on`, invisible indexes remain invisible but
the optimizer takes them into account for execution plan
construction.


Using the [`SET_VAR`](https://dev.mysql.com/doc/refman/8.0/en/optimizer-hints.html#optimizer-hints-set-var "Variable-Setting Hint Syntax") optimizer
hint to update the value of
[`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) temporarily,
you can enable invisible indexes for the duration of a single
query only, like this:


```sql
mysql> EXPLAIN SELECT /*+ SET_VAR(optimizer_switch = 'use_invisible_indexes=on') */
     >     i, j FROM t1 WHERE j >= 50\G
*************************** 1. row ***************************
           id: 1
  select_type: SIMPLE
        table: t1
   partitions: NULL
         type: range
possible_keys: j_idx
          key: j_idx
      key_len: 5
          ref: NULL
         rows: 2
     filtered: 100.00
        Extra: Using index condition

mysql> EXPLAIN SELECT i, j FROM t1 WHERE j >= 50\G
*************************** 1. row ***************************
           id: 1
  select_type: SIMPLE
        table: t1
   partitions: NULL
         type: ALL
possible_keys: NULL
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 5
     filtered: 33.33
        Extra: Using where
```

Index visibility does not affect index maintenance. For example,
an index continues to be updated per changes to table rows, and
a unique index prevents insertion of duplicates into a column,
regardless of whether the index is visible or invisible.


A table with no explicit primary key may still have an effective
implicit primary key if it has any `UNIQUE`
indexes on `NOT NULL` columns. In this case,
the first such index places the same constraint on table rows as
an explicit primary key and that index cannot be made invisible.
Consider the following table definition:


```sql
CREATE TABLE t2 (
  i INT NOT NULL,
  j INT NOT NULL,
  UNIQUE j_idx (j)
) ENGINE = InnoDB;
```

The definition includes no explicit primary key, but the index
on `NOT NULL` column `j`
places the same constraint on rows as a primary key and cannot
be made invisible:


```sql
mysql> ALTER TABLE t2 ALTER INDEX j_idx INVISIBLE;
ERROR 3522 (HY000): A primary key index cannot be invisible.
```

Now suppose that an explicit primary key is added to the table:


```sql
ALTER TABLE t2 ADD PRIMARY KEY (i);
```

The explicit primary key cannot be made invisible. In addition,
the unique index on `j` no longer acts as an
implicit primary key and as a result can be made invisible:


```sql
mysql> ALTER TABLE t2 ALTER INDEX j_idx INVISIBLE;
Query OK, 0 rows affected (0.03 sec)
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/generated-column-index-optimizations.html "Previous: Optimizer Use of Generated Column Indexes") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html "Next: Descending Indexes")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html)

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