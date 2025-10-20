---
url: https://www.php.net/manual/en/mysqli-result.fetch-all.php
scraped_at: 2025-10-20T02:47:34.764Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::fetch\_all

# mysqli\_fetch\_all

(PHP 5 >= 5.3.0, PHP 7, PHP 8)

mysqli\_result::fetch\_all \-\- mysqli\_fetch\_all — Fetch all result rows as an associative array, a numeric array, or both

### Description [¶](https://www.php.net/manual/en/mysqli-result.fetch-all.php\#refsect1-mysqli-result.fetch-all-description)

Object-oriented style

public**mysqli\_result::fetch\_all**([int](https://www.php.net/manual/en/language.types.integer.php) `$mode` = **`[MYSQLI\_NUM](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-num)`**): [array](https://www.php.net/manual/en/language.types.array.php)

Procedural style

**mysqli\_fetch\_all**([mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) `$result`, [int](https://www.php.net/manual/en/language.types.integer.php) `$mode` = **`[MYSQLI\_NUM](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-num)`**): [array](https://www.php.net/manual/en/language.types.array.php)

Returns a two-dimensional array of all result rows
as an associative array, a numeric array, or both.


> **Note**:
>
>
> Prior to PHP 8.1.0, available only with
> [mysqlnd](https://www.php.net/manual/en/book.mysqlnd.php).

### Parameters [¶](https://www.php.net/manual/en/mysqli-result.fetch-all.php\#refsect1-mysqli-result.fetch-all-parameters)

`result`

Procedural style only: A [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)
object returned by [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php), [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
[mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php).

`mode`

This optional parameter is a constant indicating what type of array
should be produced from the current row data. The possible values for
this parameter are the constants **`[MYSQLI\_ASSOC](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-assoc)`**,
**`[MYSQLI\_NUM](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-num)`**, or **`[MYSQLI\_BOTH](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-both)`**.


### Return Values [¶](https://www.php.net/manual/en/mysqli-result.fetch-all.php\#refsect1-mysqli-result.fetch-all-returnvalues)

Returns an array of associative or numeric arrays holding result rows.


### Changelog [¶](https://www.php.net/manual/en/mysqli-result.fetch-all.php\#refsect1-mysqli-result.fetch-all-changelog)

| Version | Description |
| --- | --- |
| 8.1.0 | Now also available when linking against libmysqlclient. |

### Examples [¶](https://www.php.net/manual/en/mysqli-result.fetch-all.php\#refsect1-mysqli-result.fetch-all-examples)

**Example #1 **mysqli\_result::fetch\_all()** example**

Object-oriented style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$result = $mysqli->query("SELECT Name, CountryCode FROM City ORDER BY ID LIMIT 3");
$rows = $result->fetch_all(MYSQLI_ASSOC);
foreach ($rows as $row) {
    printf("%s (%s)\n", $row["Name"], $row["CountryCode"]);
}`

Procedural style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = mysqli_connect("localhost", "my_user", "my_password", "world");
$result = mysqli_query($mysqli, "SELECT Name, CountryCode FROM City ORDER BY ID LIMIT 3");
$rows = mysqli_fetch_all($result, MYSQLI_ASSOC);
foreach ($rows as $row) {
    printf("%s (%s)\n", $row["Name"], $row["CountryCode"]);
}`

The above examples will output:

```
Kabul (AFG)
Qandahar (AFG)
Herat (AFG)
```

### See Also [¶](https://www.php.net/manual/en/mysqli-result.fetch-all.php\#refsect1-mysqli-result.fetch-all-seealso)

- [mysqli\_fetch\_array()](https://www.php.net/manual/en/mysqli-result.fetch-array.php) \- Fetch the next row of a result set as an associative, a numeric array, or both
- [mysqli\_fetch\_column()](https://www.php.net/manual/en/mysqli-result.fetch-column.php) \- Fetch a single column from the next row of a result set
- [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php) \- Performs a query on the database

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/fetch-all.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.fetch-all%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.fetch-all&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.fetch-all.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=116673&page=mysqli-result.fetch-all&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116673&page=mysqli-result.fetch-all&vote=down "Vote down!")

95


[**_jcastro at eftec dot cl_**](https://www.php.net/manual/en/mysqli-result.fetch-all.php#116673) [¶](https://www.php.net/manual/en/mysqli-result.fetch-all.php#116673)

**10 years ago**

`I tested using "fetch all" versus "while / fetch array" and :
fetch-all uses less memory (but not for so much).
In my case (test1 and test2): 147008,262848 bytes (fetch-all) versus 147112,262888 bytes (fetch-array & while.
So, about the memory, in both cases are the same.
However, about the performance
My test takes :350ms (worst case) using fetch-all, while it takes 464ms (worst case) using fetch-array, or about 35% worst using fetch array and a while cycle.
So, using fetch-all, for a normal code that returns a moderate amount of information is :
a) cleaner (a single line of code)
b) uses less memory (about 0.01% less)
c) faster.
php 5.6 32bits, windows 8.1 64bits`

[up](https://www.php.net/manual/vote-note.php?id=128928&page=mysqli-result.fetch-all&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128928&page=mysqli-result.fetch-all&vote=down "Vote down!")

4


[**_darek334 at gazeta dot pl_**](https://www.php.net/manual/en/mysqli-result.fetch-all.php#128928) [¶](https://www.php.net/manual/en/mysqli-result.fetch-all.php#128928)

**2 years ago**

`be careful fetch_all(MYSQLI_ASSOC ) returns an array in the form
<?php
array(0 => array(...row...), 1 => array(...row...) .... ), even if is one row...
?>
not compared to fetch_assoc() which returns one array of the result in form:
<?php
array(...row...)
?>`

[up](https://www.php.net/manual/vote-note.php?id=123871&page=mysqli-result.fetch-all&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123871&page=mysqli-result.fetch-all&vote=down "Vote down!")

7


[**_mail2magvay at rambler dot ru_**](https://www.php.net/manual/en/mysqli-result.fetch-all.php#123871) [¶](https://www.php.net/manual/en/mysqli-result.fetch-all.php#123871)

**6 years ago**

`By the way, this case pretty work's too:
$services = $mysqli->query("SELECT * FROM table1");
if($services && $services->num_rows>0){
    $services->fetch_all(MYSQLI_ASSOC);
}
foreach($services as $service){
    echo $service; //work properly, cause it implements Iterator
}
That's mean in this case $services is a valid array (or empty array)`

[up](https://www.php.net/manual/vote-note.php?id=107983&page=mysqli-result.fetch-all&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107983&page=mysqli-result.fetch-all&vote=down "Vote down!")

5


[**_m dot amiot at otak-arts dot com_**](https://www.php.net/manual/en/mysqli-result.fetch-all.php#107983) [¶](https://www.php.net/manual/en/mysqli-result.fetch-all.php#107983)

**13 years ago**

`If you really need this function, you can just extend the mysqli_result class with a function like this one.
<?php
        public function fetch_all($resulttype = MYSQLI_NUM)
        {
            if (method_exists('mysqli_result', 'fetch_all')) # Compatibility layer with PHP < 5.3
                $res = parent::fetch_all($resulttype);
            else
                for ($res = array(); $tmp = $this->fetch_array($resulttype);) $res[] = $tmp;
            return $res;
        }
?>`

[up](https://www.php.net/manual/vote-note.php?id=99314&page=mysqli-result.fetch-all&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99314&page=mysqli-result.fetch-all&vote=down "Vote down!")

 -3


[**_andrey at php dot net_**](https://www.php.net/manual/en/mysqli-result.fetch-all.php#99314) [¶](https://www.php.net/manual/en/mysqli-result.fetch-all.php#99314)

**15 years ago**

`Return value changed in 5.3.3 - between 5.3.0 and 5.3.2 (incl.) when the result set was empty NULL was returned. 5.3.3+ returns an empty array.
Also, mysqli_fetch_all works only for buffered result sets, which are the default for mysqli_query. MYSQLI_USE_RESULT will be supported in 5.3.4+
However, it makes little sense to use it this way, materialising unbuffered sets. In this case choose STORE_RESULT, and fetch_all won't copy the data, but reference it, as it is stored already in mysqlnd.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.fetch-all&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.fetch-all.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google