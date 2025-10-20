---
url: https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html
scraped_at: 2025-10-20T03:13:48.953Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html "Hide Sidebar")

[Previous: The Optimizer Cost Model](https://dev.mysql.com/doc/refman/8.0/en/cost-model.html "Previous: The Optimizer Cost Model")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Controlling the Query Optimizer](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html "Up: Controlling the Query Optimizer")[Next: Buffering and Caching](https://dev.mysql.com/doc/refman/8.0/en/buffering-caching.html "Next: Buffering and Caching")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/optimizer-statistics.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/optimizer-statistics.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/optimizer-statistics.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/optimizer-statistics.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/optimizer-statistics.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/optimizer-statistics.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/optimizer-statistics.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html)  / [Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
[Controlling the Query Optimizer](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html)  /

Optimizer Statistics


### 10.9.6 Optimizer Statistics

The `column_statistics` data dictionary table
stores histogram statistics about column values, for use by the
optimizer in constructing query execution plans. To perform
histogram management, use the [`ANALYZE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") statement.


The `column_statistics` table has these
characteristics:

- The table contains statistics for columns of all data types
except geometry types (spatial data) and
[`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type").


- The table is persistent so that column statistics need not
be created each time the server starts.


- The server performs updates to the table; users do not.


The `column_statistics` table is not directly
accessible by users because it is part of the data dictionary.
Histogram information is available using
[`INFORMATION_SCHEMA.COLUMN_STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-column-statistics-table.html "28.3.11 The INFORMATION_SCHEMA COLUMN_STATISTICS Table"),
which is implemented as a view on the data dictionary table.
[`COLUMN_STATISTICS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-column-statistics-table.html "28.3.11 The INFORMATION_SCHEMA COLUMN_STATISTICS Table") has these
columns:

- `SCHEMA_NAME`,
`TABLE_NAME`,
`COLUMN_NAME`: The names of the schema,
table, and column for which the statistics apply.


- `HISTOGRAM`: A
[`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type") value describing the
column statistics, stored as a histogram.


Column histograms contain buckets for parts of the range of
values stored in the column. Histograms are
[`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type") objects to permit
flexibility in the representation of column statistics. Here is
a sample histogram object:


```json
{
  "buckets": [\
    [\
      1,\
      0.3333333333333333\
    ],\
    [\
      2,\
      0.6666666666666666\
    ],\
    [\
      3,\
      1\
    ]\
  ],
  "null-values": 0,
  "last-updated": "2017-03-24 13:32:40.000000",
  "sampling-rate": 1,
  "histogram-type": "singleton",
  "number-of-buckets-specified": 128,
  "data-type": "int",
  "collation-id": 8
}
```

Histogram objects have these keys:

- `buckets`: The histogram buckets. Bucket
structure depends on the histogram type.



For `singleton` histograms, buckets contain
two values:




- Value 1: The value for the bucket. The type depends on
the column data type.


- Value 2: A double representing the cumulative frequency
for the value. For example, .25 and .75 indicate that
25% and 75% of the values in the column are less than or
equal to the bucket value.


For `equi-height` histograms, buckets
contain four values:

- Values 1, 2: The lower and upper inclusive values for
the bucket. The type depends on the column data type.


- Value 3: A double representing the cumulative frequency
for the value. For example, .25 and .75 indicate that
25% and 75% of the values in the column are less than or
equal to the bucket upper value.


- Value 4: The number of distinct values in the range from
the bucket lower value to its upper value.


- `null-values`: A number between 0.0 and 1.0
indicating the fraction of column values that are SQL
`NULL` values. If 0, the column contains no
`NULL` values.


- `last-updated`: When the histogram was
generated, as a UTC value in _`YYYY-MM-DD_
_hh:mm:ss.uuuuuu`_ format.


- `sampling-rate`: A number between 0.0 and
1.0 indicating the fraction of data that was sampled to
create the histogram. A value of 1 means that all of the
data was read (no sampling).


- `histogram-type`: The histogram type:




- `singleton`: One bucket represents one
single value in the column. This histogram type is
created when the number of distinct values in the column
is less than or equal to the number of buckets specified
in the [`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement")
statement that generated the histogram.


- `equi-height`: One bucket represents a
range of values. This histogram type is created when the
number of distinct values in the column is greater than
the number of buckets specified in the
[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") statement
that generated the histogram.


- `number-of-buckets-specified`: The number
of buckets specified in the [`ANALYZE\\
              TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") statement that generated the histogram.


- `data-type`: The type of data this
histogram contains. This is needed when reading and parsing
histograms from persistent storage into memory. The value is
one of `int`, `uint`
(unsigned integer), `double`,
`decimal`, `datetime`, or
`string` (includes character and binary
strings).


- `collation-id`: The collation ID for the
histogram data. It is mostly meaningful when the
`data-type` value is
`string`. Values correspond to
`ID` column values in the Information
Schema [`COLLATIONS`](https://dev.mysql.com/doc/refman/8.0/en/information-schema-collations-table.html "28.3.6 The INFORMATION_SCHEMA COLLATIONS Table") table.


To extract particular values from the histogram objects, you can
use [`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type") operations. For example:


```sql
mysql> SELECT
         TABLE_NAME, COLUMN_NAME,
         HISTOGRAM->>'$."data-type"' AS 'data-type',
         JSON_LENGTH(HISTOGRAM->>'$."buckets"') AS 'bucket-count'
       FROM INFORMATION_SCHEMA.COLUMN_STATISTICS;
+-----------------+-------------+-----------+--------------+
| TABLE_NAME      | COLUMN_NAME | data-type | bucket-count |
+-----------------+-------------+-----------+--------------+
| country         | Population  | int       |          226 |
| city            | Population  | int       |         1024 |
| countrylanguage | Language    | string    |          457 |
+-----------------+-------------+-----------+--------------+
```

The optimizer uses histogram statistics, if applicable, for
columns of any data type for which statistics are collected. The
optimizer applies histogram statistics to determine row
estimates based on the selectivity (filtering effect) of column
value comparisons against constant values. Predicates of these
forms qualify for histogram use:


```sql
col_name = constant
col_name <> constant
col_name != constant
col_name > constant
col_name < constant
col_name >= constant
col_name <= constant
col_name IS NULL
col_name IS NOT NULL
col_name BETWEEN constant AND constant
col_name NOT BETWEEN constant AND constant
col_name IN (constant[, constant] ...)
col_name NOT IN (constant[, constant] ...)
```

For example, these statements contain predicates that qualify
for histogram use:


```sql
SELECT * FROM orders WHERE amount BETWEEN 100.0 AND 300.0;
SELECT * FROM tbl WHERE col1 = 15 AND col2 > 100;
```

The requirement for comparison against a constant value includes
functions that are constant, such as
[`ABS()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_abs) and
[`FLOOR()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_floor):


```sql
SELECT * FROM tbl WHERE col1 < ABS(-34);
```

Histogram statistics are useful primarily for nonindexed
columns. Adding an index to a column for which histogram
statistics are applicable might also help the optimizer make row
estimates. The tradeoffs are:

- An index must be updated when table data is modified.


- A histogram is created or updated only on demand, so it adds
no overhead when table data is modified. On the other hand,
the statistics become progressively more out of date when
table modifications occur, until the next time they are
updated.


The optimizer prefers range optimizer row estimates to those
obtained from histogram statistics. If the optimizer determines
that the range optimizer applies, it does not use histogram
statistics.


For columns that are indexed, row estimates can be obtained for
equality comparisons using index dives (see
[Section 10.2.1.2, “Range Optimization”](https://dev.mysql.com/doc/refman/8.0/en/range-optimization.html "10.2.1.2 Range Optimization")). In this case, histogram
statistics are not necessarily useful because index dives can
yield better estimates.


In some cases, use of histogram statistics may not improve query
execution (for example, if the statistics are out of date). To
check whether this is the case, use [`ANALYZE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") to regenerate the histogram statistics, then run
the query again.


Alternatively, to disable histogram statistics, use
[`ANALYZE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") to drop them. A
different method of disabling histogram statistics is to turn
off the
[`condition_fanout_filter`](https://dev.mysql.com/doc/refman/8.0/en/switchable-optimizations.html#optflag_condition-fanout-filter) flag
of the [`optimizer_switch`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_optimizer_switch) system
variable (although this may disable other optimizations as
well):


```sql
SET optimizer_switch='condition_fanout_filter=off';
```

If histogram statistics are used, the resulting effect is
visible using [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement"). Consider
the following query, where no index is available for column
`col1`:


```sql
SELECT * FROM t1 WHERE col1 < 24;
```

If histogram statistics indicate that 57% of the rows in
`t1` satisfy the `col1 <
        24` predicate, filtering can occur even in the absence
of an index, and [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") shows
57.00 in the `filtered` column.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/cost-model.html "Previous: The Optimizer Cost Model") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/controlling-optimizer.html "Up: Controlling the Query Optimizer") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/buffering-caching.html "Next: Buffering and Caching")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimizer-statistics.html)

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