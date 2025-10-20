---
url: https://www.php.net/manual/en/mysqli-result.num-rows.php
scraped_at: 2025-10-20T02:38:57.458Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::$num\_rows

# mysqli\_num\_rows

(PHP 5, PHP 7, PHP 8)

mysqli\_result::$num\_rows \-\- mysqli\_num\_rows — Gets the number of rows in the result set

### Description [¶](https://www.php.net/manual/en/mysqli-result.num-rows.php\#refsect1-mysqli-result.num-rows-description)

Object-oriented style

[int](https://www.php.net/manual/en/language.types.integer.php)\|[string](https://www.php.net/manual/en/language.types.string.php)[$mysqli\_result->num\_rows](https://www.php.net/manual/en/mysqli-result.num-rows.php);

Procedural style

**mysqli\_num\_rows**([mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) `$result`): [int](https://www.php.net/manual/en/language.types.integer.php)\|[string](https://www.php.net/manual/en/language.types.string.php)

Returns the number of rows in the result set.


The behaviour of **mysqli\_num\_rows()** depends on whether
buffered or unbuffered result sets are being used.
This function returns `0` for unbuffered result sets unless
all rows have been fetched from the server.


### Parameters [¶](https://www.php.net/manual/en/mysqli-result.num-rows.php\#refsect1-mysqli-result.num-rows-parameters)

`result`

Procedural style only: A [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)
object returned by [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php), [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
[mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php).

### Return Values [¶](https://www.php.net/manual/en/mysqli-result.num-rows.php\#refsect1-mysqli-result.num-rows-returnvalues)

An [int](https://www.php.net/manual/en/language.types.integer.php) representing the number of fetched rows.
Returns `0` in unbuffered mode unless all rows have been
fetched from the server.


> **Note**:
>
> If the number of rows is greater than **`[PHP\_INT\_MAX](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-max)`**,
> the number will be returned as a [string](https://www.php.net/manual/en/language.types.string.php).

### Examples [¶](https://www.php.net/manual/en/mysqli-result.num-rows.php\#refsect1-mysqli-result.num-rows-examples)

**Example #1 Object-oriented style**

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$result = $mysqli->query("SELECT Code, Name FROM Country ORDER BY Name");
/* Get the number of rows in the result set */
$row_cnt = $result->num_rows;
printf("Result set has %d rows.\n", $row_cnt);`

**Example #2 Procedural style**

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$link = mysqli_connect("localhost", "my_user", "my_password", "world");
$result = mysqli_query($link, "SELECT Code, Name FROM Country ORDER BY Name");
/* Get the number of rows in the result set */
$row_cnt = mysqli_num_rows($result);
printf("Result set has %d rows.\n", $row_cnt);`

The above examples will output:

```
Result set has 239 rows.
```

### Notes [¶](https://www.php.net/manual/en/mysqli-result.num-rows.php\#refsect1-mysqli-result.num-rows-notes)

> **Note**:
>
>
> In contrast to the [mysqli\_stmt\_num\_rows()](https://www.php.net/manual/en/mysqli-stmt.num-rows.php) function,
> this function doesn't have object-oriented method variant.
> In the object-oriented style, use the getter property.

### See Also [¶](https://www.php.net/manual/en/mysqli-result.num-rows.php\#refsect1-mysqli-result.num-rows-seealso)

- [mysqli\_affected\_rows()](https://www.php.net/manual/en/mysqli.affected-rows.php) \- Gets the number of affected rows in a previous MySQL operation
- [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php) \- Transfers a result set from the last query
- [mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) \- Initiate a result set retrieval
- [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php) \- Performs a query on the database
- [mysqli\_stmt\_num\_rows()](https://www.php.net/manual/en/mysqli-stmt.num-rows.php) \- Returns the number of rows fetched from the server

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/num-rows.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.num-rows%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.num-rows&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.num-rows.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=105289&page=mysqli-result.num-rows&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105289&page=mysqli-result.num-rows&vote=down "Vote down!")

116


[**_borisigna_**](https://www.php.net/manual/en/mysqli-result.num-rows.php#105289) [¶](https://www.php.net/manual/en/mysqli-result.num-rows.php#105289)

**14 years ago**

`If you have problems making work this num_rows, you have to declare ->store_result() first.
<?php
$mysqli = new mysqli("localhost","root", "", "tables");
$query = $mysqli->prepare("SELECT * FROM table1");
$query->execute();
$query->store_result();
$rows = $query->num_rows;
echo $rows;
// Return 4 for example
?>`

[up](https://www.php.net/manual/vote-note.php?id=121078&page=mysqli-result.num-rows&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121078&page=mysqli-result.num-rows&vote=down "Vote down!")

2


[**_min0u_**](https://www.php.net/manual/en/mysqli-result.num-rows.php#121078) [¶](https://www.php.net/manual/en/mysqli-result.num-rows.php#121078)

**8 years ago**

`This function doesn't work with LIMIT used jointly with SQL_CALC_FOUND_ROWS. If you want to obtain the total rows found you must do it manually, example:
<?php
public function errorList(int $limit=25,int $offset=0){
        $errorList = array();
        $result = $this->con->query("SELECT SQL_CALC_FOUND_ROWS id, erreur FROM Erreurs ORDER BY id DESC LIMIT $limit OFFSET $offset");
        while($row = $result->fetch_assoc()){
            $errorList[] = new Erreur($row);
        }
        $result->free();
        // $foundRows = $result->num_rows; // 25
        $foundRows = $this->con->query("SELECT FOUND_ROWS() as foundRows");
        $this->foundRows = $foundRows->fetch_assoc(); // 178
        return $errorList;
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.num-rows&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.num-rows.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google