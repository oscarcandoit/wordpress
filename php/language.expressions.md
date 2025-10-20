---
url: https://www.php.net/manual/en/language.expressions.php
scraped_at: 2025-10-20T02:37:31.985Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Expressions [¶](https://www.php.net/manual/en/language.expressions.php\#language.expressions)

Expressions are the most important building blocks of PHP. In PHP,
almost anything you write is an expression. The simplest yet
most accurate way to define an expression is "anything that has a
value".


The most basic forms of expressions are constants and variables.
When you type `$a = 5`, you're assigning `5` into
$a. `5`, obviously,
has the value 5, or in other words `5` is an expression with the
value of 5 (in this case, `5` is an integer constant).


After this assignment, you'd expect $a's value to be 5 as
well, so if you wrote `$b = $a`, you'd expect it to behave just as
if you wrote `$b = 5`. In other words, $a is an expression with the
value of 5 as well. If everything works right, this is exactly
what will happen.


Slightly more complex examples for expressions are functions. For
instance, consider the following function:


`<?php
function foo ()
{
    return 5;
}
?>`

Assuming you're familiar with the concept of functions (if you're
not, take a look at the chapter about [functions](https://www.php.net/manual/en/language.functions.php)), you'd assume
that typing `$c = foo()` is essentially just like
writing `$c = 5`, and you're right. Functions
are expressions with the value of their return value. Since `foo()`
returns 5, the value of the expression ' `foo()`' is 5. Usually
functions don't just return a static value but compute something.


Of course, values in PHP don't have to be integers, and very often
they aren't. PHP supports four scalar value types: [int](https://www.php.net/manual/en/language.types.integer.php)
values, floating point values ([float](https://www.php.net/manual/en/language.types.float.php)), [string](https://www.php.net/manual/en/language.types.string.php)
values and [bool](https://www.php.net/manual/en/language.types.boolean.php) values (scalar values are values that you
can't 'break' into smaller pieces, unlike arrays, for instance). PHP also
supports two composite (non-scalar) types: arrays and objects. Each of
these value types can be assigned into variables or returned from functions.


PHP takes expressions much further, in the same way many other languages
do. PHP is an expression-oriented language, in the
sense that almost everything is an expression. Consider the
example we've already dealt with, `$a = 5`. It's easy to see that
there are two values involved here, the value of the integer
constant `5`, and the value of $a which is being updated to 5 as
well. But the truth is that there's one additional value involved
here, and that's the value of the assignment itself. The
assignment itself evaluates to the assigned value, in this case 5.
In practice, it means that `$a = 5`, regardless of what it does,
is an expression with the value 5. Thus, writing something like
`$b = ($a = 5)` is like writing
`$a = 5; $b = 5;` (a semicolon
marks the end of a statement). Since assignments are parsed in a
right to left order, you can also write `$b = $a = 5`.


Another good example of expression orientation is pre- and
post-increment and decrement. Users of PHP and many other
languages may be familiar with the notation of `variable++` and
`variable--`. These are [increment and decrement operators](https://www.php.net/manual/en/language.operators.increment.php). In PHP, like in C, there
are two types of increment - pre-increment and post-increment.
Both pre-increment and post-increment essentially increment the
variable, and the effect on the variable is identical. The
difference is with the value of the increment expression.
Pre-increment, which is written `++$variable`, evaluates to the
incremented value (PHP increments the variable before reading its
value, thus the name 'pre-increment'). Post-increment, which is
written `$variable++` evaluates to the original value of
$variable, before it was incremented (PHP increments the variable
after reading its value, thus the name 'post-increment').


A very common type of expressions are [comparison](https://www.php.net/manual/en/language.operators.comparison.php)
expressions. These expressions evaluate to either **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** or **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**. PHP
supports > (bigger than), >= (bigger than or equal to), == (equal),
!= (not equal), < (smaller than) and <= (smaller than or equal to).
The language also supports a set of strict equivalence operators: ===
(equal to and same type) and !== (not equal to or not same type).
These expressions are most commonly used inside conditional execution,
such as `if` statements.


The last example of expressions we'll deal with here is combined
operator-assignment expressions. You already know that if you
want to increment $a by 1, you can simply write
`$a++` or `++$a`.
But what if you want to add more than one to it, for instance 3?
You could write `$a++` multiple times, but this
is obviously not a very efficient or comfortable way. A much more
common practice is to write `$a =
    $a + 3`. `$a + 3` evaluates
to the value of $a plus 3, and is assigned back
into $a, which results in incrementing $a
by 3. In PHP, as in several other languages like C, you can write this
in a shorter way, which with time would become clearer and quicker to
understand as well. Adding 3 to the current value of $a
can be written `$a += 3`. This means exactly
"take the value of $a, add 3 to it, and assign it
back into $a". In addition to being shorter and
clearer, this also results in faster execution. The value of
`$a += 3`, like the value of a regular assignment, is
the assigned value. Notice that it is NOT 3, but the combined value
of $a plus 3 (this is the value that's
assigned into $a). Any two-place operator can be used
in this operator-assignment mode, for example `$a -= 5`
(subtract 5 from the value of $a), `$b *= 7`
(multiply the value of $b by 7), etc.


There is one more expression that may seem odd if you haven't seen
it in other languages, the ternary conditional operator:


`<?php
$first ? $second : $third
?>`

If the value of the first subexpression is **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** (non-zero), then
the second subexpression is evaluated, and that is the result of
the conditional expression. Otherwise, the third subexpression is
evaluated, and that is the value.


The following example should help you understand pre- and
post-increment and expressions in general a bit better:


`<?php
function double($i)
{
    return $i*2;
}
$b = $a = 5;        /* assign the value five into the variable $a and $b */
$c = $a++;          /* post-increment, assign original value of $a
                       (5) to $c */
$e = $d = ++$b;     /* pre-increment, assign the incremented value of
                       $b (6) to $d and $e */
/* at this point, both $d and $e are equal to 6 */
$f = double($d++);  /* assign twice the value of $d before
                       the increment, 2*6 = 12 to $f */
$g = double(++$e);  /* assign twice the value of $e after
                       the increment, 2*7 = 14 to $g */
$h = $g += 10;      /* first, $g is incremented by 10 and ends with the
                       value of 24. the value of the assignment (24) is
                       then assigned into $h, and $h ends with the value
                       of 24 as well. */
?>`

Some expressions can be considered as statements. In
this case, a statement has the form of ' `expr ;`' that is, an
expression followed by a semicolon. In `$b = $a = 5;`,
`$a = 5` is a valid expression, but it's not a statement
by itself. `$b = $a = 5;`, however, is a valid statement.


One last thing worth mentioning is the truth value of expressions.
In many events, mainly in conditional execution and loops, you're
not interested in the specific value of the expression, but only
care about whether it means **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.



The constants **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** and **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** (case-insensitive) are the two
possible boolean values. When necessary, an expression is
automatically converted to boolean. See the
[section about\\
type-casting](https://www.php.net/manual/en/language.types.type-juggling.php#language.types.typecasting) for details about how.


PHP provides a full and powerful implementation of expressions, and
documenting it entirely goes beyond the scope of this manual. The
above examples should give you a good idea about what expressions
are and how you can construct useful expressions. Throughout the
rest of this manual we'll write expr
to indicate any valid PHP expression.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/expressions.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.expressions%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.expressions&repo=en&redirect=https://www.php.net/manual/en/language.expressions.php)

### User Contributed Notes 12 notes

[up](https://www.php.net/manual/vote-note.php?id=90327&page=language.expressions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90327&page=language.expressions&vote=down "Vote down!")

59


[**_Magnus Deininger, dma05 at web dot de_**](https://www.php.net/manual/en/language.expressions.php#90327) [¶](https://www.php.net/manual/en/language.expressions.php#90327)

**16 years ago**

`Note that even though PHP borrows large portions of its syntax from C, the ',' is treated quite differently. It's not possible to create combined expressions in PHP using the comma-operator that C has, except in for() loops.
Example (parse error):
<?php
$a = 2, $b = 4;
echo $a."\n";
echo $b."\n";
?>
Example (works):
<?php
for ($a = 2, $b = 4; $a < 3; $a++)
{
echo $a."\n";
echo $b."\n";
}
?>
This is because PHP doesn't actually have a proper comma-operator, it's only supported as syntactic sugar in for() loop headers. In C, it would have been perfectly legitimate to have this:
int f()
{
int a, b;
a = 2, b = 4;
return a;
}
or even this:
int g()
{
int a, b;
a = (2, b = 4);
return a;
}
In f(), a would have been set to 2, and b would have been set to 4.
In g(), (2, b = 4) would be a single expression which evaluates to 4, so both a and b would have been set to 4.`

[up](https://www.php.net/manual/vote-note.php?id=11883&page=language.expressions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=11883&page=language.expressions&vote=down "Vote down!")

54


[**_yasuo\_ohgaki at hotmail dot com_**](https://www.php.net/manual/en/language.expressions.php#11883) [¶](https://www.php.net/manual/en/language.expressions.php#11883)

**24 years ago**

`Manual defines "expression is anything that has value", Therefore, parser will give error for following code.
<?php
($val) ? echo('true') : echo('false');
Note: "? : " operator has this syntax  "expr ? expr : expr;"
?>
since echo does not have(return) value and ?: expects expression(value).
However, if function/language constructs that have/return value, such as include(), parser compiles code.
Note: User defined functions always have/return value without explicit return statement (returns NULL if there is no return statement). Therefore, user defined functions are always valid expressions.
[It may be useful to have VOID as new type to prevent programmer to use function as RVALUE by mistake]
For example,
<?php
($val) ? include('true.inc') : include('false.inc');
?>
is valid, since "include" returns value.
The fact "echo" does not return value(="echo" is not a expression), is less obvious to me.
Print() and Echo() is NOT identical since print() has/returns value and can be a valid expression.`

[up](https://www.php.net/manual/vote-note.php?id=112682&page=language.expressions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112682&page=language.expressions&vote=down "Vote down!")

26


[**_chriswarbo at gmail dot com_**](https://www.php.net/manual/en/language.expressions.php#112682) [¶](https://www.php.net/manual/en/language.expressions.php#112682)

**12 years ago**

`Note that there is a difference between a function and a function call, and both
are expressions. PHP has two kinds of function, "named functions" and "anonymous
functions". Here's an example with both:
<?php
// A named function. Its name is "double".
function double($x) {
return 2 * $x;
}
// An anonymous function. It has no name, in the same way that the string
// "hello" has no name. Since it is an expression, we can give it a temporary
// name by assigning it to the variable $triple.
$triple = function($x) {
return 3 * $x;
};
?>
We can "call" (or "run") both kinds of function. A "function call" is an
expression with the value of whatever the function returns. For example:
<?php
// The easiest way to run a function is to put () after its name, containing its
// arguments (if any)
$my_numbers = array(double(5), $triple(5));
?>
$my_numbers is now an array containing 10 and 15, which are the return values of
double and $triple when applied to the number 5.
Importantly, if we *don't* call a function, ie. we don't put () after its name,
then we still get expressions. For example:
<?php
$my_functions = array('double', $triple);
?>
$my_functions is now an array containing these two functions. Notice that named
functions are more awkward than anonymous functions. PHP treats them differently
because it didn't use to have anonymous functions, and the way named functions
were implemented didn't work for anonymous functions when they were eventually
added.
This means that instead of using a named function literally, like we can with
anonymous functions, we have to use a string containing its name instead. PHP
makes sure that these strings will be treated as functions when it's
appropriate. For example:
<?php
$temp      = 'double';
$my_number = $temp(5);
?>
$my_number will be 10, since PHP has spotted that we're treating a string as if
it were a function, so it has looked up that named function for us.
Unfortunately PHP's parser is very quirky; rather than looking for generic
patterns like "x(y)" and seeing if "x" is a function, it has lots of
special-cases like "$x(y)". This makes code like "'double'(5)" invalid, so we
have to do tricks like using temporary variables. There is another way around
this restriction though, and that is to pass our functions to the
"call_user_func" or "call_user_func_array" functions when we want to call them.
For example:
<?php
$my_numbers = array(call_user_func('double', 5), call_user_func($triple, 5));
?>
$my_numbers contains 10 and 15 because "call_user_func" called our functions for
us. This is possible because the string 'double' and the anonymous function
$triple are expressions. Note that we can even use this technique to call an
anonymous function without ever giving it a name:
<?php
$my_number = call_user_func(function($x) { return 4 * $x; }, 5);
?>
$my_number is now 20, since "call_user_func" called the anonymous function,
which quadruples its argument, with the value 5.
Passing functions around as expressions like this is very useful whenever we
need to use a 'callback'. Great examples of this are array_map and array_reduce.`

[up](https://www.php.net/manual/vote-note.php?id=77291&page=language.expressions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77291&page=language.expressions&vote=down "Vote down!")

18


[**_winks716_**](https://www.php.net/manual/en/language.expressions.php#77291) [¶](https://www.php.net/manual/en/language.expressions.php#77291)

**18 years ago**

`reply to egonfreeman at gmail dot com
04-Apr-2007 07:45
the second example u mentioned as follow:
=====================================
$n = 3;
$n * $n++
from 3 * 3 into 3 * 4. Post- operations operate on a variable after it has been 'checked', but it doesn't necessarily state that it should happen AFTER an evaluation is over (on the contrary, as a matter of fact).
===========================================
everything works correctly but one sentence should be modified:
"from 3 * 3 into 3 * 4"  should be "from 3 * 3 into 4 * 3"
best regards~ :)`

[up](https://www.php.net/manual/vote-note.php?id=74308&page=language.expressions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74308&page=language.expressions&vote=down "Vote down!")

16


[**_egonfreeman at gmail dot com_**](https://www.php.net/manual/en/language.expressions.php#74308) [¶](https://www.php.net/manual/en/language.expressions.php#74308)

**18 years ago**

`It is worthy to mention that:
$n = 3;
$n * --$n
WILL RETURN 4 instead of 6.
It can be a hard to spot "error", because in our human thought process this really isn't an error at all! But you have to remember that PHP (as it is with many other high-level languages) evaluates its statements RIGHT-TO-LEFT, and therefore "--$n" comes BEFORE multiplying, so - in the end - it's really "2 * 2", not "3 * 2".
It is also worthy to mention that the same behavior will change:
$n = 3;
$n * $n++
from 3 * 3 into 3 * 4. Post- operations operate on a variable after it has been 'checked', but it doesn't necessarily state that it should happen AFTER an evaluation is over (on the contrary, as a matter of fact).
So, if you ever find yourself on a 'wild goose chase' for a bug in that "impossible-to-break, so-very-simple" piece of code that uses pre-/post-'s, remember this post. :)
(just thought I'd check it out - turns out I was right :P)`

[up](https://www.php.net/manual/vote-note.php?id=21750&page=language.expressions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=21750&page=language.expressions&vote=down "Vote down!")

19


[**_Mattias at mail dot ee_**](https://www.php.net/manual/en/language.expressions.php#21750) [¶](https://www.php.net/manual/en/language.expressions.php#21750)

**23 years ago**

`A note about the short-circuit behaviour of the boolean operators.
1. if (func1() || func2())
Now, if func1() returns true, func2() isn't run, since the expression
will be true anyway.
2. if (func1() && func2())
Now, if func1() returns false, func2() isn't run, since the expression
will be false anyway.
The reason for this behaviour comes probably from the programming
language C, on which PHP seems to be based on. There the
short-circuiting can be a very useful tool. For example:
int * myarray = a_func_to_set_myarray(); // init the array
if (myarray != NULL && myarray[0] != 4321) // check
    myarray[0] = 1234;
Now, the pointer myarray is checked for being not null, then the
contents of the array is validated. This is important, because if
you try to access an array whose address is invalid, the program
will crash and die a horrible death. But thanks to the short
circuiting, if myarray == NULL then myarray[0] won't be accessed,
and the program will work fine.`

[up](https://www.php.net/manual/vote-note.php?id=81849&page=language.expressions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81849&page=language.expressions&vote=down "Vote down!")

10


[**_denzoo at gmail dot com_**](https://www.php.net/manual/en/language.expressions.php#81849) [¶](https://www.php.net/manual/en/language.expressions.php#81849)

**17 years ago**

`To jvm at jvmyers dot com:
Your first two if statements just check if there's anything in the string, if you wish to actually execute the code in your string you need eval().`

[up](https://www.php.net/manual/vote-note.php?id=78636&page=language.expressions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78636&page=language.expressions&vote=down "Vote down!")

9


[**_petruzanauticoyahoo?com!ar_**](https://www.php.net/manual/en/language.expressions.php#78636) [¶](https://www.php.net/manual/en/language.expressions.php#78636)

**17 years ago**

`Regarding the ternary operator, I would rather say that the best option is to enclose all the expression in parantheses, to avoid errors and improve clarity:
<?php
print ( $a > 1 ? "many" : "just one" );
?>
PS: for php, C++, and any other language that has it.`

[up](https://www.php.net/manual/vote-note.php?id=24119&page=language.expressions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=24119&page=language.expressions&vote=down "Vote down!")

8


[**_oliver at hankeln-online dot de_**](https://www.php.net/manual/en/language.expressions.php#24119) [¶](https://www.php.net/manual/en/language.expressions.php#24119)

**23 years ago**

`The short-circuiting IS a feature. It is also available in C, so I suppose the developers won?t remove it in future PHP versions.
It is rather nice to write:
$file=fopen("foo","r") or die("Error!");
Greets,
Oliver`

[up](https://www.php.net/manual/vote-note.php?id=120459&page=language.expressions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120459&page=language.expressions&vote=down "Vote down!")

5


[**_Bichis Paul_**](https://www.php.net/manual/en/language.expressions.php#120459) [¶](https://www.php.net/manual/en/language.expressions.php#120459)

**8 years ago**

`Regarding 12345alex at gmx dot net's example:
I think you miss the identical equal documentation line from: [http://php.net/manual/en/language.operators.comparison.php](http://php.net/manual/en/language.operators.comparison.php)
$a == $b     Equal     TRUE if $a is equal to $b after type juggling.
$a === $b     Identical     TRUE if $a is equal to $b, and they are of the same type.
Try:
print array() === NULL ? "True" : "False";
Check this:
var_dump(is_null(array()));`

[up](https://www.php.net/manual/vote-note.php?id=107687&page=language.expressions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107687&page=language.expressions&vote=down "Vote down!")

6


[**_antickon at gmail dot com_**](https://www.php.net/manual/en/language.expressions.php#107687) [¶](https://www.php.net/manual/en/language.expressions.php#107687)

**13 years ago**

`evaluation order of subexpressions is not strictly defined for all operators
<?php
function a() {echo 'a';}
function b() {echo 'b';}
a() == b(); // outputs "ab", ie evaluates left-to-right
$a = 3;
var_dump( $a == $a = 4 ); // outputs bool(true), ie evaluates right-to-left
?>
this is not a bug: "we [php developers] make no guarantee about the order of evaluation".
See [https://bugs.php.net/bug.php?id=61188](https://bugs.php.net/bug.php?id=61188)`

[up](https://www.php.net/manual/vote-note.php?id=73261&page=language.expressions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73261&page=language.expressions&vote=down "Vote down!")

4


[**_shawnster_**](https://www.php.net/manual/en/language.expressions.php#73261) [¶](https://www.php.net/manual/en/language.expressions.php#73261)

**18 years ago**

`An easy fix (although intuitively tough to do...) is to reverse the comparison.
if (5 == $a) {}
If you forget the second '=', you'll get a parse error for trying to assign a value to a non-variable.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.expressions&repo=en&redirect=https://www.php.net/manual/en/language.expressions.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google