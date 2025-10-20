---
url: https://www.php.net/manual/en/language.types.boolean.php
scraped_at: 2025-10-20T02:37:34.157Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Booleans [¶](https://www.php.net/manual/en/language.types.boolean.php\#language.types.boolean)

The [bool](https://www.php.net/manual/en/language.types.boolean.php) type only has two values, and is used to express
a truth value. It can be either **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


### Syntax [¶](https://www.php.net/manual/en/language.types.boolean.php\#language.types.boolean.syntax)

To specify a [bool](https://www.php.net/manual/en/language.types.boolean.php) literal, use the constants **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** or
**`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**. Both are case-insensitive.


`<?php
$foo = True; // assign the value TRUE to $foo
?>`

Run code

Typically, the result of an [operator](https://www.php.net/manual/en/language.operators.php)
which returns a [bool](https://www.php.net/manual/en/language.types.boolean.php) value is passed on to a
[control structure](https://www.php.net/manual/en/language.control-structures.php).


`<?php
$action = "show_version";
$show_separators = true;
// == is an operator which tests
// equality and returns a boolean
if ($action == "show_version") {
    echo "The version is 1.23";
}
// this is not necessary...
if ($show_separators == TRUE) {
    echo "<hr>\n";
}
// ...because this can be used with exactly the same meaning:
if ($show_separators) {
    echo "<hr>\n";
}
?>`

Run code

### Converting to boolean [¶](https://www.php.net/manual/en/language.types.boolean.php\#language.types.boolean.casting)

To explicitly convert a value to [bool](https://www.php.net/manual/en/language.types.boolean.php), use the
`(bool)` cast. Generally this is not necessary because when
a value is used in a logical context it will be automatically interpreted
as a value of type [bool](https://www.php.net/manual/en/language.types.boolean.php). For more information see the
[Type Juggling](https://www.php.net/manual/en/language.types.type-juggling.php) page.


When converting to [bool](https://www.php.net/manual/en/language.types.boolean.php), the following values are considered
**`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**:


- the [boolean](https://www.php.net/manual/en/language.types.boolean.php) **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** itself

- the [integer](https://www.php.net/manual/en/language.types.integer.php) `0` (zero)

- the [float](https://www.php.net/manual/en/language.types.float.php) s
`0.0` and `-0.0` (zero)

- the empty [string](https://www.php.net/manual/en/language.types.string.php) `""`,
and the [string](https://www.php.net/manual/en/language.types.string.php) `"0"`
- an [array](https://www.php.net/manual/en/language.types.array.php) with zero elements

- the unit type [NULL](https://www.php.net/manual/en/language.types.null.php) (including
unset variables)

- Internal objects that overload their casting behaviour to bool.
For example: [SimpleXML](https://www.php.net/manual/en/ref.simplexml.php) objects
created from empty elements without attributes.


Every other value is considered **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**
(including [resource](https://www.php.net/manual/en/language.types.resource.php)
and **`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`**).


**Warning**

`-1` is considered **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, like any other non-zero
(whether negative or positive) number!


**Example #1 Casting to Boolean**

`<?php
var_dump((bool) "");        // bool(false)
var_dump((bool) "0");       // bool(false)
var_dump((bool) 1);         // bool(true)
var_dump((bool) -2);        // bool(true)
var_dump((bool) "foo");     // bool(true)
var_dump((bool) 2.3e5);     // bool(true)
var_dump((bool) array(12)); // bool(true)
var_dump((bool) array());   // bool(false)
var_dump((bool) "false");   // bool(true)
?>`

Run code

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/boolean.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.boolean%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.boolean&repo=en&redirect=https://www.php.net/manual/en/language.types.boolean.php)

### User Contributed Notes 12 notes

[up](https://www.php.net/manual/vote-note.php?id=112190&page=language.types.boolean&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112190&page=language.types.boolean&vote=down "Vote down!")

1002


[**_Fred Koschara_**](https://www.php.net/manual/en/language.types.boolean.php#112190) [¶](https://www.php.net/manual/en/language.types.boolean.php#112190)

**12 years ago**

`Ah, yes, booleans - bit values that are either set (TRUE) or not set (FALSE).  Now that we have 64 bit compilers using an int variable for booleans, there is *one* value which is FALSE (zero) and 2**64-1 values that are TRUE (everything else).  It appears there's a lot more truth in this universe, but false can trump anything that's true...
PHP's handling of strings as booleans is *almost* correct - an empty string is FALSE, and a non-empty string is TRUE - with one exception:  A string containing a single zero is considered FALSE.  Why?  If *any* non-empty strings are going to be considered FALSE, why *only* a single zero?  Why not "FALSE" (preferably case insensitive), or "0.0" (with how many decimal places), or "NO" (again, case insensitive), or ... ?
The *correct* design would have been that *any* non-empty string is TRUE - period, end of story.  Instead, there's another GOTCHA for the less-than-completely-experienced programmer to watch out for, and fixing the language's design error at this late date would undoubtedly break so many things that the correction is completely out of the question.
Speaking of GOTCHAs, consider this code sequence:
<?php
$x=TRUE;
$y=FALSE;
$z=$y OR $x;
?>
Is $z TRUE or FALSE?
In this case, $z will be FALSE because the above code is equivalent to <?php ($z=$y) OR $x ?> rather than <?php $z=($y OR $x) ?> as might be expected - because the OR operator has lower precedence than assignment operators.
On the other hand, after this code sequence:
<?php
$x=TRUE;
$y=FALSE;
$z=$y || $x;
?>
$z will be TRUE, as expected, because the || operator has higher precedence than assignment:  The code is equivalent to $z=($y OR $x).
This is why you should NEVER use the OR operator without explicit parentheses around the expression where it is being used.`

[up](https://www.php.net/manual/vote-note.php?id=121143&page=language.types.boolean&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121143&page=language.types.boolean&vote=down "Vote down!")

180


[**_Mark Simon_**](https://www.php.net/manual/en/language.types.boolean.php#121143) [¶](https://www.php.net/manual/en/language.types.boolean.php#121143)

**8 years ago**

`Note for JavaScript developers:
In PHP, an empty array evaluates to false, while in JavaScript an empty array evaluates to true.
In PHP, you can test an empty array as <?php if(!$stuff) …; ?> which won’t work in JavaScript where you need to test the array length.
This is because in JavaScript, an array is an object, and, while it may not have any elements, it is still regarded as something.
Just a trap for young players who routinely work in both langauges.`

[up](https://www.php.net/manual/vote-note.php?id=119799&page=language.types.boolean&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119799&page=language.types.boolean&vote=down "Vote down!")

98


[**_goran77 at fastmail dot fm_**](https://www.php.net/manual/en/language.types.boolean.php#119799) [¶](https://www.php.net/manual/en/language.types.boolean.php#119799)

**9 years ago**

`Just something that will probably save time for many new developers: beware of interpreting FALSE and TRUE as integers.
For example, a small function for deleting elements of an array may give unexpected results if you are not fully aware of what happens:
<?php
function remove_element($element, $array)
{
//array_search returns index of element, and FALSE if nothing is found
$index = array_search($element, $array);
unset ($array[$index]);
return $array;
}
// this will remove element 'A'
$array = ['A', 'B', 'C'];
$array = remove_element('A', $array);
//but any non-existent element will also remove 'A'!
$array = ['A', 'B', 'C'];
$array = remove_element('X', $array);
?>
The problem here is, although array_search returns boolean false when it doesn't find specific element, it is interpreted as zero when used as array index.
So you have to explicitly check for FALSE, otherwise you'll probably loose some elements:
<?php
//correct
function remove_element($element, $array)
{
$index = array_search($element, $array);
if ($index !== FALSE)
{
       unset ($array[$index]);
}
return $array;
}`

[up](https://www.php.net/manual/vote-note.php?id=74827&page=language.types.boolean&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74827&page=language.types.boolean&vote=down "Vote down!")

56


[**_terminatorul at gmail dot com_**](https://www.php.net/manual/en/language.types.boolean.php#74827) [¶](https://www.php.net/manual/en/language.types.boolean.php#74827)

**18 years ago**

`Beware that "0.00" converts to boolean TRUE !
You may get such a string from your database, if you have columns of type DECIMAL or CURRENCY. In such cases you have to explicitly check if the value is != 0 or to explicitly convert the value to int also, not only to boolean.`

[up](https://www.php.net/manual/vote-note.php?id=121144&page=language.types.boolean&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121144&page=language.types.boolean&vote=down "Vote down!")

23


[**_Mark Simon_**](https://www.php.net/manual/en/language.types.boolean.php#121144) [¶](https://www.php.net/manual/en/language.types.boolean.php#121144)

**8 years ago**

`Note on the OR operator.
A previous comment notes the trap you can fall into with this operator. This is about its usefulness.
Both OR and || are short-circuited operators, which means they will stop evaluating once they reach a TRUE value. By design, OR is evaluated after assignment (while || is evaluated before assignment).
This has the benefit of allowing some simple constructions such as:
<?php
    $stuff=getStuff() or die('oops');
    $thing=something() or $thing=whatever();
?>
The first example, often seen in PERL, could have been written as <?php if(!$stuff=getStuff()) die('oops'); ?> but reads a little more naturally. I have often used it in situations where null or false indicate failure.
The second allows for an alternative value if a falsy one is regarded as insufficient. The following example
<?php
    $page=@$_GET['page'] or $page=@$_COOKIE['page'] or $page=1;
?>
is a simple way sequencing alternative values. (Note the usual warnings about using the @ operator or accepting unfiltered input …)
All this presupposes that 0 is also an unacceptable value in the situation.`

[up](https://www.php.net/manual/vote-note.php?id=80433&page=language.types.boolean&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80433&page=language.types.boolean&vote=down "Vote down!")

45


[**_Steve_**](https://www.php.net/manual/en/language.types.boolean.php#80433) [¶](https://www.php.net/manual/en/language.types.boolean.php#80433)

**17 years ago**

`PHP does not break any rules with the values of true and false.  The value false is not a constant for the number 0, it is a boolean value that indicates false.  The value true is also not a constant for 1, it is a special boolean value that indicates true.  It just happens to cast to integer 1 when you print it or use it in an expression, but it's not the same as a constant for the integer value 1 and you shouldn't use it as one.  Notice what it says at the top of the page:
A boolean expresses a truth value.
It does not say "a boolean expresses a 0 or 1".
It's true that symbolic constants are specifically designed to always and only reference their constant value.  But booleans are not symbolic constants, they are values.  If you're trying to add 2 boolean values you might have other problems in your application.`

[up](https://www.php.net/manual/vote-note.php?id=126107&page=language.types.boolean&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126107&page=language.types.boolean&vote=down "Vote down!")

8


[**_asma dot gi dot 14 at gmail dot com_**](https://www.php.net/manual/en/language.types.boolean.php#126107) [¶](https://www.php.net/manual/en/language.types.boolean.php#126107)

**4 years ago**

`when using echo false; or print false; the display will be empty but when using echo 0; or print 0; the display will be 0.`

[up](https://www.php.net/manual/vote-note.php?id=80648&page=language.types.boolean&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80648&page=language.types.boolean&vote=down "Vote down!")

36


[**_Wackzingo_**](https://www.php.net/manual/en/language.types.boolean.php#80648) [¶](https://www.php.net/manual/en/language.types.boolean.php#80648)

**17 years ago**

`It is correct that TRUE or FALSE should not be used as constants for the numbers 0 and 1. But there may be times when it might be helpful to see the value of the Boolean as a 1 or 0. Here's how to do it.
<?php
$var1 = TRUE;
$var2 = FALSE;
echo $var1; // Will display the number 1
echo $var2; //Will display nothing
/* To get it to display the number 0 for
a false value you have to typecast it: */
echo (int)$var2; //This will display the number 0 for false.
?>`

[up](https://www.php.net/manual/vote-note.php?id=126106&page=language.types.boolean&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126106&page=language.types.boolean&vote=down "Vote down!")

6


[**_asma dot gi dot 14 at gmail dot com_**](https://www.php.net/manual/en/language.types.boolean.php#126106) [¶](https://www.php.net/manual/en/language.types.boolean.php#126106)

**4 years ago**

`Please keep in mind that the result of  0 == 'whatever'  is true in PHP Version 7 and false in PHP version 8.`

[up](https://www.php.net/manual/vote-note.php?id=78099&page=language.types.boolean&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78099&page=language.types.boolean&vote=down "Vote down!")

26


[**_artktec at gmail dot com_**](https://www.php.net/manual/en/language.types.boolean.php#78099) [¶](https://www.php.net/manual/en/language.types.boolean.php#78099)

**18 years ago**

`Note you can also use the '!' to convert a number to a boolean, as if it was an explicit (bool) cast then NOT.
So you can do something like:
<?php
$t = !0; // This will === true;
$f = !1; // This will === false;
?>
And non-integers are casted as if to bool, then NOT.
Example:
<?php
$a = !array();      // This will === true;
$a = !array('a');   // This will === false;
$s = !"";           // This will === true;
$s = !"hello";      // This will === false;
?>
To cast as if using a (bool) you can NOT the NOT with "!!" (double '!'), then you are casting to the correct (bool).
Example:
<?php
$a = !!array();   // This will === false; (as expected)
/*
This can be a substitute for count($array) > 0 or !(empty($array)) to check to see if an array is empty or not  (you would use: !!$array).
*/
$status = (!!$array ? 'complete' : 'incomplete');
$s = !!"testing"; // This will === true; (as expected)
/*
Note: normal casting rules apply so a !!"0" would evaluate to an === false
*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=129268&page=language.types.boolean&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129268&page=language.types.boolean&vote=down "Vote down!")

0


[**_Anonymous_**](https://www.php.net/manual/en/language.types.boolean.php#129268) [¶](https://www.php.net/manual/en/language.types.boolean.php#129268)

**1 year ago**

`Note the imperfectness of php and booleans when dealing with SQL strings. A 'boolean' included in a string to send to MySQL for example, evaluates to a n empty string with the result that:
$TF  = false;
$SQL = "INSERT INTO ... (...., booleanTF) VALUES (...., $TF)"
will generate a mysql error "You have an error ... near '(....,)"`

[up](https://www.php.net/manual/vote-note.php?id=118181&page=language.types.boolean&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118181&page=language.types.boolean&vote=down "Vote down!")

1


[**_marklgr_**](https://www.php.net/manual/en/language.types.boolean.php#118181) [¶](https://www.php.net/manual/en/language.types.boolean.php#118181)

**9 years ago**

`For those wondering why the string "0" is falsy, consider that a good deal of input data is actually string-typed, even when it is semantically numeral.
PHP often tries to autoconvert these strings to numeral, as the programmer certainly intended (try 'echo "2"+3'). Consequently, PHP designers decided to treat 0 and "0" similarly, ie. falsy, for consistency and to avoid bugs where the programmer believes he got a true numeral that would happen to be truthy when zero.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.boolean&repo=en&redirect=https://www.php.net/manual/en/language.types.boolean.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google