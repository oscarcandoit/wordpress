---
url: https://www.php.net/manual/en/mysqli-result.data-seek.php
scraped_at: 2025-10-20T02:42:54.266Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::data\_seek

# mysqli\_data\_seek

(PHP 5, PHP 7, PHP 8)

mysqli\_result::data\_seek \-\- mysqli\_data\_seek — Adjusts the result pointer to an arbitrary row in the result

### Description [¶](https://www.php.net/manual/en/mysqli-result.data-seek.php\#refsect1-mysqli-result.data-seek-description)

Object-oriented style

public**mysqli\_result::data\_seek**([int](https://www.php.net/manual/en/language.types.integer.php) `$offset`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Procedural style

**mysqli\_data\_seek**([mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) `$result`, [int](https://www.php.net/manual/en/language.types.integer.php) `$offset`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

The **mysqli\_data\_seek()** function seeks to an arbitrary
result pointer specified by the `offset` in the
result set.


### Parameters [¶](https://www.php.net/manual/en/mysqli-result.data-seek.php\#refsect1-mysqli-result.data-seek-parameters)

`result`

Procedural style only: A [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)
object returned by [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php), [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
[mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php).

`offset`

The row offset. Must be between zero and the total number of rows
minus one (0..[mysqli\_num\_rows()](https://www.php.net/manual/en/mysqli-result.num-rows.php) \- 1).


### Return Values [¶](https://www.php.net/manual/en/mysqli-result.data-seek.php\#refsect1-mysqli-result.data-seek-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/mysqli-result.data-seek.php\#refsect1-mysqli-result.data-seek-examples)

**Example #1 **mysqli::data\_seek()** example**

Object-oriented style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$query = "SELECT Name, CountryCode FROM City ORDER BY Name";
$result = $mysqli->query($query);
/* Seek to row no. 401 */
$result->data_seek(400);
/* Fetch single row */
$row = $result->fetch_row();
printf("City: %s  Countrycode: %s\n", $row[0], $row[1]);`

Procedural style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$link = mysqli_connect("localhost", "my_user", "my_password", "world");
$query = "SELECT Name, CountryCode FROM City ORDER BY Name";
$result = mysqli_query($link, $query);
/* Seek to row no. 401 */
mysqli_data_seek($result, 400);
/* Fetch single row */
$row = mysqli_fetch_row($result);
printf ("City: %s  Countrycode: %s\n", $row[0], $row[1]);`

The above examples will output:

```
City: Benin City  Countrycode: NGA
```

**Example #2 Adjusting the result pointer when iterating**

This function can be useful when iterating over the result set to impose
a custom order or rewind the result set when iterating multiple times.


`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$query = "SELECT Name, CountryCode FROM City ORDER BY Name LIMIT 15,4";
$result = $mysqli->query($query);
/* Iterate the result set in reverse order */
for ($row_no = $result->num_rows - 1; $row_no >= 0; $row_no--) {
    $result->data_seek($row_no);
    /* Fetch single row */
    $row = $result->fetch_row();
    printf("City: %s  Countrycode: %s\n", $row[0], $row[1]);
}
/* Reset pointer to the beginning of the result set */
$result->data_seek(0);
print "\n";
/* Iterate the same result set again */
while ($row = $result->fetch_row()) {
    printf("City: %s  Countrycode: %s\n", $row[0], $row[1]);
}`

The above examples will output:

```
City: Acmbaro  Countrycode: MEX
City: Abuja  Countrycode: NGA
City: Abu Dhabi  Countrycode: ARE
City: Abottabad  Countrycode: PAK

City: Abottabad  Countrycode: PAK
City: Abu Dhabi  Countrycode: ARE
City: Abuja  Countrycode: NGA
City: Acmbaro  Countrycode: MEX
```

### Notes [¶](https://www.php.net/manual/en/mysqli-result.data-seek.php\#refsect1-mysqli-result.data-seek-notes)

> **Note**:
>
>
> This function can only be used with buffered results attained from the
> use of the [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
> [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php) functions.

### See Also [¶](https://www.php.net/manual/en/mysqli-result.data-seek.php\#refsect1-mysqli-result.data-seek-seealso)

- [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php) \- Transfers a result set from the last query
- [mysqli\_fetch\_row()](https://www.php.net/manual/en/mysqli-result.fetch-row.php) \- Fetch the next row of a result set as an enumerated array
- [mysqli\_fetch\_array()](https://www.php.net/manual/en/mysqli-result.fetch-array.php) \- Fetch the next row of a result set as an associative, a numeric array, or both
- [mysqli\_fetch\_assoc()](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php) \- Fetch the next row of a result set as an associative array
- [mysqli\_fetch\_object()](https://www.php.net/manual/en/mysqli-result.fetch-object.php) \- Fetch the next row of a result set as an object
- [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php) \- Performs a query on the database
- [mysqli\_num\_rows()](https://www.php.net/manual/en/mysqli-result.num-rows.php) \- Gets the number of rows in the result set

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/data-seek.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.data-seek%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.data-seek&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.data-seek.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google