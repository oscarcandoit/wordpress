---
url: https://www.php.net/manual/en/mysqli-result.lengths.php
scraped_at: 2025-10-20T02:37:20.050Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::$lengths

# mysqli\_fetch\_lengths

(PHP 5, PHP 7, PHP 8)

mysqli\_result::$lengths \-\- mysqli\_fetch\_lengths — Returns the lengths of the columns of the current row in the result set

### Description [¶](https://www.php.net/manual/en/mysqli-result.lengths.php\#refsect1-mysqli-result.lengths-description)

Object-oriented style

?[array](https://www.php.net/manual/en/language.types.array.php)[$mysqli\_result->lengths](https://www.php.net/manual/en/mysqli-result.lengths.php);

Procedural style

**mysqli\_fetch\_lengths**([mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) `$result`): [array](https://www.php.net/manual/en/language.types.array.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

The **mysqli\_fetch\_lengths()** function returns an array
containing the lengths of every column of the current row within the result
set.


### Parameters [¶](https://www.php.net/manual/en/mysqli-result.lengths.php\#refsect1-mysqli-result.lengths-parameters)

`result`

Procedural style only: A [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)
object returned by [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php), [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
[mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php).

### Return Values [¶](https://www.php.net/manual/en/mysqli-result.lengths.php\#refsect1-mysqli-result.lengths-returnvalues)

An array of integers representing the size of each column (not including
any terminating null characters). **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if an error occurred.


**mysqli\_fetch\_lengths()** is valid only for the current
row of the result set. It returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if you call it before calling
mysqli\_fetch\_row/array/object or after retrieving all rows in the result.


### Examples [¶](https://www.php.net/manual/en/mysqli-result.lengths.php\#refsect1-mysqli-result.lengths-examples)

**Example #1 Object-oriented style**

`<?php
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
/* check connection */
if (mysqli_connect_errno()) {
    printf("Connect failed: %s\n", mysqli_connect_error());
    exit();
}
$query = "SELECT * from Country ORDER BY Code LIMIT 1";
if ($result = $mysqli->query($query)) {
    $row = $result->fetch_row();
    /* display column lengths */
    foreach ($result->lengths as $i => $val) {
        printf("Field %2d has Length %2d\n", $i+1, $val);
    }
    $result->close();
}
/* close connection */
$mysqli->close();
?>`

**Example #2 Procedural style**

`<?php
$link = mysqli_connect("localhost", "my_user", "my_password", "world");
/* check connection */
if (mysqli_connect_errno()) {
    printf("Connect failed: %s\n", mysqli_connect_error());
    exit();
}
$query = "SELECT * from Country ORDER BY Code LIMIT 1";
if ($result = mysqli_query($link, $query)) {
    $row = mysqli_fetch_row($result);
    /* display column lengths */
    foreach (mysqli_fetch_lengths($result) as $i => $val) {
        printf("Field %2d has Length %2d\n", $i+1, $val);
    }
    mysqli_free_result($result);
}
/* close connection */
mysqli_close($link);
?>`

The above examples will output:

```
Field  1 has Length  3
Field  2 has Length  5
Field  3 has Length 13
Field  4 has Length  9
Field  5 has Length  6
Field  6 has Length  1
Field  7 has Length  6
Field  8 has Length  4
Field  9 has Length  6
Field 10 has Length  6
Field 11 has Length  5
Field 12 has Length 44
Field 13 has Length  7
Field 14 has Length  3
Field 15 has Length  2
```

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/lengths.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.lengths%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.lengths&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.lengths.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google