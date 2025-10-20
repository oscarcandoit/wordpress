---
url: https://www.php.net/manual/en/mysqli-result.fetch-array.php
scraped_at: 2025-10-20T02:35:32.087Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::fetch\_array

# mysqli\_fetch\_array

(PHP 5, PHP 7, PHP 8)

mysqli\_result::fetch\_array \-\- mysqli\_fetch\_array — Fetch the next row of a result set as an associative, a numeric array, or both

### Description [¶](https://www.php.net/manual/en/mysqli-result.fetch-array.php\#refsect1-mysqli-result.fetch-array-description)

Object-oriented style

public**mysqli\_result::fetch\_array**([int](https://www.php.net/manual/en/language.types.integer.php) `$mode` = **`[MYSQLI\_BOTH](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-both)`**): [array](https://www.php.net/manual/en/language.types.array.php)\|[null](https://www.php.net/manual/en/language.types.null.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Procedural style

**mysqli\_fetch\_array**([mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) `$result`, [int](https://www.php.net/manual/en/language.types.integer.php) `$mode` = **`[MYSQLI\_BOTH](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-both)`**): [array](https://www.php.net/manual/en/language.types.array.php)\|[null](https://www.php.net/manual/en/language.types.null.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Fetches one row of data from the result set and returns it as an array.
Each subsequent call to this function will return the next row within the
result set, or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** if there are no more rows.


In addition to storing the data in the numeric indices of the result array,
this function can also store the data in associative indices
by using the field names of the result set as keys.


If two or more columns of the result have the same name, the last
column will take precedence and overwrite any previous data. To
access multiple columns with the same name, the numerically indexed
version of the row must be used.


> **Note**: Field names returned by this function
> are _case-sensitive_.

> **Note**: This function sets NULL fields to
> the PHP **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** value.

### Parameters [¶](https://www.php.net/manual/en/mysqli-result.fetch-array.php\#refsect1-mysqli-result.fetch-array-parameters)

`result`

Procedural style only: A [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)
object returned by [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php), [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
[mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php).

`mode`

This optional parameter is a constant indicating what type of array
should be produced from the current row data. The possible values for
this parameter are the constants **`[MYSQLI\_ASSOC](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-assoc)`**,
**`[MYSQLI\_NUM](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-num)`**, or **`[MYSQLI\_BOTH](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-both)`**.


By using the **`[MYSQLI\_ASSOC](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-assoc)`** constant this function
will behave identically to the [mysqli\_fetch\_assoc()](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php),
while **`[MYSQLI\_NUM](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-num)`** will behave identically to the
[mysqli\_fetch\_row()](https://www.php.net/manual/en/mysqli-result.fetch-row.php) function. The final option
**`[MYSQLI\_BOTH](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-both)`** will create a single array with the
attributes of both.


### Return Values [¶](https://www.php.net/manual/en/mysqli-result.fetch-array.php\#refsect1-mysqli-result.fetch-array-returnvalues)

Returns an array representing the fetched row, **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** if there
are no more rows in the result set, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/mysqli-result.fetch-array.php\#refsect1-mysqli-result.fetch-array-examples)

**Example #1 **mysqli\_result::fetch\_array()** example**

Object-oriented style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$query = "SELECT Name, CountryCode FROM City ORDER BY ID LIMIT 3";
$result = $mysqli->query($query);
/* numeric array */
$row = $result->fetch_array(MYSQLI_NUM);
printf("%s (%s)\n", $row[0], $row[1]);
/* associative array */
$row = $result->fetch_array(MYSQLI_ASSOC);
printf("%s (%s)\n", $row["Name"], $row["CountryCode"]);
/* associative and numeric array */
$row = $result->fetch_array(MYSQLI_BOTH);
printf("%s (%s)\n", $row[0], $row["CountryCode"]);`

Procedural style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = mysqli_connect("localhost", "my_user", "my_password", "world");
$query = "SELECT Name, CountryCode FROM City ORDER by ID LIMIT 3";
$result = mysqli_query($mysqli, $query);
/* numeric array */
$row = mysqli_fetch_array($result, MYSQLI_NUM);
printf("%s (%s)\n", $row[0], $row[1]);
/* associative array */
$row = mysqli_fetch_array($result, MYSQLI_ASSOC);
printf("%s (%s)\n", $row["Name"], $row["CountryCode"]);
/* associative and numeric array */
$row = mysqli_fetch_array($result, MYSQLI_BOTH);
printf("%s (%s)\n", $row[0], $row["CountryCode"]);`

The above examples will output
something similar to:

```
Kabul (AFG)
Qandahar (AFG)
Herat (AFG)
```

### See Also [¶](https://www.php.net/manual/en/mysqli-result.fetch-array.php\#refsect1-mysqli-result.fetch-array-seealso)

- [mysqli\_fetch\_assoc()](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php) \- Fetch the next row of a result set as an associative array
- [mysqli\_fetch\_column()](https://www.php.net/manual/en/mysqli-result.fetch-column.php) \- Fetch a single column from the next row of a result set
- [mysqli\_fetch\_row()](https://www.php.net/manual/en/mysqli-result.fetch-row.php) \- Fetch the next row of a result set as an enumerated array
- [mysqli\_fetch\_object()](https://www.php.net/manual/en/mysqli-result.fetch-object.php) \- Fetch the next row of a result set as an object
- [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php) \- Performs a query on the database
- [mysqli\_data\_seek()](https://www.php.net/manual/en/mysqli-result.data-seek.php) \- Adjusts the result pointer to an arbitrary row in the result

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/fetch-array.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.fetch-array%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.fetch-array&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.fetch-array.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google