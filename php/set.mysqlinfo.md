---
url: https://www.php.net/manual/en/set.mysqlinfo.php
scraped_at: 2025-10-20T02:36:05.563Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# MySQL Drivers and Plugins [¶](https://www.php.net/manual/en/set.mysqlinfo.php\#set.mysqlinfo)

PHP offers several MySQL drivers and plugins for accessing and
handling MySQL.


The differences and functionality of the MySQL extensions are described
within the overview of this section.


The extensions listed support the MySQL protocol.
Examples of compatible database servers are
[» MariaDB Server](http://www.mariadb.org/),
[» MySQL Server](http://www.mysql.com/),
[» Percona Server for MySQL](https://www.percona.com/mysql/software/percona-server-for-mysql),
and
[» TiDB](https://www.pingcap.com/tidb/).


- [Overview of the MySQL PHP drivers](https://www.php.net/manual/en/mysql.php)
  - [Introduction](https://www.php.net/manual/en/mysqlinfo.intro.php)
  - [Terminology overview](https://www.php.net/manual/en/mysqlinfo.terminology.php)
  - [Choosing an API](https://www.php.net/manual/en/mysqlinfo.api.choosing.php)
  - [Choosing a library](https://www.php.net/manual/en/mysqlinfo.library.choosing.php)
  - [Concepts](https://www.php.net/manual/en/mysqlinfo.concepts.php)
- [MySQLi](https://www.php.net/manual/en/book.mysqli.php) — MySQL Improved Extension
  - [Introduction](https://www.php.net/manual/en/intro.mysqli.php)
  - [Overview](https://www.php.net/manual/en/mysqli.overview.php)
  - [Quick start guide](https://www.php.net/manual/en/mysqli.quickstart.php)
  - [Installing/Configuring](https://www.php.net/manual/en/mysqli.setup.php)
  - [The mysqli Extension and Persistent Connections](https://www.php.net/manual/en/mysqli.persistconns.php)
  - [Predefined Constants](https://www.php.net/manual/en/mysqli.constants.php)
  - [Notes](https://www.php.net/manual/en/mysqli.notes.php)
  - [The MySQLi Extension Function Summary](https://www.php.net/manual/en/mysqli.summary.php)
  - [mysqli](https://www.php.net/manual/en/class.mysqli.php) — The mysqli class
  - [mysqli\_stmt](https://www.php.net/manual/en/class.mysqli-stmt.php) — The mysqli\_stmt class
  - [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) — The mysqli\_result class
  - [mysqli\_driver](https://www.php.net/manual/en/class.mysqli-driver.php) — The mysqli\_driver class
  - [mysqli\_warning](https://www.php.net/manual/en/class.mysqli-warning.php) — The mysqli\_warning class
  - [mysqli\_sql\_exception](https://www.php.net/manual/en/class.mysqli-sql-exception.php) — The mysqli\_sql\_exception class
  - [Aliases and deprecated Mysqli Functions](https://www.php.net/manual/en/ref.mysqli.php)
  - [Changelog](https://www.php.net/manual/en/changelog.mysqli.php)
- [Mysql\_xdevapi](https://www.php.net/manual/en/book.mysql-xdevapi.php)
  - [Introduction](https://www.php.net/manual/en/intro.mysql-xdevapi.php)
  - [Installing/Configuring](https://www.php.net/manual/en/mysql-xdevapi.setup.php)
  - [Predefined Constants](https://www.php.net/manual/en/mysql-xdevapi.constants.php)
  - [Changelog](https://www.php.net/manual/en/changelog.mysql_xdevapi.php)
  - [Examples](https://www.php.net/manual/en/mysql-xdevapi.examples.php)
  - [Mysql\_xdevapi Functions](https://www.php.net/manual/en/ref.mysql-xdevapi.php)
  - [mysql\_xdevapi\\BaseResult](https://www.php.net/manual/en/class.mysql-xdevapi-baseresult.php) — BaseResult interface
  - [mysql\_xdevapi\\Client](https://www.php.net/manual/en/class.mysql-xdevapi-client.php) — Client class
  - [mysql\_xdevapi\\Collection](https://www.php.net/manual/en/class.mysql-xdevapi-collection.php) — Collection class
  - [mysql\_xdevapi\\CollectionAdd](https://www.php.net/manual/en/class.mysql-xdevapi-collectionadd.php) — CollectionAdd class
  - [mysql\_xdevapi\\CollectionFind](https://www.php.net/manual/en/class.mysql-xdevapi-collectionfind.php) — CollectionFind class
  - [mysql\_xdevapi\\CollectionModify](https://www.php.net/manual/en/class.mysql-xdevapi-collectionmodify.php) — CollectionModify class
  - [mysql\_xdevapi\\CollectionRemove](https://www.php.net/manual/en/class.mysql-xdevapi-collectionremove.php) — CollectionRemove class
  - [mysql\_xdevapi\\ColumnResult](https://www.php.net/manual/en/class.mysql-xdevapi-columnresult.php) — ColumnResult class
  - [mysql\_xdevapi\\CrudOperationBindable](https://www.php.net/manual/en/class.mysql-xdevapi-crudoperationbindable.php) — CrudOperationBindable interface
  - [mysql\_xdevapi\\CrudOperationLimitable](https://www.php.net/manual/en/class.mysql-xdevapi-crudoperationlimitable.php) — CrudOperationLimitable interface
  - [mysql\_xdevapi\\CrudOperationSkippable](https://www.php.net/manual/en/class.mysql-xdevapi-crudoperationskippable.php) — CrudOperationSkippable interface
  - [mysql\_xdevapi\\CrudOperationSortable](https://www.php.net/manual/en/class.mysql-xdevapi-crudoperationsortable.php) — CrudOperationSortable interface
  - [mysql\_xdevapi\\DatabaseObject](https://www.php.net/manual/en/class.mysql-xdevapi-databaseobject.php) — DatabaseObject interface
  - [mysql\_xdevapi\\DocResult](https://www.php.net/manual/en/class.mysql-xdevapi-docresult.php) — DocResult class
  - [mysql\_xdevapi\\Exception](https://www.php.net/manual/en/class.mysql-xdevapi-exception.php) — Exception class
  - [mysql\_xdevapi\\Executable](https://www.php.net/manual/en/class.mysql-xdevapi-executable.php) — Executable interface
  - [mysql\_xdevapi\\ExecutionStatus](https://www.php.net/manual/en/class.mysql-xdevapi-executionstatus.php) — ExecutionStatus class
  - [mysql\_xdevapi\\Expression](https://www.php.net/manual/en/class.mysql-xdevapi-expression.php) — Expression class
  - [mysql\_xdevapi\\Result](https://www.php.net/manual/en/class.mysql-xdevapi-result.php) — Result class
  - [mysql\_xdevapi\\RowResult](https://www.php.net/manual/en/class.mysql-xdevapi-rowresult.php) — RowResult class
  - [mysql\_xdevapi\\Schema](https://www.php.net/manual/en/class.mysql-xdevapi-schema.php) — Schema class
  - [mysql\_xdevapi\\SchemaObject](https://www.php.net/manual/en/class.mysql-xdevapi-schemaobject.php) — SchemaObject interface
  - [mysql\_xdevapi\\Session](https://www.php.net/manual/en/class.mysql-xdevapi-session.php) — Session class
  - [mysql\_xdevapi\\SqlStatement](https://www.php.net/manual/en/class.mysql-xdevapi-sqlstatement.php) — SqlStatement class
  - [mysql\_xdevapi\\SqlStatementResult](https://www.php.net/manual/en/class.mysql-xdevapi-sqlstatementresult.php) — SqlStatementResult class
  - [mysql\_xdevapi\\Statement](https://www.php.net/manual/en/class.mysql-xdevapi-statement.php) — Statement class
  - [mysql\_xdevapi\\Table](https://www.php.net/manual/en/class.mysql-xdevapi-table.php) — Table class
  - [mysql\_xdevapi\\TableDelete](https://www.php.net/manual/en/class.mysql-xdevapi-tabledelete.php) — TableDelete class
  - [mysql\_xdevapi\\TableInsert](https://www.php.net/manual/en/class.mysql-xdevapi-tableinsert.php) — TableInsert class
  - [mysql\_xdevapi\\TableSelect](https://www.php.net/manual/en/class.mysql-xdevapi-tableselect.php) — TableSelect class
  - [mysql\_xdevapi\\TableUpdate](https://www.php.net/manual/en/class.mysql-xdevapi-tableupdate.php) — TableUpdate class
  - [mysql\_xdevapi\\Warning](https://www.php.net/manual/en/class.mysql-xdevapi-warning.php) — Warning class
- [MySQL (Original)](https://www.php.net/manual/en/book.mysql.php) — Original MySQL API
  - [Introduction](https://www.php.net/manual/en/intro.mysql.php)
  - [Installing/Configuring](https://www.php.net/manual/en/mysql.setup.php)
  - [Changelog](https://www.php.net/manual/en/changelog.mysql.php)
  - [Predefined Constants](https://www.php.net/manual/en/mysql.constants.php)
  - [Examples](https://www.php.net/manual/en/mysql.examples.php)
  - [MySQL Functions](https://www.php.net/manual/en/ref.mysql.php)
- [Mysqlnd](https://www.php.net/manual/en/book.mysqlnd.php) — MySQL Native Driver
  - [Introduction](https://www.php.net/manual/en/intro.mysqlnd.php)
  - [Overview](https://www.php.net/manual/en/mysqlnd.overview.php)
  - [Installation](https://www.php.net/manual/en/mysqlnd.install.php)
  - [Runtime Configuration](https://www.php.net/manual/en/mysqlnd.config.php)
  - [Incompatibilities](https://www.php.net/manual/en/mysqlnd.incompatibilities.php)
  - [Persistent Connections](https://www.php.net/manual/en/mysqlnd.persist.php)
  - [Statistics](https://www.php.net/manual/en/mysqlnd.stats.php)
  - [Notes](https://www.php.net/manual/en/mysqlnd.notes.php)
  - [Memory management](https://www.php.net/manual/en/mysqlnd.memory.php)
  - [MySQL Native Driver Plugin API](https://www.php.net/manual/en/mysqlnd.plugin.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqlinfo/set.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fset.mysqlinfo%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=set.mysqlinfo&repo=en&redirect=https://www.php.net/manual/en/set.mysqlinfo.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google