---
url: https://dev.mysql.com/doc/refman/8.0/en/json-functions.html
scraped_at: 2025-10-20T03:02:02.515Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/json-functions.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/json-functions.html "Hide Sidebar")

[Previous: Spatial Convenience Functions](https://dev.mysql.com/doc/refman/8.0/en/spatial-convenience-functions.html "Previous: Spatial Convenience Functions")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html "Up: Functions and Operators")[Next: JSON Function Reference](https://dev.mysql.com/doc/refman/8.0/en/json-function-reference.html "Next: JSON Function Reference")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/json-functions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/json-functions.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/json-functions.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/json-functions.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/json-functions.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/json-functions.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/json-functions.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/json-functions.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/json-functions.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/json-functions.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/json-functions.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/json-functions.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/json-functions.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html)  /
JSON Functions


## 14.17 JSON Functions

[14.17.1 JSON Function Reference](https://dev.mysql.com/doc/refman/8.0/en/json-function-reference.html)[14.17.2 Functions That Create JSON Values](https://dev.mysql.com/doc/refman/8.0/en/json-creation-functions.html)[14.17.3 Functions That Search JSON Values](https://dev.mysql.com/doc/refman/8.0/en/json-search-functions.html)[14.17.4 Functions That Modify JSON Values](https://dev.mysql.com/doc/refman/8.0/en/json-modification-functions.html)[14.17.5 Functions That Return JSON Value Attributes](https://dev.mysql.com/doc/refman/8.0/en/json-attribute-functions.html)[14.17.6 JSON Table Functions](https://dev.mysql.com/doc/refman/8.0/en/json-table-functions.html)[14.17.7 JSON Schema Validation Functions](https://dev.mysql.com/doc/refman/8.0/en/json-validation-functions.html)[14.17.8 JSON Utility Functions](https://dev.mysql.com/doc/refman/8.0/en/json-utility-functions.html)

The functions described in this section perform operations on JSON
values. For discussion of the [`JSON`](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type")
data type and additional examples showing how to use these
functions, see [Section 13.5, “The JSON Data Type”](https://dev.mysql.com/doc/refman/8.0/en/json.html "13.5 The JSON Data Type").


For functions that take a JSON argument, an error occurs if the
argument is not a valid JSON value. Arguments parsed as JSON are
indicated by _`json_doc`_; arguments
indicated by _`val`_ are not parsed.


Functions that return JSON values always perform normalization of
these values (see [Normalization, Merging, and Autowrapping of JSON Values](https://dev.mysql.com/doc/refman/8.0/en/json.html#json-normalization "Normalization, Merging, and Autowrapping of JSON Values")), and thus
orders them. _The precise outcome of the sort is subject to_
_change at any time; do not rely on it to be consistent between_
_releases_.


A set of spatial functions for operating on GeoJSON values is also
available. See [Section 14.16.11, “Spatial GeoJSON Functions”](https://dev.mysql.com/doc/refman/8.0/en/spatial-geojson-functions.html "14.16.11 Spatial GeoJSON Functions").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/spatial-convenience-functions.html "Previous: Spatial Convenience Functions") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/functions.html "Up: Functions and Operators") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/json-function-reference.html "Next: JSON Function Reference")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/json-functions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/json-functions.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/json-functions.html)

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