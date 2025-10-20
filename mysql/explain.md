---
url: https://dev.mysql.com/doc/refman/8.0/en/explain.html
scraped_at: 2025-10-20T03:04:13.247Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/explain.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/explain.html "Hide Sidebar")

[Previous: DESCRIBE Statement](https://dev.mysql.com/doc/refman/8.0/en/describe.html "Previous: DESCRIBE Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Utility Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-utility-statements.html "Up: Utility Statements")[Next: HELP Statement](https://dev.mysql.com/doc/refman/8.0/en/help.html "Next: HELP Statement")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/explain.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/explain.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/explain.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/explain.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/explain.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/explain.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/explain.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/explain.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/explain.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/explain.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/explain.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/explain.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/explain.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/explain.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Utility Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-utility-statements.html)  /

EXPLAIN Statement


### 15.8.2 EXPLAIN Statement

```sql
{EXPLAIN | DESCRIBE | DESC}
    tbl_name [col_name | wild]

{EXPLAIN | DESCRIBE | DESC}
    [explain_type]
    {explainable_stmt | FOR CONNECTION connection_id}

{EXPLAIN | DESCRIBE | DESC} ANALYZE [explain_type] select_stmt

explain_type: {
    FORMAT = format_name
}

format_name: {
    TRADITIONAL
  | JSON
  | TREE
}

explainable_stmt: {
    select_stmt
  | TABLE ...
  | DELETE ...
  | INSERT ...
  | REPLACE ...
  | UPDATE ...
}

select_stmt:
    SELECT ...
```

The [`DESCRIBE`](https://dev.mysql.com/doc/refman/8.0/en/describe.html "15.8.1 DESCRIBE Statement") and
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") statements are synonyms. In
practice, the [`DESCRIBE`](https://dev.mysql.com/doc/refman/8.0/en/describe.html "15.8.1 DESCRIBE Statement") keyword is
more often used to obtain information about table structure,
whereas [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") is used to obtain a
query execution plan (that is, an explanation of how MySQL would
execute a query).


The following discussion uses the
[`DESCRIBE`](https://dev.mysql.com/doc/refman/8.0/en/describe.html "15.8.1 DESCRIBE Statement") and
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") keywords in accordance with
those uses, but the MySQL parser treats them as completely
synonymous.

- [Obtaining Table Structure Information](https://dev.mysql.com/doc/refman/8.0/en/explain.html#explain-table-structure "Obtaining Table Structure Information")

- [Obtaining Execution Plan Information](https://dev.mysql.com/doc/refman/8.0/en/explain.html#explain-execution-plan "Obtaining Execution Plan Information")

- [Obtaining Information with EXPLAIN ANALYZE](https://dev.mysql.com/doc/refman/8.0/en/explain.html#explain-analyze "Obtaining Information with EXPLAIN ANALYZE")


#### Obtaining Table Structure Information

[`DESCRIBE`](https://dev.mysql.com/doc/refman/8.0/en/describe.html "15.8.1 DESCRIBE Statement") provides information
about the columns in a table:


```sql
mysql> DESCRIBE City;
+------------+----------+------+-----+---------+----------------+
| Field      | Type     | Null | Key | Default | Extra          |
+------------+----------+------+-----+---------+----------------+
| Id         | int(11)  | NO   | PRI | NULL    | auto_increment |
| Name       | char(35) | NO   |     |         |                |
| Country    | char(3)  | NO   | UNI |         |                |
| District   | char(20) | YES  | MUL |         |                |
| Population | int(11)  | NO   |     | 0       |                |
+------------+----------+------+-----+---------+----------------+
```

[`DESCRIBE`](https://dev.mysql.com/doc/refman/8.0/en/describe.html "15.8.1 DESCRIBE Statement") is a shortcut for
[`SHOW COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "15.7.7.5 SHOW COLUMNS Statement"). These statements
also display information for views. The description for
[`SHOW COLUMNS`](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "15.7.7.5 SHOW COLUMNS Statement") provides more
information about the output columns. See
[Section 15.7.7.5, “SHOW COLUMNS Statement”](https://dev.mysql.com/doc/refman/8.0/en/show-columns.html "15.7.7.5 SHOW COLUMNS Statement").


By default, [`DESCRIBE`](https://dev.mysql.com/doc/refman/8.0/en/describe.html "15.8.1 DESCRIBE Statement") displays
information about all columns in the table.
_`col_name`_, if given, is the name of a
column in the table. In this case, the statement displays
information only for the named column.
_`wild`_, if given, is a pattern string.
It can contain the SQL `%` and
`_` wildcard characters. In this case, the
statement displays output only for the columns with names
matching the string. There is no need to enclose the string
within quotation marks unless it contains spaces or other
special characters.


The [`DESCRIBE`](https://dev.mysql.com/doc/refman/8.0/en/describe.html "15.8.1 DESCRIBE Statement") statement is
provided for compatibility with Oracle.


The [`SHOW CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/show-create-table.html "15.7.7.10 SHOW CREATE TABLE Statement"),
[`SHOW TABLE STATUS`](https://dev.mysql.com/doc/refman/8.0/en/show-table-status.html "15.7.7.38 SHOW TABLE STATUS Statement"), and
[`SHOW INDEX`](https://dev.mysql.com/doc/refman/8.0/en/show-index.html "15.7.7.22 SHOW INDEX Statement") statements also
provide information about tables. See [Section 15.7.7, “SHOW Statements”](https://dev.mysql.com/doc/refman/8.0/en/show.html "15.7.7 SHOW Statements").


The [`explain_format`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_explain_format) system
variable, added in MySQL 8.0.32, has no effect on the output of
`EXPLAIN` when used to obtain information about
table columns.

#### Obtaining Execution Plan Information

The [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") statement provides
information about how MySQL executes statements:

- [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") works with
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"),
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement"),
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement"),
[`REPLACE`](https://dev.mysql.com/doc/refman/8.0/en/replace.html "15.2.12 REPLACE Statement"), and
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") statements. In MySQL
8.0.19 and later, it also works with
[`TABLE`](https://dev.mysql.com/doc/refman/8.0/en/table.html "15.2.16 TABLE Statement") statements.


- When [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") is used with an
explainable statement, MySQL displays information from the
optimizer about the statement execution plan. That is, MySQL
explains how it would process the statement, including
information about how tables are joined and in which order.
For information about using
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") to obtain execution
plan information, see [Section 10.8.2, “EXPLAIN Output Format”](https://dev.mysql.com/doc/refman/8.0/en/explain-output.html "10.8.2 EXPLAIN Output Format").


- When [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") is used with
`FOR CONNECTION
              connection_id` rather
than an explainable statement, it displays the execution
plan for the statement executing in the named connection.
See [Section 10.8.4, “Obtaining Execution Plan Information for a Named Connection”](https://dev.mysql.com/doc/refman/8.0/en/explain-for-connection.html "10.8.4 Obtaining Execution Plan Information for a Named Connection").


- For explainable statements,
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") produces additional
execution plan information that can be displayed using
[`SHOW WARNINGS`](https://dev.mysql.com/doc/refman/8.0/en/show-warnings.html "15.7.7.42 SHOW WARNINGS Statement"). See
[Section 10.8.3, “Extended EXPLAIN Output Format”](https://dev.mysql.com/doc/refman/8.0/en/explain-extended.html "10.8.3 Extended EXPLAIN Output Format").


- [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") is useful for
examining queries involving partitioned tables. See
[Section 26.3.5, “Obtaining Information About Partitions”](https://dev.mysql.com/doc/refman/8.0/en/partitioning-info.html "26.3.5 Obtaining Information About Partitions").


- The `FORMAT` option can be used to select
the output format. `TRADITIONAL` presents
the output in tabular format. This is the default if no
`FORMAT` option is present.
`JSON` format displays the information in
JSON format. In MySQL 8.0.16 and later,
`TREE` provides tree-like output with more
precise descriptions of query handling than the
`TRADITIONAL` format; it is the only format
which shows hash join usage (see
[Section 10.2.1.4, “Hash Join Optimization”](https://dev.mysql.com/doc/refman/8.0/en/hash-joins.html "10.2.1.4 Hash Join Optimization")) and is always used for
`EXPLAIN ANALYZE`.



As of MySQL 8.0.32, the default output format used by
`EXPLAIN` (that is, when it has no
`FORMAT` option) is determined by the value
of the [`explain_format`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_explain_format)
system variable. The precise effects of this variable are
described later in this section.



For complex statements, the JSON output can be quite large;
in particular, it can be difficult when reading it to pair
the closing bracket and opening brackets; to cause the JSON
structure's key, if it has one, to be repeated near the
closing bracket, set
[`end_markers_in_json=ON`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_end_markers_in_json). You
should be aware that while this makes the output easier to
read, it also renders the JSON invalid, causing JSON
functions to raise an error.


[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") requires the same
privileges required to execute the explained statement.
Additionally, [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") also
requires the [`SHOW VIEW`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_show-view) privilege
for any explained view.
[`EXPLAIN ... FOR\\
        CONNECTION`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") also requires the
[`PROCESS`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_process) privilege if the
specified connection belongs to a different user.


The [`explain_format`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_explain_format) system
variable introduced in MySQL 8.0.32 determines the format of the
output from `EXPLAIN` when used to display a
query execution plan. This variable can take any of the values
used with the `FORMAT` option, with the
addition of `DEFAULT` as a synonym for
`TRADITIONAL`. The following example uses the
`country` table from the
`world` database which can be obtained from
[MySQL: Other\\
Downloads](https://dev.mysql.com/doc/index-other.html):


```sql
mysql> USE world; # Make world the current database
Database changed
```

Checking the value of `explain_format`, we see
that it has the default value, and that
`EXPLAIN` (with no `FORMAT`
option) therefore uses the traditional tabular output:


```sql
mysql> SELECT @@explain_format;
+------------------+
| @@explain_format |
+------------------+
| TRADITIONAL      |
+------------------+
1 row in set (0.00 sec)

mysql> EXPLAIN SELECT Name FROM country WHERE Code Like 'A%';
+----+-------------+---------+------------+-------+---------------+---------+---------+------+------+----------+-------------+
| id | select_type | table   | partitions | type  | possible_keys | key     | key_len | ref  | rows | filtered | Extra       |
+----+-------------+---------+------------+-------+---------------+---------+---------+------+------+----------+-------------+
|  1 | SIMPLE      | country | NULL       | range | PRIMARY       | PRIMARY | 12      | NULL |   17 |   100.00 | Using where |
+----+-------------+---------+------------+-------+---------------+---------+---------+------+------+----------+-------------+
1 row in set, 1 warning (0.00 sec)
```

If we set the value of `explain_format` to
`TREE`, then rerun the same
`EXPLAIN` statement, the output uses the
tree-like format:


```sql
mysql> SET @@explain_format=TREE;
Query OK, 0 rows affected (0.00 sec)

mysql> SELECT @@explain_format;
+------------------+
| @@explain_format |
+------------------+
| TREE             |
+------------------+
1 row in set (0.00 sec)

mysql> EXPLAIN SELECT Name FROM country WHERE Code LIKE 'A%';
+--------------------------------------------------------------------------------------------------------------+
| EXPLAIN                                                                                                      |
+--------------------------------------------------------------------------------------------------------------+
| -> Filter: (country.`Code` like 'A%')  (cost=3.67 rows=17)
    -> Index range scan on country using PRIMARY over ('A' <= Code <= 'A????????')  (cost=3.67 rows=17)  |
+--------------------------------------------------------------------------------------------------------------+
1 row in set, 1 warning (0.00 sec)
```

As stated previously, the `FORMAT` option
overrides this setting. Executing the same
`EXPLAIN` statement using
`FORMAT=JSON` instead of
`FORMAT=TREE` shows that this is the case:


```sql
mysql> EXPLAIN FORMAT=JSON SELECT Name FROM country WHERE Code LIKE 'A%';
+------------------------------------------------------------------------------+
| EXPLAIN                                                                      |
+------------------------------------------------------------------------------+
| {
  "query_block": {
    "select_id": 1,
    "cost_info": {
      "query_cost": "3.67"
    },
    "table": {
      "table_name": "country",
      "access_type": "range",
      "possible_keys": [\
        "PRIMARY"\
      ],
      "key": "PRIMARY",
      "used_key_parts": [\
        "Code"\
      ],
      "key_length": "12",
      "rows_examined_per_scan": 17,
      "rows_produced_per_join": 17,
      "filtered": "100.00",
      "cost_info": {
        "read_cost": "1.97",
        "eval_cost": "1.70",
        "prefix_cost": "3.67",
        "data_read_per_join": "16K"
      },
      "used_columns": [\
        "Code",\
        "Name"\
      ],
      "attached_condition": "(`world`.`country`.`Code` like 'A%')"
    }
  }
}                                                                              |
+------------------------------------------------------------------------------+
1 row in set, 1 warning (0.00 sec)
```

To return the default output of `EXPLAIN` to
the tabular format, set `explain_format` to
`TRADITIONAL`. Alternatively, you can set it to
`DEFAULT`, which has the same effect, as shown
here:


```sql
mysql> SET @@explain_format=DEFAULT;
Query OK, 0 rows affected (0.00 sec)

mysql> SELECT @@explain_format;
+------------------+
| @@explain_format |
+------------------+
| TRADITIONAL      |
+------------------+
1 row in set (0.00 sec)
```

With the help of [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement"), you can
see where you should add indexes to tables so that the statement
executes faster by using indexes to find rows. You can also use
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") to check whether the
optimizer joins the tables in an optimal order. To give a hint
to the optimizer to use a join order corresponding to the order
in which the tables are named in a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement, begin the
statement with `SELECT STRAIGHT_JOIN` rather
than just [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement"). (See
[Section 15.2.13, “SELECT Statement”](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement").)


The optimizer trace may sometimes provide information
complementary to that of [`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement").
However, the optimizer trace format and content are subject to
change between versions. For details, see
[Section 10.15, “Tracing the Optimizer”](https://dev.mysql.com/doc/refman/8.0/en/optimizer-tracing.html "10.15 Tracing the Optimizer").


If you have a problem with indexes not being used when you
believe that they should be, run [`ANALYZE\\
        TABLE`](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement") to update table statistics, such as cardinality
of keys, that can affect the choices the optimizer makes. See
[Section 15.7.3.1, “ANALYZE TABLE Statement”](https://dev.mysql.com/doc/refman/8.0/en/analyze-table.html "15.7.3.1 ANALYZE TABLE Statement").

Note

MySQL Workbench has a Visual Explain capability that provides a
visual representation of
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html "15.8.2 EXPLAIN Statement") output. See
[Tutorial: Using Explain to Improve Query Performance](https://dev.mysql.com/doc/workbench/en/wb-tutorial-visual-explain-dbt3.html).

#### Obtaining Information with EXPLAIN ANALYZE

MySQL 8.0.18 introduces `EXPLAIN ANALYZE`,
which runs a statement and produces
[`EXPLAIN`](https://dev.mysql.com/doc/refman/8.0/en/explain.html#explain-execution-plan "Obtaining Execution Plan Information")
output along with timing and additional, iterator-based,
information about how the optimizer's expectations matched
the actual execution. For each iterator, the following
information is provided:

- Estimated execution cost



(Some iterators are not accounted for by the cost model, and
so are not included in the estimate.)


- Estimated number of returned rows


- Time to return first row


- Time spent executing this iterator (including child
iterators, but not parent iterators), in milliseconds.



(When there are multiple loops, this figure shows the
average time per loop.)


- Number of rows returned by the iterator


- Number of loops


The query execution information is displayed using the
`TREE` output format, in which nodes represent
iterators. `EXPLAIN ANALYZE` always uses the
`TREE` output format. In MySQL 8.0.21 and
later, this can optionally be specified explicitly using
`FORMAT=TREE`; formats other than
`TREE` remain unsupported.


`EXPLAIN ANALYZE` can be used with
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statements, as well as
with multi-table [`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") and
[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") statements. Beginning with
MySQL 8.0.19, it can also be used with
[`TABLE`](https://dev.mysql.com/doc/refman/8.0/en/table.html "15.2.16 TABLE Statement") statements.


Beginning with MySQL 8.0.20, you can terminate this statement
using [`KILL QUERY`](https://dev.mysql.com/doc/refman/8.0/en/kill.html "15.7.8.4 KILL Statement")
or **CTRL-C**.


`EXPLAIN ANALYZE` cannot be used with
`FOR CONNECTION`.


Example output:


```sql
mysql> EXPLAIN ANALYZE SELECT * FROM t1 JOIN t2 ON (t1.c1 = t2.c2)\G
*************************** 1. row ***************************
EXPLAIN: -> Inner hash join (t2.c2 = t1.c1)  (cost=4.70 rows=6)
(actual time=0.032..0.035 rows=6 loops=1)
    -> Table scan on t2  (cost=0.06 rows=6)
(actual time=0.003..0.005 rows=6 loops=1)
    -> Hash
        -> Table scan on t1  (cost=0.85 rows=6)
(actual time=0.018..0.022 rows=6 loops=1)

mysql> EXPLAIN ANALYZE SELECT * FROM t3 WHERE i > 8\G
*************************** 1. row ***************************
EXPLAIN: -> Filter: (t3.i > 8)  (cost=1.75 rows=5)
(actual time=0.019..0.021 rows=6 loops=1)
    -> Table scan on t3  (cost=1.75 rows=15)
(actual time=0.017..0.019 rows=15 loops=1)

mysql> EXPLAIN ANALYZE SELECT * FROM t3 WHERE pk > 17\G
*************************** 1. row ***************************
EXPLAIN: -> Filter: (t3.pk > 17)  (cost=1.26 rows=5)
(actual time=0.013..0.016 rows=5 loops=1)
    -> Index range scan on t3 using PRIMARY  (cost=1.26 rows=5)
(actual time=0.012..0.014 rows=5 loops=1)
```

The tables used in the example output were created by the
statements shown here:


```sql
CREATE TABLE t1 (
    c1 INTEGER DEFAULT NULL,
    c2 INTEGER DEFAULT NULL
);

CREATE TABLE t2 (
    c1 INTEGER DEFAULT NULL,
    c2 INTEGER DEFAULT NULL
);

CREATE TABLE t3 (
    pk INTEGER NOT NULL PRIMARY KEY,
    i INTEGER DEFAULT NULL
);
```

Values shown for `actual time` in the output of
this statement are expressed in milliseconds.


As of MySQL 8.0.32, the
[`explain_format`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_explain_format) system variable
has the following effects on `EXPLAIN ANALYZE`:

- If the value of this variable is
`TRADITIONAL` or `TREE`
(or the synonym `DEFAULT`),
`EXPLAIN ANALYZE` uses the
`TREE` format. This ensures that this
statement continues to use the `TREE`
format by default, as it did prior to the introduction of
`explain_format`.


- If the value of `explain_format` is
`JSON`, `EXPLAIN ANALYZE`
returns an error unless `FORMAT=TREE` is
specified as part of the statement. This is due to the fact
that `EXPLAIN ANALYZE` supports only the
`TREE` output format.


We illustrate the behavior described in the second point here,
re-using the last `EXPLAIN ANALYZE` statement
from the previous example:


```sql
mysql> SET @@explain_format=JSON;
Query OK, 0 rows affected (0.00 sec)

mysql> SELECT @@explain_format;
+------------------+
| @@explain_format |
+------------------+
| JSON             |
+------------------+
1 row in set (0.00 sec)

mysql> EXPLAIN ANALYZE SELECT * FROM t3 WHERE pk > 17\G
ERROR 1235 (42000): This version of MySQL doesn't yet support 'EXPLAIN ANALYZE with JSON format'

mysql> EXPLAIN ANALYZE FORMAT=TRADITIONAL SELECT * FROM t3 WHERE pk > 17\G
ERROR 1235 (42000): This version of MySQL doesn't yet support 'EXPLAIN ANALYZE with TRADITIONAL format'

mysql> EXPLAIN ANALYZE FORMAT=TREE SELECT * FROM t3 WHERE pk > 17\G
*************************** 1. row ***************************
EXPLAIN: -> Filter: (t3.pk > 17)  (cost=1.26 rows=5)
(actual time=0.013..0.016 rows=5 loops=1)
    -> Index range scan on t3 using PRIMARY  (cost=1.26 rows=5)
(actual time=0.012..0.014 rows=5 loops=1)
```

Using `FORMAT=TRADITIONAL` or
`FORMAT=JSON` with `EXPLAIN
        ANALYZE` always raises an error, regardless of the
value of `explain_format`.


Beginning with MySQL 8.0.33, numbers in the output of
`EXPLAIN ANALYZE` and `EXPLAIN
        FORMAT=TREE` are formatted according to the following
rules:

- Numbers in the range 0.001-999999.5 are printed as decimal
numbers.



Decimal numbers less than 1000 have three significant
digits; the remainder have four, five, or six.


- Numbers outside the range 0.001-999999.5 are printed in
engineering format. Examples of such values are
`1.23e+9` and `934e-6`.


- No trailing zeros are printed. For example, we print
`2.3` rather than `2.30`,
and `1.2e+6` rather than
`1.20e+6`.


- Numbers less than `1e-12` are printed as
`0`.


[PREV](https://dev.mysql.com/doc/refman/8.0/en/describe.html "Previous: DESCRIBE Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-utility-statements.html "Up: Utility Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/help.html "Next: HELP Statement")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/explain.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/explain.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/explain.html)

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