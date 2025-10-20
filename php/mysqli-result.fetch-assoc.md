---
url: https://www.php.net/manual/en/mysqli-result.fetch-assoc.php
scraped_at: 2025-10-20T02:38:14.143Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::fetch\_assoc

# mysqli\_fetch\_assoc

(PHP 5, PHP 7, PHP 8)

mysqli\_result::fetch\_assoc \-\- mysqli\_fetch\_assoc — Fetch the next row of a result set as an associative array

### Description [¶](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php\#refsect1-mysqli-result.fetch-assoc-description)

Object-oriented style

public**mysqli\_result::fetch\_assoc**(): [array](https://www.php.net/manual/en/language.types.array.php)\|[null](https://www.php.net/manual/en/language.types.null.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Procedural style

**mysqli\_fetch\_assoc**([mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) `$result`): [array](https://www.php.net/manual/en/language.types.array.php)\|[null](https://www.php.net/manual/en/language.types.null.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Fetches one row of data from the result set and returns it as an associative
array.
Each subsequent call to this function will return the next row within the
result set, or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** if there are no more rows.


If two or more columns of the result have the same name, the last
column will take precedence and overwrite any previous data. To
access multiple columns with the same name,
[mysqli\_fetch\_row()](https://www.php.net/manual/en/mysqli-result.fetch-row.php) may be used to fetch the numerically
indexed array, or aliases may be used in the SQL query select list to give
columns different names.


> **Note**: Field names returned by this function
> are _case-sensitive_.

> **Note**: This function sets NULL fields to
> the PHP **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** value.

### Parameters [¶](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php\#refsect1-mysqli-result.fetch-assoc-parameters)

`result`

Procedural style only: A [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)
object returned by [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php), [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
[mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php).

### Return Values [¶](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php\#refsect1-mysqli-result.fetch-assoc-returnvalues)

Returns an associative array representing the fetched row,
where each key in the array represents the name of one of the result
set's columns, **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** if there
are no more rows in the result set, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php\#refsect1-mysqli-result.fetch-assoc-examples)

**Example #1 **mysqli\_result::fetch\_assoc()** example**

Object-oriented style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$query = "SELECT Name, CountryCode FROM City ORDER BY ID DESC";
$result = $mysqli->query($query);
/* fetch associative array */
while ($row = $result->fetch_assoc()) {
    printf("%s (%s)\n", $row["Name"], $row["CountryCode"]);
}`

Procedural style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = mysqli_connect("localhost", "my_user", "my_password", "world");
$query = "SELECT Name, CountryCode FROM City ORDER BY ID DESC";
$result = mysqli_query($mysqli, $query);
/* fetch associative array */
while ($row = mysqli_fetch_assoc($result)) {
    printf("%s (%s)\n", $row["Name"], $row["CountryCode"]);
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

**Example #2 Comparison of [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)[iterator](https://www.php.net/manual/en/class.iterator.php) and **mysqli\_result::fetch\_assoc()** usage**

[mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) can be iterated using [`foreach`](https://www.php.net/manual/en/control-structures.foreach.php).
The result set will always be iterated from the first row, regardless of the current position.


`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$query = 'SELECT Name, CountryCode FROM City ORDER BY ID DESC';
// Using iterators
$result = $mysqli->query($query);
foreach ($result as $row) {
    printf("%s (%s)\n", $row["Name"], $row["CountryCode"]);
}
echo "\n==================\n";
// Not using iterators
$result = $mysqli->query($query);
while ($row = $result->fetch_assoc()) {
    printf("%s (%s)\n", $row["Name"], $row["CountryCode"]);
}`

The above example will output
something similar to:

```
Pueblo (USA)
Arvada (USA)
Cape Coral (USA)
Green Bay (USA)
Santa Clara (USA)

==================
Pueblo (USA)
Arvada (USA)
Cape Coral (USA)
Green Bay (USA)
Santa Clara (USA)
```

### See Also [¶](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php\#refsect1-mysqli-result.fetch-assoc-seealso)

- [mysqli\_fetch\_array()](https://www.php.net/manual/en/mysqli-result.fetch-array.php) \- Fetch the next row of a result set as an associative, a numeric array, or both
- [mysqli\_fetch\_column()](https://www.php.net/manual/en/mysqli-result.fetch-column.php) \- Fetch a single column from the next row of a result set
- [mysqli\_fetch\_row()](https://www.php.net/manual/en/mysqli-result.fetch-row.php) \- Fetch the next row of a result set as an enumerated array
- [mysqli\_fetch\_object()](https://www.php.net/manual/en/mysqli-result.fetch-object.php) \- Fetch the next row of a result set as an object
- [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php) \- Performs a query on the database
- [mysqli\_data\_seek()](https://www.php.net/manual/en/mysqli-result.data-seek.php) \- Adjusts the result pointer to an arbitrary row in the result

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/fetch-assoc.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.fetch-assoc%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.fetch-assoc&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.fetch-assoc.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=112924&page=mysqli-result.fetch-assoc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112924&page=mysqli-result.fetch-assoc&vote=down "Vote down!")

87


[**_Miller_**](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php#112924) [¶](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php#112924)

**12 years ago**

``I often like to have my results sent elsewhere in the format of an array (although keep in mind that if you just plan on traversing through the array in another part of the script, this extra step is just a waste of time).
This is my one-liner for transforming a mysqli_result set into an array.
<?php
$sql = new MySQLi($host, $username, $password, $database);
$result = $sql->query("SELECT * FROM `$table`;");
for ($set = array (); $row = $result->fetch_assoc(); $set[] = $row);
print_r($set);
?>
Outputs:
Array
(
    [0] => Array
        (
            [id] => 1
            [field2] => a
            [field3] => b
        ),
    [1] => Array
        (
            [id] => 2
            [field2] => c
            [field3] => d
        )
)
I use other variations to adapt to the situation, i.e. if I am selecting only one field:
<?php
$sql = new MySQLi($host, $username, $password, $database);
$result = $sql->query("SELECT `field2` FROM `$table`;");
for ($set = array (); $row = $result->fetch_assoc(); $set[] = $row['field2']);
print_r($set);
?>
Outputs:
Array
(
    [0] => a
    [1] => c
)
Or, to make the array associative with the primary index (code assumes primary index is the first field in the table):
<?php
$sql = new MySQLi($host, $username, $password, $database);
$result = $sql->query("SELECT * FROM `$table`;");
for ($set = array (); $row = $result->fetch_assoc(); $set[array_shift($row)] = $row);
print_r($set);
?>
Outputs:
Array
(
    [1] => Array
        (
            [field2] => a
            [field3] => b
        ),
    [2] => Array
        (
            [field2] => c
            [field3] => d
        )
)``

[up](https://www.php.net/manual/vote-note.php?id=105365&page=mysqli-result.fetch-assoc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105365&page=mysqli-result.fetch-assoc&vote=down "Vote down!")

26


[**_james dot phx at gmail dot com_**](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php#105365) [¶](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php#105365)

**14 years ago**

`IMPORTANT NOTE:
If you were used to using code like this:
<?php
while(false !== ($row = mysql_fetch_assoc($result)))
{
    //...
}
?>
You must change it to this for mysqli:
<?php
while(null !== ($row = mysqli_fetch_assoc($result)))
{
    //...
}
?>
The former will cause your script to run until max_execution_time is reached.`

[up](https://www.php.net/manual/vote-note.php?id=128432&page=mysqli-result.fetch-assoc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128432&page=mysqli-result.fetch-assoc&vote=down "Vote down!")

3


[**_Enrique Garcia_**](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php#128432) [¶](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php#128432)

**2 years ago**

`There is a difference between MariaDB and MySQL(>5.4) whether the input parameter (mysqli object) has data or is empty (it comes from a previus query).
-MariaDB:  you get an exception:
Fatal error: Uncaught TypeError: mysqli_fetch_assoc(): Argument #1 ($result) must be of type mysqli_result
-MySQL: you can continue, in spite of not having data in the mysqli object.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.fetch-assoc&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.fetch-assoc.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google