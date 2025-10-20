---
url: https://www.php.net/manual/en/sqlite3.exec.php
scraped_at: 2025-10-20T02:50:02.238Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# SQLite3::exec

(PHP 5 >= 5.3.0, PHP 7, PHP 8)

SQLite3::exec — Executes a result-less query against a given database

### Description [¶](https://www.php.net/manual/en/sqlite3.exec.php\#refsect1-sqlite3.exec-description)

public**SQLite3::exec**([string](https://www.php.net/manual/en/language.types.string.php) `$query`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Executes a result-less query against a given database.


> **Note**:
>
> SQLite3 may need to create [» temporary files](https://sqlite.org/tempfiles.html)
> during the execution of queries, so the respective directories may have to be writable.

### Parameters [¶](https://www.php.net/manual/en/sqlite3.exec.php\#refsect1-sqlite3.exec-parameters)

`query`

The SQL query to execute (typically an INSERT, UPDATE, or DELETE
query).


### Return Values [¶](https://www.php.net/manual/en/sqlite3.exec.php\#refsect1-sqlite3.exec-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if the query succeeded, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/sqlite3.exec.php\#refsect1-sqlite3.exec-examples)

**Example #1 **SQLite3::exec()** example**

`<?php
$db = new SQLite3('mysqlitedb.db');
$db->exec('CREATE TABLE bar (bar TEXT)');
?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/sqlite3/sqlite3/exec.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsqlite3.exec%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=sqlite3.exec&repo=en&redirect=https://www.php.net/manual/en/sqlite3.exec.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=118837&page=sqlite3.exec&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118837&page=sqlite3.exec&vote=down "Vote down!")

17


[**_alexandre dot schmidt at gmail dot com_**](https://www.php.net/manual/en/sqlite3.exec.php#118837) [¶](https://www.php.net/manual/en/sqlite3.exec.php#118837)

**9 years ago**

`I was getting "database locked" all the time until I found out some features of sqlite3 must be set by using SQL special instructions (i.e. using PRAGMA keyword). For instance, what apparently solved my problem with "database locked" was to set journal_mode to 'wal' (it is defaulting to 'delete', as stated here: [https://www.sqlite.org/wal.html](https://www.sqlite.org/wal.html) (see Activating  And Configuring WAL Mode)).
So basically what I had to do was creating a connection to the database and setting journal_mode with the SQL statement. Example:
<?php
$db = new SQLite3('/my/sqlite/file.sqlite3');
$db->busyTimeout(5000);
// WAL mode has better control over concurrency.
// Source: [https://www.sqlite.org/wal.html](https://www.sqlite.org/wal.html)
$db->exec('PRAGMA journal_mode = wal;');
?>
Hope that helps.`

[up](https://www.php.net/manual/vote-note.php?id=127340&page=sqlite3.exec&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127340&page=sqlite3.exec&vote=down "Vote down!")

 -2


[**_synnus_**](https://www.php.net/manual/en/sqlite3.exec.php#127340) [¶](https://www.php.net/manual/en/sqlite3.exec.php#127340)

**3 years ago**

`<?php
       $db->exec('PRAGMA journal_mode = wal;');
       $db->exec('PRAGMA synchronous = NORMAL;');
       $db->exec('PRAGMA schema.taille_cache = 16000;');
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=sqlite3.exec&repo=en&redirect=https://www.php.net/manual/en/sqlite3.exec.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google