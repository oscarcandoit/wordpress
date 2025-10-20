---
url: https://www.php.net/manual/en/function.natcasesort.php
scraped_at: 2025-10-20T02:49:04.494Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# natcasesort

(PHP 4, PHP 5, PHP 7, PHP 8)

natcasesort — Sort an array using a case insensitive "natural order" algorithm

### Description [¶](https://www.php.net/manual/en/function.natcasesort.php\#refsect1-function.natcasesort-description)

**natcasesort**([array](https://www.php.net/manual/en/language.types.array.php) `&$array`): [true](https://www.php.net/manual/en/language.types.singleton.php)

**natcasesort()** is a case insensitive version of
[natsort()](https://www.php.net/manual/en/function.natsort.php).


This function implements a sort algorithm that orders
alphanumeric strings in the way a human being would while maintaining
key/value associations. This is described as a "natural ordering".


> **Note**:
>
>
> If two members compare as equal, they retain their original order.
> Prior to PHP 8.0.0, their relative order in the sorted array was undefined.

> **Note**:
>
>
> Resets array's internal pointer to the first element.

### Parameters [¶](https://www.php.net/manual/en/function.natcasesort.php\#refsect1-function.natcasesort-parameters)

`array`

The input array.


### Return Values [¶](https://www.php.net/manual/en/function.natcasesort.php\#refsect1-function.natcasesort-returnvalues)

Always returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.


### Changelog [¶](https://www.php.net/manual/en/function.natcasesort.php\#refsect1-function.natcasesort-changelog)

| Version | Description |
| --- | --- |
| 8.2.0 | The return type is **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** now; previously, it was [bool](https://www.php.net/manual/en/language.types.boolean.php). |

### Examples [¶](https://www.php.net/manual/en/function.natcasesort.php\#refsect1-function.natcasesort-examples)

**Example #1 **natcasesort()** example**

`<?php
$array1 = $array2 = array('IMG0.png', 'img12.png', 'img10.png', 'img2.png', 'img1.png', 'IMG3.png');
sort($array1);
echo "Standard sorting\n";
print_r($array1);
natcasesort($array2);
echo "\nNatural order sorting (case-insensitive)\n";
print_r($array2);
?>`

Run code

The above example will output:

```
Standard sorting
Array
(
    [0] => IMG0.png
    [1] => IMG3.png
    [2] => img1.png
    [3] => img10.png
    [4] => img12.png
    [5] => img2.png
)

Natural order sorting (case-insensitive)
Array
(
    [0] => IMG0.png
    [4] => img1.png
    [3] => img2.png
    [5] => IMG3.png
    [2] => img10.png
    [1] => img12.png
)
```

For more information see: Martin Pool's [» Natural Order String Comparison](https://github.com/sourcefrog/natsort)
page.


### See Also [¶](https://www.php.net/manual/en/function.natcasesort.php\#refsect1-function.natcasesort-seealso)

- [natsort()](https://www.php.net/manual/en/function.natsort.php) \- Sort an array using a "natural order" algorithm
- The [comparison of array sorting functions](https://www.php.net/manual/en/array.sorting.php)
- [strnatcmp()](https://www.php.net/manual/en/function.strnatcmp.php) \- String comparisons using a "natural order" algorithm
- [strnatcasecmp()](https://www.php.net/manual/en/function.strnatcasecmp.php) \- Case insensitive string comparisons using a "natural order" algorithm

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/natcasesort.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.natcasesort%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.natcasesort&repo=en&redirect=https://www.php.net/manual/en/function.natcasesort.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=32610&page=function.natcasesort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=32610&page=function.natcasesort&vote=down "Vote down!")

46


[**_dslicer at maine dot rr dot com_**](https://www.php.net/manual/en/function.natcasesort.php#32610) [¶](https://www.php.net/manual/en/function.natcasesort.php#32610)

**22 years ago**

`Something that should probably be documented is the fact that both natsort and natcasesort maintain the key-value associations of the array. If you natsort a numerically indexed array, a for loop will not produce the sorted order; a foreach loop, however, will produce the sorted order, but the indices won't be in numeric order. If you want natsort and natcasesort to break the key-value associations, just use array_values on the sorted array, like so:
natcasesort($arr);
$arr = array_values($arr);`

[up](https://www.php.net/manual/vote-note.php?id=101394&page=function.natcasesort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101394&page=function.natcasesort&vote=down "Vote down!")

3


[**_w-dot-rosenbach-at-netskill-de_**](https://www.php.net/manual/en/function.natcasesort.php#101394) [¶](https://www.php.net/manual/en/function.natcasesort.php#101394)

**14 years ago**

`Sorting UTF-8 by arbitrary order:
<?php
mb_internal_encoding("UTF-8");
class utf_8_german
{
// everything else is sorted at the end
static $order = '0123456789AaÄäBbCcDdEeFfGgHhIiJjKkLlMm
NnOoÖöPpQqRrSsßTtUuÜüVvWwXxYyZz';
static $char2order;

static function cmp($a, $b) {
    if ($a == $b) {
        return 0;
    }

    // lazy init mapping
    if (empty(self::$char2order))
    {
      $order = 1;
      $len = mb_strlen(self::$order);
      for ($order=0; $order<$len; ++$order)
      {
        self::$char2order[mb_substr(self::$order, $order, 1)] = $order;
      }
    }

    $len_a = mb_strlen($a);
    $len_b = mb_strlen($b);
    $max=min($len_a, $len_b);
    for($i=0; $i<$max; ++$i)
    {
      $char_a= mb_substr($a, $i, 1);
      $char_b= mb_substr($b, $i, 1);

      if ($char_a == $char_b) continue;
      $order_a = (isset(self::$char2order[$char_a])) ? self::$char2order[$char_a] : 9999;
      $order_b = (isset(self::$char2order[$char_b])) ? self::$char2order[$char_b] : 9999;

      return ($order_a < $order_b) ? -1 : 1;
    }
    return ($len_a < $len_b) ? -1 : 1;
}
}
// usage example:
$t = array(
'Birnen', 'Birne', 'Äpfel', 'Apfel',
);
uasort($t, 'utf_8_german::cmp');
echo '$t: <pre>'.htmlspecialchars(print_r($t,true),null,'UTF-8').'</pre>';
?>`

[up](https://www.php.net/manual/vote-note.php?id=88037&page=function.natcasesort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88037&page=function.natcasesort&vote=down "Vote down!")

 -1


[**_claude at schlesser dot lu_**](https://www.php.net/manual/en/function.natcasesort.php#88037) [¶](https://www.php.net/manual/en/function.natcasesort.php#88037)

**16 years ago**

`Here a function that will natural sort an array by keys with keys that contain special characters.
<?php
function natksort($array)
{
    $original_keys_arr = array();
    $original_values_arr = array();
    $clean_keys_arr = array();
    $i = 0;
    foreach ($array AS $key => $value)
    {
        $original_keys_arr[$i] = $key;
        $original_values_arr[$i] = $value;
        $clean_keys_arr[$i] = strtr($key, "ÄÖÜäöüÉÈÀËëéèàç", "AOUaouEEAEeeeac");
        $i++;
    }
    natcasesort($clean_keys_arr);
    $result_arr = array();
    foreach ($clean_keys_arr AS $key => $value)
    {
        $original_key = $original_keys_arr[$key];
        $original_value = $original_values_arr[$key];
        $result_arr[$original_key] = $original_value;
    }
    return $result_arr;
}
?>
Hope it will be useful to somebody :)`

[up](https://www.php.net/manual/vote-note.php?id=35720&page=function.natcasesort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=35720&page=function.natcasesort&vote=down "Vote down!")

 -1


[**_vbAlexDOSMan at Yahoo dot com_**](https://www.php.net/manual/en/function.natcasesort.php#35720) [¶](https://www.php.net/manual/en/function.natcasesort.php#35720)

**22 years ago**

`Ulli at Stemmeler dot net:  I remade your function -- it's a little more compact now -- Enjoy...
function ignorecasesort(&$array) {
/*Make each element it's lowercase self plus itself*/
/*(e.g. "MyWebSite" would become "mywebsiteMyWebSite"*/
for ($i = 0; $i < sizeof($array); $array[$i] = strtolower($array[$i]).$array[$i], $i++);
/*Sort it -- only the lowercase versions will be used*/
sort($array);
/*Take each array element, cut it in half, and add the latter half to a new array*/
/*(e.g. "mywebsiteMyWebSite" would become "MyWebSite")*/
for ($i = 0; $i < sizeof($array); $i++) {
    $this = $array[$i];
    $array[$i] = substr($this, (strlen($this)/2), strlen($this));
}
}`

[up](https://www.php.net/manual/vote-note.php?id=21033&page=function.natcasesort&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=21033&page=function.natcasesort&vote=down "Vote down!")

 -5


[**_tmiller25 at hotmail dot com_**](https://www.php.net/manual/en/function.natcasesort.php#21033) [¶](https://www.php.net/manual/en/function.natcasesort.php#21033)

**23 years ago**

`add this loop to the function above if you want items which have the same first characters to be listed in a way that the shorter string comes first.
--------------------
/* short before longer (e.g. 'abc' should come before 'abcd') */
for($i=count($array)-1;$i>0;$i--) {
    $str_a = $array[$i  ];
    $str_b = $array[$i-1];
    $cmp_a = strtolower(substr($str_a,0,strlen($str_a)));
    $cmp_b = strtolower(substr($str_b,0,strlen($str_a)));
    if ($cmp_a==$cmp_b && strlen($str_a)<strlen($str_b)) {
      $array[$i]=$str_b; $array[$i-1]=$str_a; $i+=2;
    }
}
--------------------`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.natcasesort&repo=en&redirect=https://www.php.net/manual/en/function.natcasesort.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google