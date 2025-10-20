---
url: https://www.php.net/manual/en/mysqli.store-result.php
scraped_at: 2025-10-20T02:35:30.243Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli::store\_result

# mysqli\_store\_result

(PHP 5, PHP 7, PHP 8)

mysqli::store\_result \-\- mysqli\_store\_result — Transfers a result set from the last query

### Description [¶](https://www.php.net/manual/en/mysqli.store-result.php\#refsect1-mysqli.store-result-description)

Object-oriented style

public**mysqli::store\_result**([int](https://www.php.net/manual/en/language.types.integer.php) `$mode` = 0): [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Procedural style

**mysqli\_store\_result**([mysqli](https://www.php.net/manual/en/class.mysqli.php) `$mysql`, [int](https://www.php.net/manual/en/language.types.integer.php) `$mode` = 0): [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Transfers the result set from the last query on the database connection
represented by the `mysql` parameter to be used with
the [mysqli\_data\_seek()](https://www.php.net/manual/en/mysqli-result.data-seek.php) function.


### Parameters [¶](https://www.php.net/manual/en/mysqli.store-result.php\#refsect1-mysqli.store-result-parameters)

`mysql`

Procedural style only: A [mysqli](https://www.php.net/manual/en/class.mysqli.php) object
returned by [mysqli\_connect()](https://www.php.net/manual/en/function.mysqli-connect.php) or [mysqli\_init()](https://www.php.net/manual/en/mysqli.init.php)

`mode`

The option that you want to set. As of PHP 8.1, this parameter has no effect. It can be one of the following values:


| Name | Description |
| --- | --- |
| **`[MYSQLI\_STORE\_RESULT\_COPY\_DATA](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-store-result-copy-data)`** | Copy results from the internal mysqlnd buffer into the PHP variables fetched. By default,<br> mysqlnd will use a reference logic to avoid copying and duplicating results held in memory.<br> For certain result sets, for example, result sets with many small rows, the copy approach can<br> reduce the overall memory usage because PHP variables holding results may be<br> released earlier (available with mysqlnd only) |

**Valid options**

### Return Values [¶](https://www.php.net/manual/en/mysqli.store-result.php\#refsect1-mysqli.store-result-returnvalues)

Returns a buffered result object or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if an error occurred.


> **Note**:
>
>
> **mysqli\_store\_result()** returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** in case the query
> didn't return a result set (if the query was, for example an INSERT
> statement). This function also returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if the reading of the
> result set failed. You can check if you have got an error by checking
> if [mysqli\_error()](https://www.php.net/manual/en/mysqli.error.php) doesn't return an empty string, if
> [mysqli\_errno()](https://www.php.net/manual/en/mysqli.errno.php) returns a non zero value, or if
> [mysqli\_field\_count()](https://www.php.net/manual/en/mysqli.field-count.php) returns a non zero value.
> Also possible reason for this function returning **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** after
> successful call to [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php) can be too large
> result set (memory for it cannot be allocated). If
> [mysqli\_field\_count()](https://www.php.net/manual/en/mysqli.field-count.php) returns a non-zero value, the
> statement should have produced a non-empty result set.

### Errors/Exceptions [¶](https://www.php.net/manual/en/mysqli.store-result.php\#refsect1-mysqli.store-result-errors)

If mysqli error reporting is enabled ( **`[MYSQLI\_REPORT\_ERROR](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-error)`**) and the requested operation fails,
a warning is generated. If, in addition, the mode is set to **`[MYSQLI\_REPORT\_STRICT](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-strict)`**,
a [mysqli\_sql\_exception](https://www.php.net/manual/en/class.mysqli-sql-exception.php) is thrown instead.

### Changelog [¶](https://www.php.net/manual/en/mysqli.store-result.php\#refsect1-mysqli.store-result-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Passing the `mode` parameter is now deprecated.<br> The parameter has had no effect as of PHP 8.1.0. |

### Examples [¶](https://www.php.net/manual/en/mysqli.store-result.php\#refsect1-mysqli.store-result-examples)

See [mysqli\_multi\_query()](https://www.php.net/manual/en/mysqli.multi-query.php).


### Notes [¶](https://www.php.net/manual/en/mysqli.store-result.php\#refsect1-mysqli.store-result-notes)

> **Note**:
>
>
> Although it is always good practice to free the memory used by the result
> of a query using the [mysqli\_free\_result()](https://www.php.net/manual/en/mysqli-result.free.php) function,
> when transferring large result sets using the
> **mysqli\_store\_result()** this becomes particularly
> important.

### See Also [¶](https://www.php.net/manual/en/mysqli.store-result.php\#refsect1-mysqli.store-result-seealso)

- [mysqli\_real\_query()](https://www.php.net/manual/en/mysqli.real-query.php) \- Execute an SQL query
- [mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) \- Initiate a result set retrieval

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli/store-result.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli.store-result%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli.store-result&repo=en&redirect=https://www.php.net/manual/en/mysqli.store-result.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=96048&page=mysqli.store-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96048&page=mysqli.store-result&vote=down "Vote down!")

11


[**_mitchind_**](https://www.php.net/manual/en/mysqli.store-result.php#96048) [¶](https://www.php.net/manual/en/mysqli.store-result.php#96048)

**15 years ago**

`After reading through original notes and example above as well as wading through the documentation, I finally got a loop to work with two stored procedures.
Using the results of the first one as a parameter for the second one. Easier to do this way than a huge modified sequence of Inner Join queries.
Hope this helps others...
<?php
// Connect to server and database
$mysqli        = new mysqli("$dbServer", "$dbUser", "$dbPass", "$dbName");
// Open First Stored Procedure using MYSQLI_STORE_RESULT to retain for looping
$resultPicks = $mysqli->query("CALL $proc ($searchDate, $maxRSI, $incRSI, $minMACD, $minVol, $minTrades, $minClose, $maxClose)", MYSQLI_STORE_RESULT);
// process one row at a time from first SP
while($picksRow = $resultPicks->fetch_array(MYSQLI_ASSOC)) {
    // Get Parameter for next SP
    $symbol     = $picksRow['Symbol'];
    // Free stored results
    clearStoredResults($mysqli);
    // Execute second SP using value from first as a parameter (MYSQLI_USE_RESULT and free result right away)
    $resultData    = $mysqli->query("CALL prcGetLastMACDDatesBelowZero('$symbol', $searchDate)", MYSQLI_USE_RESULT);
    $dataRow    = $resultData->fetch_array(MYSQLI_ASSOC);
    // Dump result from both related queries
    echo "<p>$symbol ... Num Dates: " . $dataRow['NumDates'];
    // Free results from second SP
    $resultData->free();
}
// Free results from first SP
$resultPicks->free();
// close connections
$mysqli->close();
#------------------------------------------
function clearStoredResults($mysqli_link){
#------------------------------------------
    while($mysqli_link->next_result()){
      if($l_result = $mysqli_link->store_result()){
              $l_result->free();
      }
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=122404&page=mysqli.store-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122404&page=mysqli.store-result&vote=down "Vote down!")

2


[**_filippo at ecoms dot it_**](https://www.php.net/manual/en/mysqli.store-result.php#122404) [¶](https://www.php.net/manual/en/mysqli.store-result.php#122404)

**7 years ago**

`Code to handling errors:
if ($mysqli->multi_query($query)) {
    $result = $mysqli->store_result();
    if ($mysqli->errno == 0) {

        /* First result set or FALSE (if the query didn't return a result set) is stored in $result */
        while ($mysqli->more_results()) {
            if ($mysqli->next_result()) {
                $result = $mysqli->store_result();
                if ($mysqli->errno == 0) {
                    /* The result set or FALSE (see above) is stored in $result */
                }
                else {
                    /* Result set read error */
                    break;
                }
            }
            else {
                /* Error in the query */
            }
        }
    }
    else {
        /* First result set read error */
    }
}
else {
    /* Error in the first query */
}`

[up](https://www.php.net/manual/vote-note.php?id=92352&page=mysqli.store-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92352&page=mysqli.store-result&vote=down "Vote down!")

 -4


[**_Warner_**](https://www.php.net/manual/en/mysqli.store-result.php#92352) [¶](https://www.php.net/manual/en/mysqli.store-result.php#92352)

**16 years ago**

`It also seems, that executing a SET statement in multi_query() returns an extra recordset too, which one would not expect.`

[up](https://www.php.net/manual/vote-note.php?id=74478&page=mysqli.store-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74478&page=mysqli.store-result&vote=down "Vote down!")

 -4


[**_lau at goldenweb dot com dot au_**](https://www.php.net/manual/en/mysqli.store-result.php#74478) [¶](https://www.php.net/manual/en/mysqli.store-result.php#74478)

**18 years ago**

`Beware when using stored procedures:
If you connect to the database and then call dbproc A followed by a call to db proc B and then close the connection to the db, the second procedure call will not work.
It looks like there is a bug in MYSQL or mysqli that returns an extra recordset than you would expect. It then doesn't let you call another stored procedure until you finish processing all the recordsets from the first stored procedure call.
The solution is to simply loop through the additional recordsets between calls to db procs. Here is a function that I call between db proc calls:
<?php
#--------------------------------
function ClearRecordsets($p_Result){
#--------------------------------
    $p_Result->free();
    while($this->Mysqli->next_result()){
      if($l_result = $this->Mysqli->store_result()){
              $l_result->free();
      }
    }
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli.store-result&repo=en&redirect=https://www.php.net/manual/en/mysqli.store-result.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google