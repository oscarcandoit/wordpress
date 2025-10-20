---
url: https://www.php.net/manual/en/mysqli.kill.php
scraped_at: 2025-10-20T02:49:58.370Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli::kill

# mysqli\_kill

(PHP 5, PHP 7, PHP 8)

mysqli::kill \-\- mysqli\_kill — Asks the server to kill a MySQL thread

**Warning**

This function has been
_DEPRECATED_ as of PHP 8.4.0. Relying on this function
is highly discouraged.

### Description [¶](https://www.php.net/manual/en/mysqli.kill.php\#refsect1-mysqli.kill-description)

Object-oriented style

[#\[\\Deprecated\]](https://www.php.net/manual/en/class.deprecated.php)

public**mysqli::kill**([int](https://www.php.net/manual/en/language.types.integer.php) `$process_id`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Procedural style

[#\[\\Deprecated\]](https://www.php.net/manual/en/class.deprecated.php)

**mysqli\_kill**([mysqli](https://www.php.net/manual/en/class.mysqli.php) `$mysql`, [int](https://www.php.net/manual/en/language.types.integer.php) `$process_id`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

This function is used to ask the server to kill a MySQL thread specified
by the `process_id` parameter. This value must be
retrieved by calling the [mysqli\_thread\_id()](https://www.php.net/manual/en/mysqli.thread-id.php) function.


To stop a running query you should use the SQL command
`KILL QUERY processid`.


### Parameters [¶](https://www.php.net/manual/en/mysqli.kill.php\#refsect1-mysqli.kill-parameters)

`mysql`

Procedural style only: A [mysqli](https://www.php.net/manual/en/class.mysqli.php) object
returned by [mysqli\_connect()](https://www.php.net/manual/en/function.mysqli-connect.php) or [mysqli\_init()](https://www.php.net/manual/en/mysqli.init.php)

### Return Values [¶](https://www.php.net/manual/en/mysqli.kill.php\#refsect1-mysqli.kill-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Errors/Exceptions [¶](https://www.php.net/manual/en/mysqli.kill.php\#refsect1-mysqli.kill-errors)

If mysqli error reporting is enabled ( **`[MYSQLI\_REPORT\_ERROR](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-error)`**) and the requested operation fails,
a warning is generated. If, in addition, the mode is set to **`[MYSQLI\_REPORT\_STRICT](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-strict)`**,
a [mysqli\_sql\_exception](https://www.php.net/manual/en/class.mysqli-sql-exception.php) is thrown instead.

### Changelog [¶](https://www.php.net/manual/en/mysqli.kill.php\#refsect1-mysqli.kill-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Both **mysqli::kill()** and<br> **mysqli\_kill()** are now deprecated. Use the<br> `KILL` SQL command instead. |

### Examples [¶](https://www.php.net/manual/en/mysqli.kill.php\#refsect1-mysqli.kill-examples)

**Example #1 **mysqli::kill()** example**

Object-oriented style

`<?php
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
/* check connection */
if (mysqli_connect_errno()) {
    printf("Connect failed: %s\n", mysqli_connect_error());
    exit();
}
/* determine our thread id */
$thread_id = $mysqli->thread_id;
/* Kill connection */
$mysqli->kill($thread_id);
/* This should produce an error */
if (!$mysqli->query("CREATE TABLE myCity LIKE City")) {
    printf("Error: %s\n", $mysqli->error);
    exit;
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
/* determine our thread id */
$thread_id = mysqli_thread_id($link);
/* Kill connection */
mysqli_kill($link, $thread_id);
/* This should produce an error */
if (!mysqli_query($link, "CREATE TABLE myCity LIKE City")) {
    printf("Error: %s\n", mysqli_error($link));
    exit;
}
/* close connection */
mysqli_close($link);
?>`

The above examples will output:

```
Error: MySQL server has gone away
```

### See Also [¶](https://www.php.net/manual/en/mysqli.kill.php\#refsect1-mysqli.kill-seealso)

- [mysqli\_thread\_id()](https://www.php.net/manual/en/mysqli.thread-id.php) \- Returns the thread ID for the current connection

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli/kill.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli.kill%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli.kill&repo=en&redirect=https://www.php.net/manual/en/mysqli.kill.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google