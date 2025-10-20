---
url: https://www.php.net/manual/en/language.operators.type.php
scraped_at: 2025-10-20T02:37:09.631Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Type Operators [¶](https://www.php.net/manual/en/language.operators.type.php\#language.operators.type)

`instanceof` is used to determine whether a PHP variable
is an instantiated object of a certain
[class](https://www.php.net/manual/en/language.oop5.basic.php#language.oop5.basic.class):


**Example #1 Using `instanceof` with classes**

`<?php
class MyClass
{
}
class NotMyClass
{
}
$a = new MyClass;
var_dump($a instanceof MyClass);
var_dump($a instanceof NotMyClass);
?>`

Run code

The above example will output:

```
bool(true)
bool(false)

```

`instanceof` can also be used to determine whether a variable
is an instantiated object of a class that inherits from a parent class:


**Example #2 Using `instanceof` with inherited classes**

`<?php
class ParentClass
{
}
class MyClass extends ParentClass
{
}
$a = new MyClass;
var_dump($a instanceof MyClass);
var_dump($a instanceof ParentClass);
?>`

Run code

The above example will output:

```
bool(true)
bool(true)

```

To check if an object is _not_ an instanceof a class, the
[logical `not`\\
operator](https://www.php.net/manual/en/language.operators.logical.php) can be used.


**Example #3 Using `instanceof` to check if object is _not_ an**
**instanceof a class**

`<?php
class MyClass
{
}
$a = new MyClass;
var_dump(!($a instanceof stdClass));
?>`

Run code

The above example will output:

```
bool(true)

```

Lastly, `instanceof` can also be used to determine whether
a variable is an instantiated object of a class that implements an
[interface](https://www.php.net/manual/en/language.oop5.interfaces.php):


**Example #4 Using `instanceof` with interfaces**

`<?php
interface MyInterface
{
}
class MyClass implements MyInterface
{
}
$a = new MyClass;
var_dump($a instanceof MyClass);
var_dump($a instanceof MyInterface);
?>`

Run code

The above example will output:

```
bool(true)
bool(true)

```

Although `instanceof` is usually used with a literal classname,
it can also be used with another object or a string variable:


**Example #5 Using `instanceof` with other variables**

`<?php
interface MyInterface
{
}
class MyClass implements MyInterface
{
}
$a = new MyClass;
$b = new MyClass;
$c = 'MyClass';
$d = 'NotMyClass';
var_dump($a instanceof $b); // $b is an object of class MyClass
var_dump($a instanceof $c); // $c is a string 'MyClass'
var_dump($a instanceof $d); // $d is a string 'NotMyClass'
?>`

Run code

The above example will output:

```
bool(true)
bool(true)
bool(false)

```

instanceof does not throw any error if the variable being tested is not
an object, it simply returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**. Constants, however, were not allowed
prior to PHP 7.3.0.


**Example #6 Using `instanceof` to test other variables**

`<?php
$a = 1;
$b = NULL;
$c = fopen('/tmp/', 'r');
var_dump($a instanceof stdClass); // $a is an integer
var_dump($b instanceof stdClass); // $b is NULL
var_dump($c instanceof stdClass); // $c is a resource
var_dump(FALSE instanceof stdClass);
?>`

Run code

The above example will output:

```
bool(false)
bool(false)
bool(false)
PHP Fatal error:  instanceof expects an object instance, constant given

```

As of PHP 7.3.0, constants are allowed on the left-hand-side of the
`instanceof` operator.


**Example #7 Using `instanceof` to test constants**

`<?php
var_dump(FALSE instanceof stdClass);
?>`

Run code

Output of the above example in PHP 7.3:

```
bool(false)

```

As of PHP 8.0.0, `instanceof` can now be used with arbitrary expressions.
The expression must be wrapped in parentheses and produce a [string](https://www.php.net/manual/en/language.types.string.php).



**Example #8 Using `instanceof` with an arbitrary expression**

`<?php
class ClassA extends \stdClass {}
class ClassB extends \stdClass {}
class ClassC extends ClassB {}
class ClassD extends ClassA {}
function getSomeClass(): string
{
    return ClassA::class;
}
var_dump(new ClassA instanceof ('std' . 'Class'));
var_dump(new ClassB instanceof ('Class' . 'B'));
var_dump(new ClassC instanceof ('Class' . 'A'));
var_dump(new ClassD instanceof (getSomeClass()));
?>`

Run code

Output of the above example in PHP 8:

```
bool(true)
bool(true)
bool(false)
bool(true)

```

The `instanceof` operator has a functional variant
with the [is\_a()](https://www.php.net/manual/en/function.is-a.php) function.


### See Also

- [get\_class()](https://www.php.net/manual/en/function.get-class.php)
- [is\_a()](https://www.php.net/manual/en/function.is-a.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/operators/type.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.operators.type%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.type&repo=en&redirect=https://www.php.net/manual/en/language.operators.type.php)

### User Contributed Notes 16 notes

[up](https://www.php.net/manual/vote-note.php?id=76352&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76352&page=language.operators.type&vote=down "Vote down!")

140


[**_jphaas at gmail dot com_**](https://www.php.net/manual/en/language.operators.type.php#76352) [¶](https://www.php.net/manual/en/language.operators.type.php#76352)

**18 years ago**

`Posting this so the word typeof appears on this page, so that this page will show up when you google 'php typeof'.  ...yeah, former Java user.`

[up](https://www.php.net/manual/vote-note.php?id=111527&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111527&page=language.operators.type&vote=down "Vote down!")

64


[**_knarlin at yahoo dot com dot au_**](https://www.php.net/manual/en/language.operators.type.php#111527) [¶](https://www.php.net/manual/en/language.operators.type.php#111527)

**12 years ago**

`Checking an object is not an instance of a class, example #3 uses extraneous parentheses.
<?php
var_dump(!($a instanceof stdClass));
?>
Because instanceof has higher operator precedence than ! you can just do
<?php
var_dump( ! $a instanceof stdClass );
?>`

[up](https://www.php.net/manual/vote-note.php?id=106882&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106882&page=language.operators.type&vote=down "Vote down!")

50


[**_Sudarshan Wadkar_**](https://www.php.net/manual/en/language.operators.type.php#106882) [¶](https://www.php.net/manual/en/language.operators.type.php#106882)

**13 years ago**

``I don't see any mention of "namespaces" on this page so I thought I would chime in. The instanceof operator takes FQCN as second operator when you pass it as string and not a simple class name. It will not resolve it even if you have a `use MyNamespace\Bar;` at the top level. Here is what I am trying to say:
## testinclude.php ##
<?php
namespace Bar1;
{
class Foo1{ }
}
namespace Bar2;
{
class Foo2{ }
}
?>
## test.php ##
<?php
include('testinclude.php');
use Bar1\Foo1 as Foo;
$foo1 = new Foo(); $className = 'Bar1\Foo1';
var_dump($foo1 instanceof Bar1\Foo1);
var_dump($foo1 instanceof $className);
$className = 'Foo';
var_dump($foo1 instanceof $className);
use Bar2\Foo2;
$foo2 = new Foo2(); $className = 'Bar2\Foo2';
var_dump($foo2 instanceof Bar2\Foo2);
var_dump($foo2 instanceof $className);
$className = 'Foo2';
var_dump($foo2 instanceof $className);
?>
## stdout ##
bool(true)
bool(true)
bool(false)
bool(true)
bool(true)
bool(false)``

[up](https://www.php.net/manual/vote-note.php?id=113871&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113871&page=language.operators.type&vote=down "Vote down!")

47


[**_dava_**](https://www.php.net/manual/en/language.operators.type.php#113871) [¶](https://www.php.net/manual/en/language.operators.type.php#113871)

**11 years ago**

`You are also able to compare 2 objects using instanceOf. In that case, instanceOf will compare the types of both objects. That is sometimes very useful:
<?php
class A { }
class B { }
$a = new A;
$b = new B;
$a2 = new A;
echo $a instanceOf $a; // true
echo $a instanceOf $b; // false
echo $a instanceOf $a2; // true
?>`

[up](https://www.php.net/manual/vote-note.php?id=126060&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126060&page=language.operators.type&vote=down "Vote down!")

5


[**_wapinet at mail dot ru_**](https://www.php.net/manual/en/language.operators.type.php#126060) [¶](https://www.php.net/manual/en/language.operators.type.php#126060)

**4 years ago**

`if you have only class names (not objects) you can use that snippet: [https://3v4l.org/mUKUC](https://3v4l.org/mUKUC)
<?php
interface i{}
class a implements i{}
var_dump(a::class instanceof i); // false
var_dump(in_array(i::class, class_implements(a::class), true)); // true`

[up](https://www.php.net/manual/vote-note.php?id=121460&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121460&page=language.operators.type&vote=down "Vote down!")

8


[**_wadih at creationmw dot com_**](https://www.php.net/manual/en/language.operators.type.php#121460) [¶](https://www.php.net/manual/en/language.operators.type.php#121460)

**8 years ago**

`Doing $a instanceof stdClass from inside a namespace will not work on its own.
You will have to do:
<?php
if ($a instanceof \stdClass)
?>`

[up](https://www.php.net/manual/vote-note.php?id=85239&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85239&page=language.operators.type&vote=down "Vote down!")

9


[**_kevin dot benton at beatport dot com_**](https://www.php.net/manual/en/language.operators.type.php#85239) [¶](https://www.php.net/manual/en/language.operators.type.php#85239)

**17 years ago**

`Example #5 could also be extended to include...
var_dump($a instanceof MyInterface);
The new result would be
bool(true)
So - instanceof is smart enough to know that a class that implements an interface is an instance of the interface, not just the class.  I didn't see that point made clearly enough in the explanation at the top.`

[up](https://www.php.net/manual/vote-note.php?id=121827&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121827&page=language.operators.type&vote=down "Vote down!")

6


[**_Hayley Watson_**](https://www.php.net/manual/en/language.operators.type.php#121827) [¶](https://www.php.net/manual/en/language.operators.type.php#121827)

**7 years ago**

`If you want to use "$foo instanceof $bar" to determine if two objects are the same class, remember that "instanceof" will also evaluate to true if $foo is an instance of a _subclass_ of $bar's class.
If you really want to see if they are the _same_ class, then they both have to be instances of each other's class. That is:
<?php
($foo instanceof $bar && $bar instanceof $foo)
?>
Consider it an alternative to "get_class($bar) == get_class($foo)" that avoids the detour through to string lookups and comparisons.`

[up](https://www.php.net/manual/vote-note.php?id=87053&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87053&page=language.operators.type&vote=down "Vote down!")

17


[**_jtaal at eljakim dot nl_**](https://www.php.net/manual/en/language.operators.type.php#87053) [¶](https://www.php.net/manual/en/language.operators.type.php#87053)

**16 years ago**

`You can use "self" to reference to the current class:
<?php
class myclass {
    function mymethod($otherObject) {
        if ($otherObject instanceof self) {
            $otherObject->mymethod(null);
        }
        return 'works!';
    }
}
$a = new myclass();
print $a->mymethod($a);
?>`

[up](https://www.php.net/manual/vote-note.php?id=102988&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=102988&page=language.operators.type&vote=down "Vote down!")

13


[**_fbableus_**](https://www.php.net/manual/en/language.operators.type.php#102988) [¶](https://www.php.net/manual/en/language.operators.type.php#102988)

**14 years ago**

`If you want to test if a classname is an instance of a class, the instanceof operator won't work.
<?php
$classname = 'MyClass';
if( $classname instanceof MyParentClass) echo 'Child of it';
else echo 'Not child of it';
?>
Will always output
Not child of it
You must use a ReflectionClass :
<?php
$classname = 'MyClass';
$myReflection = new ReflectionClass($classname);
if( $myReflection->isSubclassOf('MyParentClass')) echo  'Child of it';
else echo 'Not child of it';
?>
Will output the good result.
If you're testing an interface, use implementsInterface() instead of isSublassOf().`

[up](https://www.php.net/manual/vote-note.php?id=108696&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=108696&page=language.operators.type&vote=down "Vote down!")

5


[**_wbcarts at juno dot com_**](https://www.php.net/manual/en/language.operators.type.php#108696) [¶](https://www.php.net/manual/en/language.operators.type.php#108696)

**13 years ago**

`SIMPLE, CLEAN, CLEAR use of the instanceof OPERATOR
First, define a couple of simple PHP Objects to work on -- I'll introduce Circle and Point. Here's the class definitions for both:
<?php
class Circle
{
protected $radius = 1.0;
/*
* This function is the reason we are going to use the
* instanceof operator below.
*/
public function setRadius($r)
{
    $this->radius = $r;
}
public function __toString()
{
    return 'Circle [radius=' . $this->radius . ']';
}
}
class Point
{
protected $x = 0;
protected $y = 0;
/*
* This function is the reason we are going to use the
* instanceof operator below.
*/
public function setLocation($x, $y)
{
    $this->x = $x;
    $this->y = $y;
}
public function __toString()
{
    return 'Point [x=' . $this->x . ', y=' . $this->y . ']';
}
}
?>
Now instantiate a few instances of these types. Note, I will put them in an array (collection) so we can iterate through them quickly.
<?php
$myCollection = array(123, 'abc', 'Hello World!',
new Circle(), new Circle(), new Circle(),
new Point(), new Point(), new Point());
$i = 0;
foreach($myCollection AS $item)
{
/*
* The setRadius() function is written in the Circle class
* definition above, so make sure $item is an instance of
* type Circle BEFORE calling it AND to avoid PHP PMS!
*/
if($item instanceof Circle)
{
    $item->setRadius($i);
}
/*
* The setLocation() function is written in the Point class
* definition above, so make sure $item is an instance of
* type Point BEFORE calling it AND to stay out of the ER!
*/
if($item instanceof Point)
{
    $item->setLocation($i, $i);
}
echo '$myCollection[' . $i++ . '] = ' . $item . '<br>';
}
?>
$myCollection[0] = 123
$myCollection[1] = abc
$myCollection[2] = Hello World!
$myCollection[3] = Circle [radius=3]
$myCollection[4] = Circle [radius=4]
$myCollection[5] = Circle [radius=5]
$myCollection[6] = Point [x=6, y=6]
$myCollection[7] = Point [x=7, y=7]
$myCollection[8] = Point [x=8, y=8]`

[up](https://www.php.net/manual/vote-note.php?id=124629&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124629&page=language.operators.type&vote=down "Vote down!")

2


[**_ASchmidt at Anamera dot net_**](https://www.php.net/manual/en/language.operators.type.php#124629) [¶](https://www.php.net/manual/en/language.operators.type.php#124629)

**5 years ago**

`Using an undefined variable will result in an error.
If variable is in doubt, one must prequalify:
    if ( isset( $MyInstance ) and $MyInstance instanceof MyClass ) ...`

[up](https://www.php.net/manual/vote-note.php?id=76582&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76582&page=language.operators.type&vote=down "Vote down!")

5


[**_julien plee using g mail dot com_**](https://www.php.net/manual/en/language.operators.type.php#76582) [¶](https://www.php.net/manual/en/language.operators.type.php#76582)

**18 years ago**

`Response to vinyanov at poczta dot onet dot pl:
You mentionned "the instanceof operator will not accept a string as its first operand". However, this behavior is absolutely right and therefore, you're misleading the meaning of an instance.
<?php 'ClassA' instanceof 'ClassB'; ?> means "the class named ClassA is an instance of the class named ClassB". This is a nonsense sentence because when you instanciate a class, you ALWAYS obtain an object. Consequently, you only can ask if an object is an instance of a class.
I believe asking if "a ClassA belongs to a ClassB" (or "a ClassA is a class of (type) ClassB") or even "a ClassA is (also) a ClassB" is more appropriate. But the first is not implemented and the second only works with objects, just like the instanceof operator.
Plus, I just have tested your code and it does absolutely NOT do the same as instanceof (extended to classes)! I can't advise anyone to reuse it. The use of <?php is_instance_of ($instanceOfA, 'ClassB'); ?> raises a warning "include_once(Object id #1.php) …" when using __autoload (trying to look for $instanceOfA as if it was a class name).
Finally, here is a fast (to me) sample function code to verify if an object or class:
<?php
function kind_of (&$object_or_class, $class)
{
    return is_object ($object_or_class) ?
        $object_or_class instanceof $class
        : (is_subclass_of ($object_or_class $class)
           || strtolower ($object_or_class) == strtolower ($class));
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=73853&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73853&page=language.operators.type&vote=down "Vote down!")

2


[**_jeanyves dot terrien at orange-ftgroup dot com_**](https://www.php.net/manual/en/language.operators.type.php#73853) [¶](https://www.php.net/manual/en/language.operators.type.php#73853)

**18 years ago**

`Cross version function even if you are working in php4
(instanceof is an undefined operator for php4)
function isMemberOf($classename) {
      $ver = floor(phpversion());
      if($ver > 4) {
         $instanceof = create_function ('$obj,$classname','return $obj instanceof $classname;');
         return $instanceof($this,$classname);
      } else {
         // Php4 uses lowercase for classname.
         return is_a($this, strtolower($classname));
      }
} // end function isMemberOf`

[up](https://www.php.net/manual/vote-note.php?id=80495&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80495&page=language.operators.type&vote=down "Vote down!")

3


[**_ejohnson82 at gmail dot com_**](https://www.php.net/manual/en/language.operators.type.php#80495) [¶](https://www.php.net/manual/en/language.operators.type.php#80495)

**17 years ago**

`The PHP parser generates a parse error on either of the two lines that are commented out here.
Apparently the 'instanceof' construct will take a string variable in the second spot, but it will NOT take a string... lame
class Bar {}
$b = new Bar;
$b_class = "Bar";
var_export($b instanceof Bar); // this is ok
var_export($b instanceof $b_class); // this is ok
//var_export($f instanceof "Bar"); // this is syntactically illegal
//var_export($f instanceof 'Bar'); // this is syntactically illegal`

[up](https://www.php.net/manual/vote-note.php?id=73609&page=language.operators.type&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73609&page=language.operators.type&vote=down "Vote down!")

2


[**_soletan at toxa dot de_**](https://www.php.net/manual/en/language.operators.type.php#73609) [¶](https://www.php.net/manual/en/language.operators.type.php#73609)

**18 years ago**

`Please note: != is a separate operator with separate semantics. Thinking about language grammar it's kind of ridicilous to negate an operator. Of course, it's possible to negate the result of a function (like is_a()), since it isn't negating the function itself or its semantics.
instanceof is a binary operator, and so used in binary terms like this
terma instanceof termb
while ! (negation) is a unary operator and so may be applied to a single term like this
!term
And a term never consists of an operator, only! There is no such construct in any language (please correct me!). However, instanceof doesn't finally support nested terms in every operand position ("terma" or "termb" above) as negation does:
!!!!!!!!!!!!!!term == term
So back again, did you ever write
a !!!!!!!!!!!!= b
to test equivalence?`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.type&repo=en&redirect=https://www.php.net/manual/en/language.operators.type.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google