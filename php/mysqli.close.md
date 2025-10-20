---
url: https://www.php.net/manual/en/mysqli.close.php
scraped_at: 2025-10-20T02:56:42.088Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli::close

# mysqli\_close

(PHP 5, PHP 7, PHP 8)

mysqli::close \-\- mysqli\_close — Closes a previously opened database connection

### Description [¶](https://www.php.net/manual/en/mysqli.close.php\#refsect1-mysqli.close-description)

Object-oriented style

public**mysqli::close**(): [true](https://www.php.net/manual/en/language.types.singleton.php)

Procedural style

**mysqli\_close**([mysqli](https://www.php.net/manual/en/class.mysqli.php) `$mysql`): [true](https://www.php.net/manual/en/language.types.singleton.php)

Closes a previously opened database connection.


Open non-persistent MySQL connections and result sets are automatically
closed when their objects are destroyed. Explicitly closing open
connections and freeing result sets is optional. However, it's a good idea
to close the connection as soon as the script finishes performing all of its
database operations, if it still has a lot of processing to do after
getting the results.


### Parameters [¶](https://www.php.net/manual/en/mysqli.close.php\#refsect1-mysqli.close-parameters)

`mysql`

Procedural style only: A [mysqli](https://www.php.net/manual/en/class.mysqli.php) object
returned by [mysqli\_connect()](https://www.php.net/manual/en/function.mysqli-connect.php) or [mysqli\_init()](https://www.php.net/manual/en/mysqli.init.php)

### Return Values [¶](https://www.php.net/manual/en/mysqli.close.php\#refsect1-mysqli.close-returnvalues)

Always returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.


### Changelog [¶](https://www.php.net/manual/en/mysqli.close.php\#refsect1-mysqli.close-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | This function now always returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**. Previously it returned **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure. |

### Examples [¶](https://www.php.net/manual/en/mysqli.close.php\#refsect1-mysqli.close-examples)

**Example #1 **mysqli::close()** example**

Object-oriented style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$result = $mysqli->query("SELECT Name, CountryCode FROM City ORDER BY ID LIMIT 3");
/* Close the connection as soon as it's no longer needed */
$mysqli->close();
foreach ($result as $row) {
    /* Processing of the data retrieved from the database */
}`

Procedural style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = mysqli_connect("localhost", "my_user", "my_password", "world");
$result = mysqli_query($mysqli, "SELECT Name, CountryCode FROM City ORDER BY ID LIMIT 3");
/* Close the connection as soon as it's no longer needed */
mysqli_close($mysqli);
foreach ($result as $row) {
    /* Processing of the data retrieved from the database */
}`

### Notes [¶](https://www.php.net/manual/en/mysqli.close.php\#refsect1-mysqli.close-notes)

> **Note**:
>
>
> **mysqli\_close()** will not close persistent connections.
> For additional details, see the manual page on
> [persistent connections](https://www.php.net/manual/en/features.persistent-connections.php).

### See Also [¶](https://www.php.net/manual/en/mysqli.close.php\#refsect1-mysqli.close-seealso)

- [mysqli::\_\_construct()](https://www.php.net/manual/en/mysqli.construct.php) \- Open a new connection to the MySQL server
- [mysqli\_init()](https://www.php.net/manual/en/mysqli.init.php) \- Initializes MySQLi and returns an object for use with mysqli\_real\_connect()
- [mysqli\_real\_connect()](https://www.php.net/manual/en/mysqli.real-connect.php) \- Opens a connection to a mysql server
- [mysqli\_free\_result()](https://www.php.net/manual/en/mysqli-result.free.php) \- Frees the memory associated with a result

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli/close.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli.close%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli.close&repo=en&redirect=https://www.php.net/manual/en/mysqli.close.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google