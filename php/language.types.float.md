---
url: https://www.php.net/manual/en/language.types.float.php
scraped_at: 2025-10-20T02:33:36.227Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Floating point numbers [¶](https://www.php.net/manual/en/language.types.float.php\#language.types.float)

Floating point numbers (also known as "floats", "doubles", or "real numbers")
can be specified using any of the following syntaxes:


`<?php
$a = 1.234;
$b = 1.2e3;
$c = 7E-10;
$d = 1_234.567; // as of PHP 7.4.0
?>`

Run code

Formally as of PHP 7.4.0 (previously, underscores have not been allowed):


```
LNUM          [0-9]+(_[0-9]+)*
DNUM          ({LNUM}?"."{LNUM}) | ({LNUM}"."{LNUM}?)
EXPONENT_DNUM (({LNUM} | {DNUM}) [eE][+-]? {LNUM})

```

The size of a float is platform-dependent, although a maximum of approximately 1.8e308
with a precision of roughly 14 decimal digits is a common value (the 64 bit IEEE
format).


**Warning**

# Floating point precision

Floating point numbers have limited precision. Although it depends on the
system, PHP typically uses the IEEE 754 double precision format, which will
give a maximum relative error due to rounding in the order of 1.11e-16.
Non elementary arithmetic operations may give larger errors, and, of course,
error propagation must be considered when several operations are
compounded.


Additionally, rational numbers that are exactly representable as floating
point numbers in base 10, like `0.1` or
`0.7`, do not have an exact representation as floating
point numbers in base 2, which is used internally, no matter the size of
the mantissa. Hence, they cannot be converted into their internal binary
counterparts without a small loss of precision. This can lead to confusing
results: for example, `floor((0.1+0.7)*10)` will usually
return `7` instead of the expected `8`,
since the internal representation will be something like
`7.9999999999999991118...`.


So never trust floating number results to the last digit, and do not compare
floating point numbers directly for equality. If higher precision is
necessary, the [arbitrary precision math functions](https://www.php.net/manual/en/ref.bc.php)
and [gmp](https://www.php.net/manual/en/ref.gmp.php) functions are available.


For a "simple" explanation, see the [» floating point guide](http://floating-point-gui.de/)
that's also titled "Why don’t my numbers add up?"


### Converting to float [¶](https://www.php.net/manual/en/language.types.float.php\#language.types.float.casting)

#### From strings [¶](https://www.php.net/manual/en/language.types.float.php\#language.types.float.casting.from-string)

If the string is
[numeric](https://www.php.net/manual/en/language.types.numeric-strings.php)
or leading numeric then it will resolve to the
corresponding float value, otherwise it is converted to zero
( `0`).


#### From other types [¶](https://www.php.net/manual/en/language.types.float.php\#language.types.float.casting.from-other)

For values of other types, the conversion is performed by converting the
value to [int](https://www.php.net/manual/en/language.types.integer.php) first and then to [float](https://www.php.net/manual/en/language.types.float.php). See
[Converting to integer](https://www.php.net/manual/en/language.types.integer.php#language.types.integer.casting)
for more information.


> **Note**:
>
>
> As certain types have undefined behavior when converting to
> [int](https://www.php.net/manual/en/language.types.integer.php), this is also the case when converting to
> [float](https://www.php.net/manual/en/language.types.float.php).

### Comparing floats [¶](https://www.php.net/manual/en/language.types.float.php\#language.types.float.comparison)

As noted in the warning above, testing floating point values for equality is
problematic, due to the way that they are represented internally. However,
there are ways to make comparisons of floating point values that work around
these limitations.


To test floating point values for equality, an upper bound on the relative
error due to rounding is used. This value is known as the machine epsilon,
or unit roundoff, and is the smallest acceptable difference in calculations.


$a and $b are equal to 5 digits of
precision.


**Example #1 Comparing Floats**

`<?php
$a = 1.23456789;
$b = 1.23456780;
$epsilon = 0.00001;
if (abs($a - $b) < $epsilon) {
    echo "true";
}
?>`

Run code

### NaN [¶](https://www.php.net/manual/en/language.types.float.php\#language.types.float.nan)

Some numeric operations can result in a value represented by the constant
**`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`**. This result represents an undefined or
unrepresentable value in floating-point calculations. Any loose or strict
comparisons of this value against any other value, including itself, but except **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, will
have a result of **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


Because **`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`** represents any number of different values,
**`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`** should not be compared to other values, including
itself, and instead should be checked for using [is\_nan()](https://www.php.net/manual/en/function.is-nan.php).


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/float.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.float%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.float&repo=en&redirect=https://www.php.net/manual/en/language.types.float.php)

### User Contributed Notes 12 notes

[up](https://www.php.net/manual/vote-note.php?id=113703&page=language.types.float&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113703&page=language.types.float&vote=down "Vote down!")

263


[**_catalin dot luntraru at gmail dot com_**](https://www.php.net/manual/en/language.types.float.php#113703) [¶](https://www.php.net/manual/en/language.types.float.php#113703)

**11 years ago**

`$x = 8 - 6.4;  // which is equal to 1.6
$y = 1.6;
var_dump($x == $y); // is not true
PHP thinks that 1.6 (coming from a difference) is not equal to 1.6. To make it work, use round()
var_dump(round($x, 2) == round($y, 2)); // this is true
This happens probably because $x is not really 1.6, but 1.599999.. and var_dump shows it to you as being 1.6.`

[up](https://www.php.net/manual/vote-note.php?id=44692&page=language.types.float&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=44692&page=language.types.float&vote=down "Vote down!")

138


[**_feline at NOSPAM dot penguin dot servehttp dot com_**](https://www.php.net/manual/en/language.types.float.php#44692) [¶](https://www.php.net/manual/en/language.types.float.php#44692)

**21 years ago**

`General computing hint: If you're keeping track of money, do yourself and your users the favor of handling everything internally in cents and do as much math as you can in integers. Store values in cents if at all possible. Add and subtract in cents. At every operation that wii involve floats, ask yourself "what will happen in the real world if I get a fraction of a cent here" and if the answer is that this operation will generate a transaction in integer cents, do not try to carry fictional fractional accuracy that will only screw things up later.`

[up](https://www.php.net/manual/vote-note.php?id=29170&page=language.types.float&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=29170&page=language.types.float&vote=down "Vote down!")

66


[**_www.sarioz.com_**](https://www.php.net/manual/en/language.types.float.php#29170) [¶](https://www.php.net/manual/en/language.types.float.php#29170)

**22 years ago**

`just a comment on something the "Floating point precision" inset, which goes: "This is related to .... 0.3333333."
While the author probably knows what they are talking about, this loss of precision has nothing to do with decimal notation, it has to do with representation as a floating-point binary in a finite register, such as while 0.8 terminates in decimal, it is the repeating 0.110011001100... in binary, which is truncated.  0.1 and 0.7 are also non-terminating in binary, so they are also truncated, and the sum of these truncated numbers does not add up to the truncated binary representation of 0.8 (which is why (floor)(0.8*10) yields a different, more intuitive, result).  However, since 2 is a factor of 10, any number that terminates in binary also terminates in decimal.`

[up](https://www.php.net/manual/vote-note.php?id=30071&page=language.types.float&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=30071&page=language.types.float&vote=down "Vote down!")

19


[**_backov at spotbrokers-nospamplz dot com_**](https://www.php.net/manual/en/language.types.float.php#30071) [¶](https://www.php.net/manual/en/language.types.float.php#30071)

**22 years ago**

`I'd like to point out a "feature" of PHP's floating point support that isn't made clear anywhere here, and was driving me insane.
This test (where var_dump says that $a=0.1 and $b=0.1)
if ($a>=$b) echo "blah!";
Will fail in some cases due to hidden precision (standard C problem, that PHP docs make no mention of, so I assumed they had gotten rid of it). I should point out that I originally thought this was an issue with the floats being stored as strings, so I forced them to be floats and they still didn't get evaluated properly (probably 2 different problems there).
To fix, I had to do this horrible kludge (the equivelant of anyway):
if (round($a,3)>=round($b,3)) echo "blah!";
THIS works. Obviously even though var_dump says the variables are identical, and they SHOULD BE identical (started at 0.01 and added 0.001 repeatedly), they're not. There's some hidden precision there that was making me tear my hair out. Perhaps this should be added to the documentation?`

[up](https://www.php.net/manual/vote-note.php?id=120766&page=language.types.float&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120766&page=language.types.float&vote=down "Vote down!")

6


[**_lwiwala at gmail dot com_**](https://www.php.net/manual/en/language.types.float.php#120766) [¶](https://www.php.net/manual/en/language.types.float.php#120766)

**8 years ago**

`To compare two numbers use:
$epsilon = 1e-6;
if(abs($firstNumber-$secondNumber) < $epsilon){
// equals
}`

[up](https://www.php.net/manual/vote-note.php?id=98216&page=language.types.float&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=98216&page=language.types.float&vote=down "Vote down!")

7


[**_magicaltux at php dot net_**](https://www.php.net/manual/en/language.types.float.php#98216) [¶](https://www.php.net/manual/en/language.types.float.php#98216)

**15 years ago**

`In some cases you may want to get the maximum value for a float without getting "INF".
var_dump(1.8e308); will usually show: float(INF)
I wrote a tiny function that will iterate in order to find the biggest non-infinite float value. It comes with a configurable multiplicator and affine values so you can share more CPU to get a more accurate estimate.
I haven't seen better values with more affine, but well, the possibility is here so if you really thing it's worth the cpu time, just try to affine more.
Best results seems to be with mul=2/affine=1. You can play with the values and see what you get. The good thing is this method will work on any system.
<?php
function float_max($mul = 2, $affine = 1) {
    $max = 1; $omax = 0;
    while((string)$max != 'INF') { $omax = $max; $max *= $mul; }
    for($i = 0; $i < $affine; $i++) {
      $pmax = 1; $max = $omax;
      while((string)$max != 'INF') {
        $omax = $max;
        $max += $pmax;
        $pmax *= $mul;
      }
    }
    return $omax;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=58824&page=language.types.float&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=58824&page=language.types.float&vote=down "Vote down!")

6


[**_Luzian_**](https://www.php.net/manual/en/language.types.float.php#58824) [¶](https://www.php.net/manual/en/language.types.float.php#58824)

**19 years ago**

`Be careful when using float values in strings that are used as code later, for example when generating JavaScript code or SQL statements. The float is actually formatted according to the browser's locale setting, which means that "0.23" will result in "0,23". Imagine something like this:
$x = 0.23;
$js = "var foo = doBar($x);";
print $js;
This would result in a different result for users with some locales. On most systems, this would print:
var foo = doBar(0.23);
but when for example a user from Germany arrives, it would be different:
var foo = doBar(0,23);
which is obviously a different call to the function. JavaScript won't state an error, additional arguments are discarded without notice, but the function doBar(a) would get 0 as parameter. Similar problems could arise anywhere else (SQL, any string used as code somewhere else). The problem persists, if you use the "." operator instead of evaluating the variable in the string.
So if you REALLY need to be sure to have the string correctly formatted, use number_format() to do it!`

[up](https://www.php.net/manual/vote-note.php?id=130511&page=language.types.float&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130511&page=language.types.float&vote=down "Vote down!")

0


[**_ql at quendistudio dot com_**](https://www.php.net/manual/en/language.types.float.php#130511) [¶](https://www.php.net/manual/en/language.types.float.php#130511)

**4 days ago**

`Since actual values can vary slightly, $epsilon may not be set according to your configuration. You can replace $epsilon with PHP_FLOAT_EPSILON. There is also, in my opinion, a more elegant method for checking float equality:
<?php
// bccomp will returns 0 for equality, 1 if $value1 is greater and -1 otherwise
if (bccomp($value1, $value2) == 0) {
// equals
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=130510&page=language.types.float&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130510&page=language.types.float&vote=down "Vote down!")

0


[**_ql at quendistudio dot com_**](https://www.php.net/manual/en/language.types.float.php#130510) [¶](https://www.php.net/manual/en/language.types.float.php#130510)

**4 days ago**

`Since actual values can vary slightly, $epsilon may not be set according to your configuration. You can replace $epsilon with PHP_FLOAT_EPSILON. There is also, in my opinion, a more elegant method for checking float equality:
bccomp($value1, $value2) == 0 // bccomp will returns 0 for equality, 1 if $value1 is greater and -1 otherwise`

[up](https://www.php.net/manual/vote-note.php?id=54494&page=language.types.float&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=54494&page=language.types.float&vote=down "Vote down!")

3


[**_rick at ninjafoo dot com_**](https://www.php.net/manual/en/language.types.float.php#54494) [¶](https://www.php.net/manual/en/language.types.float.php#54494)

**20 years ago**

`Concider the following:
(19.6*100) != 1960
echo gettype(19.6*100) returns 'double', However even .....
(19.6*100) !== (double)1960
19.6*100 cannot be compaired to anything without manually
casting it as something else first.
(string)(19.6*100) == 1960
Rule of thumb, if it has a decimal point, use the BCMath functions.`

[up](https://www.php.net/manual/vote-note.php?id=31622&page=language.types.float&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=31622&page=language.types.float&vote=down "Vote down!")

3


[**_james dot cridland at virginradio dot co dot uk_**](https://www.php.net/manual/en/language.types.float.php#31622) [¶](https://www.php.net/manual/en/language.types.float.php#31622)

**22 years ago**

`The 'floating point precision' box in practice means:
<? echo (69.1-floor(69.1)); ?>
Think this'll return 0.1?
It doesn't - it returns 0.099999999999994
<? echo round((69.1-floor(69.1))); ?>
This returns 0.1 and is the workaround we use.
Note that
<? echo (4.1-floor(4.1)); ?>
*does* return 0.1 - so if you, like us, test this with low numbers, you won't, like us, understand why all of a sudden your script stops working, until you spend a lot of time, like us, debugging it.
So, that's all lovely then.`

[up](https://www.php.net/manual/vote-note.php?id=103209&page=language.types.float&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103209&page=language.types.float&vote=down "Vote down!")

0


[**_zelko at mojeime dot com_**](https://www.php.net/manual/en/language.types.float.php#103209) [¶](https://www.php.net/manual/en/language.types.float.php#103209)

**14 years ago**

`<?php
$binarydata32 = pack('H*','00000000');
$float32 = unpack("f", $binarydata32); // 0.0
$binarydata64 = pack('H*','0000000000000000');
$float64 = unpack("d", $binarydata64); // 0.0
?>
I get 0 both for 32-bit and 64-bit numbers.
But, please don't use your own "functions" to "convert" from float to binary and vice versa. Looping performance in PHP is horrible. Using pack/unpack you use processor's encoding, which is always correct. In C++ you can access the same 32/64 data as either float/double or 32/64 bit integer. No "conversions".
To get binary encoding:
<?php
$float32 = pack("f", 5300231);
$binarydata32 =unpack('H*',$float32); //"0EC0A14A"
$float64 = pack("d", 5300231);
$binarydata64 =unpack('H*',$float64); //"000000C001385441"
?>
And my example from half a year ago:
<?php
    $binarydata32 = pack('H*','0EC0A14A');
    $float32 = unpack("f", $binarydata32); // 5300231

    $binarydata64 = pack('H*','000000C001385441');
    $float64 = unpack("d", $binarydata64); // 5300231
?>
And please mind the Big and Little endian boys...`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.float&repo=en&redirect=https://www.php.net/manual/en/language.types.float.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google