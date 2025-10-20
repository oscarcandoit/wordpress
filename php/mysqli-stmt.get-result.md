---
url: https://www.php.net/manual/en/mysqli-stmt.get-result.php
scraped_at: 2025-10-20T02:31:16.843Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_stmt::get\_result

# mysqli\_stmt\_get\_result

(PHP 5 >= 5.3.0, PHP 7, PHP 8)

mysqli\_stmt::get\_result \-\- mysqli\_stmt\_get\_result — Gets a result set from a prepared statement as a [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) object

### Description [¶](https://www.php.net/manual/en/mysqli-stmt.get-result.php\#refsect1-mysqli-stmt.get-result-description)

Object-oriented style

public**mysqli\_stmt::get\_result**(): [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Procedural style

**mysqli\_stmt\_get\_result**([mysqli\_stmt](https://www.php.net/manual/en/class.mysqli-stmt.php) `$statement`): [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Retrieves a result set from a prepared statement as a
[mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) object. The data will be fetched from
the MySQL server to PHP. This method should be called only for
queries which produce a result set.


> **Note**:
>
>
> Available only with [mysqlnd](https://www.php.net/manual/en/book.mysqlnd.php).

> **Note**:
>
>
> This function cannot be used together
> with [mysqli\_stmt\_store\_result()](https://www.php.net/manual/en/mysqli-stmt.store-result.php). Both of these functions
> retrieve the full result set from the MySQL server.

### Parameters [¶](https://www.php.net/manual/en/mysqli-stmt.get-result.php\#refsect1-mysqli-stmt.get-result-parameters)

`statement`

Procedural style only: A [mysqli\_stmt](https://www.php.net/manual/en/class.mysqli-stmt.php) object
returned by [mysqli\_stmt\_init()](https://www.php.net/manual/en/mysqli.stmt-init.php).

### Return Values [¶](https://www.php.net/manual/en/mysqli-stmt.get-result.php\#refsect1-mysqli-stmt.get-result-returnvalues)

Returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure. For successful queries which produce a result set, such as `SELECT, SHOW, DESCRIBE` or
`EXPLAIN`, **mysqli\_stmt\_get\_result()** will return
a [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) object. For other successful queries, **mysqli\_stmt\_get\_result()** will
return **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**. The [mysqli\_stmt\_errno()](https://www.php.net/manual/en/mysqli-stmt.errno.php) function can be
used to distinguish between the two reasons for **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**; due to a bug, prior to PHP 7.4.13,
[mysqli\_errno()](https://www.php.net/manual/en/mysqli.errno.php) had to be used for this purpose.


### Errors/Exceptions [¶](https://www.php.net/manual/en/mysqli-stmt.get-result.php\#refsect1-mysqli-stmt.get-result-errors)

If mysqli error reporting is enabled ( **`[MYSQLI\_REPORT\_ERROR](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-error)`**) and the requested operation fails,
a warning is generated. If, in addition, the mode is set to **`[MYSQLI\_REPORT\_STRICT](https://www.php.net/manual/en/mysqli.constants.php#constant.mysqli-report-strict)`**,
a [mysqli\_sql\_exception](https://www.php.net/manual/en/class.mysqli-sql-exception.php) is thrown instead.

### Examples [¶](https://www.php.net/manual/en/mysqli-stmt.get-result.php\#refsect1-mysqli-stmt.get-result-examples)

**Example #1 Object-oriented style**

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
$query = "SELECT Name, Population, Continent FROM Country WHERE Continent=? ORDER BY Name LIMIT 1";
$stmt = $mysqli->prepare($query);
$stmt->bind_param("s", $continent);
$continentList = array('Europe', 'Africa', 'Asia', 'North America');
foreach ($continentList as $continent) {
    $stmt->execute();
    $result = $stmt->get_result();
    while ($row = $result->fetch_array(MYSQLI_NUM)) {
        foreach ($row as $r) {
            print "$r ";
        }
        print "\n";
    }
}`

**Example #2 Procedural style**

`<?php
mysqli_report(MYSQLI_REPORT_ERROR | MYSQLI_REPORT_STRICT);
$link = mysqli_connect("localhost", "my_user", "my_password", "world");
$query = "SELECT Name, Population, Continent FROM Country WHERE Continent=? ORDER BY Name LIMIT 1";
$stmt = mysqli_prepare($link, $query);
mysqli_stmt_bind_param($stmt, "s", $continent);
$continentList= array('Europe', 'Africa', 'Asia', 'North America');
foreach ($continentList as $continent) {
    mysqli_stmt_execute($stmt);
    $result = mysqli_stmt_get_result($stmt);
    while ($row = mysqli_fetch_array($result, MYSQLI_NUM)) {
        foreach ($row as $r) {
            print "$r ";
        }
        print "\n";
    }
}`

The above examples will output
something similar to:

```
Albania 3401200 Europe
Algeria 31471000 Africa
Afghanistan 22720000 Asia
Anguilla 8000 North America
```

### See Also [¶](https://www.php.net/manual/en/mysqli-stmt.get-result.php\#refsect1-mysqli-stmt.get-result-seealso)

- [mysqli\_prepare()](https://www.php.net/manual/en/mysqli.prepare.php) \- Prepares an SQL statement for execution
- [mysqli\_stmt\_result\_metadata()](https://www.php.net/manual/en/mysqli-stmt.result-metadata.php) \- Returns result set metadata from a prepared statement
- [mysqli\_stmt\_fetch()](https://www.php.net/manual/en/mysqli-stmt.fetch.php) \- Fetch results from a prepared statement into the bound variables
- [mysqli\_fetch\_array()](https://www.php.net/manual/en/mysqli-result.fetch-array.php) \- Fetch the next row of a result set as an associative, a numeric array, or both
- [mysqli\_stmt\_store\_result()](https://www.php.net/manual/en/mysqli-stmt.store-result.php) \- Stores a result set in an internal buffer

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_stmt/get-result.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-stmt.get-result%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-stmt.get-result&repo=en&redirect=https://www.php.net/manual/en/mysqli-stmt.get-result.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=113398&page=mysqli-stmt.get-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113398&page=mysqli-stmt.get-result&vote=down "Vote down!")

48


[**_Anonymous_**](https://www.php.net/manual/en/mysqli-stmt.get-result.php#113398) [¶](https://www.php.net/manual/en/mysqli-stmt.get-result.php#113398)

**12 years ago**

`I went through a lot of trouble on a server where mysqlnd wasn't available, and had a lot of headaches.
If you don't have mysqlnd installed/loaded whatever, you will get an undefined reference when trying to call "mysqli_stmt_get_result()".
I wrote my own mysqli_stmt_get_result() and a mysqli_result_fetch_array() to go with it.
<?php
class iimysqli_result
{
    public $stmt, $nCols;
}
function iimysqli_stmt_get_result($stmt)
{
    /**    EXPLANATION:
     * We are creating a fake "result" structure to enable us to have
     * source-level equivalent syntax to a query executed via
     * mysqli_query().
     *
     *    $stmt = mysqli_prepare($conn, "");
     *    mysqli_bind_param($stmt, "types", ...);
     *
     *    $param1 = 0;
     *    $param2 = 'foo';
     *    $param3 = 'bar';
     *    mysqli_execute($stmt);
     *    $result _mysqli_stmt_get_result($stmt);
     *        [ $arr = _mysqli_result_fetch_array($result);\
     *            || $assoc = _mysqli_result_fetch_assoc($result); ]
     *    mysqli_stmt_close($stmt);
     *    mysqli_close($conn);
     *
     * At the source level, there is no difference between this and mysqlnd.
     **/
    $metadata = mysqli_stmt_result_metadata($stmt);
    $ret = new iimysqli_result;
    if (!$ret) return NULL;
    $ret->nCols = mysqli_num_fields($metadata);
    $ret->stmt = $stmt;
    mysqli_free_result($metadata);
    return $ret;
}
function iimysqli_result_fetch_array(&$result)
{
    $ret = array();
    $code = "return mysqli_stmt_bind_result(\$result->stmt ";
    for ($i=0; $i<$result->nCols; $i++)
    {
        $ret[$i] = NULL;
        $code .= ", \$ret['" .$i ."']";
    };
    $code .= ");";
    if (!eval($code)) { return NULL; };
    // This should advance the "$stmt" cursor.
    if (!mysqli_stmt_fetch($result->stmt)) { return NULL; };
    // Return the array we built.
    return $ret;
}
?>
Hope this helps someone.`

[up](https://www.php.net/manual/vote-note.php?id=122869&page=mysqli-stmt.get-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122869&page=mysqli-stmt.get-result&vote=down "Vote down!")

23


[**_Anon_**](https://www.php.net/manual/en/mysqli-stmt.get-result.php#122869) [¶](https://www.php.net/manual/en/mysqli-stmt.get-result.php#122869)

**7 years ago**

`Please OH PLEASE.
I have been trying to get a result set from this function, and I had 0 luck completely, for nearly 3 hours!
If you ARE using mysqli_stmt_get_results() to get a result set, in conjuction with mysqli_stmt_store_results in order to retrieve the number of rows returned, you are going to have some major trouble!
PHP Documentation states that to retrieve the number of rows returned by a prepared select sql statement, one should call the following statements respectively:
mysqli_stmt_execute($stmt);
mysqli_stmt_store_result($stmt);
$num_rows = mysqli_stmt_num_rows($stmt);
THIS IS A MAJOR DEATH TRAP, IF YOU ARE USING mysqli_stmt_get_result() in conjunction!!!! Results of doing so vary depending which statements you call first, but in the end, you will NOT get the desired result.
In conclusion, please, PLEASE, NEVER use mysqli_stmt_store_result(), then mysqli_ AND mysqli_stmt_get_result() at the the same time. This is a MAJOR death trap.
SOLUTION:
If you are trying to get a result set, and you need the number of rows returned at the same time, use the following statements respectively instead:
$result_set = mysqli_stmt_get_results($stmt);
$num_rows = mysqli_num_rows($result_set);
Reflecting on my actions, this solution may seem fairly obvious. However, to someone new using PHP (like me) or someone who is not fully comfortable with prepared statements, it's very easy to get lost by using Google and learn on your own.
Summary:
NEVER use mysqli_stmt_store_result($stmt) & mysqli_stmt_num_rows($stmt) in conjunction with mysqli_stmt_get_result($stmt). You will regret it!! I have been stuck on this for hours, and Google offered me no answer!`

[up](https://www.php.net/manual/vote-note.php?id=105802&page=mysqli-stmt.get-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105802&page=mysqli-stmt.get-result&vote=down "Vote down!")

24


[**_jari dot wiklund at gmail dot com_**](https://www.php.net/manual/en/mysqli-stmt.get-result.php#105802) [¶](https://www.php.net/manual/en/mysqli-stmt.get-result.php#105802)

**14 years ago**

`Please note that this method requires the mysqlnd driver. Othervise you will get this error: Call to undefined method mysqli_stmt::get_result()`

[up](https://www.php.net/manual/vote-note.php?id=122897&page=mysqli-stmt.get-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122897&page=mysqli-stmt.get-result&vote=down "Vote down!")

5


[**_jeffspicer at gmail dot com_**](https://www.php.net/manual/en/mysqli-stmt.get-result.php#122897) [¶](https://www.php.net/manual/en/mysqli-stmt.get-result.php#122897)

**7 years ago**

`To prevent others from hours of screaming trying to figure out why this does not work when you have the native driver enabled.  It is because you need to make sure you enable both native drives mysqlnd and nd_mysqli on your server if you wish to use this functionality.
Otherwise just enabling the mysqlnd native driver does include the mysqli_stmt_get_result function as this apparently resides in the nd_mysqli native driver.  Unfortunately, most documentation only ever talks about the mysqlnd native driver.
Once you enable both native drivers this function works as documented.`

[up](https://www.php.net/manual/vote-note.php?id=120097&page=mysqli-stmt.get-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120097&page=mysqli-stmt.get-result&vote=down "Vote down!")

1


[**_Haravikk_**](https://www.php.net/manual/en/mysqli-stmt.get-result.php#120097) [¶](https://www.php.net/manual/en/mysqli-stmt.get-result.php#120097)

**8 years ago**

`For those interested, this function seems to always produce a stored result, making it equivalent to mysqli::store_result(), rather than fetching on demand as in the case of mysqli::use_result().
This is important as it means that you cannot control the nature of the result as you would normally by calling mysqli_stmt::store_result() prior to fetching, as I had personally expected.
So, if you want to emulate the behaviour of mysqli::use_result() you will still need to use mysqli_stmt::bind_param() and mysqli_stmt::fetch().`

[up](https://www.php.net/manual/vote-note.php?id=124074&page=mysqli-stmt.get-result&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124074&page=mysqli-stmt.get-result&vote=down "Vote down!")

1


[**_HeadlessDev_**](https://www.php.net/manual/en/mysqli-stmt.get-result.php#124074) [¶](https://www.php.net/manual/en/mysqli-stmt.get-result.php#124074)

**6 years ago**

`Thanks to everyone that leaves notes, without them I would not be able to do what I do. I wrote this function with help from notes on this page and others.
I did not have mysqlnd available to me, but wanted to be able to get_result() of a query as an object.
PLEASE NOTE: I am not an expert at PHP
Heres an example of using my get_result() to login users
<?php
    //Sanitize input before using this function
    function login($email, $password){
        require 'connect_db.php';
        $query = $sql->stmt_init();
        if($query->prepare("SELECT CustomerId, Password, Admin FROM users WHERE Email = ?")){
            $query->bind_param("s",$email);
            $result = get_result($query); //USING FUNCTION  HERE
            if($result != NULL){
                $user = $result[0];
                if(password_verify($password, $user->Password)){
                    $_SESSION['user_id'] = $user->CustomerId;
                    if($user->Admin == 1){
                        $_SESSION['admin'] = true;
                    }
                    $sql->close();
                    return true;
                }
            }
        }
        $sql->close();
        //If we get here they are not logged in
        return false;
    }
    //Returns an array with each row as an object
    function get_result($stmt){
        $stmt->execute(); //Execute query
        $stmt->store_result(); //Store the results
        $num_rows = $stmt->num_rows; //Get the number of results
        $results = NULL;
        if($num_rows > 0){
            //Get metadata about the results
            $meta = $stmt->result_metadata();
            //Here we get all the column/field names and create the binding code
            $bind_code = "return mysqli_stmt_bind_result(\$stmt, ";
            while($_field = $meta->fetch_field()){
                $bind_code .= "\$row[\"".$_field->name."\"], ";
            }
            //Replace trailing ", " with ");"
            $bind_code = substr_replace($bind_code,");", -2);
           //Run the code, if it doesn't work return NULL
            if(!eval($bind_code)) {
                $stmt->close();
                return NULL;
            }
            //This is where we create the object and add it to our final result array
            for($i=0;$i<$num_rows;$i++){
               //Gets the row by index
                $stmt->data_seek($i);
                //Update bound variables used in $bind_code with new row values
                $stmt->fetch();
                foreach($row as $key=>$value){
                    //Create array using the column/field name as the index
                    $_result[$key] = $value;
                }
                //Cast $_result to object and append to our final results
                $results[$i] = (object)$_result;
            }
        }
        $stmt->close();
        return $results;
    }
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-stmt.get-result&repo=en&redirect=https://www.php.net/manual/en/mysqli-stmt.get-result.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google