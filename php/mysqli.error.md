---
url: https://www.php.net/manual/en/mysqli.error.php
scraped_at: 2025-10-20T03:01:33.167Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli::$error

# mysqli\_error

(PHP 5, PHP 7, PHP 8)

mysqli::$error \-\- mysqli\_error — Returns a string description of the last error

### Description [¶](https://www.php.net/manual/en/mysqli.error.php\#refsect1-mysqli.error-description)

Object-oriented style

[string](https://www.php.net/manual/en/language.types.string.php)[$mysqli->error](https://www.php.net/manual/en/mysqli.error.php);

Procedural style

**mysqli\_error**([mysqli](https://www.php.net/manual/en/class.mysqli.php) `$mysql`): [string](https://www.php.net/manual/en/language.types.string.php)

Returns the last error message for the most recent MySQLi function call
that can succeed or fail.


### Parameters [¶](https://www.php.net/manual/en/mysqli.error.php\#refsect1-mysqli.error-parameters)

`mysql`

Procedural style only: A [mysqli](https://www.php.net/manual/en/class.mysqli.php) object
returned by [mysqli\_connect()](https://www.php.net/manual/en/function.mysqli-connect.php) or [mysqli\_init()](https://www.php.net/manual/en/mysqli.init.php)

### Return Values [¶](https://www.php.net/manual/en/mysqli.error.php\#refsect1-mysqli.error-returnvalues)

A string that describes the error. An empty string if no error occurred.


### Examples [¶](https://www.php.net/manual/en/mysqli.error.php\#refsect1-mysqli.error-examples)

**Example #1 $mysqli->error example**

Object-oriented style

`<?php
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
/* check connection */
if ($mysqli->connect_errno) {
    printf("Connect failed: %s\n", $mysqli->connect_error);
    exit();
}
if (!$mysqli->query("SET a=1")) {
    printf("Error message: %s\n", $mysqli->error);
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
if (!mysqli_query($link, "SET a=1")) {
    printf("Error message: %s\n", mysqli_error($link));
}
/* close connection */
mysqli_close($link);
?>`

The above examples will output:

```
Error message: Unknown system variable 'a'
```

### See Also [¶](https://www.php.net/manual/en/mysqli.error.php\#refsect1-mysqli.error-seealso)

- [mysqli\_connect\_errno()](https://www.php.net/manual/en/mysqli.connect-errno.php) \- Returns the error code from last connect call
- [mysqli\_connect\_error()](https://www.php.net/manual/en/mysqli.connect-error.php) \- Returns a description of the last connection error
- [mysqli\_errno()](https://www.php.net/manual/en/mysqli.errno.php) \- Returns the error code for the most recent function call
- [mysqli\_sqlstate()](https://www.php.net/manual/en/mysqli.sqlstate.php) \- Returns the SQLSTATE error from previous MySQL operation

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli/error.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli.error%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli.error&repo=en&redirect=https://www.php.net/manual/en/mysqli.error.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=61044&page=mysqli.error&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=61044&page=mysqli.error&vote=down "Vote down!")

17


[**_information at saunderswebsolutions dot com_**](https://www.php.net/manual/en/mysqli.error.php#61044) [¶](https://www.php.net/manual/en/mysqli.error.php#61044)

**19 years ago**

`The mysqli_sql_exception class is not available to PHP 5.05
I used this code to catch errors
<?php
$query = "SELECT XXname FROM customer_table ";
$res = $mysqli->query($query);
if (!$res) {
printf("Errormessage: %s\n", $mysqli->error);
}
?>
The problem with this is that valid values for $res are: a mysqli_result object , true or false
This doesn't tell us that there has been an error with the sql used.
If you pass an update statement, false is a valid result if the update fails.
So, a better way is:
<?php
$query = "SELECT XXname FROM customer_table ";
$res = $mysqli->query($query);
if (!$mysqli->error) {
printf("Errormessage: %s\n", $mysqli->error);
}
?>
This would output something like:
Unexpected PHP error [mysqli::query() [<a href='function.query'>function.query</a>]: (42S22/1054): Unknown column 'XXname' in 'field list'] severity [E_WARNING] in [G:\database.php] line [249]
Very frustrating as I wanted to also catch the sql error and print out the stack trace.
A better way is:
<?php
mysqli_report(MYSQLI_REPORT_OFF); //Turn off irritating default messages
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$query = "SELECT XXname FROM customer_table ";
$res = $mysqli->query($query);
if ($mysqli->error) {
    try {
        throw new Exception("MySQL error $mysqli->error <br> Query:<br> $query", $msqli->errno);
    } catch(Exception $e ) {
        echo "Error No: ".$e->getCode(). " - ". $e->getMessage() . "<br >";
        echo nl2br($e->getTraceAsString());
    }
}
//Do stuff with the result
?>
Prints out something like:
Error No: 1054
Unknown column 'XXname' in 'field list'
Query:
SELECT XXname FROM customer_table
#0 G:\\database.php(251): database->dbError('Unknown column ...', 1054, 'getQuery()', 'SELECT XXname F...')
#1 G:\data\WorkSites\1framework5\tests\dbtest.php(29): database->getString('SELECT XXname F...')
#2 c:\PHP\includes\simpletest\runner.php(58): testOfDB->testGetVal()
#3 c:\PHP\includes\simpletest\runner.php(96): SimpleInvoker->invoke('testGetVal')
#4 c:\PHP\includes\simpletest\runner.php(125): SimpleInvokerDecorator->invoke('testGetVal')
#5 c:\PHP\includes\simpletest\runner.php(183): SimpleErrorTrappingInvoker->invoke('testGetVal')
#6 c:\PHP\includes\simpletest\simple_test.php(90): SimpleRunner->run()
#7 c:\PHP\includes\simpletest\simple_test.php(498): SimpleTestCase->run(Object(HtmlReporter))
#8 c:\PHP\includes\simpletest\simple_test.php(500): GroupTest->run(Object(HtmlReporter))
#9 G:\all_tests.php(16): GroupTest->run(Object(HtmlReporter))
This will actually print out the error, a stack trace and the offending sql statement. Much more helpful when the sql statement is generated somewhere else in the code.`

[up](https://www.php.net/manual/vote-note.php?id=64770&page=mysqli.error&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=64770&page=mysqli.error&vote=down "Vote down!")

9


[**_se (at) brainbits (dot) net_**](https://www.php.net/manual/en/mysqli.error.php#64770) [¶](https://www.php.net/manual/en/mysqli.error.php#64770)

**19 years ago**

`The decription "mysqli_error -- Returns a string description of the LAST error" is not exactly that what you get from mysqli_error. You get the error description from the last mysqli-function, not from the last mysql-error.
If you have the following situation
if (!$mysqli->query("SET a=1")) {
$mysqli->query("ROLLBACK;")
printf("Errormessage: %s\n", $mysqli->error);
}
you don't get an error-message, if the ROLLBACK-Query didn't failed, too. In order to get the right error-message you have to write:
if (!$mysqli->query("SET a=1")) {
printf("Errormessage: %s\n", $mysqli->error);
$mysqli->query("ROLLBACK;")
}`

[up](https://www.php.net/manual/vote-note.php?id=116849&page=mysqli.error&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116849&page=mysqli.error&vote=down "Vote down!")

6


[**_callforeach at gmail dot com_**](https://www.php.net/manual/en/mysqli.error.php#116849) [¶](https://www.php.net/manual/en/mysqli.error.php#116849)

**10 years ago**

`I had to set mysqli_report(MYSQLI_REPORT_ALL) at the begin of my script to be able to catch mysqli errors within the catch block of my php code.
Initially, I used the below code to throw and subsequent catch mysqli exceptions
<?php
try {
$mysqli = new mysqli('localhost','root','pwd','db');
    if ($mysqli->connect_errno)
        throw new Exception($mysqli->connect_error);
} catch (Exception $e) {
     echo $e->getMessage();
}
I realized the exception was being thrown before the actual throw statement and hence the catch block was not being called.
My current code looks like
mysqli_report(MYSQLI_REPORT_ALL) ;
try {
      $mysqli = new mysqli('localhost','root','pwd','db');
      /* I don't need to throw the exception, it's being thrown automatically */
} catch (Exception $e) {
echo $e->getMessage();
}
This works fine and I'm able to trap all mysqli errors`

[up](https://www.php.net/manual/vote-note.php?id=113587&page=mysqli.error&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113587&page=mysqli.error&vote=down "Vote down!")

 -1


[**_asmith16 at littlesvr dot ca_**](https://www.php.net/manual/en/mysqli.error.php#113587) [¶](https://www.php.net/manual/en/mysqli.error.php#113587)

**11 years ago**

`Please note that the string returned may contain data initially provided by the user, possibly making your code vulnerable to XSS.
So even if you escape everything in your SQL query using mysqli_real_escape_string(), make sure that if you plan to display the string returned by mysqli_error() you run that string through htmlspecialchars().
As far as I can tell the two escape functions don't escape the same characters, which is why you need both (the first for SQL and the second for HTML/JS).`

[up](https://www.php.net/manual/vote-note.php?id=127549&page=mysqli.error&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127549&page=mysqli.error&vote=down "Vote down!")

 -2


[**_abderrahmanekaddour dot aissat at gmail dot com_**](https://www.php.net/manual/en/mysqli.error.php#127549) [¶](https://www.php.net/manual/en/mysqli.error.php#127549)

**3 years ago**

`<?php
// The idea is the add formated errors information for developers to easier bugs detection.
$myfile = fopen("database_log.log", "r");
$db = new mysqli("localhost", "root","root","data");
if(!$db->query("SELECT")){
$timestamp = new DateTime();
$data_err = " {
     \"title\": \" Select statement error \",
     \"date_time\": ".$timestamp->getTimestamp().",
     \"error\":\" ".$db->error." \"
     } "; // Do more information
fwrite($myfile, $data_err); // writing data
}
    // In separate file do file read and format it for good visual.
$db->close();
fclose($myfile);
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli.error&repo=en&redirect=https://www.php.net/manual/en/mysqli.error.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google