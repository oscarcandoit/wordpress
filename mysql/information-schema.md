---
url: https://dev.mysql.com/doc/refman/8.0/en/information-schema.html
scraped_at: 2025-10-20T03:07:12.588Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html "Hide Sidebar")

[Previous: Restrictions on Views](https://dev.mysql.com/doc/refman/8.0/en/view-restrictions.html "Previous: Restrictions on Views")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up")[Next: Introduction](https://dev.mysql.com/doc/refman/8.0/en/information-schema-introduction.html "Next: Introduction")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/information-schema.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/information-schema.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/information-schema.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/information-schema.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/information-schema.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/information-schema.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/information-schema.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/information-schema.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
INFORMATION\_SCHEMA Tables


# Chapter 28 INFORMATION\_SCHEMA Tables

**Table of Contents**

[28.1 Introduction](https://dev.mysql.com/doc/refman/8.0/en/information-schema-introduction.html)[28.2 INFORMATION\_SCHEMA Table Reference](https://dev.mysql.com/doc/refman/8.0/en/information-schema-table-reference.html)[28.3 INFORMATION\_SCHEMA General Tables](https://dev.mysql.com/doc/refman/8.0/en/general-information-schema-tables.html)[28.3.1 INFORMATION\_SCHEMA General Table Reference](https://dev.mysql.com/doc/refman/8.0/en/information-schema-general-table-reference.html)[28.3.2 The INFORMATION\_SCHEMA ADMINISTRABLE\_ROLE\_AUTHORIZATIONS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-administrable-role-authorizations-table.html)[28.3.3 The INFORMATION\_SCHEMA APPLICABLE\_ROLES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-applicable-roles-table.html)[28.3.4 The INFORMATION\_SCHEMA CHARACTER\_SETS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-character-sets-table.html)[28.3.5 The INFORMATION\_SCHEMA CHECK\_CONSTRAINTS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-check-constraints-table.html)[28.3.6 The INFORMATION\_SCHEMA COLLATIONS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-collations-table.html)[28.3.7 The INFORMATION\_SCHEMA COLLATION\_CHARACTER\_SET\_APPLICABILITY Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-collation-character-set-applicability-table.html)[28.3.8 The INFORMATION\_SCHEMA COLUMNS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-table.html)[28.3.9 The INFORMATION\_SCHEMA COLUMNS\_EXTENSIONS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-columns-extensions-table.html)[28.3.10 The INFORMATION\_SCHEMA COLUMN\_PRIVILEGES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-column-privileges-table.html)[28.3.11 The INFORMATION\_SCHEMA COLUMN\_STATISTICS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-column-statistics-table.html)[28.3.12 The INFORMATION\_SCHEMA ENABLED\_ROLES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-enabled-roles-table.html)[28.3.13 The INFORMATION\_SCHEMA ENGINES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-engines-table.html)[28.3.14 The INFORMATION\_SCHEMA EVENTS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-events-table.html)[28.3.15 The INFORMATION\_SCHEMA FILES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-files-table.html)[28.3.16 The INFORMATION\_SCHEMA KEY\_COLUMN\_USAGE Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-key-column-usage-table.html)[28.3.17 The INFORMATION\_SCHEMA KEYWORDS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-keywords-table.html)[28.3.18 The INFORMATION\_SCHEMA ndb\_transid\_mysql\_connection\_map Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-ndb-transid-mysql-connection-map-table.html)[28.3.19 The INFORMATION\_SCHEMA OPTIMIZER\_TRACE Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-optimizer-trace-table.html)[28.3.20 The INFORMATION\_SCHEMA PARAMETERS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-parameters-table.html)[28.3.21 The INFORMATION\_SCHEMA PARTITIONS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-partitions-table.html)[28.3.22 The INFORMATION\_SCHEMA PLUGINS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-plugins-table.html)[28.3.23 The INFORMATION\_SCHEMA PROCESSLIST Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-processlist-table.html)[28.3.24 The INFORMATION\_SCHEMA PROFILING Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-profiling-table.html)[28.3.25 The INFORMATION\_SCHEMA REFERENTIAL\_CONSTRAINTS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-referential-constraints-table.html)[28.3.26 The INFORMATION\_SCHEMA RESOURCE\_GROUPS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-resource-groups-table.html)[28.3.27 The INFORMATION\_SCHEMA ROLE\_COLUMN\_GRANTS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-role-column-grants-table.html)[28.3.28 The INFORMATION\_SCHEMA ROLE\_ROUTINE\_GRANTS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-role-routine-grants-table.html)[28.3.29 The INFORMATION\_SCHEMA ROLE\_TABLE\_GRANTS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-role-table-grants-table.html)[28.3.30 The INFORMATION\_SCHEMA ROUTINES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-routines-table.html)[28.3.31 The INFORMATION\_SCHEMA SCHEMATA Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-schemata-table.html)[28.3.32 The INFORMATION\_SCHEMA SCHEMATA\_EXTENSIONS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-schemata-extensions-table.html)[28.3.33 The INFORMATION\_SCHEMA SCHEMA\_PRIVILEGES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-schema-privileges-table.html)[28.3.34 The INFORMATION\_SCHEMA STATISTICS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-statistics-table.html)[28.3.35 The INFORMATION\_SCHEMA ST\_GEOMETRY\_COLUMNS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-st-geometry-columns-table.html)[28.3.36 The INFORMATION\_SCHEMA ST\_SPATIAL\_REFERENCE\_SYSTEMS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-st-spatial-reference-systems-table.html)[28.3.37 The INFORMATION\_SCHEMA ST\_UNITS\_OF\_MEASURE Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-st-units-of-measure-table.html)[28.3.38 The INFORMATION\_SCHEMA TABLES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-table.html)[28.3.39 The INFORMATION\_SCHEMA TABLES\_EXTENSIONS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tables-extensions-table.html)[28.3.40 The INFORMATION\_SCHEMA TABLESPACES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tablespaces-table.html)[28.3.41 The INFORMATION\_SCHEMA TABLESPACES\_EXTENSIONS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tablespaces-extensions-table.html)[28.3.42 The INFORMATION\_SCHEMA TABLE\_CONSTRAINTS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-table-constraints-table.html)[28.3.43 The INFORMATION\_SCHEMA TABLE\_CONSTRAINTS\_EXTENSIONS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-table-constraints-extensions-table.html)[28.3.44 The INFORMATION\_SCHEMA TABLE\_PRIVILEGES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-table-privileges-table.html)[28.3.45 The INFORMATION\_SCHEMA TRIGGERS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-triggers-table.html)[28.3.46 The INFORMATION\_SCHEMA USER\_ATTRIBUTES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-user-attributes-table.html)[28.3.47 The INFORMATION\_SCHEMA USER\_PRIVILEGES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-user-privileges-table.html)[28.3.48 The INFORMATION\_SCHEMA VIEWS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-views-table.html)[28.3.49 The INFORMATION\_SCHEMA VIEW\_ROUTINE\_USAGE Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-view-routine-usage-table.html)[28.3.50 The INFORMATION\_SCHEMA VIEW\_TABLE\_USAGE Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-view-table-usage-table.html)[28.4 INFORMATION\_SCHEMA InnoDB Tables](https://dev.mysql.com/doc/refman/8.0/en/innodb-information-schema-tables.html)[28.4.1 INFORMATION\_SCHEMA InnoDB Table Reference](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-table-reference.html)[28.4.2 The INFORMATION\_SCHEMA INNODB\_BUFFER\_PAGE Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-buffer-page-table.html)[28.4.3 The INFORMATION\_SCHEMA INNODB\_BUFFER\_PAGE\_LRU Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-buffer-page-lru-table.html)[28.4.4 The INFORMATION\_SCHEMA INNODB\_BUFFER\_POOL\_STATS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-buffer-pool-stats-table.html)[28.4.5 The INFORMATION\_SCHEMA INNODB\_CACHED\_INDEXES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-cached-indexes-table.html)[28.4.6 The INFORMATION\_SCHEMA INNODB\_CMP and INNODB\_CMP\_RESET Tables](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-cmp-table.html)[28.4.7 The INFORMATION\_SCHEMA INNODB\_CMPMEM and INNODB\_CMPMEM\_RESET Tables](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-cmpmem-table.html)[28.4.8 The INFORMATION\_SCHEMA INNODB\_CMP\_PER\_INDEX and\\
INNODB\_CMP\_PER\_INDEX\_RESET Tables](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-cmp-per-index-table.html)[28.4.9 The INFORMATION\_SCHEMA INNODB\_COLUMNS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-columns-table.html)[28.4.10 The INFORMATION\_SCHEMA INNODB\_DATAFILES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-datafiles-table.html)[28.4.11 The INFORMATION\_SCHEMA INNODB\_FIELDS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-fields-table.html)[28.4.12 The INFORMATION\_SCHEMA INNODB\_FOREIGN Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-foreign-table.html)[28.4.13 The INFORMATION\_SCHEMA INNODB\_FOREIGN\_COLS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-foreign-cols-table.html)[28.4.14 The INFORMATION\_SCHEMA INNODB\_FT\_BEING\_DELETED Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-ft-being-deleted-table.html)[28.4.15 The INFORMATION\_SCHEMA INNODB\_FT\_CONFIG Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-ft-config-table.html)[28.4.16 The INFORMATION\_SCHEMA INNODB\_FT\_DEFAULT\_STOPWORD Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-ft-default-stopword-table.html)[28.4.17 The INFORMATION\_SCHEMA INNODB\_FT\_DELETED Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-ft-deleted-table.html)[28.4.18 The INFORMATION\_SCHEMA INNODB\_FT\_INDEX\_CACHE Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-ft-index-cache-table.html)[28.4.19 The INFORMATION\_SCHEMA INNODB\_FT\_INDEX\_TABLE Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-ft-index-table-table.html)[28.4.20 The INFORMATION\_SCHEMA INNODB\_INDEXES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-indexes-table.html)[28.4.21 The INFORMATION\_SCHEMA INNODB\_METRICS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-metrics-table.html)[28.4.22 The INFORMATION\_SCHEMA INNODB\_SESSION\_TEMP\_TABLESPACES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-session-temp-tablespaces-table.html)[28.4.23 The INFORMATION\_SCHEMA INNODB\_TABLES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-tables-table.html)[28.4.24 The INFORMATION\_SCHEMA INNODB\_TABLESPACES Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-tablespaces-table.html)[28.4.25 The INFORMATION\_SCHEMA INNODB\_TABLESPACES\_BRIEF Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-tablespaces-brief-table.html)[28.4.26 The INFORMATION\_SCHEMA INNODB\_TABLESTATS View](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-tablestats-table.html)[28.4.27 The INFORMATION\_SCHEMA INNODB\_TEMP\_TABLE\_INFO Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-temp-table-info-table.html)[28.4.28 The INFORMATION\_SCHEMA INNODB\_TRX Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-trx-table.html)[28.4.29 The INFORMATION\_SCHEMA INNODB\_VIRTUAL Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-innodb-virtual-table.html)[28.5 INFORMATION\_SCHEMA Thread Pool Tables](https://dev.mysql.com/doc/refman/8.0/en/thread-pool-information-schema-tables.html)[28.5.1 INFORMATION\_SCHEMA Thread Pool Table Reference](https://dev.mysql.com/doc/refman/8.0/en/information-schema-thread-pool-table-reference.html)[28.5.2 The INFORMATION\_SCHEMA TP\_THREAD\_GROUP\_STATE Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tp-thread-group-state-table.html)[28.5.3 The INFORMATION\_SCHEMA TP\_THREAD\_GROUP\_STATS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tp-thread-group-stats-table.html)[28.5.4 The INFORMATION\_SCHEMA TP\_THREAD\_STATE Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-tp-thread-state-table.html)[28.6 INFORMATION\_SCHEMA Connection Control Tables](https://dev.mysql.com/doc/refman/8.0/en/connection-control-information-schema-tables.html)[28.6.1 INFORMATION\_SCHEMA Connection Control Table Reference](https://dev.mysql.com/doc/refman/8.0/en/information-schema-connection-control-table-reference.html)[28.6.2 The INFORMATION\_SCHEMA CONNECTION\_CONTROL\_FAILED\_LOGIN\_ATTEMPTS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-connection-control-failed-login-attempts-table.html)[28.7 INFORMATION\_SCHEMA MySQL Enterprise Firewall Tables](https://dev.mysql.com/doc/refman/8.0/en/firewall-information-schema-tables.html)[28.7.1 INFORMATION\_SCHEMA Firewall Table Reference](https://dev.mysql.com/doc/refman/8.0/en/information-schema-firewall-table-reference.html)[28.7.2 The INFORMATION\_SCHEMA MYSQL\_FIREWALL\_USERS Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-mysql-firewall-users-table.html)[28.7.3 The INFORMATION\_SCHEMA MYSQL\_FIREWALL\_WHITELIST Table](https://dev.mysql.com/doc/refman/8.0/en/information-schema-mysql-firewall-whitelist-table.html)[28.8 Extensions to SHOW Statements](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html)

`INFORMATION_SCHEMA` provides access to database
metadata, information about
the MySQL server such as the name of a database or table, the data
type of a column, or access privileges. Other terms that are
sometimes used for this information are
data dictionary and
system catalog.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/view-restrictions.html "Previous: Restrictions on Views") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/index.html "Up") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/information-schema-introduction.html "Next: Introduction")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)

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