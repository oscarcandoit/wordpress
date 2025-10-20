---
url: https://www.php.net/manual/en/mysqli-stmt.execute.php
scraped_at: 2025-10-20T02:42:05.108Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_stmt::execute

# mysqli\_stmt\_execute

(PHP 5, PHP 7, PHP 8)

mysqli\_stmt::execute \-\- mysqli\_stmt\_execute — Executes a prepared statement

### Description [¶](https://www.php.net/manual/en/mysqli-stmt.execute.php\#refsect1-mysqli-stmt.execute-description)

Object-oriented style

public**mysqli\_stmt::execute**([?](https://www.php.net/manual/en/language.types.null.php)[array](https://www.php.net/manual/en/language.types.array.php) `$params` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Procedural style

**mysqli\_stmt\_execute**([mysqli\_stmt](https://www.php.net/manual/en/class.mysqli-stmt.php) `$statement`, [?](https://www.php.net/manual/en/language.types.null.php)[array](https://www.php.net/manual/en/language.types.array.php) `$params` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Executes previously prepared statement. The statement must be successfully
prepared prior to execution, using either
the [mysqli\_prepare()](https://www.php.net/manual/en/mysqli.prepare.php) or
[mysqli\_stmt\_prepare()](https://www.php.net/manual/en/mysqli-stmt.prepare.php) function, or by passing the second
argument to [mysqli\_stmt::\_\_construct()](https://www.php.net/manual/en/mysqli-stmt.construct.php).


If the statement is `UPDATE`, `DELETE`,
or `INSERT`, the total number of affected rows can be
determined by using the [mysqli\_stmt\_affected\_rows()](https://www.php.net/manual/en/mysqli-stmt.affected-rows.php)
function. If the query yields a result set, it can be fetched using
[mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php) function or by fetching it
row by row directly from the statement using
[mysqli\_stmt\_fetch()](https://www.php.net/manual/en/mysqli-stmt.fetch.php) function.


### Parameters [¶](https://www.php.net/manual/en/mysqli-stmt.execute.php\#refsect1-mysqli-stmt.execute-parameters)

`statement`

Procedural style only: A [mysqli\_stmt](https://www.php.net/manual/en/class.mysqli-stmt.php) object
returned by [mysqli\_stmt\_init()](https://www.php.net/manual/en/mysqli.stmt-init.php).

`params`

An optional list [array](https://www.php.net/manual/en/language.types.array.php) with as many elements as there are bound parameters in the SQL statement being executed. Each value is treated as a [string](https://www.php.net/manual/en/language.types.string.php).


### Return Values [¶](https://www.php.net/manual/en/mysqli-stmt.execute.php\#refsect1-mysqli-stmt.execute-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Errors/Exceptions [¶](https://www.php.net/manual/en/mysqli-stmt.execute.php\#refsect1-mysqli-stmt.execute-errors)

If mysqli error reporting is enabled ( **`[MYSQLI\_REPORT\_ERROR](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-error)`**) and the requested operation fails,
a warning is generated. If, in addition, the mode is set to **`[MYSQLI\_REPORT\_STRICT](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-strict)`**,
a [mysqli\_sql\_exception](https://www.php.net/manual/en/class.mysqli-sql-exception.php) is thrown instead.

### Changelog [¶](https://www.php.net/manual/en/mysqli-stmt.execute.php\#refsect1-mysqli-stmt.execute-changelog)

| Version | Description |
| --- | --- |
| 8.1.0 | The optional `params` parameter has been added. |

### Examples [¶](https://www.php.net/manual/en/mysqli-stmt.execute.php\#refsect1-mysqli-stmt.execute-examples)

**Example #1 Execute a prepared statement with bound variables**

Object-oriented style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$mysqli->query("CREATE TEMPORARY TABLE myCity LIKE City");
/* Prepare an insert statement */
$stmt = $mysqli->prepare("INSERT INTO myCity (Name, CountryCode, District) VALUES (?,?,?)");
/* Bind variables to parameters */
$stmt->bind_param("sss", $val1, $val2, $val3);
$val1 = 'Stuttgart';
$val2 = 'DEU';
$val3 = 'Baden-Wuerttemberg';
/* Execute the statement */
$stmt->execute();
$val1 = 'Bordeaux';
$val2 = 'FRA';
$val3 = 'Aquitaine';
/* Execute the statement */
$stmt->execute();
/* Retrieve all rows from myCity */
$query = "SELECT Name, CountryCode, District FROM myCity";
$result = $mysqli->query($query);
while ($row = $result->fetch_row()) {
    printf("%s (%s,%s)\n", $row[0], $row[1], $row[2]);
}`

Procedural style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$link = mysqli_connect("localhost", "my_user", "my_password", "world");
mysqli_query($link, "CREATE TEMPORARY TABLE myCity LIKE City");
/* Prepare an insert statement */
$stmt = mysqli_prepare($link, "INSERT INTO myCity (Name, CountryCode, District) VALUES (?,?,?)");
/* Bind variables to parameters */
mysqli_stmt_bind_param($stmt, "sss", $val1, $val2, $val3);
$val1 = 'Stuttgart';
$val2 = 'DEU';
$val3 = 'Baden-Wuerttemberg';
/* Execute the statement */
mysqli_stmt_execute($stmt);
$val1 = 'Bordeaux';
$val2 = 'FRA';
$val3 = 'Aquitaine';
/* Execute the statement */
mysqli_stmt_execute($stmt);
/* Retrieve all rows from myCity */
$query = "SELECT Name, CountryCode, District FROM myCity";
$result = mysqli_query($link, $query);
while ($row = mysqli_fetch_row($result)) {
    printf("%s (%s,%s)\n", $row[0], $row[1], $row[2]);
}`

The above examples will output:

```
Stuttgart (DEU,Baden-Wuerttemberg)
Bordeaux (FRA,Aquitaine)
```

**Example #2 Execute a prepared statement with an array of values**

Object-oriented style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli('localhost', 'my_user', 'my_password', 'world');
$mysqli->query('CREATE TEMPORARY TABLE myCity LIKE City');
/* Prepare an insert statement */
$stmt = $mysqli->prepare('INSERT INTO myCity (Name, CountryCode, District) VALUES (?,?,?)');
/* Execute the statement */
$stmt->execute(['Stuttgart', 'DEU', 'Baden-Wuerttemberg']);
/* Retrieve all rows from myCity */
$query = 'SELECT Name, CountryCode, District FROM myCity';
$result = $mysqli->query($query);
while ($row = $result->fetch_row()) {
    printf("%s (%s,%s)\n", $row[0], $row[1], $row[2]);
}`

Procedural style

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$link = mysqli_connect('localhost', 'my_user', 'my_password', 'world');
mysqli_query($link, 'CREATE TEMPORARY TABLE myCity LIKE City');
/* Prepare an insert statement */
$stmt = mysqli_prepare($link, 'INSERT INTO myCity (Name, CountryCode, District) VALUES (?,?,?)');
/* Execute the statement */
mysqli_stmt_execute($stmt, ['Stuttgart', 'DEU', 'Baden-Wuerttemberg']);
/* Retrieve all rows from myCity */
$query = 'SELECT Name, CountryCode, District FROM myCity';
$result = mysqli_query($link, $query);
while ($row = mysqli_fetch_row($result)) {
    printf("%s (%s,%s)\n", $row[0], $row[1], $row[2]);
}`

The above examples will output:

```
Stuttgart (DEU,Baden-Wuerttemberg)
```

### See Also [¶](https://www.php.net/manual/en/mysqli-stmt.execute.php\#refsect1-mysqli-stmt.execute-seealso)

- [mysqli\_execute\_query()](https://www.php.net/manual/en/mysqli.execute-query.php) \- Prepares, binds parameters, and executes SQL statement
- [mysqli\_prepare()](https://www.php.net/manual/en/mysqli.prepare.php) \- Prepares an SQL statement for execution
- [mysqli\_stmt\_bind\_param()](https://www.php.net/manual/en/mysqli-stmt.bind-param.php) \- Binds variables to a prepared statement as parameters
- [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php) \- Gets a result set from a prepared statement as a mysqli\_result object

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_stmt/execute.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-stmt.execute%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-stmt.execute&repo=en&redirect=https://www.php.net/manual/en/mysqli-stmt.execute.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=72012&page=mysqli-stmt.execute&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72012&page=mysqli-stmt.execute&vote=down "Vote down!")

13


[**_Typer85 at gmail dot com_**](https://www.php.net/manual/en/mysqli-stmt.execute.php#72012) [¶](https://www.php.net/manual/en/mysqli-stmt.execute.php#72012)

**18 years ago**

`Just to clarify this note in the Manual regarding this function:
"Note:  When using mysqli_stmt_execute(), the mysqli_stmt_fetch()  function must be used to fetch the data prior to performing any additional queries."
This is because this function DOES NOT store the result set on the client side so you have to fetch everything in the result set or else you risk major errors.
If you however use the function mysqli_stmt_store_result immediately after you use this function, you are forcing the result set to be stored on the client side and thus it is safe to issue extra queries before fetching all the data.
This is where you really have to make a choice regarding on your application's priorities. If you know your result set is memory hefty, then its a good idea not to store it on the client side so you don't run in any errors regarding unavailable memory on the server. But this also means your not going to do a lot of calculations on the result set or else you will prevent any other usage of the table to which the result set came from until you fetched it all.
If your going to do a lot of calculations or your result set is not memory hefty, its probably a good idea to store it on the client side.
Most of these problems can easily be solved if you have a lot of memory available on your server but thats usually not the case for those on shared hosting.
An intelligent way to counter this problem if your on a shared host is to be smart in the way you design your queries. Try to limit the result set if you know you will be fetching memory hefty result sets.
Test different alternatives for your application and see what works best for you under different conditions.
Good Luck,`

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-stmt.execute&repo=en&redirect=https://www.php.net/manual/en/mysqli-stmt.execute.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google