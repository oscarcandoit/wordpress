---
url: https://www.php.net/manual/en/function.array-sum.php
scraped_at: 2025-10-20T02:57:51.546Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# array\_sum

(PHP 4 >= 4.0.4, PHP 5, PHP 7, PHP 8)

array\_sum — Calculate the sum of values in an array

### Description [¶](https://www.php.net/manual/en/function.array-sum.php\#refsect1-function.array-sum-description)

**array\_sum**([array](https://www.php.net/manual/en/language.types.array.php) `$array`): [int](https://www.php.net/manual/en/language.types.integer.php)\|[float](https://www.php.net/manual/en/language.types.float.php)

**array\_sum()** returns the sum of values in an array.


### Parameters [¶](https://www.php.net/manual/en/function.array-sum.php\#refsect1-function.array-sum-parameters)

`array`

The input array.


### Return Values [¶](https://www.php.net/manual/en/function.array-sum.php\#refsect1-function.array-sum-returnvalues)

Returns the sum of values as an integer or float; `0` if the
`array` is empty.


### Changelog [¶](https://www.php.net/manual/en/function.array-sum.php\#refsect1-function.array-sum-changelog)

| Version | Description |
| --- | --- |
| 8.3.0 | Now emits **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** when `array` values<br> cannot be converted to [int](https://www.php.net/manual/en/language.types.integer.php) or [float](https://www.php.net/manual/en/language.types.float.php).<br> Previously [array](https://www.php.net/manual/en/language.types.array.php)s and [object](https://www.php.net/manual/en/language.types.object.php)s where ignored whilst every other value was cast to [int](https://www.php.net/manual/en/language.types.integer.php).<br> Moreover, objects that define a numeric cast (e.g. [GMP](https://www.php.net/manual/en/class.gmp.php)) are now cast instead of ignored. |

### Examples [¶](https://www.php.net/manual/en/function.array-sum.php\#refsect1-function.array-sum-examples)

**Example #1 **array\_sum()** examples**

`<?php
$a = array(2, 4, 6, 8);
echo "sum(a) = " . array_sum($a) . "\n";
$b = array("a" => 1.2, "b" => 2.3, "c" => 3.4);
echo "sum(b) = " . array_sum($b) . "\n";
?>`

Run code

The above example will output:

```
sum(a) = 20
sum(b) = 6.9
```

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/array-sum.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.array-sum%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.array-sum&repo=en&redirect=https://www.php.net/manual/en/function.array-sum.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=126810&page=function.array-sum&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126810&page=function.array-sum&vote=down "Vote down!")

23


[**_rodrigo at adboosters dot com_**](https://www.php.net/manual/en/function.array-sum.php#126810) [¶](https://www.php.net/manual/en/function.array-sum.php#126810)

**3 years ago**

`If you want to calculate the sum in multi-dimensional arrays:
<?php
function array_multisum(array $arr): float {
    $sum = array_sum($arr);
    foreach($arr as $child) {
        $sum += is_array($child) ? array_multisum($child) : 0;
    }
    return $sum;
}
?>
Example:
<?php
$data =
[\
    'a' => 5,\
    'b' =>\
    [\
        'c' => 7,\
        'd' => 3\
    ],\
    'e' => 4,\
    'f' =>\
    [\
        'g' => 6,\
        'h' =>\
        [\
            'i' => 1,\
            'j' => 2\
        ]\
    ]\
];
echo array_multisum($data);
//output: 28
?>`

[up](https://www.php.net/manual/vote-note.php?id=128066&page=function.array-sum&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128066&page=function.array-sum&vote=down "Vote down!")

2


[**_harl at gmail dot com_**](https://www.php.net/manual/en/function.array-sum.php#128066) [¶](https://www.php.net/manual/en/function.array-sum.php#128066)

**2 years ago**

`array_sum() doesn't "ignore strings if they are not convertible", it converts them to zero. array_product() does the same thing, where the difference between "ignoring" and "converting to zero" is much more obvious.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.array-sum&repo=en&redirect=https://www.php.net/manual/en/function.array-sum.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google