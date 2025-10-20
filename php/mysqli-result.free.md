---
url: https://www.php.net/manual/en/mysqli-result.free.php
scraped_at: 2025-10-20T02:32:10.618Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::free

# mysqli\_result::close

# mysqli\_result::free\_result

# mysqli\_free\_result

(PHP 5, PHP 7, PHP 8)

mysqli\_result::free \-\- mysqli\_result::close \-\- mysqli\_result::free\_result \-\- mysqli\_free\_result — Frees the memory associated with a result

### Description [¶](https://www.php.net/manual/en/mysqli-result.free.php\#refsect1-mysqli-result.free-description)

Object-oriented style

public**mysqli\_result::free**(): [void](https://www.php.net/manual/en/language.types.void.php)

public**mysqli\_result::close**(): [void](https://www.php.net/manual/en/language.types.void.php)

public**mysqli\_result::free\_result**(): [void](https://www.php.net/manual/en/language.types.void.php)

Procedural style

**mysqli\_free\_result**([mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) `$result`): [void](https://www.php.net/manual/en/language.types.void.php)

Frees the memory associated with the result.


### Parameters [¶](https://www.php.net/manual/en/mysqli-result.free.php\#refsect1-mysqli-result.free-parameters)

`result`

Procedural style only: A [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)
object returned by [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php), [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
[mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php).

### Return Values [¶](https://www.php.net/manual/en/mysqli-result.free.php\#refsect1-mysqli-result.free-returnvalues)

No value is returned.


### See Also [¶](https://www.php.net/manual/en/mysqli-result.free.php\#refsect1-mysqli-result.free-seealso)

- [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php) \- Performs a query on the database
- [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php) \- Gets a result set from a prepared statement as a mysqli\_result object
- [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php) \- Transfers a result set from the last query
- [mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) \- Initiate a result set retrieval

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/free.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.free%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.free&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.free.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=123708&page=mysqli-result.free&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123708&page=mysqli-result.free&vote=down "Vote down!")

19


[**_jack\_action100 at hotmail dot example dot com_**](https://www.php.net/manual/en/mysqli-result.free.php#123708) [¶](https://www.php.net/manual/en/mysqli-result.free.php#123708)

**6 years ago**

``If you are STILL getting this error, even after freeing your results:
Internal SQL Bug: 2014, Commands out of sync; you can't run this command now
You may have a stored procedure in your query.   A procedure can return more than one result set, and it will always return one extra empty result set that carries some meta information on the procedure call itself, especially error information. ( source:  [https://bugs.mysql.com/bug.php?id=71044](https://bugs.mysql.com/bug.php?id=71044) )
While calling single procedures, with one SELECT in them, using mysqli->query("CALL `stored_procedure`();"), I had to do the following to make it work between two calls:
<?php
$result->free();
$mysqli->next_result();
?>
It has no negative impact if you are not calling a stored procedure.``

[up](https://www.php.net/manual/vote-note.php?id=126623&page=mysqli-result.free&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126623&page=mysqli-result.free&vote=down "Vote down!")

1


[**_polygon dot co dot in at gmail dot com_**](https://www.php.net/manual/en/mysqli-result.free.php#126623) [¶](https://www.php.net/manual/en/mysqli-result.free.php#126623)

**3 years ago**

`We should free the mysql results using mysqli_free_result respectively or else this will consume your server RAM resource.
This is demonstrated as below
<?php
$link = mysqli_connect('Hostname','Username','Password','Database');
echo '<br/>Memory Usage Before Query = '.memory_get_usage(false); // 449464 bytes
$resultResource = mysqli_query($link, 'SELECT * FROM test');
echo '<br/>Memory Usage after Query = '.memory_get_usage(false); // 466528 bytes
$result = array();
while ($result[] = mysqli_fetch_assoc($resultResource)) {}
echo '<br/><br/>Memory Usage Before Free Result = '.memory_get_usage(false); // 474208 bytes
mysqli_free_result($resultResource);
echo '<br/>Memory Usage After Free Result = '.memory_get_usage(false); // 457336 bytes
?>
Output below.
Memory Usage Before Query = 449464
Memory Usage after Query = 466528
Memory Usage Before Free Result = 474208
Memory Usage After Free Result = 457336
So, One can observer there is memory usage after the query is executed. The results are returned by DB server to the web server instantaniously once the query execution is over. The results present on web server are then processed for fetching from the resource link on web server.
Also this is observed that there is lesser memory usage after using mysqli_free_result because the resources stored on web server for respective query are freed by providing respective resource link.`

[up](https://www.php.net/manual/vote-note.php?id=95357&page=mysqli-result.free&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95357&page=mysqli-result.free&vote=down "Vote down!")

2


[**_Vector at ionisis dot com_**](https://www.php.net/manual/en/mysqli-result.free.php#95357) [¶](https://www.php.net/manual/en/mysqli-result.free.php#95357)

**15 years ago**

`If you are getting this error:
Internal SQL Bug: 2014, Commands out of sync; you can't run this command now
Then you never called mysqli_result::free(), mysqli_result::free_result(), mysqli_result::close(), or mysqli_free_result() in your script, and must call it before executing another stored procedure.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.free&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.free.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google