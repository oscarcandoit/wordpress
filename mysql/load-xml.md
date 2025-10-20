---
url: https://dev.mysql.com/doc/refman/8.0/en/load-xml.html
scraped_at: 2025-10-20T03:11:08.152Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "Hide Sidebar")

[Previous: LOAD DATA Statement](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "Previous: LOAD DATA Statement")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Up: Data Manipulation Statements")[Next: Parenthesized Query Expressions](https://dev.mysql.com/doc/refman/8.0/en/parenthesized-query-expressions.html "Next: Parenthesized Query Expressions")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/load-xml.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/load-xml.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/load-xml.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/load-xml.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/load-xml.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/load-xml.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/load-xml.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/load-xml.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html)  / [SQL Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-statements.html)  /
[Data Manipulation Statements](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html)  /

LOAD XML Statement


### 15.2.10 LOAD XML Statement

```sql
LOAD XML
    [LOW_PRIORITY | CONCURRENT] [LOCAL]
    INFILE 'file_name'
    [REPLACE | IGNORE]
    INTO TABLE [db_name.]tbl_name
    [CHARACTER SET charset_name]
    [ROWS IDENTIFIED BY '<tagname>']
    [IGNORE number {LINES | ROWS}]
    [(field_name_or_user_var\
        [, field_name_or_user_var] ...)]
    [SET col_name={expr | DEFAULT}\
        [, col_name={expr | DEFAULT}] ...]
```

The [`LOAD XML`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement") statement reads data
from an XML file into a table. The
_`file_name`_ must be given as a literal
string. The _`tagname`_ in the optional
`ROWS IDENTIFIED BY` clause must also be given as
a literal string, and must be surrounded by angle brackets
( `<` and `>`).


[`LOAD XML`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement") acts as the complement of
running the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client in XML output mode
(that is, starting the client with the
[`--xml`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_xml) option). To write data from a
table to an XML file, you can invoke the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client")
client with the [`--xml`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_xml) and
[`-e`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_execute) options from
the system shell, as shown here:


```terminal
$> mysql --xml -e 'SELECT * FROM mydb.mytable' > file.xml
```

To read the file back into a table, use [`LOAD\\
      XML`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement"). By default, the `<row>`
element is considered to be the equivalent of a database table
row; this can be changed using the `ROWS IDENTIFIED
      BY` clause.


This statement supports three different XML formats:

- Column names as attributes and column values as attribute
values:



```xml
<row column1="value1" column2="value2" .../>
```

- Column names as tags and column values as the content of these
tags:



```xml
<row>
    <column1>value1</column1>
    <column2>value2</column2>
</row>
```

- Column names are the `name` attributes of
`<field>` tags, and values are the
contents of these tags:



```xml
<row>
    <field name='column1'>value1</field>
    <field name='column2'>value2</field>
</row>
```



This is the format used by other MySQL tools, such as
[**mysqldump**](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html "6.5.4 mysqldump — A Database Backup Program").


All three formats can be used in the same XML file; the import
routine automatically detects the format for each row and
interprets it correctly. Tags are matched based on the tag or
attribute name and the column name.


Prior to MySQL 8.0.21, `LOAD XML` did not support
`CDATA` sections in the source XML. (Bug
#30753708, Bug #98199)


The following clauses work essentially the same way for
[`LOAD XML`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement") as they do for
[`LOAD DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement"):

- `LOW_PRIORITY` or
`CONCURRENT`

- `LOCAL`

- `REPLACE` or `IGNORE`

- `CHARACTER SET`

- `SET`


See [Section 15.2.9, “LOAD DATA Statement”](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement"), for more information about these
clauses.


`(field_name_or_user_var,
      ...)` is a list of one or more comma-separated XML fields
or user variables. The name of a user variable used for this
purpose must match the name of a field from the XML file, prefixed
with `@`. You can use field names to select only
desired fields. User variables can be employed to store the
corresponding field values for subsequent re-use.


The `IGNORE number
      LINES` or `IGNORE
      number ROWS` clause causes the
first _`number`_ rows in the XML file to be
skipped. It is analogous to the [`LOAD\\
      DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement") statement's `IGNORE ... LINES`
clause.


Suppose that we have a table named `person`,
created as shown here:


```sql
USE test;

CREATE TABLE person (
    person_id INT NOT NULL PRIMARY KEY,
    fname VARCHAR(40) NULL,
    lname VARCHAR(40) NULL,
    created TIMESTAMP
);
```

Suppose further that this table is initially empty.


Now suppose that we have a simple XML file
`person.xml`, whose contents are as shown here:


```xml
<list>
  <person person_id="1" fname="Kapek" lname="Sainnouine"/>
  <person person_id="2" fname="Sajon" lname="Rondela"/>
  <person person_id="3"><fname>Likame</fname><lname>Örrtmons</lname></person>
  <person person_id="4"><fname>Slar</fname><lname>Manlanth</lname></person>
  <person><field name="person_id">5</field><field name="fname">Stoma</field>
    <field name="lname">Milu</field></person>
  <person><field name="person_id">6</field><field name="fname">Nirtam</field>
    <field name="lname">Sklöd</field></person>
  <person person_id="7"><fname>Sungam</fname><lname>Dulbåd</lname></person>
  <person person_id="8" fname="Sraref" lname="Encmelt"/>
</list>
```

Each of the permissible XML formats discussed previously is
represented in this example file.


To import the data in `person.xml` into the
`person` table, you can use this statement:


```sql
mysql> LOAD XML LOCAL INFILE 'person.xml'
    ->   INTO TABLE person
    ->   ROWS IDENTIFIED BY '<person>';

Query OK, 8 rows affected (0.00 sec)
Records: 8  Deleted: 0  Skipped: 0  Warnings: 0
```

Here, we assume that `person.xml` is located in
the MySQL data directory. If the file cannot be found, the
following error results:


```none
ERROR 2 (HY000): File '/person.xml' not found (Errcode: 2)
```

The `ROWS IDENTIFIED BY '<person>'` clause
means that each `<person>` element in the
XML file is considered equivalent to a row in the table into which
the data is to be imported. In this case, this is the
`person` table in the `test`
database.


As can be seen by the response from the server, 8 rows were
imported into the `test.person` table. This can
be verified by a simple [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
statement:


```sql
mysql> SELECT * FROM person;
+-----------+--------+------------+---------------------+
| person_id | fname  | lname      | created             |
+-----------+--------+------------+---------------------+
|         1 | Kapek  | Sainnouine | 2007-07-13 16:18:47 |
|         2 | Sajon  | Rondela    | 2007-07-13 16:18:47 |
|         3 | Likame | Örrtmons   | 2007-07-13 16:18:47 |
|         4 | Slar   | Manlanth   | 2007-07-13 16:18:47 |
|         5 | Stoma  | Nilu       | 2007-07-13 16:18:47 |
|         6 | Nirtam | Sklöd      | 2007-07-13 16:18:47 |
|         7 | Sungam | Dulbåd     | 2007-07-13 16:18:47 |
|         8 | Sreraf | Encmelt    | 2007-07-13 16:18:47 |
+-----------+--------+------------+---------------------+
8 rows in set (0.00 sec)
```

This shows, as stated earlier in this section, that any or all of
the 3 permitted XML formats may appear in a single file and be
read using [`LOAD XML`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement").


The inverse of the import operation just shown—that is,
dumping MySQL table data into an XML file—can be
accomplished using the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client from the
system shell, as shown here:


```terminal
$> mysql --xml -e "SELECT * FROM test.person" > person-dump.xml
$> cat person-dump.xml
<?xml version="1.0"?>

<resultset statement="SELECT * FROM test.person" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <row>
	<field name="person_id">1</field>
	<field name="fname">Kapek</field>
	<field name="lname">Sainnouine</field>
  </row>

  <row>
	<field name="person_id">2</field>
	<field name="fname">Sajon</field>
	<field name="lname">Rondela</field>
  </row>

  <row>
	<field name="person_id">3</field>
	<field name="fname">Likema</field>
	<field name="lname">Örrtmons</field>
  </row>

  <row>
	<field name="person_id">4</field>
	<field name="fname">Slar</field>
	<field name="lname">Manlanth</field>
  </row>

  <row>
	<field name="person_id">5</field>
	<field name="fname">Stoma</field>
	<field name="lname">Nilu</field>
  </row>

  <row>
	<field name="person_id">6</field>
	<field name="fname">Nirtam</field>
	<field name="lname">Sklöd</field>
  </row>

  <row>
	<field name="person_id">7</field>
	<field name="fname">Sungam</field>
	<field name="lname">Dulbåd</field>
  </row>

  <row>
	<field name="person_id">8</field>
	<field name="fname">Sreraf</field>
	<field name="lname">Encmelt</field>
  </row>
</resultset>
```

Note

The [`--xml`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_xml) option causes the
[**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client to use XML formatting for its
output; the [`-e`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_execute)
option causes the client to execute the SQL statement
immediately following the option. See [Section 6.5.1, “mysql — The MySQL Command-Line Client”](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client").

You can verify that the dump is valid by creating a copy of the
`person` table and importing the dump file into
the new table, like this:


```sql
mysql> USE test;
mysql> CREATE TABLE person2 LIKE person;
Query OK, 0 rows affected (0.00 sec)

mysql> LOAD XML LOCAL INFILE 'person-dump.xml'
    ->   INTO TABLE person2;
Query OK, 8 rows affected (0.01 sec)
Records: 8  Deleted: 0  Skipped: 0  Warnings: 0

mysql> SELECT * FROM person2;
+-----------+--------+------------+---------------------+
| person_id | fname  | lname      | created             |
+-----------+--------+------------+---------------------+
|         1 | Kapek  | Sainnouine | 2007-07-13 16:18:47 |
|         2 | Sajon  | Rondela    | 2007-07-13 16:18:47 |
|         3 | Likema | Örrtmons   | 2007-07-13 16:18:47 |
|         4 | Slar   | Manlanth   | 2007-07-13 16:18:47 |
|         5 | Stoma  | Nilu       | 2007-07-13 16:18:47 |
|         6 | Nirtam | Sklöd      | 2007-07-13 16:18:47 |
|         7 | Sungam | Dulbåd     | 2007-07-13 16:18:47 |
|         8 | Sreraf | Encmelt    | 2007-07-13 16:18:47 |
+-----------+--------+------------+---------------------+
8 rows in set (0.00 sec)
```

There is no requirement that every field in the XML file be
matched with a column in the corresponding table. Fields which
have no corresponding columns are skipped. You can see this by
first emptying the `person2` table and dropping
the `created` column, then using the same
[`LOAD XML`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement") statement we just employed
previously, like this:


```sql
mysql> TRUNCATE person2;
Query OK, 8 rows affected (0.26 sec)

mysql> ALTER TABLE person2 DROP COLUMN created;
Query OK, 0 rows affected (0.52 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> SHOW CREATE TABLE person2\G
*************************** 1. row ***************************
       Table: person2
Create Table: CREATE TABLE `person2` (
  `person_id` int NOT NULL,
  `fname` varchar(40) DEFAULT NULL,
  `lname` varchar(40) DEFAULT NULL,
  PRIMARY KEY (`person_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
1 row in set (0.00 sec)

mysql> LOAD XML LOCAL INFILE 'person-dump.xml'
    ->   INTO TABLE person2;
Query OK, 8 rows affected (0.01 sec)
Records: 8  Deleted: 0  Skipped: 0  Warnings: 0

mysql> SELECT * FROM person2;
+-----------+--------+------------+
| person_id | fname  | lname      |
+-----------+--------+------------+
|         1 | Kapek  | Sainnouine |
|         2 | Sajon  | Rondela    |
|         3 | Likema | Örrtmons   |
|         4 | Slar   | Manlanth   |
|         5 | Stoma  | Nilu       |
|         6 | Nirtam | Sklöd      |
|         7 | Sungam | Dulbåd     |
|         8 | Sreraf | Encmelt    |
+-----------+--------+------------+
8 rows in set (0.00 sec)
```

The order in which the fields are given within each row of the XML
file does not affect the operation of [`LOAD\\
      XML`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement"); the field order can vary from row to row, and is
not required to be in the same order as the corresponding columns
in the table.


As mentioned previously, you can use a
`(field_name_or_user_var,
      ...)` list of one or more XML fields (to select desired
fields only) or user variables (to store the corresponding field
values for later use). User variables can be especially useful
when you want to insert data from an XML file into table columns
whose names do not match those of the XML fields. To see how this
works, we first create a table named `individual`
whose structure matches that of the `person`
table, but whose columns are named differently:


```sql
mysql> CREATE TABLE individual (
    ->     individual_id INT NOT NULL PRIMARY KEY,
    ->     name1 VARCHAR(40) NULL,
    ->     name2 VARCHAR(40) NULL,
    ->     made TIMESTAMP
    -> );
Query OK, 0 rows affected (0.42 sec)
```

In this case, you cannot simply load the XML file directly into
the table, because the field and column names do not match:


```sql
mysql> LOAD XML INFILE '../bin/person-dump.xml' INTO TABLE test.individual;
ERROR 1263 (22004): Column set to default value; NULL supplied to NOT NULL column 'individual_id' at row 1
```

This happens because the MySQL server looks for field names
matching the column names of the target table. You can work around
this problem by selecting the field values into user variables,
then setting the target table's columns equal to the values
of those variables using `SET`. You can perform
both of these operations in a single statement, as shown here:


```sql
mysql> LOAD XML INFILE '../bin/person-dump.xml'
    ->     INTO TABLE test.individual (@person_id, @fname, @lname, @created)
    ->     SET individual_id=@person_id, name1=@fname, name2=@lname, made=@created;
Query OK, 8 rows affected (0.05 sec)
Records: 8  Deleted: 0  Skipped: 0  Warnings: 0

mysql> SELECT * FROM individual;
+---------------+--------+------------+---------------------+
| individual_id | name1  | name2      | made                |
+---------------+--------+------------+---------------------+
|             1 | Kapek  | Sainnouine | 2007-07-13 16:18:47 |
|             2 | Sajon  | Rondela    | 2007-07-13 16:18:47 |
|             3 | Likema | Örrtmons   | 2007-07-13 16:18:47 |
|             4 | Slar   | Manlanth   | 2007-07-13 16:18:47 |
|             5 | Stoma  | Nilu       | 2007-07-13 16:18:47 |
|             6 | Nirtam | Sklöd      | 2007-07-13 16:18:47 |
|             7 | Sungam | Dulbåd     | 2007-07-13 16:18:47 |
|             8 | Srraf  | Encmelt    | 2007-07-13 16:18:47 |
+---------------+--------+------------+---------------------+
8 rows in set (0.00 sec)
```

The names of the user variables _must_ match
those of the corresponding fields from the XML file, with the
addition of the required `@` prefix to indicate
that they are variables. The user variables need not be listed or
assigned in the same order as the corresponding fields.


Using a `ROWS IDENTIFIED BY
      '<tagname>'` clause, it
is possible to import data from the same XML file into database
tables with different definitions. For this example, suppose that
you have a file named `address.xml` which
contains the following XML:


```xml
<?xml version="1.0"?>

<list>
  <person person_id="1">
    <fname>Robert</fname>
    <lname>Jones</lname>
    <address address_id="1" street="Mill Creek Road" zip="45365" city="Sidney"/>
    <address address_id="2" street="Main Street" zip="28681" city="Taylorsville"/>
  </person>

  <person person_id="2">
    <fname>Mary</fname>
    <lname>Smith</lname>
    <address address_id="3" street="River Road" zip="80239" city="Denver"/>
    <!-- <address address_id="4" street="North Street" zip="37920" city="Knoxville"/> -->
  </person>

</list>
```

You can again use the `test.person` table as
defined previously in this section, after clearing all the
existing records from the table and then showing its structure as
shown here:


```sql
mysql< TRUNCATE person;
Query OK, 0 rows affected (0.04 sec)

mysql< SHOW CREATE TABLE person\G
*************************** 1. row ***************************
       Table: person
Create Table: CREATE TABLE `person` (
  `person_id` int(11) NOT NULL,
  `fname` varchar(40) DEFAULT NULL,
  `lname` varchar(40) DEFAULT NULL,
  `created` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`person_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
1 row in set (0.00 sec)
```

Now create an `address` table in the
`test` database using the following
[`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement:


```sql
CREATE TABLE address (
    address_id INT NOT NULL PRIMARY KEY,
    person_id INT NULL,
    street VARCHAR(40) NULL,
    zip INT NULL,
    city VARCHAR(40) NULL,
    created TIMESTAMP
);
```

To import the data from the XML file into the
`person` table, execute the following
[`LOAD XML`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement") statement, which specifies
that rows are to be specified by the
`<person>` element, as shown here;


```sql
mysql> LOAD XML LOCAL INFILE 'address.xml'
    ->   INTO TABLE person
    ->   ROWS IDENTIFIED BY '<person>';
Query OK, 2 rows affected (0.00 sec)
Records: 2  Deleted: 0  Skipped: 0  Warnings: 0
```

You can verify that the records were imported using a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement:


```sql
mysql> SELECT * FROM person;
+-----------+--------+-------+---------------------+
| person_id | fname  | lname | created             |
+-----------+--------+-------+---------------------+
|         1 | Robert | Jones | 2007-07-24 17:37:06 |
|         2 | Mary   | Smith | 2007-07-24 17:37:06 |
+-----------+--------+-------+---------------------+
2 rows in set (0.00 sec)
```

Since the `<address>` elements in the XML
file have no corresponding columns in the
`person` table, they are skipped.


To import the data from the `<address>`
elements into the `address` table, use the
[`LOAD XML`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement") statement shown here:


```sql
mysql> LOAD XML LOCAL INFILE 'address.xml'
    ->   INTO TABLE address
    ->   ROWS IDENTIFIED BY '<address>';
Query OK, 3 rows affected (0.00 sec)
Records: 3  Deleted: 0  Skipped: 0  Warnings: 0
```

You can see that the data was imported using a
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement") statement such as this one:


```sql
mysql> SELECT * FROM address;
+------------+-----------+-----------------+-------+--------------+---------------------+
| address_id | person_id | street          | zip   | city         | created             |
+------------+-----------+-----------------+-------+--------------+---------------------+
|          1 |         1 | Mill Creek Road | 45365 | Sidney       | 2007-07-24 17:37:37 |
|          2 |         1 | Main Street     | 28681 | Taylorsville | 2007-07-24 17:37:37 |
|          3 |         2 | River Road      | 80239 | Denver       | 2007-07-24 17:37:37 |
+------------+-----------+-----------------+-------+--------------+---------------------+
3 rows in set (0.00 sec)
```

The data from the `<address>` element that
is enclosed in XML comments is not imported. However, since there
is a `person_id` column in the
`address` table, the value of the
`person_id` attribute from the parent
`<person>` element for each
`<address>` _is_
imported into the `address` table.


**Security Considerations.**
As with the [`LOAD DATA`](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "15.2.9 LOAD DATA Statement") statement,
the transfer of the XML file from the client host to the server
host is initiated by the MySQL server. In theory, a patched
server could be built that would tell the client program to
transfer a file of the server's choosing rather than the file
named by the client in the [`LOAD\\
        XML`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement") statement. Such a server could access any file on
the client host to which the client user has read access.


In a Web environment, clients usually connect to MySQL from a Web
server. A user that can run any command against the MySQL server
can use [`LOAD XML\\
      LOCAL`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement") to read any files to which the Web server process
has read access. In this environment, the client with respect to
the MySQL server is actually the Web server, not the remote
program being run by the user who connects to the Web server.


You can disable loading of XML files from clients by starting the
server with [`--local-infile=0`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_local_infile) or
[`--local-infile=OFF`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_local_infile). This option
can also be used when starting the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client
to disable [`LOAD XML`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement") for the
duration of the client session.


To prevent a client from loading XML files from the server, do not
grant the [`FILE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_file) privilege to the
corresponding MySQL user account, or revoke this privilege if the
client user account already has it.

Important

Revoking the [`FILE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_file) privilege (or
not granting it in the first place) keeps the user only from
executing the [`LOAD XML`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement") statement
(as well as the [`LOAD_FILE()`](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html#function_load-file)
function; it does _not_ prevent the user from
executing [`LOAD XML\\
        LOCAL`](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html "15.2.10 LOAD XML Statement"). To disallow this statement, you must start the
server or the client with `--local-infile=OFF`.


In other words, the [`FILE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_file)
privilege affects only whether the client can read files on the
server; it has no bearing on whether the client can read files
on the local file system.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/load-data.html "Previous: LOAD DATA Statement") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/sql-data-manipulation-statements.html "Up: Data Manipulation Statements") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/parenthesized-query-expressions.html "Next: Parenthesized Query Expressions")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/load-xml.html)

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