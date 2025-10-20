---
url: https://www.php.net/manual/en/function.round.php
scraped_at: 2025-10-20T02:31:46.508Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# round

(PHP 4, PHP 5, PHP 7, PHP 8)

round — Rounds a float

### Description [¶](https://www.php.net/manual/en/function.round.php\#refsect1-function.round-description)

**round**([int](https://www.php.net/manual/en/language.types.integer.php)\|[float](https://www.php.net/manual/en/language.types.float.php) `$num`, [int](https://www.php.net/manual/en/language.types.integer.php) `$precision` = 0, [int](https://www.php.net/manual/en/language.types.integer.php)\|[RoundingMode](https://www.php.net/manual/en/enum.roundingmode.php) `$mode` = RoundingMode::HalfAwayFromZero): [float](https://www.php.net/manual/en/language.types.float.php)

Returns the rounded value of `num` to
specified `precision`
(number of digits after the decimal point).
`precision` can also be negative or zero (default).


### Parameters [¶](https://www.php.net/manual/en/function.round.php\#refsect1-function.round-parameters)

`num`

The value to round.


`precision`

The optional number of decimal digits to round to.


If the `precision` is positive, `num` is
rounded to `precision` significant digits after the decimal point.


If the `precision` is negative, `num` is
rounded to `precision` significant digits before the decimal point,
i.e. to the nearest multiple of `pow(10, -$precision)`, e.g. for a
`precision` of -1 `num` is rounded to tens,
for a `precision` of -2 to hundreds, etc.


`mode`

Use [RoundingMode](https://www.php.net/manual/en/enum.roundingmode.php) or one of the following constants to specify the mode in which rounding occurs.


| Constants | Description |
| --- | --- |
| **`[PHP\_ROUND\_HALF\_UP](https://www.php.net/manual/en/math.constants.php#constant.php-round-half-up)`** | Rounds `num` away from zero when it is half way there,<br> making 1.5 into 2 and -1.5 into -2. |
| **`[PHP\_ROUND\_HALF\_DOWN](https://www.php.net/manual/en/math.constants.php#constant.php-round-half-down)`** | Rounds `num` towards zero when it is half way there,<br> making 1.5 into 1 and -1.5 into -1. |
| **`[PHP\_ROUND\_HALF\_EVEN](https://www.php.net/manual/en/math.constants.php#constant.php-round-half-even)`** | Rounds `num` towards the nearest even value when it is half way<br> there, making both 1.5 and 2.5 into 2. |
| **`[PHP\_ROUND\_HALF\_ODD](https://www.php.net/manual/en/math.constants.php#constant.php-round-half-odd)`** | Rounds `num` towards the nearest odd value when it is half way<br> there, making 1.5 into 1 and 2.5 into 3. |

However, please note that some newly added modes only exist in [RoundingMode](https://www.php.net/manual/en/enum.roundingmode.php).



### Return Values [¶](https://www.php.net/manual/en/function.round.php\#refsect1-function.round-returnvalues)

The value rounded to the given `precision` as a [float](https://www.php.net/manual/en/language.types.float.php).


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.round.php\#refsect1-function.round-errors)

The function throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if `mode` is
invalid.
Prior to PHP 8.4.0, an invalid mode would silently default to **`[PHP\_ROUND\_HALF\_UP](https://www.php.net/manual/en/math.constants.php#constant.php-round-half-up)`**.


### Changelog [¶](https://www.php.net/manual/en/function.round.php\#refsect1-function.round-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Four new rounding modes have been added. |
| 8.4.0 | Now throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if<br> `mode` is invalid. |
| 8.0.0 | `num` no longer accepts internal objects which support<br> numeric conversion. |

### Examples [¶](https://www.php.net/manual/en/function.round.php\#refsect1-function.round-examples)

**Example #1 **round()** examples**

`<?php
var_dump(round(3.4));
var_dump(round(3.5));
var_dump(round(3.6));
var_dump(round(3.6, 0));
var_dump(round(5.045, 2));
var_dump(round(5.055, 2));
var_dump(round(345, -2));
var_dump(round(345, -3));
var_dump(round(678, -2));
var_dump(round(678, -3));
?>`

Run code

The above example will output:

```
float(3)
float(4)
float(4)
float(4)
float(5.05)
float(5.06)
float(300)
float(0)
float(700)
float(1000)
```

**Example #2 How `precision` affects a float**

`<?php
$number = 135.79;
var_dump(round($number, 3));
var_dump(round($number, 2));
var_dump(round($number, 1));
var_dump(round($number, 0));
var_dump(round($number, -1));
var_dump(round($number, -2));
var_dump(round($number, -3));
?>`

Run code

The above example will output:

```
float(135.79)
float(135.79)
float(135.8)
float(136)
float(140)
float(100)
float(0)
```

**Example #3 `mode` examples**

`<?php
echo 'Rounding modes with 9.5' . PHP_EOL;
var_dump(round(9.5, 0, PHP_ROUND_HALF_UP));
var_dump(round(9.5, 0, PHP_ROUND_HALF_DOWN));
var_dump(round(9.5, 0, PHP_ROUND_HALF_EVEN));
var_dump(round(9.5, 0, PHP_ROUND_HALF_ODD));
echo PHP_EOL;
echo 'Rounding modes with 8.5' . PHP_EOL;
var_dump(round(8.5, 0, PHP_ROUND_HALF_UP));
var_dump(round(8.5, 0, PHP_ROUND_HALF_DOWN));
var_dump(round(8.5, 0, PHP_ROUND_HALF_EVEN));
var_dump(round(8.5, 0, PHP_ROUND_HALF_ODD));
?>`

Run code

The above example will output:

```
Rounding modes with 9.5
float(10)
float(9)
float(10)
float(9)

Rounding modes with 8.5
float(9)
float(8)
float(8)
float(9)
```

**Example #4 `mode` with `precision` examples**

`<?php
echo 'Using PHP_ROUND_HALF_UP with 1 decimal digit precision' . PHP_EOL;
var_dump(round( 1.55, 1, PHP_ROUND_HALF_UP));
var_dump(round(-1.55, 1, PHP_ROUND_HALF_UP));
echo PHP_EOL;
echo 'Using PHP_ROUND_HALF_DOWN with 1 decimal digit precision' . PHP_EOL;
var_dump(round( 1.55, 1, PHP_ROUND_HALF_DOWN));
var_dump(round(-1.55, 1, PHP_ROUND_HALF_DOWN));
echo PHP_EOL;
echo 'Using PHP_ROUND_HALF_EVEN with 1 decimal digit precision' . PHP_EOL;
var_dump(round( 1.55, 1, PHP_ROUND_HALF_EVEN));
var_dump(round(-1.55, 1, PHP_ROUND_HALF_EVEN));
echo PHP_EOL;
echo 'Using PHP_ROUND_HALF_ODD with 1 decimal digit precision' . PHP_EOL;
var_dump(round( 1.55, 1, PHP_ROUND_HALF_ODD));
var_dump(round(-1.55, 1, PHP_ROUND_HALF_ODD));
?>`

Run code

The above example will output:

```
Using PHP_ROUND_HALF_UP with 1 decimal digit precision
float(1.6)
float(-1.6)

Using PHP_ROUND_HALF_DOWN with 1 decimal digit precision
float(1.5)
float(-1.5)

Using PHP_ROUND_HALF_EVEN with 1 decimal digit precision
float(1.6)
float(-1.6)

Using PHP_ROUND_HALF_ODD with 1 decimal digit precision
float(1.5)
float(-1.5)
```

**Example #5 Example of using [RoundingMode](https://www.php.net/manual/en/enum.roundingmode.php)**

`<?php
foreach (RoundingMode::cases() as $mode) {
    foreach ([\
        8.5,\
        9.5,\
        -3.5,\
    ] as $number) {
        printf("%-17s: %+.17g -> %+.17g\n", $mode->name, $number, round($number, 0, $mode));
    }
    echo "\n";
}
?>`

Run code

The above example will output:

```
HalfAwayFromZero : +8.5 -> +9
HalfAwayFromZero : +9.5 -> +10
HalfAwayFromZero : -3.5 -> -4

HalfTowardsZero  : +8.5 -> +8
HalfTowardsZero  : +9.5 -> +9
HalfTowardsZero  : -3.5 -> -3

HalfEven         : +8.5 -> +8
HalfEven         : +9.5 -> +10
HalfEven         : -3.5 -> -4

HalfOdd          : +8.5 -> +9
HalfOdd          : +9.5 -> +9
HalfOdd          : -3.5 -> -3

TowardsZero      : +8.5 -> +8
TowardsZero      : +9.5 -> +9
TowardsZero      : -3.5 -> -3

AwayFromZero     : +8.5 -> +9
AwayFromZero     : +9.5 -> +10
AwayFromZero     : -3.5 -> -4

NegativeInfinity : +8.5 -> +8
NegativeInfinity : +9.5 -> +9
NegativeInfinity : -3.5 -> -4

PositiveInfinity : +8.5 -> +9
PositiveInfinity : +9.5 -> +10
PositiveInfinity : -3.5 -> -3
```

### See Also [¶](https://www.php.net/manual/en/function.round.php\#refsect1-function.round-seealso)

- [ceil()](https://www.php.net/manual/en/function.ceil.php) \- Round fractions up
- [floor()](https://www.php.net/manual/en/function.floor.php) \- Round fractions down
- [number\_format()](https://www.php.net/manual/en/function.number-format.php) \- Format a number with grouped thousands

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/math/functions/round.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.round%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.round&repo=en&redirect=https://www.php.net/manual/en/function.round.php)

### User Contributed Notes 13 notes

[up](https://www.php.net/manual/vote-note.php?id=114573&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114573&page=function.round&vote=down "Vote down!")

327


[**_takingsides at gmail dot com_**](https://www.php.net/manual/en/function.round.php#114573) [¶](https://www.php.net/manual/en/function.round.php#114573)

**11 years ago**

`In my opinion this function lacks two flags:
- PHP_ROUND_UP - Always round up.
- PHP_ROUND_DOWN - Always round down.
In accounting, it's often necessary to always round up, or down to a precision of thousandths.
<?php
function round_up($number, $precision = 2)
{
    $fig = (int) str_pad('1', $precision, '0');
    return (ceil($number * $fig) / $fig);
}
function round_down($number, $precision = 2)
{
    $fig = (int) str_pad('1', $precision, '0');
    return (floor($number * $fig) / $fig);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=120467&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120467&page=function.round&vote=down "Vote down!")

33


[**_depaula at unilogica dot com_**](https://www.php.net/manual/en/function.round.php#120467) [¶](https://www.php.net/manual/en/function.round.php#120467)

**8 years ago**

`As PHP doesn't have a a native number truncate function, this is my solution - a function that can be usefull if you need truncate instead round a number.
<?php
/**
* Truncate a float number, example: <code>truncate(-1.49999, 2); // returns -1.49
* truncate(.49999, 3); // returns 0.499
* </code>
* @param float $val Float number to be truncate
* @param int f Number of precision
* @return float
*/
function truncate($val, $f="0")
{
    if(($p = strpos($val, '.')) !== false) {
        $val = floatval(substr($val, 0, $p + 1 + $f));
    }
    return $val;
}
?>
Originally posted in [http://stackoverflow.com/a/12710283/1596489](http://stackoverflow.com/a/12710283/1596489)`

[up](https://www.php.net/manual/vote-note.php?id=115653&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115653&page=function.round&vote=down "Vote down!")

31


[**_slimusgm at gmail dot com_**](https://www.php.net/manual/en/function.round.php#115653) [¶](https://www.php.net/manual/en/function.round.php#115653)

**11 years ago**

`If you have negative zero and you need return positive number simple add +0:
$number = -2.38419e-07;
var_dump(round($number,1));//float(-0)
var_dump(round($number,1) + 0);//float(0)`

[up](https://www.php.net/manual/vote-note.php?id=115298&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115298&page=function.round&vote=down "Vote down!")

20


[**_esion99 at gmail dot com_**](https://www.php.net/manual/en/function.round.php#115298) [¶](https://www.php.net/manual/en/function.round.php#115298)

**11 years ago**

`Unexpected result or misunderstanding (php v5.5.9)
<?php
echo round(1.55, 1, PHP_ROUND_HALF_DOWN); // 1.5
echo round(1.551, 1, PHP_ROUND_HALF_DOWN); //1.6
?>`

[up](https://www.php.net/manual/vote-note.php?id=114122&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114122&page=function.round&vote=down "Vote down!")

21


[**_djcox99 at googlemail dot com_**](https://www.php.net/manual/en/function.round.php#114122) [¶](https://www.php.net/manual/en/function.round.php#114122)

**11 years ago**

`I discovered that under some conditions you can get rounding errors with round when converting the number to a string afterwards.
To fix this I swapped round() for number_format().
Unfortunately i cant give an example (because the number cant be represented as a string !)
essentially I had round(0.688888889,2);
which would stay as 0.68888889 when printed as a string.
But using number_format it correctly became 0.69.`

[up](https://www.php.net/manual/vote-note.php?id=113917&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113917&page=function.round&vote=down "Vote down!")

10


[**_craft at ckdevelop dot org_**](https://www.php.net/manual/en/function.round.php#113917) [¶](https://www.php.net/manual/en/function.round.php#113917)

**11 years ago**

`function mround($val, $f=2, $d=6){
    return sprintf("%".$d.".".$f."f", $val);
}
echo mround(34.89999);  //34.90`

[up](https://www.php.net/manual/vote-note.php?id=100322&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100322&page=function.round&vote=down "Vote down!")

17


[**_Anonymous_**](https://www.php.net/manual/en/function.round.php#100322) [¶](https://www.php.net/manual/en/function.round.php#100322)

**15 years ago**

`Here is function that rounds to a specified increment, but always up. I had to use it for price adjustment that always went up to $5 increments.
<?php
function roundUpTo($number, $increments) {
    $increments = 1 / $increments;
    return (ceil($number * $increments) / $increments);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=5832&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=5832&page=function.round&vote=down "Vote down!")

18


[**_twan at ecreation dot nl_**](https://www.php.net/manual/en/function.round.php#5832) [¶](https://www.php.net/manual/en/function.round.php#5832)

**25 years ago**

`If you'd only want to round for displaying variables (not for calculating on the rounded result) then you should use printf with the float:
<?php printf ("%6.2f",3.39532); ?>
This returns: 3.40 .`

[up](https://www.php.net/manual/vote-note.php?id=105790&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105790&page=function.round&vote=down "Vote down!")

8


[**_christian at deligant dot net_**](https://www.php.net/manual/en/function.round.php#105790) [¶](https://www.php.net/manual/en/function.round.php#105790)

**14 years ago**

`this function (as all mathematical operators) takes care of the setlocale setting, resulting in some weirdness when using the result where the english math notation is expected, as the printout of the result in a width: style attribute!
<?php
$a=3/4;
echo round($a, 2); // 0.75
setlocale(LC_ALL, 'it_IT@euro', 'it_IT', 'it');
$b=3/4;
echo round($b,2); // 0,75
?>`

[up](https://www.php.net/manual/vote-note.php?id=93747&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93747&page=function.round&vote=down "Vote down!")

7


[**_michaeldnelson dot mdn at gmail dot com_**](https://www.php.net/manual/en/function.round.php#93747) [¶](https://www.php.net/manual/en/function.round.php#93747)

**16 years ago**

`This function will let you round to an arbitrary non-zero number.  Zero of course causes a division by zero.
<?php
function roundTo($number, $to){
    return round($number/$to, 0)* $to;
}
echo roundTo(87.23, 20); //80
echo roundTo(-87.23, 20); //-80
echo roundTo(87.23, .25); //87.25
echo roundTo(.23, .25); //.25
?>`

[up](https://www.php.net/manual/vote-note.php?id=120232&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120232&page=function.round&vote=down "Vote down!")

3


[**_greghenle at gmail dot com_**](https://www.php.net/manual/en/function.round.php#120232) [¶](https://www.php.net/manual/en/function.round.php#120232)

**8 years ago**

`/**
* Round to first significant digit
* +N to +infinity
* -N to -infinity
*
*/
function round1stSignificant ( $N ) {
if ( $N === 0 ) {
    return 0;
}
$x = floor ( log10 ( abs( $N ) ) );
return ( $N > 0 )
    ? ceil( $N * pow ( 10, $x * -1 ) ) * pow( 10, $x )
    : floor( $N * pow ( 10, $x * -1 ) ) * pow( 10, $x );
}
echo round1stSignificant( 39144818 ) . PHP_EOL;
echo round1stSignificant( 124818 ) . PHP_EOL;
echo round1stSignificant( 0.07468 ) . PHP_EOL;
echo round1stSignificant( 0 ) . PHP_EOL;
echo round1stSignificant( -0.07468 ) . PHP_EOL;
/**
* Output
*
* 40000000
* 200000
* 0.08
* 0
* -0.08
*
*/`

[up](https://www.php.net/manual/vote-note.php?id=109380&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109380&page=function.round&vote=down "Vote down!")

4


[**_dastra_**](https://www.php.net/manual/en/function.round.php#109380) [¶](https://www.php.net/manual/en/function.round.php#109380)

**13 years ago**

`round() will sometimes return E notation when rounding a float when the amount is small enough - see  [https://bugs.php.net/bug.php?id=44223](https://bugs.php.net/bug.php?id=44223) .  Apparently it's a feature.
To work around this "feature" when converting to a string, surround your round statement with an sprintf:
sprintf("%.10f", round( $amountToBeRounded, 10));`

[up](https://www.php.net/manual/vote-note.php?id=24379&page=function.round&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=24379&page=function.round&vote=down "Vote down!")

9


[**_php at silisoftware dot com_**](https://www.php.net/manual/en/function.round.php#24379) [¶](https://www.php.net/manual/en/function.round.php#24379)

**23 years ago**

`Here's a function to round to an arbitary number of significant digits. Don't confuse it with rounding to a negative precision - that counts back from the decimal point, this function counts forward from the Most Significant Digit.
ex:
<?php
round(1241757, -3); // 1242000
RoundSigDigs(1241757, 3); // 1240000
?>
Works on negative numbers too. $sigdigs should be >= 0
<?php
function RoundSigDigs($number, $sigdigs) {
    $multiplier = 1;
    while ($number < 0.1) {
        $number *= 10;
        $multiplier /= 10;
    }
    while ($number >= 1) {
        $number /= 10;
        $multiplier *= 10;
    }
    return round($number, $sigdigs) * $multiplier;
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.round&repo=en&redirect=https://www.php.net/manual/en/function.round.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google