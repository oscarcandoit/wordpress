---
url: https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html
scraped_at: 2025-10-20T02:59:36.525Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html "Hide Sidebar")

[Previous: Out-of-Range and Overflow Handling](https://dev.mysql.com/doc/refman/8.0/en/out-of-range-and-overflow.html "Previous: Out-of-Range and Overflow Handling")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Types](https://dev.mysql.com/doc/refman/8.0/en/data-types.html "Up: Data Types")[Next: Date and Time Data Type Syntax](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-type-syntax.html "Next: Date and Time Data Type Syntax")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/date-and-time-types.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/date-and-time-types.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/date-and-time-types.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/date-and-time-types.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/date-and-time-types.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/date-and-time-types.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/date-and-time-types.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/date-and-time-types.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Data Types](https://dev.mysql.com/doc/refman/8.0/en/data-types.html)  /
Date and Time Data Types


## 13.2 Date and Time Data Types

[13.2.1 Date and Time Data Type Syntax](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-type-syntax.html)[13.2.2 The DATE, DATETIME, and TIMESTAMP Types](https://dev.mysql.com/doc/refman/8.0/en/datetime.html)[13.2.3 The TIME Type](https://dev.mysql.com/doc/refman/8.0/en/time.html)[13.2.4 The YEAR Type](https://dev.mysql.com/doc/refman/8.0/en/year.html)[13.2.5 Automatic Initialization and Updating for TIMESTAMP and DATETIME](https://dev.mysql.com/doc/refman/8.0/en/timestamp-initialization.html)[13.2.6 Fractional Seconds in Time Values](https://dev.mysql.com/doc/refman/8.0/en/fractional-seconds.html)[13.2.7 What Calendar Is Used By MySQL?](https://dev.mysql.com/doc/refman/8.0/en/mysql-calendar.html)[13.2.8 Conversion Between Date and Time Types](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-type-conversion.html)[13.2.9 2-Digit Years in Dates](https://dev.mysql.com/doc/refman/8.0/en/two-digit-years.html)

The date and time data types for representing temporal values are
[`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"),
[`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type"),
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"),
[`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"), and
[`YEAR`](https://dev.mysql.com/doc/refman/8.0/en/year.html "13.2.4 The YEAR Type"). Each temporal type has a
range of valid values, as well as a “zero” value that
may be used when you specify an invalid value that MySQL cannot
represent. The [`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") and
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") types have special
automatic updating behavior, described in
[Section 13.2.5, “Automatic Initialization and Updating for TIMESTAMP and DATETIME”](https://dev.mysql.com/doc/refman/8.0/en/timestamp-initialization.html "13.2.5 Automatic Initialization and Updating for TIMESTAMP and DATETIME").


For information about storage requirements of the temporal data
types, see [Section 13.7, “Data Type Storage Requirements”](https://dev.mysql.com/doc/refman/8.0/en/storage-requirements.html "13.7 Data Type Storage Requirements").


For descriptions of functions that operate on temporal values, see
[Section 14.7, “Date and Time Functions”](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html "14.7 Date and Time Functions").


Keep in mind these general considerations when working with date
and time types:

- MySQL retrieves values for a given date or time type in a
standard output format, but it attempts to interpret a variety
of formats for input values that you supply (for example, when
you specify a value to be assigned to or compared to a date or
time type). For a description of the permitted formats for
date and time types, see
[Section 11.1.3, “Date and Time Literals”](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-literals.html "11.1.3 Date and Time Literals"). It is expected that
you supply valid values. Unpredictable results may occur if
you use values in other formats.


- Although MySQL tries to interpret values in several formats,
date parts must always be given in year-month-day order (for
example, `'98-09-04'`), rather than in the
month-day-year or day-month-year orders commonly used
elsewhere (for example, `'09-04-98'`,
`'04-09-98'`). To convert strings in other
orders to year-month-day order, the
[`STR_TO_DATE()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_str-to-date) function may be
useful.


- Dates containing 2-digit year values are ambiguous because the
century is unknown. MySQL interprets 2-digit year values using
these rules:




- Year values in the range `70-99` become
`1970-1999`.


- Year values in the range `00-69` become
`2000-2069`.


See also [Section 13.2.9, “2-Digit Years in Dates”](https://dev.mysql.com/doc/refman/8.0/en/two-digit-years.html "13.2.9 2-Digit Years in Dates").


- Conversion of values from one temporal type to another occurs
according to the rules in
[Section 13.2.8, “Conversion Between Date and Time Types”](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-type-conversion.html "13.2.8 Conversion Between Date and Time Types").


- MySQL automatically converts a date or time value to a number
if the value is used in numeric context and vice versa.


- By default, when MySQL encounters a value for a date or time
type that is out of range or otherwise invalid for the type,
it converts the value to the “zero” value for
that type. The exception is that out-of-range
[`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type") values are clipped to the
appropriate endpoint of the
[`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type") range.


- By setting the SQL mode to the appropriate value, you can
specify more exactly what kind of dates you want MySQL to
support. (See [Section 7.1.11, “Server SQL Modes”](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html "7.1.11 Server SQL Modes").) You can get MySQL
to accept certain dates, such as
`'2009-11-31'`, by enabling the
[`ALLOW_INVALID_DATES`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_allow_invalid_dates) SQL
mode. This is useful when you want to store a “possibly
wrong” value which the user has specified (for example,
in a web form) in the database for future processing. Under
this mode, MySQL verifies only that the month is in the range
from 1 to 12 and that the day is in the range from 1 to 31.


- MySQL permits you to store dates where the day or month and
day are zero in a [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") or
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") column. This is useful
for applications that need to store birthdates for which you
may not know the exact date. In this case, you simply store
the date as `'2009-00-00'` or
`'2009-01-00'`. However, with dates such as
these, you should not expect to get correct results for
functions such as [`DATE_SUB()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_date-sub) or
[`DATE_ADD()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_date-add) that require
complete dates. To disallow zero month or day parts in dates,
enable the [`NO_ZERO_IN_DATE`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_no_zero_in_date)
mode.


- MySQL permits you to store a “zero” value of
`'0000-00-00'` as a “dummy
date.” In some cases, this is more convenient than
using `NULL` values, and uses less data and
index space. To disallow `'0000-00-00'`,
enable the [`NO_ZERO_DATE`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_no_zero_date)
mode.


- “Zero” date or time values used through
Connector/ODBC are converted automatically to
`NULL` because ODBC cannot handle such
values.


The following table shows the format of the “zero”
value for each type. The “zero” values are special,
but you can store or refer to them explicitly using the values
shown in the table. You can also do this using the values
`'0'` or `0`, which are easier
to write. For temporal types that include a date part
( [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"),
[`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types"), and
[`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types")), use of these values may
produce warning or errors. The precise behavior depends on which,
if any, of the strict and
[`NO_ZERO_DATE`](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html#sqlmode_no_zero_date) SQL modes are
enabled; see [Section 7.1.11, “Server SQL Modes”](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html "7.1.11 Server SQL Modes").

| Data Type | “Zero” Value |
| --- | --- |
| [`DATE`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") | `'0000-00-00'` |
| [`TIME`](https://dev.mysql.com/doc/refman/8.0/en/time.html "13.2.3 The TIME Type") | `'00:00:00'` |
| [`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") | `'0000-00-00 00:00:00'` |
| [`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "13.2.2 The DATE, DATETIME, and TIMESTAMP Types") | `'0000-00-00 00:00:00'` |
| [`YEAR`](https://dev.mysql.com/doc/refman/8.0/en/year.html "13.2.4 The YEAR Type") | `0000` |

[PREV](https://dev.mysql.com/doc/refman/8.0/en/out-of-range-and-overflow.html "Previous: Out-of-Range and Overflow Handling") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/data-types.html "Up: Data Types") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-type-syntax.html "Next: Date and Time Data Type Syntax")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html)

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