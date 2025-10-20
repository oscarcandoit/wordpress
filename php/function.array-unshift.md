---
url: https://www.php.net/manual/en/function.array-unshift.php
scraped_at: 2025-10-20T02:53:13.628Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# array\_unshift

(PHP 4, PHP 5, PHP 7, PHP 8)

array\_unshift — Prepend one or more elements to the beginning of an array

### Description [¶](https://www.php.net/manual/en/function.array-unshift.php\#refsect1-function.array-unshift-description)

**array\_unshift**([array](https://www.php.net/manual/en/language.types.array.php) `&$array`, [mixed](https://www.php.net/manual/en/language.types.mixed.php) `...$values`): [int](https://www.php.net/manual/en/language.types.integer.php)

**array\_unshift()** prepends passed elements to the front
of the `array`. Note that the list of elements is
prepended as a whole, so that the prepended elements stay in the same
order. All numerical array keys will be modified to start counting from
zero while literal keys won't be changed.


> **Note**:
>
>
> Resets array's internal pointer to the first element.

### Parameters [¶](https://www.php.net/manual/en/function.array-unshift.php\#refsect1-function.array-unshift-parameters)

`array`

The input array.


`values`

The values to prepend.


### Return Values [¶](https://www.php.net/manual/en/function.array-unshift.php\#refsect1-function.array-unshift-returnvalues)

Returns the new number of elements in the `array`.


### Changelog [¶](https://www.php.net/manual/en/function.array-unshift.php\#refsect1-function.array-unshift-changelog)

| Version | Description |
| --- | --- |
| 7.3.0 | This function can now be called with only one parameter. Formerly, at<br> least two parameters have been required. |

### Examples [¶](https://www.php.net/manual/en/function.array-unshift.php\#refsect1-function.array-unshift-examples)

**Example #1 **array\_unshift()** example**

`<?php
$queue = [\
    "orange",\
    "banana"\
];
array_unshift($queue, "apple", "raspberry");
var_dump($queue);
?>`

Run code

The above example will output:

```
array(4) {
  [0] =>
  string(5) "apple"
  [1] =>
  string(9) "raspberry"
  [2] =>
  string(6) "orange"
  [3] =>
  string(6) "banana"
}
```

**Example #2 Usage with associative arrays**

If one associative array is prepended to another associative array,
the prepended array is numerically indexed into the former array.


`<?php
$foods = [\
    'apples' => [\
        'McIntosh' => 'red',\
        'Granny Smith' => 'green',\
    ],\
    'oranges' => [\
        'Navel' => 'orange',\
        'Valencia' => 'orange',\
    ],\
];
$vegetables = [\
    'lettuce' => [\
        'Iceberg' => 'green',\
        'Butterhead' => 'green',\
    ],\
    'carrots' => [\
        'Deep Purple Hybrid' => 'purple',\
        'Imperator' => 'orange',\
    ],\
    'cucumber' => [\
        'Kirby' => 'green',\
        'Gherkin' => 'green',\
    ],\
];
array_unshift($foods, $vegetables);
var_dump($foods);
?>`

Run code

The above example will output:

```
array(3) {
  [0]=>
  array(3) {
    ["lettuce"]=>
    array(2) {
      ["Iceberg"]=>
      string(5) "green"
      ["Butterhead"]=>
      string(5) "green"
    }
    ["carrots"]=>
    array(2) {
      ["Deep Purple Hybrid"]=>
      string(6) "purple"
      ["Imperator"]=>
      string(6) "orange"
    }
    ["cucumber"]=>
    array(2) {
      ["Kirby"]=>
      string(5) "green"
      ["Gherkin"]=>
      string(5) "green"
    }
  }
  ["apples"]=>
  array(2) {
    ["McIntosh"]=>
    string(3) "red"
    ["Granny Smith"]=>
    string(5) "green"
  }
  ["oranges"]=>
  array(2) {
    ["Navel"]=>
    string(6) "orange"
    ["Valencia"]=>
    string(6) "orange"
  }
}
```

### See Also [¶](https://www.php.net/manual/en/function.array-unshift.php\#refsect1-function.array-unshift-seealso)

- [array\_merge()](https://www.php.net/manual/en/function.array-merge.php) \- Merge one or more arrays
- [array\_shift()](https://www.php.net/manual/en/function.array-shift.php) \- Shift an element off the beginning of array
- [array\_push()](https://www.php.net/manual/en/function.array-push.php) \- Push one or more elements onto the end of array
- [array\_pop()](https://www.php.net/manual/en/function.array-pop.php) \- Pop the element off the end of array

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/array-unshift.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.array-unshift%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.array-unshift&repo=en&redirect=https://www.php.net/manual/en/function.array-unshift.php)

### User Contributed Notes 12 notes

[up](https://www.php.net/manual/vote-note.php?id=78238&page=function.array-unshift&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78238&page=function.array-unshift&vote=down "Vote down!")

210


[**_sergei at gmx dot net_**](https://www.php.net/manual/en/function.array-unshift.php#78238) [¶](https://www.php.net/manual/en/function.array-unshift.php#78238)

**18 years ago**

`You can preserve keys and unshift an array with numerical indexes in a really simple way if you'll do the following:
<?php
$someArray=array(224=>'someword1', 228=>'someword2', 102=>'someword3', 544=>'someword3',95=>'someword4');
$someArray=array(100=>'Test Element 1 ',255=>'Test Element 2')+$someArray;
?>
now the array looks as follows:
array(
100=>'Test Element 1 ',
255=>'Test Element 2'
224=>'someword1',
228=>'someword2',
102=>'someword3',
544=>'someword3',
95=>'someword4'
);`

[up](https://www.php.net/manual/vote-note.php?id=23882&page=function.array-unshift&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=23882&page=function.array-unshift&vote=down "Vote down!")

37


[**_rsmith\_NOSPAM\_ at \_NOSPAM\_unitec dot ac dot nz_**](https://www.php.net/manual/en/function.array-unshift.php#23882) [¶](https://www.php.net/manual/en/function.array-unshift.php#23882)

**23 years ago**

`array_merge() will also reindex (see array_merge() manual entry), but the '+' operator won't, so...
<?php
$arrayone=array("newkey"=>"newvalue") + $arrayone;
?>
does the job.`

[up](https://www.php.net/manual/vote-note.php?id=106570&page=function.array-unshift&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106570&page=function.array-unshift&vote=down "Vote down!")

35


[**_Anonymous_**](https://www.php.net/manual/en/function.array-unshift.php#106570) [¶](https://www.php.net/manual/en/function.array-unshift.php#106570)

**13 years ago**

`Sahn's example almost works but has a small error. Try it like this if you need to prepend something to the array without the keys being reindexed and/or need to prepend a key value pair, you can use this short function:
<?php
function array_unshift_assoc(&$arr, $key, $val)
{
    $arr = array_reverse($arr, true);
    $arr[$key] = $val;
    return = array_reverse($arr, true);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=117119&page=function.array-unshift&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117119&page=function.array-unshift&vote=down "Vote down!")

10


[**_daniel at smallboxcms dot com_**](https://www.php.net/manual/en/function.array-unshift.php#117119) [¶](https://www.php.net/manual/en/function.array-unshift.php#117119)

**10 years ago**

`Anonymous' associative version wasn't working for me, but it did with this small tweak:
function array_unshift_assoc(&$arr, $key, $val)
{
    $arr = array_reverse($arr, true);
    $arr[$key] = $val;
    $arr = array_reverse($arr, true);
    return $arr;
}`

[up](https://www.php.net/manual/vote-note.php?id=74129&page=function.array-unshift&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74129&page=function.array-unshift&vote=down "Vote down!")

2


[**_amschroeder at gmail dot com_**](https://www.php.net/manual/en/function.array-unshift.php#74129) [¶](https://www.php.net/manual/en/function.array-unshift.php#74129)

**18 years ago**

`This becomes a nice little problem if you index your arrays out of order (while manually sorting).  For example:
<?php
$recordMonths[3] = '8/%/2006';
$recordMonths[4] = '7/%/2004';
$recordMonths[0] = '3/%/2007';
$recordMonths[1] = '2/%/2007';
$recordMonths[5] = '12/%/2000';
$recordMonths[6] = '11/%/2000';
$recordMonths[7] = '10/%/2000';
$recordMonths[2] = '1/%/2007';
for($i = 0; $i < count($recordMonths); $i++)
{
    $singleMonth = $recordMonths[$i];
    echo "singleMonth: $singleMonth <br />";
}
array_unshift($recordMonths,'%');
for($i = 0; $i < count($recordMonths); $i++)
{
    $singleMonth = $recordMonths[$i];
    echo "singleMonth: $singleMonth <br />";
}
?>
Produces:
singleMonth: 3/%/2007
singleMonth: 2/%/2007
singleMonth: 1/%/2007
singleMonth: 8/%/2006
singleMonth: 7/%/2004
singleMonth: 12/%/2000
singleMonth: 11/%/2000
singleMonth: 10/%/2000
singleMonth: %
singleMonth: 8/%/2006
singleMonth: 7/%/2004
singleMonth: 3/%/2007
singleMonth: 2/%/2007
singleMonth: 12/%/2000
singleMonth: 11/%/2000
singleMonth: 10/%/2000
singleMonth: 1/%/2007
It reindexes them based on the order they were created.  It seems like if an array has all numeric indexes, then it should reindex them based on the order of their index.  Just my opinion...`

[up](https://www.php.net/manual/vote-note.php?id=40270&page=function.array-unshift&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=40270&page=function.array-unshift&vote=down "Vote down!")

2


[**_php at electricsurfer dot com_**](https://www.php.net/manual/en/function.array-unshift.php#40270) [¶](https://www.php.net/manual/en/function.array-unshift.php#40270)

**21 years ago**

`even simpler unshifting of a reference !
<?php
/**
* @return int
* @param $array array
* @param $value mixed
* @desc Prepend a reference to an element to the beginning of an array. Renumbers numeric keys, so $value is always inserted to $array[0]
*/
function array_unshift_ref(&$array, &$value)
{
$return = array_unshift($array,'');
$array[0] =& $value;
return $return;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=18847&page=function.array-unshift&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=18847&page=function.array-unshift&vote=down "Vote down!")

2


[**_robert dot wills at fuzzbrain dot uklinux dot net_**](https://www.php.net/manual/en/function.array-unshift.php#18847) [¶](https://www.php.net/manual/en/function.array-unshift.php#18847)

**23 years ago**

`Actually this problem with the keys getting reindexed only happens when the keys are numerical:
<?php
$a = array("f"=>"five", "s" =>"six", "t" =>
        "twenty");
print_r($a);
echo "\n";
foreach($a as $key=>$val)
{
    echo "k: $key v: $val \n";
}
array_unshift($a, "zero");
print_r($a);
echo "\n";
foreach($a as $key=>$val)
{
    echo "k: $key v: $val \n";
}
?>
Array
(
    [f] => five
    [s] => six
    [t] => twenty
)
k: f v: five
k: s v: six
k: t v: twenty
Array
(
    [0] => zero
    [f] => five
    [s] => six
    [t] => twenty
)
k: 0 v: zero
k: f v: five
k: s v: six
k: t v: twenty`

[up](https://www.php.net/manual/vote-note.php?id=129005&page=function.array-unshift&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129005&page=function.array-unshift&vote=down "Vote down!")

 -1


[**_eliasritter168667 at gmail dot com_**](https://www.php.net/manual/en/function.array-unshift.php#129005) [¶](https://www.php.net/manual/en/function.array-unshift.php#129005)

**1 year ago**

`This function helps if you want to prepend a key and value pair to the beginning of an array:
function array_kunshift(array $array, string|int $key, mixed $value): array {
        return array_merge([$key => $value], $array);
    }`

[up](https://www.php.net/manual/vote-note.php?id=119009&page=function.array-unshift&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119009&page=function.array-unshift&vote=down "Vote down!")

0


[**_Richard Akindele_**](https://www.php.net/manual/en/function.array-unshift.php#119009) [¶](https://www.php.net/manual/en/function.array-unshift.php#119009)

**9 years ago**

`Another way to tack something to the beginning of an array is with array_merge().
$plans = array('AARP'=>'Senior', 'AAA'=>'Automobile Club');
$plans = array_merge(array("BAR"=>"Best Available Rate"),  $plans);`

[up](https://www.php.net/manual/vote-note.php?id=34308&page=function.array-unshift&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=34308&page=function.array-unshift&vote=down "Vote down!")

 -1


[**_chris dot NoThxSpam dot given at hp dot com_**](https://www.php.net/manual/en/function.array-unshift.php#34308) [¶](https://www.php.net/manual/en/function.array-unshift.php#34308)

**22 years ago**

`If you need to change the name of a key without changing its position in the array this function may be useful.
<?php
function array_key_change($Old, $New, $In, $NewVal=NULL) {
        $Temp = array();
        while(isset($Temp[$Old]) == false) {
                list($k, $v) = each($In);
                $Temp[$k] = $v;
                unset($In[$k]);
        }
        if($NewVal == NULL) {
                $NewVal = $Temp[$Old];
        }
        unset($Temp[$Old]);
        $Temp = array_reverse($Temp);
        $In = array_merge(array($New=>$NewVal), $In);
        while(list($k,$v) = each($Temp)) {
                $In = array_merge(array($k=>$v), $In);
        }
        return($In);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=14358&page=function.array-unshift&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=14358&page=function.array-unshift&vote=down "Vote down!")

 -3


[**_sahn at hmc dot edu_**](https://www.php.net/manual/en/function.array-unshift.php#14358) [¶](https://www.php.net/manual/en/function.array-unshift.php#14358)

**24 years ago**

`If you need to prepend something to the array without the keys being reindexed and/or need to prepend a key value pair, you can use this short function:
<?php
function array_unshift_assoc(&$arr, $key, $val)
{
    $arr = array_reverse($arr, true);
    $arr[$key] = $val;
    $arr = array_reverse($arr, true);
    return count($arr);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=67085&page=function.array-unshift&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=67085&page=function.array-unshift&vote=down "Vote down!")

 -5


[**_John Brooking_**](https://www.php.net/manual/en/function.array-unshift.php#67085) [¶](https://www.php.net/manual/en/function.array-unshift.php#67085)

**19 years ago**

`I had a need tonight to convert a numeric array from 1-based to 0-based, and found that the following worked just fine due to the "side effect" of renumbering:
<?php
array_unshift( $myArray, array_shift( $myArray ));
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.array-unshift&repo=en&redirect=https://www.php.net/manual/en/function.array-unshift.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google