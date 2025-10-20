---
url: https://www.php.net/manual/en/function.array-slice.php
scraped_at: 2025-10-20T02:54:04.282Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# array\_slice

(PHP 4, PHP 5, PHP 7, PHP 8)

array\_slice — Extract a slice of the array

### Description [¶](https://www.php.net/manual/en/function.array-slice.php\#refsect1-function.array-slice-description)

**array\_slice**(

[array](https://www.php.net/manual/en/language.types.array.php) `$array`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$offset`,

[?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$length` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$preserve_keys` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**

): [array](https://www.php.net/manual/en/language.types.array.php)

**array\_slice()** returns the sequence of elements
from the array `array` as specified by the
`offset` and `length`
parameters.


### Parameters [¶](https://www.php.net/manual/en/function.array-slice.php\#refsect1-function.array-slice-parameters)

`array`

The input array.


`offset`

If `offset` is non-negative, the sequence will
start at that offset in the `array`.


If `offset` is negative, the sequence will
start that far from the end of the `array`.


> **Note**:
>
>
> The `offset` parameter denotes the position
> in the array, not the key.

`length`

If `length` is given and is positive,
then the sequence will have up to that many elements in it.


If the array is shorter than the `length`,
then only the available array elements will be present.


If `length` is given and is negative then the
sequence will stop that many elements from the end of the array.


If it is omitted, then the sequence will have everything
from `offset` up until the end of the
`array`.


`preserve_keys`

> **Note**:
>
>
> **array\_slice()** will reorder and reset the
> integer array indices by default. This behaviour can be changed
> by setting `preserve_keys` to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.
> String keys are always preserved, regardless of this parameter.

### Return Values [¶](https://www.php.net/manual/en/function.array-slice.php\#refsect1-function.array-slice-returnvalues)

Returns the slice. If the offset is larger than the size of the array,
an empty array is returned.


### Examples [¶](https://www.php.net/manual/en/function.array-slice.php\#refsect1-function.array-slice-examples)

**Example #1 **array\_slice()** examples**

`<?php
$input = array("a", "b", "c", "d", "e");
$output = array_slice($input, 2);      // returns "c", "d", and "e"
$output = array_slice($input, -2, 1);  // returns "d"
$output = array_slice($input, 0, 3);   // returns "a", "b", and "c"
// note the differences in the array keys
print_r(array_slice($input, 2, -1));
print_r(array_slice($input, 2, -1, true));
?>`

Run code

The above example will output:

```
Array
(
    [0] => c
    [1] => d
)
Array
(
    [2] => c
    [3] => d
)
```

**Example #2 **array\_slice()** and one-based array**

`<?php
$input = array(1 => "a", "b", "c", "d", "e");
print_r(array_slice($input, 1, 2));
?>`

Run code

The above example will output:

```
Array
(
    [0] => b
    [1] => c
)
```

**Example #3 **array\_slice()** and array with mixed keys**

`<?php
$ar = array('a'=>'apple', 'b'=>'banana', '42'=>'pear', 'd'=>'orange');
print_r(array_slice($ar, 0, 3));
print_r(array_slice($ar, 0, 3, true));
?>`

Run code

The above example will output:

```
Array
(
    [a] => apple
    [b] => banana
    [0] => pear
)
Array
(
    [a] => apple
    [b] => banana
    [42] => pear
)
```

### See Also [¶](https://www.php.net/manual/en/function.array-slice.php\#refsect1-function.array-slice-seealso)

- [array\_chunk()](https://www.php.net/manual/en/function.array-chunk.php) \- Split an array into chunks
- [array\_splice()](https://www.php.net/manual/en/function.array-splice.php) \- Remove a portion of the array and replace it with something else
- [unset()](https://www.php.net/manual/en/function.unset.php) \- unset a given variable

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/array-slice.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.array-slice%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.array-slice&repo=en&redirect=https://www.php.net/manual/en/function.array-slice.php)

### User Contributed Notes 17 notes

[up](https://www.php.net/manual/vote-note.php?id=64122&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=64122&page=function.array-slice&vote=down "Vote down!")

51


[**_taylorbarstow at the google mail service_**](https://www.php.net/manual/en/function.array-slice.php#64122) [¶](https://www.php.net/manual/en/function.array-slice.php#64122)

**19 years ago**

`Array slice function that works with associative arrays (keys):
function array_slice_assoc($array,$keys) {
    return array_intersect_key($array,array_flip($keys));
}`

[up](https://www.php.net/manual/vote-note.php?id=122200&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122200&page=function.array-slice&vote=down "Vote down!")

7


[**_nathan dot fiscaletti at gmail dot com_**](https://www.php.net/manual/en/function.array-slice.php#122200) [¶](https://www.php.net/manual/en/function.array-slice.php#122200)

**7 years ago**

`If you want an associative version of this you can do the following:
function array_slice_assoc($array,$keys) {
    return array_intersect_key($array,array_flip($keys));
}
However, if you want an inverse associative version of this, just use array_diff_key instead of array_intersect_key.
function array_slice_assoc_inverse($array,$keys) {
    return array_diff_key($array,array_flip($keys));
}
Example:
$arr = [\
    'name' => 'Nathan',\
    'age' => 20,\
    'height' => 6\
];
array_slice_assoc($arr, ['name','age']);
will return
Array (
     'name' = 'Nathan',
     'age' = 20
)
Where as
array_slice_assoc_inverse($arr, ['name']);
will return
Array (
    'age' = 20,
    'height' = 6
)`

[up](https://www.php.net/manual/vote-note.php?id=112359&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112359&page=function.array-slice&vote=down "Vote down!")

19


[**_Ray.Paseur often uses Gmail_**](https://www.php.net/manual/en/function.array-slice.php#112359) [¶](https://www.php.net/manual/en/function.array-slice.php#112359)

**12 years ago**

`<?php
// CHOP $num ELEMENTS OFF THE FRONT OF AN ARRAY
// RETURN THE CHOP, SHORTENING THE SUBJECT ARRAY
function array_chop(&$arr, $num)
{
    $ret = array_slice($arr, 0, $num);
    $arr = array_slice($arr, $num);
    return $ret;
}`

[up](https://www.php.net/manual/vote-note.php?id=82950&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82950&page=function.array-slice&vote=down "Vote down!")

4


[**_ted.devito at 9gmail9 dot 99com_**](https://www.php.net/manual/en/function.array-slice.php#82950) [¶](https://www.php.net/manual/en/function.array-slice.php#82950)

**17 years ago**

`based on worldclimb's arem(), here is a recursive array value removal tool that can work with multidimensional arrays.
function remove_from_array($array,$value){
    $clear = true;
    $holding=array();

    foreach($array as $k => $v){
        if (is_array($v)) {
            $holding [$k] = remove_from_array ($v, $value);
            }
        elseif ($value == $v) {
            $clear = false;
            }
        elseif($value != $v){
            $holding[$k]=$v; // removes an item by combing through the array in order and saving the good stuff
        }
    }
    if ($clear) return $holding; // only pass back the holding array if we didn't find the value
}`

[up](https://www.php.net/manual/vote-note.php?id=81973&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81973&page=function.array-slice&vote=down "Vote down!")

11


[**_worldclimb at 99gmail99 dot com_**](https://www.php.net/manual/en/function.array-slice.php#81973) [¶](https://www.php.net/manual/en/function.array-slice.php#81973)

**17 years ago**

`array_slice can be used to remove elements from an array but it's pretty simple to use a custom function.
One day array_remove() might become part of PHP and will likely be a reserved function name, hence the unobvious choice for this function's names.
<?
function arem($array,$value){
    $holding=array();
    foreach($array as $k => $v){
        if($value!=$v){
            $holding[$k]=$v;
        }
    }
    return $holding;
}
function akrem($array,$key){
    $holding=array();
    foreach($array as $k => $v){
        if($key!=$k){
            $holding[$k]=$v;
        }
    }
    return $holding;
}
$lunch = array('sandwich' => 'cheese', 'cookie'=>'oatmeal','drink' => 'tea','fruit' => 'apple');
echo '<pre>';
print_r($lunch);
$lunch=arem($lunch,'apple');
print_r($lunch);
$lunch=akrem($lunch,'sandwich');
print_r($lunch);
echo '</pre>';
?>
(remove 9's in email)`

[up](https://www.php.net/manual/vote-note.php?id=128935&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128935&page=function.array-slice&vote=down "Vote down!")

2


[**_Benjamin Sonntag_**](https://www.php.net/manual/en/function.array-slice.php#128935) [¶](https://www.php.net/manual/en/function.array-slice.php#128935)

**2 years ago**

`The documentation doesn't say it, but if LENGTH is ZERO, then the result is an empty array [].`

[up](https://www.php.net/manual/vote-note.php?id=18741&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=18741&page=function.array-slice&vote=down "Vote down!")

8


[**_developer at i-space dot org_**](https://www.php.net/manual/en/function.array-slice.php#18741) [¶](https://www.php.net/manual/en/function.array-slice.php#18741)

**23 years ago**

`remember that array_slice returns an array with the current element. you must use array_slice($array, $index+1) if you want to get the next elements.`

[up](https://www.php.net/manual/vote-note.php?id=85695&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85695&page=function.array-slice&vote=down "Vote down!")

5


[**_s0i0m at dreamevilconcepts dot com_**](https://www.php.net/manual/en/function.array-slice.php#85695) [¶](https://www.php.net/manual/en/function.array-slice.php#85695)

**17 years ago**

`Using the varname function referenced from the array_search page, submitted by dcez at land dot ru. I created a multi-dimensional array splice function. It's usage is like so:
$array['admin'] = array('blah1', 'blah2');
$array['voice'] = array('blah3', 'blah4');
array_cut('blah4', $array);
...Would strip blah4 from the array, no matter where the position of it was in the array ^^ Returning this...
Array ( [admin] => Array ( [0] => blah1 [1] => blah2 ) [voice] => Array ( [0] => blah3 ) )
Here is the code...
<?php
function varname ($var)
{
    // varname function by dcez at land dot ru
    return (isset($var)) ? array_search($var, $GLOBALS) : false;
}
function array_cut($needle, $haystack)
{
    foreach ($haystack as $k => $v)
    {
      for ($i=0; $i<count($v); $i++)
        if ($v[$i] === $needle)
        {
          return array_splice($GLOBALS[varname($haystack)][$k], $i, 1);
          break; break;
        }
    }
?>
Check out dreamevilconcept's forum for more innovative creations!`

[up](https://www.php.net/manual/vote-note.php?id=117802&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117802&page=function.array-slice&vote=down "Vote down!")

0


[**_kansey_**](https://www.php.net/manual/en/function.array-slice.php#117802) [¶](https://www.php.net/manual/en/function.array-slice.php#117802)

**10 years ago**

`To save the sort order of a numeric index in the array. Version php =>5.5.26
/*
Example
*/
$arr = array( "1" =>2, "2" =>3 , "3" =>5 );
print_r(array_slice($arr,1,null,true));
/*
Result
Array
(
[2] => 3
[3] => 5
)
*/`

[up](https://www.php.net/manual/vote-note.php?id=102215&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=102215&page=function.array-slice&vote=down "Vote down!")

 -2


[**_xananax at yelostudio dot com_**](https://www.php.net/manual/en/function.array-slice.php#102215) [¶](https://www.php.net/manual/en/function.array-slice.php#102215)

**14 years ago**

`<?php
/**
* Reorders an array by keys according to a list of values.
* @param array $array the array to reorder. Passed by reference
* @param array $list the list to reorder by
* @param boolean $keepRest if set to FALSE, anything not in the $list array will be removed.
* @param boolean $prepend if set to TRUE, will prepend the remaining values instead of appending them
* @author xananax AT yelostudio DOT com
*/
function array_reorder(array &$array,array $list,$keepRest=TRUE,$prepend=FALSE,$preserveKeys=TRUE){
    $temp = array();
    foreach($list as $i){
        if(isset($array[$i])){
            $tempValue = array_slice(
                $array,
                array_search($i,array_keys($array)),
                1,
                $preserveKeys
            );
            $temp[$i] = array_shift($tempValue);
            unset($array[$i]);
        }
    }
    $array = $keepRest ?
        ($prepend?
            $array+$temp
            :$temp+$array
        )
        : $temp;
}
/** exemple ** /
$a = array(
    'a'    =>    'a',
    'b'    =>    'b',
    'c'    =>    'c',
    'd'    =>    'd',
    'e'    =>    'e'
);
$order = array('c','b','a');
array_reorder($a,$order,TRUE);
echo '<pre>';
print_r($a);
echo '</pre>';
/** exemple end **/
?>`

[up](https://www.php.net/manual/vote-note.php?id=56535&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56535&page=function.array-slice&vote=down "Vote down!")

 -1


[**_andreasblixt (at) msn (dot) com_**](https://www.php.net/manual/en/function.array-slice.php#56535) [¶](https://www.php.net/manual/en/function.array-slice.php#56535)

**20 years ago**

`<?php
    // Combines two arrays by inserting one into the other at a given position then returns the result
    function array_insert($src, $dest, $pos) {
        if (!is_array($src) || !is_array($dest) || $pos <= 0) return FALSE;
        return array_merge(array_slice($dest, 0, $pos), $src, array_slice($dest, $pos));
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=65711&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=65711&page=function.array-slice&vote=down "Vote down!")

 -1


[**_Anonymous_**](https://www.php.net/manual/en/function.array-slice.php#65711) [¶](https://www.php.net/manual/en/function.array-slice.php#65711)

**19 years ago**

`If you specify the fourth argument (to not reassign the keys), then there appears to be no way to get the function to return all values to the end of the array. Assigning -0 or NULL or just putting two commas in a row won't return any results.`

[up](https://www.php.net/manual/vote-note.php?id=73572&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73572&page=function.array-slice&vote=down "Vote down!")

 -2


[**_aflavio at gmail dot com_**](https://www.php.net/manual/en/function.array-slice.php#73572) [¶](https://www.php.net/manual/en/function.array-slice.php#73572)

**18 years ago**

`/**
    * Remove a value from a array
    * @param string $val
    * @param array $arr
    * @return array $array_remval
    */
    function array_remval($val, &$arr)
    {
          $array_remval = $arr;
          for($x=0;$x<count($array_remval);$x++)
          {
              $i=array_search($val,$array_remval);
              if (is_numeric($i)) {
                  $array_temp  = array_slice($array_remval, 0, $i );
                $array_temp2 = array_slice($array_remval, $i+1, count($array_remval)-1 );
                $array_remval = array_merge($array_temp, $array_temp2);
              }
          }
          return $array_remval;
    }
$stack=Array('apple','banana','pear','apple', 'cherry', 'apple');
array_remval("apple", $stack);
//output: Array('banana','pear', 'cherry')`

[up](https://www.php.net/manual/vote-note.php?id=78257&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78257&page=function.array-slice&vote=down "Vote down!")

 -4


[**_aexchecker at yahoo dot com_**](https://www.php.net/manual/en/function.array-slice.php#78257) [¶](https://www.php.net/manual/en/function.array-slice.php#78257)

**18 years ago**

`<?php
/**
* @desc
* Combines two arrays by inserting one into the other at a given position then
* returns the result.
*
* @since   2007/10/04
* @version v0.7 2007/10/04 18:47:52
* @author  AexChecker <AexChecker@yahoo.com>
* @param   array $source
* @param   array $destination
* @param   int [optional] $offset
* @param   int [optional] $length
* @return  array
*/
function array_insert($source, $destination, $offset = NULL, $length = NULL) {
    if (!is_array($source) || empty($source)) {
        if (is_array($destination) && !empty($destination)) {
            return $destination;
        }
        return array();
    }
    if (is_null($offset)) {
        return array_merge($destination, $source);
    }
    $offset = var2int($offset);
    if (is_null($length)) {
        if ($offset === 0) {
            return array_merge($source, array_slice($destination, 1));
        }
        if ($offset === -1) {
            return array_merge(array_slice($destination, 0, -1), $source);
        }
        return array_merge(
            array_slice($destination, 0, $offset),
            $source,
            array_slice($destination, ++$offset)
        );
    }
    if ($offset === 0) {
        return array_merge($source, array_slice($destination, $length));
    }
    $destination_count = count($destination);
    $length = var2int($length);
    if ($offset > 0) {
        if ($destination_count - $offset < 1) {
            return array_merge($destination, $source);
        }
    } else{
        if (($t = $destination_count + $offset) < 1) {
            return array_merge($source, $destination);
        }
        $offset = $t;
    }
    if ($length > 0) {
        $length+= $offset;
    } elseif ($length < 0 && !($length * -1 < $destination_count)) {
        return $source;
    } else {
        $length = $offset;
    }
    return array_merge(
        array_slice($destination, 0, $offset),
        $source,
        array_slice($destination, $length)
    );
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=87002&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87002&page=function.array-slice&vote=down "Vote down!")

 -3


[**_Mr. P_**](https://www.php.net/manual/en/function.array-slice.php#87002) [¶](https://www.php.net/manual/en/function.array-slice.php#87002)

**16 years ago**

`Note that offset is not the same thing as key. Offset always starts at 0, while keys might be any number.
So this:
<?php print_r(array_slice(array(0 => 0, 5 => 5, 13 => 13),1)); ?>
will result in this:
Array
(
    [0] => 5
    [1] => 13
)`

[up](https://www.php.net/manual/vote-note.php?id=48006&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=48006&page=function.array-slice&vote=down "Vote down!")

 -3


[**_bishop_**](https://www.php.net/manual/en/function.array-slice.php#48006) [¶](https://www.php.net/manual/en/function.array-slice.php#48006)

**20 years ago**

`Sometimes you need to pick certain non-integer and/or non-sequential keys out of an array. Consider using the array_pick() implementation below to pull specific keys, in a specific order, out of a source array:
<?php
$a = array ('a' => 1, 'b' => 2, 'c' => 3, 'd' => 4);
$b = array_pick($a, array ('d', 'b'));
// now:
// $a = array ('a' => 1, 'c' => '3');
// $b = array ('d' => 4, 'b' => '2');
function &array_pick(&$array, $keys)
{
    if (! is_array($array)) {
        trigger_error('First parameter must be an array', E_USER_ERROR);
        return false;
    }
    if (! (is_array($keys) || is_scalar($keys))) {
        trigger_error('Second parameter must be an array of keys or a scalar key', E_USER_ERROR);
        return false;
    }
    if (is_array($keys)) {
        // nothing to do
    } else if (is_scalar($keys)) {
        $keys = array ($keys);
    }
    $resultArray = array ();
    foreach ($keys as $key) {
        if (is_scalar($key)) {
            if (array_key_exists($key, $array)) {
                $resultArray[$key] = $array[$key];
                unset($array[$key]);
            }
        } else {
            trigger_error('Supplied key is not scalar', E_USER_ERROR);
            return false;
        }
    }
    return $resultArray;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=102383&page=function.array-slice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=102383&page=function.array-slice&vote=down "Vote down!")

 -5


[**_delew_**](https://www.php.net/manual/en/function.array-slice.php#102383) [¶](https://www.php.net/manual/en/function.array-slice.php#102383)

**14 years ago**

`just a little tip.
to preserve keys without providing length: use NULL
array_slice($array, $my_offset, NULL, true);`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.array-slice&repo=en&redirect=https://www.php.net/manual/en/function.array-slice.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google