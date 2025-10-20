---
url: https://www.php.net/manual/en/sqlite3.backup.php
scraped_at: 2025-10-20T03:01:18.928Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# SQLite3::backup

(PHP 7 >= 7.4.0, PHP 8)

SQLite3::backup — Backup one database to another database

### Description [¶](https://www.php.net/manual/en/sqlite3.backup.php\#refsect1-sqlite3.backup-description)

public**SQLite3::backup**([SQLite3](https://www.php.net/manual/en/class.sqlite3.php) `$destination`, [string](https://www.php.net/manual/en/language.types.string.php) `$sourceDatabase` = "main", [string](https://www.php.net/manual/en/language.types.string.php) `$destinationDatabase` = "main"): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**SQLite3::backup()** copies the contents of one database
into another, overwriting the contents of the destination database.
It is useful either for creating backups of databases
or for copying in-memory databases to or from persistent files.


**Tip**

As of SQLite 3.27.0 (2019-02-07), it is also possible to use the statement
`VACUUM INTO 'file.db';` to backup the database to a new file.


### Parameters [¶](https://www.php.net/manual/en/sqlite3.backup.php\#refsect1-sqlite3.backup-parameters)

`destination`

A database connection opened with [SQLite3::open()](https://www.php.net/manual/en/sqlite3.open.php).


`sourceDatabase`

The database name is `"main"` for the main database,
`"temp"` for the temporary database,
or the name specified after the `AS` keyword
in an `ATTACH` statement for an attached database.


`destinationDatabase`

Analogous to `sourceDatabase`
but for the `destination`.


### Return Values [¶](https://www.php.net/manual/en/sqlite3.backup.php\#refsect1-sqlite3.backup-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/sqlite3.backup.php\#refsect1-sqlite3.backup-examples)

**Example #1 Backup an existing database**

`<?php
// $conn is a connection to an already opened sqlite3 database
$backup = new SQLite3('backup.sqlite');
$conn->backup($backup);
?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/sqlite3/sqlite3/backup.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsqlite3.backup%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=sqlite3.backup&repo=en&redirect=https://www.php.net/manual/en/sqlite3.backup.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google