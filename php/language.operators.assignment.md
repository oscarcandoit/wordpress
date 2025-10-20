---
url: https://www.php.net/manual/en/language.operators.assignment.php
scraped_at: 2025-10-20T02:35:52.243Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Assignment Operators [¶](https://www.php.net/manual/en/language.operators.assignment.php\#language.operators.assignment)

The basic assignment operator is "=". Your first inclination might
be to think of this as "equal to". Don't. It really means that the
left operand gets set to the value of the expression on the
right (that is, "gets set to").


The value of an assignment expression is the value assigned. That
is, the value of " `$a = 3`" is 3. This allows you to do some tricky
things:


**Example #1 Nested Assignments**

`<?php
$a = ($b = 4) + 5; // $a is equal to 9 now, and $b has been set to 4.
var_dump($a);
?>`

Run code

In addition to the basic assignment operator, there are "combined
operators" for all of the [binary\\
arithmetic](https://www.php.net/manual/en/language.operators.php), array union and string operators that allow you to use a value in an
expression and then set its value to the result of that expression. For
example:


**Example #2 Combined Assignments**

`<?php
$a = 3;
$a += 5; // sets $a to 8, as if we had said: $a = $a + 5;
$b = "Hello ";
$b .= "There!"; // sets $b to "Hello There!", just like $b = $b . "There!";
var_dump($a, $b);
?>`

Run code

Note that the assignment copies the original variable to the new
one (assignment by value), so changes to one will not affect the
other. This may also have relevance if you need to copy something
like a large array inside a tight loop.


An exception to the usual assignment by value behaviour within PHP occurs
with [object](https://www.php.net/manual/en/language.types.object.php)s, which are assigned by reference.
Objects may be explicitly copied via the [clone](https://www.php.net/manual/en/language.oop5.cloning.php) keyword.


### Assignment by Reference [¶](https://www.php.net/manual/en/language.operators.assignment.php\#language.operators.assignment.reference)

Assignment by reference is also supported, using the
"$var = &$othervar;" syntax.
Assignment by reference means that both variables end up pointing at the
same data, and nothing is copied anywhere.


**Example #3 Assigning by reference**

`<?php
$a = 3;
$b = &$a; // $b is a reference to $a
print "$a\n"; // prints 3
print "$b\n"; // prints 3
$a = 4; // change $a
print "$a\n"; // prints 4
print "$b\n"; // prints 4 as well, since $b is a reference to $a, which has
              // been changed
?>`

Run code

The [new](https://www.php.net/manual/en/language.oop5.basic.php#language.oop5.basic.new)
operator returns a reference automatically, as such assigning the result of
[new](https://www.php.net/manual/en/language.oop5.basic.php#language.oop5.basic.new) by reference is an error.


**Example #4 new Operator By-Reference**

`<?php
class C {}
$o = &new C;
?>`

Run code

The above example will output:

```
Parse error: syntax error, unexpected token ";", expecting "("

```

More information on references and their potential uses can be found in
the [References Explained](https://www.php.net/manual/en/language.references.php)
section of the manual.


### Arithmetic Assignment Operators [¶](https://www.php.net/manual/en/language.operators.assignment.php\#language.operators.assignment.arithmetic)

| Example | Equivalent | Operation |
| --- | --- | --- |
| $a += $b | $a = $a + $b | Addition |
| $a -= $b | $a = $a - $b | Subtraction |
| $a \*= $b | $a = $a \* $b | Multiplication |
| $a /= $b | $a = $a / $b | Division |
| $a %= $b | $a = $a % $b | Modulus |
| $a \*\*= $b | $a = $a \*\* $b | Exponentiation |

### Bitwise Assignment Operators [¶](https://www.php.net/manual/en/language.operators.assignment.php\#language.operators.assignment.bitwise)

| Example | Equivalent | Operation |
| --- | --- | --- |
| $a &= $b | $a = $a & $b | Bitwise And |
| $a \|= $b | $a = $a \| $b | Bitwise Or |
| $a ^= $b | $a = $a ^ $b | Bitwise Xor |
| $a <<= $b | $a = $a << $b | Left Shift |
| $a >>= $b | $a = $a >> $b | Right Shift |

### Other Assignment Operators [¶](https://www.php.net/manual/en/language.operators.assignment.php\#language.operators.assignment.other)

| Example | Equivalent | Operation |
| --- | --- | --- |
| $a .= $b | $a = $a . $b | String Concatenation |
| $a ??= $b | $a = $a ?? $b | Null Coalesce |

### See Also [¶](https://www.php.net/manual/en/language.operators.assignment.php\#language.operators.assignment.see-also)

- [arithmetic operators](https://www.php.net/manual/en/language.operators.arithmetic.php)
- [bitwise operators](https://www.php.net/manual/en/language.operators.bitwise.php)
- [null coalescing operator](https://www.php.net/manual/en/language.operators.comparison.php#language.operators.comparison.coalesce)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/operators/assignment.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.operators.assignment%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.assignment&repo=en&redirect=https://www.php.net/manual/en/language.operators.assignment.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=102385&page=language.operators.assignment&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=102385&page=language.operators.assignment&vote=down "Vote down!")

144


[**_Peter, Moscow_**](https://www.php.net/manual/en/language.operators.assignment.php#102385) [¶](https://www.php.net/manual/en/language.operators.assignment.php#102385)

**14 years ago**

`Using $text .= "additional text"; instead of $text =  $text ."additional text"; can seriously enhance performance due to memory allocation efficiency.
I reduced execution time from 5 sec to .5 sec (10 times) by simply switching to the first pattern for a loop with 900 iterations over a string $text that reaches 800K by the end.`

[up](https://www.php.net/manual/vote-note.php?id=116873&page=language.operators.assignment&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116873&page=language.operators.assignment&vote=down "Vote down!")

60


[**_Robert Schneider_**](https://www.php.net/manual/en/language.operators.assignment.php#116873) [¶](https://www.php.net/manual/en/language.operators.assignment.php#116873)

**10 years ago**

`Be aware of assignments with conditionals. The assignment operator is stronger as 'and', 'or' and 'xor'.
<?php
$x = true and false;   //$x will be true
$y = (true and false); //$y will be false
?>`

[up](https://www.php.net/manual/vote-note.php?id=78345&page=language.operators.assignment&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78345&page=language.operators.assignment&vote=down "Vote down!")

31


[**_Hayley Watson_**](https://www.php.net/manual/en/language.operators.assignment.php#78345) [¶](https://www.php.net/manual/en/language.operators.assignment.php#78345)

**18 years ago**

`bradlis7 at bradlis7 dot com's description is a bit confusing. Here it is rephrased.
<?php
$a = 'a';
$b = 'b';
$a .= $b .= "foo";
echo $a,"\n",$b;?>
outputs
abfoo
bfoo
Because the assignment operators are right-associative and evaluate to the result of the assignment
<?php
$a .= $b .= "foo";
?>
is equivalent to
<?php
$a .= ($b .= "foo");
?>
and therefore
<?php
$b .= "foo";
$a .= $b;
?>`

[up](https://www.php.net/manual/vote-note.php?id=117641&page=language.operators.assignment&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117641&page=language.operators.assignment&vote=down "Vote down!")

17


[**_asc at putc dot de_**](https://www.php.net/manual/en/language.operators.assignment.php#117641) [¶](https://www.php.net/manual/en/language.operators.assignment.php#117641)

**10 years ago**

`PHP uses a temporary variable for combined assign-operators (unlike JavaScript), therefore the left-hand-side (target) gets evaluated last.
Input:
$a += $b + $c;
Meaning:
$a = ($b + $c) + $a;
Not:
$a = $a + ($b + $c);
This can be important if the target gets modified inside the expression.
$a = 0;
$a += (++$a) + (++$a); // yields 5 (instead of 4)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.assignment&repo=en&redirect=https://www.php.net/manual/en/language.operators.assignment.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google