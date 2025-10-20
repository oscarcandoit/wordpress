---
url: https://www.php.net/manual/en/function.empty.php
scraped_at: 2025-10-20T03:01:26.821Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# empty

(PHP 4, PHP 5, PHP 7, PHP 8)

empty — Determine whether a variable is empty

### Description [¶](https://www.php.net/manual/en/function.empty.php\#refsect1-function.empty-description)

**empty**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$var`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Determine whether a variable is considered to be empty. A variable is considered empty if it does not exist or if its value equals **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**. **empty()** does not generate a warning if the variable does not exist.


### Parameters [¶](https://www.php.net/manual/en/function.empty.php\#refsect1-function.empty-parameters)

`var`

Variable to be checked


No warning is generated if the variable does not exist.
That means **empty()** is essentially the
concise equivalent to **!isset($var) \|\| $var == false**.
This also applies to nested structures, such as a multidimensional array or chained properties.


### Return Values [¶](https://www.php.net/manual/en/function.empty.php\#refsect1-function.empty-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if `var` does not exist or has a value that is empty or equal to zero,
aka falsey, see [conversion to boolean](https://www.php.net/manual/en/language.types.boolean.php#language.types.boolean.casting).
Otherwise returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


### Examples [¶](https://www.php.net/manual/en/function.empty.php\#refsect1-function.empty-examples)

**Example #1**
**A simple **empty()** / [isset()](https://www.php.net/manual/en/function.isset.php)**
**comparison.**

`<?php
$var = 0;
// Evaluates to true because $var is empty
if (empty($var)) {
    echo '$var is either 0, empty, or not set at all';
}
// Evaluates as true because $var is set
if (isset($var)) {
    echo '$var is set even though it is empty';
}
?>`

Run code

**Example #2 **empty()** on String Offsets**

`<?php
$expected_array_got_string = 'somestring';
var_dump(empty($expected_array_got_string['some_key']));
var_dump(empty($expected_array_got_string[0]));
var_dump(empty($expected_array_got_string['0']));
var_dump(empty($expected_array_got_string['0.5']));
var_dump(empty($expected_array_got_string['0 Mostel']));
?>`

Run code

The above example will output:

```
bool(true)
bool(false)
bool(false)
bool(true)
bool(true)
```

**Example #3 **empty()** on multidimensional arrays**

`<?php
$multidimensional = [\
    'some' => [\
        'deep' => [\
            'nested' => 'value'\
        ]\
    ]\
];
if (!empty($multidimensional['some']['some']['nested'])) {
    $someVariable = $multidimensional['some']['deep']['nested'];
}
var_dump(empty($multidimensional['some-undefined-key']));
var_dump(empty($multidimensional['some']['deep']['unknown']));
var_dump(empty($multidimensional['some']['deep']['nested']));
?>`

Run code

The above example will output:

```
bool(true)
bool(true)
bool(false)
```

### Notes [¶](https://www.php.net/manual/en/function.empty.php\#refsect1-function.empty-notes)

> **Note**: Because this is a
> language construct and not a function, it cannot be called using
> [variable functions](https://www.php.net/manual/en/functions.variable-functions.php),
> or [named arguments](https://www.php.net/manual/en/functions.arguments.php#functions.named-arguments).

> **Note**:
>
>
> When using **empty()** on inaccessible object properties,
> the [\_\_isset()](https://www.php.net/manual/en/language.oop5.overloading.php#object.isset)
> overloading method will be called, if declared.

### See Also [¶](https://www.php.net/manual/en/function.empty.php\#refsect1-function.empty-seealso)

- [isset()](https://www.php.net/manual/en/function.isset.php) \- Determine if a variable is declared and is different than null
- [\_\_isset()](https://www.php.net/manual/en/language.oop5.overloading.php#object.isset)
- [unset()](https://www.php.net/manual/en/function.unset.php) \- unset a given variable
- [array\_key\_exists()](https://www.php.net/manual/en/function.array-key-exists.php) \- Checks if the given key or index exists in the array
- [count()](https://www.php.net/manual/en/function.count.php) \- Counts all elements in an array or in a Countable object
- [strlen()](https://www.php.net/manual/en/function.strlen.php) \- Get string length
- [The type comparison tables](https://www.php.net/manual/en/types.comparisons.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/functions/empty.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.empty%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.empty&repo=en&redirect=https://www.php.net/manual/en/function.empty.php)

### User Contributed Notes 36 notes

[up](https://www.php.net/manual/vote-note.php?id=114267&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114267&page=function.empty&vote=down "Vote down!")

256


[**_Nanhe Kumar_**](https://www.php.net/manual/en/function.empty.php#114267) [¶](https://www.php.net/manual/en/function.empty.php#114267)

**11 years ago**

`<?php
/**
* @author :  Nanhe Kumar <nanhe.kumar@gmail.com>
* List of all empty values
**/
$testCase = array(
    1 => '',
    2 => "",
    3 => null,
    4 => array(),
    5 => FALSE,
    6 => NULL,
    7=>'0',
    8=>0,

);
foreach ($testCase as $k => $v) {
    if (empty($v)) {
        echo "<br> $k=>$v is empty";
    }
}
/**
Output
1=> is empty
2=> is empty
3=> is empty
4=>Array is empty
5=> is empty
6=> is empty
7=>0 is empty
8=>0 is empty
**/
?>`

[up](https://www.php.net/manual/vote-note.php?id=93117&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93117&page=function.empty&vote=down "Vote down!")

96


[**_Janci_**](https://www.php.net/manual/en/function.empty.php#93117) [¶](https://www.php.net/manual/en/function.empty.php#93117)

**16 years ago**

`Please note that results of empty() when called on non-existing / non-public variables of a class are a bit confusing if using magic method __get (as previously mentioned by nahpeps at gmx dot de). Consider this example:
<?php
class Registry
{
    protected $_items = array();
    public function __set($key, $value)
    {
        $this->_items[$key] = $value;
    }
    public function __get($key)
    {
        if (isset($this->_items[$key])) {
            return $this->_items[$key];
        } else {
            return null;
        }
    }
}
$registry = new Registry();
$registry->empty = '';
$registry->notEmpty = 'not empty';
var_dump(empty($registry->notExisting)); // true, so far so good
var_dump(empty($registry->empty)); // true, so far so good
var_dump(empty($registry->notEmpty)); // true, .. say what?
$tmp = $registry->notEmpty;
var_dump(empty($tmp)); // false as expected
?>
The result for empty($registry->notEmpty) is a bit unexpeced as the value is obviously set and non-empty. This is due to the fact that the empty() function uses __isset() magic functin in these cases. Although it's noted in the documentation above, I think it's worth mentioning in more detail as the behaviour is not straightforward. In order to achieve desired (expexted?) results, you need to add  __isset() magic function to your class:
<?php
class Registry
{
    protected $_items = array();
    public function __set($key, $value)
    {
        $this->_items[$key] = $value;
    }
    public function __get($key)
    {
        if (isset($this->_items[$key])) {
            return $this->_items[$key];
        } else {
            return null;
        }
    }
    public function __isset($key)
    {
        if (isset($this->_items[$key])) {
            return (false === empty($this->_items[$key]));
        } else {
            return null;
        }
    }
}
$registry = new Registry();
$registry->empty = '';
$registry->notEmpty = 'not empty';
var_dump(empty($registry->notExisting)); // true, so far so good
var_dump(empty($registry->empty)); // true, so far so good
var_dump(empty($registry->notEmpty)); // false, finally!
?>
It actually seems that empty() is returning negation of the __isset() magic function result, hence the negation of the empty() result in the __isset() function above.`

[up](https://www.php.net/manual/vote-note.php?id=103756&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103756&page=function.empty&vote=down "Vote down!")

69


[**_steven at nevvix dot com_**](https://www.php.net/manual/en/function.empty.php#103756) [¶](https://www.php.net/manual/en/function.empty.php#103756)

**14 years ago**

`When you need to accept these as valid, non-empty values:
- 0 (0 as an integer)
- 0.0 (0 as a float)
- "0" (0 as a string)
<?php
function is_blank($value) {
    return empty($value) && !is_numeric($value);
}
?>
This is similar to Rails' blank? method.`

[up](https://www.php.net/manual/vote-note.php?id=123147&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123147&page=function.empty&vote=down "Vote down!")

6


[**_GazetteSDF_**](https://www.php.net/manual/en/function.empty.php#123147) [¶](https://www.php.net/manual/en/function.empty.php#123147)

**7 years ago**

`For the verification of a form, to "block" entries such as a simple space or other, I thought of this combination:
function isEmpty($string){
    $val = preg_replace('#[^A-Za-z0-9]+#', '', $string) ;
    $val = trim($string, '');
    return ($string=='') ;
}
This protects entries like: ' ' ,'  -  ', '. - +', ... On entries like name, profession, ... it's helpful`

[up](https://www.php.net/manual/vote-note.php?id=83361&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=83361&page=function.empty&vote=down "Vote down!")

13


[**_tom at tomwardrop dot com_**](https://www.php.net/manual/en/function.empty.php#83361) [¶](https://www.php.net/manual/en/function.empty.php#83361)

**17 years ago**

`In reply to "admin at ninthcircuit dot info",
Using str_replace is unnecessary. I would encourage the use of trim which would most likely be faster (haven't tested) and easier. Trim also takes care of other white space like line breaks and tabs. Actually, in most of the applications I code, I use a multi-dimensional array map function with trim on the Super Globals such as $_POST, $_GET and $_COOKIE as so far, there hasn't been an instance where I would want any user input to begin or end with whitespace. The good thing about doing this is that you never have to worry about 'trimming' your input which makes your code easier and more reliable (incase you forget to trim some input).`

[up](https://www.php.net/manual/vote-note.php?id=126263&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126263&page=function.empty&vote=down "Vote down!")

12


[**_info at ensostudio dot ru_**](https://www.php.net/manual/en/function.empty.php#126263) [¶](https://www.php.net/manual/en/function.empty.php#126263)

**4 years ago**

`Multiple empty():
<?php
/**
* Multiple empty().
*
* @param mixed[] $vars Variables to test
* @return bool
*/
function multi_empty(& ...$vars)
{
    // no callback is supplied, all empty values will be removed
    return array_filter($vars) === [];
}
?>
example:
<?php
$notEmptyVar = 1;
$emptyVar = null;
// $undefinedVar - not defined
multi_empty($emptyVar); // true
multi_empty($emptyVar, $undefinedVar); // true
multi_empty($notEmptyVar , $emptyVar); // false
multi_empty($notEmptyVar , $emptyVar, $undefinedVar); // false
?>`

[up](https://www.php.net/manual/vote-note.php?id=115692&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115692&page=function.empty&vote=down "Vote down!")

16


[**_chrisdmiddleton at gmail dot com_**](https://www.php.net/manual/en/function.empty.php#115692) [¶](https://www.php.net/manual/en/function.empty.php#115692)

**11 years ago**

`If you want to use empty() to evaluate an expression (not a variable), and you don't have PHP 5.5+, you can do it by wrapping the call to empty in a function, like so:
<?php
function is_empty($var) {
    return empty($var);
}
?>
Then you can do something like
<?php
if(is_empty(NULL)) {
/* ... */
}
?>
without issue, since the local variable $var is being tested rather than the expression in the function call itself.`

[up](https://www.php.net/manual/vote-note.php?id=116388&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116388&page=function.empty&vote=down "Vote down!")

18


[**_your dot brother dot t at hotmail dot com_**](https://www.php.net/manual/en/function.empty.php#116388) [¶](https://www.php.net/manual/en/function.empty.php#116388)

**10 years ago**

``(experienced in PHP 5.6.3) The `empty()` can't evaluate `__get()` results explicitly, so the `empty()` statement bellow always renders true
<?php
class Juice extends Liquid{
protected $apple;
protected $orange;
public function __get($name) {
      return $this->$name;
}
public function __construct($apple, $orange) {
      $this->apple = $apple;
      $this->orange = $orange;
}
}
class Glass {
protected $liquid;
public function __get($name) {
      return $name == "liquid" ? $this->liquid : false;
}
public function __construct() {
      $this->juice = new Juice(3, 5);
}
}
$glass = new Glass();
var_dump(empty($this->liquid->apple));
/**
* The output is:
* bool(true)
*/
?>
The correct way is to force the evaluation of `__get()` first, by using extra braces around implicit statements like this:
<?php
var_dump(empty(($this->liquid->apple)));
/**
* The output is:
* bool(false)
*/
?>
So if you are using packages that utilize object oriented designs and magic methods like `__get()`, it's a good practice to always use double braces for `empty()` calls.``

[up](https://www.php.net/manual/vote-note.php?id=120871&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120871&page=function.empty&vote=down "Vote down!")

13


[**_Claudio Galdiolo_**](https://www.php.net/manual/en/function.empty.php#120871) [¶](https://www.php.net/manual/en/function.empty.php#120871)

**8 years ago**

`Warning: an "empty" object is NOT considered to be empty
<?php
$var = new stdClass(); // "empty" object
var_dump(empty($var)); // bool(false)
?>
I don't know if there is a standard way to test for "empty" objects, I personally use array casting:
<?php
$var = new stdClass(); // "empty" object
$var = (array) $var; // cast to empty array
var_dump(empty($var)); // bool(true)
?>`

[up](https://www.php.net/manual/vote-note.php?id=123719&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123719&page=function.empty&vote=down "Vote down!")

10


[**_markmanning at gmail dot com_**](https://www.php.net/manual/en/function.empty.php#123719) [¶](https://www.php.net/manual/en/function.empty.php#123719)

**6 years ago**

`I normally count() an array, so I wanted to see how empty() would stack up.
<?php
    $test = array();
    $test2 = array();
    for ($x = 0; $x < 1000; $x++)  $test[] = $x;
    $ts = microtime(true);
    for ($x = 0; $x < 100000000; $x++)
    {
        if (count($test))
        {
        }
    }
    echo "Time taken:  " . (microtime(true) - $ts) . " sec\n";
?>
For 100,000,000 comparisons, here are the results against PHP 7.2.16 on my hardware:
count($test):  2.697 sec
count($test2):  2.596 sec
$test === array():  2.579 sec
$test2 === array():  2.552 sec
empty($test):  3.085 sec
empty($test2):  3.113 sec
In short, it doesn't matter what method is used although empty() is actually just ever so slightly slower despite it being a language construct.  YMMV.`

[up](https://www.php.net/manual/vote-note.php?id=91182&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91182&page=function.empty&vote=down "Vote down!")

7


[**_mlibazisi mabandla_**](https://www.php.net/manual/en/function.empty.php#91182) [¶](https://www.php.net/manual/en/function.empty.php#91182)

**16 years ago**

`in cases when "0" is not intended to be empty, here is a simple function to safely test for an empty string (or mixed variable):
<?php
function _empty($string){
     $string = trim($string);
     if(!is_numeric($string)) return empty($string);
     return FALSE;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=107926&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107926&page=function.empty&vote=down "Vote down!")

19


[**_martin dot aarhof at gmail dot com_**](https://www.php.net/manual/en/function.empty.php#107926) [¶](https://www.php.net/manual/en/function.empty.php#107926)

**13 years ago**

`<?php
$str = '            ';
var_dump(empty($str)); // boolean false
?>
So remember to trim your strings first!
<?php
$str = '        ';
$str = trim($str);
var_dump(empty($str)); // boolean true
?>`

[up](https://www.php.net/manual/vote-note.php?id=96997&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96997&page=function.empty&vote=down "Vote down!")

10


[**_aidan1103 at yahoo dot com_**](https://www.php.net/manual/en/function.empty.php#96997) [¶](https://www.php.net/manual/en/function.empty.php#96997)

**15 years ago**

`empty() should not necessarily return the negation of the __isset() magic function result, if you set a data member to 0, isset() should return true and empty should also return true.  A simpler implementation of the __isset magic function would be:
public function __isset($key) {
return isset($this->{$key});
}
I don't understand why this isn't included in stdClass and inherited by default.`

[up](https://www.php.net/manual/vote-note.php?id=42591&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=42591&page=function.empty&vote=down "Vote down!")

10


[**_paul at worldwithoutwalls dot co dot uk_**](https://www.php.net/manual/en/function.empty.php#42591) [¶](https://www.php.net/manual/en/function.empty.php#42591)

**21 years ago**

`Note the exceptions when it comes to decimal numbers:
<?php
$a = 0.00;
$b = '0.00';
echo (empty($a)? "empty": "not empty"); //result empty
echo (empty($b)? "empty": "not empty"); //result not empty
//BUT...
$c = intval($b);
echo (empty($c)? "empty": "not empty"); //result empty
?>
For those of you using MySQL, if you have a table with a column of decimal type, when you do a SELECT, your data will be returned as a string, so you'll need to do apply intval() before testing for empty.
e.g.
TABLE t has columns id MEDIUMINT and d DECIMAL(4,2)
and contains 1 row where id=1, d=0.00
<?php
$q = "SELECT * FROM t";
$res = mysql_query($q);
$row = mysql_fetch_assoc($res);
echo (empty($row['d'])? "empty": "not empty"); //result not empty
?>`

[up](https://www.php.net/manual/vote-note.php?id=121299&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121299&page=function.empty&vote=down "Vote down!")

4


[**_wranvaud at gmail dot com_**](https://www.php.net/manual/en/function.empty.php#121299) [¶](https://www.php.net/manual/en/function.empty.php#121299)

**8 years ago**

`Note that if your variable only has an "end of line" (aka carriage return), PHP_EOL it is not considered as empty. Since end of lines are not always easy to spot this can be confusing.`

[up](https://www.php.net/manual/vote-note.php?id=100036&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100036&page=function.empty&vote=down "Vote down!")

9


[**_ehsmeng_**](https://www.php.net/manual/en/function.empty.php#100036) [¶](https://www.php.net/manual/en/function.empty.php#100036)

**15 years ago**

`I can't use empty() in all situations because '0' is usually not considered empty to me. I did a quick benchmark over the most common ways of testing it. '' == var suffers from '' == 0 is true so that's just there for curiosity.
<?php
    $microtimeref = microtime(true);
    $a = 0;
    $b = 'asd';
    for ($i = 0; $i < 5000000; $i++)
    {
        if (0 == mb_strlen ($b))
        {
            $a++;
        }
    }
    echo "Total time 0 == mb_strlen(var): <b>" . round(microtime(true) - $microtimeref,3) . 's</b><br />';
?>
The results:
Total time 0 == mb_strlen(var): 3.141s
Total time 0 === strlen(var): 2.904s
Total time 0 == strlen(var): 2.878s
Total time '' == var: 1.774s
Total time '' === var: 1.706s
Total time empty(var): 1.496s
Thus '' === var will be my zero length string test.`

[up](https://www.php.net/manual/vote-note.php?id=85215&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85215&page=function.empty&vote=down "Vote down!")

12


[**_Anonymous_**](https://www.php.net/manual/en/function.empty.php#85215) [¶](https://www.php.net/manual/en/function.empty.php#85215)

**17 years ago**

`To add on to what anon said, what's happening in john_jian's example seems unusual because we don't see the implicit typecasting going on behind the scenes.  What's really happening is:
$a = '';
$b = 0;
$c = '0';
(int)$a == $b -> true, because any string that's not a number gets converted to 0
$b==(int)$c -> true, because the int in the string gets converted
and
$a==$c -> false, because they're being compared as strings, rather than integers.  (int)$a==(int)$c should return true, however.
Note: I don't remember if PHP even *has* typecasting, much less if this is the correct syntax.  I'm just using something for the sake of examples.`

[up](https://www.php.net/manual/vote-note.php?id=101988&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101988&page=function.empty&vote=down "Vote down!")

13


[**_phpsort_**](https://www.php.net/manual/en/function.empty.php#101988) [¶](https://www.php.net/manual/en/function.empty.php#101988)

**14 years ago**

`I'm summarising a few points on empty() with inaccessible properties, in the hope of saving others a bit of time. Using PHP 5.3.2.
<?php
class MyClass {
    private $foo = 'foo';
}
$myClass = new MyClass;
echo $myClass->foo;
?>
As expected, this gives "Fatal error: Cannot access private property MyClass::$foo".
But substitute the line
if (empty($myClass->foo)) echo 'foo is empty'; else echo 'foo is not empty';
and we get the misleading result "foo is empty".
There is NO ERROR OR WARNING, so this is a real gotcha. Your code will just go wrong silently, and I would say it amounts to a bug.
If you add two magic functions to the class:
public function __get($var) { return $this->$var; }
public function __isset($var) { return isset($this->$var); }
then we get the expected result. You need both functions.
For empty($myClass->foo), I believe PHP calls __isset, and if that is true returns the result of empty on the result of __get. (Some earlier posts wrongly suggest PHP just returns the negation of __isset).
BUT …
See the earlier post by php at lanar dot com. I confirm those results, and if you extend the test with isset($x->a->b->c) it appears that __isset is only called for the last property in the chain. Arguably another bug. empty() behaves in the same way. So things are not as clear as we might hope.
See also the note on empty() at
[http://uk3.php.net/manual/en/language.oop5.overloading.php](http://uk3.php.net/manual/en/language.oop5.overloading.php)
Clear as mud!`

[up](https://www.php.net/manual/vote-note.php?id=99959&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99959&page=function.empty&vote=down "Vote down!")

8


[**_marko dot crni at gmail dot com_**](https://www.php.net/manual/en/function.empty.php#99959) [¶](https://www.php.net/manual/en/function.empty.php#99959)

**15 years ago**

`Calling non existing object property, empty($object->prop), will trigger __isset(), the same way as isset($object->prop) does, but there is one difference. If __isset() returns TRUE, another call to __get() will be made and actual return value will be result of empty() and result of __get().`

[up](https://www.php.net/manual/vote-note.php?id=123641&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123641&page=function.empty&vote=down "Vote down!")

3


[**_fahimcseiiuc at gmail dot com_**](https://www.php.net/manual/en/function.empty.php#123641) [¶](https://www.php.net/manual/en/function.empty.php#123641)

**6 years ago**

`<?php
    /*"" (an empty string)
      0 (0 as an integer)
      0.0 (0 as a float)
      "0" (0 as a string)
      NULL
      FALSE
      array() (an empty array)*/
$anEmptyString = "";
empty($anEmptyString);
if(empty($anEmptyString) == TRUE){
    echo "TRUE";
} else{
    echo "FALSE";
}
echo "<hr>";         //line break
$anIntegerNumber = 0;
empty($anIntegerNumber);
if(empty($anIntegerNumber) == TRUE){
    echo "TRUE";
} else{
    echo "FALSE";
}
echo "<hr>";         //line break
$aFloatNumber = 0.0;
empty($aFloatNumber);
if(empty($aFloatNumber) == TRUE){
    echo "TRUE";
} else{
    echo "FALSE";
}
echo "<hr>";       //line break
$aZeroValuedString = "0";
empty($aZeroValuedString);
if(empty($aZeroValuedString) == TRUE){
    echo "TRUE";
} else{
    echo "FALSE";
}
echo "<hr>";        //line break
$aNULL = NULL;
empty($aNULL);
if(empty($aNULL) == TRUE){
    echo "TRUE";
} else{
    echo "FALSE";
}
echo "<hr>";        //line break
$aBooleanFALSE = FALSE;
empty($aBooleanFALSE);
if(empty($aBooleanFALSE) == TRUE){
    echo "TRUE";
} else{
    echo "FALSE";
}
echo "<hr>";        //line break
$anEmptyArray = array();
empty($anEmptyArray);
if(empty($anEmptyArray) == TRUE){
    echo "TRUE";
} else{
    echo "FALSE";
}
echo "<hr>";       //line break
?>`

[up](https://www.php.net/manual/vote-note.php?id=92308&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92308&page=function.empty&vote=down "Vote down!")

17


[**_denobasis-bozic et yahoo.com_**](https://www.php.net/manual/en/function.empty.php#92308) [¶](https://www.php.net/manual/en/function.empty.php#92308)

**16 years ago**

`test if all multiarray's are empty
<?php
function is_multiArrayEmpty($multiarray) {
    if(is_array($multiarray) and !empty($multiarray)){
        $tmp = array_shift($multiarray);
            if(!is_multiArrayEmpty($multiarray) or !is_multiArrayEmpty($tmp)){
                return false;
            }
            return true;
    }
    if(empty($multiarray)){
        return true;
    }
    return false;
}
$testCase = array (
0 => '',
1 => "",
2 => null,
3 => array(),
4 => array(array()),
5 => array(array(array(array(array())))),
6 => array(array(), array(), array(), array(), array()),
7 => array(array(array(), array()), array(array(array(array(array(array(), array())))))),
8 => array(null),
9 => 'not empty',
10 => "not empty",
11 => array(array("not empty")),
12 => array(array(),array("not empty"),array(array()))
);
foreach ($testCase as $key => $case ) {
    echo "$key is_multiArrayEmpty= ".is_multiArrayEmpty($case)."<br>";
}
?>
OUTPUT:
========
0 is_multiArrayEmpty= 1
1 is_multiArrayEmpty= 1
2 is_multiArrayEmpty= 1
3 is_multiArrayEmpty= 1
4 is_multiArrayEmpty= 1
5 is_multiArrayEmpty= 1
6 is_multiArrayEmpty= 1
7 is_multiArrayEmpty= 1
8 is_multiArrayEmpty= 1
9 is_multiArrayEmpty=
10 is_multiArrayEmpty=
11 is_multiArrayEmpty=
12 is_multiArrayEmpty=`

[up](https://www.php.net/manual/vote-note.php?id=82942&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82942&page=function.empty&vote=down "Vote down!")

7


[**_Greg Hartwig_**](https://www.php.net/manual/en/function.empty.php#82942) [¶](https://www.php.net/manual/en/function.empty.php#82942)

**17 years ago**

`David from CodeXplorer:
>> The ONLY reason to use empty() is for code readability. It is the same as an IF/ELSE check.
>> So, don't bother using EMPTY in the real world.
This is NOT true.  empty() will not generate warnings if you're testing against an undefined variable as a simple boolean check will.  On production systems, warnings are usually shut off, but they are often active on development systems.
You could test a flag with
<?php if ($flagvar)  ... ?>
but this can generate a warning if $flagvar is not set.
Instead of
<?php if (isset($flagvar) && $flagvar)  ... ?>
you can simply use
<?php if (!empty($flagvar))  ... ?>
for easy readability without warnings.`

[up](https://www.php.net/manual/vote-note.php?id=128069&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128069&page=function.empty&vote=down "Vote down!")

2


[**_mmulej at gmail dot com_**](https://www.php.net/manual/en/function.empty.php#128069) [¶](https://www.php.net/manual/en/function.empty.php#128069)

**2 years ago**

``Tests on
- Win 11
- Intel(R) Core(TM) i7-8750H CPU @ 2.20GHz   2.21 GHz
- 64Gb RAM,
- PHP 8.1.10 (in Tinkerwell)
repeatedly show `empty` > `count` > `=== []`, but the margin is small and not worth the micro-optimizations.
Note: Same results (with `$n = 10000000`) for PHP v7.4.33 using onlinephp(dot)io sandbox tool.
<?php
$test = range(0, 1000);
$test2 = [];
$n = 1000_000_000;
$t1 = microtime(true); for ($x = 0; $x < $n; $x++) if (count($test)) {}
$t2 = microtime(true); for ($x = 0; $x < $n; $x++) if (count($test2)) {}
$t3 = microtime(true); for ($x = 0; $x < $n; $x++) if ($test === []) {}
$t4 = microtime(true); for ($x = 0; $x < $n; $x++) if ($test2 === []) {}
$t5 = microtime(true); for ($x = 0; $x < $n; $x++) if (empty($test)) {}
$t6 = microtime(true); for ($x = 0; $x < $n; $x++) if (empty($test2)) {}
$t7 = microtime(true);
echo "count(\$test):  " . ($t2 - $t1) . " sec\n";
echo "count(\$test2): " . ($t3 - $t2) . " sec\n";
echo "\$test === []:  " . ($t4 - $t3) . " sec\n";
echo "\$test2 === []: " . ($t5 - $t4) . " sec\n";
echo "empty(\$test):  " . ($t6 - $t5) . " sec\n";
echo "empty(\$test2): " . ($t7 - $t6) . " sec\n";
?>
Results:
<?php
count($test):  18.034885168076 sec
count($test2): 17.133869886398 sec
$test === []:  20.059770107269 sec
$test2 === []: 14.204195022583 sec
empty($test):  13.583840847015 sec
empty($test2): 12.971315145493 sec
?>``

[up](https://www.php.net/manual/vote-note.php?id=105722&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105722&page=function.empty&vote=down "Vote down!")

10


[**_chris dot wisefool at gmail dot com_**](https://www.php.net/manual/en/function.empty.php#105722) [¶](https://www.php.net/manual/en/function.empty.php#105722)

**14 years ago**

`Note that checking the existence of a subkey of an array when that subkey does not exist but the parent does and is a string will return false for empty.
i.e.
<?php
$params = array('search'=>'1');
empty($params['search']['filter']); # returns false
?>
This is correct, per the documentation ( [http://php.net/manual/en/language.types.string.php](http://php.net/manual/en/language.types.string.php)); quite a bit down the page is the Warning: "Writing to an out of range offset pads the string with spaces. Non-integer types are converted to integer." ) I didn't receive a warning but perhaps that's correct too...depends on whether the string -> integer conversion is considered "illegal": "Illegal offset type emits E_NOTICE."
(i.e. since $params['search'] is a string, the 'filter' subscript is converted to 0, so the test becomes empty($params['search'][0]), which is obviously false), but it tripped me up enough to mistakenly file a bug report (which I've since closed).`

[up](https://www.php.net/manual/vote-note.php?id=54368&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=54368&page=function.empty&vote=down "Vote down!")

6


[**_jmarbas at hotmail dot com_**](https://www.php.net/manual/en/function.empty.php#54368) [¶](https://www.php.net/manual/en/function.empty.php#54368)

**20 years ago**

`empty($var) will return TRUE if $var is empty (according to the definition of 'empty' above) AND if $var is not set.
I know that the statement in the "Return Values" section of the manual already says this in reverse:
"Returns FALSE if var has a non-empty and non-zero value."
but I was like "Why is this thing returning TRUE for unset variables???"... oh i see now... Its supposed to return TRUE for unset variables!!!
<?php
ini_set('error_reporting',E_ALL);
ini_set('display_errors','1');
empty($var);
?>`

[up](https://www.php.net/manual/vote-note.php?id=119297&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119297&page=function.empty&vote=down "Vote down!")

5


[**_mcfogw at gmail dot com_**](https://www.php.net/manual/en/function.empty.php#119297) [¶](https://www.php.net/manual/en/function.empty.php#119297)

**9 years ago**

``I'm comparing behavior of `!` and `empty()`, find an undocumented behavior here.
just like cast-to-boolean, `empty()` cares about if SimpleXML object is made from emty tags.
`empty(simplexml_load_string('<root />'))` is TRUE
this behavior begins from php 5.1.0~7, in 5.0.x that's FALSE
proof here => [https://3v4l.org/74Tc4](https://3v4l.org/74Tc4)``

[up](https://www.php.net/manual/vote-note.php?id=100807&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100807&page=function.empty&vote=down "Vote down!")

5


[**_e dot klerks at i-bytes dot nl_**](https://www.php.net/manual/en/function.empty.php#100807) [¶](https://www.php.net/manual/en/function.empty.php#100807)

**14 years ago**

`To make an empty function, which only accepts arrays, one can use type-hinting:
<?php
// emptyArray :: [a] -> Bool
function emptyArray(array $xs){
return empty($xs);
}
?>
Type hinting is a good thing to use in your code, because it makes it more easy to reason about your code. Besides that, it automatically documents the code.`

[up](https://www.php.net/manual/vote-note.php?id=100584&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100584&page=function.empty&vote=down "Vote down!")

6


[**_rodolphe dot bodeau at free dot fr_**](https://www.php.net/manual/en/function.empty.php#100584) [¶](https://www.php.net/manual/en/function.empty.php#100584)

**14 years ago**

`Be careful, if "0" (zero as a string), 0 (zero as an integer) and -0 (minus zero as an integer) return true, "-0" (minus zero as a string (yes, I already had some customers that wrote -0 into a form field)) returns false. You need to cast your variable before testing it with the empty() function :
<?php
$var = "-0";
echo empty($var);  // returns false
$var = (int) $var; // casts $var as an integer
echo empty($vat);  // returns true
?>`

[up](https://www.php.net/manual/vote-note.php?id=127028&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127028&page=function.empty&vote=down "Vote down!")

1


[**_Lukas_**](https://www.php.net/manual/en/function.empty.php#127028) [¶](https://www.php.net/manual/en/function.empty.php#127028)

**3 years ago**

`<?php
// Difference of empty() vs. isset()
$testCase = array(
    1 => '',
    2 => ' ',
    3 => null,
    4 => array(),
    5 => false,
    6 => true,
    7 => '0',
    8 => 0,
);
foreach ($testCase as $k => $v) {
    echo "<br> $k => " . strval($v) . " " . (empty($v) ? "is empty" : "is not empty") . " / " . (isset($v) ? "is set" : "is not set");
}
/*
RESULT:
1 =>  is empty / is set
2 =>   is not empty / is set
3 =>  is empty / is not set
4 => Array is empty / is set
5 =>  is empty / is set
6 => 1 is not empty / is set
7 => 0 is empty / is set
8 => 0 is empty / is set
*/`

[up](https://www.php.net/manual/vote-note.php?id=124468&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124468&page=function.empty&vote=down "Vote down!")

1


[**_pm1625637 at gmail dot com_**](https://www.php.net/manual/en/function.empty.php#124468) [¶](https://www.php.net/manual/en/function.empty.php#124468)

**5 years ago**

`Be careful about this  :
<?php
$del = '';
echo empty($del);
?>
Output : 1`

[up](https://www.php.net/manual/vote-note.php?id=78269&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78269&page=function.empty&vote=down "Vote down!")

5


[**_EllisGL_**](https://www.php.net/manual/en/function.empty.php#78269) [¶](https://www.php.net/manual/en/function.empty.php#78269)

**18 years ago**

`Here's what I do for the zero issue issue:
if($val == '' && $val !== 0 && $val !== '0')`

[up](https://www.php.net/manual/vote-note.php?id=77617&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77617&page=function.empty&vote=down "Vote down!")

4


[**_rkulla2 at gmail dot com_**](https://www.php.net/manual/en/function.empty.php#77617) [¶](https://www.php.net/manual/en/function.empty.php#77617)

**18 years ago**

`Since I didn't like how empty() considers 0 and "0" to be empty (which can easily lead to bugs in your code), and since it doesn't deal with whitespace, i created the following function:
<?php
function check_not_empty($s, $include_whitespace = false)
{
    if ($include_whitespace) {
        // make it so strings containing white space are treated as empty too
        $s = trim($s);
    }
    return (isset($s) && strlen($s)); // var is set and not an empty string ''
}
?>
Instead of saying if (!empty($var)) { // it's not empty } you can just say if (check_not_empty($var)) { // it's not empty }.
If you want strings that only contain whitespace (such as tabs or spaces) to be treated as empty then do: check_not_empty($var, 1)
If you want to check if a string IS empty then do: !check_not_empty($var).
So, whenever you want to check if a form field both exists and contains a value just do: if (check_not_empty($_POST['foo'], 1))
no need to do if (isset() && !empty()) anymore =]`

[up](https://www.php.net/manual/vote-note.php?id=107819&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107819&page=function.empty&vote=down "Vote down!")

2


[**_qeremy_**](https://www.php.net/manual/en/function.empty.php#107819) [¶](https://www.php.net/manual/en/function.empty.php#107819)

**13 years ago**

`Simple solution for: "Fatal error: Can't use function return value in write context in ..."
<?php
function _empty($val) { return empty($val); }
?>`

[up](https://www.php.net/manual/vote-note.php?id=121375&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121375&page=function.empty&vote=down "Vote down!")

0


[**_xzero at elite7hackers dot net_**](https://www.php.net/manual/en/function.empty.php#121375) [¶](https://www.php.net/manual/en/function.empty.php#121375)

**8 years ago**

`Note that empty() will return false on null byte. Eg.
<?php
// Save to variable, so it works on older PHP versions
$null_byte = chr(0); // === \0
var_dump(
    empty(null),
    empty($null_byte)
);
/**
* Results:
*
* bool(true)
* bool(false)
*/`

[up](https://www.php.net/manual/vote-note.php?id=118981&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118981&page=function.empty&vote=down "Vote down!")

0


[**_Javier Alfonso_**](https://www.php.net/manual/en/function.empty.php#118981) [¶](https://www.php.net/manual/en/function.empty.php#118981)

**9 years ago**

`If you test an element of an array (like $_POST['key]), it test if the key doesn't exist or if it exist if its value is empty and never emit a warning.
For who don't want to test what happen if passed an array element here is my test and result.
<?php
$a = array();
$b = array('key');
$c = array('key' => false);
$d = array('key' => 'La verdad nos hace libres');
echo (empty($a['key'])?'A empty':'A not empty'), ' - ', (empty($b['key'])?'B empty':'B not empty'), ' - ', (empty($c['key'])?'C empty':'C not empty'), ' - ', (empty($d['key'])?'D empty':'D not empty');
?>
And the result is:
    A empty - B empty - C empty - D not empty`

[up](https://www.php.net/manual/vote-note.php?id=87302&page=function.empty&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87302&page=function.empty&vote=down "Vote down!")

0


[**_thomas at thomasnoest dot nl_**](https://www.php.net/manual/en/function.empty.php#87302) [¶](https://www.php.net/manual/en/function.empty.php#87302)

**16 years ago**

`Note on the selfmade empty function below:
function_exists() returns false on language constructs and empty is a language construct.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.empty&repo=en&redirect=https://www.php.net/manual/en/function.empty.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google