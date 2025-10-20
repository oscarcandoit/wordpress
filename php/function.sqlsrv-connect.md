---
url: https://www.php.net/manual/en/function.sqlsrv-connect.php
scraped_at: 2025-10-20T02:58:03.853Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# sqlsrv\_connect

(No version information available, might only be in Git)

sqlsrv\_connect — Opens a connection to a Microsoft SQL Server database

### Description [¶](https://www.php.net/manual/en/function.sqlsrv-connect.php\#refsect1-function.sqlsrv-connect-description)

**sqlsrv\_connect**([string](https://www.php.net/manual/en/language.types.string.php) `$serverName`, [array](https://www.php.net/manual/en/language.types.array.php) `$connectionInfo` = ?): [resource](https://www.php.net/manual/en/language.types.resource.php)

Opens a connection to a Microsoft SQL Server database. By default, the connection
is attempted using Windows Authentication. To connect using SQL Server
Authentication, include "UID" and "PWD" in the connection options array.


### Parameters [¶](https://www.php.net/manual/en/function.sqlsrv-connect.php\#refsect1-function.sqlsrv-connect-parameters)

`serverName`

The name of the server to which a connection is established. To connect
to a specific instance, follow the server name with a backward slash
and the instance name (e.g. serverName\\sqlexpress).


`connectionInfo`

An associative array that specifies options for connecting to the server.
If values for the UID and PWD keys are not specified, the connection
will be attempted using Windows Authentication. For a complete list of supported
keys, see [» SQLSRV Connection Options](http://msdn.microsoft.com/en-us/library/ff628167.aspx).


### Return Values [¶](https://www.php.net/manual/en/function.sqlsrv-connect.php\#refsect1-function.sqlsrv-connect-returnvalues)

A connection resource. If a connection cannot be successfully opened, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** is returned.


### Examples [¶](https://www.php.net/manual/en/function.sqlsrv-connect.php\#refsect1-function.sqlsrv-connect-examples)

**Example #1 Connect using Windows Authentication.**

`<?php
$serverName = "serverName\\sqlexpress"; //serverName\instanceName
// Since UID and PWD are not specified in the $connectionInfo array,
// The connection will be attempted using Windows Authentication.
$connectionInfo = array( "Database"=>"dbName");
$conn = sqlsrv_connect( $serverName, $connectionInfo);
if( $conn ) {
     echo "Connection established.<br />";
}else{
     echo "Connection could not be established.<br />";
     die( print_r( sqlsrv_errors(), true));
}
?>`

**Example #2 Connect by specifying a user name and password.**

`<?php
$serverName = "serverName\\sqlexpress"; //serverName\instanceName
$connectionInfo = array( "Database"=>"dbName", "UID"=>"userName", "PWD"=>"password");
$conn = sqlsrv_connect( $serverName, $connectionInfo);
if( $conn ) {
     echo "Connection established.<br />";
}else{
     echo "Connection could not be established.<br />";
     die( print_r( sqlsrv_errors(), true));
}
?>`

**Example #3 Connect on a specified port.**

`<?php
$serverName = "serverName\\sqlexpress, 1542"; //serverName\instanceName, portNumber (default is 1433)
$connectionInfo = array( "Database"=>"dbName", "UID"=>"userName", "PWD"=>"password");
$conn = sqlsrv_connect( $serverName, $connectionInfo);
if( $conn ) {
     echo "Connection established.<br />";
}else{
     echo "Connection could not be established.<br />";
     die( print_r( sqlsrv_errors(), true));
}
?>`

### Notes [¶](https://www.php.net/manual/en/function.sqlsrv-connect.php\#refsect1-function.sqlsrv-connect-notes)

By default, the **sqlsrv\_connect()** uses connection pooling to
improve connection performance. To turn off connection pooling (i.e. force a
new connection on each call), set the "ConnectionPooling" option in the
$connectionOptions array to 0 (or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**). For more information, see
[» SQLSRV Connection Pooling](http://msdn.microsoft.com/en-us/library/cc644930.aspx).


The SQLSRV extension does not have a dedicated function for changing which
database is connected to. The target database is specified in the
$connectionOptions array that is passed to sqlsrv\_connect. To change the
database on an open connection, execute the following query "USE dbName"
(e.g. sqlsrv\_query($conn, "USE dbName")).


### See Also [¶](https://www.php.net/manual/en/function.sqlsrv-connect.php\#refsect1-function.sqlsrv-connect-seealso)

- [sqlsrv\_close()](https://www.php.net/manual/en/function.sqlsrv-close.php) \- Closes an open connection and releases resourses associated with the connection
- [sqlsrv\_errors()](https://www.php.net/manual/en/function.sqlsrv-errors.php) \- Returns error and warning information about the last SQLSRV operation performed
- [sqlsrv\_query()](https://www.php.net/manual/en/function.sqlsrv-query.php) \- Prepares and executes a query

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/sqlsrv/functions/sqlsrv-connect.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.sqlsrv-connect%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.sqlsrv-connect&repo=en&redirect=https://www.php.net/manual/en/function.sqlsrv-connect.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=119863&page=function.sqlsrv-connect&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119863&page=function.sqlsrv-connect&vote=down "Vote down!")

5


[**_alvaro at demogracia dot com_**](https://www.php.net/manual/en/function.sqlsrv-connect.php#119863) [¶](https://www.php.net/manual/en/function.sqlsrv-connect.php#119863)

**9 years ago**

`You can use the connectionInfo parameter to specify connection encoding, e.g.:
<?php
$connectionInfo = [\
    'CharacterSet' => 'UTF-8',\
];
$conn = sqlsrv_connect($serverName, $connectionInfo);
?>
Beware though that only two options exist:
- SQLSRV_ENC_CHAR (constant) for ANSI, which is the default
- 'UTF-8' (string) for Unicode`

[up](https://www.php.net/manual/vote-note.php?id=118117&page=function.sqlsrv-connect&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118117&page=function.sqlsrv-connect&vote=down "Vote down!")

4


[**_Eion Robb_**](https://www.php.net/manual/en/function.sqlsrv-connect.php#118117) [¶](https://www.php.net/manual/en/function.sqlsrv-connect.php#118117)

**10 years ago**

`As mentioned at [https://msdn.microsoft.com/en-us/library/cc296193.aspx](https://msdn.microsoft.com/en-us/library/cc296193.aspx) the connection will convert some data into PHP data types.  Of particular difference to other database functions in PHP is that dates will be output as objects instead of strings.
To make the sqlsrv_fetch_{array|object}() functions return dates/times/datetimes as strings instead, specify:
'ReturnDatesAsStrings' => true
in the $connectionInfo array.
For more info about this behaviour, see [https://msdn.microsoft.com/en-us/library/ee376928.aspx](https://msdn.microsoft.com/en-us/library/ee376928.aspx)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.sqlsrv-connect&repo=en&redirect=https://www.php.net/manual/en/function.sqlsrv-connect.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google