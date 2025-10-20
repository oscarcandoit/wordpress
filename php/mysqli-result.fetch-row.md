---
url: https://www.php.net/manual/en/mysqli-result.fetch-row.php
scraped_at: 2025-10-20T02:38:50.834Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::fetch\_row

# mysqli\_fetch\_row

(PHP 5, PHP 7, PHP 8)

mysqli\_result::fetch\_row \-\- mysqli\_fetch\_row — Fetch the next row of a result set as an enumerated array

### Description [¶](https://www.php.net/manual/en/mysqli-result.fetch-row.php\#refsect1-mysqli-result.fetch-row-description)

Object-oriented style

public**mysqli\_result::fetch\_row**(): [array](https://www.php.net/manual/en/language.types.array.php)\|[null](https://www.php.net/manual/en/language.types.null.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Procedural style

**mysqli\_fetch\_row**([mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) `$result`): [array](https://www.php.net/manual/en/language.types.array.php)\|[null](https://www.php.net/manual/en/language.types.null.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Fetches one row of data from the result set and returns it as an enumerated
array, where each column is stored in an array offset starting from 0 (zero).
Each subsequent call to this function will return the next row within the
result set, or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** if there are no more rows.


> **Note**: This function sets NULL fields to
> the PHP **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** value.

### Parameters [¶](https://www.php.net/manual/en/mysqli-result.fetch-row.php\#refsect1-mysqli-result.fetch-row-parameters)

`result`

Procedural style only: A [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)
object returned by [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php), [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
[mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php).

### Return Values [¶](https://www.php.net/manual/en/mysqli-result.fetch-row.php\#refsect1-mysqli-result.fetch-row-returnvalues)

Returns an enumerated array representing the fetched row, **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** if there
are no more rows in the result set, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/mysqli-result.fetch-row.php\#refsect1-mysqli-result.fetch-row-examples)

**Example #1 **mysqli\_result::fetch\_row()** example**

Object-oriented style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$query = "SELECT Name, CountryCode FROM City ORDER BY ID DESC";
$result = $mysqli->query($query);
/* fetch object array */
while ($row = $result->fetch_row()) {
    printf("%s (%s)\n", $row[0], $row[1]);
}`

Procedural style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = mysqli_connect("localhost", "my_user", "my_password", "world");
$query = "SELECT Name, CountryCode FROM City ORDER BY ID DESC";
$result = mysqli_query($mysqli, $query);
/* fetch associative array */
while ($row = mysqli_fetch_row($result)) {
    printf("%s (%s)\n", $row[0], $row[1]);
}`

The above examples will output
something similar to:

```
Pueblo (USA)
Arvada (USA)
Cape Coral (USA)
Green Bay (USA)
Santa Clara (USA)
```

### See Also [¶](https://www.php.net/manual/en/mysqli-result.fetch-row.php\#refsect1-mysqli-result.fetch-row-seealso)

- [mysqli\_fetch\_array()](https://www.php.net/manual/en/mysqli-result.fetch-array.php) \- Fetch the next row of a result set as an associative, a numeric array, or both
- [mysqli\_fetch\_assoc()](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php) \- Fetch the next row of a result set as an associative array
- [mysqli\_fetch\_column()](https://www.php.net/manual/en/mysqli-result.fetch-column.php) \- Fetch a single column from the next row of a result set
- [mysqli\_fetch\_object()](https://www.php.net/manual/en/mysqli-result.fetch-object.php) \- Fetch the next row of a result set as an object
- [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php) \- Performs a query on the database
- [mysqli\_data\_seek()](https://www.php.net/manual/en/mysqli-result.data-seek.php) \- Adjusts the result pointer to an arbitrary row in the result

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/fetch-row.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.fetch-row%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.fetch-row&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.fetch-row.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=72527&page=mysqli-result.fetch-row&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72527&page=mysqli-result.fetch-row&vote=down "Vote down!")

20


[**_Stephen_**](https://www.php.net/manual/en/mysqli-result.fetch-row.php#72527) [¶](https://www.php.net/manual/en/mysqli-result.fetch-row.php#72527)

**18 years ago**

`It's worth noting that the MySQLi functions (and, I presume, the MySQL functions) fetch a string regardless of the MySQL data type. E.g. if you fetch a row with an integer column, the corresponding value for that column and row will still be stored as a string in the array returned by mysql_fetch_row.`

[up](https://www.php.net/manual/vote-note.php?id=114649&page=mysqli-result.fetch-row&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114649&page=mysqli-result.fetch-row&vote=down "Vote down!")

4


[**_sainthyoga2003 at gmail dot com_**](https://www.php.net/manual/en/mysqli-result.fetch-row.php#114649) [¶](https://www.php.net/manual/en/mysqli-result.fetch-row.php#114649)

**11 years ago**

`Note that mysqli_fetch() is deprecated but still is in PHP function list. mysqli_fetch_row() is nowadays mysql procedural style used, but is not listed in PHP functions.`

[up](https://www.php.net/manual/vote-note.php?id=77861&page=mysqli-result.fetch-row&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77861&page=mysqli-result.fetch-row&vote=down "Vote down!")

5


[**_evangun2001 at yahoo dot fr_**](https://www.php.net/manual/en/mysqli-result.fetch-row.php#77861) [¶](https://www.php.net/manual/en/mysqli-result.fetch-row.php#77861)

**18 years ago**

`Remember that fetch() and fetch_row() are two different things, and differ in the way to use them.
- fetch() is used on a statement (like an executed prepared statement) and needs to be used in association with bind_result().
- fetch_row() is used on a result (like the result of query()).
As a consequence, if you want to use to use fetch_row() with an executed prepared statement, first you'll have to get the result out of this statement with mysqli_store_result() or mysqli_use_result().`

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.fetch-row&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.fetch-row.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google