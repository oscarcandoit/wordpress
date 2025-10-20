---
url: https://www.php.net/manual/en/function.settype.php
scraped_at: 2025-10-20T02:34:35.419Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# settype

(PHP 4, PHP 5, PHP 7, PHP 8)

settype — Set the type of a variable

### Description [¶](https://www.php.net/manual/en/function.settype.php\#refsect1-function.settype-description)

**settype**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `&$var`, [string](https://www.php.net/manual/en/language.types.string.php) `$type`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Set the type of variable `var` to
`type`.


### Parameters [¶](https://www.php.net/manual/en/function.settype.php\#refsect1-function.settype-parameters)

`var`

The variable being converted.


`type`

Possibles values of `type` are:


- "boolean" or "bool"

- "integer" or "int"

- "float" or "double"

- "string"

- "array"

- "object"

- "null"


### Return Values [¶](https://www.php.net/manual/en/function.settype.php\#refsect1-function.settype-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/function.settype.php\#refsect1-function.settype-examples)

**Example #1 **settype()** example**

`<?php
$foo = "5bar"; // string
$bar = true;   // boolean
settype($foo, "integer"); // $foo is now 5   (integer)
settype($bar, "string");  // $bar is now "1" (string)
var_dump($foo, $bar);
?>`

Run code

### Notes [¶](https://www.php.net/manual/en/function.settype.php\#refsect1-function.settype-notes)

> **Note**:
>
>
> Maximum value for "int" is **`[PHP\_INT\_MAX](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-max)`**.

### See Also [¶](https://www.php.net/manual/en/function.settype.php\#refsect1-function.settype-seealso)

- [gettype()](https://www.php.net/manual/en/function.gettype.php) \- Get the type of a variable
- [type-casting](https://www.php.net/manual/en/language.types.type-juggling.php#language.types.typecasting)
- [type-juggling](https://www.php.net/manual/en/language.types.type-juggling.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/functions/settype.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.settype%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.settype&repo=en&redirect=https://www.php.net/manual/en/function.settype.php)

### User Contributed Notes 9 notes

[up](https://www.php.net/manual/vote-note.php?id=107683&page=function.settype&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107683&page=function.settype&vote=down "Vote down!")

68


[**_Special Notes_**](https://www.php.net/manual/en/function.settype.php#107683) [¶](https://www.php.net/manual/en/function.settype.php#107683)

**13 years ago**

`Note that you can't use this to convert a string 'true' or 'false' to a boolean variable true or false as a string 'false' is a boolean true. The empty string would be false instead...
<?php
$var = "true";
settype($var, 'bool');
var_dump($var); // true
$var = "false";
settype($var, 'bool');
var_dump($var); // true as well!
$var = "";
settype($var, 'bool');
var_dump($var); // false
?>`

[up](https://www.php.net/manual/vote-note.php?id=81595&page=function.settype&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81595&page=function.settype&vote=down "Vote down!")

50


[**_robin at barafranca dot com_**](https://www.php.net/manual/en/function.settype.php#81595) [¶](https://www.php.net/manual/en/function.settype.php#81595)

**17 years ago**

`Just a quick note, as this caught me out very briefly:
settype() returns bool, not the typecasted variable - so:
$blah = settype($blah, "int"); // is wrong, changes $blah to 0 or 1
settype($blah, "int"); // is correct
Hope this helps someone else who makes a mistake.. ;)`

[up](https://www.php.net/manual/vote-note.php?id=35587&page=function.settype&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=35587&page=function.settype&vote=down "Vote down!")

17


[**_sdibb at myway dot com_**](https://www.php.net/manual/en/function.settype.php#35587) [¶](https://www.php.net/manual/en/function.settype.php#35587)

**22 years ago**

`Using settype is not the best way to convert a string into an integer, since it will strip the string wherever the first non-numeric character begins.  The function intval($string) does the same thing.
If you're looking for a security check, or to strip non-numeric characters (such as cleaning up phone numbers or ZIP codes),  try this instead:
<?
     $number=ereg_replace("[^0-9]","",$number);
?>`

[up](https://www.php.net/manual/vote-note.php?id=55016&page=function.settype&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=55016&page=function.settype&vote=down "Vote down!")

10


[**_nospamplease at veganismus dot ch_**](https://www.php.net/manual/en/function.settype.php#55016) [¶](https://www.php.net/manual/en/function.settype.php#55016)

**20 years ago**

`you must note that this function will not set the type permanently! the next time you set the value of that variable php will change its type as well.`

[up](https://www.php.net/manual/vote-note.php?id=126018&page=function.settype&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126018&page=function.settype&vote=down "Vote down!")

5


[**_DarkMaster_**](https://www.php.net/manual/en/function.settype.php#126018) [¶](https://www.php.net/manual/en/function.settype.php#126018)

**4 years ago**

`<?php
/*
This example works 4x faster than settype() function in PHP-CGI 5.4.13 and
8x faster in PHP-CGI 7.1.3(x64) for windows
*/
$v = '12345';
$v = (int)$v;
$v = (string)$v;
?>`

[up](https://www.php.net/manual/vote-note.php?id=124531&page=function.settype&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124531&page=function.settype&vote=down "Vote down!")

1


[**_geoffsmiths at hotmail dot com_**](https://www.php.net/manual/en/function.settype.php#124531) [¶](https://www.php.net/manual/en/function.settype.php#124531)

**5 years ago**

`Please note:
When using settype to convert indexed arrays to objects, the properties of the typed object will be integers:
A brief example:
$a = ['1', '2'];
settype($a, 'object');
var_dump($a);
// output
object(stdClass)#1 (2) {
["0"]=>
string(1) "1"
["1"]=>
string(1) "2"
}`

[up](https://www.php.net/manual/vote-note.php?id=123490&page=function.settype&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123490&page=function.settype&vote=down "Vote down!")

1


[**_Anonymous_**](https://www.php.net/manual/en/function.settype.php#123490) [¶](https://www.php.net/manual/en/function.settype.php#123490)

**6 years ago**

`If you attempt to convert the special $this variable from an instance method (only in classes) :
* PHP will silently return TRUE and leave $this unchanged if the type was 'bool', 'array', 'object' or 'NULL'
* PHP will generate an E_NOTICE if the type was 'int', 'float' or 'double', and $this will not be casted
* PHP will throw a catchable fatal error when the type is 'string' and the class does not define the __toString() method
Unless the new variable type passed as the second argument is invalid, settype() will return TRUE. In all cases the object will remain unchanged.
<?php
    // This was tested with PHP 7.2
    class Foo {
        function test() {
            printf("%-20s %-20s %s\n", 'Type', 'Succeed?', 'Converted');

            // settype() should throw a fatal error, as $this cannot be re-assigned
            printf("%-20s %-20s %s\n", 'bool', settype($this, 'bool'), print_r($this, TRUE));
            printf("%-20s %-20s %s\n", 'int', settype($this, 'int'), print_r($this, TRUE));
            printf("%-20s %-20s %s\n", 'float', settype($this, 'float'), print_r($this));
            printf("%-20s %-20s %s\n", 'array', settype($this, 'array'), print_r($this, TRUE));
            printf("%-20s %-20s %s\n", 'object', settype($this, 'object'), print_r($this, TRUE));
            printf("%-20s %-20s %s\n", 'unknowntype', settype($this, 'unknowntype'), print_r($this, TRUE));
            printf("%-20s %-20s %s\n", 'NULL', settype($this, 'NULL'), print_r($this, TRUE));
            printf("%-20s %-20s %s\n", 'string', settype($this, 'string'), print_r($this, TRUE));
        }
    }
    $a = new Foo();
    $a->test();
?>
Here is the result :
Type                 Succeed?             Converted
bool                 1                    Foo Object
(
)
Notice: Object of class Foo could not be converted to int in C:\php\examples\oop-settype-this.php on line 9
int                  1                    Foo Object
(
)
Notice: Object of class Foo could not be converted to float in C:\php\examples\oop-settype-this.php on line 10
float                1                    Foo Object
(
)
array                1                    Foo Object
(
)
object               1                    Foo Object
(
)
Warning: settype(): Invalid type in C:\php\examples\oop-settype-this.php on line 14
unknowntype                               Foo Object
(
)
NULL                 1                    Foo Object
(
)
Catchable fatal error: Object of class Foo could not be converted to string in C:\php\examples\oop-settype-this.php on line 15
If the class Foo implements __toString() :
<?php
    class Foo {
        // ...
        function __toString() {
            return 'Foo object is awesome!';
        }
        // ...
    }
?>
So the first code snippet will not generate an E_RECOVERABLE_ERROR, but instead print the same string as for the other types, and not look at the one returned by the __toString() method.
Hope this helps !  :)`

[up](https://www.php.net/manual/vote-note.php?id=59444&page=function.settype&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=59444&page=function.settype&vote=down "Vote down!")

0


[**_matt at mattsoft dot net_**](https://www.php.net/manual/en/function.settype.php#59444) [¶](https://www.php.net/manual/en/function.settype.php#59444)

**19 years ago**

`using (int) insted of the settype function works out much better for me. I have always used it. I personally don't see where settype would ever come in handy.`

[up](https://www.php.net/manual/vote-note.php?id=5593&page=function.settype&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=5593&page=function.settype&vote=down "Vote down!")

0


[**_ns at canada dot com_**](https://www.php.net/manual/en/function.settype.php#5593) [¶](https://www.php.net/manual/en/function.settype.php#5593)

**25 years ago**

`This settype() behaviour seems consistent to me. Quoting two sections from the manual:
"When casting from a scalar or a string variable to an array, the variable will become the first element of the array: "
<pre>
2 $var = 'ciao';
3 $arr = (array) $var;
4 echo $arr[0];  // outputs 'ciao'
</pre>
And if (like your code above) you do a settype on an empty variable, you'll end up with a one element array with an empty (not unset!) first element. So appeanding to it will start appending at index 1. As for why reset() doesn't do anything:
"When you assign a value to an array variable using empty brackets, the value will be added onto the end of the array."
It doesn't matter where the array counter is; values are added at the end, not at the counter.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.settype&repo=en&redirect=https://www.php.net/manual/en/function.settype.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google