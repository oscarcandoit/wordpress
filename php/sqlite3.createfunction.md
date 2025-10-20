---
url: https://www.php.net/manual/en/sqlite3.createfunction.php
scraped_at: 2025-10-20T02:59:39.116Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# SQLite3::createFunction

(PHP 5 >= 5.3.0, PHP 7, PHP 8)

SQLite3::createFunction — Registers a PHP function for use as an SQL scalar function

### Description [¶](https://www.php.net/manual/en/sqlite3.createfunction.php\#refsect1-sqlite3.createfunction-description)

public**SQLite3::createFunction**(

[string](https://www.php.net/manual/en/language.types.string.php) `$name`,

[callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$argCount` = -1,

[int](https://www.php.net/manual/en/language.types.integer.php) `$flags` = 0

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Registers a PHP function or user-defined function for use as an SQL scalar
function for use within SQL statements.


### Parameters [¶](https://www.php.net/manual/en/sqlite3.createfunction.php\#refsect1-sqlite3.createfunction-parameters)

`name`

Name of the SQL function to be created or redefined.


`callback`

The name of a PHP function or user-defined function to apply as a
callback, defining the behavior of the SQL function.


This function need to be defined as:


callback([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$value`, [mixed](https://www.php.net/manual/en/language.types.mixed.php) `...$values`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

`value`

The first argument passed to the SQL function.


`values`

Further arguments passed to the SQL function.


`argCount`

The number of arguments that the SQL function takes. If
this parameter is `-1`, then the SQL function may take
any number of arguments.


`flags`

A bitwise conjunction of flags. Currently, only
**`[SQLITE3\_DETERMINISTIC](https://www.php.net/manual/en/sqlite3.constants.php#constant.sqlite3-deterministic)`** is supported, which specifies
that the function always returns the same result given the same inputs
within a single SQL statement.


### Return Values [¶](https://www.php.net/manual/en/sqlite3.createfunction.php\#refsect1-sqlite3.createfunction-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** upon successful creation of the function, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Changelog [¶](https://www.php.net/manual/en/sqlite3.createfunction.php\#refsect1-sqlite3.createfunction-changelog)

| Version | Description |
| --- | --- |
| 7.1.4 | The `flags` parameter has been added. |

### Examples [¶](https://www.php.net/manual/en/sqlite3.createfunction.php\#refsect1-sqlite3.createfunction-examples)

**Example #1 **SQLite3::createFunction()** example**

`<?php
function my_udf_md5($string) {
    return hash('md5', $string);
}
$db = new SQLite3('mysqlitedb.db');
$db->createFunction('my_udf_md5', 'my_udf_md5');
var_dump($db->querySingle('SELECT my_udf_md5("test")'));
?>`

The above example will output
something similar to:

```
string(32) "098f6bcd4621d373cade4e832627b4f6"
```

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/sqlite3/sqlite3/createfunction.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsqlite3.createfunction%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=sqlite3.createfunction&repo=en&redirect=https://www.php.net/manual/en/sqlite3.createfunction.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=98110&page=sqlite3.createfunction&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=98110&page=sqlite3.createfunction&vote=down "Vote down!")

10


[**_koalay at gmail dot com_**](https://www.php.net/manual/en/sqlite3.createfunction.php#98110) [¶](https://www.php.net/manual/en/sqlite3.createfunction.php#98110)

**15 years ago**

`Since regular expression is not supported by default SQLite, we can create a user function to do the job.
<?php
$db = new SQLite3("database.sqlit3", 0666);
// create a function named "preg_match"
// with the php core function "preg_match"
if ($db->createFunction("preg_match", "preg_match", 2) === FALSE)
exit("Failed creating function\n");
// this query will then works as expected
$result = $db->query("SELECT * FROM table1 WHERE
preg_match('/^(apple|orange)$/', variable1)");
?>`

[up](https://www.php.net/manual/vote-note.php?id=107707&page=sqlite3.createfunction&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107707&page=sqlite3.createfunction&vote=down "Vote down!")

 -1


[**_bohwaz_**](https://www.php.net/manual/en/sqlite3.createfunction.php#107707) [¶](https://www.php.net/manual/en/sqlite3.createfunction.php#107707)

**13 years ago**

`In PHP 5.4 there will be a createCollation method to use your custom collation method, to be able to sort datasets using unicode, like this:
<?php
setlocale(LC_COLLATE, 'fr_FR.UTF-8');
$db->createCollation('PHP_COLLATE', 'strcoll');
$db->query('SELECT * FROM my_table ORDER BY name COLLATE PHP_COLLATE;');
?>
But until this cool feature becomes available, you'll have to do some tricks, like this for french:
<?php
function sqlite3_to_ascii($str, $charset = 'UTF-8')
{
    // Don't process empty strings
    if (!trim($str))
        return $str;
    // We only process non-ascii strings
    if (preg_match('!^[[:ascii:]]+$!', $str))
        return $str;
    $str = htmlentities($str, ENT_NOQUOTES, $charset);
    $str = preg_replace('#&([A-za-z])(?:acute|cedil|circ|grave|orn|ring|slash|th|tilde|uml);#', '\1', $str);
    $str = preg_replace('#&([A-za-z]{2})(?:lig);#', '\1', $str);
    $str = preg_replace('#&[^;]+;#', '', $str);
    return $str;
}
$db->createFunction('to_ascii', 'sqlite3_to_ascii', 1);
$res = $db->query('SELECT * FROM test ORDER BY to_ascii(text);');
?>
This will convert non-ascii characters to ascii ones before collation. In fact this won't work with non-latin languages, but for latin-languages it's better than nothing.
Please note that this will slow down about 1.8 times the query (tested on a 10.000 rows table).`

[＋add a note](https://www.php.net/manual/add-note.php?sect=sqlite3.createfunction&repo=en&redirect=https://www.php.net/manual/en/sqlite3.createfunction.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google