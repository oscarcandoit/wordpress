---
url: https://www.php.net/manual/en/function.list.php
scraped_at: 2025-10-20T02:56:09.613Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# list

(PHP 4, PHP 5, PHP 7, PHP 8)

list — Assign variables as if they were an array

### Description [¶](https://www.php.net/manual/en/function.list.php\#refsect1-function.list-description)

**list**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$var`, [mixed](https://www.php.net/manual/en/language.types.mixed.php) `...$vars` = ?): [array](https://www.php.net/manual/en/language.types.array.php)

Like [array()](https://www.php.net/manual/en/function.array.php), this is not really a function,
but a language construct. **list()** is used to
assign a list of variables in one operation.
Only arrays and objects that implement [ArrayAccess](https://www.php.net/manual/en/class.arrayaccess.php) can be unpacked.
**list()** expressions can not be completely empty.


> **Note**:
>
>
> Before PHP 7.1.0, **list()** only worked on numerical arrays and assumes
> the numerical indices start at 0.

As of PHP 7.1.0, **list()** can also contain explicit keys, allowing for the
destructuring of arrays with non-integer or non-sequential keys. For more details on
array destructuring, see the [array destructuring section](https://www.php.net/manual/en/language.types.array.php#language.types.array.syntax.destructuring).


> **Note**:
>
>
> Attempting to access an array key which has not been defined is
> the same as accessing any other undefined variable:
> an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**-level error message
> ( **`[E\_NOTICE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-notice)`**-level prior to PHP 8.0.0) will be
> issued, and the result will be **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**.
>
>
> Attempting to unpack a scalar assigns **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** to all variables.
> Attempting to unpack an object that does not implement ArrayAccess is a fatal error.

### Parameters [¶](https://www.php.net/manual/en/function.list.php\#refsect1-function.list-parameters)

`var`

A variable.


`vars`

Further variables.


### Return Values [¶](https://www.php.net/manual/en/function.list.php\#refsect1-function.list-returnvalues)

Returns the assigned array.


### Changelog [¶](https://www.php.net/manual/en/function.list.php\#refsect1-function.list-changelog)

| Version | Description |
| --- | --- |
| 7.3.0 | Support for reference assignments in array destructuring was added. |
| 7.1.0 | It is now possible to specify keys in **list()**. This<br> enables destructuring of arrays with non-integer or non-sequential keys. |

### Examples [¶](https://www.php.net/manual/en/function.list.php\#refsect1-function.list-examples)

**Example #1 **list()** examples**

`<?php
$info = array('coffee', 'brown', 'caffeine');
// Listing all the variables
list($drink, $color, $power) = $info;
echo "$drink is $color and $power makes it special.\n";
// Listing some of them
list($drink, , $power) = $info;
echo "$drink has $power.\n";
// Or let's skip to only the third one
list( , , $power) = $info;
echo "I need $power!\n";
// list() doesn't work with strings
list($bar) = "abcde";
var_dump($bar); // NULL
?>`

Run code

**Example #2 An example use of **list()****

`<?php
$result = $pdo->query("SELECT id, name FROM employees");
while (list($id, $name) = $result->fetch(PDO::FETCH_NUM)) {
    echo "id: $id, name: $name\n";
}
?>`

**Example #3 Using nested **list()****

`<?php
list($a, list($b, $c)) = array(1, array(2, 3));
var_dump($a, $b, $c);
?>`

Run code

The above example will output:

```
int(1)
int(2)
int(3)
```

The order in which the indices of the array to be consumed by
**list()** are defined is irrelevant.


**Example #4 **list()** and order of index definitions**

`<?php
$foo = array(2 => 'a', 'foo' => 'b', 0 => 'c');
$foo[1] = 'd';
list($x, $y, $z) = $foo;
var_dump($foo, $x, $y, $z);`

Run code

Gives the following output (note the order of the elements compared in
which order they were written in the **list()** syntax):


```
array(4) {
  [2]=>
  string(1) "a"
  ["foo"]=>
  string(1) "b"
  [0]=>
  string(1) "c"
  [1]=>
  string(1) "d"
}
string(1) "c"
string(1) "d"
string(1) "a"
```

**Example #5 **list()** with keys**

As of PHP 7.1.0 **list()** can now also contain
explicit keys, which can be given as arbitrary expressions.
Mixing of integer and string keys is allowed; however, elements
with and without keys cannot be mixed.


`<?php
$data = [\
    ["id" => 1, "name" => 'Tom'],\
    ["id" => 2, "name" => 'Fred'],\
];
foreach ($data as ["id" => $id, "name" => $name]) {
    echo "id: $id, name: $name\n";
}
echo PHP_EOL;
list(1 => $second, 3 => $fourth) = [1, 2, 3, 4];
echo "$second, $fourth\n";`

Run code

The above example will output:

```
id: 1, name: Tom
id: 2, name: Fred

2, 4
```

### See Also [¶](https://www.php.net/manual/en/function.list.php\#refsect1-function.list-seealso)

- [each()](https://www.php.net/manual/en/function.each.php) \- Return the current key and value pair from an array and advance the array cursor
- [array()](https://www.php.net/manual/en/function.array.php) \- Create an array
- [extract()](https://www.php.net/manual/en/function.extract.php) \- Import variables into the current symbol table from an array

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/list.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.list%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.list&repo=en&redirect=https://www.php.net/manual/en/function.list.php)

### User Contributed Notes 25 notes

[up](https://www.php.net/manual/vote-note.php?id=120463&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120463&page=function.list&vote=down "Vote down!")

152


[**_carlosv775 at gmail dot com_**](https://www.php.net/manual/en/function.list.php#120463) [¶](https://www.php.net/manual/en/function.list.php#120463)

**8 years ago**

`In PHP 7.1 we can do the following:
<?php
    [$a, $b, $c] = ['a', 'b', 'c'];
?>
Before, we had to do:
<?php
    list($a, $b, $c) = ['a', 'b',  'c'];
?>`

[up](https://www.php.net/manual/vote-note.php?id=121094&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121094&page=function.list&vote=down "Vote down!")

142


[**_Rhamnia Mohamed_**](https://www.php.net/manual/en/function.list.php#121094) [¶](https://www.php.net/manual/en/function.list.php#121094)

**8 years ago**

`Since PHP 7.1, keys can be specified
exemple :
<?php
$array = ['locality' => 'Tunis', 'postal_code' => '1110'];
list('postal_code' => $zipCode, 'locality' => $locality) = $array;
print $zipCode; // will output 1110
print $locality; // will output Tunis
?>`

[up](https://www.php.net/manual/vote-note.php?id=129920&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129920&page=function.list&vote=down "Vote down!")

4


[**_xmgr2 at protonmail dot com_**](https://www.php.net/manual/en/function.list.php#129920) [¶](https://www.php.net/manual/en/function.list.php#129920)

**10 months ago**

`... and it also supports pushing items onto arrays.
I couldn't find any official documentation on this behavior, but it appears that you can "push" elements onto arrays directly using array destructuring assignments.
<?php
$users = [\
    [1, 'Alice', 'alice@example.com', 'secret123'],\
    [2, 'Bob', 'bob@example.com', 'pass456'],\
    [3, 'Charlie', 'charlie@example.com', 'hunter678'],\
];
$ids       = [];
$names     = [];
$emails    = [];
$passwords = [];
foreach ($users as $user) {
    [$ids[], $names[], $emails[], $passwords[]] = $user;
}
?>
For well-documented alternatives, consider using array_column(), which does quite the same:
<?php
$ids       = array_column($users, 0);
$names     = array_column($users, 1);
$emails    = array_column($users, 2);
$passwords = array_column($users, 3);
?>`

[up](https://www.php.net/manual/vote-note.php?id=115975&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115975&page=function.list&vote=down "Vote down!")

99


[**_grzeniufication_**](https://www.php.net/manual/en/function.list.php#115975) [¶](https://www.php.net/manual/en/function.list.php#115975)

**10 years ago**

`The example showing that:
$info = array('kawa', 'brązowa', 'kofeina');
list($a[0], $a[1], $a[2]) = $info;
var_dump($a);
outputs:
array(3) {
[2]=>
string(8) "kofeina"
[1]=>
string(5) "brązowa"
[0]=>
string(6) "kawa"
}
One thing to note here is that if you define the array earlier, e.g.:
$a = [0, 0, 0];
the indexes will be kept in the correct order:
array(3) {
[0]=>
string(4) "kawa"
[1]=>
string(8) "brązowa"
[2]=>
string(7) "kofeina"
}
Thought that it was worth mentioning.`

[up](https://www.php.net/manual/vote-note.php?id=113189&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113189&page=function.list&vote=down "Vote down!")

77


[**_megan at voices dot com_**](https://www.php.net/manual/en/function.list.php#113189) [¶](https://www.php.net/manual/en/function.list.php#113189)

**12 years ago**

`As noted, list() will give an error if the input array is too short. This can be avoided by array_merge()'ing in some default values. For example:
<?php
$parameter = 'name';
list( $a, $b ) = array_merge( explode( '=', $parameter ), array( true ) );
?>
However, you will have to array_merge with an array long enough to ensure there are enough elements (if $parameter is empty, the code above would still error).
An alternate approach would be to use array_pad on the array to ensure its length (if all the defaults you need to add are the same).
<?php
    $parameter = 'bob-12345';
    list( $name, $id, $fav_color, $age ) = array_pad( explode( '-', $parameter ), 4, '' );
    var_dump($name, $id, $fav_color, $age);
/* outputs
string(3) "bob"
string(5) "12345"
string(0) ""
string(0) ""
*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=121139&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121139&page=function.list&vote=down "Vote down!")

56


[**_grzeniufication_**](https://www.php.net/manual/en/function.list.php#121139) [¶](https://www.php.net/manual/en/function.list.php#121139)

**8 years ago**

`<?php
/**
* It seems you can skip listed values.
* Here's an example to show what I mean.
*
* FYI works just as well with PHP 7.1 shorthand list syntax.
* Tested against PHP 5.6.30, 7.1.5
*/
$a = [ 1, 2, 3, 4 ];
// this is quite normal use case for list
echo "Unpack all values\n";
list($v1, $v2, $v3, $v4) = $a;
echo "$v1, $v2, $v3, $v4\n";
unset($v1, $v2, $v3, $v4);
// this is what I mean:
echo "Skip middle\n";
list($v1, , , $v4) = $a;
echo "$v1, $v2, $v3, $v4\n";
unset($v1, $v2, $v3, $v4);
echo "Skip beginning\n";
list( , , $v3, $v4) = $a;
echo "$v1, $v2, $v3, $v4\n";
unset($v1, $v2, $v3, $v4);
echo "Skip end\n";
list($v1, $v2, , ) = $a;
echo "$v1, $v2, $v3, $v4\n";
unset($v1, $v2, $v3, $v4);
echo "Leave middle\n";
list( , $v2, $v3, ) = $a;
echo "$v1, $v2, $v3, $v4\n";
unset($v1, $v2, $v3, $v4);`

[up](https://www.php.net/manual/vote-note.php?id=110563&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110563&page=function.list&vote=down "Vote down!")

77


[**_chris at chlab dot ch_**](https://www.php.net/manual/en/function.list.php#110563) [¶](https://www.php.net/manual/en/function.list.php#110563)

**12 years ago**

`The example states the following:
<?php
// list() doesn't work with strings
list($bar) = "abcde";
var_dump($bar);
// output: NULL
?>
If the string is in a variable however, it seems using list() will treat the string as an array:
<?php
$string = "abcde";
list($foo) = $string;
var_dump($foo);
// output: string(1) "a"
?>`

[up](https://www.php.net/manual/vote-note.php?id=128059&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128059&page=function.list&vote=down "Vote down!")

8


[**_nek dot dev at gmail dot com_**](https://www.php.net/manual/en/function.list.php#128059) [¶](https://www.php.net/manual/en/function.list.php#128059)

**2 years ago**

``It can be convenient to specify a default value in case an element is missing in the list. You can use operator + for this:
<?php
$someArray = ['color' => 'orange'];
['color' => $color, 'size' => $size] = $someArray + ['color' => null, 'size' => null];
?>
This will avoid the warning `Undefined array key "size"` you would encounter otherwise.``

[up](https://www.php.net/manual/vote-note.php?id=118786&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118786&page=function.list&vote=down "Vote down!")

38


[**_pemapmodder1970 at gmail dot com_**](https://www.php.net/manual/en/function.list.php#118786) [¶](https://www.php.net/manual/en/function.list.php#118786)

**9 years ago**

`list() can be used with foreach
<?php
$array = [[1, 2], [3, 4], [5, 6]];
foreach($array as list($odd, $even)){
    echo "$odd is odd; $even is even", PHP_EOL;
}
?>
The output:
===
1 is odd; 2 is even
3 is odd; 4 is even
5 is odd; 6 is even`

[up](https://www.php.net/manual/vote-note.php?id=113845&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113845&page=function.list&vote=down "Vote down!")

29


[**_john at jbwalker dot com_**](https://www.php.net/manual/en/function.list.php#113845) [¶](https://www.php.net/manual/en/function.list.php#113845)

**11 years ago**

`The list construct seems to look for a sequential list of indexes rather taking elements in sequence. What that obscure statement means is that if you unset an element, list will not simply jump to the next element and assign that to the variable but will treat the missing element as a null or empty variable:
    $test = array("a","b","c","d");
    unset($test[1]);
    list($a,$b,$c)=$test;
    print "\$a='$a' \$b='$b' \$c='$c'<BR>";
results in:
$a='a' $b='' $c='c'
not:
$a='a' $b='c' $c='d'`

[up](https://www.php.net/manual/vote-note.php?id=126208&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126208&page=function.list&vote=down "Vote down!")

9


[**_diyor024 at gmail dot com_**](https://www.php.net/manual/en/function.list.php#126208) [¶](https://www.php.net/manual/en/function.list.php#126208)

**4 years ago**

`Don't miss simple array pattern matching since php 7
<?php
[$a] = ['hello!'];
var_dump($a); // 'hello!'
$arr = [4 => 50];
[4 => $fifty] = $arr;
var_dump($fifty); // 50
$multidimensionalArray = [['id' => 15, 'email' => 'diyor024@gmail.com']];
[['id'  => $id, 'email' => $email]] = $multidimensionalArray;
var_dump($id, $email); // 15 diyor024@gmail.com
?>`

[up](https://www.php.net/manual/vote-note.php?id=124642&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124642&page=function.list&vote=down "Vote down!")

7


[**_vike2000 at gmail dot com_**](https://www.php.net/manual/en/function.list.php#124642) [¶](https://www.php.net/manual/en/function.list.php#124642)

**5 years ago**

`Setting it like <?php list($var1,$varN) = null ?> does _not_ raise an E_NOTICE (or other error) and afaics effectively equals an [https://php.net/function.unset](https://php.net/function.unset) of $var1,$varN.
I note this as contrasting with the fact that PHP triggers an E_NOTICE about "Undefined offset" "if there aren't enough array elements to fill the list()", as attow documented for [https://php.net/control-structures.foreach#control-structures.foreach.list](https://php.net/control-structures.foreach#control-structures.foreach.list) and here only noted in [https://php.net/function.list#122951](https://php.net/function.list#122951) by Mardaneus.
For completeness, a bash(1) (v5.0 or 4.3 on macos10.13) cli test producing the same result for all my PHP-versions (installed via macports.org) follows. It's also tested with php7.3 using bash5.0 on Debian10:
bash --noprofile --norc -c 'for php in php{{53..56},{70..73}};do for literal in "array()" null;do echo -n $php …=$literal:&&$php -n -d error_reporting=E_ALL -r "var_dump(list(\$var)=$literal);";done;done'
# Above produces the same result pairs per version from:
php53 …=array():
Notice: Undefined offset: 0 in Command line code on line 1
array(0) {
}
# ... to:
php73 …=null:NULL`

[up](https://www.php.net/manual/vote-note.php?id=125644&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125644&page=function.list&vote=down "Vote down!")

8


[**_mark at manngo dot net_**](https://www.php.net/manual/en/function.list.php#125644) [¶](https://www.php.net/manual/en/function.list.php#125644)

**4 years ago**

`For PHP 7.1 on, the documentation states that integer and string keys can be mixed, but that elements with and without keys cannot. Here is an example, using data from getimagesize() with mixed keys:
<?php
    $data=[\
        0=> 160,\
        1 => 120,\
        2 => 2,\
        3 => 'width="160" height="120"',\
        'mime' => 'image/jpeg'\
    ];
    list(0=>$width,1=>$height,2=>$type,3=>$dimensions,'mime'=>$mime)=$data;
?>
Here, the numeric keys also need to be specified, as if the whole array is treated as an associative array.
As noted elsewhere, the list() operator can be written in array format:
<?php
    [0=>$width,1=>$height,2=>$type,3=>$dimensions,'mime'=>$mime]=$data;
?>`

[up](https://www.php.net/manual/vote-note.php?id=110921&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110921&page=function.list&vote=down "Vote down!")

47


[**_svennd_**](https://www.php.net/manual/en/function.list.php#110921) [¶](https://www.php.net/manual/en/function.list.php#110921)

**12 years ago**

`The list() definition won't throw an error if your array is longer then defined list.
<?php
list($a, $b, $c) = array("a", "b", "c", "d");
var_dump($a); // a
var_dump($b); // b
var_dump($c); // c
?>`

[up](https://www.php.net/manual/vote-note.php?id=125864&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125864&page=function.list&vote=down "Vote down!")

6


[**_samraskul at gmail dot com_**](https://www.php.net/manual/en/function.list.php#125864) [¶](https://www.php.net/manual/en/function.list.php#125864)

**4 years ago**

`list($a, $b, $c) = ["blue", "money", 32];
shortcut:
[$a, $b, $c] = ["blue", "money", 32];`

[up](https://www.php.net/manual/vote-note.php?id=122615&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122615&page=function.list&vote=down "Vote down!")

11


[**_petru at fuxspam dot xtremeweb dot ro_**](https://www.php.net/manual/en/function.list.php#122615) [¶](https://www.php.net/manual/en/function.list.php#122615)

**7 years ago**

`This is something I haven't seen in documentation.
Since PHP 7.1, you can use short-hand list unpacking using square brackets, just like short-hand array declaration:
<?php
$foo = ['a', 'b', 'c'];
// short-hand array definition
[$a, $b, $c] = $foo;
echo $a; // displays "a"
// it's same like:
list($x, $y, $z) = $foo;
echo $x; // displays "a"
?>`

[up](https://www.php.net/manual/vote-note.php?id=124004&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124004&page=function.list&vote=down "Vote down!")

8


[**_Paul Marti_**](https://www.php.net/manual/en/function.list.php#124004) [¶](https://www.php.net/manual/en/function.list.php#124004)

**6 years ago**

`Since 7.1.0, you can use an array directly without list():
<?php
[$test, $test2] = explode(",", "hello, world");
echo $test . $test2; // hello, world
?>`

[up](https://www.php.net/manual/vote-note.php?id=121586&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121586&page=function.list&vote=down "Vote down!")

6


[**_blazej_**](https://www.php.net/manual/en/function.list.php#121586) [¶](https://www.php.net/manual/en/function.list.php#121586)

**8 years ago**

`From PHP Version 7.1 you can specify keys in list(), or its new shorthand [] syntax. This enables destructuring of arrays with non-integer or non-sequential keys.
<?php
$data = [\
    ["id" => 1, "name" => 'Tom'],\
    ["id" => 2, "name" => 'Fred'],\
];
// list() style
list("id" => $id1, "name" => $name1) = $data[0];
// [] style
["id" => $id1, "name" => $name1] = $data[0];
// list() style
foreach ($data as list("id" => $id, "name" => $name)) {
    // logic here with $id and $name
}
// [] style
foreach ($data as ["id" => $id, "name" => $name]) {
    // logic here with $id and $name
}`

[up](https://www.php.net/manual/vote-note.php?id=120076&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120076&page=function.list&vote=down "Vote down!")

4


[**_anthony dot ossent at live dot fr_**](https://www.php.net/manual/en/function.list.php#120076) [¶](https://www.php.net/manual/en/function.list.php#120076)

**8 years ago**

`a simple example of use to swap two variables :
$a = 'hello';
$b = 'world';
list($a, $b) = [$b, $a];
echo $a . ' ' . $b; //display "world hello"
another example :
function getPosition($x, $y, $z)
{
// ... some operations like $x++...
return [$x, $y, $z];
}
list($x, $y, $z) = getPosition($x ,$y, $z);`

[up](https://www.php.net/manual/vote-note.php?id=122560&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122560&page=function.list&vote=down "Vote down!")

3


[**_contato at tobias dot ws_**](https://www.php.net/manual/en/function.list.php#122560) [¶](https://www.php.net/manual/en/function.list.php#122560)

**7 years ago**

`Since PHP 7.1 the [] may now be used as an alternative to the existing list() syntax:
<?php
[$number, $message] = explode('|', '123|Hello World!');
?>`

[up](https://www.php.net/manual/vote-note.php?id=117677&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117677&page=function.list&vote=down "Vote down!")

3


[**_Colin Guthrie_**](https://www.php.net/manual/en/function.list.php#117677) [¶](https://www.php.net/manual/en/function.list.php#117677)

**10 years ago**

`If you want use the undefined behaviour as you might expect it e.g. if you want:
$b = ['a','b']; list($a, $b) = $b;
to result in $a=='a' and $b=='b', then you can just cast $b to an array (even although it already is) to create a copy. e.g.
$b = ['a','b']; list($a, $b) = (array)$b;
and get the expected results.`

[up](https://www.php.net/manual/vote-note.php?id=130521&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130521&page=function.list&vote=down "Vote down!")

0


[**_biziclop at example dot net_**](https://www.php.net/manual/en/function.list.php#130521) [¶](https://www.php.net/manual/en/function.list.php#130521)

**1 day ago**

`Since PHP 7.3, it is possible to assign to variables by reference.
[https://wiki.php.net/rfc/list\_reference\_assignment](https://wiki.php.net/rfc/list_reference_assignment)
<?php
$a = array();
$a[0] =  111;
$a[1] =& $a[0];
$a[0] =  222;
var_dump( $a );  // array(2){  [0] => &int(222)  [1] => &int(222)  }
list( & $b, & $c ) = $a;
$b = 333;
var_dump( $c );  // int(333)
?>`

[up](https://www.php.net/manual/vote-note.php?id=122951&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122951&page=function.list&vote=down "Vote down!")

0


[**_Mardaneus_**](https://www.php.net/manual/en/function.list.php#122951) [¶](https://www.php.net/manual/en/function.list.php#122951)

**7 years ago**

`Unless you specify keys when using list() it expects the array being fed into it to start at 0.
So having the following code will result in a notice level warning "Undefined offset: 0" and variables not filling as expected
<?php
list($c1, $c2, $c3) = array [1 =>'a', 2 => 'b', 3 => 'c'];
var_dump($c1); // NULL
var_dump($c2); // string(1) "a"
var_dump($c3); // string(1) "b"
?>`

[up](https://www.php.net/manual/vote-note.php?id=118463&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118463&page=function.list&vote=down "Vote down!")

 -1


[**_Dean_**](https://www.php.net/manual/en/function.list.php#118463) [¶](https://www.php.net/manual/en/function.list.php#118463)

**9 years ago**

`UNDOCUMENTED BEHAVIOR:
    list($a,$b,$c) = null;
in fact works like:
    $a = null; $b = null; $c = null;
...So correspondingly:
    list($rows[]) = null;
Will increment count($rows), just as if you had executed $rows[] = null;
Watch out for this (for example) when retrieving entire tables from a database, e.g.
    while (list($rows[]) = $mysqlresult->fetch_row());
This will leave an extra 'null' entry as the last element of $rows.`

[up](https://www.php.net/manual/vote-note.php?id=124730&page=function.list&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124730&page=function.list&vote=down "Vote down!")

 -4


[**_fredsaavedra at hotmail dot com_**](https://www.php.net/manual/en/function.list.php#124730) [¶](https://www.php.net/manual/en/function.list.php#124730)

**5 years ago**

`Easy way to get actual date and time values in variables.
list($day,$month,$year,$hour,$minute,$second) = explode('-',date('d-m-Y-G-i-s'));
echo "$day-$month-$year $hour".":".$minute.":".$second;`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.list&repo=en&redirect=https://www.php.net/manual/en/function.list.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google