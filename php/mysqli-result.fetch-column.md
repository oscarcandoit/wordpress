---
url: https://www.php.net/manual/en/mysqli-result.fetch-column.php
scraped_at: 2025-10-20T02:41:38.128Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::fetch\_column

# mysqli\_fetch\_column

(PHP 8 >= 8.1.0)

mysqli\_result::fetch\_column \-\- mysqli\_fetch\_column — Fetch a single column from the next row of a result set

### Description [¶](https://www.php.net/manual/en/mysqli-result.fetch-column.php\#refsect1-mysqli-result.fetch-column-description)

Object-oriented style

public**mysqli\_result::fetch\_column**([int](https://www.php.net/manual/en/language.types.integer.php) `$column` = 0): [null](https://www.php.net/manual/en/language.types.null.php)\|[int](https://www.php.net/manual/en/language.types.integer.php)\|[float](https://www.php.net/manual/en/language.types.float.php)\|[string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Procedural style

**mysqli\_fetch\_column**([mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) `$result`, [int](https://www.php.net/manual/en/language.types.integer.php) `$column` = 0): [null](https://www.php.net/manual/en/language.types.null.php)\|[int](https://www.php.net/manual/en/language.types.integer.php)\|[float](https://www.php.net/manual/en/language.types.float.php)\|[string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Fetches one row of data from the result set and returns the 0-indexed column.
Each subsequent call to this function will return the value from the next row
within the result set, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if there are no more rows.


> **Note**: This function sets NULL fields to
> the PHP **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** value.

### Parameters [¶](https://www.php.net/manual/en/mysqli-result.fetch-column.php\#refsect1-mysqli-result.fetch-column-parameters)

`result`

Procedural style only: A [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)
object returned by [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php), [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
[mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php).

`column`

0-indexed number of the column you wish to retrieve from the row. If
no value is supplied, the first column will be returned.


### Return Values [¶](https://www.php.net/manual/en/mysqli-result.fetch-column.php\#refsect1-mysqli-result.fetch-column-returnvalues)

Returns a single column
from the next row of a result set or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if there are no more rows.


**Warning**

There is no way to return another column from the same row if you
use this function to retrieve data.


### Examples [¶](https://www.php.net/manual/en/mysqli-result.fetch-column.php\#refsect1-mysqli-result.fetch-column-examples)

**Example #1 **mysqli\_result::fetch\_column()** example**

Object-oriented style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$query = "SELECT CountryCode, Name FROM City ORDER BY ID DESC LIMIT 5";
$result = $mysqli->query($query);
/* fetch a single value from the second column */
while ($Name = $result->fetch_column(1)) {
    printf("%s\n", $Name);
}`

Procedural style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = mysqli_connect("localhost", "my_user", "my_password", "world");
$query = "SELECT CountryCode, Name FROM City ORDER BY ID DESC LIMIT 5";
$result = mysqli_query($mysqli, $query);
/* fetch a single value from the second column */
while ($Name = mysqli_fetch_column($result, 1)) {
    printf("%s\n", $Name);
}`

The above examples will output
something similar to:

```
Rafah
Nablus
Jabaliya
Hebron
Khan Yunis
```

### See Also [¶](https://www.php.net/manual/en/mysqli-result.fetch-column.php\#refsect1-mysqli-result.fetch-column-seealso)

- [mysqli\_fetch\_all()](https://www.php.net/manual/en/mysqli-result.fetch-all.php) \- Fetch all result rows as an associative array, a numeric array, or both
- [mysqli\_fetch\_array()](https://www.php.net/manual/en/mysqli-result.fetch-array.php) \- Fetch the next row of a result set as an associative, a numeric array, or both
- [mysqli\_fetch\_assoc()](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php) \- Fetch the next row of a result set as an associative array
- [mysqli\_fetch\_object()](https://www.php.net/manual/en/mysqli-result.fetch-object.php) \- Fetch the next row of a result set as an object
- [mysqli\_fetch\_row()](https://www.php.net/manual/en/mysqli-result.fetch-row.php) \- Fetch the next row of a result set as an enumerated array
- [mysqli\_data\_seek()](https://www.php.net/manual/en/mysqli-result.data-seek.php) \- Adjusts the result pointer to an arbitrary row in the result

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/fetch-column.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.fetch-column%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.fetch-column&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.fetch-column.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google