---
url: https://www.php.net/manual/en/function.current.php
scraped_at: 2025-10-20T02:59:24.506Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# current

(PHP 4, PHP 5, PHP 7, PHP 8)

current — Return the current element in an array

### Description [¶](https://www.php.net/manual/en/function.current.php\#refsect1-function.current-description)

**current**([array](https://www.php.net/manual/en/language.types.array.php)\|[object](https://www.php.net/manual/en/language.types.object.php) `$array`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

Every array has an internal pointer to its "current" element,
which is initialized to the first element inserted into the
array.


### Parameters [¶](https://www.php.net/manual/en/function.current.php\#refsect1-function.current-parameters)

`array`

The array.


### Return Values [¶](https://www.php.net/manual/en/function.current.php\#refsect1-function.current-returnvalues)

The **current()** function simply returns the
value of the array element that's currently being pointed to by the
internal pointer. It does not move the pointer in any way. If the
internal pointer points beyond the end of the elements list or the array is
empty, **current()** returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


**Warning**

This function may
return Boolean **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**, but may also return a non-Boolean value which
evaluates to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**. Please read the section on [Booleans](https://www.php.net/manual/en/language.types.boolean.php) for more
information. Use [the ===\\
operator](https://www.php.net/manual/en/language.operators.comparison.php) for testing the return value of this
function.

### Changelog [¶](https://www.php.net/manual/en/function.current.php\#refsect1-function.current-changelog)

| Version | Description |
| --- | --- |
| 8.1.0 | Calling this function on [object](https://www.php.net/manual/en/language.types.object.php)s is deprecated.<br> Either convert the [object](https://www.php.net/manual/en/language.types.object.php) to an [array](https://www.php.net/manual/en/language.types.array.php) using [get\_mangled\_object\_vars()](https://www.php.net/manual/en/function.get-mangled-object-vars.php) first, or use the methods<br> provided by a class that implements [Iterator](https://www.php.net/manual/en/class.iterator.php), such as [ArrayIterator](https://www.php.net/manual/en/class.arrayiterator.php), instead. |
| 7.4.0 | Instances of [SPL](https://www.php.net/manual/en/book.spl.php) classes are now treated like empty objects that have no properties instead of calling the [Iterator](https://www.php.net/manual/en/class.iterator.php) method with the same name as this function. |

### Examples [¶](https://www.php.net/manual/en/function.current.php\#refsect1-function.current-examples)

**Example #1 Example use of **current()** and friends**

`<?php
$transport = array('foot', 'bike', 'car', 'plane');
echo $mode = current($transport), PHP_EOL; // $mode = 'foot';
echo $mode = next($transport), PHP_EOL;    // $mode = 'bike';
echo $mode = current($transport), PHP_EOL; // $mode = 'bike';
echo $mode = prev($transport), PHP_EOL;    // $mode = 'foot';
echo $mode = end($transport), PHP_EOL;     // $mode = 'plane';
echo $mode = current($transport), PHP_EOL; // $mode = 'plane';
$arr = array();
var_dump(current($arr)); // bool(false)
$arr = array(array());
var_dump(current($arr)); // array(0) { }
?>`

Run code

### Notes [¶](https://www.php.net/manual/en/function.current.php\#refsect1-function.current-notes)

> **Note**:
>
> The results of calling **current()** on an empty array
> and on an array, whose internal pointer points beyond the end of the elements,
> are indistinguishable from a [bool](https://www.php.net/manual/en/language.types.boolean.php) **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** element.
> To properly traverse an array which may contain **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** elements, see the
> [`foreach`](https://www.php.net/manual/en/control-structures.foreach.php) control structure.
>
> To still use **current()** and properly check if the value
> is really an element of the array, the [key()](https://www.php.net/manual/en/function.key.php)
> of the **current()** element should be checked to be strictly
> different from **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**.

### See Also [¶](https://www.php.net/manual/en/function.current.php\#refsect1-function.current-seealso)

- [end()](https://www.php.net/manual/en/function.end.php) \- Set the internal pointer of an array to its last element
- [key()](https://www.php.net/manual/en/function.key.php) \- Fetch a key from an array
- [each()](https://www.php.net/manual/en/function.each.php) \- Return the current key and value pair from an array and advance the array cursor
- [prev()](https://www.php.net/manual/en/function.prev.php) \- Rewind the internal array pointer
- [reset()](https://www.php.net/manual/en/function.reset.php) \- Set the internal pointer of an array to its first element
- [next()](https://www.php.net/manual/en/function.next.php) \- Advance the internal pointer of an array
- [`foreach`](https://www.php.net/manual/en/control-structures.foreach.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/current.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.current%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.current&repo=en&redirect=https://www.php.net/manual/en/function.current.php)

### User Contributed Notes 11 notes

[up](https://www.php.net/manual/vote-note.php?id=107147&page=function.current&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107147&page=function.current&vote=down "Vote down!")

18


[**_michael at squiloople dot com_**](https://www.php.net/manual/en/function.current.php#107147) [¶](https://www.php.net/manual/en/function.current.php#107147)

**13 years ago**

`current() also works on objects:
<?php
echo current((object) array('one', 'two')); // Outputs: one
?>`

[up](https://www.php.net/manual/vote-note.php?id=126515&page=function.current&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126515&page=function.current&vote=down "Vote down!")

6


[**_sergey dot karavay at gmail dot com_**](https://www.php.net/manual/en/function.current.php#126515) [¶](https://www.php.net/manual/en/function.current.php#126515)

**4 years ago**

````It looks like `current()` is deprectated for calling on objects since PHP 7.4.
Consider this code
```
$a = new ArrayIterator([1,2,3]);
var_dump(current($a), $a->current());
```
It returns
```
int(1)
int(1)
```
In PHP 7.3, but in PHP7.4 you get:
```
bool(false)
int(1)
```
And in PHP8:
```
Deprecated: current(): Calling current() on an object is deprecated in /in/fdrNR on line 5
bool(false)
int(1)
``` ````

[up](https://www.php.net/manual/vote-note.php?id=77064&page=function.current&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77064&page=function.current&vote=down "Vote down!")

10


[**_vaclav dot sir at gmail dot com_**](https://www.php.net/manual/en/function.current.php#77064) [¶](https://www.php.net/manual/en/function.current.php#77064)

**18 years ago**

`To that "note": You won't be able to distinguish the end of an array from a boolean FALSE element, BUT you can distinguish the end from a NULL value of the key() function.
Example:
<?php
if (key($array) === null) {
    echo "You are in the end of the array.";
} else {
    echo "Current element: " . current($array);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=113561&page=function.current&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113561&page=function.current&vote=down "Vote down!")

7


[**_strate at yandex dot com_**](https://www.php.net/manual/en/function.current.php#113561) [¶](https://www.php.net/manual/en/function.current.php#113561)

**11 years ago**

`Note, that you can pass array by expression, not only by reference (as described in doc).
<?php
var_dump( current( array(1,2,3) ) ); // (int) 1
?>`

[up](https://www.php.net/manual/vote-note.php?id=29950&page=function.current&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=29950&page=function.current&vote=down "Vote down!")

8


[**_retestro\_REMOVE at SPAM\_esperanto dot org dot il_**](https://www.php.net/manual/en/function.current.php#29950) [¶](https://www.php.net/manual/en/function.current.php#29950)

**22 years ago**

`The docs do not specify this, but adding to the array using the brackets syntax:
     <?php $my_array[] = $new_value; ?>
will not advance the internal pointer of the array. therefore, you cannot use current() to get the last value added or key() to get the key of the most recently added element.
You should do an end($my_array) to advance the internal pointer to the end ( as stated in one of the notes on end() ), then
    <?php
     $last_key = key($my_array);  // will return the key
     $last_value = current($my_array);  // will return the value
    ?>
If you have no need in the key, $last_value = end($my_array) will also do the job.
- Sergey.`

[up](https://www.php.net/manual/vote-note.php?id=41864&page=function.current&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=41864&page=function.current&vote=down "Vote down!")

6


[**_mdeng at kabenresearch dot com_**](https://www.php.net/manual/en/function.current.php#41864) [¶](https://www.php.net/manual/en/function.current.php#41864)

**21 years ago**

`For large array(my sample was 80000+ elements), if you want to traverse the array in sequence, using array index $a[$i] could be very inefficient(very slow). I had to switch to use current($a).`

[up](https://www.php.net/manual/vote-note.php?id=122924&page=function.current&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122924&page=function.current&vote=down "Vote down!")

2


[**_xedin dot unknown at gmail dot com_**](https://www.php.net/manual/en/function.current.php#122924) [¶](https://www.php.net/manual/en/function.current.php#122924)

**7 years ago**

``Array functions, such as `current()` and `rewind()` will work on `Traversable` as well, PHP 5.0 - 7.3, but not in HHVM:
<?php
$queue = new ArrayIterator(array('adasdasd'));
reset($queue);
$current = current($queue);
var_dump($current);
?>
See [https://3v4l.org/VjCHR](https://3v4l.org/VjCHR)``

[up](https://www.php.net/manual/vote-note.php?id=116128&page=function.current&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116128&page=function.current&vote=down "Vote down!")

5


[**_Vasily Yudin (st-2 at mail dot ru)_**](https://www.php.net/manual/en/function.current.php#116128) [¶](https://www.php.net/manual/en/function.current.php#116128)

**10 years ago**

`If you do current() after using uset() on foreach statement, you can get FALSE in PHP version 5.2.4 and above.
There is example:
<?php
$prices = array(
    0 => '1300990',
    1 => '500',
    2 => '600'
);
foreach($prices as $key => $price){
    if($price < 1000){
        unset($prices[$key]);
    }
}
var_dump(current($prices)); // bool(false)
?>
If you do unset() without foreach? all will be fine.
<?php
$prices = array(
    0 => '1300990',
    1 => '500',
    2 => '600'
);
unset($prices[1]);
unset($prices[2]);
var_dump(current($prices));
?>`

[up](https://www.php.net/manual/vote-note.php?id=37917&page=function.current&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=37917&page=function.current&vote=down "Vote down!")

1


[**_vitalib at 012 dot net dot il_**](https://www.php.net/manual/en/function.current.php#37917) [¶](https://www.php.net/manual/en/function.current.php#37917)

**21 years ago**

`Note that by copying an array its internal pointer is lost:
<?php
$myarray = array(0=>'a', 1=>'b', 2=>'c');
next($myarray);
print_r(current($myarray));
echo '<br>';
$a = $myarray;
print_r(current($a));
?>
Would output 'b' and then 'a' since the internal pointer wasn't copied. You can cope with that problem using references instead, like that:
<?php
$a =& $myarray;
?>`

[up](https://www.php.net/manual/vote-note.php?id=124228&page=function.current&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124228&page=function.current&vote=down "Vote down!")

0


[**_leozmm at outlook dot com_**](https://www.php.net/manual/en/function.current.php#124228) [¶](https://www.php.net/manual/en/function.current.php#124228)

**6 years ago**

``Array can be passed by both REFERENCE and EXPRESSION on `current`, because current doesn't move array's internal pointer,
this is not true for other functions like: `end`, `next`, `prev` etc.
<?php
    function foo() {return array(1,2,3);}
    echo current(foo());  // this print '1'
    echo end(foo());      // this print error: Only variables should be passed by reference
?>``

[up](https://www.php.net/manual/vote-note.php?id=121483&page=function.current&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121483&page=function.current&vote=down "Vote down!")

0


[**_pdarmis at gmail dot com_**](https://www.php.net/manual/en/function.current.php#121483) [¶](https://www.php.net/manual/en/function.current.php#121483)

**8 years ago**

`Based on this example [http://php.net/manual/en/function.current.php#116128](http://php.net/manual/en/function.current.php#116128) i would like to add the following.  As Vasily points out in his example
<?php
$prices = array(
    0 => '1300990',
    1 => '500',
    2 => '600'
);
foreach($prices as $key => $price){
    if($price < 1000){
        unset($prices[$key]);
    }
}
var_dump(current($prices)); // bool(false)
?>
The above example will not work and return false for version of PHP between 5.2.4 and 5.6.29. The issue is not present on PHP versions >= 7.0.1
A different workaround (at least from Vasily's example) would be to use reset() before using current() in order to reset the array pointer to start.
<?php
$prices = array(
    0 => '1300990',
    1 => '500',
    2 => '600'
);
foreach($prices as $key => $price){
    if($price < 1000){
        unset($prices[$key]);
    }
}
reset($prices);
var_dump(current($prices)); // string(7) "1300990"
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.current&repo=en&redirect=https://www.php.net/manual/en/function.current.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google