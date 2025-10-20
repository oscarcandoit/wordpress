---
url: https://www.php.net/manual/en/language.types.integer.php
scraped_at: 2025-10-20T02:32:53.772Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Integers [¶](https://www.php.net/manual/en/language.types.integer.php\#language.types.integer)

An [int](https://www.php.net/manual/en/language.types.integer.php) is a number of the set
ℤ = {..., -2, -1, 0, 1, 2, ...}.


### See Also

- [Floating point numbers](https://www.php.net/manual/en/language.types.float.php)
- [Arbitrary precision / BCMath](https://www.php.net/manual/en/book.bc.php)
- [Arbitrary length integer / GMP](https://www.php.net/manual/en/book.gmp.php)

### Syntax [¶](https://www.php.net/manual/en/language.types.integer.php\#language.types.integer.syntax)

[Int](https://www.php.net/manual/en/language.types.integer.php)s can be specified in decimal (base 10), hexadecimal
(base 16), octal (base 8) or binary (base 2) notation.
The [negation operator](https://www.php.net/manual/en/language.operators.arithmetic.php)
can be used to denote a negative [int](https://www.php.net/manual/en/language.types.integer.php).


To use octal notation, precede the number with a `0` (zero).
As of PHP 8.1.0, octal notation can also be preceded with `0o` or `0O`.
To use hexadecimal notation precede the number with `0x`.
To use binary notation precede the number with `0b`.


As of PHP 7.4.0, integer literals may contain underscores ( `_`) between digits,
for better readability of literals. These underscores are removed by PHP's scanner.


**Example #1 Integer literals**

`<?php
$a = 1234; // decimal number
$a = 0123; // octal number (equivalent to 83 decimal)
$a = 0o123; // octal number (as of PHP 8.1.0)
$a = 0x1A; // hexadecimal number (equivalent to 26 decimal)
$a = 0b11111111; // binary number (equivalent to 255 decimal)
$a = 1_234_567; // decimal number (as of PHP 7.4.0)
?>`

Formally, the structure for [int](https://www.php.net/manual/en/language.types.integer.php) literals is as of PHP 8.1.0
(previously, the `0o` or `0O` octal
prefixes were not allowed, and prior to PHP 7.4.0 the underscores were
not allowed):


```
decimal     : [1-9][0-9]*(_[0-9]+)*
            | 0

hexadecimal : 0[xX][0-9a-fA-F]+(_[0-9a-fA-F]+)*

octal       : 0[oO]?[0-7]+(_[0-7]+)*

binary      : 0[bB][01]+(_[01]+)*

integer     : decimal
            | hexadecimal
            | octal
            | binary

```

The size of an [int](https://www.php.net/manual/en/language.types.integer.php) is platform-dependent, although a maximum
value of about two billion is the usual value (that's 32 bits signed).
64-bit platforms usually have a maximum value of about 9E18.
PHP does not support unsigned [int](https://www.php.net/manual/en/language.types.integer.php)s.
[int](https://www.php.net/manual/en/language.types.integer.php) size can be determined
using the constant **`[PHP\_INT\_SIZE](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-size)`**, maximum value using
the constant **`[PHP\_INT\_MAX](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-max)`**,
and minimum value using the constant **`[PHP\_INT\_MIN](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-min)`**.


### Integer overflow [¶](https://www.php.net/manual/en/language.types.integer.php\#language.types.integer.overflow)

If PHP encounters a number beyond the bounds of the [int](https://www.php.net/manual/en/language.types.integer.php)
type, it will be interpreted as a [float](https://www.php.net/manual/en/language.types.float.php) instead. Also, an
operation which results in a number beyond the bounds of the
[int](https://www.php.net/manual/en/language.types.integer.php) type will return a [float](https://www.php.net/manual/en/language.types.float.php) instead.


**Example #2 Integer overflow**

`<?php
$large_number = 50000000000000000000;
var_dump($large_number);         // float(5.0E+19)
var_dump(PHP_INT_MAX + 1);       // 32-bit system: float(2147483648)
                                 // 64-bit system: float(9.2233720368548E+18)
?>`

Run code

### Integer division [¶](https://www.php.net/manual/en/language.types.integer.php\#language.types.integer.division)

There is no [int](https://www.php.net/manual/en/language.types.integer.php) division operator in PHP, to achieve this
use the [intdiv()](https://www.php.net/manual/en/function.intdiv.php) function.
`1/2` yields the [float](https://www.php.net/manual/en/language.types.float.php) `0.5`.
The value can be cast to an [int](https://www.php.net/manual/en/language.types.integer.php) to round it towards zero, or
the [round()](https://www.php.net/manual/en/function.round.php) function provides finer control over rounding.


**Example #3 Divisions**

`<?php
var_dump(25/7);         // float(3.5714285714286)
var_dump((int) (25/7)); // int(3)
var_dump(round(25/7));  // float(4)
?>`

Run code

### Converting to integer [¶](https://www.php.net/manual/en/language.types.integer.php\#language.types.integer.casting)

To explicitly convert a value to [int](https://www.php.net/manual/en/language.types.integer.php), use either the
`(int)` or `(integer)` casts. However, in
most cases the cast is not needed, since a value will be automatically
converted if an operator, function or control structure requires an
[int](https://www.php.net/manual/en/language.types.integer.php) argument. A value can also be converted to
[int](https://www.php.net/manual/en/language.types.integer.php) with the [intval()](https://www.php.net/manual/en/function.intval.php) function.


If a [resource](https://www.php.net/manual/en/language.types.resource.php) is converted to an [int](https://www.php.net/manual/en/language.types.integer.php), then
the result will be the unique resource number assigned to the
[resource](https://www.php.net/manual/en/language.types.resource.php) by PHP at runtime.


See also [Type Juggling](https://www.php.net/manual/en/language.types.type-juggling.php).


#### From [booleans](https://www.php.net/manual/en/language.types.boolean.php) [¶](https://www.php.net/manual/en/language.types.integer.php\#language.types.integer.casting.from-boolean)

**`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** will yield `0` (zero), and **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** will yield
`1` (one).


#### From [floating point numbers](https://www.php.net/manual/en/language.types.float.php) [¶](https://www.php.net/manual/en/language.types.integer.php\#language.types.integer.casting.from-float)

When converting from [float](https://www.php.net/manual/en/language.types.float.php) to [int](https://www.php.net/manual/en/language.types.integer.php), the number
will be rounded _towards zero_.
As of PHP 8.1.0, a deprecation notice is emitted when implicitly converting a non-integral [float](https://www.php.net/manual/en/language.types.float.php) to [int](https://www.php.net/manual/en/language.types.integer.php) which loses precision.


**Example #4 Casting from Float**

`<?php
function foo($value): int {
return $value;
}
var_dump(foo(8.1)); // "Deprecated: Implicit conversion from float 8.1 to int loses precision" as of PHP 8.1.0
var_dump(foo(8.1)); // 8 prior to PHP 8.1.0
var_dump(foo(8.0)); // 8 in both cases
var_dump((int) 8.1); // 8 in both cases
var_dump(intval(8.1)); // 8 in both cases
?>`

Run code

If the float is beyond the boundaries of [int](https://www.php.net/manual/en/language.types.integer.php) (usually
`+/- 2.15e+9 = 2^31` on 32-bit platforms and
`+/- 9.22e+18 = 2^63` on 64-bit platforms),
the result is undefined, since the [float](https://www.php.net/manual/en/language.types.float.php) doesn't
have enough precision to give an exact [int](https://www.php.net/manual/en/language.types.integer.php) result.
No warning, not even a notice will be issued when this happens!


> **Note**:
>
>
> `NaN`, `Inf` and `-Inf` will always be zero when cast to [int](https://www.php.net/manual/en/language.types.integer.php).

**Warning**

Never cast an unknown fraction to [int](https://www.php.net/manual/en/language.types.integer.php), as this can
sometimes lead to unexpected results.


`<?php
echo (int) ( (0.1+0.7) * 10 ); // echoes 7!
?>`

Run code

See also the [warning about float\\
precision](https://www.php.net/manual/en/language.types.float.php#warn.float-precision).


#### From strings [¶](https://www.php.net/manual/en/language.types.integer.php\#language.types.integer.casting.from-string)

If the string is
[numeric](https://www.php.net/manual/en/language.types.numeric-strings.php)
or leading numeric then it will resolve to the
corresponding integer value, otherwise it is converted to zero
( `0`).


#### From [NULL](https://www.php.net/manual/en/language.types.null.php) [¶](https://www.php.net/manual/en/language.types.integer.php\#language.types.integer.casting-from-null)

**`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** is always converted to zero ( `0`).


#### From other types [¶](https://www.php.net/manual/en/language.types.integer.php\#language.types.integer.casting.from-other)

**Caution**

The behaviour of converting to [int](https://www.php.net/manual/en/language.types.integer.php) is undefined for other
types. Do _not_ rely on any observed behaviour, as it
can change without notice.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/integer.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.integer%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.integer&repo=en&redirect=https://www.php.net/manual/en/language.types.integer.php)

### User Contributed Notes 9 notes

[up](https://www.php.net/manual/vote-note.php?id=111523&page=language.types.integer&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111523&page=language.types.integer&vote=down "Vote down!")

131


[**_php at richardneill dot org_**](https://www.php.net/manual/en/language.types.integer.php#111523) [¶](https://www.php.net/manual/en/language.types.integer.php#111523)

**12 years ago**

`A leading zero in a numeric literal means "this is octal". But don't be confused: a leading zero in a string does not. Thus:
$x = 0123;          // 83
$y = "0123" + 0     // 123`

[up](https://www.php.net/manual/vote-note.php?id=77056&page=language.types.integer&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77056&page=language.types.integer&vote=down "Vote down!")

55


[**_d\_n at NOSPAM dot Loryx dot com_**](https://www.php.net/manual/en/language.types.integer.php#77056) [¶](https://www.php.net/manual/en/language.types.integer.php#77056)

**18 years ago**

`Here are some tricks to convert from a "dotted" IP address to a LONG int, and backwards. This is very useful because accessing an IP addy in a database table is very much faster if it's stored as a BIGINT rather than in characters.
IP to BIGINT:
<?php
$ipArr    = explode('.',$_SERVER['REMOTE_ADDR']);
$ip       = $ipArr[0] * 0x1000000
            + $ipArr[1] * 0x10000
            + $ipArr[2] * 0x100
            + $ipArr[3]
            ;
?>
IP as BIGINT read from db back to dotted form:
Keep in mind, PHP integer operators are INTEGER -- not long. Also, since there is no integer divide in PHP, we save a couple of S-L-O-W floor (<division>)'s by doing bitshifts. We must use floor(/) for $ipArr[0] because though $ipVal is stored as a long value, $ipVal >> 24 will operate on a truncated, integer value of $ipVal! $ipVint is, however, a nice integer, so
we can enjoy the bitshifts.
<?php
        $ipVal = $row['client_IP'];
        $ipArr = array(0 =>
                    floor(  $ipVal               / 0x1000000) );
        $ipVint   = $ipVal-($ipArr[0]*0x1000000); // for clarity
        $ipArr[1] = ($ipVint & 0xFF0000)  >> 16;
        $ipArr[2] = ($ipVint & 0xFF00  )  >> 8;
        $ipArr[3] =  $ipVint & 0xFF;
        $ipDotted = implode('.', $ipArr);
?>`

[up](https://www.php.net/manual/vote-note.php?id=125251&page=language.types.integer&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125251&page=language.types.integer&vote=down "Vote down!")

13


[**_ganlvtech at qq dot com_**](https://www.php.net/manual/en/language.types.integer.php#125251) [¶](https://www.php.net/manual/en/language.types.integer.php#125251)

**5 years ago**

`Be aware of float to int cast overflow
<?php
// You may expected these
var_dump(0x7fffffffffffffff);                // int(9223372036854775807)
var_dump(0x7fffffffffffffff + 1);            // float(9.2233720368548E+18)
var_dump((int)(0x7fffffffffffffff + 1));     // int(9223372036854775807)
var_dump(0x7fffffffffffffff + 1 > 0);        // bool(true)
var_dump((int)(0x7fffffffffffffff + 1) > 0); // bool(true)
var_dump((int)'9223372036854775807');        // int(9223372036854775807)
var_dump(9223372036854775808);               // float(9.2233720368548E+18)
var_dump((int)'9223372036854775808');        // int(9223372036854775807)
var_dump((int)9223372036854775808);          // int(9223372036854775807)
// But actually, it likes these
var_dump(0x7fffffffffffffff);                // int(9223372036854775807)
var_dump(0x7fffffffffffffff + 1);            // float(9.2233720368548E+18)
var_dump((int)(0x7fffffffffffffff + 1));     // int(-9223372036854775808)   <-----
var_dump(0x7fffffffffffffff + 1 > 0);        // bool(true)
var_dump((int)(0x7fffffffffffffff + 1) > 0); // bool(false)                 <-----
var_dump((int)'9223372036854775807');        // int(9223372036854775807)
var_dump(9223372036854775808);               // float(9.2233720368548E+18)
var_dump((int)'9223372036854775808');        // int(9223372036854775807)
var_dump((int)9223372036854775808);          // int(-9223372036854775808)   <-----
?>
These overflows are dangerous when you try to compare it with zero, or substract it from another value (e.g. money).`

[up](https://www.php.net/manual/vote-note.php?id=121917&page=language.types.integer&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121917&page=language.types.integer&vote=down "Vote down!")

17


[**_egwayjen at gmail dot com_**](https://www.php.net/manual/en/language.types.integer.php#121917) [¶](https://www.php.net/manual/en/language.types.integer.php#121917)

**7 years ago**

`"There is no integer division operator in PHP". But since PHP 7, there is the intdiv function.`

[up](https://www.php.net/manual/vote-note.php?id=121886&page=language.types.integer&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121886&page=language.types.integer&vote=down "Vote down!")

13


[**_dhairya lakhera_**](https://www.php.net/manual/en/language.types.integer.php#121886) [¶](https://www.php.net/manual/en/language.types.integer.php#121886)

**7 years ago**

`-------------------------------------------------------------------------
Question :
var_dump((int) 010);  //Output 8
var_dump((int) "010"); //output 10
First one is octal notation so the output is correct. But what about the when converting "010" to integer. it should be also output 8 ?
--------------------------------------------------------------------------
Answer :
Casting to an integer using (int) will always cast to the default base, which is 10.
Casting a string to a number this way does not take into account the many ways of formatting an integer value in PHP (leading zero for base 8, leading "0x" for base 16, leading "0b" for base 2). It will simply look at the first characters in a string and convert them to a base 10 integer. Leading zeroes will be stripped off because they have no meaning in numerical values, so you will end up with the decimal value 10 for (int)"010".
Converting an integer value between bases using (int)010 will take into account the various ways of formatting an integer. A leading zero like in 010 means the number is in octal notation, using (int)010 will convert it to the decimal value 8 in base 10.
This is similar to how you use 0x10 to write in hexadecimal (base 16) notation. Using (int)0x10 will convert that to the base 10 decimal value 16, whereas using (int)"0x10" will end up with the decimal value 0: since the "x" is not a numerical value, anything after that will be ignored.
If you want to interpret the string "010" as an octal value, you need to instruct PHP to do so. intval("010", 8) will interpret the number in base 8 instead of the default base 10, and you will end up with the decimal value 8. You could also use octdec("010") to convert the octal string to the decimal value 8. Another option is to use base_convert("010", 8, 10) to explicitly convert the number "010" from base 8 to base 10, however this function will return the string "8" instead of the integer 8.
Casting a string to an integer follows the same the logic used by the intval function:
Returns the integer value of var, using the specified base for the conversion (the default is base 10).
intval allows specifying a different base as the second argument, whereas a straight cast operation does not, so using (int) will always treat a string as being in base 10.
php > var_export((int) "010");
10
php > var_export(intval("010"));
10
php > var_export(intval("010", 8));
8`

[up](https://www.php.net/manual/vote-note.php?id=116479&page=language.types.integer&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116479&page=language.types.integer&vote=down "Vote down!")

7


[**_Anonymous_**](https://www.php.net/manual/en/language.types.integer.php#116479) [¶](https://www.php.net/manual/en/language.types.integer.php#116479)

**10 years ago**

`Converting to an integer works only if the input begins with a number
(int) "5txt" // will output the integer 5
(int) "before5txt" // will output the integer 0
(int) "53txt" // will output the integer 53
(int) "53txt534text" // will output the integer 53`

[up](https://www.php.net/manual/vote-note.php?id=73766&page=language.types.integer&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73766&page=language.types.integer&vote=down "Vote down!")

7


[**_Anonymous_**](https://www.php.net/manual/en/language.types.integer.php#73766) [¶](https://www.php.net/manual/en/language.types.integer.php#73766)

**18 years ago**

`To force the correct usage of 32-bit unsigned integer in some functions, just add '+0'  just before processing them.
for example
echo(dechex("2724838310"));
will print '7FFFFFFF'
but it should print 'A269BBA6'
When adding '+0' php will handle the 32bit unsigned integer
correctly
echo(dechex("2724838310"+0));
will print 'A269BBA6'`

[up](https://www.php.net/manual/vote-note.php?id=71709&page=language.types.integer&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=71709&page=language.types.integer&vote=down "Vote down!")

5


[**_rustamabd@gmail-you-know-what_**](https://www.php.net/manual/en/language.types.integer.php#71709) [¶](https://www.php.net/manual/en/language.types.integer.php#71709)

**18 years ago**

`Be careful with using the modulo operation on big numbers, it will cast a float argument to an int and may return wrong results. For example:
<?php
    $i = 6887129852;
    echo "i=$i\n";
    echo "i%36=".($i%36)."\n";
    echo "alternative i%36=".($i-floor($i/36)*36)."\n";
?>
Will output:
i=6.88713E+009
i%36=-24
alternative i%36=20`

[up](https://www.php.net/manual/vote-note.php?id=118903&page=language.types.integer&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118903&page=language.types.integer&vote=down "Vote down!")

 -1


[**_litbai_**](https://www.php.net/manual/en/language.types.integer.php#118903) [¶](https://www.php.net/manual/en/language.types.integer.php#118903)

**9 years ago**

`<?php
$ipArr = explode('.', $ipString);
$ipVal = ($ipArr[0] << 24)
       + ($ipArr[1] << 16)
       + ($ipArr[2] << 8)
       + $ipArr[3]
        ;
?>
1. the priority of bit op is lower than '+',so there should be brackets.
2. there is no unsighed int in PHP, if you use 32 bit version，the code above will get negative result when the first position of IP string greater than 127.
3. what the code actually do is calculate the integer value of transformed 32 binary bit from IP string.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.integer&repo=en&redirect=https://www.php.net/manual/en/language.types.integer.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google