---
url: https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html
scraped_at: 2025-10-20T03:03:12.761Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html "Hide Sidebar")

[Previous: The MEMORY Storage Engine](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html "Previous: The MEMORY Storage Engine")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Alternative Storage Engines](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html "Up: Alternative Storage Engines")[Next: Repairing and Checking CSV Tables](https://dev.mysql.com/doc/refman/8.0/en/se-csv-repair.html "Next: Repairing and Checking CSV Tables")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/csv-storage-engine.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/csv-storage-engine.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/csv-storage-engine.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/csv-storage-engine.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/csv-storage-engine.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/csv-storage-engine.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/csv-storage-engine.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/csv-storage-engine.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Alternative Storage Engines](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html)  /
The CSV Storage Engine


## 18.4 The CSV Storage Engine

[18.4.1 Repairing and Checking CSV Tables](https://dev.mysql.com/doc/refman/8.0/en/se-csv-repair.html)[18.4.2 CSV Limitations](https://dev.mysql.com/doc/refman/8.0/en/se-csv-limitations.html)

The `CSV` storage engine stores data in text files
using comma-separated values format.


The `CSV` storage engine is always compiled into
the MySQL server.


To examine the source for the `CSV` engine, look in
the `storage/csv` directory of a MySQL source
distribution.


When you create a `CSV` table, the server creates a
plain text data file having a name that begins with the table name
and has a `.CSV` extension. When you store data
into the table, the storage engine saves it into the data file in
comma-separated values format.


```sql
mysql> CREATE TABLE test (i INT NOT NULL, c CHAR(10) NOT NULL)
       ENGINE = CSV;
Query OK, 0 rows affected (0.06 sec)

mysql> INSERT INTO test VALUES(1,'record one'),(2,'record two');
Query OK, 2 rows affected (0.05 sec)
Records: 2  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM test;
+---+------------+
| i | c          |
+---+------------+
| 1 | record one |
| 2 | record two |
+---+------------+
2 rows in set (0.00 sec)
```

Creating a `CSV` table also creates a corresponding
metafile that stores the state of the table and the number of rows
that exist in the table. The name of this file is the same as the
name of the table with the extension `CSM`.


If you examine the `test.CSV` file in the
database directory created by executing the preceding statements,
its contents should look like this:


```none
"1","record one"
"2","record two"
```

This format can be read, and even written, by spreadsheet
applications such as Microsoft Excel.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/memory-storage-engine.html "Previous: The MEMORY Storage Engine") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html "Up: Alternative Storage Engines") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/se-csv-repair.html "Next: Repairing and Checking CSV Tables")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html)

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