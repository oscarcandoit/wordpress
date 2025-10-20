---
url: https://www.php.net/manual/en/function.is-a.php
scraped_at: 2025-10-20T02:53:49.015Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# is\_a

(PHP 4 >= 4.2.0, PHP 5, PHP 7, PHP 8)

is\_a — Checks whether the object is of a given type or subtype

### Description [¶](https://www.php.net/manual/en/function.is-a.php\#refsect1-function.is-a-description)

**is\_a**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$object_or_class`, [string](https://www.php.net/manual/en/language.types.string.php) `$class`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$allow_string` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Determines if the given `object_or_class` is the
`class` object type,
or has `class` as one of its supertypes.


### Parameters [¶](https://www.php.net/manual/en/function.is-a.php\#refsect1-function.is-a-parameters)

`object_or_class`

A class name or an object instance.


`class`

The class or interface name


`allow_string`

If this parameter set to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**, string class name as `object_or_class`
is not allowed. This also prevents from calling autoloader if the class doesn't exist.


### Return Values [¶](https://www.php.net/manual/en/function.is-a.php\#refsect1-function.is-a-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if `object_or_class` is the
`class` object type,
or has `class` as one of its supertypes, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.


### Examples [¶](https://www.php.net/manual/en/function.is-a.php\#refsect1-function.is-a-examples)

**Example #1 **is\_a()** example**

`<?php
// define a class
class WidgetFactory
{
var $oink = 'moo';
}
// create a new object
$WF = new WidgetFactory();
if (is_a($WF, 'WidgetFactory')) {
echo "yes, \$WF is still a WidgetFactory\n";
}
?>`

**Example #2 Using the _instanceof_ operator**

`<?php
// define a class
class WidgetFactory
{
var $oink = 'moo';
}
// create a new object
$WF = new WidgetFactory();
if ($WF instanceof WidgetFactory) {
    echo 'Yes, $WF is a WidgetFactory';
}
?>`

### See Also [¶](https://www.php.net/manual/en/function.is-a.php\#refsect1-function.is-a-seealso)

- [get\_class()](https://www.php.net/manual/en/function.get-class.php) \- Returns the name of the class of an object
- [get\_parent\_class()](https://www.php.net/manual/en/function.get-parent-class.php) \- Retrieves the parent class name for object or class
- [is\_subclass\_of()](https://www.php.net/manual/en/function.is-subclass-of.php) \- Checks if the object has this class as one of its parents or implements it

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/classobj/functions/is-a.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.is-a%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.is-a&repo=en&redirect=https://www.php.net/manual/en/function.is-a.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=119972&page=function.is-a&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119972&page=function.is-a&vote=down "Vote down!")

73


[**_Ronald Locke_**](https://www.php.net/manual/en/function.is-a.php#119972) [¶](https://www.php.net/manual/en/function.is-a.php#119972)

**9 years ago**

`Please note that you have to fully qualify the class name in the second parameter.
A use statement will not resolve namespace dependencies in that is_a() function.
<?php
namespace foo\bar;
class A {};
class B extends A {};
?>
<?php
namespace har\var;
use foo\bar\A;
$foo = new foo\bar\B();
is_a($foo, 'A'); // returns false;
is_a($foo, 'foo\bar\A'); // returns true;
?>
Just adding that note here because all examples are without namespaces.`

[up](https://www.php.net/manual/vote-note.php?id=105684&page=function.is-a&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105684&page=function.is-a&vote=down "Vote down!")

34


[**_Aron Budinszky_**](https://www.php.net/manual/en/function.is-a.php#105684) [¶](https://www.php.net/manual/en/function.is-a.php#105684)

**14 years ago**

`Be careful! Starting in PHP 5.3.7 the behavior of is_a() has changed slightly: when calling is_a() with a first argument that is not an object, __autoload() is triggered!
In practice, this means that calling is_a('23', 'User'); will trigger __autoload() on "23". Previously, the above statement simply returned 'false'.
More info can be found here:
[https://bugs.php.net/bug.php?id=55475](https://bugs.php.net/bug.php?id=55475)
Whether this change is considered a bug and whether it will be reverted or kept in future versions is yet to be determined, but nevertheless it is how it is, for now...`

[up](https://www.php.net/manual/vote-note.php?id=72363&page=function.is-a&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72363&page=function.is-a&vote=down "Vote down!")

18


[**_p dot scheit at zweipol dot net_**](https://www.php.net/manual/en/function.is-a.php#72363) [¶](https://www.php.net/manual/en/function.is-a.php#72363)

**18 years ago**

`At least in PHP 5.1.6 this works as well with Interfaces.
<?php
interface test {
public function A();
}
class TestImplementor implements test {
public function A () {
    print "A";
}
}
$testImpl = new TestImplementor();
var_dump(is_a($testImpl,'test'));
?>
will return true`

[up](https://www.php.net/manual/vote-note.php?id=57501&page=function.is-a&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=57501&page=function.is-a&vote=down "Vote down!")

11


[**_cesoid at yahoo dot com_**](https://www.php.net/manual/en/function.is-a.php#57501) [¶](https://www.php.net/manual/en/function.is-a.php#57501)

**20 years ago**

`is_a returns TRUE for instances of children of the class.
For example:
class Animal
{}
class Dog extends Animal
{}
$test = new Dog();
In this example is_a($test, "Animal") would evaluate to TRUE as well as is_a($test, "Dog").
This seemed intuitive to me, but did not seem to be documented.`

[up](https://www.php.net/manual/vote-note.php?id=122252&page=function.is-a&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122252&page=function.is-a&vote=down "Vote down!")

3


[**_dkrupyanskiy\[at\]gmail_**](https://www.php.net/manual/en/function.is-a.php#122252) [¶](https://www.php.net/manual/en/function.is-a.php#122252)

**7 years ago**

`Looks like the function signature given in description is wrong. Actually it can take a string  as a first parameter in the case if $allow_string is set to true.
It took some time to find out how the last parameter should be used. Please consider the following example
<?php
class Foo{}
spl_autoload_register(
    function($classname){
        printf('autoload has been triggered for %s%s', $classname, PHP_EOL);
    }
);
var_dump(is_a('UndefinedClassName', Foo::class, true));
?>`

[up](https://www.php.net/manual/vote-note.php?id=127930&page=function.is-a&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127930&page=function.is-a&vote=down "Vote down!")

3


[**_SlimDeluxe_**](https://www.php.net/manual/en/function.is-a.php#127930) [¶](https://www.php.net/manual/en/function.is-a.php#127930)

**2 years ago**

`For anyone wondering, this does not work with traits :(`

[up](https://www.php.net/manual/vote-note.php?id=107181&page=function.is-a&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107181&page=function.is-a&vote=down "Vote down!")

2


[**_eitan at mosenkis dot net_**](https://www.php.net/manual/en/function.is-a.php#107181) [¶](https://www.php.net/manual/en/function.is-a.php#107181)

**13 years ago**

`As of PHP 5.3.9, is_a() seems to return false when passed a string for the first argument. Instead, use is_subclass_of() and, if necessary for your purposes, also check if the two arguments are equal, since is_subclass_of('foo', 'foo') will return false, while is_a('foo', 'foo') used to return true.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.is-a&repo=en&redirect=https://www.php.net/manual/en/function.is-a.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google