---
url: https://www.php.net/manual/en/pdostatement.columncount.php
scraped_at: 2025-10-20T02:57:23.875Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# PDOStatement::columnCount

(PHP 5 >= 5.1.0, PHP 7, PHP 8, PECL pdo >= 0.2.0)

PDOStatement::columnCount —
Returns the number of columns in the result set


### Description [¶](https://www.php.net/manual/en/pdostatement.columncount.php\#refsect1-pdostatement.columncount-description)

public**PDOStatement::columnCount**(): [int](https://www.php.net/manual/en/language.types.integer.php)

Use **PDOStatement::columnCount()** to return the number
of columns in the result set represented by the PDOStatement object.


If the PDOStatement object was returned from [PDO::query()](https://www.php.net/manual/en/pdo.query.php),
the column count is immediately available.


If the PDOStatement object was returned from
[PDO::prepare()](https://www.php.net/manual/en/pdo.prepare.php), an accurate column count will not be
available until you invoke [PDOStatement::execute()](https://www.php.net/manual/en/pdostatement.execute.php).


### Parameters [¶](https://www.php.net/manual/en/pdostatement.columncount.php\#refsect1-pdostatement.columncount-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/pdostatement.columncount.php\#refsect1-pdostatement.columncount-returnvalues)

Returns the number of columns in the result set represented by the
PDOStatement object, even if the result set is empty. If there is no result set,
**PDOStatement::columnCount()** returns `0`.


### Errors/Exceptions [¶](https://www.php.net/manual/en/pdostatement.columncount.php\#refsect1-pdostatement.columncount-errors)

Emits an error with level **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** if the attribute **`[PDO::ATTR\_ERRMODE](https://www.php.net/manual/en/pdo.constants.php#pdo.constants.attr-errmode)`** is set
to **`[PDO::ERRMODE\_WARNING](https://www.php.net/manual/en/pdo.constants.php#pdo.constants.errmode-warning)`**.

Throws a [PDOException](https://www.php.net/manual/en/class.pdoexception.php) if the attribute **`[PDO::ATTR\_ERRMODE](https://www.php.net/manual/en/pdo.constants.php#pdo.constants.attr-errmode)`**
is set to **`[PDO::ERRMODE\_EXCEPTION](https://www.php.net/manual/en/pdo.constants.php#pdo.constants.errmode-exception)`**.

### Examples [¶](https://www.php.net/manual/en/pdostatement.columncount.php\#refsect1-pdostatement.columncount-examples)

**Example #1 Counting columns**

This example demonstrates how **PDOStatement::columnCount()**
operates with and without a result set.


`<?php
$dbh = new PDO('odbc:sample', 'db2inst1', 'ibmdb2');
$sth = $dbh->prepare("SELECT name, colour FROM fruit");
/* Count the number of columns in the (non-existent) result set */
$colcount = $sth->columnCount();
print "Before execute(), result set has $colcount columns (should be 0)\n";
$sth->execute();
/* Count the number of columns in the result set */
$colcount = $sth->columnCount();
print "After execute(), result set has $colcount columns (should be 2)\n";
?>`

The above example will output:

```
Before execute(), result set has 0 columns (should be 0)
After execute(), result set has 2 columns (should be 2)
```

### See Also [¶](https://www.php.net/manual/en/pdostatement.columncount.php\#refsect1-pdostatement.columncount-seealso)

- [PDO::prepare()](https://www.php.net/manual/en/pdo.prepare.php) \- Prepares a statement for execution and returns a statement object
- [PDOStatement::execute()](https://www.php.net/manual/en/pdostatement.execute.php) \- Executes a prepared statement
- [PDOStatement::rowCount()](https://www.php.net/manual/en/pdostatement.rowcount.php) \- Returns the number of rows affected by the last SQL statement

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/pdo/pdostatement/columncount.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fpdostatement.columncount%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=pdostatement.columncount&repo=en&redirect=https://www.php.net/manual/en/pdostatement.columncount.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google