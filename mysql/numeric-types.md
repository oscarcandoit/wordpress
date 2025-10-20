---
url: https://dev.mysql.com/doc/refman/8.0/en/numeric-types.html
scraped_at: 2025-10-20T02:59:29.357Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/numeric-types.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/numeric-types.html "Hide Sidebar")

[Previous: Data Types](https://dev.mysql.com/doc/refman/8.0/en/data-types.html "Previous: Data Types")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Types](https://dev.mysql.com/doc/refman/8.0/en/data-types.html "Up: Data Types")[Next: Numeric Data Type Syntax](https://dev.mysql.com/doc/refman/8.0/en/numeric-type-syntax.html "Next: Numeric Data Type Syntax")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/numeric-types.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/numeric-types.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/numeric-types.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/numeric-types.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/numeric-types.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/numeric-types.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/numeric-types.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/numeric-types.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/numeric-types.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/numeric-types.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/numeric-types.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/numeric-types.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/numeric-types.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Data Types](https://dev.mysql.com/doc/refman/8.0/en/data-types.html)  /
Numeric Data Types


## 13.1 Numeric Data Types

[13.1.1 Numeric Data Type Syntax](https://dev.mysql.com/doc/refman/8.0/en/numeric-type-syntax.html)[13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT,\\
MEDIUMINT, BIGINT](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html)[13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html)[13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html)[13.1.5 Bit-Value Type - BIT](https://dev.mysql.com/doc/refman/8.0/en/bit-type.html)[13.1.6 Numeric Type Attributes](https://dev.mysql.com/doc/refman/8.0/en/numeric-type-attributes.html)[13.1.7 Out-of-Range and Overflow Handling](https://dev.mysql.com/doc/refman/8.0/en/out-of-range-and-overflow.html)

MySQL supports all standard SQL numeric data types. These types
include the exact numeric data types
( [`INTEGER`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT"),
[`SMALLINT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT"),
[`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC"), and
[`NUMERIC`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC")), as well as the
approximate numeric data types
( [`FLOAT`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE"),
[`REAL`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE"), and
[`DOUBLE PRECISION`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE")). The keyword
[`INT`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT") is a synonym for
[`INTEGER`](https://dev.mysql.com/doc/refman/8.0/en/integer-types.html "13.1.2 Integer Types (Exact Value) - INTEGER, INT, SMALLINT, TINYINT, MEDIUMINT, BIGINT"), and the keywords
[`DEC`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC") and
[`FIXED`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC") are synonyms for
[`DECIMAL`](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html "13.1.3 Fixed-Point Types (Exact Value) - DECIMAL, NUMERIC"). MySQL treats
[`DOUBLE`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE") as a synonym for
[`DOUBLE PRECISION`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE") (a nonstandard
extension). MySQL also treats [`REAL`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE")
as a synonym for [`DOUBLE PRECISION`](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html "13.1.4 Floating-Point Types (Approximate Value) - FLOAT, DOUBLE")
(a nonstandard variation), unless the
[`REAL_AS_FLOAT`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_real_as_float) SQL mode is
enabled.


The [`BIT`](https://dev.mysql.com/doc/refman/8.0/en/bit-type.html "13.1.5 Bit-Value Type - BIT") data type stores bit values
and is supported for [`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine"),
[`MEMORY`](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html "18.3 The MEMORY Storage Engine"),
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine"), and
[`NDB`](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster.html "Chapter 25 MySQL NDB Cluster 8.0") tables.


For information about how MySQL handles assignment of out-of-range
values to columns and overflow during expression evaluation, see
[Section 13.1.7, “Out-of-Range and Overflow Handling”](https://dev.mysql.com/doc/refman/8.0/en/out-of-range-and-overflow.html "13.1.7 Out-of-Range and Overflow Handling").


For information about storage requirements of the numeric data
types, see [Section 13.7, “Data Type Storage Requirements”](https://dev.mysql.com/doc/refman/8.0/en/storage-requirements.html "13.7 Data Type Storage Requirements").


For descriptions of functions that operate on numeric values, see
[Section 14.6, “Numeric Functions and Operators”](https://dev.mysql.com/doc/refman/8.0/en/numeric-functions.html "14.6 Numeric Functions and Operators"). The data type used for the
result of a calculation on numeric operands depends on the types
of the operands and the operations performed on them. For more
information, see [Section 14.6.1, “Arithmetic Operators”](https://dev.mysql.com/doc/refman/8.0/en/arithmetic-functions.html "14.6.1 Arithmetic Operators").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/data-types.html "Previous: Data Types") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/data-types.html "Up: Data Types") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/numeric-type-syntax.html "Next: Numeric Data Type Syntax")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/numeric-types.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/numeric-types.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/numeric-types.html)

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