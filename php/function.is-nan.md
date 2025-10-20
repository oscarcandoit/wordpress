---
url: https://www.php.net/manual/en/function.is-nan.php
scraped_at: 2025-10-20T02:39:14.049Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# is\_nan

(PHP 4 >= 4.2.0, PHP 5, PHP 7, PHP 8)

is\_nan — Checks whether a float is NAN

### Description [¶](https://www.php.net/manual/en/function.is-nan.php\#refsect1-function.is-nan-description)

**is\_nan**([float](https://www.php.net/manual/en/language.types.float.php) `$num`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Returns whether the given `num` is **`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`** (Not A Number).


**`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`** is returned from mathematical operations that are undefined,
for example when passing parameters outside of function’s input domain. The square root
([sqrt()](https://www.php.net/manual/en/function.sqrt.php)) is only defined for positive numbers, passing a negative number
will result in **`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`**. Other examples of operations returning **`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`**
are dividing **`[INF](https://www.php.net/manual/en/math.constants.php#constant.inf)`** by **`[INF](https://www.php.net/manual/en/math.constants.php#constant.inf)`** and any operation involving an
existing **`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`** value.


> **Note**:
>
>
> Despite its name of Not A Number, **`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`** is a valid value of type [float](https://www.php.net/manual/en/language.types.float.php).

**Caution**

**`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`** does not compare equal to **`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`**. To check whether
a float is **`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`**, **is\_nan()** must be used. Checking
`$float === NAN` will not work.


### Parameters [¶](https://www.php.net/manual/en/function.is-nan.php\#refsect1-function.is-nan-parameters)

`num`

The [float](https://www.php.net/manual/en/language.types.float.php) to check


### Return Values [¶](https://www.php.net/manual/en/function.is-nan.php\#refsect1-function.is-nan-returnvalues)

**`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if `num` is **`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`**, else **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


### Examples [¶](https://www.php.net/manual/en/function.is-nan.php\#refsect1-function.is-nan-examples)

**Example #1 **is\_nan()** example**

`<?php
$nan = sqrt(-1);
var_dump($nan, is_nan($nan));
?>`

Run code

The above example will output:

```
float(NAN)
bool(true)
```

### See Also [¶](https://www.php.net/manual/en/function.is-nan.php\#refsect1-function.is-nan-seealso)

- [is\_finite()](https://www.php.net/manual/en/function.is-finite.php) \- Checks whether a float is finite
- [is\_infinite()](https://www.php.net/manual/en/function.is-infinite.php) \- Checks whether a float is infinite

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/math/functions/is-nan.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.is-nan%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.is-nan&repo=en&redirect=https://www.php.net/manual/en/function.is-nan.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=62504&page=function.is-nan&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62504&page=function.is-nan&vote=down "Vote down!")

25


[**_darkangel at moveinmod dot net_**](https://www.php.net/manual/en/function.is-nan.php#62504) [¶](https://www.php.net/manual/en/function.is-nan.php#62504)

**19 years ago**

`nan/"not a number" is not meant to see if the data type is numeric/textual/etc..
NaN is actually a set of values which can be stored in floating-point variables, but dont actually evaluate to a proper floating point number.
The floating point system has three sections: 1 bit for the sign (+/-), an 8 bit exponent, and a 23 bit fractional part.
There are rules governing which combinations of values can be placed into each section, and some values are reserved for numbers such as infinity. This leads to certain combinations being invalid, or in other words, not a number.`

[up](https://www.php.net/manual/vote-note.php?id=117310&page=function.is-nan&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117310&page=function.is-nan&vote=down "Vote down!")

14


[**_10basetom_**](https://www.php.net/manual/en/function.is-nan.php#117310) [¶](https://www.php.net/manual/en/function.is-nan.php#117310)

**10 years ago**

`I would use is_numeric() instead of ctype_digit() if you cannot be 100% sure what data type the string will be. Example from the docs:
<?php
$numeric_string = '42';
$integer        = 42;
ctype_digit($numeric_string);  // true
ctype_digit($integer);         // false (ASCII 42 is the * character)
is_numeric($numeric_string);   // true
is_numeric($integer);          // true
?>`

[up](https://www.php.net/manual/vote-note.php?id=124931&page=function.is-nan&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124931&page=function.is-nan&vote=down "Vote down!")

3


[**_ScorpioT1000_**](https://www.php.net/manual/en/function.is-nan.php#124931) [¶](https://www.php.net/manual/en/function.is-nan.php#124931)

**5 years ago**

`function is_nan2($n) {
    return $n !== $n;
}
is_nan2(NAN); // true`

[up](https://www.php.net/manual/vote-note.php?id=119161&page=function.is-nan&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119161&page=function.is-nan&vote=down "Vote down!")

1


[**_php at darkain dot com_**](https://www.php.net/manual/en/function.is-nan.php#119161) [¶](https://www.php.net/manual/en/function.is-nan.php#119161)

**9 years ago**

`Starting with PHP 7, the string 'NaN' evaluates to the NaN value as well.
Example:
var_dump( (float) 'NaN' );
PHP 5.x and HHVM:
float(0)
PHP 7.0:
float(NAN)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.is-nan&repo=en&redirect=https://www.php.net/manual/en/function.is-nan.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google