---
url: https://www.php.net/manual/en/mysqli-result.current-field.php
scraped_at: 2025-10-20T02:38:36.568Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::$current\_field

# mysqli\_field\_tell

(PHP 5, PHP 7, PHP 8)

mysqli\_result::$current\_field \-\- mysqli\_field\_tell — Get current field offset of a result pointer

### Description [¶](https://www.php.net/manual/en/mysqli-result.current-field.php\#refsect1-mysqli-result.current-field-description)

Object-oriented style

[int](https://www.php.net/manual/en/language.types.integer.php)[$mysqli\_result->current\_field](https://www.php.net/manual/en/mysqli-result.current-field.php);

Procedural style

**mysqli\_field\_tell**([mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) `$result`): [int](https://www.php.net/manual/en/language.types.integer.php)

Returns the position of the field cursor used for the last
[mysqli\_fetch\_field()](https://www.php.net/manual/en/mysqli-result.fetch-field.php) call. This value can
be used as an argument to [mysqli\_field\_seek()](https://www.php.net/manual/en/mysqli-result.field-seek.php).


### Parameters [¶](https://www.php.net/manual/en/mysqli-result.current-field.php\#refsect1-mysqli-result.current-field-parameters)

`result`

Procedural style only: A [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)
object returned by [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php), [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
[mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php).

### Return Values [¶](https://www.php.net/manual/en/mysqli-result.current-field.php\#refsect1-mysqli-result.current-field-returnvalues)

Returns current offset of field cursor.


### Examples [¶](https://www.php.net/manual/en/mysqli-result.current-field.php\#refsect1-mysqli-result.current-field-examples)

**Example #1 Object-oriented style**

`<?php
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
/* check connection */
if (mysqli_connect_errno()) {
    printf("Connect failed: %s\n", mysqli_connect_error());
    exit();
}
$query = "SELECT Name, SurfaceArea from Country ORDER BY Code LIMIT 5";
if ($result = $mysqli->query($query)) {
    /* Get field information for all columns */
    while ($finfo = $result->fetch_field()) {
        /* get fieldpointer offset */
        $currentfield = $result->current_field;
        printf("Column %d:\n", $currentfield);
        printf("Name:     %s\n", $finfo->name);
        printf("Table:    %s\n", $finfo->table);
        printf("max. Len: %d\n", $finfo->max_length);
        printf("Flags:    %d\n", $finfo->flags);
        printf("Type:     %d\n\n", $finfo->type);
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
$query = "SELECT Name, SurfaceArea from Country ORDER BY Code LIMIT 5";
if ($result = mysqli_query($link, $query)) {
    /* Get field information for all fields */
    while ($finfo = mysqli_fetch_field($result)) {
        /* get fieldpointer offset */
        $currentfield = mysqli_field_tell($result);
        printf("Column %d:\n", $currentfield);
        printf("Name:     %s\n", $finfo->name);
        printf("Table:    %s\n", $finfo->table);
        printf("max. Len: %d\n", $finfo->max_length);
        printf("Flags:    %d\n", $finfo->flags);
        printf("Type:     %d\n\n", $finfo->type);
    }
    mysqli_free_result($result);
}
/* close connection */
mysqli_close($link);
?>`

The above examples will output:

```
Column 1:
Name:     Name
Table:    Country
max. Len: 11
Flags:    1
Type:     254

Column 2:
Name:     SurfaceArea
Table:    Country
max. Len: 10
Flags:    32769
Type:     4
```

### See Also [¶](https://www.php.net/manual/en/mysqli-result.current-field.php\#refsect1-mysqli-result.current-field-seealso)

- [mysqli\_fetch\_field()](https://www.php.net/manual/en/mysqli-result.fetch-field.php) \- Returns the next field in the result set
- [mysqli\_field\_seek()](https://www.php.net/manual/en/mysqli-result.field-seek.php) \- Set result pointer to a specified field offset

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/current-field.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.current-field%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.current-field&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.current-field.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google