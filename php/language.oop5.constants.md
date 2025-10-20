---
url: https://www.php.net/manual/en/language.oop5.constants.php
scraped_at: 2025-10-20T02:41:41.897Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Class Constants [¶](https://www.php.net/manual/en/language.oop5.constants.php\#language.oop5.constants)

It is possible to define [constants](https://www.php.net/manual/en/language.constants.php)
on a per-class basis remaining the same and unchangeable.
The default visibility of class constants is `public`.


> **Note**:
>
>
> Class constants can be redefined by a child class.
> As of PHP 8.1.0, class constants cannot be redefined by a child class
> if it is defined as [final](https://www.php.net/manual/en/language.oop5.final.php).

It's also possible for interfaces to have constants. Look
at the [interface documentation](https://www.php.net/manual/en/language.oop5.interfaces.php)
for examples.


It's possible to reference the class using a variable.
The variable's value can not be a keyword (e.g. `self`,
`parent` and `static`).


Note that class constants are allocated once per class, and not for each
class instance.


As of PHP 8.3.0, class constants can have a scalar type such as `bool`,
`int`, `float`, `string`, or even
`array`. When using `array`, the contents can only be
other scalar types.


**Example #1 Defining and using a constant**

`<?php
class MyClass
{
    const CONSTANT = 'constant value';
    function showConstant() {
        echo  self::CONSTANT . "\n";
    }
}
echo MyClass::CONSTANT . "\n";
$classname = "MyClass";
echo $classname::CONSTANT . "\n";
$class = new MyClass();
$class->showConstant();
echo $class::CONSTANT."\n";
?>`

Run code

The special **`::class`** constant allows
for fully qualified class name resolution at compile time,
this is useful for namespaced classes:


**Example #2 Namespaced ::class example**

`<?php
namespace foo {
    class bar {
    }
    echo bar::class; // foo\bar
}
?>`

Run code

**Example #3 Class constant expression example**

`<?php
const ONE = 1;
class foo {
    const TWO = ONE * 2;
    const THREE = ONE + self::TWO;
    const SENTENCE = 'The value of THREE is '.self::THREE;
}
?>`

Run code

**Example #4 Class constant visibility modifiers, as of PHP 7.1.0**

`<?php
class Foo {
    public const BAR = 'bar';
    private const BAZ = 'baz';
}
echo Foo::BAR, PHP_EOL;
echo Foo::BAZ, PHP_EOL;
?>`

Run code

Output of the above example in PHP 7.1:

```
bar

Fatal error: Uncaught Error: Cannot access private const Foo::BAZ in …

```

> **Note**:
>
>
> As of PHP 7.1.0 visibility modifiers are allowed for class constants.

**Example #5 Class constant visibility variance check, as of PHP 8.3.0**

`<?php
interface MyInterface
{
    public const VALUE = 42;
}
class MyClass implements MyInterface
{
    protected const VALUE = 42;
}
?>`

Run code

Output of the above example in PHP 8.3:

```
Fatal error: Access level to MyClass::VALUE must be public (as in interface MyInterface) …

```

> **Note**:
>
> As of PHP 8.3.0 visibility variance is checked more strictly.
> Prior to this version, the visibility of a class constant could be different
> from the visibility of the constant in the implemented interface.

**Example #6 Fetch class constant syntax, as of PHP 8.3.0**

`<?php
class Foo {
    public const BAR = 'bar';
    private const BAZ = 'baz';
}
$name = 'BAR';
echo Foo::{$name}, PHP_EOL; // bar
?>`

Run code

> **Note**:
>
>
> As of PHP 8.3.0, class constants can be fetched dynamically using a
> variable.

**Example #7 Assigning types to class constants, as of PHP 8.3.0**

`<?php
class MyClass {
    public const bool MY_BOOL = true;
    public const int MY_INT = 1;
    public const float MY_FLOAT = 1.01;
    public const string MY_STRING = 'one';
    public const array MY_ARRAY = [self::MY_BOOL, self::MY_INT, self::MY_FLOAT, self::MY_STRING];
}
var_dump(MyClass::MY_BOOL);
var_dump(MyClass::MY_INT);
var_dump(MyClass::MY_FLOAT);
var_dump(MyClass::MY_STRING);
var_dump(MyClass::MY_ARRAY);
?>`

Run code

Output of the above example in PHP 8.3:

```
bool(true)
int(1)
float(1.01)
string(3) "one"
array(4) {
  [0]=>
  bool(true)
  [1]=>
  int(1)
  [2]=>
  float(1.01)
  [3]=>
  string(3) "one"
}

```

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/oop5/constants.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.oop5.constants%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.oop5.constants&repo=en&redirect=https://www.php.net/manual/en/language.oop5.constants.php)

### User Contributed Notes 13 notes

[up](https://www.php.net/manual/vote-note.php?id=104260&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104260&page=language.oop5.constants&vote=down "Vote down!")

210


[**_tmp dot 4 dot longoria at gmail dot com_**](https://www.php.net/manual/en/language.oop5.constants.php#104260) [¶](https://www.php.net/manual/en/language.oop5.constants.php#104260)

**14 years ago**

``it's possible to declare constant in base class, and override it in child, and access to correct value of the const from the static method is possible by 'get_called_class' method:
<?php
abstract class dbObject
{
    const TABLE_NAME='undefined';

    public static function GetAll()
    {
        $c = get_called_class();
        return "SELECT * FROM `".$c::TABLE_NAME."`";
    }
}
class dbPerson extends dbObject
{
    const TABLE_NAME='persons';
}
class dbAdmin extends dbPerson
{
    const TABLE_NAME='admins';
}
echo dbPerson::GetAll()."<br>";//output: "SELECT * FROM `persons`"
echo dbAdmin::GetAll()."<br>";//output: "SELECT * FROM `admins`"
?>``

[up](https://www.php.net/manual/vote-note.php?id=100142&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100142&page=language.oop5.constants&vote=down "Vote down!")

152


[**_anonymous_**](https://www.php.net/manual/en/language.oop5.constants.php#100142) [¶](https://www.php.net/manual/en/language.oop5.constants.php#100142)

**15 years ago**

`Most people miss the point in declaring constants and confuse then things by trying to declare things like functions or arrays as constants. What happens next is to try things that are more complicated then necessary and sometimes lead to bad coding practices. Let me explain...
A constant is a name for a value (but it's NOT a variable), that usually will be replaced in the code while it gets COMPILED and NOT at runtime.
So returned values from functions can't be used, because they will return a value only at runtime.
Arrays can't be used, because they are data structures that exist at runtime.
One main purpose of declaring a constant is usually using a value in your code, that you can replace easily in one place without looking for all the occurences. Another is, to avoid mistakes.
Think about some examples written by some before me:
1. const MY_ARR = "return array(\"A\", \"B\", \"C\", \"D\");";
It was said, this would declare an array that can be used with eval. WRONG! This is just a string as constant, NOT an array. Does it make sense if it would be possible to declare an array as constant? Probably not. Instead declare the values of the array as constants and make an array variable.
2. const magic_quotes = (bool)get_magic_quotes_gpc();
This can't work, of course. And it doesn't make sense either. The function already returns the value, there is no purpose in declaring a constant for the same thing.
3. Someone spoke about "dynamic" assignments to constants. What? There are no dynamic assignments to constants, runtime assignments work _only_ with variables. Let's take the proposed example:
<?php
/**
* Constants that deal only with the database
*/
class DbConstant extends aClassConstant {
    protected $host = 'localhost';
    protected $user = 'user';
    protected $password = 'pass';
    protected $database = 'db';
    protected $time;
    function __construct() {
        $this->time = time() + 1; // dynamic assignment
    }
}
?>
Those aren't constants, those are properties of the class. Something like "this->time = time()" would even totally defy the purpose of a constant. Constants are supposed to be just that, constant values, on every execution. They are not supposed to change every time a script runs or a class is instantiated.
Conclusion: Don't try to reinvent constants as variables. If constants don't work, just use variables. Then you don't need to reinvent methods to achieve things for what is already there.`

[up](https://www.php.net/manual/vote-note.php?id=116109&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116109&page=language.oop5.constants&vote=down "Vote down!")

143


[**_kuzawinski dot marcin at gmail dot com_**](https://www.php.net/manual/en/language.oop5.constants.php#116109) [¶](https://www.php.net/manual/en/language.oop5.constants.php#116109)

**10 years ago**

`As of PHP 5.6 you can finally define constant using math expressions, like this one:
<?php
class MyTimer {
    const SEC_PER_DAY = 60 * 60 * 24;
}
?>
Me happy :)`

[up](https://www.php.net/manual/vote-note.php?id=114143&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114143&page=language.oop5.constants&vote=down "Vote down!")

117


[**_delete dot this dot and dot dots dot gt at kani dot hu_**](https://www.php.net/manual/en/language.oop5.constants.php#114143) [¶](https://www.php.net/manual/en/language.oop5.constants.php#114143)

**11 years ago**

`I think it's useful if we draw some attention to late static binding here:
<?php
class A {
    const MY_CONST = false;
    public function my_const_self() {
        return self::MY_CONST;
    }
    public function my_const_static() {
        return static::MY_CONST;
    }
}
class B extends A {
const MY_CONST = true;
}
$b = new B();
echo $b->my_const_self ? 'yes' : 'no'; // output: no
echo $b->my_const_static ? 'yes' : 'no'; // output: yes
?>`

[up](https://www.php.net/manual/vote-note.php?id=114599&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114599&page=language.oop5.constants&vote=down "Vote down!")

94


[**_Xiong Chiamiov_**](https://www.php.net/manual/en/language.oop5.constants.php#114599) [¶](https://www.php.net/manual/en/language.oop5.constants.php#114599)

**11 years ago**

`const can also be used directly in namespaces, a feature never explicitly stated in the documentation.
<?php
# foo.php
namespace Foo;
const BAR = 1;
?>
<?php
# bar.php
require 'foo.php';
var_dump(Foo\BAR); // => int(1)
?>`

[up](https://www.php.net/manual/vote-note.php?id=120083&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120083&page=language.oop5.constants&vote=down "Vote down!")

51


[**_jimmmy dot chief at gmail dot com_**](https://www.php.net/manual/en/language.oop5.constants.php#120083) [¶](https://www.php.net/manual/en/language.oop5.constants.php#120083)

**8 years ago**

`Hi, i would like to point out difference between self::CONST and $this::CONST with extended class.
Let us have class a:
<?php
class a {
    const CONST_INT = 10;

    public function getSelf(){
        return self::CONST_INT;
    }

    public function getThis(){
        return $this::CONST_INT;
    }
}
?>
And class b (which extends a)
<?php
class b extends a {
    const CONST_INT = 20;

    public function getSelf(){
        return parent::getSelf();
    }

    public function getThis(){
        return parent::getThis();
    }
}
?>
Both classes have same named constant CONST_INT.
When child call method in parent class, there is different output between self and $this usage.
<?php
$b = new b();
print_r($b->getSelf());     //10
print_r($b->getThis());     //20
?>`

[up](https://www.php.net/manual/vote-note.php?id=128452&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128452&page=language.oop5.constants&vote=down "Vote down!")

5


[**_powtac at gmx dot de_**](https://www.php.net/manual/en/language.oop5.constants.php#128452) [¶](https://www.php.net/manual/en/language.oop5.constants.php#128452)

**2 years ago**

`Since it it is not mentioned in the description the following types can be set as a class constant: string, array, int, bool and probably float. But not objects.
<?php
class Test {
    const arr  = array();
    const string = 'string';
    const int = 99;
    const bool = true;
}
var_dump(
    (new Test())::arr,
    (new Test())::string,
    (new Test())::int,
    (new Test())::bool
);
/* ouput for PHP 7.0.0+:
array(0) {
}
string(6) "string"
int(99)
bool(true)`

[up](https://www.php.net/manual/vote-note.php?id=129926&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129926&page=language.oop5.constants&vote=down "Vote down!")

2


[**_AamirSohailKmAs at gmail dot com_**](https://www.php.net/manual/en/language.oop5.constants.php#129926) [¶](https://www.php.net/manual/en/language.oop5.constants.php#129926)

**9 months ago**

`Note
as of PHP 8.3, it is possible to define Typed class constants.
RFC: [https://wiki.php.net/rfc/typed\_class\_constants](https://wiki.php.net/rfc/typed_class_constants)
<?php
class Example {
    public const string NAME = "Aamir";
    public const int  MAX    = 100;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=118998&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118998&page=language.oop5.constants&vote=down "Vote down!")

31


[**_nepomuk at nepda dot de_**](https://www.php.net/manual/en/language.oop5.constants.php#118998) [¶](https://www.php.net/manual/en/language.oop5.constants.php#118998)

**9 years ago**

`[Editor's note: that is already possible as of PHP 5.6.0.]
Note, as of PHP7 it is possible to define class constants with an array.
<?php
class MyClass
{
    const ABC = array('A', 'B', 'C');
    const A = '1';
    const B = '2';
    const C = '3';
    const NUMBERS = array(
        self::A,
        self::B,
        self::C,
    );
}
var_dump(MyClass::ABC);
var_dump(MyClass::NUMBERS);
// Result:
/*
array(3) {
    [0]=>
string(1) "A"
    [1]=>
string(1) "B"
    [2]=>
string(1) "C"
}
array(3) {
    [0]=>
string(1) "1"
    [1]=>
string(1) "2"
    [2]=>
string(1) "3"
}
*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=123039&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123039&page=language.oop5.constants&vote=down "Vote down!")

3


[**_David Spector_**](https://www.php.net/manual/en/language.oop5.constants.php#123039) [¶](https://www.php.net/manual/en/language.oop5.constants.php#123039)

**7 years ago**

`The usual comma-separated syntax can be used to declare several constants:
class STATE
    {
    const INIT=0, NAME_SEEN=1, ADDR_SEEN=2;
    }
This shows the declaration of a set of enumeration literals suitable for use in a finite state machine loop. Reference such an enum by using syntax such as "STATE::INIT". Its actual type in this case will be integer.`

[up](https://www.php.net/manual/vote-note.php?id=85703&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85703&page=language.oop5.constants&vote=down "Vote down!")

9


[**_wbcarts at juno dot com_**](https://www.php.net/manual/en/language.oop5.constants.php#85703) [¶](https://www.php.net/manual/en/language.oop5.constants.php#85703)

**17 years ago**

`Use CONST to set UPPER and LOWER LIMITS
If you have code that accepts user input or you just need to make sure input is acceptable, you can use constants to set upper and lower limits. Note: a static function that enforces your limits is highly recommended... sniff the clamp() function below for a taste.
<?php
class Dimension
{
const MIN = 0, MAX = 800;
public $width, $height;
public function __construct($w = 0, $h = 0){
    $this->width  = self::clamp($w);
    $this->height = self::clamp($h);
}
public function __toString(){
    return "Dimension [width=$this->width, height=$this->height]";
}
protected static function clamp($value){
    if($value < self::MIN) $value = self::MIN;
    if($value > self::MAX) $value = self::MAX;
    return $value;
}
}
echo (new Dimension()) . '<br>';
echo (new Dimension(1500, 97)) . '<br>';
echo (new Dimension(14, -20)) . '<br>';
echo (new Dimension(240, 80)) . '<br>';
?>
- - - - - - - -
Dimension [width=0, height=0] - default size
Dimension [width=800, height=97] - width has been clamped to MAX
Dimension [width=14, height=0] - height has been clamped to MIN
Dimension [width=240, height=80] - width and height unchanged
- - - - - - - -
Setting upper and lower limits on your classes also help your objects make sense. For example, it is not possible for the width or height of a Dimension to be negative. It is up to you to keep phoney input from corrupting your objects, and to avoid potential errors and exceptions in other parts of your code.`

[up](https://www.php.net/manual/vote-note.php?id=121613&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121613&page=language.oop5.constants&vote=down "Vote down!")

3


[**_Nimja_**](https://www.php.net/manual/en/language.oop5.constants.php#121613) [¶](https://www.php.net/manual/en/language.oop5.constants.php#121613)

**8 years ago**

`Note that this magic constant DOES NOT load classes. And in fact can work on classes that do not exist.
This means it does not mess with auto-loading.
<?php
    $className = \Foo\Bar::class;
    var_dump($className);
    var_dump(class_exists($className, false));
?>
Will output:
    string(7) "Foo\Bar"
    bool(false)`

[up](https://www.php.net/manual/vote-note.php?id=130425&page=language.oop5.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130425&page=language.oop5.constants&vote=down "Vote down!")

0


[**_wbeaumo1 at gmail dot com_**](https://www.php.net/manual/en/language.oop5.constants.php#130425) [¶](https://www.php.net/manual/en/language.oop5.constants.php#130425)

**2 months ago**

`The ::class magic constant can be used on any bare text that follows the syntax requirements of a valid symbol and the symbol will be expanded appropriately regardless of whether it resolves to a class or even if it exists at all. This means you can use it to expand the names of namespaced functions and constants (but not class constants or methods) in addition to classes:
<?php
use MyNamespace\MyConstants;
use MyNamespace\MyFunctions;
function_exists(MyFunctions\my_func::class); // The argument expands to "MyNamespace\MyFunctions\my_func"
defined(MyConstants\MY_CONSTANT::class); // The argument expands to "MyNamespace\MyConstants\MY_CONSTANT" ?>
And of course it works on symbols in the global namespace:
<?php
namespace MyNamespace;
function_exists(\function_exists::class); // true
defined(\PHP_VERSION::class); // true`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.oop5.constants&repo=en&redirect=https://www.php.net/manual/en/language.oop5.constants.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google