---
url: https://www.php.net/manual/en/pdostatement.errorcode.php
scraped_at: 2025-10-20T02:57:14.931Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# PDOStatement::errorCode

(PHP 5 >= 5.1.0, PHP 7, PHP 8, PECL pdo >= 0.1.0)

PDOStatement::errorCode —
Fetch the SQLSTATE associated with the last operation on the statement handle


### Description [¶](https://www.php.net/manual/en/pdostatement.errorcode.php\#refsect1-pdostatement.errorcode-description)

public**PDOStatement::errorCode**(): [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php)

### Parameters [¶](https://www.php.net/manual/en/pdostatement.errorcode.php\#refsect1-pdostatement.errorcode-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/pdostatement.errorcode.php\#refsect1-pdostatement.errorcode-returnvalues)

Identical to [PDO::errorCode()](https://www.php.net/manual/en/pdo.errorcode.php), except that
**PDOStatement::errorCode()** only retrieves error codes
for operations performed with PDOStatement objects.


### Examples [¶](https://www.php.net/manual/en/pdostatement.errorcode.php\#refsect1-pdostatement.errorcode-examples)

**Example #1 Retrieving an SQLSTATE code**

`<?php
/* Provoke an error -- the BONES table does not exist */
$err = $dbh->prepare('SELECT skull FROM bones');
$err->execute();
echo "\nPDOStatement::errorCode(): ";
print $err->errorCode();
?>`

The above example will output:

```
PDOStatement::errorCode(): 42S02
```

### See Also [¶](https://www.php.net/manual/en/pdostatement.errorcode.php\#refsect1-pdostatement.errorcode-seealso)

- [PDO::errorCode()](https://www.php.net/manual/en/pdo.errorcode.php) \- Fetch the SQLSTATE associated with the last operation on the database handle
- [PDO::errorInfo()](https://www.php.net/manual/en/pdo.errorinfo.php) \- Fetch extended error information associated with the last operation on the database handle
- [PDOStatement::errorInfo()](https://www.php.net/manual/en/pdostatement.errorinfo.php) \- Fetch extended error information associated with the last operation on the statement handle

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/pdo/pdostatement/errorcode.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fpdostatement.errorcode%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=pdostatement.errorcode&repo=en&redirect=https://www.php.net/manual/en/pdostatement.errorcode.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=67194&page=pdostatement.errorcode&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=67194&page=pdostatement.errorcode&vote=down "Vote down!")

15


[**_vaclav dot sir at gmail dot com_**](https://www.php.net/manual/en/pdostatement.errorcode.php#67194) [¶](https://www.php.net/manual/en/pdostatement.errorcode.php#67194)

**19 years ago**

`Statement's errorCode() returns an empty string before execution, and '00000' (five zeros) after a sucessfull execution:
<?php
$stmt = $pdo->prepare($query);
assert($stmt->errorCode === '');
$stmt->execute();
assert($stmt->errorCode === '00000');
?>`

[up](https://www.php.net/manual/vote-note.php?id=85248&page=pdostatement.errorcode&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85248&page=pdostatement.errorcode&vote=down "Vote down!")

 -1


[**_dbeecher at tekops dot com_**](https://www.php.net/manual/en/pdostatement.errorcode.php#85248) [¶](https://www.php.net/manual/en/pdostatement.errorcode.php#85248)

**17 years ago**

`Neither this property nor the PDOStatement::errorInfo() properties are available if you create  your own exception handler.
I am using PHP 5.2.4, PDO_INFORMIX 1.2.0.
Making this call at any point in the program after setting your own exception handler produces an error:
PHP Notice:  Undefined property:  PDOStatement::$errorCode in new_query.php on line
or
PHP Notice:  Undefined property:  PDOStatement::$errorInfo in new_query.php on line
But if I set the PDO to SILENT, only set error codes with:
$dbh->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_SILENT)
Then process with if/else the call to this functions works fine.  The examples below only do error checking to show the result codes of this function.  Normally you would want more.
FAILS:
$dbh = new PDO("informix...")
$dbh->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
try  {
      $result = $dbh->query("asdfkjasdfkjasdfjk");  /* obvious sql error */
      if ($result) print "success!";
      }
catch
      {
      $myeCode = $dbh->errorCode();
      /* do stuff with error */
      };
$dbh=0;
The error handler gets called but knows nothing about $dbh->errorCode or $dbh->errorInfo.
WORKS:
$dbh = new PDO("informix...")
$dbh->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_SILENT);
$result = $dbh->query("asdfkjasdfkjasdfjk");  /* obvious sql error */
if ($result)
      {
      /* process result */
      print "success!";
      /* all done, didn't make any changes */
      $dbh->rollback();
      }
else
      {
      $myeCode = $dbh->errorCode();
      print_r($myeCode);
      };
$dbh=0;  /* close connection */
I hope this helps someone else.
Cheers,
David`

[＋add a note](https://www.php.net/manual/add-note.php?sect=pdostatement.errorcode&repo=en&redirect=https://www.php.net/manual/en/pdostatement.errorcode.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google