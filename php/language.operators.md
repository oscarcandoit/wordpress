---
url: https://www.php.net/manual/en/language.operators.php
scraped_at: 2025-10-20T02:32:26.083Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Operators [¶](https://www.php.net/manual/en/language.operators.php\#language.operators)

## Table of Contents [¶](https://www.php.net/manual/en/language.operators.php\#language.operators)

- [Operator Precedence](https://www.php.net/manual/en/language.operators.precedence.php)
- [Arithmetic](https://www.php.net/manual/en/language.operators.arithmetic.php)
- [Increment and Decrement](https://www.php.net/manual/en/language.operators.increment.php)
- [Assignment](https://www.php.net/manual/en/language.operators.assignment.php)
- [Bitwise](https://www.php.net/manual/en/language.operators.bitwise.php)
- [Comparison](https://www.php.net/manual/en/language.operators.comparison.php)
- [Error Control](https://www.php.net/manual/en/language.operators.errorcontrol.php)
- [Execution](https://www.php.net/manual/en/language.operators.execution.php)
- [Logic](https://www.php.net/manual/en/language.operators.logical.php)
- [String](https://www.php.net/manual/en/language.operators.string.php)
- [Array](https://www.php.net/manual/en/language.operators.array.php)
- [Type](https://www.php.net/manual/en/language.operators.type.php)
- [Functional](https://www.php.net/manual/en/language.operators.functional.php)

An operator is something that takes one or more values (or
expressions, in programming jargon) and yields another value (so that the
construction itself becomes an expression).


Operators can be grouped according to the number of values they take. Unary
operators take only one value, for example `!` (the
[logical not operator](https://www.php.net/manual/en/language.operators.logical.php)) or
`++` (the
[increment operator](https://www.php.net/manual/en/language.operators.increment.php)).
Binary operators take two values, such as the familiar
[arithmetical operators](https://www.php.net/manual/en/language.operators.arithmetic.php) `+` (plus) and `-` (minus), and the
majority of PHP operators fall into this category. Finally, there is a
single [ternary\\
operator](https://www.php.net/manual/en/language.operators.comparison.php#language.operators.comparison.ternary), `? :`, which takes three values; this is
usually referred to simply as "the ternary operator" (although it could
perhaps more properly be called the conditional operator).


A full list of PHP operators follows in the section
[Operator Precedence](https://www.php.net/manual/en/language.operators.precedence.php).
The section also explains operator precedence and associativity, which govern
exactly how expressions containing several different operators are
evaluated.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/operators.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.operators%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators&repo=en&redirect=https://www.php.net/manual/en/language.operators.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=43111&page=language.operators&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=43111&page=language.operators&vote=down "Vote down!")

238


[**_Anonymous_**](https://www.php.net/manual/en/language.operators.php#43111) [¶](https://www.php.net/manual/en/language.operators.php#43111)

**21 years ago**

`of course this should be clear, but i think it has to be mentioned espacially:
AND is not the same like &&
for example:
<?php $a && $b || $c; ?>
is not the same like
<?php $a AND $b || $c; ?>
the first thing is
(a and b) or c
the second
a and (b or c)
'cause || has got a higher priority than and, but less than &&
of course, using always [ && and || ] or [ AND and OR ] would be okay, but than you should at least respect the following:
<?php $a = $b && $c; ?>
<?php $a = $b AND $c; ?>
the first code will set $a to the result of the comparison $b with $c, both have to be true, while the second code line will set $a like $b and THAN - after that - compare the success of this with the value of $c
maybe usefull for some tricky coding and helpfull to prevent bugs :D
greetz, Warhog`

[up](https://www.php.net/manual/vote-note.php?id=125373&page=language.operators&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125373&page=language.operators&vote=down "Vote down!")

52


[**_anisgazig at gmail dot com_**](https://www.php.net/manual/en/language.operators.php#125373) [¶](https://www.php.net/manual/en/language.operators.php#125373)

**5 years ago**

```Operator are used to perform operation.
Operator are mainly divided by three groups.
1.Uniary Operators that takes one values
2.Binary Operators that takes two values
3.ternary operators that takes three values
Operator are mainly divided by three groups that are totally seventeen types.
1.Arithmetic Operator
+ = Addition
- = Subtraction
* = Multiplication
/ = Division
% = Modulo
** = Exponentiation
2.Assignment Operator
     = "equal to
3.Array Operator
    + = Union
    == = Equality
    === = Identity
    != = Inequality
    <> = Inequality
    !== =    Non-identity
4.Bitwise Operator
& = and
^ = xor
| = not
<< = shift left
>> = shift right
5.Comparison Operator
==  = equal
=== = identical
!=  = not equal
!== = not identical
<>  = not equal
< = less than
<= less than or equal
> = greater than
>= = greater than or equal
<=> = spaceship operator
6.Execution Operator
 `` = backticks
7.Error Control Operator
    @ = at sign
8.Incrementing/Decrementing Operator
    ++$a = PreIncrement
    $a++ = PostIncrement
    --$a = PreDecrement
    $a-- = Postdecrement
9.Logical Operator
    && = And
    || = Or
    ! = Not
    and = And
    xor = Xor
    or = Or
10.string Operator
    . =  concatenation operator
    .= concatenating assignment operator
11.Type Operator
    instanceof = instanceof
12.Ternary or Conditional operator
   ?: = Ternary operator
13.Null Coalescing Operator
    ??" = null coalescing
14.Clone new Operator
    clone new = clone new
15.yield from Operator
    yield from = yield from
16.yield Operator
    yield = yield
17.print Operator
    print = print```

[up](https://www.php.net/manual/vote-note.php?id=12147&page=language.operators&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=12147&page=language.operators&vote=down "Vote down!")

15


[**_yasuo\_ohgaki at hotmail dot com_**](https://www.php.net/manual/en/language.operators.php#12147) [¶](https://www.php.net/manual/en/language.operators.php#12147)

**24 years ago**

`Other Language books' operator precedence section usually include "(" and ")" - with exception of a Perl book that I have. (In PHP "{" and "}" should also be considered also). However, PHP Manual is not listed "(" and ")" in precedence list. It looks like "(" and ")" has higher precedence as it should be.
Note: If you write following code, you would need "()" to get expected value.
<?php
$bar = true;
$str = "TEST". ($bar ? 'true' : 'false') ."TEST";
?>
Without "(" and ")" you will get only "true" in $str.
(PHP4.0.4pl1/Apache DSO/Linux, PHP4.0.5RC1/Apache DSO/W2K Server)
It's due to precedence, probably.`

[up](https://www.php.net/manual/vote-note.php?id=84862&page=language.operators&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84862&page=language.operators&vote=down "Vote down!")

5


[**_figroc at gmail dot com_**](https://www.php.net/manual/en/language.operators.php#84862) [¶](https://www.php.net/manual/en/language.operators.php#84862)

**17 years ago**

`The variable symbol '$' should be considered as the highest-precedence operator, so that the variable variables such as $$a[0] won't confuse the parser.  [ [http://www.php.net/manual/en/language.variables.variable.php\]](http://www.php.net/manual/en/language.variables.variable.php])`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators&repo=en&redirect=https://www.php.net/manual/en/language.operators.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google