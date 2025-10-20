---
url: https://www.php.net/manual/en/language.operators.increment.php
scraped_at: 2025-10-20T02:39:27.176Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Incrementing/Decrementing Operators [¶](https://www.php.net/manual/en/language.operators.increment.php\#language.operators.increment)

PHP supports pre- and post-increment and decrement operators.
Those unary operators allow to increment or decrement the value by one.


| Example | Name | Effect |
| --- | --- | --- |
| ++$a | Pre-increment | Increments $a by one, then returns $a. |
| $a++ | Post-increment | Returns $a, then increments $a by one. |
| --$a | Pre-decrement | Decrements $a by one, then returns $a. |
| $a-- | Post-decrement | Returns $a, then decrements $a by one. |

**Increment/decrement Operators**

**Example #1 Examples of Increment/Decrement**

`<?php
echo 'Post-increment:', PHP_EOL;
$a = 5;
var_dump($a++);
var_dump($a);
echo 'Pre-increment:', PHP_EOL;
$a = 5;
var_dump(++$a);
var_dump($a);
echo 'Post-decrement:', PHP_EOL;
$a = 5;
var_dump($a--);
var_dump($a);
echo 'Pre-decrement:', PHP_EOL;
$a = 5;
var_dump(--$a);
var_dump($a);
?>`

Run code

The above example will output:

```
Post-increment:
int(5)
int(6)
Pre-increment:
int(6)
int(6)
Post-decrement:
int(5)
int(4)
Pre-decrement:
int(4)
int(4)

```

**Warning**

The increment and decrement operators have no effect on values
of type [bool](https://www.php.net/manual/en/language.types.boolean.php).
A **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is emitted as of PHP 8.3.0,
because this will implicitly cast the value to [int](https://www.php.net/manual/en/language.types.integer.php) in the future.


The decrement operator has no effect on values
of type [null](https://www.php.net/manual/en/language.types.null.php).
A **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is emitted as of PHP 8.3.0,
because this will implicitly cast the value to [int](https://www.php.net/manual/en/language.types.integer.php) in the future.


The decrement operator has no effect on non-
[numeric string](https://www.php.net/manual/en/language.types.numeric-strings.php).
A **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is emitted as of PHP 8.3.0,
because a [TypeError](https://www.php.net/manual/en/class.typeerror.php) will be thrown in the future.


> **Note**:
>
>
> Internal objects that support overloading addition and/or subtraction
> can also be incremented and/or decremented.
> One such internal object is [GMP](https://www.php.net/manual/en/class.gmp.php).

### PERL string increment feature [¶](https://www.php.net/manual/en/language.operators.increment.php\#language.operators.increment.string)

**Warning**

This feature is soft-deprecated as of PHP 8.3.0.
The [str\_increment()](https://www.php.net/manual/en/function.str-increment.php) function should be used instead.


It is possible to increment a non-
[numeric string](https://www.php.net/manual/en/language.types.numeric-strings.php)
in PHP. The string must be an alphanumerical ASCII string.
Which increments letters up to the next letter, when reaching the letter
`Z` the increment is carried to the value on the left.
For example, `$a = 'Z'; $a++;` turns $a
into `'AA'`.


**Example #2 PERL string increment example**

`<?php
echo '== Alphabetic strings ==' . PHP_EOL;
$s = 'W';
for ($n=0; $n<6; $n++) {
    echo ++$s . PHP_EOL;
}
// Alphanumeric strings behave differently
echo '== Alphanumeric strings ==' . PHP_EOL;
$d = 'A8';
for ($n=0; $n<6; $n++) {
    echo ++$d . PHP_EOL;
}
$d = 'A08';
for ($n=0; $n<6; $n++) {
    echo ++$d . PHP_EOL;
}
?>`

Run code

The above example will output:

```
== Alphabetic strings ==
X
Y
Z
AA
AB
AC
== Alphanumeric strings ==
A9
B0
B1
B2
B3
B4
A09
A10
A11
A12
A13
A14

```

**Warning**

If the alphanumerical string can be interpreted as a
[numeric string](https://www.php.net/manual/en/language.types.numeric-strings.php)
it will be cast to an [int](https://www.php.net/manual/en/language.types.integer.php) or [float](https://www.php.net/manual/en/language.types.float.php).
This is particularly an issue with strings that look like a floating point
numbers written in exponential notation.
The [str\_increment()](https://www.php.net/manual/en/function.str-increment.php) function does not suffer from
these implicit type cast.


**Example #3 Alphanumerical string converted to float**

`<?php
$s = "5d9";
var_dump(++$s);
var_dump(++$s);
?>`

Run code

The above example will output:

```
string(3) "5e0"
float(6)

```

This is because the value `"5e0"` is interpreted
as a [float](https://www.php.net/manual/en/language.types.float.php) and cast to the value `5.0`
before being incremented.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/operators/increment.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.operators.increment%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.increment&repo=en&redirect=https://www.php.net/manual/en/language.operators.increment.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=109621&page=language.operators.increment&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109621&page=language.operators.increment&vote=down "Vote down!")

67


[**_hartmut at php dot net_**](https://www.php.net/manual/en/language.operators.increment.php#109621) [¶](https://www.php.net/manual/en/language.operators.increment.php#109621)

**13 years ago**

`Note that
$a="9D9"; var_dump(++$a);   => string(3) "9E0"
but counting onwards from there
$a="9E0"; var_dump(++$a);   => float(10)
this is due to "9E0" being interpreted as a string representation of the float constant 9E0 (or 9e0), and thus evalutes to 9 * 10^0 = 9 (in a float context)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.increment&repo=en&redirect=https://www.php.net/manual/en/language.operators.increment.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google