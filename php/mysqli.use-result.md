---
url: https://www.php.net/manual/en/mysqli.use-result.php
scraped_at: 2025-10-20T02:32:41.794Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli::use\_result

# mysqli\_use\_result

(PHP 5, PHP 7, PHP 8)

mysqli::use\_result \-\- mysqli\_use\_result — Initiate a result set retrieval

### Description [¶](https://www.php.net/manual/en/mysqli.use-result.php\#refsect1-mysqli.use-result-description)

Object-oriented style

public**mysqli::use\_result**(): [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Procedural style

**mysqli\_use\_result**([mysqli](https://www.php.net/manual/en/class.mysqli.php) `$mysql`): [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Used to initiate the retrieval of a result set from the last query
executed using the [mysqli\_real\_query()](https://www.php.net/manual/en/mysqli.real-query.php) function on the
database connection.


Either this or the [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php) function must
be called before the results of a query can be retrieved, and one or the
other must be called to prevent the next query on that database connection
from failing.


> **Note**:
>
>
> The **mysqli\_use\_result()** function does not transfer
> the entire result set from the database and hence cannot be used functions
> such as [mysqli\_data\_seek()](https://www.php.net/manual/en/mysqli-result.data-seek.php) to move to a particular
> row within the set. To use this functionality, the result set must be
> stored using [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php). One should not
> use **mysqli\_use\_result()** if a lot of processing on
> the client side is performed, since this will tie up the server and
> prevent other threads from updating any tables from which the data is
> being fetched.

### Parameters [¶](https://www.php.net/manual/en/mysqli.use-result.php\#refsect1-mysqli.use-result-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/mysqli.use-result.php\#refsect1-mysqli.use-result-returnvalues)

Returns an unbuffered result object or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if an error occurred.


### Errors/Exceptions [¶](https://www.php.net/manual/en/mysqli.use-result.php\#refsect1-mysqli.use-result-errors)

If mysqli error reporting is enabled ( **`[MYSQLI\_REPORT\_ERROR](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-error)`**) and the requested operation fails,
a warning is generated. If, in addition, the mode is set to **`[MYSQLI\_REPORT\_STRICT](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-strict)`**,
a [mysqli\_sql\_exception](https://www.php.net/manual/en/class.mysqli-sql-exception.php) is thrown instead.

### Examples [¶](https://www.php.net/manual/en/mysqli.use-result.php\#refsect1-mysqli.use-result-examples)

**Example #1 **mysqli::use\_result()** example**

Object-oriented style

`<?php
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
/* check connection */
if (mysqli_connect_errno()) {
    printf("Connect failed: %s\n", mysqli_connect_error());
    exit();
}
$query  = "SELECT CURRENT_USER();";
$query .= "SELECT Name FROM City ORDER BY ID LIMIT 20, 5";
/* execute multi query */
if ($mysqli->multi_query($query)) {
    do {
        /* store first result set */
        if ($result = $mysqli->use_result()) {
            while ($row = $result->fetch_row()) {
                printf("%s\n", $row[0]);
            }
            $result->close();
        }
        /* print divider */
        if ($mysqli->more_results()) {
            printf("-----------------\n");
        }
    } while ($mysqli->next_result());
}
/* close connection */
$mysqli->close();
?>`

Procedural style

`<?php
$link = mysqli_connect("localhost", "my_user", "my_password", "world");
/* check connection */
if (mysqli_connect_errno()) {
    printf("Connect failed: %s\n", mysqli_connect_error());
    exit();
}
$query  = "SELECT CURRENT_USER();";
$query .= "SELECT Name FROM City ORDER BY ID LIMIT 20, 5";
/* execute multi query */
if (mysqli_multi_query($link, $query)) {
    do {
        /* store first result set */
        if ($result = mysqli_use_result($link)) {
            while ($row = mysqli_fetch_row($result)) {
                printf("%s\n", $row[0]);
            }
            mysqli_free_result($result);
        }
        /* print divider */
        if (mysqli_more_results($link)) {
            printf("-----------------\n");
        }
    } while (mysqli_next_result($link));
}
/* close connection */
mysqli_close($link);
?>`

The above examples will output:

```
my_user@localhost
-----------------
Amersfoort
Maastricht
Dordrecht
Leiden
Haarlemmermeer
```

### See Also [¶](https://www.php.net/manual/en/mysqli.use-result.php\#refsect1-mysqli.use-result-seealso)

- [mysqli\_real\_query()](https://www.php.net/manual/en/mysqli.real-query.php) \- Execute an SQL query
- [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php) \- Transfers a result set from the last query

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli/use-result.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli.use-result%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli.use-result&repo=en&redirect=https://www.php.net/manual/en/mysqli.use-result.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=110044&page=mysqli.use-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110044&page=mysqli.use-result&vote=down "Vote down!")

3


[**_Anonymous_**](https://www.php.net/manual/en/mysqli.use-result.php#110044) [¶](https://www.php.net/manual/en/mysqli.use-result.php#110044)

**13 years ago**

``> One should not use mysqli_use_result() if a lot of processing on the client side is performed, since this will tie up the server and prevent other threads from updating any tables from which the data is being fetched.
Another way of understanding the "blocking" behavior of this "use_result" method is that by using this method (or the MYSQLI_USE_RESULT flag on the "query" method), if attempting to run a second query of any kind - updates, inserts, selects, or other - while still working with these first results, the second query will fail.  Checking mysqli->error, you should get a "Commands out of sync" error on the second query call.
However, if you use the "store_result" method (or the default MYSQLI_STORE_RESULT flag on the "query" method) instead, the second query will execute just fine.
Just to demonstrate this "blocking" behavior of this "use_result" method, the second query on line 7 below would otherwise fail if you instead used "use_result" on line 3:
<?php
$mysqli->real_query('SELECT * FROM `test`');
$query = $mysqli->store_result();
while ($row = $query->fetch_assoc()) {
    $id = (int) $row['id'];
    $query2 = $mysqli->query("UPDATE `test` SET `label` = md5(rand()) WHERE `id` = $id");
}
?>``

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli.use-result&repo=en&redirect=https://www.php.net/manual/en/mysqli.use-result.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google