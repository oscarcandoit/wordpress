---
url: https://www.php.net/manual/en/language.operators.array.php
scraped_at: 2025-10-20T02:41:10.170Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Array Operators [¶](https://www.php.net/manual/en/language.operators.array.php\#language.operators.array)

| Example | Name | Result |
| --- | --- | --- |
| $a + $b | Union | Union of $a and $b. |
| $a == $b | Equality | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a and $b have the same key/value pairs. |
| $a === $b | Identity | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a and $b have the same key/value pairs in the same<br> order and of the same types. |
| $a != $b | Inequality | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is not equal to $b. |
| $a <> $b | Inequality | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is not equal to $b. |
| $a !== $b | Non-identity | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is not identical to $b. |

**Array Operators**

The `+` operator returns the right-hand array appended
to the left-hand array; for keys that exist in both arrays, the elements
from the left-hand array will be used, and the matching elements from the
right-hand array will be ignored.


**Example #1 Array Append Operator**

`<?php
$a = array("a" => "apple", "b" => "banana");
$b = array("a" => "pear", "b" => "strawberry", "c" => "cherry");
$c = $a + $b; // Union of $a and $b
echo "Union of \$a and \$b: \n";
var_dump($c);
$c = $b + $a; // Union of $b and $a
echo "Union of \$b and \$a: \n";
var_dump($c);
$a += $b; // Union of $a += $b is $a and $b
echo "Union of \$a += \$b: \n";
var_dump($a);
?>`

Run code

The above example will output:

```
Union of $a and $b:
array(3) {
  ["a"]=>
  string(5) "apple"
  ["b"]=>
  string(6) "banana"
  ["c"]=>
  string(6) "cherry"
}
Union of $b and $a:
array(3) {
  ["a"]=>
  string(4) "pear"
  ["b"]=>
  string(10) "strawberry"
  ["c"]=>
  string(6) "cherry"
}
Union of $a += $b:
array(3) {
  ["a"]=>
  string(5) "apple"
  ["b"]=>
  string(6) "banana"
  ["c"]=>
  string(6) "cherry"
}

```

Elements of arrays are equal for the comparison if they have the
same key and value.


**Example #2 Comparing arrays**

`<?php
$a = array("apple", "banana");
$b = array(1 => "banana", "0" => "apple");
var_dump($a == $b); // bool(true)
var_dump($a === $b); // bool(false)
?>`

Run code

### See Also

- [Array type](https://www.php.net/manual/en/language.types.array.php)
- [Array functions](https://www.php.net/manual/en/ref.array.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/operators/array.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.operators.array%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.array&repo=en&redirect=https://www.php.net/manual/en/language.operators.array.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=86379&page=language.operators.array&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86379&page=language.operators.array&vote=down "Vote down!")

241


[**_cb at netalyst dot com_**](https://www.php.net/manual/en/language.operators.array.php#86379) [¶](https://www.php.net/manual/en/language.operators.array.php#86379)

**17 years ago**

`The union operator did not behave as I thought it would on first glance. It implements a union (of sorts) based on the keys of the array, not on the values.
For instance:
<?php
$a = array('one','two');
$b=array('three','four','five');
//not a union of arrays' values
echo '$a + $b : ';
print_r ($a + $b);
//a union of arrays' values
echo "array_unique(array_merge($a,$b)):";
// cribbed from [http://oreilly.com/catalog/progphp/chapter/ch05.html](http://oreilly.com/catalog/progphp/chapter/ch05.html)
print_r (array_unique(array_merge($a,$b)));
?>
//output
$a + $b : Array
(
    [0] => one
    [1] => two
    [2] => five
)
array_unique(array_merge(Array,Array)):Array
(
    [0] => one
    [1] => two
    [2] => three
    [3] => four
    [4] => five
)`

[up](https://www.php.net/manual/vote-note.php?id=74635&page=language.operators.array&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74635&page=language.operators.array&vote=down "Vote down!")

45


[**_Q1712 at online dot ms_**](https://www.php.net/manual/en/language.operators.array.php#74635) [¶](https://www.php.net/manual/en/language.operators.array.php#74635)

**18 years ago**

`The example may get u into thinking that the identical operator returns true because the key of apple is a string but that is not the case, cause if a string array key is the standart representation of a integer it's gets a numeral key automaticly.
The identical operator just requires that the keys are in the same order in both arrays:
<?php
$a = array (0 => "apple", 1 => "banana");
$b = array (1 => "banana", 0 => "apple");
var_dump($a === $b); // prints bool(false) as well
$b = array ("0" => "apple", "1" => "banana");
var_dump($a === $b); // prints bool(true)
?>`

[up](https://www.php.net/manual/vote-note.php?id=41811&page=language.operators.array&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=41811&page=language.operators.array&vote=down "Vote down!")

27


[**_dfranklin at fen dot com_**](https://www.php.net/manual/en/language.operators.array.php#41811) [¶](https://www.php.net/manual/en/language.operators.array.php#41811)

**21 years ago**

`Note that + will not renumber numeric array keys.  If you have two numeric arrays, and their indices overlap, + will use the first array's values for each numeric key, adding the 2nd array's values only where the first doesn't already have a value for that index.  Example:
$a = array('red', 'orange');
$b = array('yellow', 'green', 'blue');
$both = $a + $b;
var_dump($both);
Produces the output:
array(3) { [0]=>  string(3) "red" [1]=>  string(6) "orange" [2]=>  string(4) "blue" }
To get a 5-element array, use array_merge.
    Dan`

[up](https://www.php.net/manual/vote-note.php?id=121665&page=language.operators.array&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121665&page=language.operators.array&vote=down "Vote down!")

11


[**_xtpeqii at Hotmail dot com_**](https://www.php.net/manual/en/language.operators.array.php#121665) [¶](https://www.php.net/manual/en/language.operators.array.php#121665)

**8 years ago**

`$a=[ 3, 2, 1];
$b=[ 6, 5, 4];
var_dump( $a + $b );
output:
array(3) {
[0]=>
int(3)
[1]=>
int(2)
[2]=>
int(1)
}
The reason for the above output is that EVERY array in PHP is an associative one.
Since the 3 elements in $b have the same keys( or numeric indices ) as those in $a, those elements in $b are ignored by the union operator.`

[up](https://www.php.net/manual/vote-note.php?id=27536&page=language.operators.array&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=27536&page=language.operators.array&vote=down "Vote down!")

19


[**_amirlaher AT yahoo DOT co SPOT uk_**](https://www.php.net/manual/en/language.operators.array.php#27536) [¶](https://www.php.net/manual/en/language.operators.array.php#27536)

**22 years ago**

`[]= could be considered an Array Operator (in the same way that .= is a String Operator).
[]= pushes an element onto the end of an array, similar to array_push:
<?
$array= array(0=>"Amir",1=>"needs");
$array[]= "job";
print_r($array);
?>
Prints: Array ( [0] => Amir [1] => needs [2] => job )`

[up](https://www.php.net/manual/vote-note.php?id=107784&page=language.operators.array&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107784&page=language.operators.array&vote=down "Vote down!")

14


[**_Dan Patrick_**](https://www.php.net/manual/en/language.operators.array.php#107784) [¶](https://www.php.net/manual/en/language.operators.array.php#107784)

**13 years ago**

`It should be mentioned that the array union operator functions almost identically to array_replace with the exception that precedence of arguments is reversed.`

[up](https://www.php.net/manual/vote-note.php?id=127761&page=language.operators.array&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127761&page=language.operators.array&vote=down "Vote down!")

0


[**_Anonymous_**](https://www.php.net/manual/en/language.operators.array.php#127761) [¶](https://www.php.net/manual/en/language.operators.array.php#127761)

**2 years ago**

`Merge two arrays and retain only unique values.
Append values from second array.
Do not care about keys.
<?php
$array1 = [\
    0 => 'apple',\
    1 => 'orange',\
    2 => 'pear',\
];
$array2 = [\
    0 => 'melon',\
    1 => 'orange',\
    2 => 'banana',\
];
$result = array_keys(
    array_flip($array1) + array_flip($array2)
);
?>
Result:
[\
[0] => "apple",\
[1] => "orange",\
[2] => "pear",\
[3] => "melon",\
[4] => "banana",\
}`\
\
[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.array&repo=en&redirect=https://www.php.net/manual/en/language.operators.array.php)\
\
![To Top](https://www.php.net/images/to-top@2x.png)\
\
`↑` and `↓` to navigate •\
`Enter` to select •\
`Esc` to close\
\
\
Press `Enter` without\
selection to search using Google