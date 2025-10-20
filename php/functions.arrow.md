---
url: https://www.php.net/manual/en/functions.arrow.php
scraped_at: 2025-10-20T02:31:55.022Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Arrow Functions [¶](https://www.php.net/manual/en/functions.arrow.php\#functions.arrow)

Arrow functions were introduced in PHP 7.4 as a more concise syntax for
[anonymous functions](https://www.php.net/manual/en/functions.anonymous.php).


Both anonymous functions and arrow functions are implemented using the
[Closure](https://www.php.net/manual/en/class.closure.php) class.


Arrow functions have the basic form
`fn (argument_list) => expr`.


Arrow functions support the same features as
[anonymous functions](https://www.php.net/manual/en/functions.anonymous.php),
except that using variables from the parent scope is always automatic.


When a variable used in the expression is defined in the parent scope
it will be implicitly captured by-value.
In the following example, the functions $fn1 and
$fn2 behave the same way.


**Example #1 Arrow functions capture variables by value automatically**

`<?php
$y = 1;
$fn1 = fn($x) => $x + $y;
// equivalent to using $y by value:
$fn2 = function ($x) use ($y) {
    return $x + $y;
};
var_export($fn1(3));
?>`

The above example will output:

```
4

```

This also works if the arrow functions are nested:


**Example #2 Arrow functions capture variables by value automatically, even when nested**

`<?php
$z = 1;
$fn = fn($x) => fn($y) => $x * $y + $z;
// Outputs 51
var_export($fn(5)(10));
?>`

Similarly to anonymous functions,
the arrow function syntax allows arbitrary function signatures,
including parameter and return types, default values, variadics,
as well as by-reference passing and returning.
All of the following are valid examples of arrow functions:


**Example #3 Examples of arrow functions**

`<?php
fn(array $x) => $x;
static fn($x): int => $x;
fn($x = 42) => $x;
fn(&$x) => $x;
fn&($x) => $x;
fn($x, ...$rest) => $rest;
?>`

Arrow functions use by-value variable binding.
This is roughly equivalent to performing a `use($x)` for every
variable $x used inside the arrow function.
A by-value binding means that it is not possible to modify any values
from the outer scope.
[Anonymous functions](https://www.php.net/manual/en/functions.anonymous.php)
can be used instead for by-ref bindings.


**Example #4 Values from the outer scope cannot be modified by arrow functions**

`<?php
$x = 1;
$fn = fn() => $x++; // Has no effect
$fn();
var_export($x);  // Outputs 1
?>`

### Changelog

| Version | Description |
| --- | --- |
| 7.4.0 | Arrow functions became available. |

### Notes

> **Note**:
>
> It is possible to use [func\_num\_args()](https://www.php.net/manual/en/function.func-num-args.php),
> [func\_get\_arg()](https://www.php.net/manual/en/function.func-get-arg.php), and [func\_get\_args()](https://www.php.net/manual/en/function.func-get-args.php)
> from within an arrow function.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/functions.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunctions.arrow%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=functions.arrow&repo=en&redirect=https://www.php.net/manual/en/functions.arrow.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=125673&page=functions.arrow&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125673&page=functions.arrow&vote=down "Vote down!")

49


[**_InvisibleSmiley_**](https://www.php.net/manual/en/functions.arrow.php#125673) [¶](https://www.php.net/manual/en/functions.arrow.php#125673)

**4 years ago**

`Unlike anonymous functions, arrow functions cannot have a void return type declaration.
May seem obvious, but if you thought you could make use of the benefits of arrow functions (using variables from the parent scope) to simplify a function or method call, keep in mind that this is only possible if you do NOT tell PHP that the arrow function does indeed return void.`

[up](https://www.php.net/manual/vote-note.php?id=125213&page=functions.arrow&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125213&page=functions.arrow&vote=down "Vote down!")

43


[**_Koushil Mankali_**](https://www.php.net/manual/en/functions.arrow.php#125213) [¶](https://www.php.net/manual/en/functions.arrow.php#125213)

**5 years ago**

`In example 4  (Values from the outer scope cannot be modified by arrow functions)
<?php
$x = 1;
$fn = fn() => $x++; // Has no effect
$fn();
var_export($x);  // Outputs 1
?>
Here we can use reference variable in fn(&$x) and pass the value from function call $fn($x) so that we will get the output as expected with out using Anonymous functions.
Example:
<?php
$x = 1;
$fn = fn(&$x) => $x++;
$fn($x);
var_export($x);
?>
Output : 2 (as expected)
But here it will not take values from parent scope automatically but we have to pass them explicitly.`

[up](https://www.php.net/manual/vote-note.php?id=129898&page=functions.arrow&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129898&page=functions.arrow&vote=down "Vote down!")

12


[**_aaronw at catalyst dot net dot nz_**](https://www.php.net/manual/en/functions.arrow.php#129898) [¶](https://www.php.net/manual/en/functions.arrow.php#129898)

**10 months ago**

`If you're a JavaScript developer, here are the similarities and differences to JS arrow functions:
Same:
-  Makes an anonymous function
-  Binds the value of "$this" to its value in the parent scope.
    - (along with all other variables of the parent scope. See note below)
Different:
- You must write "fn()" instead of just "()"
- The function body is limited to just ONE expression
    - So no multi-line function bodies with "{" and "}"
Same and Different at the same time:
- Binds ALL the variables of the parent scope
    - In JavaScript all functions are closures, binding to the variables in their parent scope (except for "this").
    - But in PHP, normal anonymous functions (defined with "function() {}") do NOT get access to the parent scope, unless they explicitly declare a closure with keyword "use"
    - PHP arrow functions, on the other hand, automatically bind to ALL variables in the parent scope. So, this makes them behave the same as JS functions, but be aware that in PHP this is special behavior unique to arrow functions.`

[up](https://www.php.net/manual/vote-note.php?id=125984&page=functions.arrow&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125984&page=functions.arrow&vote=down "Vote down!")

27


[**_itsunclexo at gmail dot com_**](https://www.php.net/manual/en/functions.arrow.php#125984) [¶](https://www.php.net/manual/en/functions.arrow.php#125984)

**4 years ago**

`As you already know, variable bindings occur in arrow functions by "by-value".  That means, an arrow function returns a copy of the value of the variable used in it from the outer scope.
Now let us see an example of how a arrow function returns a reference instead of a copy of a value.
<?php
$x = 0;
$fn = fn &(&$x) => $x;  // Returns a reference
$y = &$fn($x);  // Now $y represents the reference
var_dump($y);  // Outputs: 0
$y = 3;  // Changing value of $y affects $x
var_dump($x);  // Ouputs: 3
?>`

[up](https://www.php.net/manual/vote-note.php?id=125239&page=functions.arrow&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125239&page=functions.arrow&vote=down "Vote down!")

15


[**_dexen dot devries at gmail dot com_**](https://www.php.net/manual/en/functions.arrow.php#125239) [¶](https://www.php.net/manual/en/functions.arrow.php#125239)

**5 years ago**

`Beware compact() not being able to access (import) variables from external scope (known in versions: 7.4.0, 7.4.8) (bug: [https://bugs.php.net/bug.php?id=78970](https://bugs.php.net/bug.php?id=78970)).
A workaround is available - use the variable directly; this will cause it to be imported into the arrow function's namespace and make it available to the compact() too.
<?php
$aa = 111;
$accessing_variable_works = fn($bb) => [ $aa, $bb ];
$compact_is_broken = fn($bb) => compact('aa', 'bb');
$compact_can_work_with_workaround = fn($bb) => compact('aa', 'bb') + ['workaround' => $aa];
var_dump($accessing_variable_works(333));
var_dump($compact_is_broken(555));
var_dump($compact_can_work_with_workaround(777));
?>
result:
array(2) {
[0]=>
int(111)
[1]=>
int(333)
}
PHP Notice:  compact(): Undefined variable: aa in /home/m/vlt/guitar/tlb/s/public_html/index.php on line 9
array(1) {
["bb"]=>
int(555)
}
array(3) {
["aa"]=>
int(111)
["bb"]=>
int(777)
["workaround"]=>
int(111)
}`

[＋add a note](https://www.php.net/manual/add-note.php?sect=functions.arrow&repo=en&redirect=https://www.php.net/manual/en/functions.arrow.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google