---
url: https://www.php.net/manual/en/pdo.errorcode.php
scraped_at: 2025-10-20T02:51:46.115Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# PDO::errorCode

(PHP 5 >= 5.1.0, PHP 7, PHP 8, PECL pdo >= 0.1.0)

PDO::errorCode —
Fetch the SQLSTATE associated with the last operation on the database handle


### Description [¶](https://www.php.net/manual/en/pdo.errorcode.php\#refsect1-pdo.errorcode-description)

public**PDO::errorCode**(): [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php)

### Parameters [¶](https://www.php.net/manual/en/pdo.errorcode.php\#refsect1-pdo.errorcode-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/pdo.errorcode.php\#refsect1-pdo.errorcode-returnvalues)

Returns an SQLSTATE, a five characters alphanumeric identifier defined in
the ANSI SQL-92 standard. Briefly, an SQLSTATE consists of a
two characters class value followed by a three characters subclass value. A
class value of 01 indicates a warning and is accompanied by a return code
of SQL\_SUCCESS\_WITH\_INFO. Class values other than '01', except for the
class 'IM', indicate an error. The class 'IM' is specific to warnings
and errors that derive from the implementation of PDO (or perhaps ODBC,
if you're using the ODBC driver) itself. The subclass value '000' in any
class indicates that there is no subclass for that SQLSTATE.


**PDO::errorCode()** only retrieves error codes for operations
performed directly on the database handle. If you create a PDOStatement
object through [PDO::prepare()](https://www.php.net/manual/en/pdo.prepare.php) or
[PDO::query()](https://www.php.net/manual/en/pdo.query.php) and invoke an error on the statement
handle, **PDO::errorCode()** will not reflect that error.
You must call [PDOStatement::errorCode()](https://www.php.net/manual/en/pdostatement.errorcode.php) to return the error
code for an operation performed on a particular statement handle.


Returns **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** if no operation has been run on the database handle.


### Examples [¶](https://www.php.net/manual/en/pdo.errorcode.php\#refsect1-pdo.errorcode-examples)

**Example #1 Retrieving an SQLSTATE code**

`<?php
/* Provoke an error -- the BONES table does not exist */
$dbh->exec("INSERT INTO bones(skull) VALUES ('lucy')");
echo "\nPDO::errorCode(): ", $dbh->errorCode();
?>`

The above example will output:

```
PDO::errorCode(): 42S02
```

### See Also [¶](https://www.php.net/manual/en/pdo.errorcode.php\#refsect1-pdo.errorcode-seealso)

- [PDO::errorInfo()](https://www.php.net/manual/en/pdo.errorinfo.php) \- Fetch extended error information associated with the last operation on the database handle
- [PDOStatement::errorCode()](https://www.php.net/manual/en/pdostatement.errorcode.php) \- Fetch the SQLSTATE associated with the last operation on the statement handle
- [PDOStatement::errorInfo()](https://www.php.net/manual/en/pdostatement.errorinfo.php) \- Fetch extended error information associated with the last operation on the statement handle

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/pdo/pdo/errorcode.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fpdo.errorcode%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=pdo.errorcode&repo=en&redirect=https://www.php.net/manual/en/pdo.errorcode.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=59357&page=pdo.errorcode&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=59357&page=pdo.errorcode&vote=down "Vote down!")

44


[**_Matthias Leuffen_**](https://www.php.net/manual/en/pdo.errorcode.php#59357) [¶](https://www.php.net/manual/en/pdo.errorcode.php#59357)

**19 years ago**

`Hi,
List containing all SQL-92 SQLSTATE Return Codes:
[http://www.unix.org.ua/orelly/java-ent/jenut/ch08\_06.htm](http://www.unix.org.ua/orelly/java-ent/jenut/ch08_06.htm)
Use the following Code to let PDO throw Exceptions (PDOException) on Error.
<?PHP
$pdo = new PDO (whatever);
$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
try {
    $pdo->exec ("QUERY WITH SYNTAX ERROR");
} catch (PDOException $e) {
    if ($e->getCode() == '2A000')
        echo "Syntax Error: ".$e->getMessage();
}
?>
Bye,
Matthias`

[＋add a note](https://www.php.net/manual/add-note.php?sect=pdo.errorcode&repo=en&redirect=https://www.php.net/manual/en/pdo.errorcode.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google