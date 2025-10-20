---
url: https://www.php.net/manual/en/mysqli.autocommit.php
scraped_at: 2025-10-20T02:56:53.670Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli::autocommit

# mysqli\_autocommit

(PHP 5, PHP 7, PHP 8)

mysqli::autocommit \-\- mysqli\_autocommit — Turns on or off auto-committing database modifications

### Description [¶](https://www.php.net/manual/en/mysqli.autocommit.php\#refsect1-mysqli.autocommit-description)

Object-oriented style

public**mysqli::autocommit**([bool](https://www.php.net/manual/en/language.types.boolean.php) `$enable`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Procedural style

**mysqli\_autocommit**([mysqli](https://www.php.net/manual/en/class.mysqli.php) `$mysql`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$enable`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Turns on or off auto-commit mode on queries for the database connection.


To determine the current state of autocommit use the SQL command
`SELECT @@autocommit`.


### Parameters [¶](https://www.php.net/manual/en/mysqli.autocommit.php\#refsect1-mysqli.autocommit-parameters)

`mysql`

Procedural style only: A [mysqli](https://www.php.net/manual/en/class.mysqli.php) object
returned by [mysqli\_connect()](https://www.php.net/manual/en/function.mysqli-connect.php) or [mysqli\_init()](https://www.php.net/manual/en/mysqli.init.php)

`enable`

Whether to turn on auto-commit or not.


### Return Values [¶](https://www.php.net/manual/en/mysqli.autocommit.php\#refsect1-mysqli.autocommit-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Errors/Exceptions [¶](https://www.php.net/manual/en/mysqli.autocommit.php\#refsect1-mysqli.autocommit-errors)

If mysqli error reporting is enabled ( **`[MYSQLI\_REPORT\_ERROR](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-error)`**) and the requested operation fails,
a warning is generated. If, in addition, the mode is set to **`[MYSQLI\_REPORT\_STRICT](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-strict)`**,
a [mysqli\_sql\_exception](https://www.php.net/manual/en/class.mysqli-sql-exception.php) is thrown instead.

### Examples [¶](https://www.php.net/manual/en/mysqli.autocommit.php\#refsect1-mysqli.autocommit-examples)

**Example #1 **mysqli::autocommit()** example**

Object-oriented style

`<?php
/* Tell mysqli to throw an exception if an error occurs */
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
/* The table engine has to support transactions */
$mysqli->query("CREATE TABLE IF NOT EXISTS language (
    Code text NOT NULL,
    Speakers int(11) NOT NULL
    ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;");
/* Turn autocommit off */
$mysqli->autocommit(false);
$result = $mysqli->query("SELECT @@autocommit");
$row = $result->fetch_row();
printf("Autocommit is %s\n", $row[0]);
try {
    /* Prepare insert statement */
    $stmt = $mysqli->prepare('INSERT INTO language(Code, Speakers) VALUES (?,?)');
    $stmt->bind_param('ss', $language_code, $native_speakers);
    /* Insert some values */
    $language_code = 'DE';
    $native_speakers = 50_123_456;
    $stmt->execute();
    $language_code = 'FR';
    $native_speakers = 40_546_321;
    $stmt->execute();
    /* Commit the data in the database. This doesn't set autocommit=true */
    $mysqli->commit();
    print "Committed 2 rows in the database\n";
    $result = $mysqli->query("SELECT @@autocommit");
    $row = $result->fetch_row();
    printf("Autocommit is %s\n", $row[0]);
    /* Try to insert more values */
    $language_code = 'PL';
    $native_speakers = 30_555_444;
    $stmt->execute();
    $language_code = 'DK';
    $native_speakers = 5_222_444;
    $stmt->execute();
    /* Setting autocommit=true will trigger a commit */
    $mysqli->autocommit(true);
    print "Committed 2 row in the database\n";
} catch (mysqli_sql_exception $exception) {
    $mysqli->rollback();
    throw $exception;
}`

Procedural style

`<?php
/* Tell mysqli to throw an exception if an error occurs */
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = mysqli_connect("localhost", "my_user", "my_password", "world");
/* The table engine has to support transactions */
mysqli_query($mysqli, "CREATE TABLE IF NOT EXISTS language (
    Code text NOT NULL,
    Speakers int(11) NOT NULL
    ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;");
/* Turn autocommit off */
mysqli_autocommit($mysqli, false);
$result = mysqli_query($mysqli, "SELECT @@autocommit");
$row = mysqli_fetch_row($result);
printf("Autocommit is %s\n", $row[0]);
try {
    /* Prepare insert statement */
    $stmt = mysqli_prepare($mysqli, 'INSERT INTO language(Code, Speakers) VALUES (?,?)');
    mysqli_stmt_bind_param($stmt, 'ss', $language_code, $native_speakers);
    /* Insert some values */
    $language_code = 'DE';
    $native_speakers = 50_123_456;
    mysqli_stmt_execute($stmt);
    $language_code = 'FR';
    $native_speakers = 40_546_321;
    mysqli_stmt_execute($stmt);
    /* Commit the data in the database. This doesn't set autocommit=true */
    mysqli_commit($mysqli);
    print "Committed 2 rows in the database\n";
    $result = mysqli_query($mysqli, "SELECT @@autocommit");
    $row = mysqli_fetch_row($result);
    printf("Autocommit is %s\n", $row[0]);
    /* Try to insert more values */
    $language_code = 'PL';
    $native_speakers = 30_555_444;
    mysqli_stmt_execute($stmt);
    $language_code = 'DK';
    $native_speakers = 5_222_444;
    mysqli_stmt_execute($stmt);
    /* Setting autocommit=true will trigger a commit */
    mysqli_autocommit($mysqli, true);
    print "Committed 2 row in the database\n";
} catch (mysqli_sql_exception $exception) {
    mysqli_rollback($mysqli);
    throw $exception;
}`

The above examples will output:

```
Autocommit is 0
Committed 2 rows in the database
Autocommit is 0
Committed 2 row in the database
Autocommit is 0
Committed 2 rows in the database
Autocommit is 0
Committed 2 row in the database
```

### Notes [¶](https://www.php.net/manual/en/mysqli.autocommit.php\#refsect1-mysqli.autocommit-notes)

> **Note**:
>
>
> This function does not work with non transactional table types (like
> MyISAM or ISAM).

### See Also [¶](https://www.php.net/manual/en/mysqli.autocommit.php\#refsect1-mysqli.autocommit-seealso)

- [mysqli\_begin\_transaction()](https://www.php.net/manual/en/mysqli.begin-transaction.php) \- Starts a transaction
- [mysqli\_commit()](https://www.php.net/manual/en/mysqli.commit.php) \- Commits the current transaction
- [mysqli\_rollback()](https://www.php.net/manual/en/mysqli.rollback.php) \- Rolls back current transaction

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli/autocommit.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli.autocommit%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli.autocommit&repo=en&redirect=https://www.php.net/manual/en/mysqli.autocommit.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=79103&page=mysqli.autocommit&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=79103&page=mysqli.autocommit&vote=down "Vote down!")

23


[**_jcwebb at dicoe dot com_**](https://www.php.net/manual/en/mysqli.autocommit.php#79103) [¶](https://www.php.net/manual/en/mysqli.autocommit.php#79103)

**17 years ago**

`Just to be clear, autocommit not only turns on/off transactions, but will also 'commit' any waiting queries.
<?php
mysqli_autocommit($link, FALSE); // turn OFF auto
-some query 1;
-some query 2;
mysqli_commit($link); // process ALL queries so far
-some query 3;
-some query 4;
mysqli_autocommit($link, TRUE); // turn ON auto
?>
All 4 will be processed.`

[up](https://www.php.net/manual/vote-note.php?id=75112&page=mysqli.autocommit&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75112&page=mysqli.autocommit&vote=down "Vote down!")

14


[**_Geoffrey Thubron_**](https://www.php.net/manual/en/mysqli.autocommit.php#75112) [¶](https://www.php.net/manual/en/mysqli.autocommit.php#75112)

**18 years ago**

`It's worth noting that you can perform transactions without disabling autocommit just using standard sql. "START TRANSACTION;" will start a transaction. "COMMIT;" will commit the results and "ROLLBACK;" will revert to the pre-transaction state.
CREATE TABLE and CREATE DATABASE (and probably others) are always commited immediately and your transaction appears to terminate. Thus any commands before and after will be commited, even if a subsequent rollback is attempted.
If you are in the middle of a transaction and you call mysqli_close() it appears that you get the funcitonality of an implicit rollback.
I can't reproduce the "code bug causes lock" problem outlined below (I always get a successful rollback and the script will run umtine times successfully). Therefore, I would suggest that the problem is fixed in php-5.2.2.`

[up](https://www.php.net/manual/vote-note.php?id=73816&page=mysqli.autocommit&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73816&page=mysqli.autocommit&vote=down "Vote down!")

4


[**_Glen_**](https://www.php.net/manual/en/mysqli.autocommit.php#73816) [¶](https://www.php.net/manual/en/mysqli.autocommit.php#73816)

**18 years ago**

`I've found that if PHP exits due to a code bug during a transaction, an InnoDB table can remain locked until Apache is restarted.
The simple test is to start a transaction by setting $mysqli_obj->autocommit(false) and executing an insert statement.  Before getting to a $mysqli_obj->commit statement - have a runtime code bug bomb PHP.  You check the database, no insert happened (you assume a rollback occurred) .. and you go fix the bug, and try again... but this time the script takes about 50 seconds to timeout - the insert statement returning with a “1205 - Lock wait timeout exceeded; try restarting transaction”.  No rollback occurred. And this error will not go away until you restart Apache - for whatever reason, the resources are not released until the process is killed.
I found that an ‘exit’, instead of a PHP code bug, will not cause a problem. So there is an auto-rollback mechanism in place - it just fails miserably when PHP dies unexpectantly. Having to restarting apache is a pretty drastic measure to overcome a code bug.
To avoid this problem, I use “register_shutdown_function()” when I start a transaction, and set a flag to indicate a transaction is in process (because there is no unregister_shutdown_function()). See below. So the __shutdown_check() routine (I beleive it needs to be public) is called when the script bombs - which is able to invoke the rollback().
these are just the relevant bits to give u an idea...
<?php
public function begin_transaction() {
$ret = $this->mysqli_obj->autocommit(false);
$this->transaction_in_progress = true;
register_shutdown_function(array($this, "__shutdown_check"));
}
public function __shutdown_check() {
if ($this->transaction_in_progress) {
    $this->rollback();
}
}
public function commit() {
$ret = $this->mysqli_obj->commit();
$this->transaction_in_progress = false;
}
public function rollback() {
$ret = $this->mysqli_obj->rollback();
$this->transaction_in_progress = false;
}
?>
True for PHP 5.1.6 + MySQL 5.0.24a.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli.autocommit&repo=en&redirect=https://www.php.net/manual/en/mysqli.autocommit.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google