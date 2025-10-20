---
url: https://www.php.net/manual/en/language.operators.precedence.php
scraped_at: 2025-10-20T02:30:54.471Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Operator Precedence [¶](https://www.php.net/manual/en/language.operators.precedence.php\#language.operators.precedence)

The precedence of an operator specifies how "tightly" it binds two
expressions together. For example, in the expression `1 +
5 * 3`, the answer is `16` and not
`18` because the multiplication ("\*") operator
has a higher precedence than the addition ("+") operator.
Parentheses may be used to force precedence, if necessary. For
instance: `(1 + 5) * 3` evaluates to
`18`.


When operators have equal precedence their associativity decides
how the operators are grouped. For example "-" is left-associative, so
`1 - 2 - 3` is grouped as `(1 - 2) - 3`
and evaluates to `-4`. "=" on the other hand is
right-associative, so `$a = $b = $c` is grouped as
`$a = ($b = $c)`.


Operators of equal precedence that are non-associative cannot be used
next to each other, for example `1 < 2 > 1` is
illegal in PHP. The expression `1 <= 1 == 1` on the
other hand is legal, because the `==` operator has a lower
precedence than the `<=` operator.


Associativity is only meaningful for binary (and ternary) operators.
Unary operators are either prefix or postfix so this notion is not applicable.
For example `!!$a` can only be grouped as `!(!$a)`.


Use of parentheses, even when not strictly necessary, can often increase
readability of the code by making grouping explicit rather than relying
on the implicit operator precedence and associativity.


The following table lists the operators in order of precedence, with
the highest-precedence ones at the top. Operators on the same line
have equal precedence, in which case associativity decides grouping.


| Associativity | Operators | Additional Information |
| --- | --- | --- |
| (n/a) | `clone` `new` | [clone](https://www.php.net/manual/en/language.oop5.cloning.php) and [new](https://www.php.net/manual/en/language.oop5.basic.php#language.oop5.basic.new) |
| right | `**` | [arithmetic](https://www.php.net/manual/en/language.operators.arithmetic.php) |
| (n/a) | `+` `-` `++` `--` `~` `(int)` `(float)` `(string)` `(array)` `(object)` `(bool)` `@` | [arithmetic](https://www.php.net/manual/en/language.operators.arithmetic.php) (unary `+` and `-`),<br> [increment/decrement](https://www.php.net/manual/en/language.operators.increment.php),<br> [bitwise](https://www.php.net/manual/en/language.operators.bitwise.php),<br> [type casting](https://www.php.net/manual/en/language.types.type-juggling.php#language.types.typecasting) and<br> [error control](https://www.php.net/manual/en/language.operators.errorcontrol.php) |
| left | `instanceof` | [type](https://www.php.net/manual/en/language.operators.type.php) |
| (n/a) | `!` | [logical](https://www.php.net/manual/en/language.operators.logical.php) |
| left | `*` `/` `%` | [arithmetic](https://www.php.net/manual/en/language.operators.arithmetic.php) |
| left | `+` `-` `.` | [arithmetic](https://www.php.net/manual/en/language.operators.arithmetic.php) (binary `+` and `-`),<br> [array](https://www.php.net/manual/en/language.operators.array.php) and<br> [string](https://www.php.net/manual/en/language.operators.string.php) ( `.` prior to PHP 8.0.0) |
| left | `<<` `>>` | [bitwise](https://www.php.net/manual/en/language.operators.bitwise.php) |
| left | `.` | [string](https://www.php.net/manual/en/language.operators.string.php) (as of PHP 8.0.0) |
| non-associative | `<` `<=` `>` `>=` | [comparison](https://www.php.net/manual/en/language.operators.comparison.php) |
| non-associative | `==` `!=` `===` `!==` `<>` `<=>` | [comparison](https://www.php.net/manual/en/language.operators.comparison.php) |
| left | `&` | [bitwise](https://www.php.net/manual/en/language.operators.bitwise.php) and<br> [references](https://www.php.net/manual/en/language.references.php) |
| left | `^` | [bitwise](https://www.php.net/manual/en/language.operators.bitwise.php) |
| left | `|` | [bitwise](https://www.php.net/manual/en/language.operators.bitwise.php) |
| left | `&&` | [logical](https://www.php.net/manual/en/language.operators.logical.php) |
| left | `||` | [logical](https://www.php.net/manual/en/language.operators.logical.php) |
| right | `??` | [null coalescing](https://www.php.net/manual/en/language.operators.comparison.php#language.operators.comparison.coalesce) |
| non-associative | `? :` | [ternary](https://www.php.net/manual/en/language.operators.comparison.php#language.operators.comparison.ternary)<br> (left-associative prior to PHP 8.0.0) |
| right | `=` `+=` `-=` `*=` `**=` `/=` `.=` `%=` `&=` `|=` `^=` `<<=` `>>=` `??=` | [assignment](https://www.php.net/manual/en/language.operators.assignment.php) |
| (n/a) | `yield from` | [yield from](https://www.php.net/manual/en/language.generators.syntax.php#control-structures.yield.from) |
| (n/a) | `yield` | [yield](https://www.php.net/manual/en/language.generators.syntax.php#control-structures.yield) |
| (n/a) | `print` | [print](https://www.php.net/manual/en/function.print.php) |
| left | `and` | [logical](https://www.php.net/manual/en/language.operators.logical.php) |
| left | `xor` | [logical](https://www.php.net/manual/en/language.operators.logical.php) |
| left | `or` | [logical](https://www.php.net/manual/en/language.operators.logical.php) |

**Operator Precedence**

**Example #1 Associativity**

`<?php
$a = 3 * 3 % 5; // (3 * 3) % 5 = 4
var_dump($a);
$a = 1;
$b = 2;
$a = $b += 3; // $a = ($b += 3) -> $a = 5, $b = 5
var_dump($a, $b);
?>`

Run code

The ternary operator specifically requires the use of parenthesis to
disambiguate precedence.


**Example #2 Explicit Precedence**

`<?php
$a = true ? 0 : (true ? 1 : 2);
var_dump($a);
// this is not allowed since PHP 8
// $a = true ? 0 : true ? 1 : 2;
?>`

Run code

Operator precedence and associativity only determine how expressions
are grouped, they do not specify an order of evaluation. PHP does not
(in the general case) specify in which order an expression is evaluated
and code that assumes a specific order of evaluation should be avoided,
because the behavior can change between versions of PHP or depending on
the surrounding code.


**Example #3 Undefined order of evaluation**

`<?php
$a = 1;
echo $a + $a++; // may print either 2 or 3
$i = 1;
$array[$i] = $i++; // may set either index 1 or 2
?>`

**Example #4 `+`, `-` and `.` precedence**

`<?php
$x = 4;
// this line might result in unexpected output:
echo "x minus one equals " . $x-1 . ", or so I hope\n";
// the desired precedence can be enforced by using parentheses:
echo "x minus one equals " . ($x-1) . ", or so I hope\n";
// this is not allowed, and throws a TypeError:
echo (("x minus one equals " . $x) - 1) . ", or so I hope\n";
?>`

Run code

The above example will output:

```
-1, or so I hope
-1, or so I hope
Fatal error: Uncaught TypeError: Unsupported operand types: string - int

```

**Example #5 Prior to PHP 8, `+`, `-` and `.` had the same precedence**

`<?php
$x = 4;
// this line might result in unexpected output:
echo "x minus one equals " . $x-1 . ", or so I hope\n";
// because it is evaluated like this line (prior to PHP 8.0.0):
echo (("x minus one equals " . $x) - 1) . ", or so I hope\n";
// the desired precedence can be enforced by using parentheses:
echo "x minus one equals " . ($x-1) . ", or so I hope\n";
?>`

The above example will output:

```
-1, or so I hope
-1, or so I hope
x minus one equals 3, or so I hope

```

> **Note**:
>
>
> Although `=` has a lower precedence than
> most other operators, PHP will still allow expressions
> similar to the following: `if (!$a = foo())`,
> in which case the return value of `foo()` is
> put into $a.

### Changelog

| Version | Description |
| --- | --- |
| 8.0.0 | String concatenation ( `.`) now has a lower precedence than<br> arithmetic addition/subtraction ( `+` and `-`) and<br> bitwise shift left/right ( `<<` and `>>`);<br> previously it had the same precedence as `+` and `-`<br> and a higher precedence than `<<` and `>>`. |
| 8.0.0 | The ternary operator ( `? :`) is non-associative now;<br> previously it was left-associative. |
| 7.4.0 | Relying on the precedence of string concatenation ( `.`) relative to<br> arithmetic addition/subtraction ( `+` or `-`) or<br> bitwise shift left/right ( `<<` or `>>`),<br> i.e. using them together in an unparenthesized expression, is deprecated. |
| 7.4.0 | Relying on left-associativity of the ternary operator ( `? :`),<br> i.e. nesting multiple unparenthesized ternary operators, is deprecated. |

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/operators/precedence.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.operators.precedence%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.precedence&repo=en&redirect=https://www.php.net/manual/en/language.operators.precedence.php)

### User Contributed Notes 8 notes

[up](https://www.php.net/manual/vote-note.php?id=117390&page=language.operators.precedence&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117390&page=language.operators.precedence&vote=down "Vote down!")

243


[**_fabmlk_**](https://www.php.net/manual/en/language.operators.precedence.php#117390) [¶](https://www.php.net/manual/en/language.operators.precedence.php#117390)

**10 years ago**

`Watch out for the difference of priority between 'and vs &&' or '|| vs or':
<?php
$bool = true && false;
var_dump($bool); // false, that's expected
$bool = true and false;
var_dump($bool); // true, ouch!
?>
Because 'and/or' have lower priority than '=' but '||/&&' have higher.`

[up](https://www.php.net/manual/vote-note.php?id=128174&page=language.operators.precedence&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128174&page=language.operators.precedence&vote=down "Vote down!")

9


[**_rvwoens at gmail dot com_**](https://www.php.net/manual/en/language.operators.precedence.php#128174) [¶](https://www.php.net/manual/en/language.operators.precedence.php#128174)

**2 years ago**

`Note that ?? has a low priority, so this can lead to unexpected results:
$a=[];
$a['aa']??'not set'
--> not set (as expected)
but
"lets see if it is set".$a['aa']??'not set'
--> notice; undefined index aa
--> lets see if it is set
so you need to use parenthesis
"lets see if it is set".($a['aa']??'not set')`

[up](https://www.php.net/manual/vote-note.php?id=121509&page=language.operators.precedence&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121509&page=language.operators.precedence&vote=down "Vote down!")

48


[**_aaronw at catalyst dot net dot nz_**](https://www.php.net/manual/en/language.operators.precedence.php#121509) [¶](https://www.php.net/manual/en/language.operators.precedence.php#121509)

**8 years ago**

`If you've come here looking for a full list of PHP operators, take note that the table here is *not* complete. There are some additional operators (or operator-ish punctuation tokens) that are not included here, such as "->", "::", and "...".
For a really comprehensive list, take a look at the "List of Parser Tokens" page: [http://php.net/manual/en/tokens.php](http://php.net/manual/en/tokens.php)`

[up](https://www.php.net/manual/vote-note.php?id=109325&page=language.operators.precedence&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109325&page=language.operators.precedence&vote=down "Vote down!")

52


[**_Carsten Milkau_**](https://www.php.net/manual/en/language.operators.precedence.php#109325) [¶](https://www.php.net/manual/en/language.operators.precedence.php#109325)

**13 years ago**

`Beware the unusual order of bit-wise operators and comparison operators, this has often lead to bugs in my experience. For instance:
<?php if ( $flags & MASK  == 1) do_something(); ?>
will not do what you might expect from other languages. Use
<?php if (($flags & MASK) == 1) do_something(); ?>
in PHP instead.`

[up](https://www.php.net/manual/vote-note.php?id=126388&page=language.operators.precedence&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126388&page=language.operators.precedence&vote=down "Vote down!")

6


[**_tlili dot mokhtar at gmail dot com_**](https://www.php.net/manual/en/language.operators.precedence.php#126388) [¶](https://www.php.net/manual/en/language.operators.precedence.php#126388)

**4 years ago**

`An easy trick to get the result of the left shift operation (<<), e.g.
15 << 2 = 15 * (2*2) = 60
15 << 3 = 15 * (2*2*2) = 120
15 << 5 = 15 * (2*2*2*2*2) = 480
and so on...
So it's:
(number on left) multiplied by (number on right) times 2.
The same goes for the right shift operator (>>), where:
(number on left) divided by (number on right) times 2 e.g.
15 >> 2 = (15/2)/2 = 7/2 = 3 (use floor values if result is in decimals).
35 >> 3 = (((35/2)/2)/2 = (17/2)/2 = 8/2 = 4`

[up](https://www.php.net/manual/vote-note.php?id=127888&page=language.operators.precedence&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127888&page=language.operators.precedence&vote=down "Vote down!")

5


[**_sangala at seznam dot cz_**](https://www.php.net/manual/en/language.operators.precedence.php#127888) [¶](https://www.php.net/manual/en/language.operators.precedence.php#127888)

**2 years ago**

`Using cast and ternary operator can be unclear,
(Useful to know with: declare(strict_types = 1) ).
<?php
$num_str="5";
$i1 = (int)  isset($num_str) ? $num_str : 0;
$i2 = (int) (isset($num_str) ? $num_str : 0);
var_dump($i1);
var_dump($i2);
?>
Output:
string(1) "5"
int(5)`

[up](https://www.php.net/manual/vote-note.php?id=121011&page=language.operators.precedence&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121011&page=language.operators.precedence&vote=down "Vote down!")

12


[**_ivan at dilber dot info_**](https://www.php.net/manual/en/language.operators.precedence.php#121011) [¶](https://www.php.net/manual/en/language.operators.precedence.php#121011)

**8 years ago**

`<?php
// Another tricky thing here is using && or || with ternary ?:
$x && $y ? $a : $b;  // ($x && $y) ? $a : $b;
// while:
$x and $y ? $a : $b;  // $x and ($y ? $a : $b);
?>`

[up](https://www.php.net/manual/vote-note.php?id=125846&page=language.operators.precedence&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125846&page=language.operators.precedence&vote=down "Vote down!")

3


[**_instatiendaweb at gmail dot com_**](https://www.php.net/manual/en/language.operators.precedence.php#125846) [¶](https://www.php.net/manual/en/language.operators.precedence.php#125846)

**4 years ago**

``//incorrect
$a = true ? 0 : true ? 1 : 2; // (true ? 0 : true) ? 1 : 2 = 2
//Unparenthesized `a ? b : c ? d : e` is not supported. Use either `(a ? b : c) ? d : e` or `a ? b : (c ? d : e)`
//correct
$a = (true ? 0 : true) ? 1 : 2; // (true ? 0 : true) ? 1 : 2 = 2
==> correction documentation.``

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.precedence&repo=en&redirect=https://www.php.net/manual/en/language.operators.precedence.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google