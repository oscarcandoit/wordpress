---
url: https://www.php.net/manual/en/pdostatement.fetchcolumn.php
scraped_at: 2025-10-20T02:50:33.658Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# PDOStatement::fetchColumn

(PHP 5 >= 5.1.0, PHP 7, PHP 8, PECL pdo >= 0.9.0)

PDOStatement::fetchColumn —
Returns a single column from the next row of a result set


### Description [¶](https://www.php.net/manual/en/pdostatement.fetchcolumn.php\#refsect1-pdostatement.fetchcolumn-description)

public**PDOStatement::fetchColumn**([int](https://www.php.net/manual/en/language.types.integer.php) `$column` = 0): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

Returns a single column from the next row of a result set or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if
there are no more rows.


> **Note**:
>
>
> **PDOStatement::fetchColumn()** should not be used to
> retrieve boolean columns, as it is impossible to distinguish a value of
> **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** from there being no more rows to retrieve. Use
> [PDOStatement::fetch()](https://www.php.net/manual/en/pdostatement.fetch.php) instead.

### Parameters [¶](https://www.php.net/manual/en/pdostatement.fetchcolumn.php\#refsect1-pdostatement.fetchcolumn-parameters)

`column`

0-indexed number of the column you wish to retrieve from the row. If
no value is supplied, **PDOStatement::fetchColumn()**
fetches the first column.


### Return Values [¶](https://www.php.net/manual/en/pdostatement.fetchcolumn.php\#refsect1-pdostatement.fetchcolumn-returnvalues)

**PDOStatement::fetchColumn()** returns a single column
from the next row of a result set or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if there are no more rows.


**Warning**

There is no way to return another column from the same row if you
use **PDOStatement::fetchColumn()** to retrieve data.


### Errors/Exceptions [¶](https://www.php.net/manual/en/pdostatement.fetchcolumn.php\#refsect1-pdostatement.fetchcolumn-errors)

Emits an error with level **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** if the attribute **`[PDO::ATTR\_ERRMODE](https://www.php.net/manual/en/pdo.constants.php#pdo.constants.attr-errmode)`** is set
to **`[PDO::ERRMODE\_WARNING](https://www.php.net/manual/en/pdo.constants.php#pdo.constants.errmode-warning)`**.

Throws a [PDOException](https://www.php.net/manual/en/class.pdoexception.php) if the attribute **`[PDO::ATTR\_ERRMODE](https://www.php.net/manual/en/pdo.constants.php#pdo.constants.attr-errmode)`**
is set to **`[PDO::ERRMODE\_EXCEPTION](https://www.php.net/manual/en/pdo.constants.php#pdo.constants.errmode-exception)`**.

### Examples [¶](https://www.php.net/manual/en/pdostatement.fetchcolumn.php\#refsect1-pdostatement.fetchcolumn-examples)

**Example #1 Return first column of the next row**

`<?php
$sth = $dbh->prepare("SELECT name, colour FROM fruit");
$sth->execute();
print "Fetch the first column from the first row in the result set:\n";
$result = $sth->fetchColumn();
print "name = $result\n";
print "Fetch the second column from the second row in the result set:\n";
$result = $sth->fetchColumn(1);
print "colour = $result\n";
?>`

The above example will output:

```
Fetch the first column from the first row in the result set:
name = lemon
Fetch the second column from the second row in the result set:
colour = red
```

### See Also [¶](https://www.php.net/manual/en/pdostatement.fetchcolumn.php\#refsect1-pdostatement.fetchcolumn-seealso)

- [PDO::query()](https://www.php.net/manual/en/pdo.query.php) \- Prepares and executes an SQL statement without placeholders
- [PDOStatement::fetch()](https://www.php.net/manual/en/pdostatement.fetch.php) \- Fetches the next row from a result set
- [PDOStatement::fetchAll()](https://www.php.net/manual/en/pdostatement.fetchall.php) \- Fetches the remaining rows from a result set
- [PDO::prepare()](https://www.php.net/manual/en/pdo.prepare.php) \- Prepares a statement for execution and returns a statement object
- [PDOStatement::setFetchMode()](https://www.php.net/manual/en/pdostatement.setfetchmode.php) \- Set the default fetch mode for this statement

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/pdo/pdostatement/fetchcolumn.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fpdostatement.fetchcolumn%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=pdostatement.fetchcolumn&repo=en&redirect=https://www.php.net/manual/en/pdostatement.fetchcolumn.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=100522&page=pdostatement.fetchcolumn&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100522&page=pdostatement.fetchcolumn&vote=down "Vote down!")

55


[**_PhoneixSegovia at GOOGLE\_MAIL\_SERVER dot com_**](https://www.php.net/manual/en/pdostatement.fetchcolumn.php#100522) [¶](https://www.php.net/manual/en/pdostatement.fetchcolumn.php#100522)

**14 years ago**

`fetchColumn return boolean false when a row not is found or don't had more rows.`

[up](https://www.php.net/manual/vote-note.php?id=72609&page=pdostatement.fetchcolumn&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72609&page=pdostatement.fetchcolumn&vote=down "Vote down!")

14


[**_seanferd at assmasterdonkeyranch dot com_**](https://www.php.net/manual/en/pdostatement.fetchcolumn.php#72609) [¶](https://www.php.net/manual/en/pdostatement.fetchcolumn.php#72609)

**18 years ago**

`This is an excellent method for returning a column count. For example:
<?php
$db = new PDO('mysql:host=localhost;dbname=pictures','user','password');
$pics = $db->query('SELECT COUNT(id) FROM pics');
$this->totalpics = $pics->fetchColumn();
$db = null;
?>
In my case $pics->fetchColumn() returns 641 because that is how many pictures I have in my db.`

[up](https://www.php.net/manual/vote-note.php?id=129145&page=pdostatement.fetchcolumn&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129145&page=pdostatement.fetchcolumn&vote=down "Vote down!")

 -1


[**_theking2(at)king.ma_**](https://www.php.net/manual/en/pdostatement.fetchcolumn.php#129145) [¶](https://www.php.net/manual/en/pdostatement.fetchcolumn.php#129145)

**1 year ago**

``When migrating from mysqli it is important that while mysqli_result::fetch_column will iterate over subsequent rows  PDOStatement::fetchColumn will NOT!
<?php
while ( $row0 = $db->query("SELECT `value` FROM `bool`")->fetchColumn(0) ) {
var_dump( $row0 );
}
?>
is an endless loop unless the first column in the first row of the table bool is "0".``

[＋add a note](https://www.php.net/manual/add-note.php?sect=pdostatement.fetchcolumn&repo=en&redirect=https://www.php.net/manual/en/pdostatement.fetchcolumn.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google