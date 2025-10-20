---
url: https://www.php.net/manual/en/function.usort.php
scraped_at: 2025-10-20T02:38:05.378Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# usort

(PHP 4, PHP 5, PHP 7, PHP 8)

usort — Sort an array by values using a user-defined comparison function

### Description [¶](https://www.php.net/manual/en/function.usort.php\#refsect1-function.usort-description)

**usort**([array](https://www.php.net/manual/en/language.types.array.php) `&$array`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [true](https://www.php.net/manual/en/language.types.singleton.php)

Sorts `array` in place by values using a
user-supplied comparison function to determine the order.


> **Note**:
>
>
> If two members compare as equal, they retain their original order.
> Prior to PHP 8.0.0, their relative order in the sorted array was undefined.

> **Note**: This function
> assigns new keys to the elements in `array`.
> It will remove any existing keys that may have been assigned, rather
> than just reordering the keys.

### Parameters [¶](https://www.php.net/manual/en/function.usort.php\#refsect1-function.usort-parameters)

`array`

The input array.


`callback`

The comparison function must return an integer less than, equal to, or greater than zero if the first argument is considered to be respectively less than, equal to, or greater than the second.

callback([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$a`, [mixed](https://www.php.net/manual/en/language.types.mixed.php) `$b`): [int](https://www.php.net/manual/en/language.types.integer.php)

**Caution**

Returning _non-integer_ values from the comparison
function, such as [float](https://www.php.net/manual/en/language.types.float.php), will result in an internal cast to
[int](https://www.php.net/manual/en/language.types.integer.php) of the callback's return value. So values such as
`0.99` and `0.1` will both be cast to an
integer value of `0`, which will compare such values as equal.


### Return Values [¶](https://www.php.net/manual/en/function.usort.php\#refsect1-function.usort-returnvalues)

Always returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.


### Changelog [¶](https://www.php.net/manual/en/function.usort.php\#refsect1-function.usort-changelog)

| Version | Description |
| --- | --- |
| 8.2.0 | The return type is **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** now; previously, it was [bool](https://www.php.net/manual/en/language.types.boolean.php). |
| 8.0.0 | If `callback` expects a parameter to be passed<br> by reference, this function will now emit an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**. |

### Examples [¶](https://www.php.net/manual/en/function.usort.php\#refsect1-function.usort-examples)

**Example #1 **usort()** example**

`<?php
function cmp($a, $b)
{
    if ($a == $b) {
        return 0;
    }
    return ($a < $b) ? -1 : 1;
}
$a = array(3, 2, 5, 6, 1);
usort($a, "cmp");
foreach ($a as $key => $value) {
    echo "$key: $value\n";
}
?>`

Run code

The above example will output:

```
0: 1
1: 2
2: 3
3: 5
4: 6
```

The spaceship operator may be used to
simplify the internal comparison even further.


`<?php
function cmp($a, $b)
{
    return $a <=> $b;
}
$a = array(3, 2, 5, 6, 1);
usort($a, "cmp");
foreach ($a as $key => $value) {
    echo "$key: $value\n";
}
?>`

Run code

> **Note**:
>
>
> Obviously in this trivial case the [sort()](https://www.php.net/manual/en/function.sort.php)
> function would be more appropriate.

**Example #2**
****usort()** example using multi-dimensional array**

`<?php
function cmp($a, $b)
{
    return strcmp($a["fruit"], $b["fruit"]);
}
$fruits[0]["fruit"] = "lemons";
$fruits[1]["fruit"] = "apples";
$fruits[2]["fruit"] = "grapes";
usort($fruits, "cmp");
foreach ($fruits as $key => $value) {
    echo "\$fruits[$key]: " . $value["fruit"] . "\n";
}
?>`

Run code

The above example will output:

```
$fruits[0]: apples
$fruits[1]: grapes
$fruits[2]: lemons
```

When sorting a multi-dimensional array, $a and
$b contain references to the first index of the array.


**Example #3**
****usort()** example using a member function of an object**

`<?php
class TestObj {
    public string $name;
    function __construct($name)
    {
        $this->name = $name;
    }
    /* This is the static comparing function: */
    static function cmp_obj($a, $b)
    {
        return strtolower($a->name) <=> strtolower($b->name);
    }
}
$a[] = new TestObj("c");
$a[] = new TestObj("b");
$a[] = new TestObj("d");
usort($a, [TestObj::class, "cmp_obj"]);
foreach ($a as $item) {
    echo $item->name . "\n";
}
?>`

Run code

The above example will output:

```
b
c
d
```

**Example #4**
****usort()** example using a [closure](https://www.php.net/manual/en/functions.anonymous.php)**
**to sort a multi-dimensional array**

`<?php
$array[0] = array('key_a' => 'z', 'key_b' => 'c');
$array[1] = array('key_a' => 'x', 'key_b' => 'b');
$array[2] = array('key_a' => 'y', 'key_b' => 'a');
function build_sorter($key) {
    return function ($a, $b) use ($key) {
        return strnatcmp($a[$key], $b[$key]);
    };
}
usort($array, build_sorter('key_b'));
foreach ($array as $item) {
    echo $item['key_a'] . ', ' . $item['key_b'] . "\n";
}
?>`

Run code

The above example will output:

```
y, a
x, b
z, c
```

**Example #5**
****usort()** example using the spaceship operator**

The spaceship operator allows for straightforward comparison of
compound values across multiple axes. The following example will sort
`$people` by last name, then by first name if the
last name matches.


`<?php
$people[0] = ['first' => 'Adam', 'last' => 'West'];
$people[1] = ['first' => 'Alec', 'last' => 'Baldwin'];
$people[2] = ['first' => 'Adam', 'last' => 'Baldwin'];
function sorter(array $a, array $b) {
    return [$a['last'], $a['first']] <=> [$b['last'], $b['first']];
}
usort($people, 'sorter');
foreach ($people as $person) {
    print $person['last'] . ', ' . $person['first'] . PHP_EOL;
}
?>`

Run code

The above example will output:

```
Baldwin, Adam
Baldwin, Alec
West, Adam
```

### See Also [¶](https://www.php.net/manual/en/function.usort.php\#refsect1-function.usort-seealso)

- [uasort()](https://www.php.net/manual/en/function.uasort.php) \- Sort an array with a user-defined comparison function and maintain index association
- [uksort()](https://www.php.net/manual/en/function.uksort.php) \- Sort an array by keys using a user-defined comparison function
- The [comparison of array sorting functions](https://www.php.net/manual/en/array.sorting.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/usort.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.usort%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.usort&repo=en&redirect=https://www.php.net/manual/en/function.usort.php)

### User Contributed Notes 11 notes

[up](https://www.php.net/manual/vote-note.php?id=111883&page=function.usort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111883&page=function.usort&vote=down "Vote down!")

23


[**_Hayley Watson_**](https://www.php.net/manual/en/function.usort.php#111883) [¶](https://www.php.net/manual/en/function.usort.php#111883)

**12 years ago**

`As the documentation says, the comparison function needs to return an integer that is either "less than, equal to, or greater than zero". There is no requirement to restrict the value returned to -1, 0, 1.
<?php
usort($array, function($a, $b) {
    if($a->integer_property > $b->integer_property) {
        return 1;
    }
    elseif($a->integer_property < $b->integer_property) {
        return -1;
    }
    else {
        return 0;
    }
});
?>
can be simplified to
<?php
usort($array, function($a, $b) {
    return $a->integer_property - $b->integer_property;
});
?>
This of course applies to any comparison function that calculates an integer "score" for each of its arguments to decide which is "greater".`

[up](https://www.php.net/manual/vote-note.php?id=89919&page=function.usort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=89919&page=function.usort&vote=down "Vote down!")

12


[**_luke dot semerau at gmail dot com_**](https://www.php.net/manual/en/function.usort.php#89919) [¶](https://www.php.net/manual/en/function.usort.php#89919)

**16 years ago**

`If you need to use usort with a key in the calling method, I wrote this as a utility:
<?php
function usort_comparison($obj, $method, $key) {
    $usorter = &new Usort($obj, $method, $key);
    return array($usorter, "sort");
}
class Usort {
    function __construct($obj, $method, $key) {
        $this->obj = $obj;
        $this->method = $method;
        $this->key = $key;
    }
    function sort($a, $b) {
        return call_user_func_array(array($this->obj, $this->method), array($a, $b, $this->key));
    }
}
?>
<?php
require_once("util/usort.php");
class Foo {
    $items = array(FooBar(13), FooBar(2));
    public function sorter() {
        usort($this-items, usort_comparison("Foo", "_cmp", "item"));
    }
    public static function _cmp($a, $b, $key) {
         return strcasecmp($a->$key, $b->$key);
    }
}
class FooBar {
    public $item;
    function __construct($val) {
        $this->item = $val;
    }
}
?>
~ simple example... but in the way I need to use it was the key was used in a switch statement to choose the different member of the object to compare against dynamically (as in, sort by x or y or z)`

[up](https://www.php.net/manual/vote-note.php?id=25360&page=function.usort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=25360&page=function.usort&vote=down "Vote down!")

15


[**_mkr at binarywerks dot dk_**](https://www.php.net/manual/en/function.usort.php#25360) [¶](https://www.php.net/manual/en/function.usort.php#25360)

**23 years ago**

`If you want to sort an array according to another array acting as a priority list, you can use this function.
<?php
function listcmp($a, $b)
{
global $order;
foreach($order as $key => $value)
    {
      if($a==$value)
        {
          return 0;
          break;
        }
      if($b==$value)
        {
          return 1;
          break;
        }
    }
}
$order[0] = "first";
$order[1] = "second";
$order[2] = "third";
$array[0] = "second";
$array[1] = "first";
$array[2] = "third";
$array[3] = "fourth";
$array[4] = "second";
$array[5] = "first";
$array[6] = "second";
usort($array, "listcmp");
print_r($array);
?>`

[up](https://www.php.net/manual/vote-note.php?id=8587&page=function.usort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=8587&page=function.usort&vote=down "Vote down!")

9


[**_derek at luddite dot net_**](https://www.php.net/manual/en/function.usort.php#8587) [¶](https://www.php.net/manual/en/function.usort.php#8587)

**25 years ago**

`Needed a date sort and I didn't know if one was available so I wrote one. Maybe it'll help someone:
<?php
function DateSort($a,$b,$d="-") {
    if ($a == $b) {
        return 0;
    } else {  //Convert into dates and compare
        list($am,$ad,$ay)=split($d,$a);
        list($bm,$bd,$by)=split($d,$b);
        if (mktime(0,0,0,$am,$ad,$ay) < mktime(0,0,0,$bm,$bd,$by)) {
            return -1;
        } else {
            return 1;
        }
    }
}
?>
$d is the delimeter`

[up](https://www.php.net/manual/vote-note.php?id=60777&page=function.usort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60777&page=function.usort&vote=down "Vote down!")

5


[**_sydney at totoche dot org_**](https://www.php.net/manual/en/function.usort.php#60777) [¶](https://www.php.net/manual/en/function.usort.php#60777)

**19 years ago**

`Instead of doing  :
<?php $strc = strcmp( strtolower($a[$f]), strtolower($b[$f]) ); ?>
you could do this :
<?php $strc = strcasecmp( $a[$f], $b[$f] ); ?>
which is more efficient and is does case insensitive comparison according to the current locale.`

[up](https://www.php.net/manual/vote-note.php?id=123923&page=function.usort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123923&page=function.usort&vote=down "Vote down!")

2


[**_gus dot antoniassi at gmail dot com_**](https://www.php.net/manual/en/function.usort.php#123923) [¶](https://www.php.net/manual/en/function.usort.php#123923)

**6 years ago**

`This is a simple way to sort based on a "priority list":
<?php
$order = [1,3,0,2];
$arr =   [\
    [ 'id' => 0 ],\
    [ 'id' => 1 ],\
    [ 'id' => 2 ],\
    [ 'id' => 3 ],\
];
uasort(
    $arr,
    function ($a, $b) use ($order) {
        return array_search($a['id'], $order) <=> array_search($b['id'], $order);
    }
);
print_r($arr);
?>
This will return:
Array
(
    [1] => Array
        (
            [id] => 1
        )
    [3] => Array
        (
            [id] => 3
        )
    [0] => Array
        (
            [id] => 0
        )
    [2] => Array
        (
            [id] => 2
        )
)
Note that if you have a value in $arr that is not on the $order list, you will need additional checks since the array_search function returns FALSE for undefined indexes.`

[up](https://www.php.net/manual/vote-note.php?id=120470&page=function.usort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120470&page=function.usort&vote=down "Vote down!")

5


[**_inigo dot grimbergen at gmail dot com_**](https://www.php.net/manual/en/function.usort.php#120470) [¶](https://www.php.net/manual/en/function.usort.php#120470)

**8 years ago**

`to sort with numeric and empty values  and have the smallest on top:
<?php
    usort($list, function($a, $b) {
        if( $a == null && $b != null ) return 1;
        if( $a != null && $b == null ) return -1;
        return $a > $b ? 1 : -1;
    });
?>
returns
1
2
3
null
null
null`

[up](https://www.php.net/manual/vote-note.php?id=123532&page=function.usort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123532&page=function.usort&vote=down "Vote down!")

1


[**_chris at candm dot org dot uk_**](https://www.php.net/manual/en/function.usort.php#123532) [¶](https://www.php.net/manual/en/function.usort.php#123532)

**6 years ago**

`In case anyone is interested, comparative timings over 100000000 runs
Based on comparing integers (500 and 501)
Spaceship:4
()?: operator:10
Subtraction:2
Based on comparing floats (500.1 and 501.3) (caveats noted)
Spaceship:5
()?: operator:9
Subtraction:3
Based on comparing strings ("five" and "four")
Spaceship:7
()?: operator:17
(Subtraction obviously not available)
Note: a dummy run was done with an empty loop and the elapsed time for this was subtracted from each of the above times so that they reflect ONLY the time to do the comparisons. As for significance. unless you are doing very large numbers of comparisons where spaceships are the order of the day, the difference is insignificant.`

[up](https://www.php.net/manual/vote-note.php?id=12047&page=function.usort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=12047&page=function.usort&vote=down "Vote down!")

2


[**_bo at erichsen dot com_**](https://www.php.net/manual/en/function.usort.php#12047) [¶](https://www.php.net/manual/en/function.usort.php#12047)

**24 years ago**

`when using usort to refer to a function inside a class i have succesfully used:
<?php usort($myarray,array($this,"cmp")); ?>`

[up](https://www.php.net/manual/vote-note.php?id=107372&page=function.usort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107372&page=function.usort&vote=down "Vote down!")

1


[**_andi\_mclean at ntlworld dot com_**](https://www.php.net/manual/en/function.usort.php#107372) [¶](https://www.php.net/manual/en/function.usort.php#107372)

**13 years ago**

`I needed a sort method that would sort strings but take note of any numbers and would compare them as number. I also want to ignore any non alphanumerical characters.
Eg.
Slot 1 Example
Slot 10 Example
Slot 2 Example
Should infact be
Slot 1 Example
Slot 2 Example
Slot 10 Example
<?php
function sort_with_numbers($a , $b) {
    $a = explode(' ',$a);
    $b = explode(' ',$b);
    $size = min(count($a), count($b));
    for($index =0; $index < $size; ++$index) {
        $a1 = ereg_replace("[^A-Za-z0-9]", "",$a[$index]);
        $b1 = ereg_replace("[^A-Za-z0-9]", "",$b[$index]);
        $equal = 0;
        if (is_numeric($a1) && is_numeric($b1)) {
            $equal = $a1 - $b1;
        } else {
            $equal = strcasecmp($a1,$b1);
        }
        if ($equal < 0) {
            return -1;
        }
        if ($equal > 0) {
            return 1;
        }
    }
    return count($a) - count($b);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=129697&page=function.usort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129697&page=function.usort&vote=down "Vote down!")

1


[**_rh at 20i dot com_**](https://www.php.net/manual/en/function.usort.php#129697) [¶](https://www.php.net/manual/en/function.usort.php#129697)

**1 year ago**

````A sort function to sort elements by a reference order.
function sort_by_reference(array $array_to_sort, array $reference_array): array {
    usort($array_to_sort, function($a, $b) use ($reference_array) {
        $pos_a = array_search($a, $reference_array);
        $pos_b = array_search($b, $reference_array);
        return $pos_a - $pos_b;
    });
    return $array_to_sort;
}
// Example usage
$reference_array = ["one", "two", "three", "four", "five", "six", "seven", "eight", "nine", "ten"];
$array_to_sort = ["three", "one", "seven", "four", "ten"];
$sorted_array = sort_by_reference($array_to_sort, $reference_array);
// Print the result to verify the sorting
print_r($sorted_array);
```
Array
(
    [0] => one
    [1] => three
    [2] => four
    [3] => seven
    [4] => ten
)
``` ````

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.usort&repo=en&redirect=https://www.php.net/manual/en/function.usort.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google