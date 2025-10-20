---
url: https://www.php.net/manual/en/mysqli-result.construct.php
scraped_at: 2025-10-20T02:39:24.712Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::\_\_construct

(PHP 5, PHP 7, PHP 8)

mysqli\_result::\_\_construct — Constructs a [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) object

### Description [¶](https://www.php.net/manual/en/mysqli-result.construct.php\#refsect1-mysqli-result.construct-description)

public**mysqli\_result::\_\_construct**([mysqli](https://www.php.net/manual/en/class.mysqli.php) `$mysql`, [int](https://www.php.net/manual/en/language.types.integer.php) `$result_mode` = **`[MYSQLI\_STORE\_RESULT](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-store-result)`**)

This method constructs a new [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) object.


It can be used to create the [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) object
after calling the [mysqli\_real\_query()](https://www.php.net/manual/en/mysqli.real-query.php) or
[mysqli\_multi\_query()](https://www.php.net/manual/en/mysqli.multi-query.php) function. Constructing the object
manually is equivalent to calling the [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php)
or [mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) function.


### Parameters [¶](https://www.php.net/manual/en/mysqli-result.construct.php\#refsect1-mysqli-result.construct-parameters)

`mysql`

Procedural style only: A [mysqli](https://www.php.net/manual/en/class.mysqli.php) object
returned by [mysqli\_connect()](https://www.php.net/manual/en/function.mysqli-connect.php) or [mysqli\_init()](https://www.php.net/manual/en/mysqli.init.php)

`result_mode`

The result mode can be one of 2 constants indicating how the result will
be returned from the MySQL server.


**`[MYSQLI\_STORE\_RESULT](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-store-result)`** (default) - creates a
[mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) object with buffered result set.


**`[MYSQLI\_USE\_RESULT](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-use-result)`** \- creates a
[mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) object with unbuffered result set.
As long as there are pending records waiting to be fetched, the
connection line will be busy and all subsequent calls will return error
`Commands out of sync`. To avoid the error all records
must be fetched from the server or the result set must be discarded by
calling [mysqli\_free\_result()](https://www.php.net/manual/en/mysqli-result.free.php). The connection must
remain open for the rows to be fetched.


### Errors/Exceptions [¶](https://www.php.net/manual/en/mysqli-result.construct.php\#refsect1-mysqli-result.construct-errors)

If mysqli error reporting is enabled ( **`[MYSQLI\_REPORT\_ERROR](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-error)`**) and the requested operation fails,
a warning is generated. If, in addition, the mode is set to **`[MYSQLI\_REPORT\_STRICT](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-strict)`**,
a [mysqli\_sql\_exception](https://www.php.net/manual/en/class.mysqli-sql-exception.php) is thrown instead.

### Examples [¶](https://www.php.net/manual/en/mysqli-result.construct.php\#refsect1-mysqli-result.construct-examples)

**Example #1 Creation of a [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) object**

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
/* Select queries return a result set */
$mysqli->real_query("SELECT Name FROM City LIMIT 10");
$result = new mysqli_result($mysqli);
printf("Select returned %d rows.\n", $result->num_rows);`

The above examples will output
something similar to:

```
Select returned 10 rows.
```

### See Also [¶](https://www.php.net/manual/en/mysqli-result.construct.php\#refsect1-mysqli-result.construct-seealso)

- [mysqli\_multi\_query()](https://www.php.net/manual/en/mysqli.multi-query.php) \- Performs one or more queries on the database
- [mysqli\_real\_query()](https://www.php.net/manual/en/mysqli.real-query.php) \- Execute an SQL query
- [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php) \- Transfers a result set from the last query
- [mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) \- Initiate a result set retrieval

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/construct.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.construct%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.construct&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.construct.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google