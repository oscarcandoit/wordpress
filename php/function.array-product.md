---
url: https://www.php.net/manual/en/function.array-product.php
scraped_at: 2025-10-20T02:57:54.328Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# array\_product

(PHP 5 >= 5.1.0, PHP 7, PHP 8)

array\_product — Calculate the product of values in an array

### Description [¶](https://www.php.net/manual/en/function.array-product.php\#refsect1-function.array-product-description)

**array\_product**([array](https://www.php.net/manual/en/language.types.array.php) `$array`): [int](https://www.php.net/manual/en/language.types.integer.php)\|[float](https://www.php.net/manual/en/language.types.float.php)

**array\_product()** returns the product of values
in an array.


### Parameters [¶](https://www.php.net/manual/en/function.array-product.php\#refsect1-function.array-product-parameters)

`array`

The array.


### Return Values [¶](https://www.php.net/manual/en/function.array-product.php\#refsect1-function.array-product-returnvalues)

Returns the product as an integer or float.


### Changelog [¶](https://www.php.net/manual/en/function.array-product.php\#refsect1-function.array-product-changelog)

| Version | Description |
| --- | --- |
| 8.3.0 | Now emits **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** when `array` values<br> cannot be converted to [int](https://www.php.net/manual/en/language.types.integer.php) or [float](https://www.php.net/manual/en/language.types.float.php).<br> Previously [array](https://www.php.net/manual/en/language.types.array.php)s and [object](https://www.php.net/manual/en/language.types.object.php)s where ignored whilst every other value was cast to [int](https://www.php.net/manual/en/language.types.integer.php).<br> Moreover, objects that define a numeric cast (e.g. [GMP](https://www.php.net/manual/en/class.gmp.php)) are now cast instead of ignored. |

### Examples [¶](https://www.php.net/manual/en/function.array-product.php\#refsect1-function.array-product-examples)

**Example #1 **array\_product()** examples**

`<?php
$a = array(2, 4, 6, 8);
echo "product(a) = " . array_product($a) . "\n";
echo "product(array()) = " . array_product(array()) . "\n";
?>`

Run code

The above example will output:

```
product(a) = 384
product(array()) = 1
```

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/array-product.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.array-product%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.array-product&repo=en&redirect=https://www.php.net/manual/en/function.array-product.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=68694&page=function.array-product&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=68694&page=function.array-product&vote=down "Vote down!")

28


[**_Andre D_**](https://www.php.net/manual/en/function.array-product.php#68694) [¶](https://www.php.net/manual/en/function.array-product.php#68694)

**19 years ago**

`This function can be used to test if all values in an array of booleans are TRUE.
Consider:
<?php
function outbool($test)
{
    return (bool) $test;
}
$check[] = outbool(TRUE);
$check[] = outbool(1);
$check[] = outbool(FALSE);
$check[] = outbool(0);
$result = (bool) array_product($check);
// $result is set to FALSE because only two of the four values evaluated to TRUE
?>
The above is equivalent to:
<?php
$check1 = outbool(TRUE);
$check2 = outbool(1);
$check3 = outbool(FALSE);
$check4 = outbool(0);
$result = ($check1 && $check2 && $check3 && $check4);
?>
This use of array_product is especially useful when testing an indefinite number of booleans and is easy to construct in a loop.`

[up](https://www.php.net/manual/vote-note.php?id=121185&page=function.array-product&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121185&page=function.array-product&vote=down "Vote down!")

14


[**_bsr dot anwar at gmail dot com_**](https://www.php.net/manual/en/function.array-product.php#121185) [¶](https://www.php.net/manual/en/function.array-product.php#121185)

**8 years ago**

`Here's how you can find a factorial of a any given number with help of range and array_product functions.
function factorial($num) {
    return array_product(range(1, $num));
}
printf("%d", factorial(5)); //120`

[up](https://www.php.net/manual/vote-note.php?id=128326&page=function.array-product&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128326&page=function.array-product&vote=down "Vote down!")

2


[**_gergely dot lukacsy at streamnet dot hu_**](https://www.php.net/manual/en/function.array-product.php#128326) [¶](https://www.php.net/manual/en/function.array-product.php#128326)

**2 years ago**

`Just a little correction for Andre D's answer: "(bool) array_product($array);" is equivalent with the conjunction of each array elements of $array, UNLESS the provided array is empty in which case array_product() will return 1, which will translate to boolean TRUE.
To mitigate this, you should expand the function with an additional check:
<?php
$result = !empty($check) && !!array_product($check);
?>`

[up](https://www.php.net/manual/vote-note.php?id=127879&page=function.array-product&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127879&page=function.array-product&vote=down "Vote down!")

0


[**_biziclop_**](https://www.php.net/manual/en/function.array-product.php#127879) [¶](https://www.php.net/manual/en/function.array-product.php#127879)

**2 years ago**

`You can use array_product() to calculate the geometric mean of an array of numbers:
<?php
$a = [ 1, 10, 100 ];
$geom_avg = pow( array_product( $a ), 1 / count( $a ));
// = 9.999999999999998 ≈ 10
?>`

[up](https://www.php.net/manual/vote-note.php?id=100153&page=function.array-product&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100153&page=function.array-product&vote=down "Vote down!")

0


[**_Marcel G_**](https://www.php.net/manual/en/function.array-product.php#100153) [¶](https://www.php.net/manual/en/function.array-product.php#100153)

**15 years ago**

`You can use array_product to calculate the factorial of n:
<?php
function factorial( $n )
{
if( $n < 1 ) $n = 1;
return array_product( range( 1, $n ));
}
?>
If you need the factorial without having array_product available, here is one:
<?php
function factorial( $n )
{
if( $n < 1 ) $n = 1;
for( $p++; $n; ) $p *= $n--;
return $p;
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.array-product&repo=en&redirect=https://www.php.net/manual/en/function.array-product.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google