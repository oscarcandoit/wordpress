---
url: https://www.php.net/manual/en/function.array-multisort.php
scraped_at: 2025-10-20T02:58:52.136Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# array\_multisort

(PHP 4, PHP 5, PHP 7, PHP 8)

array\_multisort — Sort multiple or multi-dimensional arrays

### Description [¶](https://www.php.net/manual/en/function.array-multisort.php\#refsect1-function.array-multisort-description)

**array\_multisort**(

[array](https://www.php.net/manual/en/language.types.array.php) `&$array1`,

[mixed](https://www.php.net/manual/en/language.types.mixed.php) `$array1_sort_order` = SORT\_ASC,

[mixed](https://www.php.net/manual/en/language.types.mixed.php) `$array1_sort_flags` = SORT\_REGULAR,

[mixed](https://www.php.net/manual/en/language.types.mixed.php) `...$rest`

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**array\_multisort()** can be used to sort several
arrays at once, or a multi-dimensional array by one or more
dimensions.


Associative ([string](https://www.php.net/manual/en/language.types.string.php)) keys will be maintained, but numeric
keys will be re-indexed.


> **Note**:
>
>
> If two members compare as equal, they retain their original order.
> Prior to PHP 8.0.0, their relative order in the sorted array was undefined.

> **Note**:
>
>
> Resets array's internal pointer to the first element.

### Parameters [¶](https://www.php.net/manual/en/function.array-multisort.php\#refsect1-function.array-multisort-parameters)

`array1`

An [array](https://www.php.net/manual/en/language.types.array.php) being sorted.


`array1_sort_order`

The order used to sort the previous [array](https://www.php.net/manual/en/language.types.array.php) argument. Either
**`[SORT\_ASC](https://www.php.net/manual/en/array.constants.php#constant.sort-asc)`** to sort ascendingly or **`[SORT\_DESC](https://www.php.net/manual/en/array.constants.php#constant.sort-desc)`**
to sort descendingly.


This argument can be swapped with `array1_sort_flags`
or omitted entirely, in which case **`[SORT\_ASC](https://www.php.net/manual/en/array.constants.php#constant.sort-asc)`** is assumed.


`array1_sort_flags`

Sort options for the previous [array](https://www.php.net/manual/en/language.types.array.php) argument:


Sorting type flags:


- **`[SORT\_REGULAR](https://www.php.net/manual/en/array.constants.php#constant.sort-regular)`** \- compare items normally
(don't change types)
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


This argument can be swapped with `array1_sort_order`
or omitted entirely, in which case **`[SORT\_REGULAR](https://www.php.net/manual/en/array.constants.php#constant.sort-regular)`** is assumed.


`rest`

More arrays, optionally followed by sort order and flags. Only elements
corresponding to equivalent elements in previous arrays are compared.
In other words, the sort is lexicographical.


### Return Values [¶](https://www.php.net/manual/en/function.array-multisort.php\#refsect1-function.array-multisort-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/function.array-multisort.php\#refsect1-function.array-multisort-examples)

**Example #1 Sorting multiple arrays**

`<?php
$ar1 = array(10, 100, 100, 0);
$ar2 = array(1, 3, 2, 4);
array_multisort($ar1, $ar2);
var_dump($ar1);
var_dump($ar2);
?>`

Run code

In this example, after sorting, the first array will contain 0,
10, 100, 100. The second array will contain 4, 1, 2, 3. The
entries in the second array corresponding to the identical
entries in the first array (100 and 100) were sorted as well.


```
array(4) {
  [0]=> int(0)
  [1]=> int(10)
  [2]=> int(100)
  [3]=> int(100)
}
array(4) {
  [0]=> int(4)
  [1]=> int(1)
  [2]=> int(2)
  [3]=> int(3)
}
```

**Example #2 Sorting multi-dimensional array**

`<?php
$ar = array(
       array("10", 11, 100, 100, "a"),
       array(   1,  2, "2",   3,   1)
      );
array_multisort($ar[0], SORT_ASC, SORT_STRING,
                $ar[1], SORT_NUMERIC, SORT_DESC);
var_dump($ar);
?>`

Run code

In this example, after sorting, the first array will transform to
"10", 100, 100, 11, "a" (it was sorted as strings in ascending
order). The second will contain 1, 3, "2", 2, 1 (sorted as numbers,
in descending order).


```
array(2) {
  [0]=> array(5) {
    [0]=> string(2) "10"
    [1]=> int(100)
    [2]=> int(100)
    [3]=> int(11)
    [4]=> string(1) "a"
  }
  [1]=> array(5) {
    [0]=> int(1)
    [1]=> int(3)
    [2]=> string(1) "2"
    [3]=> int(2)
    [4]=> int(1)
  }
}
```

**Example #3 Sorting database results**

For this example, each element in the data
array represents one row in a table. This type of dataset is typical
of database records.


Example data:


```
volume | edition
-------+--------
    67 |       2
    86 |       1
    85 |       6
    98 |       2
    86 |       6
    67 |       7
```

The data as an array, called data. This would usually,
for example, be obtained by looping with [mysqli\_fetch\_assoc()](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php).


In this example, we will order by volume descending,
edition ascending.


We have an array of rows, but **array\_multisort()**
requires an array of columns, so we use the below code to obtain the
columns, then perform the sorting.


`<?php
// The data as created by looping over mysqli_fetch_assoc:
$data[] = array('volume' => 67, 'edition' => 2);
$data[] = array('volume' => 86, 'edition' => 1);
$data[] = array('volume' => 85, 'edition' => 6);
$data[] = array('volume' => 98, 'edition' => 2);
$data[] = array('volume' => 86, 'edition' => 6);
$data[] = array('volume' => 67, 'edition' => 7);
// Obtain a list of columns
foreach ($data as $key => $row) {
    $volume[$key]  = $row['volume'];
    $edition[$key] = $row['edition'];
}
// You can use array_column() instead of the above code
$volume  = array_column($data, 'volume');
$edition = array_column($data, 'edition');
// Sort the data with volume descending, edition ascending
// Add $data as the last parameter, to sort by the common key
array_multisort($volume, SORT_DESC, $edition, SORT_ASC, $data);
// Loop over the data and output the sorted values for each column
echo 'volume | edition', PHP_EOL;
echo '-------+--------', PHP_EOL;
for ($i = 0; $i < count($data); $i++) {
     printf("%6d | %7d\n", $volume[$i], $edition[$i]);
}
?>`

Run code

The dataset is now sorted, and will look like this:


```
volume | edition
-------+--------
    98 |       2
    86 |       1
    86 |       6
    85 |       6
    67 |       2
    67 |       7
```

**Example #4 Case insensitive sorting**

Both **`[SORT\_STRING](https://www.php.net/manual/en/array.constants.php#constant.sort-string)`** and
**`[SORT\_REGULAR](https://www.php.net/manual/en/array.constants.php#constant.sort-regular)`** are case sensitive, strings
starting with a capital letter will come before strings starting
with a lowercase letter.


To perform a case insensitive sort, force the sorting order to be
determined by a lowercase copy of the original array.


`<?php
$array = array('Alpha', 'atomic', 'Beta', 'bank');
$array_lowercase = array_map('strtolower', $array);
array_multisort($array_lowercase, SORT_ASC, SORT_STRING, $array);
print_r($array);
?>`

Run code

The above example will output:

```
Array
(
    [0] => Alpha
    [1] => atomic
    [2] => bank
    [3] => Beta
)
```

### See Also [¶](https://www.php.net/manual/en/function.array-multisort.php\#refsect1-function.array-multisort-seealso)

- [usort()](https://www.php.net/manual/en/function.usort.php) \- Sort an array by values using a user-defined comparison function
- The [comparison of array sorting functions](https://www.php.net/manual/en/array.sorting.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/array-multisort.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.array-multisort%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.array-multisort&repo=en&redirect=https://www.php.net/manual/en/function.array-multisort.php)

### User Contributed Notes 8 notes

[up](https://www.php.net/manual/vote-note.php?id=100534&page=function.array-multisort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100534&page=function.array-multisort&vote=down "Vote down!")

225


[**_jimpoz at jimpoz dot com_**](https://www.php.net/manual/en/function.array-multisort.php#100534) [¶](https://www.php.net/manual/en/function.array-multisort.php#100534)

**14 years ago**

`I came up with an easy way to sort database-style results. This does what example 3 does, except it takes care of creating those intermediate arrays for you before passing control on to array_multisort().
<?php
function array_orderby()
{
    $args = func_get_args();
    $data = array_shift($args);
    foreach ($args as $n => $field) {
        if (is_string($field)) {
            $tmp = array();
            foreach ($data as $key => $row)
                $tmp[$key] = $row[$field];
            $args[$n] = $tmp;
            }
    }
    $args[] = &$data;
    call_user_func_array('array_multisort', $args);
    return array_pop($args);
}
?>
The sorted array is now in the return value of the function instead of being passed by reference.
<?php
$data[] = array('volume' => 67, 'edition' => 2);
$data[] = array('volume' => 86, 'edition' => 1);
$data[] = array('volume' => 85, 'edition' => 6);
$data[] = array('volume' => 98, 'edition' => 2);
$data[] = array('volume' => 86, 'edition' => 6);
$data[] = array('volume' => 67, 'edition' => 7);
// Pass the array, followed by the column names and sort flags
$sorted = array_orderby($data, 'volume', SORT_DESC, 'edition', SORT_ASC);
?>`

[up](https://www.php.net/manual/vote-note.php?id=119291&page=function.array-multisort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119291&page=function.array-multisort&vote=down "Vote down!")

74


[**_matt at bosc dot io_**](https://www.php.net/manual/en/function.array-multisort.php#119291) [¶](https://www.php.net/manual/en/function.array-multisort.php#119291)

**9 years ago**

`One-liner function to sort multidimensionnal array by key, thank's to array_column
<?php
array_multisort (array_column($array, 'key'), SORT_DESC, $array);
?>`

[up](https://www.php.net/manual/vote-note.php?id=91638&page=function.array-multisort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91638&page=function.array-multisort&vote=down "Vote down!")

91


[**_cagret at gmail dot com_**](https://www.php.net/manual/en/function.array-multisort.php#91638) [¶](https://www.php.net/manual/en/function.array-multisort.php#91638)

**16 years ago**

`A more inuitive way of sorting multidimensional arrays using array_msort() in just one line, you don't have to divide the original array into per-column-arrays:
<?php
$arr1 = array(
    array('id'=>1,'name'=>'aA','cat'=>'cc'),
    array('id'=>2,'name'=>'aa','cat'=>'dd'),
    array('id'=>3,'name'=>'bb','cat'=>'cc'),
    array('id'=>4,'name'=>'bb','cat'=>'dd')
);
$arr2 = array_msort($arr1, array('name'=>SORT_DESC, 'cat'=>SORT_ASC));
debug($arr1, $arr2);
arr1:
    0:
        id: 1 (int)
        name: aA (string:2)
        cat: cc (string:2)
    1:
        id: 2 (int)
        name: aa (string:2)
        cat: dd (string:2)
    2:
        id: 3 (int)
        name: bb (string:2)
        cat: cc (string:2)
    3:
        id: 4 (int)
        name: bb (string:2)
        cat: dd (string:2)
arr2:
    2:
        id: 3 (int)
        name: bb (string:2)
        cat: cc (string:2)
    3:
        id: 4 (int)
        name: bb (string:2)
        cat: dd (string:2)
    0:
        id: 1 (int)
        name: aA (string:2)
        cat: cc (string:2)
    1:
        id: 2 (int)
        name: aa (string:2)
        cat: dd (string:2)
function array_msort($array, $cols)
{
    $colarr = array();
    foreach ($cols as $col => $order) {
        $colarr[$col] = array();
        foreach ($array as $k => $row) { $colarr[$col]['_'.$k] = strtolower($row[$col]); }
    }
    $eval = 'array_multisort(';
    foreach ($cols as $col => $order) {
        $eval .= '$colarr[\''.$col.'\'],'.$order.',';
    }
    $eval = substr($eval,0,-1).');';
    eval($eval);
    $ret = array();
    foreach ($colarr as $col => $arr) {
        foreach ($arr as $k => $v) {
            $k = substr($k,1);
            if (!isset($ret[$k])) $ret[$k] = $array[$k];
            $ret[$k][$col] = $array[$k][$col];
        }
    }
    return $ret;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=114076&page=function.array-multisort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114076&page=function.array-multisort&vote=down "Vote down!")

48


[**_Robert C_**](https://www.php.net/manual/en/function.array-multisort.php#114076) [¶](https://www.php.net/manual/en/function.array-multisort.php#114076)

**11 years ago**

`Hi,
I would like to see the next code snippet to be added to [http://nl3.php.net/array\_multisort](http://nl3.php.net/array_multisort)
Purpose: Sort a 2-dimensional array on some key(s)
Advantage of function:
- uses PHP's array_multisort function for sorting;
- it prepares the arrays (needed by array_multisort) for you;
- allows the sort criteria be passed as a separate array (It is possible to use sort order and flags.);
- easy to set/overwrite the way strings are sorted (case insensitive instead of case sensitive, which is PHP's default way of sorting);
- performs excellent
function MultiSort($data, $sortCriteria, $caseInSensitive = true)
{
if( !is_array($data) || !is_array($sortCriteria))
    return false;
$args = array();
$i = 0;
foreach($sortCriteria as $sortColumn => $sortAttributes)
{
    $colList = array();
    foreach ($data as $key => $row)
    {
      $convertToLower = $caseInSensitive && (in_array(SORT_STRING, $sortAttributes) || in_array(SORT_REGULAR, $sortAttributes));
      $rowData = $convertToLower ? strtolower($row[$sortColumn]) : $row[$sortColumn];
      $colLists[$sortColumn][$key] = $rowData;
    }
    $args[] = &$colLists[$sortColumn];

    foreach($sortAttributes as $sortAttribute)
    {
      $tmp[$i] = $sortAttribute;
      $args[] = &$tmp[$i];
      $i++;
     }
}
$args[] = &$data;
call_user_func_array('array_multisort', $args);
return end($args);
}
Usage:
//Fill an array with random test data
define('MAX_ITEMS', 15);
define('MAX_VAL', 20);
for($i=0; $i < MAX_ITEMS; $i++)
$data[] = array('field1' => rand(1, MAX_VAL), 'field2' => rand(1, MAX_VAL), 'field3' => rand(1, MAX_VAL) );

//Set the sort criteria (add as many fields as you want)
$sortCriteria =
array('field1' => array(SORT_DESC, SORT_NUMERIC),
       'field3' => array(SORT_DESC, SORT_NUMERIC)
);
//Call it like this:
$sortedData = MultiSort($data, $sortCriteria, true);`

[up](https://www.php.net/manual/vote-note.php?id=105798&page=function.array-multisort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105798&page=function.array-multisort&vote=down "Vote down!")

21


[**_nick (\[AT\]) nickyost (\[DOT\]) com_**](https://www.php.net/manual/en/function.array-multisort.php#105798) [¶](https://www.php.net/manual/en/function.array-multisort.php#105798)

**14 years ago**

`USort function can be used to sort multidimensional arrays with almost no work whatsoever by using the individual values within the custom sort function.
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
This does in 4 lines what other functions took 40 to 50 lines to do. This does not require you to create temporary arrays or anything. This is, for me, a highly preferred solution over this function.
Hope it helps!`

[up](https://www.php.net/manual/vote-note.php?id=69656&page=function.array-multisort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=69656&page=function.array-multisort&vote=down "Vote down!")

3


[**_brettz9 throu gh yah_**](https://www.php.net/manual/en/function.array-multisort.php#69656) [¶](https://www.php.net/manual/en/function.array-multisort.php#69656)

**19 years ago**

`Often, one may have a group of arrays which have parallel data that need to be kept associated with each other (e.g., the various attribute values of a group of elements might be stored in their own arrays). Using array_multisort as is, by specifying additional fields, it is possible, as in the documentation example cited below, that this association will be lost.
To take this example set of data from the documentation:
<?php
$ar1 = array("10", 100, 100, "a");
$ar2 = array(1, 3, "2", 1);
?>
The example goes on to sort it this way:
<?php
array_multisort($ar1, $ar2);
?>
In this case, although the "10" remains associated with the first '1' after being sorted, the "2" and '3' are reversed from their original order.
In order to sort by one field only (yet still have the other array(s) being correspondingly sorted), one can use array_keys (which makes an array out of the keys) to ensure that no further sub-sorting is performed. This works because array_keys is making an array for which no duplicates can exist (since keys will be unique), and thus, the subsequent fields will have no relevance as far as subsorting.
So, using the above data, we can perform this sort instead:
<?php
$ar3 = array_keys($ar1);
array_multisort($ar1, $ar3, $ar2);
?>
which, when $ar1 and $ar2 are dumped gives:
array(4) {
[0]=> string(2) "10"
[1]=> string(1) "a"
[2]=> int(100)
[3]=> int(100)
}
array(4) {
[0]=>  int(1)
[1]=>  int(1)
[2]=>  int(3)
[3]=>  string(1) "2"
}`

[up](https://www.php.net/manual/vote-note.php?id=113445&page=function.array-multisort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113445&page=function.array-multisort&vote=down "Vote down!")

3


[**_Magento-User_**](https://www.php.net/manual/en/function.array-multisort.php#113445) [¶](https://www.php.net/manual/en/function.array-multisort.php#113445)

**12 years ago**

`When sorting an array of (complex) objects, this function can give you a "Fatal error:  Nesting level too deep" since it directly compares elements in later arrays if the elements in earlier ones compare equal. This can be worked around with the Flag-Parameter:
<?php
$sortKeys = array_map($extractKey, $lotsOfComplexObjects);
array_multisort($sortKeys, $lotsOfComplexObjects, SORT_ASC, SORT_NUMERIC);
?>
I'm replacing an 'uasort()'-call which is significantly slower since it leads to a lot of calls to the comparison-function but most of the objects involved are recursive.
If this 'trick' gives a wrong order,  you need a better key.`

[up](https://www.php.net/manual/vote-note.php?id=130470&page=function.array-multisort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130470&page=function.array-multisort&vote=down "Vote down!")

1


[**_seb at example dot net_**](https://www.php.net/manual/en/function.array-multisort.php#130470) [¶](https://www.php.net/manual/en/function.array-multisort.php#130470)

**1 month ago**

`Be aware with array_multisort() and array_column() when you don't want to sort all columns. The last arg ...$rest is used to sort too!
<?php
$data = [\
    ['id' => 5, 'name' => 'Marie'],\
    ['id' => 7, 'name' => 'Lisa'],\
    ['id' => 4, 'name' => 'Marie'],\
    ['id' => 3, 'name' => 'Jean'],\
    ['id' => 1, 'name' => 'Marie'],\
    ['id' => 2, 'name' => 'Jean'],\
];
array_multisort(
    array_column($data, 'name'), SORT_ASC, SORT_REGULAR,
    $data,
);
/*
We could guess :
3       Jean
2       Jean
7       Lisa
5      Marie
4      Marie
1      Marie
But the result is :
2       Jean
3       Jean
7       Lisa
1      Marie
4      Marie
5      Marie
... id column has been sorted too!
*/`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.array-multisort&repo=en&redirect=https://www.php.net/manual/en/function.array-multisort.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google