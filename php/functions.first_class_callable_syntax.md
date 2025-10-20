---
url: https://www.php.net/manual/en/functions.first_class_callable_syntax.php
scraped_at: 2025-10-20T02:31:57.510Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## First class callable syntax [¶](https://www.php.net/manual/en/functions.first_class_callable_syntax.php\#functions.first_class_callable_syntax)

The first class callable syntax is introduced as of PHP 8.1.0, as a way of creating [anonymous functions](https://www.php.net/manual/en/functions.anonymous.php) from [callable](https://www.php.net/manual/en/language.types.callable.php).
It supersedes existing callable syntax using strings and arrays.
The advantage of this syntax is that it is accessible to static analysis, and uses the scope at the point where the callable is acquired.


`CallableExpr(...)` syntax is used to create a [Closure](https://www.php.net/manual/en/class.closure.php) object from callable. `CallableExpr` accepts any expression that can be directly called in the PHP grammar:


**Example #1 Simple first class callable syntax**

`<?php
class Foo {
public function method() {}
public static function staticmethod() {}
public function __invoke() {}
}
$obj = new Foo();
$classStr = 'Foo';
$methodStr = 'method';
$staticmethodStr = 'staticmethod';
$f1 = strlen(...);
$f2 = $obj(...);  // invokable object
$f3 = $obj->method(...);
$f4 = $obj->$methodStr(...);
$f5 = Foo::staticmethod(...);
$f6 = $classStr::$staticmethodStr(...);
// traditional callable using string, array
$f7 = 'strlen'(...);
$f8 = [$obj, 'method'](...);
$f9 = [Foo::class, 'staticmethod'](...);
?>`

> **Note**:
>
>
> The `...` is part of the syntax, and not an omission.

`CallableExpr(...)` has the same semantics as [Closure::fromCallable()](https://www.php.net/manual/en/closure.fromcallable.php).
That is, unlike callable using strings and arrays, `CallableExpr(...)` respects the scope at the point where it is created:


**Example #2 Scope comparison of `CallableExpr(...)` and traditional callable**

`<?php
class Foo {
    public function getPrivateMethod() {
        return [$this, 'privateMethod'];
    }
    private function privateMethod() {
        echo __METHOD__, "\n";
    }
}
$foo = new Foo;
$privateMethod = $foo->getPrivateMethod();
$privateMethod();
// Fatal error: Call to private method Foo::privateMethod() from global scope
// This is because call is performed outside from Foo and visibility will be checked from this point.
class Foo1 {
    public function getPrivateMethod() {
        // Uses the scope where the callable is acquired.
        return $this->privateMethod(...); // identical to Closure::fromCallable([$this, 'privateMethod']);
    }
    private function privateMethod() {
        echo __METHOD__, "\n";
    }
}
$foo1 = new Foo1;
$privateMethod = $foo1->getPrivateMethod();
$privateMethod();  // Foo1::privateMethod
?>`

> **Note**:
>
>
> Object creation by this syntax (e.g `new Foo(...)`) is not supported, because `new Foo()` syntax is not considered a call.

> **Note**:
>
>
> The first-class callable syntax cannot be combined with the [nullsafe operator](https://www.php.net/manual/en/language.oop5.basic.php#language.oop5.basic.nullsafe). Both of the following result in a compile-time error:
>
>
> `<?php
> $obj?->method(...);
> $obj?->prop->method(...);
> ?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/functions.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunctions.first_class_callable_syntax%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=functions.first_class_callable_syntax&repo=en&redirect=https://www.php.net/manual/en/functions.first_class_callable_syntax.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=128590&page=functions.first_class_callable_syntax&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128590&page=functions.first_class_callable_syntax&vote=down "Vote down!")

22


[**_bienvenunet at yahoo dot com_**](https://www.php.net/manual/en/functions.first_class_callable_syntax.php#128590) [¶](https://www.php.net/manual/en/functions.first_class_callable_syntax.php#128590)

**2 years ago**

`There's a major gotcha with this syntax that may not be apparent until you use this syntax and find you're getting "Cannot rebind scope of closure created from method" exceptions in some random library code.
As the documentation indicates, the first-class callable uses the scope at the point where the callable is acquired. This is fine as long as nothing in your code will attempt to bind the callable with the \Closure::bindTo method.
I found this the hard way by changing callables going to Laravel's Macroable functionality from the array style to the first-class callable style. The Macroable functionality \Closure::bindTo calls on the callable.
AFAIK, the only workaround is to use the uglier array syntax.`

[up](https://www.php.net/manual/vote-note.php?id=130188&page=functions.first_class_callable_syntax&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130188&page=functions.first_class_callable_syntax&vote=down "Vote down!")

1


[**_dan dot feder at civicactions dot com_**](https://www.php.net/manual/en/functions.first_class_callable_syntax.php#130188) [¶](https://www.php.net/manual/en/functions.first_class_callable_syntax.php#130188)

**6 months ago**

`Also note that closures are not serializable. So if you are storing a reference to a callback in a variable that will be serialized for caching or any other purpose, do not switch to this syntax or your serialization will break.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=functions.first_class_callable_syntax&repo=en&redirect=https://www.php.net/manual/en/functions.first_class_callable_syntax.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google