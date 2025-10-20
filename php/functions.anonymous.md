---
url: https://www.php.net/manual/en/functions.anonymous.php
scraped_at: 2025-10-20T02:35:56.552Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Anonymous functions [¶](https://www.php.net/manual/en/functions.anonymous.php\#functions.anonymous)

Anonymous functions, also known as `closures`, allow the
creation of functions which have no specified name. They are most useful as
the value of [callable](https://www.php.net/manual/en/language.types.callable.php)
parameters, but they have many other uses.


Anonymous functions are implemented using the [Closure](https://www.php.net/manual/en/class.closure.php) class.


**Example #1 Anonymous function example**

`<?php
echo preg_replace_callback('~-([a-z])~', function ($match) {
    return strtoupper($match[1]);
}, 'hello-world');
// outputs helloWorld
?>`

Closures can also be used as the values of variables; PHP automatically
converts such expressions into instances of the
[Closure](https://www.php.net/manual/en/class.closure.php) internal class. Assigning a closure to a
variable uses the same syntax as any other assignment, including the
trailing semicolon:


**Example #2 Anonymous function variable assignment example**

`<?php
$greet = function($name) {
    printf("Hello %s\r\n", $name);
};
$greet('World');
$greet('PHP');
?>`

Closures may also inherit variables from the parent scope. Any such
variables must be passed to the `use` language construct.
As of PHP 7.1, these variables must not include [superglobals](https://www.php.net/manual/en/language.variables.predefined.php),
$this, or variables with the same name as a parameter.
A return type declaration of the function has to be placed
_after_ the `use` clause.


**Example #3 Inheriting variables from the parent scope**

`<?php
$message = 'hello';
// No "use"
$example = function () {
    var_dump($message);
};
$example();
// Inherit $message
$example = function () use ($message) {
    var_dump($message);
};
$example();
// Inherited variable's value is from when the function
// is defined, not when called
$message = 'world';
$example();
// Reset message
$message = 'hello';
// Inherit by-reference
$example = function () use (&$message) {
    var_dump($message);
};
$example();
// The changed value in the parent scope
// is reflected inside the function call
$message = 'world';
$example();
// Closures can also accept regular arguments
$example = function ($arg) use ($message) {
    var_dump($arg . ' ' . $message);
};
$example("hello");
// Return type declaration comes after the use clause
$example = function () use ($message): string {
    return "hello $message";
};
var_dump($example());
?>`

The above example will output
something similar to:

```
Notice: Undefined variable: message in /example.php on line 6
NULL
string(5) "hello"
string(5) "hello"
string(5) "hello"
string(5) "world"
string(11) "hello world"
string(11) "hello world"

```

As of PHP 8.0.0, the list of scope-inherited variables may include a trailing
comma, which will be ignored.


Inheriting variables from the parent scope is _not_
the same as using global variables.
Global variables exist in the global scope, which is the same no
matter what function is executing. The parent scope of a closure is the
function in which the closure was declared (not necessarily the function it
was called from). See the following example:


**Example #4 Closures and scoping**

`<?php
// A basic shopping cart which contains a list of added products
// and the quantity of each product. Includes a method which
// calculates the total price of the items in the cart using a
// closure as a callback.
class Cart
{
    const PRICE_BUTTER  = 1.00;
    const PRICE_MILK    = 3.00;
    const PRICE_EGGS    = 6.95;
    protected $products = array();

    public function add($product, $quantity)
    {
        $this->products[$product] = $quantity;
    }

    public function getQuantity($product)
    {
        return isset($this->products[$product]) ? $this->products[$product] :
               FALSE;
    }

    public function getTotal($tax)
    {
        $total = 0.00;

        $callback =
            function ($quantity, $product) use ($tax, &$total)
            {
                $pricePerItem = constant(__CLASS__ . "::PRICE_" .
                    strtoupper($product));
                $total += ($pricePerItem * $quantity) * ($tax + 1.0);
            };

        array_walk($this->products, $callback);
        return round($total, 2);
    }
}
$my_cart = new Cart;
// Add some items to the cart
$my_cart->add('butter', 1);
$my_cart->add('milk', 3);
$my_cart->add('eggs', 6);
// Print the total with a 5% sales tax.
print $my_cart->getTotal(0.05) . "\n";
// The result is 54.29
?>`

**Example #5 Automatic binding of `$this`**

`<?php
class Test
{
    public function testing()
    {
        return function() {
            var_dump($this);
        };
    }
}
$object = new Test;
$function = $object->testing();
$function();

?>`

The above example will output:

```
object(Test)#1 (0) {
}

```

When declared in the context of a class, the current class is
automatically bound to it, making `$this` available
inside of the function's scope. If this automatic binding of the current
class is not wanted, then
[static anonymous\\
functions](https://www.php.net/manual/en/functions.anonymous.php#functions.anonymous-functions.static) may be used instead.


### Static anonymous functions [¶](https://www.php.net/manual/en/functions.anonymous.php\#functions.anonymous-functions.static)

Anonymous functions may be declared statically. This
prevents them from having the current class automatically bound to
them. Objects may also not be bound to them at runtime.


**Example #6 Attempting to use `$this` inside a static anonymous function**

`<?php
class Foo
{
    function __construct()
    {
        $func = static function() {
            var_dump($this);
        };
        $func();
    }
};
new Foo();
?>`

The above example will output:

```
Notice: Undefined variable: this in %s on line %d
NULL

```

**Example #7 Attempting to bind an object to a static anonymous function**

`<?php
$func = static function() {
    // function body
};
$func = $func->bindTo(new stdClass);
$func();
?>`

The above example will output:

```
Warning: Cannot bind an instance to a static closure in %s on line %d

```

### Changelog

| Version | Description |
| --- | --- |
| 8.3.0 | Closures created from [magic\<br> methods](https://www.php.net/manual/en/language.oop5.magic.php) can accept named parameters. |
| 7.1.0 | Anonymous functions may not close over [superglobals](https://www.php.net/manual/en/language.variables.predefined.php),<br> $this, or any variable with the same name as a<br> parameter. |

### Notes

> **Note**:
>
> It is possible to use [func\_num\_args()](https://www.php.net/manual/en/function.func-num-args.php),
> [func\_get\_arg()](https://www.php.net/manual/en/function.func-get-arg.php), and [func\_get\_args()](https://www.php.net/manual/en/function.func-get-args.php)
> from within a closure.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/functions.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunctions.anonymous%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=functions.anonymous&repo=en&redirect=https://www.php.net/manual/en/functions.anonymous.php)

### User Contributed Notes 20 notes

[up](https://www.php.net/manual/vote-note.php?id=99287&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99287&page=functions.anonymous&vote=down "Vote down!")

336


[**_orls_**](https://www.php.net/manual/en/functions.anonymous.php#99287) [¶](https://www.php.net/manual/en/functions.anonymous.php#99287)

**15 years ago**

`Watch out when 'importing' variables to a closure's scope  -- it's easy to miss / forget that they are actually being *copied* into the closure's scope, rather than just being made available.
So you will need to explicitly pass them in by reference if your closure cares about their contents over time:
<?php
$result = 0;
$one = function()
{ var_dump($result); };
$two = function() use ($result)
{ var_dump($result); };
$three = function() use (&$result)
{ var_dump($result); };
$result++;
$one();    // outputs NULL: $result is not in scope
$two();    // outputs int(0): $result was copied
$three();    // outputs int(1)
?>
Another less trivial example with objects (what I actually tripped up on):
<?php
//set up variable in advance
$myInstance = null;
$broken = function() uses ($myInstance)
{
    if(!empty($myInstance)) $myInstance->doSomething();
};
$working = function() uses (&$myInstance)
{
    if(!empty($myInstance)) $myInstance->doSomething();
}
//$myInstance might be instantiated, might not be
if(SomeBusinessLogic::worked() == true)
{
    $myInstance = new myClass();
}
$broken();    // will never do anything: $myInstance will ALWAYS be null inside this closure.
$working();    // will call doSomething if $myInstance is instantiated
?>`

[up](https://www.php.net/manual/vote-note.php?id=117504&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117504&page=functions.anonymous&vote=down "Vote down!")

30


[**_erolmon dot kskn at gmail dot com_**](https://www.php.net/manual/en/functions.anonymous.php#117504) [¶](https://www.php.net/manual/en/functions.anonymous.php#117504)

**10 years ago**

`<?php
    /*
    (string) $name Name of the function that you will add to class.
    Usage : $Foo->add(function(){},$name);
    This will add a public function in Foo Class.
    */
    class Foo
    {
        public function add($func,$name)
        {
            $this->{$name} = $func;
        }
        public function __call($func,$arguments){
            call_user_func_array($this->{$func}, $arguments);
        }
    }
    $Foo = new Foo();
    $Foo->add(function(){
        echo "Hello World";
    },"helloWorldFunction");
    $Foo->add(function($parameterone){
        echo $parameterone;
    },"exampleFunction");
    $Foo->helloWorldFunction(); /*Output : Hello World*/
    $Foo->exampleFunction("Hello PHP"); /*Output : Hello PHP*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=113896&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113896&page=functions.anonymous&vote=down "Vote down!")

29


[**_cHao_**](https://www.php.net/manual/en/functions.anonymous.php#113896) [¶](https://www.php.net/manual/en/functions.anonymous.php#113896)

**11 years ago**

``In case you were wondering (cause i was), anonymous functions can return references just like named functions can.  Simply use the & the same way you would for a named function...right after the `function` keyword (and right before the nonexistent name).
<?php
    $value = 0;
    $fn = function &() use (&$value) { return $value; };
    $x =& $fn();
    var_dump($x, $value);        // 'int(0)', 'int(0)'
    ++$x;
    var_dump($x, $value);        // 'int(1)', 'int(1)'``

[up](https://www.php.net/manual/vote-note.php?id=121034&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121034&page=functions.anonymous&vote=down "Vote down!")

12


[**_ayon at hyurl dot com_**](https://www.php.net/manual/en/functions.anonymous.php#121034) [¶](https://www.php.net/manual/en/functions.anonymous.php#121034)

**8 years ago**

`One way to call a anonymous function recursively is to use the USE keyword and pass a reference to the function itself:
<?php
$count = 1;
$add = function($count) use (&$add){
    $count += 1;
    if($count < 10) $count = $add($count); //recursive calling
    return $count;
};
echo $add($count); //Will output 10 as expected
?>`

[up](https://www.php.net/manual/vote-note.php?id=91610&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91610&page=functions.anonymous&vote=down "Vote down!")

15


[**_a dot schaffhirt at sedna-soft dot de_**](https://www.php.net/manual/en/functions.anonymous.php#91610) [¶](https://www.php.net/manual/en/functions.anonymous.php#91610)

**16 years ago**

`When using anonymous functions as properties in Classes, note that there are three name scopes: one for constants, one for properties and one for methods. That means, you can use the same name for a constant, for a property and for a method at a time.
Since a property can be also an anonymous function as of PHP 5.3.0, an oddity arises when they share the same name, not meaning that there would be any conflict.
Consider the following example:
<?php
    class MyClass {
        const member = 1;

        public $member;

        public function member () {
            return "method 'member'";
        }

        public function __construct () {
            $this->member = function () {
                return "anonymous function 'member'";
            };
        }
    }

    header("Content-Type: text/plain");

    $myObj = new MyClass();
    var_dump(MyClass::member);  // int(1)
    var_dump($myObj->member);   // object(Closure)#2 (0) {}
    var_dump($myObj->member()); // string(15) "method 'member'"
    $myMember = $myObj->member;
    var_dump($myMember());      // string(27) "anonymous function 'member'"
?>
That means, regular method invocations work like expected and like before. The anonymous function instead, must be retrieved into a variable first (just like a property) and can only then be invoked.
Best regards,`

[up](https://www.php.net/manual/vote-note.php?id=94804&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94804&page=functions.anonymous&vote=down "Vote down!")

10


[**_rob at ubrio dot us_**](https://www.php.net/manual/en/functions.anonymous.php#94804) [¶](https://www.php.net/manual/en/functions.anonymous.php#94804)

**15 years ago**

`You can always call protected members using the __call() method - similar to how you hack around this in Ruby using send.
<?php
class Fun
{
protected function debug($message)
{
echo "DEBUG: $message\n";
}
public function yield_something($callback)
{
return $callback("Soemthing!!");
}
public function having_fun()
{
$self =& $this;
return $this->yield_something(function($data) use (&$self)
{
     $self->debug("Doing stuff to the data");
     // do something with $data
     $self->debug("Finished doing stuff with the data.");
});
}
// Ah-Ha!
public function __call($method, $args = array())
{
if(is_callable(array($this, $method)))
     return call_user_func_array(array($this, $method), $args);
}
}
$fun = new Fun();
echo $fun->having_fun();
?>`

[up](https://www.php.net/manual/vote-note.php?id=122809&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122809&page=functions.anonymous&vote=down "Vote down!")

13


[**_dexen dot devries at gmail dot com_**](https://www.php.net/manual/en/functions.anonymous.php#122809) [¶](https://www.php.net/manual/en/functions.anonymous.php#122809)

**7 years ago**

`Every instance of a lambda has own instance of static variables. This provides for great event handlers, accumulators, etc., etc.
Creating new lambda with function() { ... }; expression creates new instance of its static variables. Assigning a lambda to a variable does not create a new instance. A lambda is object of class Closure, and assigning lambdas to variables has the same semantics as assigning object instance to variables.
Example script: $a and $b have separate instances of static variables, thus produce different output. However $b and $c share their instance of static variables - because $c is refers to the same object of class Closure as $b - thus produce the same output.
#!/usr/bin/env php
<?php
function generate_lambda() : Closure
{
        # creates new instance of lambda
    return function($v = null) {
        static $stored;
        if ($v !== null)
            $stored = $v;
        return $stored;
    };
}
$a = generate_lambda();  # creates new instance of statics
$b = generate_lambda();  # creates new instance of statics
$c = $b;                                 # uses the same instance of statics as $b
$a('test AAA');
$b('test BBB');
$c('test CCC');  # this overwrites content held by $b, because it refers to the same object
var_dump([ $a(), $b(), $c() ]);
?>
This test script outputs:
array(3) {
[0]=>
string(8) "test AAA"
[1]=>
string(8) "test CCC"
[2]=>
string(8) "test CCC"
}`

[up](https://www.php.net/manual/vote-note.php?id=114433&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114433&page=functions.anonymous&vote=down "Vote down!")

11


[**_mail at mkharitonov dot net_**](https://www.php.net/manual/en/functions.anonymous.php#114433) [¶](https://www.php.net/manual/en/functions.anonymous.php#114433)

**11 years ago**

`Some comparisons of PHP and JavaScript closures.
=== Example 1 (passing by value) ===
PHP code:
<?php
$aaa = 111;
$func = function() use($aaa){ print $aaa; };
$aaa = 222;
$func(); // Outputs "111"
?>
Similar JavaScript code:
<script type="text/javascript">
var aaa = 111;
var func = (function(aaa){ return function(){ alert(aaa); } })(aaa);
aaa = 222;
func(); // Outputs "111"
</script>
Be careful, following code is not similar to previous code:
<script type="text/javascript">
var aaa = 111;
var bbb = aaa;
var func = function(){ alert(bbb); };
aaa = 222;
func(); // Outputs "111", but only while "bbb" is not changed after function declaration
// And this technique is not working in loops:
var functions = [];
for (var i = 0; i < 2; i++)
{
    var i2 = i;
    functions.push(function(){ alert(i2); });
}
functions[0](); // Outputs "1", wrong!
functions[1](); // Outputs "1", ok
</script>
=== Example 2 (passing by reference) ===
PHP code:
<?php
$aaa = 111;
$func = function() use(&$aaa){ print $aaa; };
$aaa = 222;
$func(); // Outputs "222"
?>
Similar JavaScript code:
<script type="text/javascript">
var aaa = 111;
var func = function(){ alert(aaa); };
aaa = 222; // Outputs "222"
func();
</script>`

[up](https://www.php.net/manual/vote-note.php?id=105261&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105261&page=functions.anonymous&vote=down "Vote down!")

11


[**_simon at generalflows dot com_**](https://www.php.net/manual/en/functions.anonymous.php#105261) [¶](https://www.php.net/manual/en/functions.anonymous.php#105261)

**14 years ago**

`<?php
/*
* An example showing how to use closures to implement a Python-like decorator
* pattern.
*
* My goal was that you should be able to decorate a function with any
* other function, then call the decorated function directly:
*
* Define function:         $foo = function($a, $b, $c, ...) {...}
* Define decorator:        $decorator = function($func) {...}
* Decorate it:             $foo = $decorator($foo)
* Call it:                 $foo($a, $b, $c, ...)
*
* This example show an authentication decorator for a service, using a simple
* mock session and mock service.
*/

session_start();
/*
* Define an example decorator. A decorator function should take the form:
* $decorator = function($func) {
*     return function() use $func) {
*         // Do something, then call the decorated function when needed:
*         $args = func_get_args($func);
*         call_user_func_array($func, $args);
*         // Do something else.
*     };
* };
*/
$authorise = function($func) {
    return function() use ($func) {
        if ($_SESSION['is_authorised'] == true) {
            $args = func_get_args($func);
            call_user_func_array($func, $args);
        }
        else {
            echo "Access Denied";
        }
    };
};
/*
* Define a function to be decorated, in this example a mock service that
* need to be authorised.
*/
$service = function($foo) {
    echo "Service returns: $foo";
};
/*
* Decorate it. Ensure you replace the origin function reference with the
* decorated function; ie just $authorise($service) won't work, so do
* $service = $authorise($service)
*/
$service = $authorise($service);
/*
* Establish mock authorisation, call the service; should get
* 'Service returns: test 1'.
*/
$_SESSION['is_authorised'] = true;
$service('test 1');
/*
* Remove mock authorisation, call the service; should get 'Access Denied'.
*/
$_SESSION['is_authorised'] = false;
$service('test 2');
?>`

[up](https://www.php.net/manual/vote-note.php?id=120611&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120611&page=functions.anonymous&vote=down "Vote down!")

14


[**_john at binkmail dot com_**](https://www.php.net/manual/en/functions.anonymous.php#120611) [¶](https://www.php.net/manual/en/functions.anonymous.php#120611)

**8 years ago**

`PERFORMANCE BENCHMARK 2017!
I decided to compare a single, saved closure against constantly creating the same anonymous closure on every loop iteration. And I tried 10 million loop iterations, in PHP 7.0.14 from Dec 2016. Result:
a single saved closure kept in a variable and re-used (10000000 iterations): 1.3874590396881 seconds
new anonymous closure created each time (10000000 iterations): 2.8460240364075 seconds
In other words, over the course of 10 million iterations, creating the closure again during every iteration only added a total of "1.459 seconds" to the runtime. So that means that every creation of a new anonymous closure takes about 146 nanoseconds on my 7 years old dual-core laptop. I guess PHP keeps a cached "template" for the anonymous function and therefore doesn't need much time to create a new instance of the closure!
So you do NOT have to worry about constantly re-creating your anonymous closures over and over again in tight loops! At least not as of PHP 7! There is absolutely NO need to save an instance in a variable and re-use it. And not being restricted by that is a great thing, because it means you can feel free to use anonymous functions exactly where they matter, as opposed to defining them somewhere else in the code. :-)`

[up](https://www.php.net/manual/vote-note.php?id=122182&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122182&page=functions.anonymous&vote=down "Vote down!")

12


[**_toonitw at gmail dot com_**](https://www.php.net/manual/en/functions.anonymous.php#122182) [¶](https://www.php.net/manual/en/functions.anonymous.php#122182)

**7 years ago**

`As of PHP 7.0, you can use IIFE(Immediately-invoked function expression) by wrapping your anonymous function with ().
<?php
$type = 'number';
var_dump( ...( function() use ($type) {
    if ($type=='number') return [1,2,3];
    else if ($type=='alphabet') return ['a','b','c'];
} )() );
?>`

[up](https://www.php.net/manual/vote-note.php?id=114079&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114079&page=functions.anonymous&vote=down "Vote down!")

8


[**_derkontrollfreak+9hy5l at gmail dot com_**](https://www.php.net/manual/en/functions.anonymous.php#114079) [¶](https://www.php.net/manual/en/functions.anonymous.php#114079)

**11 years ago**

`Beware that since PHP 5.4 registering a Closure as an object property that has been instantiated in the same object scope will create a circular reference which prevents immediate object destruction:
<?php
class Test
{
    private $closure;
    public function __construct()
    {
        $this->closure = function () {
        };
    }
    public function __destruct()
    {
        echo "destructed\n";
    }
}
new Test;
echo "finished\n";
/*
* Result in PHP 5.3:
* ------------------
* destructed
* finished
*
* Result since PHP 5.4:
* ---------------------
* finished
* destructed
*/
?>
To circumvent this, you can instantiate the Closure in a static method:
<?php
public function __construct()
{
    $this->closure = self::createClosure();
}
public static function createClosure()
{
    return function () {
    };
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=123498&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123498&page=functions.anonymous&vote=down "Vote down!")

4


[**_jake dot tunaley at berkeleyit dot com_**](https://www.php.net/manual/en/functions.anonymous.php#123498) [¶](https://www.php.net/manual/en/functions.anonymous.php#123498)

**6 years ago**

`Beware of using $this in anonymous functions assigned to a static variable.
<?php
class Foo {
    public function bar() {
        static $anonymous = null;
        if ($anonymous === null) {
            // Expression is not allowed as static initializer workaround
            $anonymous = function () {
                return $this;
            };
        }
        return $anonymous();
    }
}
$a = new Foo();
$b = new Foo();
var_dump($a->bar() === $a); // True
var_dump($b->bar() === $a); // Also true
?>
In a static anonymous function, $this will be the value of whatever object instance that method was called on first.
To get the behaviour you're probably expecting, you need to pass the $this context into the function.
<?php
class Foo {
    public function bar() {
        static $anonymous = null;
        if ($anonymous === null) {
            // Expression is not allowed as static initializer workaround
            $anonymous = function (self $thisObj) {
                return $thisObj;
            };
        }
        return $anonymous($this);
    }
}
$a = new Foo();
$b = new Foo();
var_dump($a->bar() === $a); // True
var_dump($b->bar() === $a); // False
?>`

[up](https://www.php.net/manual/vote-note.php?id=97906&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=97906&page=functions.anonymous&vote=down "Vote down!")

7


[**_kdelux at gmail dot com_**](https://www.php.net/manual/en/functions.anonymous.php#97906) [¶](https://www.php.net/manual/en/functions.anonymous.php#97906)

**15 years ago**

`Here is an example of one way to define, then use the variable ( $this ) in Closure functions.  The code below explores all uses, and shows restrictions.
The most useful tool in this snippet is the requesting_class() function that will tell you which class is responsible for executing the current Closure().
Overview:
-----------------------
Successfully find calling object reference.
Successfully call $this(__invoke);
Successfully reference $$this->name;
Successfully call call_user_func(array($this, 'method'))
Failure: reference anything through $this->
Failure: $this->name = '';
Failure: $this->delfect();
<?php



    function requesting_class()
    {
        foreach(debug_backtrace(true) as $stack){
            if(isset($stack['object'])){
                return $stack['object'];
            }
        }

    }






    class Person
    {
        public $name = '';
        public $head = true;
        public $feet = true;
        public $deflected = false;

        function __invoke($p){ return $this->$p; }
        function __toString(){ return 'this'; } // test for reference

        function __construct($name){ $this->name = $name; }
        function deflect(){ $this->deflected = true; }

        public function shoot()
        { // If customAttack is defined, use that as the shoot resut.  Otherwise shoot feet
            if(is_callable($this->customAttack)){
                return call_user_func($this->customAttack);
            }

            $this->feet = false;
        }
    }
    $p = new Person('Bob');

    $p->customAttack =
                function(){

                    echo $this; // Notice: Undefined variable: this

                    #$this = new Class() // FATAL ERROR

                    // Trick to assign the variable '$this'
                    extract(array('this' => requesting_class())); // Determine what class is responsible for making the call to Closure

                    var_dump( $this  );  // Passive reference works
                    var_dump( $$this ); // Added to class:  function __toString(){ return 'this'; }

                    $name = $this('name'); // Success
                    echo $name;            // Outputs: Bob
                    echo '<br />';
                    echo $$this->name;

                    call_user_func_array(array($this, 'deflect'), array()); // SUCCESSFULLY CALLED

                    #$this->head = 0; //** FATAL ERROR: Using $this when not in object context
                    $$this->head = 0;  // Successfully sets value

                };

    print_r($p);

    $p->shoot();

    print_r($p);

    die();
?>`

[up](https://www.php.net/manual/vote-note.php?id=129516&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129516&page=functions.anonymous&vote=down "Vote down!")

0


[**_Hayley Watson_**](https://www.php.net/manual/en/functions.anonymous.php#129516) [¶](https://www.php.net/manual/en/functions.anonymous.php#129516)

**1 year ago**

`If you have a closure (or other callable) stored in an object property and you want to call it, you can use parentheses to disambiguate between it and a method call:
<?php
class Test
{
    public $callable;
    function __construct()
    {
        $this->callable = function($a) { return $a + 2; };
    }
}
$t = new Test;
echo ($t->callable)(40);
?>`

[up](https://www.php.net/manual/vote-note.php?id=128951&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128951&page=functions.anonymous&vote=down "Vote down!")

0


[**_Hayley Watson_**](https://www.php.net/manual/en/functions.anonymous.php#128951) [¶](https://www.php.net/manual/en/functions.anonymous.php#128951)

**2 years ago**

`"If this automatic binding of the current class is not wanted, then static anonymous functions may be used instead. "
The main reason why you would not want automatic binding is that as long as the Closure object created for the anonymous function exists, it retains a reference to the object that spawned it, preventing the object from being destroyed, even if the object is no longer alive anywhere else in the program, and even if the function itself doesn't use $this.
<?php
class Foo
{
    public function __construct(private string $id)
    {
        echo "Creating Foo " . $this->id, "\n";
    }
    public function gimme_function()
    {
        return function(){};
    }
    public function gimme_static_function()
    {
        return static function(){};
    }
    public function __destruct()
    {
        echo "Destroying Foo " . $this->id, "\n";
    }
}
echo "An object is destroyed as soon as its last reference is removed.\n";
$t = new Foo('Alice');
$t = new Foo('Bob'); // Causes Alice to be destroyed.
// Now destroy Bob.
unset($t);
echo "---\n";
echo "A non-static anonymous function retains a reference to the object which created it.\n";
$u = new Foo('Carol');
$ufn = $u->gimme_function();
$u = new Foo('Daisy'); // Does not cause Carol to be destroyed,
                       // because there is still a reference to
                       // it in the function held by $ufn.
unset($u); // Causes Daisy to be destroyed.
echo "---\n"; // Note that Carol hasn't been destroyed yet.
echo "A static anonymous function does not retain a reference to the object which created it.\n";
$v = new Foo('Eve');
$vfn = $v->gimme_static_function();
$v = new Foo('Farid'); // The function held by $vfn does not
                       // hold a reference to Eve, so Eve does get destroyed here.
unset($v); // Destroy Farid
echo "---\n";
// And then the program finishes, discarding any references to any objects still alive
// (specifically, Carol).
?>
Because $ufn survived to the end of the end of the program, Carol survived as well. $vfn also survived to the end of the program, but the function it contained was declared static, so didn't retain a reference to Eve.
Anonymous functions that retain references to otherwise-dead objects are therefore a potential source of memory leaks. If the function has no use for the object that spawned it, declaring it static prevents it from causing the object to outlive its usefulness.`

[up](https://www.php.net/manual/vote-note.php?id=107245&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107245&page=functions.anonymous&vote=down "Vote down!")

1


[**_mike at borft dot student dot utwente dot nl_**](https://www.php.net/manual/en/functions.anonymous.php#107245) [¶](https://www.php.net/manual/en/functions.anonymous.php#107245)

**13 years ago**

`Since it is possible to assign closures to class variables, it is a shame it is not possible to call them directly. ie. the following does not work:
<?php
class foo {
public test;
public function __construct(){
    $this->test = function($a) {
      print "$a\n";
    };
}
}
$f = new foo();
$f->test();
?>
However, it is possible using the magic __call function:
<?php
class foo {
public test;
public function __construct(){
    $this->test = function($a) {
      print "$a\n";
    };
}
public function __call($method, $args){
    if ( $this->{$method} instanceof Closure ) {
      return call_user_func_array($this->{$method},$args);
    } else {
      return parent::__call($method, $args);
    }
}
}
$f = new foo();
$f->test();
?>
it
Hope it helps someone ;)`

[up](https://www.php.net/manual/vote-note.php?id=92664&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92664&page=functions.anonymous&vote=down "Vote down!")

1


[**_Anonymous_**](https://www.php.net/manual/en/functions.anonymous.php#92664) [¶](https://www.php.net/manual/en/functions.anonymous.php#92664)

**16 years ago**

`If you want to check whether you're dealing with a closure specifically and not a string or array callback you can do this:
<?php
$isAClosure = is_callable($thing) && is_object($thing);
?>`

[up](https://www.php.net/manual/vote-note.php?id=98978&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=98978&page=functions.anonymous&vote=down "Vote down!")

 -2


[**_gabriel dot totoliciu at ddsec dot net_**](https://www.php.net/manual/en/functions.anonymous.php#98978) [¶](https://www.php.net/manual/en/functions.anonymous.php#98978)

**15 years ago**

`If you want to make a recursive closure, you will need to write this:
$some_var1="1";
$some_var2="2";
function($param1, $param2) use ($some_var1, $some_var2)
{
//some code here
call_user_func(__FUNCTION__, $other_param1, $other_param2);
//some code here
}
If you need to pass values by reference you should check out
[http://www.php.net/manual/en/function.call-user-func.php](http://www.php.net/manual/en/function.call-user-func.php)
[http://www.php.net/manual/en/function.call-user-func-array.php](http://www.php.net/manual/en/function.call-user-func-array.php)
If you're wondering if $some_var1 and $some_var2 are still visible by using the call_user_func, yes, they are available.`

[up](https://www.php.net/manual/vote-note.php?id=129679&page=functions.anonymous&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129679&page=functions.anonymous&vote=down "Vote down!")

 -1


[**_petersenc at gmail dot com_**](https://www.php.net/manual/en/functions.anonymous.php#129679) [¶](https://www.php.net/manual/en/functions.anonymous.php#129679)

**1 year ago**

`As of PHP 8.3.9 PHP doesn't allow type hinting within the use statement. Consider the following Laravel route:
Route::get('/tags/{tag}', function (string $tag) use ($posts): View {
    $tagPosts = $posts->filter(
            function (Post $post) use ($tag): bool {
                return in_array($tag, $post->tags);
            }
        );

    return view('tags.show', [\
        'posts' => $tagPosts,\
        'tag' => $tag\
    ]);
});
As you can see I can make the code more verbose in the closures by type hinting the parameters and the return type. use however doesn't allow type hinting.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=functions.anonymous&repo=en&redirect=https://www.php.net/manual/en/functions.anonymous.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google