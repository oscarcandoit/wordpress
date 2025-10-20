---
url: https://www.php.net/manual/en/function.asort.php
scraped_at: 2025-10-20T02:48:04.809Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# asort

(PHP 4, PHP 5, PHP 7, PHP 8)

asort — Sort an array in ascending order and maintain index association

### Description [¶](https://www.php.net/manual/en/function.asort.php\#refsect1-function.asort-description)

**asort**([array](https://www.php.net/manual/en/language.types.array.php) `&$array`, [int](https://www.php.net/manual/en/language.types.integer.php) `$flags` = **`[SORT\_REGULAR](https://www.php.net/manual/en/array.constants.php#constant.sort-regular)`**): [true](https://www.php.net/manual/en/language.types.singleton.php)

Sorts `array` in place in ascending order,
such that its keys maintain their correlation with the values they
are associated with.


This is used mainly when sorting associative arrays where the actual
element order is significant.


> **Note**:
>
>
> If two members compare as equal, they retain their original order.
> Prior to PHP 8.0.0, their relative order in the sorted array was undefined.

> **Note**:
>
>
> Resets array's internal pointer to the first element.

### Parameters [¶](https://www.php.net/manual/en/function.asort.php\#refsect1-function.asort-parameters)

`array`

The input array.


`flags`

The optional second parameter `flags`
may be used to modify the sorting behavior using these values:


Sorting type flags:


- **`[SORT\_REGULAR](https://www.php.net/manual/en/array.constants.php#constant.sort-regular)`** \- compare items normally;
the details are described in the [comparison operators](https://www.php.net/manual/en/language.operators.comparison.php) section
- **`[SORT\_NUMERIC](https://www.php.net/manual/en/array.constants.php#constant.sort-numeric)`** \- compare items numerically
- **`[SORT\_STRING](https://www.php.net/manual/en/array.constants.php#constant.sort-string)`** \- compare items as strings
- **`[SORT\_LOCALE\_STRING](https://www.php.net/manual/en/array.constants.php#constant.sort-locale-string)`** \- compare items as
strings, based on the current locale. It uses the locale,
which can be changed using [setlocale()](https://www.php.net/manual/en/function.setlocale.php)
- **`[SORT\_NATURAL](https://www.php.net/manual/en/array.constants.php#constant.sort-natural)`** \- compare items as strings
using "natural ordering" like [natsort()](https://www.php.net/manual/en/function.natsort.php)
- **`[SORT\_FLAG\_CASE](https://www.php.net/manual/en/array.constants.php#constant.sort-flag-case)`** \- can be combined
(bitwise OR) with
**`[SORT\_STRING](https://www.php.net/manual/en/array.constants.php#constant.sort-string)`** or
**`[SORT\_NATURAL](https://www.php.net/manual/en/array.constants.php#constant.sort-natural)`** to sort strings case-insensitively


### Return Values [¶](https://www.php.net/manual/en/function.asort.php\#refsect1-function.asort-returnvalues)

Always returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.


### Changelog [¶](https://www.php.net/manual/en/function.asort.php\#refsect1-function.asort-changelog)

| Version | Description |
| --- | --- |
| 8.2.0 | The return type is **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** now; previously, it was [bool](https://www.php.net/manual/en/language.types.boolean.php). |

### Examples [¶](https://www.php.net/manual/en/function.asort.php\#refsect1-function.asort-examples)

**Example #1 **asort()** example**

`<?php
$fruits = array("d" => "lemon", "a" => "orange", "b" => "banana", "c" => "apple");
asort($fruits);
foreach ($fruits as $key => $val) {
    echo "$key = $val\n";
}
?>`

Run code

The above example will output:

```
c = apple
b = banana
d = lemon
a = orange
```

The fruits have been sorted in alphabetical order, and the index
associated with each element has been maintained.


### See Also [¶](https://www.php.net/manual/en/function.asort.php\#refsect1-function.asort-seealso)

- [sort()](https://www.php.net/manual/en/function.sort.php) \- Sort an array in ascending order
- [arsort()](https://www.php.net/manual/en/function.arsort.php) \- Sort an array in descending order and maintain index association
- The [comparison of array sorting functions](https://www.php.net/manual/en/array.sorting.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/asort.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.asort%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.asort&repo=en&redirect=https://www.php.net/manual/en/function.asort.php)

### User Contributed Notes 31 notes

[up](https://www.php.net/manual/vote-note.php?id=105797&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105797&page=function.asort&vote=down "Vote down!")

107


[**_nick (\[AT\]) nickyost (\[DOT\]) com_**](https://www.php.net/manual/en/function.asort.php#105797) [¶](https://www.php.net/manual/en/function.asort.php#105797)

**14 years ago**

`This function can be used to sort multidimensional arrays with almost no work whatsoever by using the individual values within the custom sort function.
This function passes the entire child element even if it is not a string. If it is an array, as would be the case in multidimensional arrays, it will pass the whole child array as one parameter.
Therefore, do something elegant like this:
<?php
     // Sort the multidimensional array
     usort($results, "custom_sort");
     // Define the custom sort function
     function custom_sort($a,$b) {
          return $a['some_sub_var']>$b['some_sub_var'];
     }
?>
This does in 4 lines what other functions took 40 to 50 lines to do. This does not require you to create temporary arrays or anything. This is, for me, a highly preferred solution.
Hope it helps!`

[up](https://www.php.net/manual/vote-note.php?id=117778&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117778&page=function.asort&vote=down "Vote down!")

24


[**_aditycse at gmail dot com_**](https://www.php.net/manual/en/function.asort.php#117778) [¶](https://www.php.net/manual/en/function.asort.php#117778)

**10 years ago**

`/*
* Name : Aditya Mehrotra
* Email: aditycse@gmail.com
*/
//Example for sorting by values for an alphanumeric array also having case-sensitive data
$exampleArray1 = $exampleArray2 = array(
    0 => 'example1',
    1 => 'Example10',
    2 => 'example12',
    3 => 'Example2',
    4 => 'example3',
    5 => 'EXAMPLE10',
    6 => 'example10'
);
//default sorting
asort($exampleArray1);
// alphanumeric with case-sensitive data sorting by values
asort($exampleArray2, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
//output of defaut sorting
print_r($exampleArray1);
/*
* output of default sorting
Array
(
[5] => EXAMPLE10
[1] => Example10
[3] => Example2
[0] => example1
[6] => example10
[2] => example12
[4] => example3
)
*/
print_r($exampleArray2);
/*
* output of alphanumeric with case-sensitive data sorting by values
Array
(
    [0] => example1
    [3] => Example2
    [4] => example3
    [5] => EXAMPLE10
    [1] => Example10
    [6] => example10
    [2] => example12
)
*/`

[up](https://www.php.net/manual/vote-note.php?id=71318&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=71318&page=function.asort&vote=down "Vote down!")

21


[**_richard at happymango dot me dot uk_**](https://www.php.net/manual/en/function.asort.php#71318) [¶](https://www.php.net/manual/en/function.asort.php#71318)

**18 years ago**

`This is a function to sort an indexed 2D array by a specified sub array key, either ascending or descending.
It is usefull for sorting query results from a database by a particular field after the query has been returned
This function can be quite greedy. It recreates the array as a hash to use ksort() then back again
By default it will sort ascending but if you specify $reverse as true it will return the records sorted descending
<?php
function record_sort($records, $field, $reverse=false)
{
    $hash = array();

    foreach($records as $record)
    {
        $hash[$record[$field]] = $record;
    }

    ($reverse)? krsort($hash) : ksort($hash);

    $records = array();

    foreach($hash as $record)
    {
        $records []= $record;
    }

    return $records;
}
// Example below
$airports = array
(
    array( "code" => "LHR", "name" => "Heathrow" ),
    array( "code" => "LGW", "name" => "Gatwick" ),
);
printf("Before: <pre>%s</pre>", print_r($airports, true));
$airports = record_sort($airports, "name");
printf("After: <pre>%s</pre>", print_r($airports, true));
?>
Example Outputs:
Before: Array
(
    [0] => Array ( [code] => LHR, [name] => Heathrow )
    [1] => Array ( [code] => LGW, [name] => Gatwick )
)
After: Array
(
    [0] => Array ( [code] => LGW, [name] => Gatwick )
    [1] => Array ( [code] => LHR, [name] => Heathrow )
)`

[up](https://www.php.net/manual/vote-note.php?id=80798&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80798&page=function.asort&vote=down "Vote down!")

14


[**_mike at clear-link dot com_**](https://www.php.net/manual/en/function.asort.php#80798) [¶](https://www.php.net/manual/en/function.asort.php#80798)

**17 years ago**

`For a recent project I needed to sort an associative array by value first, and then by key if a particular value appeared multiple times. I wrote this function to accomplish the task. Note that the parameters default to sort ascending on both keys and values, but allow granular control over each.
<?php
function aksort(&$array,$valrev=false,$keyrev=false) {
if ($valrev) { arsort($array); } else { asort($array); }
    $vals = array_count_values($array);
    $i = 0;
    foreach ($vals AS $val=>$num) {
        $first = array_splice($array,0,$i);
        $tmp = array_splice($array,0,$num);
        if ($keyrev) { krsort($tmp); } else { ksort($tmp); }
        $array = array_merge($first,$tmp,$array);
        unset($tmp);
        $i = $num;
    }
}
// Example
$tmp = array('ca'=>1,'cb'=>2,'ce'=>1,'pa'=>2,'pe'=>1);
// Standard asort
asort($tmp);
print_r($tmp);
// Sort value ASC, key ASC
aksort($tmp);
print_r($tmp);
// Sort value DESC, key ASC
aksort($tmp,true);
print_r($tmp);
// Sort value DESC, key DESC
aksort($tmp,true,true);
print_r($tmp);
// Results
Array
(
    [pe] => 1
    [ca] => 1
    [ce] => 1
    [cb] => 2
    [pa] => 2
)
Array
(
    [ca] => 1
    [ce] => 1
    [pe] => 1
    [cb] => 2
    [pa] => 2
)
Array
(
    [cb] => 2
    [pa] => 2
    [ca] => 1
    [ce] => 1
    [pe] => 1
)
Array
(
    [pa] => 2
    [cb] => 2
    [pe] => 1
    [ce] => 1
    [ca] => 1
)`

[up](https://www.php.net/manual/vote-note.php?id=7787&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=7787&page=function.asort&vote=down "Vote down!")

6


[**_sweetland at whoadammit dot com_**](https://www.php.net/manual/en/function.asort.php#7787) [¶](https://www.php.net/manual/en/function.asort.php#7787)

**25 years ago**

`Here's a little routine I whipped up to sort multi-dimensional arrays:
<?php
/**
** comesafter ($s1, $s2)
**
** Returns 1 if $s1 comes after $s2 alphabetically, 0 if not.
**/
function comesafter ($s1, $s2) {
        /**
         ** We don't want to overstep the bounds of one of the strings and segfault,
         ** so let's see which one is shorter.
         **/
        $order = 1;
        if (strlen ($s1) > strlen ($s2)) {
                $temp = $s1;
                $s1 = $s2;
                $s2 = $temp;
                $order = 0;
        }
        for ($index = 0; $index < strlen ($s1); $index++) {
                /**
                 ** $s1 comes after $s2
                 **/
                if ($s1[$index] > $s2[$index]) return ($order);
                /**
                 ** $s1 comes before $s2
                 **/
                if ($s1[$index] < $s2[$index]) return (1 - $order);
        }

        /**
         ** Special case in which $s1 is a substring of $s2
         **/
        return ($order);
}
/**
** asortbyindex ($sortarray, $index)
**
** Sort a multi-dimensional array by a second-degree index. For instance, the 0th index
** of the Ith member of both the group and user arrays is a string identifier. In the
** case of a user array this is the username; with the group array it is the group name.
** asortby
**/
function asortbyindex ($sortarray, $index) {
        $lastindex = count ($sortarray) - 1;
        for ($subindex = 0; $subindex < $lastindex; $subindex++) {
                $lastiteration = $lastindex - $subindex;
                for ($iteration = 0; $iteration < $lastiteration;    $iteration++) {
                        $nextchar = 0;
                        if (comesafter ($sortarray[$iteration][$index], $sortarray[$iteration + 1][$index])) {
                                $temp = $sortarray[$iteration];
                                $sortarray[$iteration] = $sortarray[$iteration + 1];
                                $sortarray[$iteration + 1] = $temp;
                        }
                }
        }
        return ($sortarray);
}
?>
It's a bit long with all the comments, but I hope it helps.`

[up](https://www.php.net/manual/vote-note.php?id=80802&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80802&page=function.asort&vote=down "Vote down!")

8


[**_mike at clear-link dot com_**](https://www.php.net/manual/en/function.asort.php#80802) [¶](https://www.php.net/manual/en/function.asort.php#80802)

**17 years ago**

`Small typo in the aksort function I just submitted. Here's the entire thing again, with the correction noted:
<?php
function aksort(&$array,$valrev=false,$keyrev=false) {
if ($valrev) { arsort($array); } else { asort($array); }
$vals = array_count_values($array);
    $i = 0;
    foreach ($vals AS $val=>$num) {
        $first = array_splice($array,0,$i);
        $tmp = array_splice($array,0,$num);
        if ($keyrev) { krsort($tmp); } else { ksort($tmp); }
        $array = array_merge($first,$tmp,$array);
        unset($tmp);
        $i = $i+$num;
        // Fixed from previous post: $i = $num;
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=69425&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=69425&page=function.asort&vote=down "Vote down!")

4


[**_php at web-in-time dot com_**](https://www.php.net/manual/en/function.asort.php#69425) [¶](https://www.php.net/manual/en/function.asort.php#69425)

**19 years ago**

`acecream's function works fine, especially with the spectre extension.
nevertheless sometimes the index values have to be kept. To achieve this, just replace:
$sorted_arr[] = $array[$arr_key];
with:
$sorted_arr[$arr_key] = $array[$arr_key];`

[up](https://www.php.net/manual/vote-note.php?id=3984&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=3984&page=function.asort&vote=down "Vote down!")

2


[**_jacko at kring dot co dot uk_**](https://www.php.net/manual/en/function.asort.php#3984) [¶](https://www.php.net/manual/en/function.asort.php#3984)

**25 years ago**

`asort has one anoying feature, it ignores any default or implicit order in the data.  i.e. if two elements of an array contain "banana" then it is not garanteed that the first will still be the first after the sort.
This makes the Burrows-Wheeler block sort a bit of a pain to impliment, with a trailing string having to be appended to all strings before sorting, and removed after sorting. To maintain the so called "banana" order.`

[up](https://www.php.net/manual/vote-note.php?id=71344&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=71344&page=function.asort&vote=down "Vote down!")

6


[**_richard at happymango dot me dot uk_**](https://www.php.net/manual/en/function.asort.php#71344) [¶](https://www.php.net/manual/en/function.asort.php#71344)

**18 years ago**

`This is a fixed version of the same function I posted below. Now it will handle duplicate entries in the sorted field. EG: If there were two records that had the name Heathrow it would still work.
<?php
function record_sort($records, $field, $reverse=false)
{
    $hash = array();

    foreach($records as $key => $record)
    {
        $hash[$record[$field].$key] = $record;
    }

    ($reverse)? krsort($hash) : ksort($hash);

    $records = array();

    foreach($hash as $record)
    {
        $records []= $record;
    }

    return $records;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=12757&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=12757&page=function.asort&vote=down "Vote down!")

3


[**_freeman at generalresources dot com_**](https://www.php.net/manual/en/function.asort.php#12757) [¶](https://www.php.net/manual/en/function.asort.php#12757)

**24 years ago**

`The asortbyindex($sortarray, $index) looks like sort not asort. The key of the $sortarray was changed.`

[up](https://www.php.net/manual/vote-note.php?id=43513&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=43513&page=function.asort&vote=down "Vote down!")

5


[**_rojaro_**](https://www.php.net/manual/en/function.asort.php#43513) [¶](https://www.php.net/manual/en/function.asort.php#43513)

**21 years ago**

`Advanced sort array by second index function, which produces ascending (default) or descending output and uses optionally natural case insensitive sorting (which can be optionally case sensitive as well).
Only the first two arguments are required.
<?php
function sabsi ($array, $index, $order='asc', $natsort=FALSE, $case_sensitive=FALSE) {
if(is_array($array) && count($array)>0) {
    foreach(array_keys($array) as $key) $temp[$key]=$array[$key][$index];
    if(!$natsort) ($order=='asc')? asort($temp) : arsort($temp);
    else {
      ($case_sensitive)? natsort($temp) : natcasesort($temp);
      if($order!='asc') $temp=array_reverse($temp,TRUE);
    }
    foreach(array_keys($temp) as $key) (is_numeric($key))? $sorted[]=$array[$key] : $sorted[$key]=$array[$key];
    return $sorted;
}
return $array;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=103858&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103858&page=function.asort&vote=down "Vote down!")

4


[**_Anon_**](https://www.php.net/manual/en/function.asort.php#103858) [¶](https://www.php.net/manual/en/function.asort.php#103858)

**14 years ago**

`Case insensitive sort in one line:
<?php
array_multisort(array_map('strtolower', $array), $array);
?>`

[up](https://www.php.net/manual/vote-note.php?id=19545&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=19545&page=function.asort&vote=down "Vote down!")

4


[**_rcwang at cmu dot edu_**](https://www.php.net/manual/en/function.asort.php#19545) [¶](https://www.php.net/manual/en/function.asort.php#19545)

**23 years ago**

`Here's my version of sorting multi-dimensional array by 2nd index.
Feel free to change the code to suit your needs.
<?php
function aSortBySecondIndex($multiArray, $secondIndex) {
    while (list($firstIndex, ) = each($multiArray))
        $indexMap[$firstIndex] = $multiArray[$firstIndex][$secondIndex];
    asort($indexMap);
    while (list($firstIndex, ) = each($indexMap))
        if (is_numeric($firstIndex))
            $sortedArray[] = $multiArray[$firstIndex];
        else $sortedArray[$firstIndex] = $multiArray[$firstIndex];
    return $sortedArray;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=20433&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=20433&page=function.asort&vote=down "Vote down!")

3


[**_salchicha at cable dot net dot co_**](https://www.php.net/manual/en/function.asort.php#20433) [¶](https://www.php.net/manual/en/function.asort.php#20433)

**23 years ago**

`Here's one I whipped up to allow you to sort an array of a specific class by a member or function:
<?php
// Sort a class by one of its members (even lowercase!!!)
function casort($arr, $var) {
$tarr = array();
$rarr = array();
for($i = 0; $i < count($arr); $i++) {
      $element = $arr[$i];
      $tarr[] = strtolower($element->{$var});
}
reset($tarr);
asort($tarr);
$karr = array_keys($tarr);
for($i = 0; $i < count($tarr); $i++) {
      $rarr[] = $arr[intval($karr[$i])];
}
return $rarr;
}
?>
It works very well. For example, I have a Room class with members title, isActive(), date, etc. I can sort an array by casort($rooms, "title") or casort($rooms, "isActive()") and it'll work.`

[up](https://www.php.net/manual/vote-note.php?id=125314&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125314&page=function.asort&vote=down "Vote down!")

2


[**_Jesse K_**](https://www.php.net/manual/en/function.asort.php#125314) [¶](https://www.php.net/manual/en/function.asort.php#125314)

**5 years ago**

``'asort' is fine for sorting arrays in English, but if accented characters exist in the array then it is better to use the 'asort' method of PHP's Collator class:
[https://www.php.net/manual/en/class.collator.php](https://www.php.net/manual/en/class.collator.php)
$collator = new \Collator('fr_CA');
$collator->asort($french_list);
There are options for using `setlocale()` to control `asort` behaviour, but it isn't reliable across systems.
For instance, in my development environment I only have access to the following locals:
$ locale -a
C
C.UTF-8
POSIX``

[up](https://www.php.net/manual/vote-note.php?id=23920&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=23920&page=function.asort&vote=down "Vote down!")

1


[**_Anonymous_**](https://www.php.net/manual/en/function.asort.php#23920) [¶](https://www.php.net/manual/en/function.asort.php#23920)

**23 years ago**

`Similar to above but for an array of arrays instead of an array of objects.
<?php
function aasort($x,$var,$cmp='strcasecmp'){
if ( is_string($var) ) $var = "'$var'";
uasort($x,
    create_function('$a,$b',
      'return '.$cmp.'( $a['.$var.'],$b['.$var.']);')
);
return $x;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=125418&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125418&page=function.asort&vote=down "Vote down!")

 -1


[**_marty8zhang at gmail dot com_**](https://www.php.net/manual/en/function.asort.php#125418) [¶](https://www.php.net/manual/en/function.asort.php#125418)

**5 years ago**

`"This function sorts an array such that array indices maintain their correlation with the array elements they are associated with."
Note this sentence in the description has a quite important implication especially when you're working with an originally non-indexed (or say integer-indexed) array and JSON encoding/decoding.
I'm not reporting this as a bug, because the end result does fit into the description.
<?php
$myArray = ['small_image', 'image'];
var_dump(json_encode($myArray)); // string(23) "["small_image","image"]"
var_dump(is_object($myArray)); // bool(false)
asort($myArray);
$myJson = json_encode($myArray);
var_dump($myJson); // string(31) "{"1":"image","0":"small_image"}"
var_dump(is_object($myArray)); // bool(false)
/*
* class stdClass#1 (2) {
*     public $1 =>
*     string(5) "image"
*     public $0 =>
*     string(11) "small_image"
* }
*/
var_dump(json_decode($myJson));
?>`

[up](https://www.php.net/manual/vote-note.php?id=111537&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111537&page=function.asort&vote=down "Vote down!")

0


[**_stephen \[ at \] brooksie-net \[ dot \] co \[ dot \] uk_**](https://www.php.net/manual/en/function.asort.php#111537) [¶](https://www.php.net/manual/en/function.asort.php#111537)

**12 years ago**

`It is obviously necessary to log the keys used as so we don't overwrite previous entries in the array ;o)
N.B. this also effects the timings, but still faster than the alternatives :
     * int : 0.00159    (ms)
     * str : 0.00092    (ms)
<?php
private function _keySort(Array $data)
    {
        $keys = array();

        foreach($data as $row) {

            $keyIncrement =
                (!isset($keys[$row[$this->_orderField]]))
                    ? $keys[$row[$this->_orderField]] = 0
                    : ++$keys[$row[$this->_orderField]];
            $tempArray[$row[$this->_orderField].$keyIncrement] = $row;
        }
        if ($this->_orderDirection == 'DESC') {
            krsort($tempArray, SORT_NATURAL | SORT_FLAG_CASE );
        } else {
            ksort($tempArray, SORT_NATURAL | SORT_FLAG_CASE);
        }
        return $tempArray;

    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=78925&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78925&page=function.asort&vote=down "Vote down!")

0


[**_przemekkus \[at\] interia \[dot\] pl_**](https://www.php.net/manual/en/function.asort.php#78925) [¶](https://www.php.net/manual/en/function.asort.php#78925)

**17 years ago**

`Function written by a dot brandon at chello dot nl has an error  - wrong variable name. It should be:
if($rev) arsort($named_hash,$flags=0) ;
instead of
if($reverse) arsort($named_hash,$flags=0) ;`

[up](https://www.php.net/manual/vote-note.php?id=75749&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75749&page=function.asort&vote=down "Vote down!")

0


[**_gunnar at taljaren dot se_**](https://www.php.net/manual/en/function.asort.php#75749) [¶](https://www.php.net/manual/en/function.asort.php#75749)

**18 years ago**

`for ($i=0;$i<5;$i++)
$values[] = $i;
asort($values);
works, but
for ($i=0;$i<5;$i++)
$values[$i] =$i;
asort($values);
doesn't!`

[up](https://www.php.net/manual/vote-note.php?id=72582&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72582&page=function.asort&vote=down "Vote down!")

0


[**_smileaf at smileaf dot org_**](https://www.php.net/manual/en/function.asort.php#72582) [¶](https://www.php.net/manual/en/function.asort.php#72582)

**18 years ago**

`Ok I was mistaken, after re-reading the previous post the ".$key" is important. What caused the sorting issue for me wasn't that at all. But rather something else.
doing an: asort($records, $flags); before returning fixes the sorting problems.
The sorting problem I was refearing to causes a character based sorting done on numeric data.
so instead of:
1
2
3
...
10
12
20
It was returned back as
1
10
12
2
20
3
...
basically what I was trying to fix in the first place.`

[up](https://www.php.net/manual/vote-note.php?id=27372&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=27372&page=function.asort&vote=down "Vote down!")

0


[**_mbevan at marginsoftware dot com_**](https://www.php.net/manual/en/function.asort.php#27372) [¶](https://www.php.net/manual/en/function.asort.php#27372)

**22 years ago**

`Nevermind... use my last note as a quick tip: if you wish to keep the keys, use asort() and arsort() in place of sort() and rsort().`

[up](https://www.php.net/manual/vote-note.php?id=90425&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90425&page=function.asort&vote=down "Vote down!")

 -1


[**_Eran_**](https://www.php.net/manual/en/function.asort.php#90425) [¶](https://www.php.net/manual/en/function.asort.php#90425)

**16 years ago**

`i made this sample multi dimensional array sort to someone who needed to read lines from a text file instead of using sql - order by statement.
the idea is to take the key and sort(order) the specific column and then order the entire of the array as the selected column asort returned.
<?php
/**
*
* This sample is reading text data
* and perform a sort to a 2 dimensional array
* just like a normal sql do to "order by asc"
*
*/
$foo = array();
/*
# SORT_REGULAR - compare items normally (don't change types)
# SORT_NUMERIC - compare items numerically
# SORT_STRING - compare items as strings
*/
$sort_by = SORT_REGULAR;
/*
# 0 - order by name column
# 1 - order by age column
# 2 - order by rank column
# 3 - order by color column
*/
$order_by = 1;
// source file
$line_of_text[1] = 'a1name|f2age|h3rank|jcolor';
$line_of_text[2] = 'b1name|d2age|i3rank|k4color';
$line_of_text[0] = 'c1name|e2age|g3rank|l4color';
// make array
for ($x=0; $x<=2; $x++)
{
    $line = explode('|',$line_of_text[$x]);
    // save it by coulmns otherwise it will saved like rows
    for ($i=0; $i<=3; $i++) {
          $foo[$i][$x] = $line[$i];
    }
}
// get the key order
$a = $foo[$order_by];
// sort
asort($a, $sort_by);
// start print
echo "<table cellpudding=0 cellspacing=0 border=1>\n";
        echo "<tr>\n";
          echo "<td>key</td>\n";
          echo "<td>name</td>\n";
          echo "<td>age</td>\n";
          echo "<td>rank</td>\n";
          echo "<td>color</td>\n";
        echo "</tr>\n";
// print by key order
foreach ($a as $k => $v) {
    echo "<tr>\n";
      echo "<td>$k</td>\n";
      // you can print here a for loop (0 to num of columns[=3])
      echo "<td>".$foo[0][$k]."</td>\n";
      echo "<td>".$foo[1][$k]."</td>\n";
      echo "<td>".$foo[2][$k]."</td>\n";
      echo "<td>".$foo[3][$k]."</td>\n";
    echo "</tr>\n";
}
echo "</table>\n";
?>`

[up](https://www.php.net/manual/vote-note.php?id=31628&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=31628&page=function.asort&vote=down "Vote down!")

 -1


[**_spectre at hellfish dot NOSPAM dot org_**](https://www.php.net/manual/en/function.asort.php#31628) [¶](https://www.php.net/manual/en/function.asort.php#31628)

**22 years ago**

`that works nicely, tho it breaks the result-array up if one or more of arrays indexes are deleted before sorting. this one should fix it up:
change:
for ($i = 0; $i < sizeof($array); $i++) {
to:
foreach ($array as $i => $k) {`

[up](https://www.php.net/manual/vote-note.php?id=75991&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75991&page=function.asort&vote=down "Vote down!")

 -1


[**_a dot brandon at chello dot nl_**](https://www.php.net/manual/en/function.asort.php#75991) [¶](https://www.php.net/manual/en/function.asort.php#75991)

**18 years ago**

`I use this for quasi-SQL orderby. Loosely based on smileaf. Any good for you nerds?
<?
function named_records_sort($named_recs, $order_by, $rev=false, $flags=0)
{// Create 1-dimensional named array with just
// sortfield (in stead of record) values
    $named_hash = array();
     foreach($named_recs as $key=>$fields)
             $named_hash["$key"] = $fields[$order_by];

// Order 1-dimensional array,
// maintaining key-value relations
    if($reverse) arsort($named_hash,$flags=0) ;
    else asort($named_hash, $flags=0);

// Create copy of named records array
// in order of sortarray
    $sorted_records = array();
    foreach($named_hash as $key=>$val)
           $sorted_records["$key"]= $named_recs[$key];

return $sorted_records;} // named_recs_sort()
function show_sorted_records($named_recs, $order_by, $rev=false, $flags=0)
{$sorted_records=named_records_sort($named_recs, $order_by, $rev, $flags);
foreach($sorted_records as $name=>$fields)
{echo "<b>$name</b>   ";
foreach($fields as $field=>$val)
          echo "$field = $val "; echo "<br>";}
} // show_sorted_records()
$girl_friends=array();
$girl_friends["Anna"]=
array("born"=>'1989-08-22',"cupsize"=>'B-',"IQ"=>105, "daddy"=>'rich');
$girl_friends["Zoe"]
=array("born"=>'1978-03-11',"cupsize"=>'C#',"IQ"=>130, "daddy"=>'poor');
$girl_friends["Lilly"]
=array("born"=>'1985-06-16',"cupsize"=>'DD',"IQ"=>90, "daddy"=>'nasty');
$order_by="cupsize"; echo "And the winners are: <br>";
show_sorted_records($girl_friends, $order_by, true);
?>`

[up](https://www.php.net/manual/vote-note.php?id=7386&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=7386&page=function.asort&vote=down "Vote down!")

 -2


[**_bwuhlman at tallships dot ca_**](https://www.php.net/manual/en/function.asort.php#7386) [¶](https://www.php.net/manual/en/function.asort.php#7386)

**25 years ago**

`Well, actually, asort has *two* annoying features.
It works perfectly well sorting hashes (or associative arrays, as you might have it), but doggedly refuses to sort regular arrays maintaining index assocation. Kind've makes sense, but the docs don't explicitly say you can't do it.
Urgggh.`

[up](https://www.php.net/manual/vote-note.php?id=103703&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103703&page=function.asort&vote=down "Vote down!")

 -4


[**_rick at toewsweb dot net_**](https://www.php.net/manual/en/function.asort.php#103703) [¶](https://www.php.net/manual/en/function.asort.php#103703)

**14 years ago**

`On sorting by value first, then by key (cf., 2008-01-31 notes by mike at clear-link dot com):
What occurred to me to solve this problem was to extract the keys and values into separate arrays, then use array_multisort to get the desired order:
Ex:
<?php
$kvpairs = array('noun' => 'thought', 'animal' => 'fish', 'abstract' => 'thought', 'food' => 'fish', 'verb' => 'fish');
print "before:\n";
print_r($kvpairs);
// Essentially, one line of code is all that's needed for the sort:
array_multisort(array_values($kvpairs), array_keys($kvpairs), $kvpairs);
print "after:\n";
print_r($kvpairs);
?>
before:
Array
(
    [noun] => thought
    [animal] => fish
    [abstract] => thought
    [food] => fish
    [verb] => fish
)
after:
Array
(
    [animal] => fish
    [food] => fish
    [verb] => fish
    [abstract] => thought
    [noun] => thought
)
Of course, array_multisort allows you to specify sort order (SORT_ASC, SORT_DESC) and sort type (SORT_REGULAR, SORT_STRING, SORT_NUMERIC) for each array you pass it.`

[up](https://www.php.net/manual/vote-note.php?id=23919&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=23919&page=function.asort&vote=down "Vote down!")

 -1


[**_phzzzt .a.t. acm .d.o.t. org_**](https://www.php.net/manual/en/function.asort.php#23919) [¶](https://www.php.net/manual/en/function.asort.php#23919)

**23 years ago**

`Similar to above but for an array of arrays instead of an array of objects.
<?php
function aasort($x,$var,$cmp='strcasecmp'){
if ( is_string($var) ) $var = "\'$var\'";
uasort($x,
    create_function('$a,$b',
      'return '.$cmp.'( $a['.$var.'],$b['.$var.']);')
);
return $x;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=123145&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123145&page=function.asort&vote=down "Vote down!")

 -3


[**_elhanafi123 at gmail dot com_**](https://www.php.net/manual/en/function.asort.php#123145) [¶](https://www.php.net/manual/en/function.asort.php#123145)

**7 years ago**

`I have written this function so its sort an multidimensional array with a specific key.
<?php
function sort_array($array, $sort_value, $reverse = false){
    $value = $result = array();

    foreach($array as $key => $rows){
        $value[$key] = strtolower($rows[$sort_value]);
    }

    if($reverse == true){
        arsort($value);
    }else{
        asort($value);
    }

    foreach($value as $keys => $null){
        $result[] = $array[$keys];
    }

    return $result;
}
?>
Examples
<?php
$array = array(array('a' => 'foo'), array('a' => 'foo4'), array('a' => 'foo2'), array('a' => 'foo3'));
print_r($array);
//Array ( [0] => Array ( [a] => foo ) [1] => Array ( [a] => foo4 ) [2] => Array ( [a] => foo2 ) [3] => Array ( [a] => foo3 ) )
print_r(sort_array($array, 'a'));
//Array ( [0] => Array ( [a] => foo ) [1] => Array ( [a] => foo2 ) [2] => Array ( [a] => foo3 ) [3] => Array ( [a] => foo4 ) )
print_r(sort_array($array, 'a', true));
//Array ( [0] => Array ( [a] => foo4 ) [1] => Array ( [a] => foo3 ) [2] => Array ( [a] => foo2 ) [3] => Array ( [a] => foo ) )
?>`

[up](https://www.php.net/manual/vote-note.php?id=81155&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81155&page=function.asort&vote=down "Vote down!")

 -4


[**_bakatamas at freemail dot hu_**](https://www.php.net/manual/en/function.asort.php#81155) [¶](https://www.php.net/manual/en/function.asort.php#81155)

**17 years ago**

`Dear mike at clear-link dot com!
I needed a case insensitive version of your function. It is still not perfect as I have to do something with country specific characters (öüóőúéáűíÖÜÓŐÚÉÁŰÍ)
function akisort(&$array,$valrev=false,$keyrev=false)
    {
    if ($valrev)
        {
        arsort($array);
        }
        else
        {
        asort($array);
        };
    $vals = array_count_values($array);
    $i = 0;
    foreach ($vals AS $val=>$num)
        {
        $first = array_splice($array,0,$i);
        $tmp = array_splice($array,0,$num);
        $tmp2 = array();
        foreach($tmp as $key => $value)
            {
            $tmp2[] = $key;
            $number = $value;
            };
        natcasesort($tmp2);
        reset($tmp2);
        print_r($tmp2);
        unset($tmp);
        foreach($tmp2 as $key => $value)
            {
            $tmp[$value] = $number;
            };
        if($keyrev)
            {
            $tmp = array_reverse($tmp, true);
            };
        $array = array_merge($first,$tmp,$array);
        unset($tmp);
        $i = $i+$num;
        };
};`

[up](https://www.php.net/manual/vote-note.php?id=80450&page=function.asort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80450&page=function.asort&vote=down "Vote down!")

 -3


[**_mzvarik at gmail dot com_**](https://www.php.net/manual/en/function.asort.php#80450) [¶](https://www.php.net/manual/en/function.asort.php#80450)

**17 years ago**

`I noticed that my function mentioned earlier is very misleading - somebody please delete that note!
This is how you sort:
<?php
setlocale (LC_ALL, 'czech');
$array = array("a", "č", "c");
usort ($array, 'strcoll');
print_r($array);
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.asort&repo=en&redirect=https://www.php.net/manual/en/function.asort.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google