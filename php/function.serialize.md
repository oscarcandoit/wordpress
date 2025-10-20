---
url: https://www.php.net/manual/en/function.serialize.php
scraped_at: 2025-10-20T02:35:45.736Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# serialize

(PHP 4, PHP 5, PHP 7, PHP 8)

serialize — Generates a storable representation of a value

### Description [¶](https://www.php.net/manual/en/function.serialize.php\#refsect1-function.serialize-description)

**serialize**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$value`): [string](https://www.php.net/manual/en/language.types.string.php)

Generates a storable representation of a value.


This is useful for storing or passing PHP values around without
losing their type and structure.


To make the serialized string into a PHP value again, use
[unserialize()](https://www.php.net/manual/en/function.unserialize.php).


### Parameters [¶](https://www.php.net/manual/en/function.serialize.php\#refsect1-function.serialize-parameters)

`value`

The value to be serialized. **serialize()**
handles all types, except the [resource](https://www.php.net/manual/en/language.types.resource.php)-type and some [object](https://www.php.net/manual/en/language.types.object.php)s (see note below).
You can even **serialize()** arrays that contain
references to itself. Circular references inside the array/object you
are serializing will also be stored. Any other
reference will be lost.


When serializing objects, PHP will attempt to call the member functions
[\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize) or
[\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep) prior to serialization.
This is to allow the object to do any last minute clean-up, etc. prior
to being serialized. Likewise, when the object is restored using
[unserialize()](https://www.php.net/manual/en/function.unserialize.php) the [\_\_unserialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.unserialize) or
[\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php#object.wakeup) member function is called.


> **Note**:
>
>
> Object's private members have the class name prepended to the member
> name; protected members have a '\*' prepended to the member name.
> These prepended values have null bytes on either side.

### Return Values [¶](https://www.php.net/manual/en/function.serialize.php\#refsect1-function.serialize-returnvalues)

Returns a string containing a byte-stream representation of
`value` that can be stored anywhere.


Note that this is a binary string which may include null bytes, and needs
to be stored and handled as such. For example,
**serialize()** output should generally be stored in a BLOB
field in a database, rather than a CHAR or TEXT field.


### Examples [¶](https://www.php.net/manual/en/function.serialize.php\#refsect1-function.serialize-examples)

**Example #1 **serialize()** example**

`<?php
// $session_data contains a multi-dimensional array with session
// information for the current user.  We use serialize() to store
// it in a database at the end of the request.
$conn = odbc_connect("webdb", "php", "chicken");
$stmt = odbc_prepare($conn,
      "UPDATE sessions SET data = ? WHERE id = ?");
$sqldata = array (serialize($session_data), $_SERVER['PHP_AUTH_USER']);
if (!odbc_execute($stmt, $sqldata)) {
    $stmt = odbc_prepare($conn,
     "INSERT INTO sessions (id, data) VALUES(?, ?)");
    if (!odbc_execute($stmt, array_reverse($sqldata))) {
        /* Something went wrong.. */
    }
}
?>`

### Notes [¶](https://www.php.net/manual/en/function.serialize.php\#refsect1-function.serialize-notes)

> **Note**:
>
>
> Note that many built-in PHP objects cannot be serialized. However, those with
> this ability either implement the [Serializable](https://www.php.net/manual/en/class.serializable.php) interface or the
> magic [\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize)/ [\_\_unserialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.unserialize)
> or [\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep)/ [\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php#object.wakeup) methods. If an
> internal class does not fulfill any of those requirements, it cannot reliably be
> serialized.
>
>
> There are some historical exceptions to the above rule, where some internal objects
> could be serialized without implementing the interface or exposing the methods.

**Warning**

When **serialize()** serializes objects, the leading backslash is not included in the class name of namespaced classes for maximum compatibility.


### See Also [¶](https://www.php.net/manual/en/function.serialize.php\#refsect1-function.serialize-seealso)

- [unserialize()](https://www.php.net/manual/en/function.unserialize.php) \- Creates a PHP value from a stored representation
- [var\_export()](https://www.php.net/manual/en/function.var-export.php) \- Outputs or returns a parsable string representation of a variable
- [json\_encode()](https://www.php.net/manual/en/function.json-encode.php) \- Returns the JSON representation of a value
- [Serializing Objects](https://www.php.net/manual/en/language.oop5.serialization.php)
- [\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep)
- [\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php#object.wakeup)
- [\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize)
- [\_\_unserialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.unserialize)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/functions/serialize.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.serialize%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.serialize&repo=en&redirect=https://www.php.net/manual/en/function.serialize.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=66147&page=function.serialize&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=66147&page=function.serialize&vote=down "Vote down!")

372


[**_egingell at sisna dot com_**](https://www.php.net/manual/en/function.serialize.php#66147) [¶](https://www.php.net/manual/en/function.serialize.php#66147)

**19 years ago**

`<?
/*
Anatomy of a serialize()'ed value:
String
s:size:value;
Integer
i:value;
Boolean
b:value; (does not store "true" or "false", does store '1' or '0')
Null
N;
Array
a:size:{key definition;value definition;(repeated per element)}
Object
O:strlen(object name):object name:object size:{s:strlen(property name):property name:property definition;(repeated per property)}
String values are always in double quotes
Array keys are always integers or strings
    "null => 'value'" equates to 's:0:"";s:5:"value";',
    "true => 'value'" equates to 'i:1;s:5:"value";',
    "false => 'value'" equates to 'i:0;s:5:"value";',
    "array(whatever the contents) => 'value'" equates to an "illegal offset type" warning because you can't use an
    array as a key; however, if you use a variable containing an array as a key, it will equate to 's:5:"Array";s:5:"value";',
     and
    attempting to use an object as a key will result in the same behavior as using an array will.
*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=107717&page=function.serialize&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107717&page=function.serialize&vote=down "Vote down!")

287


[**_Anonymous_**](https://www.php.net/manual/en/function.serialize.php#107717) [¶](https://www.php.net/manual/en/function.serialize.php#107717)

**13 years ago**

`Please! please! please! DO NOT serialize data and place it into your database. Serialize can be used that way, but that's missing the point of a relational database and the datatypes inherent in your database engine. Doing this makes data in your database non-portable, difficult to read, and can complicate queries. If you want your application to be portable to other languages, like let's say you find that you want to use Java for some portion of your app that it makes sense to use Java in, serialization will become a pain in the buttocks. You should always be able to query and modify data in the database without using a third party intermediary tool to manipulate data to be inserted.
I've encountered this too many times in my career, it makes for difficult to maintain code, code with portability issues, and data that is it more difficult to migrate to other RDMS systems, new schema, etc. It also has the added disadvantage of making it messy to search your database based on one of the fields that you've serialized.
That's not to say serialize() is useless. It's not... A good place to use it may be a cache file that contains the result of a data intensive operation, for instance. There are tons of others... Just don't abuse serialize because the next guy who comes along will have a maintenance or migration nightmare.`

[up](https://www.php.net/manual/vote-note.php?id=128200&page=function.serialize&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128200&page=function.serialize&vote=down "Vote down!")

5


[**_mark at bvits dot co dot uk_**](https://www.php.net/manual/en/function.serialize.php#128200) [¶](https://www.php.net/manual/en/function.serialize.php#128200)

**2 years ago**

`There is a type not mentioned in the user notes so far, 'E'.  This is the newer Enum class that can be utilised:
login_security|E:25:"Permission:manageClient"`

[up](https://www.php.net/manual/vote-note.php?id=60317&page=function.serialize&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60317&page=function.serialize&vote=down "Vote down!")

21


[**_MC\_Gurk at gmx dot net_**](https://www.php.net/manual/en/function.serialize.php#60317) [¶](https://www.php.net/manual/en/function.serialize.php#60317)

**19 years ago**

`If you are going to serialie an object which contains references to other objects you want to serialize some time later, these references will be lost when the object is unserialized.
The references can only be kept if all of your objects are serialized at once.
That means:
$a = new ClassA();
$b = new ClassB($a); //$b containes a reference to $a;
$s1=serialize($a);
$s2=serialize($b);
$a=unserialize($s1);
$b=unserialize($s2);
now b references to an object of ClassA which is not $a. $a is another object of Class A.
use this:
$buf[0]=$a;
$buf[1]=$b;
$s=serialize($buf);
$buf=unserialize($s);
$a=$buf[0];
$b=$buf[1];
all references are intact.`

[up](https://www.php.net/manual/vote-note.php?id=111168&page=function.serialize&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111168&page=function.serialize&vote=down "Vote down!")

24


[**_nh at ngin dot de_**](https://www.php.net/manual/en/function.serialize.php#111168) [¶](https://www.php.net/manual/en/function.serialize.php#111168)

**12 years ago**

`Serializing floating point numbers leads to weird precision offset errors:
<?php
echo round(96.670000000000002, 2);
// 96.67
echo serialize(round(96.670000000000002, 2));
// d:96.670000000000002;
echo serialize(96.67);
// d:96.670000000000002;
?>
Not only is this wrong, but it adds a lot of unnecessary bulk to serialized data. Probably better to use json_encode() instead (which apparently is faster than serialize(), anyway).`

[up](https://www.php.net/manual/vote-note.php?id=109953&page=function.serialize&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109953&page=function.serialize&vote=down "Vote down!")

11


[**_Andrew B_**](https://www.php.net/manual/en/function.serialize.php#109953) [¶](https://www.php.net/manual/en/function.serialize.php#109953)

**13 years ago**

`When you serialize an array the internal pointer will not be preserved. Apparently this is the expected behavior but was a bit of a gotcha moment for me. Copy and paste example below.
<?php
//Internal Pointer will be 2 once variables have been assigned.
$array = array();
$array[] = 1;
$array[] = 2;
$array[] = 3;
//Unset variables. Internal pointer will still be at 2.
unset($array[0]);
unset($array[1]);
unset($array[2]);
//Serialize
$serializeArray = serialize($array);
//Unserialize
$array = unserialize($serializeArray);
//Add a new element to the array
//If the internal pointer was preserved, the new array key should be 3.
//Instead the internal pointer has been reset, and the new array key is 0.
$array[] = 4;
//Expected Key - 3
//Actual Key - 0
echo "<pre>" , print_r($array, 1) , "</pre>";
?>`

[up](https://www.php.net/manual/vote-note.php?id=113305&page=function.serialize&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113305&page=function.serialize&vote=down "Vote down!")

12


[**_frost at easycast dot ru_**](https://www.php.net/manual/en/function.serialize.php#113305) [¶](https://www.php.net/manual/en/function.serialize.php#113305)

**12 years ago**

`Closures cannot be serialized:
<?php
$func = function () {echo 'hello!';};
$func(); // prints "hello!"
$result = serialize($func);  // Fatal error: Uncaught exception 'Exception' with message 'Serialization of 'Closure' is not allowed'
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.serialize&repo=en&redirect=https://www.php.net/manual/en/function.serialize.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google