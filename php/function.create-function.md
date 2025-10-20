---
url: https://www.php.net/manual/en/function.create-function.php
scraped_at: 2025-10-20T02:53:41.788Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# create\_function

(PHP 4 >= 4.0.1, PHP 5, PHP 7)

create\_function — Create a function dynamically by evaluating a string of code

**Warning**

This function has been
_DEPRECATED_ as of PHP 7.2.0, and _REMOVED_ as of PHP 8.0.0. Relying on this function
is highly discouraged.

### Description [¶](https://www.php.net/manual/en/function.create-function.php\#refsect1-function.create-function-description)

**create\_function**([string](https://www.php.net/manual/en/language.types.string.php) `$args`, [string](https://www.php.net/manual/en/language.types.string.php) `$code`): [string](https://www.php.net/manual/en/language.types.string.php)

Creates a function dynamically from the parameters passed, and returns a unique name for it.


**Caution**

This function internally performs an [eval()](https://www.php.net/manual/en/function.eval.php) and as such has the
same security issues as [eval()](https://www.php.net/manual/en/function.eval.php). It also has bad performance
and memory usage characteristics, because the created functions are global and
can not be freed.


A native
[anonymous function](https://www.php.net/manual/en/functions.anonymous.php) should be used instead.


### Parameters [¶](https://www.php.net/manual/en/function.create-function.php\#refsect1-function.create-function-parameters)

It is normally advisable to pass these parameters as
[single quoted](https://www.php.net/manual/en/language.types.string.php#language.types.string.syntax.single)
strings. If using [double quoted](https://www.php.net/manual/en/language.types.string.php#language.types.string.syntax.double)
strings, variable names in the code need to be escaped carefully, e.g.
`\$somevar`.


`args`

The function arguments, as a single comma-separated string.


`code`

The function code.


### Return Values [¶](https://www.php.net/manual/en/function.create-function.php\#refsect1-function.create-function-returnvalues)

Returns a unique function name as a string, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.
Note that the name contains a non-printable character ( `"\0"`),
so care should be taken when printing the name or incorporating it in any other
string.


### Examples [¶](https://www.php.net/manual/en/function.create-function.php\#refsect1-function.create-function-examples)

**Example #1**
**Creating a function dynamically, with **create\_function()****
**or anonymous functions**

You can use a dynamically created function, to (for example) create a function from
information gathered at run time. First, using **create\_function()**:


`<?php
$newfunc = create_function('$a,$b', 'return "ln($a) + ln($b) = " . log($a * $b);');
echo $newfunc(2, M_E) . "\n";
?>`

Now the same code, using an [anonymous function](https://www.php.net/manual/en/functions.anonymous.php);
note that the code and arguments are no longer contained in strings:


`<?php
$newfunc = function($a,$b) { return "ln($a) + ln($b) = " . log($a * $b); };
echo $newfunc(2, M_E) . "\n";
?>`

The above example will output:

```
ln(2) + ln(2.718281828459) = 1.6931471805599
```

**Example #2**
**Making a general processing function, with **create\_function()****
**or anonymous functions**

Another use could be to have general handler function that can apply a set
of operations to a list of parameters:


`<?php
function process($var1, $var2, $farr)
{
    foreach ($farr as $f) {
        echo $f($var1, $var2) . "\n";
    }
}
// create a bunch of math functions
$farr = array(
    create_function('$x,$y', 'return "some trig: ".(sin($x) + $x*cos($y));'),
    create_function('$x,$y', 'return "a hypotenuse: ".sqrt($x*$x + $y*$y);'),
    create_function('$a,$b', 'if ($a >=0) {return "b*a^2 = ".$b*sqrt($a);} else {return false;}'),
    create_function('$a,$b', "return \"min(b^2+a, a^2,b) = \".min(\$a*\$a+\$b,\$b*\$b+\$a);"),
    create_function('$a,$b', 'if ($a > 0 && $b != 0) {return "ln(a)/b = ".log($a)/$b; } else { return false; }')
);
echo "\nUsing the first array of dynamic functions\n";
echo "parameters: 2.3445, M_PI\n";
process(2.3445, M_PI, $farr);
// now make a bunch of string processing functions
$garr = array(
    create_function('$b,$a', 'if (strncmp($a, $b, 3) == 0) return "** \"$a\" '.
        'and \"$b\"\n** Look the same to me! (looking at the first 3 chars)";'),
    create_function('$a,$b', 'return "CRCs: " . crc32($a) . ", ".crc32($b);'),
    create_function('$a,$b', 'return "similar(a,b) = " . similar_text($a, $b, $p) . "($p%)";')
);
echo "\nUsing the second array of dynamic functions\n";
process("Twas brilling and the slithy toves", "Twas the night", $garr);
?>`

Again, here is the same code using
[anonymous functions](https://www.php.net/manual/en/functions.anonymous.php).
Note that variable names in the code no longer need to be escaped,
because they are not enclosed in a string.


`<?php
function process($var1, $var2, $farr)
{
    foreach ($farr as $f) {
        echo $f($var1, $var2) . "\n";
    }
}
// create a bunch of math functions
$farr = array(
    function($x,$y) { return "some trig: ".(sin($x) + $x*cos($y)); },
    function($x,$y) { return "a hypotenuse: ".sqrt($x*$x + $y*$y); },
    function($a,$b) { if ($a >=0) {return "b*a^2 = ".$b*sqrt($a);} else {return false;} },
    function($a,$b) { return "min(b^2+a, a^2,b) = " . min($a*$a+$b, $b*$b+$a); },
    function($a,$b) { if ($a > 0 && $b != 0) {return "ln(a)/b = ".log($a)/$b; } else { return false; } }
);
echo "\nUsing the first array of dynamic functions\n";
echo "parameters: 2.3445, M_PI\n";
process(2.3445, M_PI, $farr);
// now make a bunch of string processing functions
$garr = array(
    function($b,$a) { if (strncmp($a, $b, 3) == 0) return "** \"$a\" " .
        "and \"$b\"\n** Look the same to me! (looking at the first 3 chars)"; },
    function($a,$b) { return "CRCs: " . crc32($a) . ", ".crc32($b); },
    function($a,$b) { return "similar(a,b) = " . similar_text($a, $b, $p) . "($p%)"; }
);
echo "\nUsing the second array of dynamic functions\n";
process("Twas brilling and the slithy toves", "Twas the night", $garr);
?>`

The above example will output:

```
Using the first array of dynamic functions
parameters: 2.3445, M_PI
some trig: -1.6291725057799
a hypotenuse: 3.9199852871011
b*a^2 = 4.8103313314525
min(b^2+a, a^2,b) = 8.6382729035898
ln(a)/b = 0.27122299212594

Using the second array of dynamic functions
** "Twas the night" and "Twas brilling and the slithy toves"
** Look the same to me! (looking at the first 3 chars)
CRCs: 3569586014, 342550513
similar(a,b) = 11(45.833333333333%)
```

**Example #3 Using dynamic functions as callback functions**

Perhaps the most common use for dynamic functions
is to pass them as callbacks, for example when using
[array\_walk()](https://www.php.net/manual/en/function.array-walk.php) or [usort()](https://www.php.net/manual/en/function.usort.php).


`<?php
$av = array("the ", "a ", "that ", "this ");
array_walk($av, create_function('&$v,$k', '$v = $v . "mango";'));
print_r($av);
?>`

Converted to an [anonymous function](https://www.php.net/manual/en/functions.anonymous.php):


`<?php
$av = array("the ", "a ", "that ", "this ");
array_walk($av, function(&$v,$k) { $v = $v . "mango"; });
print_r($av);
?>`

The above example will output:

```
Array
(
  [0] => the mango
  [1] => a mango
  [2] => that mango
  [3] => this mango
)
```

Sorting strings from longest to shortest with **create\_function()**:


`<?php
$sv = array("small", "a big string", "larger", "it is a string thing");
echo "Original:\n";
print_r($sv);
echo "Sorted:\n";
usort($sv, create_function('$a,$b','return strlen($b) - strlen($a);'));
print_r($sv);
?>`

Converted to an [anonymous function](https://www.php.net/manual/en/functions.anonymous.php):


`<?php
$sv = array("small", "a big string", "larger", "it is a string thing");
echo "Original:\n";
print_r($sv);
echo "Sorted:\n";
usort($sv, function($a,$b) { return strlen($b) - strlen($a); });
print_r($sv);
?>`

The above example will output:

```
Original:
Array
(
  [0] => small
  [1] => a big string
  [2] => larger
  [3] => it is a string thing
)
Sorted:
Array
(
  [0] => it is a string thing
  [1] => a big string
  [2] => larger
  [3] => small
)
```

### See Also [¶](https://www.php.net/manual/en/function.create-function.php\#refsect1-function.create-function-seealso)

- [Anonymous functions](https://www.php.net/manual/en/functions.anonymous.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/funchand/functions/create-function.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.create-function%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.create-function&repo=en&redirect=https://www.php.net/manual/en/function.create-function.php)

### User Contributed Notes 22 notes

[up](https://www.php.net/manual/vote-note.php?id=123214&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123214&page=function.create-function&vote=down "Vote down!")

22


[**_tamagochi\_man_**](https://www.php.net/manual/en/function.create-function.php#123214) [¶](https://www.php.net/manual/en/function.create-function.php#123214)

**7 years ago**

`Whilst it was correct 11 years ago, the statement of Dan D is not so correct any moreю Anonymous functions are now objects of a class Closure and are safely collected by garbage collector.`

[up](https://www.php.net/manual/vote-note.php?id=70691&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70691&page=function.create-function&vote=down "Vote down!")

13


[**_Dan D_**](https://www.php.net/manual/en/function.create-function.php#70691) [¶](https://www.php.net/manual/en/function.create-function.php#70691)

**18 years ago**

`Beware when using anonymous functions in PHP as you would in languages like Python, Ruby, Lisp or Javascript.  As was stated previously, the allocated memory is never released; they are not objects in PHP -- they are just dynamically named global functions -- so they don't have scope and are not subject to garbage collection.
So, if you're developing anything remotely reusable (OO or otherwise), I would avoid them like the plague.  They're slow, inefficient and there's no telling if your implementation will end up in a large loop.  Mine ended up in an iteration over ~1 million records and quickly exhasted my 500MB-per-process limit.`

[up](https://www.php.net/manual/vote-note.php?id=69951&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=69951&page=function.create-function&vote=down "Vote down!")

3


[**_Josh J_**](https://www.php.net/manual/en/function.create-function.php#69951) [¶](https://www.php.net/manual/en/function.create-function.php#69951)

**19 years ago**

`In regards to the recursion issue by info at adaniels dot nl
Anon function recursion by referencing the function variable in the correct scope.
<?php
$fn2 = create_function('$a', 'echo $a; if ($a < 10) call_user_func($GLOBALS["fn2"], ++$a);');
$fn2(1);
?>`

[up](https://www.php.net/manual/vote-note.php?id=109197&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109197&page=function.create-function&vote=down "Vote down!")

3


[**_kak dot serpom dot po dot yaitsam at gmail dot com_**](https://www.php.net/manual/en/function.create-function.php#109197) [¶](https://www.php.net/manual/en/function.create-function.php#109197)

**13 years ago**

`Try this to boost performance of your scripts (increase maxCacheSize):
<?php
runkit_function_copy('create_function', 'create_function_native');
runkit_function_redefine('create_function', '$arg,$body', 'return __create_function($arg,$body);');
function __create_function($arg, $body) {
    static $cache = array();
    static $maxCacheSize = 64;
    static $sorter;
    if ($sorter === NULL) {
        $sorter = function($a, $b) {
            if ($a->hits == $b->hits) {
                return 0;
            }
            return ($a->hits < $b->hits) ? 1 : -1;
        };
    }
    $crc = crc32($arg . "\\x00" . $body);
    if (isset($cache[$crc])) {
        ++$cache[$crc][1];
        return $cache[$crc][0];
    }
    if (sizeof($cache) >= $maxCacheSize) {
        uasort($cache, $sorter);
        array_pop($cache);
    }
    $cache[$crc] = array($cb = eval('return function('.$arg.'){'.$body.'};'), 0);
    return $cb;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=74492&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74492&page=function.create-function&vote=down "Vote down!")

2


[**_kkaiser at revolution-records dot net_**](https://www.php.net/manual/en/function.create-function.php#74492) [¶](https://www.php.net/manual/en/function.create-function.php#74492)

**18 years ago**

`In the process of migrating a PHP4 codebase to PHP5, I ran into a peculiar problem. In the library, every class was derived from a generic class called 'class_container'. 'class_container' contained an array called runtime_functions and a method called class_function that was as follows:
<?php
function class_function($name,$params,$code) {
$this->runtime_functions[$name] = create_function($params,$code);
}
?>
In a subclass of class_container, there was a function that utilized class_function() to store some custom lambda functions that were self-referential:
<?php
function myfunc($name,$code) {
$this->class_function($name,'$theobj','$this=&$theobj;'.$code);
}
?>
In PHP4, this worked just fine. The idea was to write blocks of code at the subclass level, such as "echo $this->id;", then simply $MYOBJ->myfunc("go","echo $this->id;"); and later call it like $MYOBJ->runtime_functions["go"]();
It essentially worked exactly like binding anonymous functions to objects in Javascript.
Note how the "$this" keyword had to be manually redefined for the $code block to work.
In PHP5, however, you can't redeclare $this without getting a fatal error, so the code had to be updated to:
<?php
function myfunc($name,$code) {
$this->class_function($name,'$this',$code);
}
?>
Apparently create_function() allows you to set $this via a function argument, allowing you to bind anonymous functions to instantiated objects. Thought it might be useful to somebody.`

[up](https://www.php.net/manual/vote-note.php?id=65964&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=65964&page=function.create-function&vote=down "Vote down!")

2


[**_info at adaniels dot nl_**](https://www.php.net/manual/en/function.create-function.php#65964) [¶](https://www.php.net/manual/en/function.create-function.php#65964)

**19 years ago**

`Note that using __FUNCTION__ in a an anonymous function, will always result '__lambda_func'.
<?php
    $fn = create_function('', 'echo __FUNCTION__;');
    $fn();
    // Result: __lambda_func
    echo $fn;
    // Result: ºlambda_2 (the actual first character cannot be displayed)
?>
This means that a anonymous function can't be used recursively. The following code (recursively counting to 10) results in an error:
<?php
    $fn2 = create_function('$a', 'echo $a; if ($a < 10) call_user_func(__FUNCTION__, $a++);');
    $fn2(1);
    // Warning: call_user_func(__lambda_func) [function.call-user-func]: First argument is expected to be a valid callback in T:/test/test.php(21) : runtime-created function on line 1
?>`

[up](https://www.php.net/manual/vote-note.php?id=103080&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103080&page=function.create-function&vote=down "Vote down!")

1


[**_Dave H_**](https://www.php.net/manual/en/function.create-function.php#103080) [¶](https://www.php.net/manual/en/function.create-function.php#103080)

**14 years ago**

`The following function is very useful for creating an alias of a user function.
For built-in functions, it is less useful because default values are not available, so function aliases for built-in functions must have all parameters supplied, whether optional or not.
<?php
function create_function_alias($function_name, $alias_name)
{
    if(function_exists($alias_name))
        return false;
    $rf = new ReflectionFunction($function_name);
    $fproto = $alias_name.'(';
    $fcall = $function_name.'(';
    $need_comma = false;

    foreach($rf->getParameters() as $param)
    {
        if($need_comma)
        {
            $fproto .= ',';
            $fcall .= ',';
        }
        $fproto .= '$'.$param->getName();
        $fcall .= '$'.$param->getName();
        if($param->isOptional() && $param->isDefaultValueAvailable())
        {
            $val = $param->getDefaultValue();
            if(is_string($val))
                $val = "'$val'";
            $fproto .= ' = '.$val;
        }
        $need_comma = true;
    }
    $fproto .= ')';
    $fcall .= ')';
    $f = "function $fproto".PHP_EOL;
    $f .= '{return '.$fcall.';}';
    eval($f);
    return true;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=126024&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126024&page=function.create-function&vote=down "Vote down!")

0


[**_lombax85 at gmail dot com_**](https://www.php.net/manual/en/function.create-function.php#126024) [¶](https://www.php.net/manual/en/function.create-function.php#126024)

**4 years ago**

`For who *really* needs the create_function() on php8 (because of legacy code that cannot be changed easily) there is this: "composer require lombax85/create_function".`

[up](https://www.php.net/manual/vote-note.php?id=85391&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85391&page=function.create-function&vote=down "Vote down!")

0


[**_neo at nowhere dot com_**](https://www.php.net/manual/en/function.create-function.php#85391) [¶](https://www.php.net/manual/en/function.create-function.php#85391)

**17 years ago**

`In response to kkaiser at revolution-records dot net's note, even tho PHP will allow you to use
<?
$myfunc = create_function('$this', $code);
?>
You can NOT use a reference to "$this" inside of the anonymous function, as PHP will complain that you are using a reference to "$this" in a non-object context.
Currently, I have not found a work-around for this...`

[up](https://www.php.net/manual/vote-note.php?id=80904&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80904&page=function.create-function&vote=down "Vote down!")

0


[**_Rene Saarsoo_**](https://www.php.net/manual/en/function.create-function.php#80904) [¶](https://www.php.net/manual/en/function.create-function.php#80904)

**17 years ago**

`Here has been some discussion about the "memory leak" create_function() can create.
What create_function() actually does, is creating an ordinary function with name chr(0).lambda_n where n is some number:
<?php
$f = create_function('', 'return 1;');
function lambda_1() { return 2; }
$g = "lambda_1";
echo $g(); // outputs: 2
$h = chr(0)."lambda_1";
echo $h(); // outputs: 1
?>`

[up](https://www.php.net/manual/vote-note.php?id=77177&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77177&page=function.create-function&vote=down "Vote down!")

0


[**_TSE-WebDesign_**](https://www.php.net/manual/en/function.create-function.php#77177) [¶](https://www.php.net/manual/en/function.create-function.php#77177)

**18 years ago**

`Here's how to call a runtime-created function from another runtime-created function:
<?php
        $get_func = create_function('$func', 'return substr($func,1);');
        $get_value = create_function('$index','return pow($index,$index);');
        $another_func = create_function('$a', '$func="\x00"."'.$get_func($get_value).'";return $func($a);');
        echo $another_func(2); # result is 4
?>`

[up](https://www.php.net/manual/vote-note.php?id=70194&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70194&page=function.create-function&vote=down "Vote down!")

0


[**_Phlyst_**](https://www.php.net/manual/en/function.create-function.php#70194) [¶](https://www.php.net/manual/en/function.create-function.php#70194)

**19 years ago**

`In reply to info at adaniels dot nl:
You may not be able to use __FUNCTION__ in a lambda (thanks for pointing it out; I was having that problem just now), but you can use $GLOBALS to work around it if you're assigning the function to a variable. I reimplemented array_walk_recursive() in PHP4 like this:
<?php
$array_walk_recursive = create_function('&$array, $callback',
    'foreach($array as $element) {
        if(is_array($element)) {
            $funky = $GLOBALS["array_walk_recursive"];
            $funky($element, $callback);
        }
        else {
            $callback($element);
        }
    }');
?>`

[up](https://www.php.net/manual/vote-note.php?id=62577&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62577&page=function.create-function&vote=down "Vote down!")

0


[**_josh at janrain dot com_**](https://www.php.net/manual/en/function.create-function.php#62577) [¶](https://www.php.net/manual/en/function.create-function.php#62577)

**19 years ago**

`Beware! This is merely a convenience function that generates a unique name for a regular function. It is *not* a closure or even an anonymous function. It is just a regular function that gets named for you.`

[up](https://www.php.net/manual/vote-note.php?id=60913&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60913&page=function.create-function&vote=down "Vote down!")

0


[**_Joshua E Cook_**](https://www.php.net/manual/en/function.create-function.php#60913) [¶](https://www.php.net/manual/en/function.create-function.php#60913)

**19 years ago**

`Functions created by create_function() cannot return a value by reference.  The function below creates a function that can.  The arguments are the same as create_function().  Note that these arguments are passed, unmodified, to eval(), so be sure that data passed in is sanitized.
<?php
/**
* create_ref_function
* Create an anonymous (lambda-style) function
* which returns a reference
* see [http://php.net/create\_function](http://php.net/create_function)
*/
function
create_ref_function( $args, $code )
{
    static $n = 0;
    $functionName = sprintf('ref_lambda_%d',++$n);

    $declaration = sprintf('function &%s(%s) {%s}',$functionName,$args,$body);

    eval($declaration);

    return $functionName;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=40611&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=40611&page=function.create-function&vote=down "Vote down!")

0


[**_MagicalTux at FF.ST_**](https://www.php.net/manual/en/function.create-function.php#40611) [¶](https://www.php.net/manual/en/function.create-function.php#40611)

**21 years ago**

`neo at gothic-chat d0t de wrote :
Beware of memory-leaks, the garbage-collection seems to 'oversee' dynamically created functions!
Not really...
In fact, PHP can not "unassign" functions. So if you create a function, it won't be deleted until the end of the script, even if you unset the variable containing its name.
If you need to change a part of a function everytime you run a loop, think of a way to make a more general function or try using eval :) (functions are made to be re-used. If you need to run your own piece of code once, eval is much better).`

[up](https://www.php.net/manual/vote-note.php?id=30886&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=30886&page=function.create-function&vote=down "Vote down!")

0


[**_DB on music\_ml at yahoo dot com dot ar_**](https://www.php.net/manual/en/function.create-function.php#30886) [¶](https://www.php.net/manual/en/function.create-function.php#30886)

**22 years ago**

`[EDIT by danbrown AT php DOT net: Combined user-corrected post with previous (incorrect) post.]
You can't refer to a class variable from an anonymous function inside a class method using $this.  Anonymous functions don't inherit the method scope.  You'll have to do this:
<?php
class AnyClass {

var $classVar = 'some regular expression pattern';
function classMethod() {
$_anonymFunc = create_function( '$arg1, $arg2', 'if ( eregi($arg2, $arg1) ) { return true; } else { return false; } ' );
$willWork = $_anonymFunc('some string', $classVar);

}
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=113275&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113275&page=function.create-function&vote=down "Vote down!")

 -1


[**_CertaiN_**](https://www.php.net/manual/en/function.create-function.php#113275) [¶](https://www.php.net/manual/en/function.create-function.php#113275)

**12 years ago**

`Best wapper:
<?php
function create_lambda($args, $code) {
    static $func;
    if (!isset($func[$args][$code])) {
        $func[$args][$code] = create_function($args, $code);
    }
    return $func[$args][$code];
}`

[up](https://www.php.net/manual/vote-note.php?id=91949&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91949&page=function.create-function&vote=down "Vote down!")

 -1


[**_edgar at goodforall dot eu_**](https://www.php.net/manual/en/function.create-function.php#91949) [¶](https://www.php.net/manual/en/function.create-function.php#91949)

**16 years ago**

`Just a little toy I thought up, I would like to share. Creates an anonymous function, which let you use a class  as a function.
In php 5.3 there is support for real functors  (trough __invoke):
<?php
function createFunctor($className){
        $content = "
                static \$class;
                if(!\$class){
                        \$class = new $className;
                }
                return \$class->run(\$args);
        ";
        $f = create_function('$args', $content);
        return $f;
}
class test {
        public function run($args){
                print $args;
        }
}
$test = createFunctor('test');
$test('hello world');
?>`

[up](https://www.php.net/manual/vote-note.php?id=84955&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84955&page=function.create-function&vote=down "Vote down!")

 -1


[**_Alan FUNG_**](https://www.php.net/manual/en/function.create-function.php#84955) [¶](https://www.php.net/manual/en/function.create-function.php#84955)

**17 years ago**

`$f = create_function('','echo "function defined by create_function";');
$f();
result:
function defined by create_function
You may define no return in function body while you are using create_function.`

[up](https://www.php.net/manual/vote-note.php?id=60260&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60260&page=function.create-function&vote=down "Vote down!")

 -1


[**_boards at gmail dot com_**](https://www.php.net/manual/en/function.create-function.php#60260) [¶](https://www.php.net/manual/en/function.create-function.php#60260)

**19 years ago**

`If you were checking to see if a function is made properly, this would be a better way of checking:
<?php
$fnc = @create_function('$arg1,$arg2,$arg3', 'return true;');
# make that function whatever you want
if (empty($fnc)) {
die('Could not create function $fnc.');
}
# although, the follow will NOT work
if (empty(create_function('$arg', 'return $arg;'))) {
die('Could not create anonymous function.');
}
# you would get an error regarding not being able to use a
# return value in writeable context (i.e. a return value is
# a const in C, and the function empty() doesn't use a
# const void* parameter
?>`

[up](https://www.php.net/manual/vote-note.php?id=39217&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=39217&page=function.create-function&vote=down "Vote down!")

 -1


[**_neo at gothic-chat d0t de_**](https://www.php.net/manual/en/function.create-function.php#39217) [¶](https://www.php.net/manual/en/function.create-function.php#39217)

**21 years ago**

`Beware of memory-leaks, the garbage-collection seems to 'oversee' dynamically created functions!
I used a function like this to replace special characters in links with their htmlentities:
<?php
$text = preg_replace_callback (
    "/(<(frame src|a href|form action)=\")([^\"]+)(\"[^>]*>)/i",
    create_function (
        '$matches',
        'return $matches[1] . htmlentities ($matches[3]) . $matches[4];'
    ),
    $text);
?>
After 1000 calls, the process used about 5MB more than before. In my situation this boosted up the memory-size of one PHP-process up to over 100MB!
In such cases, better store the function in a global variable.`

[up](https://www.php.net/manual/vote-note.php?id=13841&page=function.create-function&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=13841&page=function.create-function&vote=down "Vote down!")

 -1


[**_x-empt\[a\_t\]ispep.cx_**](https://www.php.net/manual/en/function.create-function.php#13841) [¶](https://www.php.net/manual/en/function.create-function.php#13841)

**24 years ago**

`Create_function enables the ability to change the scope of functions.  You might have a class where it needs to define a GLOBAL function.  This is possible, like:
<?php
        class blah {
                function blah() {
                        $z=create_function('$arg1string','return "function-z-".$arg1string;');
                        $GLOBALS['z']=$z;
                }
        }
        $blah_object=new blah;
        $result=$GLOBALS['z']('Argument 1 String');
        echo $result;
?>
Making a function escape it's defined scope can be useful in many situations.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.create-function&repo=en&redirect=https://www.php.net/manual/en/function.create-function.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google