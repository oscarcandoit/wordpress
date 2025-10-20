---
url: https://www.php.net/manual/en/function.bcpow.php
scraped_at: 2025-10-20T02:56:05.728Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# bcpow

(PHP 4, PHP 5, PHP 7, PHP 8)

bcpow — Raise an arbitrary precision number to another

### Description [¶](https://www.php.net/manual/en/function.bcpow.php\#refsect1-function.bcpow-description)

**bcpow**([string](https://www.php.net/manual/en/language.types.string.php) `$num`, [string](https://www.php.net/manual/en/language.types.string.php) `$exponent`, [?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$scale` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [string](https://www.php.net/manual/en/language.types.string.php)

Raise `num` to the power
`exponent`.


### Parameters [¶](https://www.php.net/manual/en/function.bcpow.php\#refsect1-function.bcpow-parameters)

`num`

The base, as a string.


`exponent`

The exponent, as a string. Must be a value with no fractional part.
The valid range of the exponent is platform specific, but is at least
`-2147483648` to `2147483647`.


`scale`
This parameter is used to set the number of digits after the decimal place in the result.
If **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, it will default to the default scale set with [bcscale()](https://www.php.net/manual/en/function.bcscale.php),
or fallback to the value of the
[`bcmath.scale`](https://www.php.net/manual/en/bc.configuration.php#ini.bcmath.scale) INI directive.


### Return Values [¶](https://www.php.net/manual/en/function.bcpow.php\#refsect1-function.bcpow-returnvalues)

Returns the result as a string.


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.bcpow.php\#refsect1-function.bcpow-errors)

This function throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) in the following cases:


- `num` or `exponent` is not a well-formed BCMath numeric string
- `exponent` has a fractional part
- `exponent` or `scale` is outside the valid range

This function throws a [DivisionByZeroError](https://www.php.net/manual/en/class.divisionbyzeroerror.php) exception if `num`
is `0` and `exponent` is a negative value.


### Changelog [¶](https://www.php.net/manual/en/function.bcpow.php\#refsect1-function.bcpow-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Negative powers of `0` previously returned `0`, but now throw a [DivisionByZeroError](https://www.php.net/manual/en/class.divisionbyzeroerror.php)<br> exception. |
| 8.0.0 | When `exponent` has a fractional part, it now throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php)<br> instead of truncating. |
| 7.3.0 | **bcpow()** now returns numbers with the requested scale.<br> Formerly, the returned numbers may have omitted trailing decimal zeroes. |

### Examples [¶](https://www.php.net/manual/en/function.bcpow.php\#refsect1-function.bcpow-examples)

**Example #1 **bcpow()** example**

`<?php
echo bcpow('4.2', '3', 2); // 74.08
?>`

### Notes [¶](https://www.php.net/manual/en/function.bcpow.php\#refsect1-function.bcpow-notes)

> **Note**:
>
>
> Before PHP 7.3.0 **bcpow()** may return a result with fewer digits after the
> decimal point than the `scale` parameter would
> indicate. This only occurs when the result doesn't require all of the
> precision allowed by the `scale`. For example:
>
>
> **Example #2 **bcpow()** scale example**
>
> `<?php
> echo bcpow('5', '2', 2);     // prints "25", not "25.00"
> ?>`

### See Also [¶](https://www.php.net/manual/en/function.bcpow.php\#refsect1-function.bcpow-seealso)

- [bcpowmod()](https://www.php.net/manual/en/function.bcpowmod.php) \- Raise an arbitrary precision number to another, reduced by a specified modulus
- [bcsqrt()](https://www.php.net/manual/en/function.bcsqrt.php) \- Get the square root of an arbitrary precision number
- [BcMath\\Number::pow()](https://www.php.net/manual/en/bcmath-number.pow.php) \- Raises an arbitrary precision number

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/bc/functions/bcpow.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.bcpow%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.bcpow&repo=en&redirect=https://www.php.net/manual/en/function.bcpow.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=44565&page=function.bcpow&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=44565&page=function.bcpow&vote=down "Vote down!")

1


[**_Michael Bailey (jinxidoru at byu dot net)_**](https://www.php.net/manual/en/function.bcpow.php#44565) [¶](https://www.php.net/manual/en/function.bcpow.php#44565)

**21 years ago**

`bcpow() only supports exponents less than or equal to 2^31-1.  Also, bcpow() does not support decimal numbers.  If you have scale set to 0, then the exponent is converted to an interger; otherwise an error is generated.
--
Michael Bailey
[http://www.jinxidoru.com](http://www.jinxidoru.com/)`

[up](https://www.php.net/manual/vote-note.php?id=92175&page=function.bcpow&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92175&page=function.bcpow&vote=down "Vote down!")

 -2


[**_thomas at tgohome dot com_**](https://www.php.net/manual/en/function.bcpow.php#92175) [¶](https://www.php.net/manual/en/function.bcpow.php#92175)

**16 years ago**

`<?php
bcscale(100);
/*
* Computes the natural logarithm using a series.
* @author Thomas Oldbury.
* @license Public domain.
*/
function bcln($a, $iter = 10)
{
    $result = "0.0";

    for($i = 0; $i < $iter; $i++)
    {
        $pow = (1 + (2 * $i));
        $mul = bcdiv("1.0", $pow);
        $fraction = bcmul($mul, bcpow(bcsub($a, "1.0") / bcadd($a, "1.0"), $pow));
        $result = bcadd($fraction, $result);
    }

    return bcmul("2.0", $result);
}
/*
* Computes the base2 log using baseN log.
* @note Requires above functions.
* @author Thomas Oldbury.
* @license Public domain.
*/
function bclog2($a, $iter = 10)
{
    return bcdiv(bcln($a, $iter), bcln("2", $iter));
}
/*
* Computes the base10 log using baseN log.
* @note Requires above functions.
* @author Thomas Oldbury.
* @license Public domain.
*/
function bclog10($a, $iter = 10)
{
    return bcdiv(bcln($a, $iter), bcln("10", $iter));
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=49913&page=function.bcpow&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=49913&page=function.bcpow&vote=down "Vote down!")

 -2


[**_Anonymous_**](https://www.php.net/manual/en/function.bcpow.php#49913) [¶](https://www.php.net/manual/en/function.bcpow.php#49913)

**20 years ago**

`Well, if bcpow has limits, then this should work:
<?php
function bcpow_($num, $power) {
    $awnser = "1";
    while ($power) {
        $awnser = bcmul($awnser, $num, 100);
        $power = bcsub($power, "1");
    }
    return rtrim($awnser, '0.');
}
?>
Just that $power cannot have decimal digits in it.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.bcpow&repo=en&redirect=https://www.php.net/manual/en/function.bcpow.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google