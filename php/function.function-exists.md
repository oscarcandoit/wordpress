---
url: https://www.php.net/manual/en/function.function-exists.php
scraped_at: 2025-10-20T02:38:16.601Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# function\_exists

(PHP 4, PHP 5, PHP 7, PHP 8)

function\_exists — Return **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if the given function has been defined

### Description [¶](https://www.php.net/manual/en/function.function-exists.php\#refsect1-function.function-exists-description)

**function\_exists**([string](https://www.php.net/manual/en/language.types.string.php) `$function`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Checks the list of defined functions, both built-in (internal) and
user-defined, for `function`.


### Parameters [¶](https://www.php.net/manual/en/function.function-exists.php\#refsect1-function.function-exists-parameters)

`function`

The function name, as a string.


### Return Values [¶](https://www.php.net/manual/en/function.function-exists.php\#refsect1-function.function-exists-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if `function` exists and is a
function, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.


> **Note**:
>
>
> This function will return **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** for constructs, such as
> [include\_once](https://www.php.net/manual/en/function.include-once.php) and [echo](https://www.php.net/manual/en/function.echo.php).

### Examples [¶](https://www.php.net/manual/en/function.function-exists.php\#refsect1-function.function-exists-examples)

**Example #1 **function\_exists()** example**

`<?php
if (function_exists('imap_open')) {
    echo "IMAP functions are available.<br />\n";
} else {
    echo "IMAP functions are not available.<br />\n";
}
?>`

### Notes [¶](https://www.php.net/manual/en/function.function-exists.php\#refsect1-function.function-exists-notes)

> **Note**:
>
>
> A function name may exist even if the function itself is unusable due to
> configuration or compiling options (with the [image](https://www.php.net/manual/en/ref.image.php) functions being an example).

### See Also [¶](https://www.php.net/manual/en/function.function-exists.php\#refsect1-function.function-exists-seealso)

- [method\_exists()](https://www.php.net/manual/en/function.method-exists.php) \- Checks if the class method exists
- [is\_callable()](https://www.php.net/manual/en/function.is-callable.php) \- Verify that a value can be called as a function from the current scope
- [get\_defined\_functions()](https://www.php.net/manual/en/function.get-defined-functions.php) \- Returns an array of all defined functions
- [class\_exists()](https://www.php.net/manual/en/function.class-exists.php) \- Checks if the class has been defined
- [extension\_loaded()](https://www.php.net/manual/en/function.extension-loaded.php) \- Find out whether an extension is loaded

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/funchand/functions/function-exists.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.function-exists%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.function-exists&repo=en&redirect=https://www.php.net/manual/en/function.function-exists.php)

### User Contributed Notes 19 notes

[up](https://www.php.net/manual/vote-note.php?id=110163&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110163&page=function.function-exists&vote=down "Vote down!")

38


[**_kitchin_**](https://www.php.net/manual/en/function.function-exists.php#110163) [¶](https://www.php.net/manual/en/function.function-exists.php#110163)

**13 years ago**

`You can use this function to conditionally define functions, see: [http://php.net/manual/en/functions.user-defined.php](http://php.net/manual/en/functions.user-defined.php)
For instance Wordpress uses it to make functions "pluggable." If a plugin has already defined a pluggable function, then the WP code knows not to try to redefine it.
But function_exists() will always return true unless you wrap any later function definition in a conditional clause, like if(){...}. This is a subtle matter in PHP parsing. Some examples:
<?php
if (function_exists('foo')) {
print "foo defined\\n";
} else {
print "foo not defined\\n";
}
function foo() {}
if (function_exists('bar')) {
print "bar defined\\n";
} else {
print "defining bar\\n";
function bar() {}
}
print "calling bar\\n";
bar(); // ok to call function conditionally defined earlier
print "calling baz\\n";
baz(); // ok to call function unconditionally defined later
function baz() {}
qux(); // NOT ok to call function conditionally defined later
if (!function_exists('qux')) {
function qux() {}
}
?>
Prints:
foo defined
defining bar
calling bar
calling baz
PHP Fatal error: Call to undefined function qux()
Any oddities are probably due to the order in which you include/require files.`

[up](https://www.php.net/manual/vote-note.php?id=117916&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117916&page=function.function-exists&vote=down "Vote down!")

29


[**_michael at squiloople dot com_**](https://www.php.net/manual/en/function.function-exists.php#117916) [¶](https://www.php.net/manual/en/function.function-exists.php#117916)

**10 years ago**

`It should be noted that the function_exists check is not relative to the root namespace. This means that the namespace should be appended to the check:
<?php
namespace test;
if (!function_exists(__NAMESPACE__ . '\example'))
{
    function example()
    {
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=126308&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126308&page=function.function-exists&vote=down "Vote down!")

5


[**_chris at candm dot org dot uk_**](https://www.php.net/manual/en/function.function-exists.php#126308) [¶](https://www.php.net/manual/en/function.function-exists.php#126308)

**4 years ago**

`The confusion expressed in some of the submissions here arise because functions declared outside conditional blocks are defined as the code is loaded and are thus callable and exist wherever in the code they are declared, whereas those declared inside a condition block are not defined until that block is executed. Thus:
    echo foo();
    function foo() { return "I am foo"; }
yields : "I am foo"
however because those inside a conditional are defined as they are encountered during code execution
    echo foo();
    if(true) {
        function foo() { return "I am foo"; }
    }
yields: Fatal error: Uncaught Error: Call to undefined function foo()`

[up](https://www.php.net/manual/vote-note.php?id=119092&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119092&page=function.function-exists&vote=down "Vote down!")

9


[**_ayyappan dot ashok at gmail dot com_**](https://www.php.net/manual/en/function.function-exists.php#119092) [¶](https://www.php.net/manual/en/function.function-exists.php#119092)

**9 years ago**

`PHP supports nested function based on certain criteria.
Please look over the code.
function Media(){ }
function Audio()
{
    echo "Plugged Audo 5.1:<br/>";
    function Volume()
    {
    echo "Volume controls:<br/>";
    function Equalizer()
    {
        echo "Equalize Bands:<br/>";
    }
}
}
//Call to nested functions
Audio();
Volume();
Equalizer();
if(function_exists('Volume')):
echo "TRUE";
else:
echo "FALSE";
endif;
Case 1:  //Result :Works Well
--------
Audio();
Volume();
Equalizer();
Case 2:  //Results Notice Error. Root function Audio must be called first.
--------
Volume();
Case 3:  //Results Error. Root function Volume must be called.
--------
Audio();
Equalizer();
Note :
The nested function should be called based on their order used.
In our example when Audio is not called and instantly when we try to call Volume puts under error.
Even though there is an possibility to use nested functions in PHP. It looks overhead to do so. Better to avoid in logical ground of script.
Tested on PHP 5.5.32`

[up](https://www.php.net/manual/vote-note.php?id=67947&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=67947&page=function.function-exists&vote=down "Vote down!")

8


[**_andi at splitbrain dot org_**](https://www.php.net/manual/en/function.function-exists.php#67947) [¶](https://www.php.net/manual/en/function.function-exists.php#67947)

**19 years ago**

`function_exists will return false for functions disabled with the disable_functions ini directive. However those functions are still declared so trying to define them yourself will fail.
<?php
if(!function_exists('readfile')){
function readfile($file){
    $handle=@fopen($cache,"r");
    echo @fread($handle,filesize($file));
    @fclose($handle);
}
}
?>
The above will issue a "Cannot redeclare readfile()" fatal error if readfile was disabled with disable_functions.`

[up](https://www.php.net/manual/vote-note.php?id=53663&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=53663&page=function.function-exists&vote=down "Vote down!")

4


[**_fili at fili dot nl_**](https://www.php.net/manual/en/function.function-exists.php#53663) [¶](https://www.php.net/manual/en/function.function-exists.php#53663)

**20 years ago**

`To prevent direct calls to included files i use the following technique.
In the main file create an empty function with a random name. Like so:
<?php
function hjudejdjiwe() { return true; }
?>
Then check for the existence of this function within your include:
<?php
if (!function_exists('hjudejdjiwe')) { die('!'); }
?>
Simple but effective.`

[up](https://www.php.net/manual/vote-note.php?id=117858&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117858&page=function.function-exists&vote=down "Vote down!")

3


[**_BruceB_**](https://www.php.net/manual/en/function.function-exists.php#117858) [¶](https://www.php.net/manual/en/function.function-exists.php#117858)

**10 years ago**

`This is not going to go down as you might expect it should (even if you play smart and require/include_once):
<?php
if(function_exists('my_function'))
{
throw new Exception("'my_function' is already defined!");
}
function my_function()
{
// Do the work here
}
?>
This, however does work:
<?php
if( ! function_exists('my_function'))
{
function my_function()
{
      // Do the work here
}
}
else
{
throw new Exception("'my_function' is already defined!");
}
?>
Does it have anything to do with PHP parse/execute phases or global/local scope or those curly brackets or something else, I have no idea, but the latter ugly son works, while the former bombs out claiming that 'my_function' is already defined.
Thought this might save someone a few minutes of debugging time...`

[up](https://www.php.net/manual/vote-note.php?id=77980&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77980&page=function.function-exists&vote=down "Vote down!")

1


[**_webmaster at mamo-net dot de_**](https://www.php.net/manual/en/function.function-exists.php#77980) [¶](https://www.php.net/manual/en/function.function-exists.php#77980)

**18 years ago**

`If you use suhosin.executor.func.blacklist instead of disabled_functions in your php.ini, function_exists will return true for a disabled function. I used this to have the same beahviour with suhosin.executor.func.blacklist and disabled_functions:
<?php
function suhosin_function_exists($func) {
    if (extension_loaded('suhosin')) {
        $suhosin = @ini_get("suhosin.executor.func.blacklist");
        if (empty($suhosin) == false) {
            $suhosin = explode(',', $suhosin);
            $suhosin = array_map('trim', $suhosin);
            $suhosin = array_map('strtolower', $suhosin);
            return (function_exists($func) == true && array_search($func, $suhosin) === false);
        }
    }
    return function_exists($func);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=108018&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=108018&page=function.function-exists&vote=down "Vote down!")

0


[**_admin at gk-root dot com_**](https://www.php.net/manual/en/function.function-exists.php#108018) [¶](https://www.php.net/manual/en/function.function-exists.php#108018)

**13 years ago**

`// If you want to chack if the function is enabled or disable in php.ini you can use this function:
<?php
function func_enabled($func) {
    $disabled = explode(',', ini_get('disable_functions'));
    foreach ($disabled as $disableFunction) {
        $is_disabled[] = trim($disableFunction);
    }
    if (in_array($func,$is_disabled)) {
        $it_is_disabled["m"] = $func.'() has been disabled for security reasons in php.ini';
        $it_is_disabled["s"] = 0;
    } else {
        $it_is_disabled["m"] = $func.'() is allow to use';
        $it_is_disabled["s"] = 1;
    }
    return $it_is_disabled;
}
?>
// An example of how to use:
<?php
$if_is_disabled = func_enabled('exec'); // return Arrey
echo $if_is_disabled["m"]; // return text value
echo '<br/>';
echo $if_is_disabled["s"]; // return 1 or 0
?>`

[up](https://www.php.net/manual/vote-note.php?id=68186&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=68186&page=function.function-exists&vote=down "Vote down!")

0


[**_Dan_**](https://www.php.net/manual/en/function.function-exists.php#68186) [¶](https://www.php.net/manual/en/function.function-exists.php#68186)

**19 years ago**

`I would like to comment on the following post:
A note of caution: function_exists() appears to be case-insensitive (at least as of PHP 4.3.8).  e.g.:
<?php
function MyCasedFunction() {
       return true;
}
// Will return true, even though casing is "wrong"
if (function_exists("mYcAsEdFuNcTiOn"))
       echo "I see it!";
?>
I believe that function calls itself are case insensitve, so this function is returning a valid truth. PHP doesn't care about cases.`

[up](https://www.php.net/manual/vote-note.php?id=40613&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=40613&page=function.function-exists&vote=down "Vote down!")

0


[**_ckrack at i-z dot de_**](https://www.php.net/manual/en/function.function-exists.php#40613) [¶](https://www.php.net/manual/en/function.function-exists.php#40613)

**21 years ago**

`i was wondering whether is_callable or function exists is faster when checking class methods.
is_callable(array('foo', 'bar'));
function_exists('foo::bar');
my results when doing each operation 10000 times with a simple test class were the following:
is_callable: 0.28671383857727 seconds
function_exists: 0.14569997787476 seconds
(following tests have proved this to be true).
thus you can see, function_exists is twice as fast as is_callable.`

[up](https://www.php.net/manual/vote-note.php?id=34517&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=34517&page=function.function-exists&vote=down "Vote down!")

 -1


[**_breadman_**](https://www.php.net/manual/en/function.function-exists.php#34517) [¶](https://www.php.net/manual/en/function.function-exists.php#34517)

**22 years ago**

`Functions within a function are better off as anonymous returns from create_function(), unless you want to be able to call it elsewhere.
However, I have used this in skinning:  I use alert_box() to display certain errors, like a faulty SQL query.  This simply calls display_alert(), which is defined in my skin scripts.  However, alert_box() is sometimes called before I know which skin to load, so it has its own functionality which it uses if function_exists('display_alert') returns false.`

[up](https://www.php.net/manual/vote-note.php?id=65974&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=65974&page=function.function-exists&vote=down "Vote down!")

 -2


[**_neelam\_ab2003 at yahoo dot co dot in_**](https://www.php.net/manual/en/function.function-exists.php#65974) [¶](https://www.php.net/manual/en/function.function-exists.php#65974)

**19 years ago**

`<?php
/*PHP doesn't Support nested functions. I have tried following in PHP_VERSION - 5.1.2*/
function A(){}
function B(){
    function C(){
        function D(){}
    }
}
IsFunctionExist('A');
IsFunctionExist('B');
IsFunctionExist('C');
IsFunctionExist('D');
function IsFunctionExist($funcName){
    echo function_exists($funcName)?" $funcName exist <br>":" $funcName doesn't exist <br>";
}
?>
/*O U T P U T
A exist
B exist
C doesn't exist
D doesn't exist
*/`

[up](https://www.php.net/manual/vote-note.php?id=43505&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=43505&page=function.function-exists&vote=down "Vote down!")

 -3


[**_bob at thethirdshift dot net_**](https://www.php.net/manual/en/function.function-exists.php#43505) [¶](https://www.php.net/manual/en/function.function-exists.php#43505)

**21 years ago**

`I, too, was wondering whether is_callable or function exists is faster when checking class methods.  So, I setup the following test:
<?php
function doTimes($start, $end)
{
    $start_time = explode (" ", $start);
    $start_time = $start_time[1] + $start_time[0];
    $end_time = explode (" ", $end);
    $end_time = $end_time[1] + $end_time[0];
    $time = $end_time - $start_time;
    return $time;
}
class test
{
      function test()
      {
          return true;
      }
}

$callableIsTrue = false;
$startIsCallable = microtime();
for($i = 0; $i < 10000; $i++)
{
      if(is_callable(array('test', 'test'))) { $callableIsTrue = true; }
}
$endIsCallable = microtime();
$existsIsTrue = false;
$startExists = microtime();
for($i = 0; $i < 10000; $i++)
{
      if(function_exists('test::test')) { $existsIsTrue = true; }
}
$endExists = microtime();
$timeIsCallable = doTimes($startIsCallable, $endIsCallable);
$timeExists     = doTimes($startExists, $endExists);
echo "<b>is_callable = ".($callableIsTrue ? "TRUE" : "FALSE")."</b>, \n";
echo "<b>function_exists = ".($existsIsTrue ? "TRUE" : "FALSE")."</b><br>\n";
echo "<br>Did 10000 is_callables in ".$timeIsCallable." seconds";
echo "<br>Did 10000 function_exists in ".$timeExists." seconds";
?>
This gives the output :
is_callable = TRUE, function_exists = FALSE
Did 10000 is_callables in 0.0640790462494 seconds
Did 10000 function_exists in 0.0304429531097 seconds
So the fact that function_exists is twice as fast is slightly over shadowed by the fact that it doesn't work on class methods, at least not as far as I can tell.`

[up](https://www.php.net/manual/vote-note.php?id=33827&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=33827&page=function.function-exists&vote=down "Vote down!")

 -2


[**_dshearin at excite dot com_**](https://www.php.net/manual/en/function.function-exists.php#33827) [¶](https://www.php.net/manual/en/function.function-exists.php#33827)

**22 years ago**

`This can be used to conditionally define a user function. In this sense, it can act as a sort of inline include_once().
For example, suppose you have a function A that calls function B. B is only used inside function A and is never called from anywhere else in the script. It's logical (and perfectly legal in PHP) to define B inside of A's definition, like so:
<?php
function A($inputArray)
{
if (!function_exists('B'))
{
      function B($item)
      {
           // Do something with $item
         // and return result
          return $result;
      }
}
foreach ($inputArray as $nextItem) $outputArray[] = B($nextItem);
return $outputArray;
}
?>
Without the function_exists test, you would get a fatal error the second time you called A, as PHP would think you were trying to redefine B (not legal in PHP). The placement of the test is also important. Since the if block is executed sequentially, like any other block of code, it must come before any call to the function defined within.`

[up](https://www.php.net/manual/vote-note.php?id=72713&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72713&page=function.function-exists&vote=down "Vote down!")

 -4


[**_brooklynphil at hotmail dot com_**](https://www.php.net/manual/en/function.function-exists.php#72713) [¶](https://www.php.net/manual/en/function.function-exists.php#72713)

**18 years ago**

`to bob at thethirdshift dot net
regarding is_callable vs function_exists.
using your code
is_callable = TRUE, function_exists = FALSE
Did 10000 is_callables in 0.0443360805511 seconds
Did 10000 function_exists in 0.0111110210419 seconds
then we replace
is_callable(array('test','test'));
with
$callarray = array('test','test'); // place this outside for-loop
is_callable($callarray);
is_callable = TRUE, function_exists = FALSE
Did 10000 is_callables in 0.0314660072327 seconds
Did 10000 function_exists in 0.0120670795441 seconds
then we replace
is_callable(array('test','test'));
with
is_callable('test','test');
is_callable = TRUE, function_exists = FALSE
Did 10000 is_callables in 0.00991606712341 seconds
Did 10000 function_exists in 0.0113790035248 seconds
I hope you can see that loop-testing functions is not so simple. :)`

[up](https://www.php.net/manual/vote-note.php?id=81921&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81921&page=function.function-exists&vote=down "Vote down!")

 -5


[**_php at fluidthoughts dot com_**](https://www.php.net/manual/en/function.function-exists.php#81921) [¶](https://www.php.net/manual/en/function.function-exists.php#81921)

**17 years ago**

`function_exists returns false on NULL and empty string:
<?php
        if (function_exists('')) {
                echo "empty string function exists\n";
        }
        if (function_exists(NULL)) {
                echo "NULL function exists\n";
        }
?>
Neither of the echo statements happen when I run this.`

[up](https://www.php.net/manual/vote-note.php?id=77803&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77803&page=function.function-exists&vote=down "Vote down!")

 -5


[**_White-Gandalf_**](https://www.php.net/manual/en/function.function-exists.php#77803) [¶](https://www.php.net/manual/en/function.function-exists.php#77803)

**18 years ago**

`I stumbled over the same problem as "eddiec" (users not able or not willing to use "_once"-suffixes).
A possible alternative explanation for the behavior:
If a file is included, it is possibly parsed every include-time.(?)
While parsing, every function in global scope is tried to register. THIS gets wrong, when multiple times included, and it produces an error.
If functions are defined within block scopes, their registration seems to be delayed until execution of such a block. Thus, not the function "function_exists" functions wrong, but simply the philosophy of the interpreter produces such results.
Thus, the same effect can be achieved by simply putting block braces around the contents of an include_once file:
if (function_exists('function_in_question')) return;
{
    function function_in_question(...)
    {
        ...
    }
    ...other stuff
}
...which is equivalent to...
if (!function_exists('function_in_question'))
{
    function function_in_question(...)
    {
        ...
    }
    ...other stuff
}`

[up](https://www.php.net/manual/vote-note.php?id=114322&page=function.function-exists&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114322&page=function.function-exists&vote=down "Vote down!")

 -4


[**_b dot g dot dariush at gmail dot com_**](https://www.php.net/manual/en/function.function-exists.php#114322) [¶](https://www.php.net/manual/en/function.function-exists.php#114322)

**11 years ago**

`function_exists() does not cache its query internally.
by executing the following code
        $funcs = \array_shift(\get_defined_functions());
        $l = new \core\utiles\loadTime;
        $times = 0;
        $l->start();
        for($index = 0; $index<count($funcs); $index++)
        {
            foreach($funcs as $func)
            {
                $times++;
                if(\function_exists($func)) ;
            }
        }
        $s = $l->stop();
        echo "<span style='color:green'>$times</span> took : $s";
        # the output would be
         $> 2365444 took : 0.70324
By executing the
        $funcs = \array_shift(\get_defined_functions());
        $l = new \core\utiles\loadTime;
        $times = 0;
        $l->start();
        static $func_check = array();
        for($index = 0; $index<count($funcs); $index++)
        {
            foreach($funcs as $func)
            {
                $times++;
                if(!isset($func_check[$func]))
                {
                    if(\function_exists($func)) ;
                    $func_check[$func] = 1;
                }
                else $func_check[$func];
            }
        }
        $s = $l->stop();
        echo "<span style='color:green'>$times</span> took : $s";
        # the output would be
        $> 2365444 took : 0.53446
There is a 0.16878 seconds improvement, when you use static array to cache methods existence.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.function-exists&repo=en&redirect=https://www.php.net/manual/en/function.function-exists.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google