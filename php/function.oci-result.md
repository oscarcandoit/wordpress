---
url: https://www.php.net/manual/en/function.oci-result.php
scraped_at: 2025-10-20T02:57:45.210Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# oci\_result

(PHP 5, PHP 7, PHP 8, PECL OCI8 >= 1.1.0)

oci\_result — Returns field's value from the fetched row

### Description [¶](https://www.php.net/manual/en/function.oci-result.php\#refsect1-function.oci-result-description)

**oci\_result**([resource](https://www.php.net/manual/en/language.types.resource.php) `$statement`, [string](https://www.php.net/manual/en/language.types.string.php)\|[int](https://www.php.net/manual/en/language.types.integer.php) `$column`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

Returns the data from `column` in the current row,
fetched by [oci\_fetch()](https://www.php.net/manual/en/function.oci-fetch.php).


For details on the data type mapping performed by
the OCI8 extension, see the [datatypes\\
supported by the driver](https://www.php.net/manual/en/oci8.datatypes.php)

### Parameters [¶](https://www.php.net/manual/en/function.oci-result.php\#refsect1-function.oci-result-parameters)

`statement``column`

Can be either use the column number (1-based) or the column name.
The case of the column name must be the case that Oracle meta data
describes the column as, which is uppercase for columns created
case insensitively.


### Return Values [¶](https://www.php.net/manual/en/function.oci-result.php\#refsect1-function.oci-result-returnvalues)

Returns everything as strings except for abstract types (ROWIDs, LOBs and
FILEs). Returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on error.


### Examples [¶](https://www.php.net/manual/en/function.oci-result.php\#refsect1-function.oci-result-examples)

**Example #1 [oci\_fetch()](https://www.php.net/manual/en/function.oci-fetch.php) with **oci\_result()****

`<?php
$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}
$sql = 'SELECT location_id, city FROM locations WHERE location_id < 1200';
$stid = oci_parse($conn, $sql);
oci_execute($stid);
while (oci_fetch($stid)) {
    echo oci_result($stid, 'LOCATION_ID') . " is ";
    echo oci_result($stid, 'CITY') . "<br>\n";
}
// Displays:
//   1000 is Roma
//   1100 is Venice
oci_free_statement($stid);
oci_close($conn);
?>`

### See Also [¶](https://www.php.net/manual/en/function.oci-result.php\#refsect1-function.oci-result-seealso)

- [oci\_fetch\_array()](https://www.php.net/manual/en/function.oci-fetch-array.php) \- Returns the next row from a query as an associative or numeric array
- [oci\_fetch\_assoc()](https://www.php.net/manual/en/function.oci-fetch-assoc.php) \- Returns the next row from a query as an associative array
- [oci\_fetch\_object()](https://www.php.net/manual/en/function.oci-fetch-object.php) \- Returns the next row from a query as an object
- [oci\_fetch\_row()](https://www.php.net/manual/en/function.oci-fetch-row.php) \- Returns the next row from a query as a numeric array
- [oci\_fetch\_all()](https://www.php.net/manual/en/function.oci-fetch-all.php) \- Fetches multiple rows from a query into a two-dimensional array

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/oci8/functions/oci-result.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.oci-result%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.oci-result&repo=en&redirect=https://www.php.net/manual/en/function.oci-result.php)

### User Contributed Notes 9 notes

[up](https://www.php.net/manual/vote-note.php?id=1635&page=function.oci-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=1635&page=function.oci-result&vote=down "Vote down!")

2


[**_dominic dot standage at revolutionltd dot com_**](https://www.php.net/manual/en/function.oci-result.php#1635) [¶](https://www.php.net/manual/en/function.oci-result.php#1635)

**26 years ago**

`OCIResult() requires the column name to be written in capitals, so OCIResult($stmt,"column") won't work, but OCIResult($stmt,"COLUMN") works fine. Hope that helps somebody out`

[up](https://www.php.net/manual/vote-note.php?id=25533&page=function.oci-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=25533&page=function.oci-result&vote=down "Vote down!")

1


[**_erabbott at NOSPAMterra dot com dot br_**](https://www.php.net/manual/en/function.oci-result.php#25533) [¶](https://www.php.net/manual/en/function.oci-result.php#25533)

**23 years ago**

`Note that if you are making multiple table selects, you must specify an alias to each column.
This wont work:
----------------------------------------
$qry = "SELECT A.COL_ONE, B.COL_ONE FROM TABLE1 A, TABLE2 B";
$stmt = OCIParse($conn, $qry);
while(OCIFetch($stmt))
{
    $a = OCIResult($stmt, "A.COL_ONE");
...
----------------------------------------
But this will:
----------------------------------------
$qry = "SELECT A.COL_ONE AS X, B.COL_ONE AS Y FROM TABLE1 A, TABLE2 B";
$stmt = OCIParse($conn, $qry);
while(OCIFetch($stmt))
{
    $a = OCIResult($stmt, "X");
...
----------------------------------------
Regards,`

[up](https://www.php.net/manual/vote-note.php?id=56196&page=function.oci-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56196&page=function.oci-result&vote=down "Vote down!")

 -1


[**_luismanuelp at gmail dot com_**](https://www.php.net/manual/en/function.oci-result.php#56196) [¶](https://www.php.net/manual/en/function.oci-result.php#56196)

**20 years ago**

`I am trying to get a list of the first character of a character string.
SELECT distinct substr(version,1,1) as COL1 FROM SPHVVERS where Version is not null order by 1
This was working and then failed recently. I think it is because some of the strings now added contain a number as the first character.
I found to get it to work I had to use decode statement. (To_Char did not work )
SELECT distinct decode (substr(version,1,1),'1','?','0','!',substr(version,1,1)) as COL1 FROM SPHVVERS where Version is not null order by 1`

[up](https://www.php.net/manual/vote-note.php?id=29344&page=function.oci-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=29344&page=function.oci-result&vote=down "Vote down!")

 -2


[**_jthome at fcgov dot com_**](https://www.php.net/manual/en/function.oci-result.php#29344) [¶](https://www.php.net/manual/en/function.oci-result.php#29344)

**22 years ago**

`FYI--
In order to modify Oracle dates (using NLS_DATE_FORMAT...), you must set $ORACLE_HOME first.  This environmental variable is best set in the server startup script (i.e., ./apachectl)
--
Jim`

[up](https://www.php.net/manual/vote-note.php?id=8184&page=function.oci-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=8184&page=function.oci-result&vote=down "Vote down!")

 -2


[**_shayman at quiver dot com_**](https://www.php.net/manual/en/function.oci-result.php#8184) [¶](https://www.php.net/manual/en/function.oci-result.php#8184)

**25 years ago**

`As this function gets a 'mixed' variable type for the column index, you may use an integer to represent the column number. In this case, the count is starting from 1 and not from zero.
I am not sure, but I think this method is a bit faster than using the column name.
For an example, see the OCINumCols first example.`

[up](https://www.php.net/manual/vote-note.php?id=35445&page=function.oci-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=35445&page=function.oci-result&vote=down "Vote down!")

 -3


[**_gabi at gambita dot de_**](https://www.php.net/manual/en/function.oci-result.php#35445) [¶](https://www.php.net/manual/en/function.oci-result.php#35445)

**22 years ago**

`if you want to join two tables having both the same column (e.g. 'id') but you don't want to (or cannot) specify all the other fields in these two tables (like erabbott mentioned), you can use:
SELECT t1.*, t2.*, t1.id AS id1, t2.id AS id2
FROM table1 t1, table2 t2;
Note that this does _not_ work:
SELECT *,t1.id AS id1, t2.id AS id2
FROM table1 t1, table2 t2;`

[up](https://www.php.net/manual/vote-note.php?id=20278&page=function.oci-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=20278&page=function.oci-result&vote=down "Vote down!")

 -3


[**_steve dot hurst at instem-lss dot co dot uk_**](https://www.php.net/manual/en/function.oci-result.php#20278) [¶](https://www.php.net/manual/en/function.oci-result.php#20278)

**23 years ago**

`I am trying to get a list of the first character of a character string.
SELECT distinct substr(version,1,1) as COL1 FROM SPHVVERS where Version is not null order by 1
This was working and then failed recently. I think it is because some of the strings now added contain a number as the first character.
I found to get it to work I had to use decode statement. (To_Char did not work )
SELECT distinct decode (substr(version,1,1),'1','?','0','!',substr(version,1,1)) as COL1 FROM SPHVVERS where Version is not null order by 1`

[up](https://www.php.net/manual/vote-note.php?id=12487&page=function.oci-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=12487&page=function.oci-result&vote=down "Vote down!")

 -4


[**_dwilson at cae dot wisc dot edu_**](https://www.php.net/manual/en/function.oci-result.php#12487) [¶](https://www.php.net/manual/en/function.oci-result.php#12487)

**24 years ago**

`I complained that I couldn't get the time from an Oracle date field.  Joe Brown said:
This is not a PHP bug.
Consider setting NLS_DATE_FORMAT.
The manual states OCIResult() returns everything as a string.
NLS_DATE_FORMAT may not be appropriate for your needs.
There are quite a few places you can set NLS_DATE_FORMAT.
* Environment variables (or windows registry on win32)
* orclSID.ora
* on a per session basis; execute this statement after logon:
$cursor=OCIParse($connection,
"ALTER SESSION SET NLS_DATE_FORMAT='YYYY-MM-DD HH24:MI:SS'");
OCIExecute($cursor);
OCIFreeCursor($cursor);`

[up](https://www.php.net/manual/vote-note.php?id=25548&page=function.oci-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=25548&page=function.oci-result&vote=down "Vote down!")

 -5


[**_erabbott at NOSPAMterra dot com dot br_**](https://www.php.net/manual/en/function.oci-result.php#25548) [¶](https://www.php.net/manual/en/function.oci-result.php#25548)

**23 years ago**

`As in my previous post, the same thing applies when using conversion functions in CLOB columns.
Probably the same thing will occur to any conversion function that you use.
So, this wont work
SELECT ... TO_CHAR(MY_CLOB) ...
$my_clob = OCIResult($stmt,"MY_CLOB");
But this will:
SELECT ... TO_CHAR(MY_CLOB) AS MYC ...
$my_clob = OCIResult($stmt,"MYC");
Best regards.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.oci-result&repo=en&redirect=https://www.php.net/manual/en/function.oci-result.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google