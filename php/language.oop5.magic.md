---
url: https://www.php.net/manual/en/language.oop5.magic.php
scraped_at: 2025-10-20T02:40:59.280Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Magic Methods [¶](https://www.php.net/manual/en/language.oop5.magic.php\#language.oop5.magic)

Magic methods are special methods which override PHP's default's action
when certain actions are performed on an object.


**Caution**

All methods names starting with `__` are reserved by PHP.
Therefore, it is not recommended to use such method names unless overriding
PHP's behavior.


The following method names are considered magical:

[\_\_construct()](https://www.php.net/manual/en/language.oop5.decon.php#object.construct),
[\_\_destruct()](https://www.php.net/manual/en/language.oop5.decon.php#object.destruct),
[\_\_call()](https://www.php.net/manual/en/language.oop5.overloading.php#object.call),
[\_\_callStatic()](https://www.php.net/manual/en/language.oop5.overloading.php#object.callstatic),
[\_\_get()](https://www.php.net/manual/en/language.oop5.overloading.php#object.get),
[\_\_set()](https://www.php.net/manual/en/language.oop5.overloading.php#object.set),
[\_\_isset()](https://www.php.net/manual/en/language.oop5.overloading.php#object.isset),
[\_\_unset()](https://www.php.net/manual/en/language.oop5.overloading.php#object.unset),
[\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep),
[\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php#object.wakeup),
[\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize),
[\_\_unserialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.unserialize),
[\_\_toString()](https://www.php.net/manual/en/language.oop5.magic.php#object.tostring),
[\_\_invoke()](https://www.php.net/manual/en/language.oop5.magic.php#object.invoke),
[\_\_set\_state()](https://www.php.net/manual/en/language.oop5.magic.php#object.set-state),
[\_\_clone()](https://www.php.net/manual/en/language.oop5.cloning.php#object.clone), and
[\_\_debugInfo()](https://www.php.net/manual/en/language.oop5.magic.php#object.debuginfo).


**Warning**

All magic methods, with the exception of
[\_\_construct()](https://www.php.net/manual/en/language.oop5.decon.php#object.construct),
[\_\_destruct()](https://www.php.net/manual/en/language.oop5.decon.php#object.destruct), and
[\_\_clone()](https://www.php.net/manual/en/language.oop5.cloning.php#object.clone),
_must_ be declared as `public`,
otherwise an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is emitted.
Prior to PHP 8.0.0, no diagnostic was emitted for the magic methods
[\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep),
[\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php#object.wakeup),
[\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize),
[\_\_unserialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.unserialize), and
[\_\_set\_state()](https://www.php.net/manual/en/language.oop5.magic.php#object.set-state).


**Warning**

If type declarations are used in the definition of a magic method, they
must be identical to the signature described in this document.
Otherwise, a fatal error is emitted.
Prior to PHP 8.0.0, no diagnostic was emitted.
However, [\_\_construct()](https://www.php.net/manual/en/language.oop5.decon.php#object.construct) and
[\_\_destruct()](https://www.php.net/manual/en/language.oop5.decon.php#object.destruct) must not declare a return type;
otherwise a fatal error is emitted.


### [\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php\#object.sleep) and  [\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php\#object.wakeup) [¶](https://www.php.net/manual/en/language.oop5.magic.php\#language.oop5.magic.sleep)

public**\_\_sleep**(): [array](https://www.php.net/manual/en/language.types.array.php)

public**\_\_wakeup**(): [void](https://www.php.net/manual/en/language.types.void.php)

[serialize()](https://www.php.net/manual/en/function.serialize.php) checks if the class has a function with
the magic name [\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep). If so, that function is
executed prior to any serialization. It can clean up the object
and is supposed to return an array with the names of all variables
of that object that should be serialized.
If the method doesn't return anything then **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** is serialized and
**`[E\_NOTICE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-notice)`** is issued.


> **Note**:
>
>
> It is not possible for [\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep) to return names of
> private properties in parent classes. Doing this will result in an
> **`[E\_NOTICE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-notice)`** level error.
> Use [\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize) instead.

> **Note**:
>
>
> As of PHP 8.0.0, returning a value which is not an array from [\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep) generates a warning. Previously, it generated a notice.

The intended use of [\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep) is to commit pending
data or perform similar cleanup tasks. Also, the function is
useful if a very large object doesn't need to be saved completely.


Conversely, [unserialize()](https://www.php.net/manual/en/function.unserialize.php) checks for the
presence of a function with the magic name
[\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php#object.wakeup). If present, this function can
reconstruct any resources that the object may have.


The intended use of [\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php#object.wakeup) is to
reestablish any database connections that may have been lost
during serialization and perform other reinitialization
tasks.


**Example #1 Sleep and wakeup**

`<?php
class Connection
{
    protected $link;
    private $dsn, $username, $password;

    public function __construct($dsn, $username, $password)
    {
        $this->dsn = $dsn;
        $this->username = $username;
        $this->password = $password;
        $this->connect();
    }

    private function connect()
    {
        $this->link = new PDO($this->dsn, $this->username, $this->password);
    }

    public function __sleep()
    {
        return array('dsn', 'username', 'password');
    }

    public function __wakeup()
    {
        $this->connect();
    }
}?>`

Run code

### [\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php\#object.serialize) and  [\_\_unserialize()](https://www.php.net/manual/en/language.oop5.magic.php\#object.unserialize) [¶](https://www.php.net/manual/en/language.oop5.magic.php\#language.oop5.magic.serialize)

public**\_\_serialize**(): [array](https://www.php.net/manual/en/language.types.array.php)

public**\_\_unserialize**([array](https://www.php.net/manual/en/language.types.array.php) `$data`): [void](https://www.php.net/manual/en/language.types.void.php)

[serialize()](https://www.php.net/manual/en/function.serialize.php) checks if the class has a function with
the magic name [\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize). If so, that function is
executed prior to any serialization. It must construct and return an associative array of key/value pairs
that represent the serialized form of the object. If no array is returned a [TypeError](https://www.php.net/manual/en/class.typeerror.php)
will be thrown.


> **Note**:
>
>
> If both [\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize) and [\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep)
> are defined in the same object, only [\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize) will be called.
> [\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep) will be ignored. If the object implements the [Serializable](https://www.php.net/manual/en/class.serializable.php)
> interface, the interface's `serialize()` method will be ignored and [\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize)
> used instead.

The intended use of [\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize) is to define a serialization-friendly
arbitrary representation of the object. Elements of the array may correspond to properties of the object but
that is not required.


Conversely, [unserialize()](https://www.php.net/manual/en/function.unserialize.php) checks for the
presence of a function with the magic name
[\_\_unserialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.unserialize). If present, this function will be passed the
restored array that was returned from [\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize). It may
then restore the properties of the object from that array as appropriate.


> **Note**:
>
>
> If both [\_\_unserialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.unserialize) and [\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php#object.wakeup)
> are defined in the same object, only [\_\_unserialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.unserialize) will be called.
> [\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php#object.wakeup) will be ignored.

> **Note**:
>
>
> This feature is available as of PHP 7.4.0.

**Example #2 Serialize and unserialize**

`<?php
class Connection
{
    protected $link;
    private $dsn, $username, $password;
    public function __construct($dsn, $username, $password)
    {
        $this->dsn = $dsn;
        $this->username = $username;
        $this->password = $password;
        $this->connect();
    }
    private function connect()
    {
        $this->link = new PDO($this->dsn, $this->username, $this->password);
    }
    public function __serialize(): array
    {
        return [\
          'dsn' => $this->dsn,\
          'user' => $this->username,\
          'pass' => $this->password,\
        ];
    }
    public function __unserialize(array $data): void
    {
        $this->dsn = $data['dsn'];
        $this->username = $data['user'];
        $this->password = $data['pass'];
        $this->connect();
    }
}?>`

Run code

### [\_\_toString()](https://www.php.net/manual/en/language.oop5.magic.php\#object.tostring) [¶](https://www.php.net/manual/en/language.oop5.magic.php\#language.oop5.magic.tostring)

public**\_\_toString**(): [string](https://www.php.net/manual/en/language.types.string.php)

The [\_\_toString()](https://www.php.net/manual/en/language.oop5.magic.php#object.tostring) method allows a class to decide
how it will react when it is treated like a string. For example,
what `echo $obj;` will print.


**Warning**

As of PHP 8.0.0, the return value follows standard PHP type semantics,
meaning it will be coerced into a [string](https://www.php.net/manual/en/language.types.string.php) if possible and if
[strict typing](https://www.php.net/manual/en/language.types.declarations.php#language.types.declarations.strict)
is disabled.


A [Stringable](https://www.php.net/manual/en/class.stringable.php) object will
_not_ be accepted by a [string](https://www.php.net/manual/en/language.types.string.php) type declaration if
[strict typing](https://www.php.net/manual/en/language.types.declarations.php#language.types.declarations.strict)
is enabled. If such behaviour is wanted the type declaration must accept
[Stringable](https://www.php.net/manual/en/class.stringable.php) and [string](https://www.php.net/manual/en/language.types.string.php) via a union type.


As of PHP 8.0.0, any class that contains a [\_\_toString()](https://www.php.net/manual/en/language.oop5.magic.php#object.tostring)
method will also implicitly implement the [Stringable](https://www.php.net/manual/en/class.stringable.php) interface, and will
thus pass type checks for that interface. Explicitly implementing the interface anyway is
recommended.


In PHP 7.4, the returned value _must_ be a
[string](https://www.php.net/manual/en/language.types.string.php), otherwise an [Error](https://www.php.net/manual/en/class.error.php) is thrown.


Prior to PHP 7.4.0, the returned value _must_ be a
[string](https://www.php.net/manual/en/language.types.string.php), otherwise a fatal **`[E\_RECOVERABLE\_ERROR](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-recoverable-error)`**
is emitted.


**Warning**

It was not possible to throw an exception from within a
[\_\_toString()](https://www.php.net/manual/en/language.oop5.magic.php#object.tostring)
method prior to PHP 7.4.0. Doing so will result in a fatal error.


**Example #3 Simple example**

`<?php
// Declare a simple class
class TestClass
{
    public $foo;
    public function __construct($foo)
    {
        $this->foo = $foo;
    }
    public function __toString()
    {
        return $this->foo;
    }
}
$class = new TestClass('Hello');
echo $class;
?>`

Run code

The above example will output:

```
Hello

```

### [\_\_invoke()](https://www.php.net/manual/en/language.oop5.magic.php\#object.invoke) [¶](https://www.php.net/manual/en/language.oop5.magic.php\#language.oop5.magic.invoke)

**\_\_invoke**(`...$values`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

The [\_\_invoke()](https://www.php.net/manual/en/language.oop5.magic.php#object.invoke) method is called when a script tries to
call an object as a function.


**Example #4 Using [\_\_invoke()](https://www.php.net/manual/en/language.oop5.magic.php#object.invoke)**

`<?php
class CallableClass
{
    public function __invoke($x)
    {
        var_dump($x);
    }
}
$obj = new CallableClass;
$obj(5);
var_dump(is_callable($obj));
?>`

Run code

The above example will output:

```
int(5)
bool(true)

```

**Example #5 Using [\_\_invoke()](https://www.php.net/manual/en/language.oop5.magic.php#object.invoke)**

`<?php
class Sort
{
    private $key;
    public function __construct(string $key)
    {
        $this->key = $key;
    }
    public function __invoke(array $a, array $b): int
    {
        return $a[$this->key] <=> $b[$this->key];
    }
}
$customers = [\
    ['id' => 1, 'first_name' => 'John', 'last_name' => 'Do'],\
    ['id' => 3, 'first_name' => 'Alice', 'last_name' => 'Gustav'],\
    ['id' => 2, 'first_name' => 'Bob', 'last_name' => 'Filipe']\
];
// sort customers by first name
usort($customers, new Sort('first_name'));
print_r($customers);
// sort customers by last name
usort($customers, new Sort('last_name'));
print_r($customers);
?>`

Run code

The above example will output:

```
Array
(
    [0] => Array
        (
            [id] => 3
            [first_name] => Alice
            [last_name] => Gustav
        )

    [1] => Array
        (
            [id] => 2
            [first_name] => Bob
            [last_name] => Filipe
        )

    [2] => Array
        (
            [id] => 1
            [first_name] => John
            [last_name] => Do
        )

)
Array
(
    [0] => Array
        (
            [id] => 1
            [first_name] => John
            [last_name] => Do
        )

    [1] => Array
        (
            [id] => 2
            [first_name] => Bob
            [last_name] => Filipe
        )

    [2] => Array
        (
            [id] => 3
            [first_name] => Alice
            [last_name] => Gustav
        )

)

```

### [\_\_set\_state()](https://www.php.net/manual/en/language.oop5.magic.php\#object.set-state) [¶](https://www.php.net/manual/en/language.oop5.magic.php\#language.oop5.magic.set-state)

static**\_\_set\_state**([array](https://www.php.net/manual/en/language.types.array.php) `$properties`): [object](https://www.php.net/manual/en/language.types.object.php)

This [static](https://www.php.net/manual/en/language.oop5.static.php) method is called
for classes exported by [var\_export()](https://www.php.net/manual/en/function.var-export.php).


The only parameter of this method is an array containing exported
properties in the form `['property' => value, ...]`.


**Example #6 Using [\_\_set\_state()](https://www.php.net/manual/en/language.oop5.magic.php#object.set-state)**

`<?php
class A
{
    public $var1;
    public $var2;
    public static function __set_state($an_array)
    {
        $obj = new A;
        $obj->var1 = $an_array['var1'];
        $obj->var2 = $an_array['var2'];
        return $obj;
    }
}
$a = new A;
$a->var1 = 5;
$a->var2 = 'foo';
$b = var_export($a, true);
var_dump($b);
eval('$c = ' . $b . ';');
var_dump($c);
?>`

Run code

The above example will output:

```
string(60) "A::__set_state(array(
   'var1' => 5,
   'var2' => 'foo',
))"
object(A)#2 (2) {
  ["var1"]=>
  int(5)
  ["var2"]=>
  string(3) "foo"
}

```

> **Note**:
>
> When exporting an object, [var\_export()](https://www.php.net/manual/en/function.var-export.php) does not check
> whether [\_\_set\_state()](https://www.php.net/manual/en/language.oop5.magic.php#object.set-state) is
> implemented by the object's class, so re-importing objects will result in an [Error](https://www.php.net/manual/en/class.error.php) exception,
> if \_\_set\_state() is not implemented. Particularly, this affects some
> internal classes.
>
> It is the responsibility of the programmer to verify that only objects will
> be re-imported, whose class implements \_\_set\_state().

### [\_\_debugInfo()](https://www.php.net/manual/en/language.oop5.magic.php\#object.debuginfo) [¶](https://www.php.net/manual/en/language.oop5.magic.php\#language.oop5.magic.debuginfo)

**\_\_debugInfo**(): [array](https://www.php.net/manual/en/language.types.array.php)

This method is called by [var\_dump()](https://www.php.net/manual/en/function.var-dump.php) when dumping an
object to get the properties that should be shown. If the method isn't
defined on an object, then all public, protected and private properties
will be shown.


**Example #7 Using [\_\_debugInfo()](https://www.php.net/manual/en/language.oop5.magic.php#object.debuginfo)**

`<?php
class C {
    private $prop;
    public function __construct($val) {
        $this->prop = $val;
    }
    public function __debugInfo() {
        return [\
            'propSquared' => $this->prop ** 2,\
        ];
    }
}
var_dump(new C(42));
?>`

Run code

The above example will output:

```
object(C)#1 (1) {
  ["propSquared"]=>
  int(1764)
}

```

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/oop5/magic.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.oop5.magic%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.oop5.magic&repo=en&redirect=https://www.php.net/manual/en/language.oop5.magic.php)

### User Contributed Notes 10 notes

[up](https://www.php.net/manual/vote-note.php?id=86111&page=language.oop5.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86111&page=language.oop5.magic&vote=down "Vote down!")

54


[**_jon at webignition dot net_**](https://www.php.net/manual/en/language.oop5.magic.php#86111) [¶](https://www.php.net/manual/en/language.oop5.magic.php#86111)

**17 years ago**

`The __toString() method is extremely useful for converting class attribute names and values into common string representations of data (of which there are many choices). I mention this as previous references to __toString() refer only to debugging uses.
I have previously used the __toString() method in the following ways:
 - representing a data-holding object as:
   - XML
   - raw POST data
   - a GET query string
   - header name:value pairs
 - representing a custom mail object as an actual email (headers then body, all correctly represented)
When creating a class, consider what possible standard string representations are available and, of those, which would be the most relevant with respect to the purpose of the class.
Being able to represent data-holding objects in standardised string forms makes it much easier for your internal representations of data to be shared in an interoperable way with other applications.`

[up](https://www.php.net/manual/vote-note.php?id=87404&page=language.oop5.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87404&page=language.oop5.magic&vote=down "Vote down!")

19


[**_jsnell at e-normous dot com_**](https://www.php.net/manual/en/language.oop5.magic.php#87404) [¶](https://www.php.net/manual/en/language.oop5.magic.php#87404)

**16 years ago**

`Be very careful to define __set_state() in classes which inherit from a parent using it, as the static __set_state() call will be called for any children.  If you are not careful, you will end up with an object of the wrong type.  Here is an example:
<?php
class A
{
    public $var1;
    public static function __set_state($an_array)
    {
        $obj = new A;
        $obj->var1 = $an_array['var1'];
        return $obj;
    }
}
class B extends A {
}
$b = new B;
$b->var1 = 5;
eval('$new_b = ' . var_export($b, true) . ';');
var_dump($new_b);
/*
object(A)#2 (1) {
["var1"]=>
int(5)
}
*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=128621&page=language.oop5.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128621&page=language.oop5.magic&vote=down "Vote down!")

6


[**_tyler at nighthound dot us_**](https://www.php.net/manual/en/language.oop5.magic.php#128621) [¶](https://www.php.net/manual/en/language.oop5.magic.php#128621)

**2 years ago**

`Please note that as of PHP 8.2 implementing __serialize() has no control over the output of json_encode(). you still have to implement JsonSerializable.`

[up](https://www.php.net/manual/vote-note.php?id=121158&page=language.oop5.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121158&page=language.oop5.magic&vote=down "Vote down!")

11


[**_kguest at php dot net_**](https://www.php.net/manual/en/language.oop5.magic.php#121158) [¶](https://www.php.net/manual/en/language.oop5.magic.php#121158)

**8 years ago**

`__debugInfo  is also utilised when calling print_r on an object:
$ cat test.php
<?php
class FooQ {
     private $bar = '';
     public function __construct($val) {
         $this->bar = $val;
     }
     public function __debugInfo()
     {
         return ['_bar' => $this->bar];
     }
}
$fooq = new FooQ("q");
print_r ($fooq);
$ php test.php
FooQ Object
(
    [_bar] => q
)
$`

[up](https://www.php.net/manual/vote-note.php?id=125282&page=language.oop5.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125282&page=language.oop5.magic&vote=down "Vote down!")

7


[**_ctamayo at sitecrafting dot com_**](https://www.php.net/manual/en/language.oop5.magic.php#125282) [¶](https://www.php.net/manual/en/language.oop5.magic.php#125282)

**5 years ago**

`Due to a bug in PHP <= 7.3, overriding the __debugInfo() method from SPL classes is silently ignored.
<?php
class Debuggable extends ArrayObject {
public function __debugInfo() {
    return ['special' => 'This should show up'];
}
}
var_dump(new Debuggable());
// Expected output:
// object(Debuggable)#1 (1) {
//   ["special"]=>
//   string(19) "This should show up"
// }
// Actual output:
// object(Debuggable)#1 (1) {
//   ["storage":"ArrayObject":private]=>
//   array(0) {
//   }
// }
?>
Bug report: [https://bugs.php.net/bug.php?id=69264](https://bugs.php.net/bug.php?id=69264)`

[up](https://www.php.net/manual/vote-note.php?id=122684&page=language.oop5.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122684&page=language.oop5.magic&vote=down "Vote down!")

7


[**_daniel dot peder at gmail dot com_**](https://www.php.net/manual/en/language.oop5.magic.php#122684) [¶](https://www.php.net/manual/en/language.oop5.magic.php#122684)

**7 years ago**

`[http://sandbox.onlinephpfunctions.com/code/4d2cc3648aed58c0dad90c7868173a4775e5ba0c](http://sandbox.onlinephpfunctions.com/code/4d2cc3648aed58c0dad90c7868173a4775e5ba0c)
IMHO a bug or need feature change
providing a object as a array index doesn't try to us __toString() method so some volatile object identifier is used to index the array, which is breaking any persistency. Type hinting solves that, but while other than "string" type hinting doesn't work on ob jects, the automatic conversion to string should be very intuitive.
PS: tried to submit bug, but withot patch the bugs are ignored, unfortunately, I don't C coding
<?php
class shop_product_id {

    protected $shop_name;
    protected $product_id;

    function __construct($shop_name,$product_id){
        $this->shop_name = $shop_name;
        $this->product_id = $product_id;
    }
    function __toString(){
        return $this->shop_name . ':' . $this->product_id;
    }
}
$shop_name = 'Shop_A';
$product_id = 123;
$demo_id = $shop_name . ':' . $product_id;
$demo_name = 'Some product in shop A';
$all_products = [ $demo_id => $demo_name ];
$pid = new shop_product_id( $shop_name, $product_id );
echo "with type hinting: ";
echo ($demo_name === $all_products[(string)$pid]) ? "ok" : "fail";
echo "\n";
echo "without type hinting: ";
echo ($demo_name === $all_products[$pid]) ?  "ok" : "fail";
echo "\n";`

[up](https://www.php.net/manual/vote-note.php?id=55844&page=language.oop5.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=55844&page=language.oop5.magic&vote=down "Vote down!")

7


[**_martin dot goldinger at netserver dot ch_**](https://www.php.net/manual/en/language.oop5.magic.php#55844) [¶](https://www.php.net/manual/en/language.oop5.magic.php#55844)

**20 years ago**

`When you use sessions, its very important to keep the sessiondata small, due to low performance with unserialize. Every class shoud extend from this class. The result will be, that no null Values are written to the sessiondata. It will increase performance.
<?
class BaseObject
{
    function __sleep()
    {
        $vars = (array)$this;
        foreach ($vars as $key => $val)
        {
            if (is_null($val))
            {
                unset($vars[$key]);
            }
        }
        return array_keys($vars);
    }
};
?>`

[up](https://www.php.net/manual/vote-note.php?id=49413&page=language.oop5.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=49413&page=language.oop5.magic&vote=down "Vote down!")

5


[**_ddavenport at newagedigital dot com_**](https://www.php.net/manual/en/language.oop5.magic.php#49413) [¶](https://www.php.net/manual/en/language.oop5.magic.php#49413)

**20 years ago**

`One of the principles of OOP is encapsulation--the idea that an object should handle its own data and no others'.  Asking base classes to take care of subclasses' data, esp considering that a class can't possibly know how many dozens of ways it will be extended, is irresponsible and dangerous.
Consider the following...
<?php
class SomeStupidStorageClass
{
public function getContents($pos, $len) { ...stuff... }
}
class CryptedStorageClass extends SomeStupidStorageClass
{
private $decrypted_block;
public function getContents($pos, $len) { ...decrypt... }
}
?>
If SomeStupidStorageClass decided to serialize its subclasses' data as well as its own, a portion of what was once an encrypted thingie could be stored, in the clear, wherever the thingie was stored.  Obviously, CryptedStorageClass would never have chosen this...but it had to either know how to serialize its parent class's data without calling parent::_sleep(), or let the base class do what it wanted to.
Considering encapsulation again, no class should have to know how the parent handles its own private data.  And it certainly shouldn't have to worry that users will find a way to break access controls in the name of convenience.
If a class wants both to have private/protected data and to survive serialization, it should have its own __sleep() method which asks the parent to report its own fields and then adds to the list if applicable.  Like so....
<?php
class BetterClass
{
private $content;
public function __sleep()
{
    return array('basedata1', 'basedata2');
}
public function getContents() { ...stuff... }
}
class BetterDerivedClass extends BetterClass
{
private $decrypted_block;
public function __sleep()
{
    return parent::__sleep();
}
public function getContents() { ...decrypt... }
}
?>
The derived class has better control over its data, and we don't have to worry about something being stored that shouldn't be.`

[up](https://www.php.net/manual/vote-note.php?id=63863&page=language.oop5.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=63863&page=language.oop5.magic&vote=down "Vote down!")

4


[**_rayRO_**](https://www.php.net/manual/en/language.oop5.magic.php#63863) [¶](https://www.php.net/manual/en/language.oop5.magic.php#63863)

**19 years ago**

`If you use the Magical Method '__set()', be shure that the call of
<?php
$myobject->test['myarray'] = 'data';
?>
will not appear!
For that u have to do it the fine way if you want to use __set Method ;)
<?php
$myobject->test = array('myarray' => 'data');
?>
If a Variable is already set, the __set Magic Method already wont appear!
My first solution was to use a Caller Class.
With that, i ever knew which Module i currently use!
But who needs it... :]
There are quiet better solutions for this...
Here's the Code:
<?php
class Caller {
    public $caller;
    public $module;
    function __call($funcname, $args = array()) {
        $this->setModuleInformation();
        if (is_object($this->caller) && function_exists('call_user_func_array'))
            $return = call_user_func_array(array(&$this->caller, $funcname), $args);
        else
            trigger_error("Call to Function with call_user_func_array failed", E_USER_ERROR);

        $this->unsetModuleInformation();
        return $return;
    }
    function __construct($callerClassName = false, $callerModuleName = 'Webboard') {
        if ($callerClassName == false)
            trigger_error('No Classname', E_USER_ERROR);
        $this->module = $callerModuleName;
        if (class_exists($callerClassName))
            $this->caller = new $callerClassName();
        else
            trigger_error('Class not exists: \''.$callerClassName.'\'', E_USER_ERROR);
        if (is_object($this->caller))
        {
            $this->setModuleInformation();
            if (method_exists($this->caller, '__init'))
                $this->caller->__init();
            $this->unsetModuleInformation();
        }
        else
            trigger_error('Caller is no object!', E_USER_ERROR);
    }
    function __destruct() {
        $this->setModuleInformation();
        if (method_exists($this->caller, '__deinit'))
            $this->caller->__deinit();
        $this->unsetModuleInformation();
    }
    function __isset($isset) {
        $this->setModuleInformation();
        if (is_object($this->caller))
            $return = isset($this->caller->{$isset});
        else
            trigger_error('Caller is no object!', E_USER_ERROR);
        $this->unsetModuleInformation();
        return $return;
    }
    function __unset($unset) {
        $this->setModuleInformation();
        if (is_object($this->caller)) {
            if (isset($this->caller->{$unset}))
                unset($this->caller->{$unset});
        }
        else
            trigger_error('Caller is no object!', E_USER_ERROR);
        $this->unsetModuleInformation();
    }
    function __set($set, $val) {
        $this->setModuleInformation();
        if (is_object($this->caller))
            $this->caller->{$set} = $val;
        else
            trigger_error('Caller is no object!', E_USER_ERROR);
        $this->unsetModuleInformation();
    }
    function __get($get) {
        $this->setModuleInformation();
        if (is_object($this->caller)) {
            if (isset($this->caller->{$get}))
                $return = $this->caller->{$get};
            else
                $return = false;
        }
        else
            trigger_error('Caller is no object!', E_USER_ERROR);
        $this->unsetModuleInformation();
        return $return;
    }

    function setModuleInformation() {
        $this->caller->module = $this->module;
    }
    function unsetModuleInformation() {
        $this->caller->module = NULL;
    }
}
// Well this can be a Config Class?
class Config {
    public $module;
    public $test;
    function __construct()
    {
        print('Constructor will have no Module Information... Use __init() instead!<br />');
        print('--> '.print_r($this->module, 1).' <--');
        print('<br />');
        print('<br />');
        $this->test = '123';
    }

    function __init()
    {
        print('Using of __init()!<br />');
        print('--> '.print_r($this->module, 1).' <--');
        print('<br />');
        print('<br />');
    }

    function testFunction($test = false)
    {
        if ($test != false)
            $this->test = $test;
    }
}
echo('<pre>');
$wow = new Caller('Config', 'Guestbook');
print_r($wow->test);
print('<br />');
print('<br />');
$wow->test = '456';
print_r($wow->test);
print('<br />');
print('<br />');
$wow->testFunction('789');
print_r($wow->test);
print('<br />');
print('<br />');
print_r($wow->module);
echo('</pre>');
?>
Outputs something Like:
Constructor will have no Module Information... Use __init() instead!
-->  <--
Using of __init()!
--> Guestbook <--
123
456
789
Guestbook`

[up](https://www.php.net/manual/vote-note.php?id=55806&page=language.oop5.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=55806&page=language.oop5.magic&vote=down "Vote down!")

3


[**_jeffxlevy at gmail dot com_**](https://www.php.net/manual/en/language.oop5.magic.php#55806) [¶](https://www.php.net/manual/en/language.oop5.magic.php#55806)

**20 years ago**

`Intriguing what happens when __sleep() and __wakeup() and sessions() are mixed. I had a hunch that, as session data is serialized, __sleep would be called when an object, or whatever, is stored in _SESSION. true. The same hunch applied when session_start() was called. Would __wakeup() be called? True. Very helpful, specifically as I'm building massive objects (well, lots of simple objects stored in sessions), and need lots of automated tasks (potentially) reloaded at "wakeup" time. (for instance, restarting a database session/connection).`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.oop5.magic&repo=en&redirect=https://www.php.net/manual/en/language.oop5.magic.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google