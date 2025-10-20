---
url: https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html
scraped_at: 2025-10-20T03:13:19.373Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html "Hide Sidebar")

[Previous: Comparison of B-Tree and Hash Indexes](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html "Previous: Comparison of B-Tree and Hash Indexes")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes")[Next: Optimizer Use of Generated Column Indexes](https://dev.mysql.com/doc/refman/8.0/en/generated-column-index-optimizations.html "Next: Optimizer Use of Generated Column Indexes")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/index-extensions.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/index-extensions.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/index-extensions.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/index-extensions.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/index-extensions.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/index-extensions.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/index-extensions.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/index-extensions.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Optimization and Indexes](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)  /

Use of Index Extensions


### 10.3.10 Use of Index Extensions

[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") automatically extends each
secondary index by appending the primary key columns to it.
Consider this table definition:


```sql
CREATE TABLE t1 (
  i1 INT NOT NULL DEFAULT 0,
  i2 INT NOT NULL DEFAULT 0,
  d DATE DEFAULT NULL,
  PRIMARY KEY (i1, i2),
  INDEX k_d (d)
) ENGINE = InnoDB;
```

This table defines the primary key on columns `(i1,
        i2)`. It also defines a secondary index
`k_d` on column `(d)`, but
internally `InnoDB` extends this index and
treats it as columns `(d, i1, i2)`.


The optimizer takes into account the primary key columns of the
extended secondary index when determining how and whether to use
that index. This can result in more efficient query execution
plans and better performance.


The optimizer can use extended secondary indexes for
`ref`, `range`, and
[`index_merge`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_index-merge) index access, for
Loose Index Scan access, for join and sorting optimization, and
for
[`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min)/ [`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max)
optimization.


The following example shows how execution plans are affected by
whether the optimizer uses extended secondary indexes. Suppose
that `t1` is populated with these rows:


```sql
INSERT INTO t1 VALUES
(1, 1, '1998-01-01'), (1, 2, '1999-01-01'),
(1, 3, '2000-01-01'), (1, 4, '2001-01-01'),
(1, 5, '2002-01-01'), (2, 1, '1998-01-01'),
(2, 2, '1999-01-01'), (2, 3, '2000-01-01'),
(2, 4, '2001-01-01'), (2, 5, '2002-01-01'),
(3, 1, '1998-01-01'), (3, 2, '1999-01-01'),
(3, 3, '2000-01-01'), (3, 4, '2001-01-01'),
(3, 5, '2002-01-01'), (4, 1, '1998-01-01'),
(4, 2, '1999-01-01'), (4, 3, '2000-01-01'),
(4, 4, '2001-01-01'), (4, 5, '2002-01-01'),
(5, 1, '1998-01-01'), (5, 2, '1999-01-01'),
(5, 3, '2000-01-01'), (5, 4, '2001-01-01'),
(5, 5, '2002-01-01');
```

Now consider this query:


```sql
EXPLAIN SELECT COUNT(*) FROM t1 WHERE i1 = 3 AND d = '2000-01-01'
```

The execution plan depends on whether the extended index is
used.


When the optimizer does not consider index extensions, it treats
the index `k_d` as only `(d)`.
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") for the query produces
this result:


```sql
mysql> EXPLAIN SELECT COUNT(*) FROM t1 WHERE i1 = 3 AND d = '2000-01-01'\G
*************************** 1. row ***************************
           id: 1
  select_type: SIMPLE
        table: t1
         type: ref
possible_keys: PRIMARY,k_d
          key: k_d
      key_len: 4
          ref: const
         rows: 5
        Extra: Using where; Using index
```

When the optimizer takes index extensions into account, it
treats `k_d` as `(d, i1, i2)`.
In this case, it can use the leftmost index prefix `(d,
        i1)` to produce a better execution plan:


```sql
mysql> EXPLAIN SELECT COUNT(*) FROM t1 WHERE i1 = 3 AND d = '2000-01-01'\G
*************************** 1. row ***************************
           id: 1
  select_type: SIMPLE
        table: t1
         type: ref
possible_keys: PRIMARY,k_d
          key: k_d
      key_len: 8
          ref: const,const
         rows: 1
        Extra: Using index
```

In both cases, `key` indicates that the
optimizer uses secondary index `k_d` but the
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") output shows these
improvements from using the extended index:

- `key_len` goes from 4 bytes to 8 bytes,
indicating that key lookups use columns `d`
and `i1`, not just `d`.


- The `ref` value changes from
`const` to `const,const`
because the key lookup uses two key parts, not one.


- The `rows` count decreases from 5 to 1,
indicating that `InnoDB` should need to
examine fewer rows to produce the result.


- The `Extra` value changes from
`Using where; Using index` to
`Using index`. This means that rows can be
read using only the index, without consulting columns in the
data row.


Differences in optimizer behavior for use of extended indexes
can also be seen with [`SHOW\\
        STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-status.html "15.7.7.37 SHOW STATUS Statement"):


```sql
FLUSH TABLE t1;
FLUSH STATUS;
SELECT COUNT(*) FROM t1 WHERE i1 = 3 AND d = '2000-01-01';
SHOW STATUS LIKE 'handler_read%'
```

The preceding statements include [`FLUSH\\
        TABLES`](https://dev.mysql.com/doc/refman/8.0/en/flush.html#flush-tables) and [`FLUSH STATUS`](https://dev.mysql.com/doc/refman/8.0/en/flush.html#flush-status)
to flush the table cache and clear the status counters.


Without index extensions, [`SHOW\\
        STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-status.html "15.7.7.37 SHOW STATUS Statement") produces this result:


```none
+-----------------------+-------+
| Variable_name         | Value |
+-----------------------+-------+
| Handler_read_first    | 0     |
| Handler_read_key      | 1     |
| Handler_read_last     | 0     |
| Handler_read_next     | 5     |
| Handler_read_prev     | 0     |
| Handler_read_rnd      | 0     |
| Handler_read_rnd_next | 0     |
+-----------------------+-------+
```

With index extensions, [`SHOW\\
        STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-status.html "15.7.7.37 SHOW STATUS Statement") produces this result. The
[`Handler_read_next`](https://dev.mysql.com/doc/refman/8.0/en/server-status-variables.html#statvar_Handler_read_next) value
decreases from 5 to 1, indicating more efficient use of the
index:


```none
+-----------------------+-------+
| Variable_name         | Value |
+-----------------------+-------+
| Handler_read_first    | 0     |
| Handler_read_key      | 1     |
| Handler_read_last     | 0     |
| Handler_read_next     | 1     |
| Handler_read_prev     | 0     |
| Handler_read_rnd      | 0     |
| Handler_read_rnd_next | 0     |
+-----------------------+-------+
```

The [`use_index_extensions`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_use-index-extensions) flag
of the [`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) system
variable permits control over whether the optimizer takes the
primary key columns into account when determining how to use an
`InnoDB` table's secondary indexes. By
default, [`use_index_extensions`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_use-index-extensions)
is enabled. To check whether disabling use of index extensions
can improve performance, use this statement:


```sql
SET optimizer_switch = 'use_index_extensions=off';
```

Use of index extensions by the optimizer is subject to the usual
limits on the number of key parts in an index (16) and the
maximum key length (3072 bytes).

[PREV](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html "Previous: Comparison of B-Tree and Hash Indexes") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Up: Optimization and Indexes") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/generated-column-index-optimizations.html "Next: Optimizer Use of Generated Column Indexes")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html)

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