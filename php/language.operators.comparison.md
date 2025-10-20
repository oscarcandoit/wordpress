---
url: https://www.php.net/manual/en/language.operators.comparison.php
scraped_at: 2025-10-20T02:37:18.139Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Comparison Operators [¶](https://www.php.net/manual/en/language.operators.comparison.php\#language.operators.comparison)

Comparison operators, as their name implies, allow you to compare
two values. You may also be interested in viewing
[the type comparison tables](https://www.php.net/manual/en/types.comparisons.php),
as they show examples of various type related comparisons.


| Example | Name | Result |
| --- | --- | --- |
| $a == $b | Equal | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is equal to $b after type juggling. |
| $a === $b | Identical | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is equal to $b, and they are of the same<br> type. |
| $a != $b | Not equal | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is not equal to $b after type juggling. |
| $a <> $b | Not equal | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is not equal to $b after type juggling. |
| $a !== $b | Not identical | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is not equal to $b, or they are not of the same<br> type. |
| $a < $b | Less than | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is strictly less than $b. |
| $a > $b | Greater than | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is strictly greater than $b. |
| $a <= $b | Less than or equal to | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is less than or equal to $b. |
| $a >= $b | Greater than or equal to | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if $a is greater than or equal to $b. |
| $a <=> $b | Spaceship | An [int](https://www.php.net/manual/en/language.types.integer.php) less than, equal to, or greater than zero when<br> $a is less than, equal to, or greater than<br> $b, respectively. |

**Comparison Operators**

If both operands are
[numeric strings](https://www.php.net/manual/en/language.types.numeric-strings.php),
or one operand is a number and the other one is a
[numeric string](https://www.php.net/manual/en/language.types.numeric-strings.php),
then the comparison is done numerically.
These rules also apply to the
[switch](https://www.php.net/manual/en/control-structures.switch.php) statement.
The type conversion does not take place when the comparison is
`===` or `!==` as this involves
comparing the type as well as the value.


**Warning**

Prior to PHP 8.0.0, if a [string](https://www.php.net/manual/en/language.types.string.php) is compared to a number
or a numeric string then the [string](https://www.php.net/manual/en/language.types.string.php) was converted to a
number before performing the comparison. This can lead to surprising
results as can be seen with the following example:


`<?php
var_dump(0 == "a");
var_dump("1" == "01");
var_dump("10" == "1e1");
var_dump(100 == "1e2");
switch ("a") {
case 0:
    echo "0";
    break;
case "a":
    echo "a";
    break;
}
?>`

Run code

Output of the above example in PHP 7:

```
bool(true)
bool(true)
bool(true)
bool(true)
0

```

Output of the above example in PHP 8:

```
bool(false)
bool(true)
bool(true)
bool(true)
a

```

**Example #1 Comparison Operators**

`<?php
// Integers
echo 1 <=> 1, ' '; // 0
echo 1 <=> 2, ' '; // -1
echo 2 <=> 1, ' '; // 1
// Floats
echo 1.5 <=> 1.5, ' '; // 0
echo 1.5 <=> 2.5, ' '; // -1
echo 2.5 <=> 1.5, ' '; // 1
// Strings
echo "a" <=> "a", ' '; // 0
echo "a" <=> "b", ' '; // -1
echo "b" <=> "a", ' '; // 1
echo "a" <=> "aa", ' ';  // -1
echo "zz" <=> "aa", ' '; // 1
// Arrays
echo [] <=> [], ' ';               // 0
echo [1, 2, 3] <=> [1, 2, 3], ' '; // 0
echo [1, 2, 3] <=> [], ' ';        // 1
echo [1, 2, 3] <=> [1, 2, 1], ' '; // 1
echo [1, 2, 3] <=> [1, 2, 4], ' '; // -1
// Objects
$a = (object) ["a" => "b"];
$b = (object) ["a" => "b"];
echo $a <=> $b, ' '; // 0
$a = (object) ["a" => "b"];
$b = (object) ["a" => "c"];
echo $a <=> $b, ' '; // -1
$a = (object) ["a" => "c"];
$b = (object) ["a" => "b"];
echo $a <=> $b, ' '; // 1
// not only values are compared; keys must match
$a = (object) ["a" => "b"];
$b = (object) ["b" => "b"];
echo $a <=> $b, ' '; // 1
?>`

Run code

For various types, comparison is done according to the following
table (in order).


| Type of Operand 1 | Type of Operand 2 | Result |
| --- | --- | --- |
| [null](https://www.php.net/manual/en/language.types.null.php) or [string](https://www.php.net/manual/en/language.types.string.php) | [string](https://www.php.net/manual/en/language.types.string.php) | Convert **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** to "", numerical or lexical comparison |
| [bool](https://www.php.net/manual/en/language.types.boolean.php) or [null](https://www.php.net/manual/en/language.types.null.php) | anything | Convert both sides to [bool](https://www.php.net/manual/en/language.types.boolean.php), **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** < **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |
| [object](https://www.php.net/manual/en/language.types.object.php) | [object](https://www.php.net/manual/en/language.types.object.php) | Built-in classes can define its own comparison, different classes<br> are incomparable, same class see [Object Comparison](https://www.php.net/manual/en/language.oop5.object-comparison.php) |
| [string](https://www.php.net/manual/en/language.types.string.php), [resource](https://www.php.net/manual/en/language.types.resource.php), [int](https://www.php.net/manual/en/language.types.integer.php) or [float](https://www.php.net/manual/en/language.types.float.php) | [string](https://www.php.net/manual/en/language.types.string.php), [resource](https://www.php.net/manual/en/language.types.resource.php), [int](https://www.php.net/manual/en/language.types.integer.php) or [float](https://www.php.net/manual/en/language.types.float.php) | Translate strings and resources to numbers, usual math |
| [array](https://www.php.net/manual/en/language.types.array.php) | [array](https://www.php.net/manual/en/language.types.array.php) | Array with fewer members is smaller, if key from operand 1 is not<br> found in operand 2 then arrays are incomparable, otherwise - compare<br> value by value (see following example) |
| [object](https://www.php.net/manual/en/language.types.object.php) | anything | [object](https://www.php.net/manual/en/language.types.object.php) is always greater |
| [array](https://www.php.net/manual/en/language.types.array.php) | anything | [array](https://www.php.net/manual/en/language.types.array.php) is always greater |

**Comparison with Various Types**

**Example #2 Boolean/null comparison**

`<?php
// Bool and null are compared as bool always
var_dump(1 == TRUE);  // TRUE - same as (bool) 1 == TRUE
var_dump(0 == FALSE); // TRUE - same as (bool) 0 == FALSE
var_dump(100 < TRUE); // FALSE - same as (bool) 100 < TRUE
var_dump(-10 < FALSE);// FALSE - same as (bool) -10 < FALSE
var_dump(min(-100, -10, NULL, 10, 100)); // NULL - (bool) NULL < (bool) -100 is FALSE < TRUE
?>`

Run code

**Example #3 Transcription of standard array comparison**

`<?php
// Arrays are compared like this with standard comparison operators as well as the spaceship operator.
function standard_array_compare($op1, $op2)
{
    if (count($op1) < count($op2)) {
        return -1; // $op1 < $op2
    } elseif (count($op1) > count($op2)) {
        return 1; // $op1 > $op2
    }
    foreach ($op1 as $key => $val) {
        if (!array_key_exists($key, $op2)) {
            return 1;
        } elseif ($val < $op2[$key]) {
            return -1;
        } elseif ($val > $op2[$key]) {
            return 1;
        }
    }
    return 0; // $op1 == $op2
}
?>`

**Warning**

# Comparison of floating point numbers

Because of the way [float](https://www.php.net/manual/en/language.types.float.php)s are represented internally, you
should not test two [float](https://www.php.net/manual/en/language.types.float.php)s for equality.


See the documentation for [float](https://www.php.net/manual/en/language.types.float.php) for more information.


> **Note**:
>
> Be aware that PHP's type juggling is not always obvious when comparing values of different types,
> particularly comparing [int](https://www.php.net/manual/en/language.types.integer.php)s to [bool](https://www.php.net/manual/en/language.types.boolean.php)s or [int](https://www.php.net/manual/en/language.types.integer.php)s to [string](https://www.php.net/manual/en/language.types.string.php)s. It is therefore generally
> advisable to use `===` and `!==` comparisons rather than
> `==` and `!=` in most cases.

### Incomparable Values [¶](https://www.php.net/manual/en/language.operators.comparison.php\#language.operators.comparison.incomparable)

While identity comparison ( `===` and `!==`)
can be applied to arbitrary values, the other comparison operators should only be
applied to comparable values. The result of comparing incomparable values is
undefined, and should not be relied upon.


### See Also

- [strcasecmp()](https://www.php.net/manual/en/function.strcasecmp.php)
- [strcmp()](https://www.php.net/manual/en/function.strcmp.php)
- [Array operators](https://www.php.net/manual/en/language.operators.array.php)
- [Types](https://www.php.net/manual/en/language.types.php)

### Ternary Operator [¶](https://www.php.net/manual/en/language.operators.comparison.php\#language.operators.comparison.ternary)

Another conditional operator is the "?:" (or ternary) operator.


**Example #4 Assigning a default value**

`<?php
// Example usage for: Ternary Operator
$action = (empty($_POST['action'])) ? 'default' : $_POST['action'];
// The above is identical to this if/else statement
if (empty($_POST['action'])) {
    $action = 'default';
} else {
    $action = $_POST['action'];
}
?>`

Run code

The expression `(expr1) ? (expr2) : (expr3)`
evaluates to expr2 if
expr1 evaluates to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, and
expr3 if
expr1 evaluates to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


It is possible to leave out the middle part of the ternary operator.
Expression `expr1 ?: expr3` evaluates to
the result of expr1 if expr1
evaluates to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, and expr3 otherwise.
expr1 is only evaluated once in this case.


> **Note**:
>
> Please note that the ternary operator is an expression, and that it
> doesn't evaluate to a variable, but to the result of an expression. This
> is important to know if you want to return a variable by reference.
> The statement `return $var == 42 ? $a : $b;` in a
> return-by-reference function will therefore not work and a warning is
> issued.

> **Note**:
>
>
> It is recommended to avoid "stacking" ternary expressions.
> PHP's behaviour when using more than one unparenthesized ternary operator within a single
> expression is non-obvious compared to other languages.
> Indeed prior to PHP 8.0.0, ternary expressions were evaluated left-associative,
> instead of right-associative like most other programming languages.
> Relying on left-associativity is deprecated as of PHP 7.4.0.
> As of PHP 8.0.0, the ternary operator is non-associative.
>
>
> **Example #5 Non-obvious Ternary Behaviour**
>
> `<?php
> // on first glance, the following appears to output 'true'
> echo (true ? 'true' : false ? 't' : 'f');
> // however, the actual output of the above is 't' prior to PHP 8.0.0
> // this is because ternary expressions are left-associative
> // the following is a more obvious version of the same code as above
> echo ((true ? 'true' : false) ? 't' : 'f');
> // here, one can see that the first expression is evaluated to 'true', which
> // in turn evaluates to (bool) true, thus returning the true branch of the
> // second ternary expression.
> ?>`
>
> Run code

> **Note**:
>
>
> Chaining of short-ternaries ( `?:`), however, is stable and behaves reasonably.
> It will evaluate to the first argument that evaluates to a non-falsy value. Note that undefined
> values will still raise a warning.
>
>
> **Example #6 Short-ternary chaining**
>
> `<?php
> echo 0 ?: 1 ?: 2 ?: 3, PHP_EOL; //1
> echo 0 ?: 0 ?: 2 ?: 3, PHP_EOL; //2
> echo 0 ?: 0 ?: 0 ?: 3, PHP_EOL; //3
> ?>`
>
> Run code

### Null Coalescing Operator [¶](https://www.php.net/manual/en/language.operators.comparison.php\#language.operators.comparison.coalesce)

Another useful shorthand operator is the "??" (or null coalescing) operator.


**Example #7 Assigning a default value**

`<?php
// Example usage for: Null Coalesce Operator
$action = $_POST['action'] ?? 'default';
// The above is identical to this if/else statement
if (isset($_POST['action'])) {
    $action = $_POST['action'];
} else {
    $action = 'default';
}
?>`

Run code

The expression `(expr1) ?? (expr2)` evaluates to
expr2 if expr1 is
**`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, and expr1 otherwise.


In particular, this operator does not emit a notice or warning if the left-hand side
value does not exist, just like [isset()](https://www.php.net/manual/en/function.isset.php). This is especially
useful on array keys.


> **Note**:
>
> Please note that the null coalescing operator is an expression, and that it
> doesn't evaluate to a variable, but to the result of an expression. This
> is important to know if you want to return a variable by reference.
> The statement `return $foo ?? $bar;` in a
> return-by-reference function will therefore not work and a warning is
> issued.

> **Note**:
>
>
> The null coalescing operator has low precedence. That means if mixing it
> with other operators (such as string concatenation or arithmetic operators)
> parentheses will likely be required.
>
>
> `<?php
> // Raises a warning that $name is undefined.
> print 'Mr. ' . $name ?? 'Anonymous';
> // Prints "Mr. Anonymous"
> print 'Mr. ' . ($name ?? 'Anonymous');
> ?>`

> **Note**:
>
>
> Please note that the null coalescing operator allows for simple nesting:
>
>
> **Example #8 Nesting null coalescing operator**
>
> `<?php
> $foo = null;
> $bar = null;
> $baz = 1;
> $qux = 2;
> echo $foo ?? $bar ?? $baz ?? $qux; // outputs 1
> ?>`
>
> Run code

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/operators/comparison.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.operators.comparison%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.comparison&repo=en&redirect=https://www.php.net/manual/en/language.operators.comparison.php)

### User Contributed Notes 14 notes

[up](https://www.php.net/manual/vote-note.php?id=95997&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95997&page=language.operators.comparison&vote=down "Vote down!")

170


[**_crazy888s at hotmail dot com_**](https://www.php.net/manual/en/language.operators.comparison.php#95997) [¶](https://www.php.net/manual/en/language.operators.comparison.php#95997)

**15 years ago**

`I couldn't find much info on stacking the new ternary operator, so I ran some tests:
<?php
echo 0 ?: 1 ?: 2 ?: 3; //1
echo 1 ?: 0 ?: 3 ?: 2; //1
echo 2 ?: 1 ?: 0 ?: 3; //2
echo 3 ?: 2 ?: 1 ?: 0; //3
echo 0 ?: 1 ?: 2 ?: 3; //1
echo 0 ?: 0 ?: 2 ?: 3; //2
echo 0 ?: 0 ?: 0 ?: 3; //3
?>
It works just as expected, returning the first non-false value within a group of expressions.`

[up](https://www.php.net/manual/vote-note.php?id=128337&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128337&page=language.operators.comparison&vote=down "Vote down!")

6


[**_gfilippakis at sleed dot gr_**](https://www.php.net/manual/en/language.operators.comparison.php#128337) [¶](https://www.php.net/manual/en/language.operators.comparison.php#128337)

**2 years ago**

`Please note that using the null coalescing operator to check properties on a class that has the __get magic method (without an __isset magic method) invokes the magic method.
For example:
<?php
class A
{
    public function __get($property)
    {
        echo 'Called __get for ' . $property . PHP_EOL;
    }
}
$a = new A();
echo 'Trying null coalescing operator' . PHP_EOL;
$b = $a->test ?? 5;
echo 'Trying isset()' . PHP_EOL;
if (isset($a->test)) {
    $b = $a->test;
} else {
    $b = 5;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=126040&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126040&page=language.operators.comparison&vote=down "Vote down!")

10


[**_Tahazzot_**](https://www.php.net/manual/en/language.operators.comparison.php#126040) [¶](https://www.php.net/manual/en/language.operators.comparison.php#126040)

**4 years ago**

`Very careful when reading PHP documentation, Here's a lot of miss information.
According to documentation, They say's (int) 0 == (string) "a" is true. But it is not in PHP 8.
var_dump(0 == "a"); // 0 == 0 -> true
Now In PHP 8 it's False.`

[up](https://www.php.net/manual/vote-note.php?id=65863&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=65863&page=language.operators.comparison&vote=down "Vote down!")

21


[**_adam at caucho dot com_**](https://www.php.net/manual/en/language.operators.comparison.php#65863) [¶](https://www.php.net/manual/en/language.operators.comparison.php#65863)

**19 years ago**

`Note: according to the spec, PHP's comparison operators are not transitive.  For example, the following are all true in PHP5:
"11" < "a" < 2 < "11"
As a result, the outcome of sorting an array depends on the order the elements appear in the pre-sort array.  The following code will dump out two arrays with *different* orderings:
<?php
$a = array(2,    "a",  "11", 2);
$b = array(2,    "11", "a",  2);
sort($a);
var_dump($a);
sort($b);
var_dump($b);
?>
This is not a bug report -- given the spec on this documentation page, what PHP does is "correct".  But that may not be what was intended...`

[up](https://www.php.net/manual/vote-note.php?id=60866&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60866&page=language.operators.comparison&vote=down "Vote down!")

16


[**_rshawiii at yahoo dot com_**](https://www.php.net/manual/en/language.operators.comparison.php#60866) [¶](https://www.php.net/manual/en/language.operators.comparison.php#60866)

**19 years ago**

`You can't just compare two arrays with the === operator
like you would think to find out if they are equal or not.  This is more complicated when you have multi-dimensional arrays.  Here is a recursive comparison function.
<?php
/**
* Compares two arrays to see if they contain the same values.  Returns TRUE or FALSE.
* usefull for determining if a record or block of data was modified (perhaps by user input)
* prior to setting a "date_last_updated" or skipping updating the db in the case of no change.
*
* @param array $a1
* @param array $a2
* @return boolean
*/
function array_compare_recursive($a1, $a2)
{
if (!(is_array($a1) and (is_array($a2)))) { return FALSE;}

if (!count($a1) == count($a2))
      {
       return FALSE; // arrays don't have same number of entries
      }

foreach ($a1 as $key => $val)
{
       if (!array_key_exists($key, $a2))
           {return FALSE; // uncomparable array keys don't match
              }
       elseif (is_array($val) and is_array($a2[$key]))  // if both entries are arrays then compare recursive
           {if (!array_compare_recursive($val,$a2[$key])) return FALSE;
           }
       elseif (!($val === $a2[$key])) // compare entries must be of same type.
           {return FALSE;
           }
}
return TRUE; // $a1 === $a2
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=124639&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124639&page=language.operators.comparison&vote=down "Vote down!")

4


[**_Sumon Mahmud_**](https://www.php.net/manual/en/language.operators.comparison.php#124639) [¶](https://www.php.net/manual/en/language.operators.comparison.php#124639)

**5 years ago**

`Extending from here: [https://www.php.net/manual/en/language.operators.comparison.php#121907](https://www.php.net/manual/en/language.operators.comparison.php#121907)
$a = ['a' => 1, 'b' => 2, 'c' => 3, 'e' => 4];
$b = ['a' => 1, 'b' => 2, 'd' => 3, 'e' => 4];
echo $a > $b; // 0
echo $b > $a; // 0
echo $a <$b; // 0
echo $b < $a; // 0
If using spaceship operator then it is returning true like :
echo $a <=> $b; //1
echo $b <=> $a; //1
echo $a <=> $b; //1
echo $b <=> $a; //1`

[up](https://www.php.net/manual/vote-note.php?id=70762&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70762&page=language.operators.comparison&vote=down "Vote down!")

12


[**_bishop_**](https://www.php.net/manual/en/language.operators.comparison.php#70762) [¶](https://www.php.net/manual/en/language.operators.comparison.php#70762)

**18 years ago**

`When you want to know if two arrays contain the same values, regardless of the values' order, you cannot use "==" or "===".  In other words:
<?php
(array(1,2) == array(2,1)) === false;
?>
To answer that question, use:
<?php
function array_equal($a, $b) {
    return (is_array($a) && is_array($b) && array_diff($a, $b) === array_diff($b, $a));
}
?>
A related, but more strict problem, is if you need to ensure that two arrays contain the same key=>value pairs, regardless of the order of the pairs.  In that case, use:
<?php
function array_identical($a, $b) {
    return (is_array($a) && is_array($b) && array_diff_assoc($a, $b) === array_diff_assoc($b, $a));
}
?>
Example:
<?php
$a = array (2, 1);
$b = array (1, 2);
// true === array_equal($a, $b);
// false === array_identical($a, $b);
$a = array ('a' => 2, 'b' => 1);
$b = array ('b' => 1, 'a' => 2);
// true === array_identical($a, $b)
// true === array_equal($a, $b)
?>
(See also the solution "rshawiii at yahoo dot com" posted)`

[up](https://www.php.net/manual/vote-note.php?id=127428&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127428&page=language.operators.comparison&vote=down "Vote down!")

6


[**_admin at zeros dot co dot id_**](https://www.php.net/manual/en/language.operators.comparison.php#127428) [¶](https://www.php.net/manual/en/language.operators.comparison.php#127428)

**3 years ago**

``Please be careful when you try to compare strings that have a plus sign `+` at the beginning (such as phone number, etc). When you use the Equal operator `==` PHP will ignore the plus sign. Use Identical operator `===` instead
Example:
$str1 = "62";
$str2 = "+62";
var_dump($str1 == $str2); // bool(true)
var_dump($str1 === $str2); // bool(false)``

[up](https://www.php.net/manual/vote-note.php?id=128803&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128803&page=language.operators.comparison&vote=down "Vote down!")

3


[**_Hayley Watson_**](https://www.php.net/manual/en/language.operators.comparison.php#128803) [¶](https://www.php.net/manual/en/language.operators.comparison.php#128803)

**2 years ago**

`Between the "shortcut ternary" (aka "elvis") and "spaceship" operators, you can write some quite compact comparison functions for usort and its ilk.
If you want to sort an array of associative arrays by several different keys you can chain them in the same way that you can list column names in an SQL ORDER BY clause.
<?php
usort($array, fn($a, $b) => $a['a'] <=> $b['a']
                         ?: $b['b'] <=> $a['b']
                         ?: $a['c'] <=> $b['c']);
?>
Will sort the array by column 'a', then by column 'b' descending, then by column 'c'; or in SQL-speak 'ORDER BY a, b DESC, c".`

[up](https://www.php.net/manual/vote-note.php?id=124201&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124201&page=language.operators.comparison&vote=down "Vote down!")

5


[**_Ryan Mott_**](https://www.php.net/manual/en/language.operators.comparison.php#124201) [¶](https://www.php.net/manual/en/language.operators.comparison.php#124201)

**6 years ago**

`Searching for "double question mark" operator should find this page (and hopefully after this comment the crawlers will agree)`

[up](https://www.php.net/manual/vote-note.php?id=121907&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121907&page=language.operators.comparison&vote=down "Vote down!")

4


[**_niall at maranelda dot org_**](https://www.php.net/manual/en/language.operators.comparison.php#121907) [¶](https://www.php.net/manual/en/language.operators.comparison.php#121907)

**7 years ago**

`Care must be taken when using the spaceship operator with arrays that do not have the same keys:
- Contrary to the notes above ("Example #2 Transcription of standard array comparison"), it does *not* return null if the left-hand array contains a key that the right-hand array does not.
- Because of this, the result depends on the order you do the comparison in.
For example:
<?php
$a = ['a' => 1, 'b' => 2, 'c' => 3, 'e' => 4];
$b = ['a' => 1, 'b' => 2, 'd' => 3, 'e' => 4];
var_dump($a <=> $b);        // int(1) : $a > $b because $a has the 'c' key and $b doesn't.
var_dump($b <=> $a);        // int(1) : $b > $a because $b has the 'd' key and $a doesn't.
?>`

[up](https://www.php.net/manual/vote-note.php?id=104840&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104840&page=language.operators.comparison&vote=down "Vote down!")

5


[**_Cuong Huy To_**](https://www.php.net/manual/en/language.operators.comparison.php#104840) [¶](https://www.php.net/manual/en/language.operators.comparison.php#104840)

**14 years ago**

`In the table "Comparison with Various Types", please move the last line about "Object" to be above the line about "Array", since Object is considered to be greater than Array (tested on 5.3.3)
(Please remove my "Anonymous" post of the same content before. You could check IP to see that I forgot to type my name)`

[up](https://www.php.net/manual/vote-note.php?id=117511&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117511&page=language.operators.comparison&vote=down "Vote down!")

1


[**_Marcin Kuzawiski_**](https://www.php.net/manual/en/language.operators.comparison.php#117511) [¶](https://www.php.net/manual/en/language.operators.comparison.php#117511)

**10 years ago**

`A < B and still B < A...
$A = [1 => 1, 2 => 0, 3 => 1];
$B = [1 => 1, 3 => 0, 2 => 1];
var_dump($A < $B);  // TRUE
var_dump($B < $A);  // TRUE
var_dump($A > $B);  // TRUE
var_dump($B > $A);  // TRUE
Next - C and D are comparable, but neither C < D nor D < C (and still C != D)...
$C = [1 => 1, 2 => 1, 3 => 0];
$D = [1 => 1, 3 => 1, 2 => 0];
var_dump($C < $D); // FALSE
var_dump($D < $C); // FALSE
var_dump($C > $D); // FALSE
var_dump($D > $C); // FALSE
var_dump($D == $C); // FALSE`

[up](https://www.php.net/manual/vote-note.php?id=129994&page=language.operators.comparison&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129994&page=language.operators.comparison&vote=down "Vote down!")

 -2


[**_billynoah at gmail dot com_**](https://www.php.net/manual/en/language.operators.comparison.php#129994) [¶](https://www.php.net/manual/en/language.operators.comparison.php#129994)

**8 months ago**

`It's worth noting that there can be a difference in the logical operation of shorthand ternary (expr1 ?: expr2) vs the full version (expr1 ? expr1 : expr2). The shorthand style may also offer a slight performance enhancement because the initial expression will only be evaluated once.
Example:
<?php
// my_func() will be called twice here
// additionally, my_func() may not return the same value both times!
$var = my_func() ? my_func() : false;
// my_func() will only be called once here
$var = my_func() ?: false;`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.comparison&repo=en&redirect=https://www.php.net/manual/en/language.operators.comparison.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google