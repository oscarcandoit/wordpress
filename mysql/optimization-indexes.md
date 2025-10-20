---
url: https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html
scraped_at: 2025-10-20T02:59:10.961Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Hide Sidebar")

[Previous: Other Optimization Tips](https://dev.mysql.com/doc/refman/8.0/en/miscellaneous-optimization-tips.html "Previous: Other Optimization Tips")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html "Up: Optimization")[Next: How MySQL Uses Indexes](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html "Next: How MySQL Uses Indexes")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/optimization-indexes.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/optimization-indexes.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/optimization-indexes.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/optimization-indexes.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/optimization-indexes.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/optimization-indexes.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/optimization-indexes.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/optimization-indexes.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Optimization](https://dev.mysql.com/doc/refman/8.0/en/optimization.html)  /
Optimization and Indexes


## 10.3 Optimization and Indexes

[10.3.1 How MySQL Uses Indexes](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html)[10.3.2 Primary Key Optimization](https://dev.mysql.com/doc/refman/8.0/en/primary-key-optimization.html)[10.3.3 SPATIAL Index Optimization](https://dev.mysql.com/doc/refman/8.0/en/spatial-index-optimization.html)[10.3.4 Foreign Key Optimization](https://dev.mysql.com/doc/refman/8.0/en/foreign-key-optimization.html)[10.3.5 Column Indexes](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html)[10.3.6 Multiple-Column Indexes](https://dev.mysql.com/doc/refman/8.0/en/multiple-column-indexes.html)[10.3.7 Verifying Index Usage](https://dev.mysql.com/doc/refman/8.0/en/verifying-index-usage.html)[10.3.8 InnoDB and MyISAM Index Statistics Collection](https://dev.mysql.com/doc/refman/8.0/en/index-statistics.html)[10.3.9 Comparison of B-Tree and Hash Indexes](https://dev.mysql.com/doc/refman/8.0/en/index-btree-hash.html)[10.3.10 Use of Index Extensions](https://dev.mysql.com/doc/refman/8.0/en/index-extensions.html)[10.3.11 Optimizer Use of Generated Column Indexes](https://dev.mysql.com/doc/refman/8.0/en/generated-column-index-optimizations.html)[10.3.12 Invisible Indexes](https://dev.mysql.com/doc/refman/8.0/en/invisible-indexes.html)[10.3.13 Descending Indexes](https://dev.mysql.com/doc/refman/8.0/en/descending-indexes.html)[10.3.14 Indexed Lookups from TIMESTAMP Columns](https://dev.mysql.com/doc/refman/8.0/en/timestamp-lookups.html)

The best way to improve the performance of
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") operations is to create
indexes on one or more of the columns that are tested in the
query. The index entries act like pointers to the table rows,
allowing the query to quickly determine which rows match a
condition in the `WHERE` clause, and retrieve the
other column values for those rows. All MySQL data types can be
indexed.


Although it can be tempting to create an indexes for every
possible column used in a query, unnecessary indexes waste space
and waste time for MySQL to determine which indexes to use.
Indexes also add to the cost of inserts, updates, and deletes
because each index must be updated. You must find the right
balance to achieve fast queries using the optimal set of indexes.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/miscellaneous-optimization-tips.html "Previous: Other Optimization Tips") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/optimization.html "Up: Optimization") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html "Next: How MySQL Uses Indexes")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)

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