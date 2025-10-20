---
url: https://www.php.net/manual/en/language.operators.logical.php
scraped_at: 2025-10-20T02:47:13.640Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Logical Operators [¶](https://www.php.net/manual/en/language.operators.logical.php\#language.operators.logical)

| Example | Name | Result |
| --- | --- | --- |
| $a and $b | And | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if both $a and $b are **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**. |
| $a or $b | Or | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if either $a or $b is **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**. |
| $a xor $b | Xor | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if either $a or $b is **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, but not both. |
| ! $a | Not | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is not **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**. |
| $a && $b | And | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if both $a and $b are **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**. |
| $a \|\| $b | Or | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if either $a or $b is **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**. |

**Logical Operators**

The reason for the two different variations of "and" and "or"
operators is that they operate at different precedences. (See
[Operator\\
Precedence](https://www.php.net/manual/en/language.operators.precedence.php).)


**Example #1 Logical operators illustrated**

`<?php
// --------------------
// foo() will never get called as those operators are short-circuit
$a = (false && foo());
$b = (true  || foo());
$c = (false and foo());
$d = (true  or  foo());
// --------------------
// "||" has a greater precedence than "or"
// The result of the expression (false || true) is assigned to $e
// Acts like: ($e = (false || true))
$e = false || true;
// The constant false is assigned to $f before the "or" operation occurs
// Acts like: (($f = false) or true)
$f = false or true;
var_dump($e, $f);
// --------------------
// "&&" has a greater precedence than "and"
// The result of the expression (true && false) is assigned to $g
// Acts like: ($g = (true && false))
$g = true && false;
// The constant true is assigned to $h before the "and" operation occurs
// Acts like: (($h = true) and false)
$h = true and false;
var_dump($g, $h);
?>`

Run code

The above example will output
something similar to:

```
bool(true)
bool(false)
bool(false)
bool(true)

```

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/operators/logical.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.operators.logical%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.logical&repo=en&redirect=https://www.php.net/manual/en/language.operators.logical.php)

### User Contributed Notes 14 notes

[up](https://www.php.net/manual/vote-note.php?id=77411&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77411&page=language.operators.logical&vote=down "Vote down!")

320


[**_Lawrence_**](https://www.php.net/manual/en/language.operators.logical.php#77411) [¶](https://www.php.net/manual/en/language.operators.logical.php#77411)

**18 years ago**

`Note that PHP's boolean operators *always* return a boolean value... as opposed to other languages that return the value of the last evaluated expression.
For example:
$a = 0 || 'avacado';
print "A: $a\n";
will print:
A: 1
in PHP -- as opposed to printing "A: avacado" as it would in a language like Perl or JavaScript.
This means you can't use the '||' operator to set a default value:
$a = $fruit || 'apple';
instead, you have to use the '?:' operator:
$a = ($fruit ? $fruit : 'apple');`

[up](https://www.php.net/manual/vote-note.php?id=120961&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120961&page=language.operators.logical&vote=down "Vote down!")

75


[**_dumitru at floringabriel dot com_**](https://www.php.net/manual/en/language.operators.logical.php#120961) [¶](https://www.php.net/manual/en/language.operators.logical.php#120961)

**8 years ago**

`In addition to what Lawrence said about assigning a default value, one can now use the Null Coalescing Operator (PHP 7). Hence when we want to assign a default value we can write:
$a = ($fruit ?? 'apple');
//assigns the $fruit variable content to $a if the $fruit variable exists or has a value that is not NULL, or assigns the value 'apple' to $a if the $fruit variable doesn't exists or it contains the NULL value`

[up](https://www.php.net/manual/vote-note.php?id=120433&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120433&page=language.operators.logical&vote=down "Vote down!")

25


[**_thisleenobleNOSPAMPLEASE at mac dot com_**](https://www.php.net/manual/en/language.operators.logical.php#120433) [¶](https://www.php.net/manual/en/language.operators.logical.php#120433)

**8 years ago**

`In order to kind of emulate the way javascript assigns the first non-false value in an expression such as this:
var v = a || b || c || d;
I wrote a little helper method that I put in a function dump library (here presented as a bare function):
<?php
function either($a, $b){
        $val = $a ? $a : $b;
        /*
             Yes, I know the fixed parameters in the function
             are redundant since I could just use func_get_args,
             but in most instances I'll be using this a replacement
             for the ternary operator and only passing two values.
             I don't want to invoke the additional process below
             unless I REALLY have to.
        */
        $args = func_get_args();
        if($val === false && count($args) > 2){
            $args = array_slice($args, 2);
            foreach($args as $arg){
                if($arg !== false){
                    $val = $arg;
                    break;
                }
            }
        }
        return $val;
    }
?>
Now instead of:
$v = $a ? $a : $b;
I write:
$v = either($a, $b);
but more importantly, instead of writing:
$v = $a ? $a : ($b ? $b : $c);
I write:
$v = either($a, $b, $c);
or indeed:
$v = either($a, $b, $c, $d, $e, $f, $g, $h);`

[up](https://www.php.net/manual/vote-note.php?id=127992&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127992&page=language.operators.logical&vote=down "Vote down!")

4


[**_martinholtcbi at gmail dot com_**](https://www.php.net/manual/en/language.operators.logical.php#127992) [¶](https://www.php.net/manual/en/language.operators.logical.php#127992)

**2 years ago**

`In PHP, the || operator only ever returns a boolean. For a chainable assignment operator, use the ?: "Elvis" operator.
JavaScript:
let a = false;
let b = false;
let c = true;
let d = false;
let e = a || b || c || d;
// e === c
<?PHP
$a = false;
$b = false;
$c = true;
$d = false;
$e = $a ?: $b ?: $c ?: $d;
// $e === $c
?>
Credit to @egst and others for the insight. This is merely a rewording for (formerly) lost JavaScript devs like myself.`

[up](https://www.php.net/manual/vote-note.php?id=80005&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80005&page=language.operators.logical&vote=down "Vote down!")

50


[**_pepesantillan at gmail dot com_**](https://www.php.net/manual/en/language.operators.logical.php#80005) [¶](https://www.php.net/manual/en/language.operators.logical.php#80005)

**17 years ago**

`worth reading for people learning about php and programming: (adding extras <?php ?> to get highlighted code)
about the following example in this page manual:
Example#1 Logical operators illustrated
...
<?php
// "||" has a greater precedence than "or"
$e = false || true; // $e will be assigned to (false || true) which is true
$f = false or true; // $f will be assigned to false
var_dump($e, $f);
// "&&" has a greater precedence than "and"
$g = true && false; // $g will be assigned to (true && false) which is false
$h = true and false; // $h will be assigned to true
var_dump($g, $h);
?>
_______________________________________________end of my quote...
If necessary, I wanted to give further explanation on this and say that when we write:
$f = false or true; // $f will be assigned to false
the explanation:
"||" has a greater precedence than "or"
its true. But a more acurate one would be
"||" has greater precedence than "or" and than "=", whereas "or" doesnt have greater precedence than "=", so
<?php
$f = false or true;
//is like writting
($f = false ) or true;
//and
$e = false || true;
is the same as
$e = (false || true);
?>
same goes for "&&" and "AND".
If you find it hard to remember operators precedence you can always use parenthesys - "(" and ")". And even if you get to learn it remember that being a good programmer is not showing you can do code with fewer words. The point of being a good programmer is writting code that is easy to understand (comment your code when necessary!), easy to maintain and with high efficiency, among other things.`

[up](https://www.php.net/manual/vote-note.php?id=125830&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125830&page=language.operators.logical&vote=down "Vote down!")

12


[**_egst_**](https://www.php.net/manual/en/language.operators.logical.php#125830) [¶](https://www.php.net/manual/en/language.operators.logical.php#125830)

**4 years ago**

``In response to Lawrence about || always returning a boolean:
Instead of
$x ? $x : 'fallback'
you can also use the "elvis operator":
$x ?: 'fallback'
which is useful in cases, where the left-hand side of the ternary operator is too long type, is too complex to calculate twice, or has side-effects.
It also combines nicely with the ?? operator, which is equivalent to an empty() check (both isset() and `!= false`):
$x->y ?? null ?: 'fallback';
instead of:
empty($x->y) ? $x->y : 'fallback'``

[up](https://www.php.net/manual/vote-note.php?id=90386&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90386&page=language.operators.logical&vote=down "Vote down!")

22


[**_momrom at freenet dot de_**](https://www.php.net/manual/en/language.operators.logical.php#90386) [¶](https://www.php.net/manual/en/language.operators.logical.php#90386)

**16 years ago**

`Evaluation of logical expressions is stopped as soon as the result is known.
If you don't want this, you can replace the and-operator by min() and the or-operator by max().
<?php
function a($x) { echo 'Expression '; return $x; }
function b($x) { echo 'is '; return $x; }
function c($x) { echo $x ? 'true.' : 'false.' ;}
c( a( false ) and b( true ) ); // Output: Expression false.
c( min( a( false ), b( true ) ) ); // Output: Expression is false.
c( a( true ) or b( true ) ); // Output: Expression true.
c( max( a( true ), b( true ) ) ); // Output: Expression is true.
?>
This way, values aren't automaticaly converted to boolean like it would be done when using and or or. Therefore, if you aren't sure the values are already boolean, you have to convert them 'by hand':
<?php
c( min( (bool) a( false ), (bool) b( true ) ) );
?>`

[up](https://www.php.net/manual/vote-note.php?id=110785&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110785&page=language.operators.logical&vote=down "Vote down!")

20


[**_phpnet at zc dot webhop dot net_**](https://www.php.net/manual/en/language.operators.logical.php#110785) [¶](https://www.php.net/manual/en/language.operators.logical.php#110785)

**12 years ago**

`This works similar to javascripts short-curcuit assignments and setting defaults. (e.g.  var a = getParm() || 'a default';)
<?php
($a = $_GET['var']) || ($a = 'a default');
?>
$a gets assigned $_GET['var'] if there's anything in it or it will fallback to 'a default'
Parentheses are required, otherwise you'll end up with $a being a boolean.`

[up](https://www.php.net/manual/vote-note.php?id=77061&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77061&page=language.operators.logical&vote=down "Vote down!")

14


[**_Andrew_**](https://www.php.net/manual/en/language.operators.logical.php#77061) [¶](https://www.php.net/manual/en/language.operators.logical.php#77061)

**18 years ago**

`> <?php
> your_function() or return "whatever";
> ?>
doesn't work because return is not an expression, it's a statement. if return was a function it'd work fine. :/`

[up](https://www.php.net/manual/vote-note.php?id=116785&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116785&page=language.operators.logical&vote=down "Vote down!")

4


[**_samantha at adrichem dot nu_**](https://www.php.net/manual/en/language.operators.logical.php#116785) [¶](https://www.php.net/manual/en/language.operators.logical.php#116785)

**10 years ago**

`<?php
    $res |= true;
    var_dump($res);
?>
does not/no longer returns a boolean (php 5.6) instead it returns int 0 or 1`

[up](https://www.php.net/manual/vote-note.php?id=115208&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115208&page=language.operators.logical&vote=down "Vote down!")

3


[**_anatoliy at ukhvanovy dot name_**](https://www.php.net/manual/en/language.operators.logical.php#115208) [¶](https://www.php.net/manual/en/language.operators.logical.php#115208)

**11 years ago**

`If you want to use the '||' operator to set a default value, like this:
<?php
$a = $fruit || 'apple'; //if $fruit evaluates to FALSE, then $a will be set to TRUE (because (bool)'apple' == TRUE)
?>
instead, you have to use the '?:' operator:
<?php
$a = ($fruit ? $fruit : 'apple');//if $fruit evaluates to FALSE, then $a will be set to 'apple'
?>
But $fruit will be evaluated twice, which is not desirable. For example fruit() will be called twice:
<?php
function fruit($confirm) {
    if($confirm)
        return 'banana';
}
$a = (fruit(1) ? fruit(1) : 'apple');//fruit() will be called twice!
?>
But since «since PHP 5.3, it is possible to leave out the middle part of the ternary operator» ( [http://www.php.net/manual/en/language.operators.comparison.php#language.operators.comparison.ternary](http://www.php.net/manual/en/language.operators.comparison.php#language.operators.comparison.ternary)), now you can code like this:
<?php
$a = ($fruit ? : 'apple'); //this will evaluate $fruit only once, and if it evaluates to FALSE, then $a will be set to 'apple'
?>
But remember that a non-empty string '0' evaluates to FALSE!
<?php
$fruit = '1';
$a = ($fruit ? : 'apple'); //this line will set $a to '1'
$fruit = '0';
$a = ($fruit ? : 'apple'); //this line will set $a to 'apple', not '0'!
?>`

[up](https://www.php.net/manual/vote-note.php?id=78166&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78166&page=language.operators.logical&vote=down "Vote down!")

6


[**_peter dot kutak at NOSPAM dot gmail dot com_**](https://www.php.net/manual/en/language.operators.logical.php#78166) [¶](https://www.php.net/manual/en/language.operators.logical.php#78166)

**18 years ago**

`$test = true and false;     ---> $test === true
$test = (true and false);  ---> $test === false
$test = true && false;      ---> $test === false
NOTE: this is due to the first line actually being
($test = true) and false;
due to "&&" having a higher precedence than "=" while "and" has a lower one`

[up](https://www.php.net/manual/vote-note.php?id=114866&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114866&page=language.operators.logical&vote=down "Vote down!")

2


[**_void at informance dot info_**](https://www.php.net/manual/en/language.operators.logical.php#114866) [¶](https://www.php.net/manual/en/language.operators.logical.php#114866)

**11 years ago**

`To assign default value in variable assignation, the simpliest solution to me is:
<?php
$v = my_function() or $v = "default";
?>
It works because, first, $v is assigned the return value from my_function(), then this value is evaluated as a part of a logical operation:
* if the left side is false, null, 0, or an empty string, the right side must be evaluated and, again, because 'or' has low precedence, $v is assigned the string "default"
* if the left side is none of the previously mentioned values, the logical operation ends and $v keeps the return value from my_function()
This is almost the same as the solution from [phpnet at zc dot webhop dot net], except that his solution (parenthesis and double pipe) doesn't take advantage of the "or" low precedence.
NOTE: "" (the empty string) is evaluated as a FALSE logical operand, so make sure that the empty string is not an acceptable value from my_function(). If you need to consider the empty string as an acceptable return value, you must go the classical "if" way.`

[up](https://www.php.net/manual/vote-note.php?id=112752&page=language.operators.logical&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112752&page=language.operators.logical&vote=down "Vote down!")

2


[**_brian at zickzickzick dot com_**](https://www.php.net/manual/en/language.operators.logical.php#112752) [¶](https://www.php.net/manual/en/language.operators.logical.php#112752)

**12 years ago**

`This has been mentioned before, but just in case you missed it:
<?php
    // Defaults --
    //If you're trying to gat 'Jack' from:
    $jack = false or 'Jack';
    // Try:
    $jack = false or $jack = 'Jack';
    //The other option is:
    $jack = false ? false : 'Jack';
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.logical&repo=en&redirect=https://www.php.net/manual/en/language.operators.logical.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google