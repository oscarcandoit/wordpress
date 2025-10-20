---
url: https://www.php.net/manual/en/mysqli-result.fetch-fields.php
scraped_at: 2025-10-20T02:37:07.592Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mysqli\_result::fetch\_fields

# mysqli\_fetch\_fields

(PHP 5, PHP 7, PHP 8)

mysqli\_result::fetch\_fields \-\- mysqli\_fetch\_fields — Returns an array of objects representing the fields in a result set

### Description [¶](https://www.php.net/manual/en/mysqli-result.fetch-fields.php\#refsect1-mysqli-result.fetch-fields-description)

Object-oriented style

public**mysqli\_result::fetch\_fields**(): [array](https://www.php.net/manual/en/language.types.array.php)

Procedural style

**mysqli\_fetch\_fields**([mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) `$result`): [array](https://www.php.net/manual/en/language.types.array.php)

This function serves an identical purpose to the
[mysqli\_fetch\_field()](https://www.php.net/manual/en/mysqli-result.fetch-field.php) function with the single
difference that, instead of returning one object at a time for each field,
the columns are returned as an array of objects.


### Parameters [¶](https://www.php.net/manual/en/mysqli-result.fetch-fields.php\#refsect1-mysqli-result.fetch-fields-parameters)

`result`

Procedural style only: A [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php)
object returned by [mysqli\_query()](https://www.php.net/manual/en/mysqli.query.php), [mysqli\_store\_result()](https://www.php.net/manual/en/mysqli.store-result.php),
[mysqli\_use\_result()](https://www.php.net/manual/en/mysqli.use-result.php) or [mysqli\_stmt\_get\_result()](https://www.php.net/manual/en/mysqli-stmt.get-result.php).

### Return Values [¶](https://www.php.net/manual/en/mysqli-result.fetch-fields.php\#refsect1-mysqli-result.fetch-fields-returnvalues)

Returns an array of objects containing field definition information.


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

### Examples [¶](https://www.php.net/manual/en/mysqli-result.fetch-fields.php\#refsect1-mysqli-result.fetch-fields-examples)

**Example #1 Object-oriented style**

`<?php
$mysqli = new mysqli("127.0.0.1", "root", "foofoo", "sakila");
/* check connection */
if ($mysqli->connect_errno) {
    printf("Connect failed: %s\n", $mysqli->connect_error);
    exit();
}
foreach (array('latin1', 'utf8') as $charset) {
    // Set character set, to show its impact on some values (e.g., length in bytes)
    $mysqli->set_charset($charset);
    $query = "SELECT actor_id, last_name from actor ORDER BY actor_id";
    echo "======================\n";
    echo "Character Set: $charset\n";
    echo "======================\n";

    if ($result = $mysqli->query($query)) {
        /* Get field information for all columns */
        $finfo = $result->fetch_fields();
        foreach ($finfo as $val) {
            printf("Name:      %s\n",   $val->name);
            printf("Table:     %s\n",   $val->table);
            printf("Max. Len:  %d\n",   $val->max_length);
            printf("Length:    %d\n",   $val->length);
            printf("charsetnr: %d\n",   $val->charsetnr);
            printf("Flags:     %d\n",   $val->flags);
            printf("Type:      %d\n\n", $val->type);
        }
        $result->free();
    }
}
$mysqli->close();
?>`

**Example #2 Procedural style**

`<?php
$link = mysqli_connect("127.0.0.1", "my_user", "my_password", "sakila");
/* check connection */
if (mysqli_connect_errno()) {
    printf("Connect failed: %s\n", mysqli_connect_error());
    exit();
}
foreach (array('latin1', 'utf8') as $charset) {
    // Set character set, to show its impact on some values (e.g., length in bytes)
    mysqli_set_charset($link, $charset);
    $query = "SELECT actor_id, last_name from actor ORDER BY actor_id";
    echo "======================\n";
    echo "Character Set: $charset\n";
    echo "======================\n";
    if ($result = mysqli_query($link, $query)) {
        /* Get field information for all columns */
        $finfo = mysqli_fetch_fields($result);
        foreach ($finfo as $val) {
            printf("Name:      %s\n",   $val->name);
            printf("Table:     %s\n",   $val->table);
            printf("Max. Len:  %d\n",   $val->max_length);
            printf("Length:    %d\n",   $val->length);
            printf("charsetnr: %d\n",   $val->charsetnr);
            printf("Flags:     %d\n",   $val->flags);
            printf("Type:      %d\n\n", $val->type);
        }
        mysqli_free_result($result);
    }
}
mysqli_close($link);
?>`

The above examples will output:

```
======================
Character Set: latin1
======================
Name:      actor_id
Table:     actor
Max. Len:  3
Length:    5
charsetnr: 63
Flags:     49699
Type:      2

Name:      last_name
Table:     actor
Max. Len:  12
Length:    45
charsetnr: 8
Flags:     20489
Type:      253

======================
Character Set: utf8
======================
Name:      actor_id
Table:     actor
Max. Len:  3
Length:    5
charsetnr: 63
Flags:     49699
Type:      2

Name:      last_name
Table:     actor
Max. Len:  12
Length:    135
charsetnr: 33
Flags:     20489
```

### See Also [¶](https://www.php.net/manual/en/mysqli-result.fetch-fields.php\#refsect1-mysqli-result.fetch-fields-seealso)

- [mysqli\_num\_fields()](https://www.php.net/manual/en/mysqli-result.field-count.php) \- Gets the number of fields in the result set
- [mysqli\_fetch\_field\_direct()](https://www.php.net/manual/en/mysqli-result.fetch-field-direct.php) \- Fetch meta-data for a single field
- [mysqli\_fetch\_field()](https://www.php.net/manual/en/mysqli-result.fetch-field.php) \- Returns the next field in the result set

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/mysqli_result/fetch-fields.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmysqli-result.fetch-fields%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.fetch-fields&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.fetch-fields.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=101828&page=mysqli-result.fetch-fields&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101828&page=mysqli-result.fetch-fields&vote=down "Vote down!")

16


[**_AndrewRoz_**](https://www.php.net/manual/en/mysqli-result.fetch-fields.php#101828) [¶](https://www.php.net/manual/en/mysqli-result.fetch-fields.php#101828)

**14 years ago**

`The field info bit-flags used by MySql are:
(Thanks to ragtag at hotmail dot com)
<?php
/*
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
*/
// To test if a flag is set you can use & like so:
$meta = $mysqli_result_object->fetch_field();
if ($meta->flags & 4) {
     echo 'Unique key flag is set';
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=114883&page=mysqli-result.fetch-fields&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114883&page=mysqli-result.fetch-fields&vote=down "Vote down!")

6


[**_andre at koethur dot de_**](https://www.php.net/manual/en/mysqli-result.fetch-fields.php#114883) [¶](https://www.php.net/manual/en/mysqli-result.fetch-fields.php#114883)

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

[up](https://www.php.net/manual/vote-note.php?id=120045&page=mysqli-result.fetch-fields&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120045&page=mysqli-result.fetch-fields&vote=down "Vote down!")

4


[**_mccharles dot craven at dot dot gov_**](https://www.php.net/manual/en/mysqli-result.fetch-fields.php#120045) [¶](https://www.php.net/manual/en/mysqli-result.fetch-fields.php#120045)

**9 years ago**

`Those wanting to map the 'type' field in this function for use in mysqli_stmt_bind_param or to cannibalize it for their own mapping may find this function useful.
function map_field_type_to_bind_type($field_type)
{
    switch ($field_type)
    {
    case MYSQLI_TYPE_DECIMAL:
    case MYSQLI_TYPE_NEWDECIMAL:
    case MYSQLI_TYPE_FLOAT:
    case MYSQLI_TYPE_DOUBLE:
        return 'd';
    case MYSQLI_TYPE_BIT:
    case MYSQLI_TYPE_TINY:
    case MYSQLI_TYPE_SHORT:
    case MYSQLI_TYPE_LONG:
    case MYSQLI_TYPE_LONGLONG:
    case MYSQLI_TYPE_INT24:
    case MYSQLI_TYPE_YEAR:
    case MYSQLI_TYPE_ENUM:
        return 'i';
    case MYSQLI_TYPE_TIMESTAMP:
    case MYSQLI_TYPE_DATE:
    case MYSQLI_TYPE_TIME:
    case MYSQLI_TYPE_DATETIME:
    case MYSQLI_TYPE_NEWDATE:
    case MYSQLI_TYPE_INTERVAL:
    case MYSQLI_TYPE_SET:
    case MYSQLI_TYPE_VAR_STRING:
    case MYSQLI_TYPE_STRING:
    case MYSQLI_TYPE_CHAR:
    case MYSQLI_TYPE_GEOMETRY:
        return 's';
    case MYSQLI_TYPE_TINY_BLOB:
    case MYSQLI_TYPE_MEDIUM_BLOB:
    case MYSQLI_TYPE_LONG_BLOB:
    case MYSQLI_TYPE_BLOB:
        return 'b';
    default:
        trigger_error("unknown type: $field_type");
        return 's';
    }
}`

[up](https://www.php.net/manual/vote-note.php?id=113949&page=mysqli-result.fetch-fields&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113949&page=mysqli-result.fetch-fields&vote=down "Vote down!")

3


[**_educarme at adinet dot com dot uy_**](https://www.php.net/manual/en/mysqli-result.fetch-fields.php#113949) [¶](https://www.php.net/manual/en/mysqli-result.fetch-fields.php#113949)

**11 years ago**

`Codigos de tipos de datos devueltos por fetch_fields()
Nombre        Codigo
tinyint_    1
boolean_    1
smallint_    2
int_        3
float_        4
double_        5
real_        5
timestamp_    7
bigint_        8
serial        8
mediumint_    9
date_        10
time_        11
datetime_    12
year_        13
bit_        16
decimal_    246
text_        252
tinytext_    252
mediumtext_    252
longtext_    252
tinyblob_    252
mediumblob_    252
blob_        252
longblob_    252
varchar_    253
varbinary_    253
char_        254
binary_        254`

[up](https://www.php.net/manual/vote-note.php?id=116738&page=mysqli-result.fetch-fields&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116738&page=mysqli-result.fetch-fields&vote=down "Vote down!")

 -1


[**_cz dot paranoiq at gmail dot com_**](https://www.php.net/manual/en/mysqli-result.fetch-fields.php#116738) [¶](https://www.php.net/manual/en/mysqli-result.fetch-fields.php#116738)

**10 years ago**

`complete list of flags from MySQL source code:
NOT_NULL_FLAG   1       /* Field can't be NULL */
PRI_KEY_FLAG    2       /* Field is part of a primary key */
UNIQUE_KEY_FLAG 4       /* Field is part of a unique key */
MULTIPLE_KEY_FLAG 8     /* Field is part of a key */
BLOB_FLAG   16      /* Field is a blob */
UNSIGNED_FLAG   32      /* Field is unsigned */
ZEROFILL_FLAG   64      /* Field is zerofill */
BINARY_FLAG 128     /* Field is binary   */
ENUM_FLAG   256     /* field is an enum */
AUTO_INCREMENT_FLAG 512     /* field is a autoincrement field */
TIMESTAMP_FLAG  1024        /* Field is a timestamp */
SET_FLAG    2048        /* field is a set */
NO_DEFAULT_VALUE_FLAG 4096  /* Field doesn't have default value */
ON_UPDATE_NOW_FLAG 8192         /* Field is set to NOW on UPDATE */
NUM_FLAG    32768       /* Field is num (for clients) */
PART_KEY_FLAG   16384       /* Intern; Part of some key */
GROUP_FLAG  32768       /* Intern: Group field */
UNIQUE_FLAG 65536       /* Intern: Used by sql_yacc */
BINCMP_FLAG 131072      /* Intern: Used by sql_yacc */
GET_FIXED_FIELDS_FLAG (1 << 18) /* Used to get fields in item tree */
FIELD_IN_PART_FUNC_FLAG (1 << 19)/* Field part of partition func */`

[up](https://www.php.net/manual/vote-note.php?id=122454&page=mysqli-result.fetch-fields&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122454&page=mysqli-result.fetch-fields&vote=down "Vote down!")

 -2


[**_attand at gmail dot com_**](https://www.php.net/manual/en/mysqli-result.fetch-fields.php#122454) [¶](https://www.php.net/manual/en/mysqli-result.fetch-fields.php#122454)

**7 years ago**

`The nax_length gives counts in bytes. So if the text is utf-8, then we get incorrect result.
We have a code snippet where we check if the maximum length of the field and the max length of data stored becomes equal. This way we can check the potential truncation of data inserted`

[＋add a note](https://www.php.net/manual/add-note.php?sect=mysqli-result.fetch-fields&repo=en&redirect=https://www.php.net/manual/en/mysqli-result.fetch-fields.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google