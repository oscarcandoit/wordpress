---
url: https://www.php.net/manual/en/reflectionclass.newinstanceargs.php
scraped_at: 2025-10-20T02:49:00.713Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ReflectionClass::newInstanceArgs

(PHP 5 >= 5.1.3, PHP 7, PHP 8)

ReflectionClass::newInstanceArgs — Creates a new class instance from given arguments

### Description [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php\#refsect1-reflectionclass.newinstanceargs-description)

public**ReflectionClass::newInstanceArgs**([array](https://www.php.net/manual/en/language.types.array.php) `$args` = \[\]): [?](https://www.php.net/manual/en/language.types.null.php)[object](https://www.php.net/manual/en/language.types.object.php)

Creates a new instance of the class, the given arguments are passed to the
class constructor.


### Parameters [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php\#refsect1-reflectionclass.newinstanceargs-parameters)

`args`

The parameters to be passed to the class constructor as an [array](https://www.php.net/manual/en/language.types.array.php).


### Return Values [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php\#refsect1-reflectionclass.newinstanceargs-returnvalues)

Returns a new instance of the class, or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** on failure.


### Errors/Exceptions [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php\#refsect1-reflectionclass.newinstanceargs-errors)

A [ReflectionException](https://www.php.net/manual/en/class.reflectionexception.php) if the class constructor is not public.


A [ReflectionException](https://www.php.net/manual/en/class.reflectionexception.php) if the class does not have a constructor
and the `args` parameter contains one or more parameters.


### Examples [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php\#refsect1-reflectionclass.newinstanceargs-examples)

**Example #1 Basic usage of **ReflectionClass::newInstanceArgs()****

`<?php
$class = new ReflectionClass('ReflectionFunction');
$instance = $class->newInstanceArgs(array('substr'));
var_dump($instance);
?>`

Run code

The above example will output:

```
object(ReflectionFunction)#2 (1) {
  ["name"]=>
  string(6) "substr"
}
```

### See Also [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php\#refsect1-reflectionclass.newinstanceargs-seealso)

- [ReflectionClass::newInstance()](https://www.php.net/manual/en/reflectionclass.newinstance.php) \- Creates a new class instance from given arguments
- [ReflectionClass::newInstanceWithoutConstructor()](https://www.php.net/manual/en/reflectionclass.newinstancewithoutconstructor.php) \- Creates a new class instance without invoking the constructor

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/reflection/reflectionclass/newinstanceargs.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Freflectionclass.newinstanceargs%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=reflectionclass.newinstanceargs&repo=en&redirect=https://www.php.net/manual/en/reflectionclass.newinstanceargs.php)

### User Contributed Notes 8 notes

[up](https://www.php.net/manual/vote-note.php?id=118297&page=reflectionclass.newinstanceargs&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118297&page=reflectionclass.newinstanceargs&vote=down "Vote down!")

4


[**_kirillsaksin at no-spam dot yandex dot ru_**](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#118297) [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#118297)

**9 years ago**

`Hack to properly instantiate class with private constructor:
<?php
class TestClass
{
    private $property;
    private function __construct($argument)
    {
        $this->property = $argument;
    }
}
$ref = new ReflectionClass(TestClass::class);
$instance = $ref->newInstanceWithoutConstructor();
var_dump($instance);
echo PHP_EOL . '------------------------' . PHP_EOL . PHP_EOL;
$constructor = $ref->getConstructor();
$constructor->setAccessible(true);
$constructor->invokeArgs($instance, ['It works!']);
var_dump($instance);
// Output:
// class TestClass#3 (1) {
//   private $property =>
//   NULL
// }
//
// ------------------------
//
// class TestClass#3 (1) {
//   private $property =>
//   string(9) "It works!"
// }
?>`

[up](https://www.php.net/manual/vote-note.php?id=95137&page=reflectionclass.newinstanceargs&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95137&page=reflectionclass.newinstanceargs&vote=down "Vote down!")

5


[**_sarfraznawaz2005 at gmail dot com_**](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#95137) [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#95137)

**15 years ago**

`I use reflection class and also detect whether arguments are passed by reference or passed by value
and then initiate/call the method successfully with those arguments:
<?php
    if (count($args) > 1)
    {
        if (method_exists($class_name,  '__construct') === false)
        {
            exit("Constructor for the class <strong>$class_name</strong> does not exist, you should not pass arguments to the constructor of this class!");
        }

        $refMethod = new ReflectionMethod($class_name,  '__construct');
        $params = $refMethod->getParameters();

        $re_args = array();

        foreach($params as $key => $param)
        {
            if ($param->isPassedByReference())
            {
                $re_args[$key] = &$args[$key];
            }
            else
            {
                $re_args[$key] = $args[$key];
            }
        }

        $refClass = new ReflectionClass($class_name);
        $class_instance = $refClass->newInstanceArgs((array) $re_args);
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=90255&page=reflectionclass.newinstanceargs&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90255&page=reflectionclass.newinstanceargs&vote=down "Vote down!")

3


[**_richardcook at gmail dot com_**](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#90255) [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#90255)

**16 years ago**

`the newInstanceArgs function cannot call a class' constructor if it has references in its arguments, so be careful what you pass into it:
<?php
class Foo {
    function __construct (&$arr) {
        $this->arr = &$arr;
    }
    function createInstance () {
        $reflectionClass = new ReflectionClass("Bar");

        return $reflectionClass->newInstanceArgs(array($this, $this->arr));
    }
    function mod($key, $val) {
        $this->arr[$key] = $val;
    }
}
class Bar {
    function __construct (&$foo, &$arr) {
        $this->foo = &$foo;
        $this->arr = &$arr;
    }
    function mod($key, $val) {
        $this->arr[$key] = $val;
    }
}
$arr = array();
$foo = new Foo($arr);
$arr["x"] = 1;
$foo->mod("y", 2);
$bar = $foo->createInstance();
$bar->mod("z", 3);
echo "<pre>";
print_r($arr);
print_r($foo);
print_r($bar);
echo "</pre>";
/*
Output:
Warning: Invocation of Bar's constructor failed in [code path] on line 31
Fatal error: Call to a member function mod() on a non-object in [code path] on line 58
*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=100684&page=reflectionclass.newinstanceargs&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100684&page=reflectionclass.newinstanceargs&vote=down "Vote down!")

2


[**_talk at stephensugden dot com_**](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#100684) [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#100684)

**14 years ago**

`This is the way I dynamically instantiate objects in my lightweight IoC container
<?php
class SimpleContainer {
// ...
// Creates an instance of an object with the provided array of arguments
protected function instantiate($name, $args=array()){
    if(empty($args))
      return new $name();
    else {
      $ref = new ReflectionClass($name);
      return $ref->newInstanceArgs($args);
    }
}
// ...
}
?>
I explicitly do NOT handle the case where a user passes constructor arguments for a constructor-less class, as I this SHOULD fail.`

[up](https://www.php.net/manual/vote-note.php?id=117599&page=reflectionclass.newinstanceargs&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117599&page=reflectionclass.newinstanceargs&vote=down "Vote down!")

2


[**_dev at yopmail dot com_**](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#117599) [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#117599)

**10 years ago**

`With PHP 5.6, we can use the ... (T_ELLIPSIS) operator
<?php
class Test {
    public function __construct($a, $b) {
        echo $a . ' ' . $b;
    }
}
$args = array(12, 34);
new Test(... $args); // Displays "12 34"
?>`

[up](https://www.php.net/manual/vote-note.php?id=99517&page=reflectionclass.newinstanceargs&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99517&page=reflectionclass.newinstanceargs&vote=down "Vote down!")

 -2


[**_sausage at tehsausage dot com_**](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#99517) [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#99517)

**15 years ago**

`Annoyingly, this will throw an exception for classes with no constructor even if you pass an empty array for the arguments. For generic programming you should avoid this function and use call_user_func_array with newInstance.`

[up](https://www.php.net/manual/vote-note.php?id=93562&page=reflectionclass.newinstanceargs&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93562&page=reflectionclass.newinstanceargs&vote=down "Vote down!")

 -1


[**_kevinpeno at gmail dot com_**](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#93562) [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#93562)

**16 years ago**

`I misunderstood this function to be a sort of setter of Reflection::newInstance() arguments in an array form rather than a creator of new instances itself.
This function is equivilant to call_user_func_array() while Reflection::newInstance() is equivilant to call_user_func()`

[up](https://www.php.net/manual/vote-note.php?id=84763&page=reflectionclass.newinstanceargs&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84763&page=reflectionclass.newinstanceargs&vote=down "Vote down!")

 -2


[**_gromit at mailinator dot com_**](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#84763) [¶](https://www.php.net/manual/en/reflectionclass.newinstanceargs.php#84763)

**17 years ago**

`Be aware that calling the method newInstanceArgs with an empty array will still call the constructor with no arguments. If the class has no constructor then it will generate an exception.
You need to check if a constructor exists before calling this method or use try and catch to act on the exception.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=reflectionclass.newinstanceargs&repo=en&redirect=https://www.php.net/manual/en/reflectionclass.newinstanceargs.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google