---
url: https://www.php.net/manual/en/mysqli-result.fetch-field.php
scraped_at: 2025-10-20T02:47:11.761Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::fetch\_field

# mysqli\_fetch\_field

(PHP 5, PHP 7, PHP 8)

mysqli\_result::fetch\_field \-\- mysqli\_fetch\_field — Returns the next field in the result set

### Description [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php\#refsect1-mysqli-result.fetch-field-description)

Object-oriented style

public**mysqli\_result::fetch\_field**(): [object](https://www.php.net/manual/en/language.types.object.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Procedural style

**mysqli\_fetch\_field**([mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) `$result`): [object](https://www.php.net/manual/en/language.types.object.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Returns the definition of one column of a result set as an object. Call
this function repeatedly to retrieve information about all columns in the
result set.


### Parameters [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php\#refsect1-mysqli-result.fetch-field-parameters)

`result`

Procedural style only: A [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)
object returned by [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php), [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
[mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php).

### Return Values [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php\#refsect1-mysqli-result.fetch-field-returnvalues)

Returns an object which contains field definition information or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**
if no field information is available.


| Property | Description |
| --- | --- |
| name | The name of the column |
| orgname | Original column name if an alias was specified |
| table | The name of the table this field belongs to (if not calculated) |
| orgtable | Original table name if an alias was specified |
| def | Unused. Always an empty string |
| db | The name of the database |
| catalog | Unused. Always `"def"` |
| max\_length | The maximum width of the field for the result set. As of PHP 8.1, this value is always `0`. |
| length | The width of the field in bytes. For string columns,<br> the length value varies on the connection character set. For example,<br> if the character set is `latin1`, a single-byte character set,<br> the length value for a `SELECT 'abc'` query is 3.<br> If the character set is `utf8mb4`, a multibyte character<br> set in which characters take up to 4 bytes, the length value is 12. |
| charsetnr | The character set number for the field. |
| flags | An integer representing the bit-flags for the field. |
| type | The data type used for this field |
| decimals | The number of decimals for numeric fields, and the fractional seconds precision for temporal fields. |

**Object properties**

### Examples [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php\#refsect1-mysqli-result.fetch-field-examples)

**Example #1 Object-oriented style**

`<?php
$mysqli = new mysqli("localhost", "my_user", "my_password", "world");
/* check connection */
if (mysqli_connect_errno()) {
    printf("Connect failed: %s\n", mysqli_connect_error());
    exit();
}
$query = "SELECT Name, SurfaceArea from Country ORDER BY Code LIMIT 5";
if ($result = $mysqli->query($query)) {
    /* Get field information for all columns */
    while ($finfo = $result->fetch_field()) {
        printf("Name:     %s\n", $finfo->name);
        printf("Table:    %s\n", $finfo->table);
        printf("max. Len: %d\n", $finfo->max_length);
        printf("Flags:    %d\n", $finfo->flags);
        printf("Type:     %d\n\n", $finfo->type);
    }
    $result->close();
}
/* close connection */
$mysqli->close();
?>`

**Example #2 Procedural style**

`<?php
$link = mysqli_connect("localhost", "my_user", "my_password", "world");
/* check connection */
if (mysqli_connect_errno()) {
    printf("Connect failed: %s\n", mysqli_connect_error());
    exit();
}
$query = "SELECT Name, SurfaceArea from Country ORDER BY Code LIMIT 5";
if ($result = mysqli_query($link, $query)) {
    /* Get field information for all fields */
    while ($finfo = mysqli_fetch_field($result)) {
        printf("Name:     %s\n", $finfo->name);
        printf("Table:    %s\n", $finfo->table);
        printf("max. Len: %d\n", $finfo->max_length);
        printf("Flags:    %d\n", $finfo->flags);
        printf("Type:     %d\n\n", $finfo->type);
    }
    mysqli_free_result($result);
}
/* close connection */
mysqli_close($link);
?>`

The above examples will output:

```
Name:     Name
Table:    Country
max. Len: 11
Flags:    1
Type:     254

Name:     SurfaceArea
Table:    Country
max. Len: 10
Flags:    32769
Type:     4
```

### See Also [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php\#refsect1-mysqli-result.fetch-field-seealso)

- [mysqli\_num\_fields()](https://www.php.net/manual/en/mysqli-result.field-count.php) \- Gets the number of fields in the result set
- [mysqli\_fetch\_field\_direct()](https://www.php.net/manual/en/mysqli-result.fetch-field-direct.php) \- Fetch meta-data for a single field
- [mysqli\_fetch\_fields()](https://www.php.net/manual/en/mysqli-result.fetch-fields.php) \- Returns an array of objects representing the fields in a result set
- [mysqli\_field\_seek()](https://www.php.net/manual/en/mysqli-result.field-seek.php) \- Set result pointer to a specified field offset

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/fetch-field.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.fetch-field%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.fetch-field&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.fetch-field.php)

### User Contributed Notes 8 notes

[up](https://www.php.net/manual/vote-note.php?id=106064&page=mysqli-result.fetch-field&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106064&page=mysqli-result.fetch-field&vote=down "Vote down!")

63


[**_iansoko at hotmail dot com_**](https://www.php.net/manual/en/mysqli-result.fetch-field.php#106064) [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php#106064)

**14 years ago**

`here are the data types that correspond to the TYPE number returned by fetch_field.
thought i would post this here since i couldn't find the info elsewhere.
numerics
-------------
BIT: 16
TINYINT: 1
BOOL: 1
SMALLINT: 2
MEDIUMINT: 9
INTEGER: 3
BIGINT: 8
SERIAL: 8
FLOAT: 4
DOUBLE: 5
DECIMAL: 246
NUMERIC: 246
FIXED: 246
dates
------------
DATE: 10
DATETIME: 12
TIMESTAMP: 7
TIME: 11
YEAR: 13
strings & binary
------------
CHAR: 254
VARCHAR: 253
ENUM: 254
SET: 254
BINARY: 254
VARBINARY: 253
TINYBLOB: 252
BLOB: 252
MEDIUMBLOB: 252
TINYTEXT: 252
TEXT: 252
MEDIUMTEXT: 252
LONGTEXT: 252`

[up](https://www.php.net/manual/vote-note.php?id=107549&page=mysqli-result.fetch-field&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107549&page=mysqli-result.fetch-field&vote=down "Vote down!")

5


[**_Anonymous_**](https://www.php.net/manual/en/mysqli-result.fetch-field.php#107549) [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php#107549)

**13 years ago**

`The constants for the TYPE number returned by fetch_field are enumerated here (MYSQLI_TYPE_*):
[http://php.net/manual/en/mysqli.constants.php](http://php.net/manual/en/mysqli.constants.php)`

[up](https://www.php.net/manual/vote-note.php?id=85776&page=mysqli-result.fetch-field&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85776&page=mysqli-result.fetch-field&vote=down "Vote down!")

13


[**_ragtag at hotmail dot com_**](https://www.php.net/manual/en/mysqli-result.fetch-field.php#85776) [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php#85776)

**17 years ago**

`The flags used by MySql are:
       NOT_NULL_FLAG = 1
       PRI_KEY_FLAG = 2
       UNIQUE_KEY_FLAG = 4
       BLOB_FLAG = 16
       UNSIGNED_FLAG = 32
       ZEROFILL_FLAG = 64
       BINARY_FLAG = 128
       ENUM_FLAG = 256
       AUTO_INCREMENT_FLAG = 512
       TIMESTAMP_FLAG = 1024
       SET_FLAG = 2048
       NUM_FLAG = 32768
       PART_KEY_FLAG = 16384
       GROUP_FLAG = 32768
       UNIQUE_FLAG = 65536
To test if a flag is set you can use & like so:
<?php
$meta = $mysqli_result_object->fetch_field();
if ($meta->flags & 4) {
echo 'Unique key flag is set';
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=114876&page=mysqli-result.fetch-field&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114876&page=mysqli-result.fetch-field&vote=down "Vote down!")

2


[**_andre at koethur dot de_**](https://www.php.net/manual/en/mysqli-result.fetch-field.php#114876) [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php#114876)

**11 years ago**

`Here are two methods for converting the 'type' and 'flags' attributes to text for debugging purposes. They both use the predefined MYSQLI_ constants to generate the text.
<?php
public static function h_type2txt($type_id)
{
    static $types;
    if (!isset($types))
    {
        $types = array();
        $constants = get_defined_constants(true);
        foreach ($constants['mysqli'] as $c => $n) if (preg_match('/^MYSQLI_TYPE_(.*)/', $c, $m)) $types[$n] = $m[1];
    }
    return array_key_exists($type_id, $types)? $types[$type_id] : NULL;
}
public static function h_flags2txt($flags_num)
{
    static $flags;
    if (!isset($flags))
    {
        $flags = array();
        $constants = get_defined_constants(true);
        foreach ($constants['mysqli'] as $c => $n) if (preg_match('/MYSQLI_(.*)_FLAG$/', $c, $m)) if (!array_key_exists($n, $flags)) $flags[$n] = $m[1];
    }
    $result = array();
    foreach ($flags as $n => $t) if ($flags_num & $n) $result[] = $t;
    return implode(' ', $result);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=122515&page=mysqli-result.fetch-field&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122515&page=mysqli-result.fetch-field&vote=down "Vote down!")

1


[**_sofe2038 at gmail dot com_**](https://www.php.net/manual/en/mysqli-result.fetch-field.php#122515) [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php#122515)

**7 years ago**

`The constants in a few other comments above appear to be inaccurate. Here are some more official references that seem quite hard to search.
The "type" attribute: [https://dev.mysql.com/doc/internals/en/com-query-response.html#column-type](https://dev.mysql.com/doc/internals/en/com-query-response.html#column-type)
The "flags" attribute: [https://github.com/google/mysql/blob/master/include/mysql\_com.h#L133](https://github.com/google/mysql/blob/master/include/mysql_com.h#L133)
In addition, all attributes are explained on the COM_QUERY_RESPONSE page too: [https://dev.mysql.com/doc/internals/en/com-query-response.html#column-definition](https://dev.mysql.com/doc/internals/en/com-query-response.html#column-definition)`

[up](https://www.php.net/manual/vote-note.php?id=120068&page=mysqli-result.fetch-field&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120068&page=mysqli-result.fetch-field&vote=down "Vote down!")

1


[**_rvila at revolutionvisualarts dot com_**](https://www.php.net/manual/en/mysqli-result.fetch-field.php#120068) [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php#120068)

**8 years ago**

`The predefined constant values returned by the function get_predefined_constants() for:
MYSQLI_TYPE_CHAR = 1
MYSQLI _TYPE_TINYINT = 1
If the code is used to categorized the type of field use this values will of course create confusion. For example:
if($fieldtype === "CHAR"){
    $field_html_attribute = "text";
    $field_html_length = 1;
} elseif($fieldtype === "TINYINT") {
    $field_html_attribute = "number";
    $field_html_length = 1;
}
If an array is created to set the key as the numeric value and the value of that key as the the text title, TINYINT will be replaced by CHAR value. But is this process is reversed, then the code will select TINYINT if the foreach statement set to break when the numeric value of the flag equals the value of the current key as the first intance.
Base in the note added by Johnathan at [http://php.net/manual/en/mysqli.field-count.php](http://php.net/manual/en/mysqli.field-count.php) the values should be:
CHAR = 254
TINYINT = 1
But predefined function attributes the value 254 to MYSQLI_TYPE_STRING.
Just for FYI`

[up](https://www.php.net/manual/vote-note.php?id=121854&page=mysqli-result.fetch-field&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121854&page=mysqli-result.fetch-field&vote=down "Vote down!")

0


[**_nick_**](https://www.php.net/manual/en/mysqli-result.fetch-field.php#121854) [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php#121854)

**7 years ago**

`It is not possible to get the values for an enum or set field through fetch_fields(). As far as I can tell this is because it hasn't been implemented in the mysqlnd api but whatever the reason it is not possible and you must issue a query like SHOW COLUMNS directly and interrogate the result to determine them.
Incidentally you need to check the enum_flag rather than look for the enum_type to determine whether a field is enum or not. The type returned is usually some kind of string.`

[up](https://www.php.net/manual/vote-note.php?id=111151&page=mysqli-result.fetch-field&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111151&page=mysqli-result.fetch-field&vote=down "Vote down!")

2


[**_miqrogroove at gmail dot com_**](https://www.php.net/manual/en/mysqli-result.fetch-field.php#111151) [¶](https://www.php.net/manual/en/mysqli-result.fetch-field.php#111151)

**12 years ago**

`Beware the values of the predefined constants.  They do not always correlate with the actual field types.  For example:
MYSQLI_TYPE_BLOB: 252
MYSQLI_TYPE_TINY_BLOB: 249
MYSQLI_TYPE_MEDIUM_BLOB: 250
MYSQLI_TYPE_LONG_BLOB: 251
MySQLi will indeed return a value of 252 for a tinytext field, but as you can see, this does not correspond to the value of MYSQLI_TYPE_TINY_BLOB.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.fetch-field&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.fetch-field.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google