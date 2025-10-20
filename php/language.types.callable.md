---
url: https://www.php.net/manual/en/language.types.callable.php
scraped_at: 2025-10-20T02:37:23.984Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Callbacks / Callables [¶](https://www.php.net/manual/en/language.types.callable.php\#language.types.callable)

Callbacks can be denoted by the [callable](https://www.php.net/manual/en/language.types.callable.php) type declaration.


Some functions like [call\_user\_func()](https://www.php.net/manual/en/function.call-user-func.php) or
[usort()](https://www.php.net/manual/en/function.usort.php) accept user-defined callback functions as a
parameter. Callback functions can not only be simple functions, but also
[object](https://www.php.net/manual/en/language.types.object.php) methods, including static class methods.


### Passing [¶](https://www.php.net/manual/en/language.types.callable.php\#language.types.callable.passing)

A PHP function is passed by either its name as a [string](https://www.php.net/manual/en/language.types.string.php) or by
a [first-class callable](https://www.php.net/manual/en/functions.first_class_callable_syntax.php).
Any built-in or user-defined function can be used, except language constructs
such as: [array()](https://www.php.net/manual/en/function.array.php), [echo](https://www.php.net/manual/en/function.echo.php),
[empty()](https://www.php.net/manual/en/function.empty.php), [eval()](https://www.php.net/manual/en/function.eval.php),
[exit()](https://www.php.net/manual/en/function.exit.php), [isset()](https://www.php.net/manual/en/function.isset.php),
[list()](https://www.php.net/manual/en/function.list.php), [print](https://www.php.net/manual/en/function.print.php) or
[unset()](https://www.php.net/manual/en/function.unset.php).


A method of an instantiated [object](https://www.php.net/manual/en/language.types.object.php) is passed as an
[array](https://www.php.net/manual/en/language.types.array.php) containing an [object](https://www.php.net/manual/en/language.types.object.php) at index 0 and the
method name at index 1. Accessing protected and private methods from
within a class is allowed.


Static class methods can also be passed without instantiating an
[object](https://www.php.net/manual/en/language.types.object.php) of that class by either, passing the class name
instead of an [object](https://www.php.net/manual/en/language.types.object.php) at index 0, or passing
`'ClassName::methodName'`.


Apart from common user-defined function,
[anonymous functions](https://www.php.net/manual/en/functions.anonymous.php) and
[arrow functions](https://www.php.net/manual/en/functions.arrow.php) can also be
passed to a callback parameter.


> **Note**:
>
>
> As of PHP 8.1.0, anonymous functions can also be created using the [first class callable syntax](https://www.php.net/manual/en/functions.first_class_callable_syntax.php).

Generally, any object implementing [\_\_invoke()](https://www.php.net/manual/en/language.oop5.magic.php#object.invoke) can also
be passed to a callback parameter.


**Example #1**
**Callback function examples**

`<?php
// An example callback function
function my_callback_function() {
    echo 'hello world!', PHP_EOL;
}
// An example callback method
class MyClass {
    static function myCallbackMethod() {
        echo 'Hello World!', PHP_EOL;
    }
}
// Type 1: Simple callback
call_user_func('my_callback_function');
// Type 2: Static class method call
call_user_func(array('MyClass', 'myCallbackMethod'));
// Type 3: Object method call
$obj = new MyClass();
call_user_func(array($obj, 'myCallbackMethod'));
// Type 4: Static class method call
call_user_func('MyClass::myCallbackMethod');
// Type 5: Relative static class method call
class A {
    public static function who() {
        echo 'A', PHP_EOL;
    }
}
class B extends A {
    public static function who() {
        echo 'B', PHP_EOL;
    }
}
call_user_func(array('B', 'parent::who')); // A, deprecated as of PHP 8.2.0
// Type 6: Objects implementing __invoke can be used as callables
class C {
    public function __invoke($name) {
        echo 'Hello ', $name, PHP_EOL;
    }
}
$c = new C();
call_user_func($c, 'PHP!');
?>`

Run code

**Example #2**
**Callback example using a [Closure](https://www.php.net/manual/en/class.closure.php)**

`<?php
// Our closure
$double = function($a) {
    return $a * 2;
};
// This is our range of numbers
$numbers = range(1, 5);
// Use the closure as a callback here to
// double the size of each element in our
// range
$new_numbers = array_map($double, $numbers);
print implode(' ', $new_numbers);
?>`

Run code

The above example will output:

```
2 4 6 8 10

```

> **Note**:
>
> Callbacks registered
> with functions such as [call\_user\_func()](https://www.php.net/manual/en/function.call-user-func.php) and [call\_user\_func\_array()](https://www.php.net/manual/en/function.call-user-func-array.php) will not be
> called if there is an uncaught exception thrown in a previous callback.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/callable.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.callable%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.callable&repo=en&redirect=https://www.php.net/manual/en/language.types.callable.php)

### User Contributed Notes 12 notes

[up](https://www.php.net/manual/vote-note.php?id=109073&page=language.types.callable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109073&page=language.types.callable&vote=down "Vote down!")

280


[**_andrewbessa at gmail dot com_**](https://www.php.net/manual/en/language.types.callable.php#109073) [¶](https://www.php.net/manual/en/language.types.callable.php#109073)

**13 years ago**

`You can also use the $this variable to specify a callback:
<?php
class MyClass {
    public $property = 'Hello World!';
    public function MyMethod()
    {
        call_user_func(array($this, 'myCallbackMethod'));
    }
    public function MyCallbackMethod()
    {
        echo $this->property;
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=110084&page=language.types.callable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110084&page=language.types.callable&vote=down "Vote down!")

207


[**_steve at mrclay dot org_**](https://www.php.net/manual/en/language.types.callable.php#110084) [¶](https://www.php.net/manual/en/language.types.callable.php#110084)

**13 years ago**

`Performance note: The callable type hint, like is_callable(), will trigger an autoload of the class if the value looks like a static method callback.`

[up](https://www.php.net/manual/vote-note.php?id=113447&page=language.types.callable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113447&page=language.types.callable&vote=down "Vote down!")

193


[**_computrius at gmail dot com_**](https://www.php.net/manual/en/language.types.callable.php#113447) [¶](https://www.php.net/manual/en/language.types.callable.php#113447)

**12 years ago**

`When specifying a call back in array notation (ie. array($this, "myfunc") ) the method can be private if called from inside the class, but if you call it from outside you'll get a warning:
<?php
class mc {
public function go(array $arr) {
       array_walk($arr, array($this, "walkIt"));
}
private function walkIt($val) {
       echo $val . "<br />";
}
    public function export() {
        return array($this, 'walkIt');
    }
}
$data = array(1,2,3,4);
$m = new mc;
$m->go($data); // valid
array_walk($data, $m->export()); // will generate warning
?>
Output:
1<br />2<br />3<br />4<br />
Warning: array_walk() expects parameter 2 to be a valid callback, cannot access private method mc::walkIt() in /in/tfh7f on line 22`

[up](https://www.php.net/manual/vote-note.php?id=117260&page=language.types.callable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117260&page=language.types.callable&vote=down "Vote down!")

184


[**_Riikka K_**](https://www.php.net/manual/en/language.types.callable.php#117260) [¶](https://www.php.net/manual/en/language.types.callable.php#117260)

**10 years ago**

`A note on differences when calling callbacks as "variable functions" without the use of call_user_func() (e.g. "<?php $callback = 'printf'; $callback('Hello World!') ?>"):
- Using the name of a function as string has worked since at least 4.3.0
- Calling anonymous functions and invokable objects has worked since 5.3.0
- Using the array structure [$object, 'method'] has worked since 5.4.0
Note, however, that the following are not supported when calling callbacks as variable functions, even though they are supported by call_user_func():
- Calling static class methods via strings such as 'foo::doStuff'
- Calling parent method using the [$object, 'parent::method'] array structure
All of these cases are correctly recognized as callbacks by the 'callable' type hint, however. Thus, the following code will produce an error "Fatal error: Call to undefined function foo::doStuff() in /tmp/code.php on line 4":
<?php
class foo {
    static function callIt(callable $callback) {
        $callback();
    }

    static function doStuff() {
        echo "Hello World!";
    }
}
foo::callIt('foo::doStuff');
?>
The code would work fine, if we replaced the '$callback()' with 'call_user_func($callback)' or if we used the array ['foo', 'doStuff'] as the callback instead.`

[up](https://www.php.net/manual/vote-note.php?id=116640&page=language.types.callable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116640&page=language.types.callable&vote=down "Vote down!")

185


[**_edanschwartz at gmail dot com_**](https://www.php.net/manual/en/language.types.callable.php#116640) [¶](https://www.php.net/manual/en/language.types.callable.php#116640)

**10 years ago**

``You can use 'self::methodName' as a callable, but this is dangerous. Consider this example:
<?php
class Foo {
    public static function doAwesomeThings() {
        FunctionCaller::callIt('self::someAwesomeMethod');
    }
    public static function someAwesomeMethod() {
        // fantastic code goes here.
    }
}
class FunctionCaller {
    public static function callIt(callable $func) {
        call_user_func($func);
    }
}
Foo::doAwesomeThings();
?>
This results in an error:
Warning: class 'FunctionCaller' does not have a method 'someAwesomeMethod'.
For this reason you should always use the full class name:
<?php
FunctionCaller::callIt('Foo::someAwesomeMethod');
?>
I believe this is because there is no way for FunctionCaller to know that the string 'self' at one point referred to to `Foo`.``

[up](https://www.php.net/manual/vote-note.php?id=112341&page=language.types.callable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112341&page=language.types.callable&vote=down "Vote down!")

175


[**_metamarkers at gmail dot com_**](https://www.php.net/manual/en/language.types.callable.php#112341) [¶](https://www.php.net/manual/en/language.types.callable.php#112341)

**12 years ago**

`you can pass an object as a callable if its class defines the __invoke() magic method..`

[up](https://www.php.net/manual/vote-note.php?id=118032&page=language.types.callable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118032&page=language.types.callable&vote=down "Vote down!")

118


[**_mariano dot REMOVE dot perez dot rodriguez at gmail dot com_**](https://www.php.net/manual/en/language.types.callable.php#118032) [¶](https://www.php.net/manual/en/language.types.callable.php#118032)

**10 years ago**

`I needed a function that would determine the type of callable being passed, and, eventually,
normalized it to some extent. Here's what I came up with:
<?php
/**
* The callable types and normalizations are given in the table below:
*
*  Callable                        | Normalization                   | Type
* ---------------------------------+---------------------------------+--------------
*  function (...) use (...) {...}  | function (...) use (...) {...}  | 'closure'
*  $object                         | $object                         | 'invocable'
*  "function"                      | "function"                      | 'function'
*  "class::method"                 | ["class", "method"]             | 'static'
*  ["class", "parent::method"]     | ["parent of class", "method"]   | 'static'
*  ["class", "self::method"]       | ["class", "method"]             | 'static'
*  ["class", "method"]             | ["class", "method"]             | 'static'
*  [$object, "parent::method"]     | [$object, "parent::method"]     | 'object'
*  [$object, "self::method"]       | [$object, "method"]             | 'object'
*  [$object, "method"]             | [$object, "method"]             | 'object'
* ---------------------------------+---------------------------------+--------------
*  other callable                  | idem                            | 'unknown'
* ---------------------------------+---------------------------------+--------------
*  not a callable                  | null                            | false
*
* If the "strict" parameter is set to true, additional checks are
* performed, in particular:
*  - when a callable string of the form "class::method" or a callable array
*    of the form ["class", "method"] is given, the method must be a static one,
*  - when a callable array of the form [$object, "method"] is given, the
*    method must be a non-static one.
*
*/
function callableType($callable, $strict = true, callable& $norm = null) {
if (!is_callable($callable)) {
    switch (true) {
      case is_object($callable):
        $norm = $callable;
        return 'Closure' === get_class($callable) ? 'closure' : 'invocable';
      case is_string($callable):
        $m    = null;
        if (preg_match('~^(?<class>[a-z_][a-z0-9_]*)::(?<method>[a-z_][a-z0-9_]*)$~i', $callable, $m)) {
          list($left, $right) = [$m['class'], $m['method']];
          if (!$strict || (new \ReflectionMethod($left, $right))->isStatic()) {
            $norm = [$left, $right];
            return 'static';
          }
        } else {
          $norm = $callable;
          return 'function';
        }
        break;
      case is_array($callable):
        $m = null;
        if (preg_match('~^(:?(?<reference>self|parent)::)?(?<method>[a-z_][a-z0-9_]*)$~i', $callable[1], $m)) {
          if (is_string($callable[0])) {
            if ('parent' === strtolower($m['reference'])) {
              list($left, $right) = [get_parent_class($callable[0]), $m['method']];
            } else {
              list($left, $right) = [$callable[0], $m['method']];
            }
            if (!$strict || (new \ReflectionMethod($left, $right))->isStatic()) {
              $norm = [$left, $right];
              return 'static';
            }
          } else {
            if ('self' === strtolower($m['reference'])) {
              list($left, $right) = [$callable[0], $m['method']];
            } else {
              list($left, $right) = $callable;
            }
            if (!$strict || !(new \ReflectionMethod($left, $right))->isStatic()) {
              $norm = [$left, $right];
              return 'object';
            }
          }
        }
        break;
    }
    $norm = $callable;
    return 'unknown';
}
$norm = null;
return false;
}
?>
Hope someone else finds it useful.`

[up](https://www.php.net/manual/vote-note.php?id=119166&page=language.types.callable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119166&page=language.types.callable&vote=down "Vote down!")

24


[**_bradyn at NOSPAM dot bradynpoulsen dot com_**](https://www.php.net/manual/en/language.types.callable.php#119166) [¶](https://www.php.net/manual/en/language.types.callable.php#119166)

**9 years ago**

`When trying to make a callable from a function name located in a namespace, you MUST give the fully qualified function name (regardless of the current namespace or use statements).
<?php
namespace MyNamespace;
function doSomethingFancy($arg1)
{
    // do something...
}
$values = [1, 2, 3];
array_map('doSomethingFancy', $values);
// array_map() expects parameter 1 to be a valid callback, function 'doSomethingFancy' not found or invalid function name
array_map('MyNamespace\doSomethingFancy', $values);
// => [..., ..., ...]`

[up](https://www.php.net/manual/vote-note.php?id=125947&page=language.types.callable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125947&page=language.types.callable&vote=down "Vote down!")

11


[**_InvisibleSmiley_**](https://www.php.net/manual/en/language.types.callable.php#125947) [¶](https://www.php.net/manual/en/language.types.callable.php#125947)

**4 years ago**

`If you pass a callable method to a function with a callable type declaration, the error message is misleading:
<?php
class X {
    protected function foo(): void {}
}
function bar(callable $c) {}
$x = new X;
$c = [$x, 'foo'];
bar($c);
?>
Error message will be something like "Argument #1 ($c) must be of type callable, array given" while the actual problem here is only the visibility of method "foo". All you need to do is changing it to public (or use a different approach, e.g. with a Closure).`

[up](https://www.php.net/manual/vote-note.php?id=124054&page=language.types.callable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124054&page=language.types.callable&vote=down "Vote down!")

6


[**_gulaschsuppe2 at gmail dot com_**](https://www.php.net/manual/en/language.types.callable.php#124054) [¶](https://www.php.net/manual/en/language.types.callable.php#124054)

**6 years ago**

`I tried many possible ways of calling functions by function name directly and assigned to a variable on 3v4l. Not mentioned yet, it is possible to use an array as a caller, at least since PHP 7.1.25. The following script contains all the information I gained:
<?php
// Call function via function name:
    // Basics:
        // A function can also be called by using its string name:
        function callbackFunc() {
            echo 'Hello World';
        }
        'callbackFunc'(); // Hello World

        // A function can also be called if its name is assigned to a variable:
            function callbackFunc() {
                echo 'Hello World';
            }
            $funcName = 'callbackFunc';
            $funcName(); // Hello World
    // Static class method:
        // It is also possible to call a public static class method via 'ClassName::functioName' notation:
            class A {
                public static function callbackMethod() {
                    echo "Hello World\n";
                }
            }
            'A::callbackMethod'(); // Hello World
            $funcName = 'A::callbackMethod';
            $funcName(); // Hello World
    // Non static class method:
        // It is also possible to call non static class methods by creating an array which first element is the object the method should be called on and the second element is the non static method to be called. The array can directly be used as a caller:
            class A {
                private $prop = "Hello World\n";
                public function callbackMethod() {
                    echo $this->prop;
                }
            }
            $a = new A;
            [$a, 'callbackMethod']();
            $funcCallArr = [$a, 'callbackMethod'];
            $funcCallArr();
        // Of course this also works inside the class with '$this':
            class A {
                private function privCallback() {
                    echo 'Private';
                }
                public function privCallbackCaller($funcName) {
                    [$this, $funcName]();
                }
            }
            (new A)->privCallbackCaller('privCallback'); // Private
?>`

[up](https://www.php.net/manual/vote-note.php?id=119159&page=language.types.callable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119159&page=language.types.callable&vote=down "Vote down!")

2


[**_pawel dot tadeusz dot niedzielski at gmail dot com_**](https://www.php.net/manual/en/language.types.callable.php#119159) [¶](https://www.php.net/manual/en/language.types.callable.php#119159)

**9 years ago**

`@edanschwartz at gmail dot com
You can use ::class property to always indicate the class you're in when using static methods:
<?php
class Foo {
    public static function doAwesomeThings() {
        FunctionCaller::callIt(self::class . '::someAwesomeMethod');
    }
    public static function someAwesomeMethod() {
        // fantastic code goes here.
    }
}
class FunctionCaller {
    public static function callIt(callable $func) {
        call_user_func($func);
    }
}
Foo::doAwesomeThings();
?>`

[up](https://www.php.net/manual/vote-note.php?id=123449&page=language.types.callable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123449&page=language.types.callable&vote=down "Vote down!")

0


[**_chris dot rutledge at gmail dot com_**](https://www.php.net/manual/en/language.types.callable.php#123449) [¶](https://www.php.net/manual/en/language.types.callable.php#123449)

**6 years ago**

`Having read this line in the manual above,
"A method of an instantiated object is passed as an array containing an object at index 0 and the method name at index 1. Accessing protected and private methods from within a class is allowed."
I decided to do some testing to see if I could access private methods using the call_user_func methods. Thankfully not, but for completeness here is my test which also covers using static and object contexts
<?php
class foo {

    public static $isInstance = false;

    public function __construct() {
        self::$isInstance = true;
    }
    public function bar() {
        var_dump(self::$isInstance);
        echo __METHOD__;
    }

    private function baz() {
        var_dump(self::$isInstance);
        echo __METHOD__;
    }

    public function qux() {
        $this->baz();
    }

    public function quux() {
        self::baz();
    }
}
call_user_func(['foo','bar']);    //fase, foo:bar
call_user_func(['foo','baz']);  //warning, cannot access private method
call_user_func(['foo','quux']); //false, foo::baz
call_user_func(['foo','qux']);  //fatal, Using $this when not in object context
$foo = new foo;
call_user_func([$foo,'bar']);    //true, foo::bar
call_user_func([$foo,'baz']);    //warning, cannot access private method
call_user_func([$foo,'qux']);    //true, foo::baz
call_user_func(['foo','bar']);  //true, foo::bar (static call, yet $isInstance is true)
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.callable&repo=en&redirect=https://www.php.net/manual/en/language.types.callable.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google