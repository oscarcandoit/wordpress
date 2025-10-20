---
url: https://www.php.net/manual/en/function.isset.php
scraped_at: 2025-10-20T02:47:56.558Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# isset

(PHP 4, PHP 5, PHP 7, PHP 8)

isset — Determine if a variable is declared and is different than **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**

### Description [¶](https://www.php.net/manual/en/function.isset.php\#refsect1-function.isset-description)

**isset**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$var`, [mixed](https://www.php.net/manual/en/language.types.mixed.php) `...$vars`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Determine if a variable is considered set,
this means if a variable is declared and is different than **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**.


If a variable has been unset with the [unset()](https://www.php.net/manual/en/function.unset.php)
function, it is no longer considered to be set.


**isset()** will return **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** when checking a
variable that has been assigned to **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**.
Also note that a null character ( `"\0"`) is not
equivalent to the PHP **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** constant.


If multiple parameters are supplied then **isset()**
will return **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** only if all of the parameters are considered set.
Evaluation goes from left to right and stops as soon as an unset
variable is encountered.


### Parameters [¶](https://www.php.net/manual/en/function.isset.php\#refsect1-function.isset-parameters)

`var`

The variable to be checked.


`vars`

Further variables.


### Return Values [¶](https://www.php.net/manual/en/function.isset.php\#refsect1-function.isset-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if `var` exists and has
any value other than **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**. **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.


### Examples [¶](https://www.php.net/manual/en/function.isset.php\#refsect1-function.isset-examples)

**Example #1 **isset()** Examples**

`<?php
$var = '';
// This will evaluate to TRUE so the text will be printed.
if (isset($var)) {
    echo "This var is set so I will print.", PHP_EOL;
}
// In the next examples we'll use var_dump to output
// the return value of isset().
$a = "test";
$b = "anothertest";
var_dump(isset($a));      // TRUE
var_dump(isset($a, $b)); // TRUE
unset ($a);
var_dump(isset($a));     // FALSE
var_dump(isset($a, $b)); // FALSE
$foo = NULL;
var_dump(isset($foo));   // FALSE
?>`

Run code

This also work for elements in arrays:


**Example #2 Example of **isset()** with array elements**

`<?php
$a = array ('test' => 1, 'hello' => NULL, 'pie' => array('a' => 'apple'));
var_dump(isset($a['test']));            // TRUE
var_dump(isset($a['foo']));             // FALSE
var_dump(isset($a['hello']));           // FALSE
// The key 'hello' equals NULL so is considered unset
// If you want to check for NULL key values then try:
var_dump(array_key_exists('hello', $a)); // TRUE
// Checking deeper array values
var_dump(isset($a['pie']['a']));        // TRUE
var_dump(isset($a['pie']['b']));        // FALSE
var_dump(isset($a['cake']['a']['b']));  // FALSE
?>`

Run code

**Example #3 **isset()** on String Offsets**

`<?php
$expected_array_got_string = 'somestring';
var_dump(isset($expected_array_got_string['some_key']));
var_dump(isset($expected_array_got_string[0]));
var_dump(isset($expected_array_got_string['0']));
var_dump(isset($expected_array_got_string[0.5]));
var_dump(isset($expected_array_got_string['0.5']));
var_dump(isset($expected_array_got_string['0 Mostel']));
?>`

Run code

The above example will output:

```
bool(false)
bool(true)
bool(true)
bool(true)
bool(false)
bool(false)
```

### Notes [¶](https://www.php.net/manual/en/function.isset.php\#refsect1-function.isset-notes)

**Warning**

**isset()** only works with variables as passing anything
else will result in a parse error. For checking if
[constants](https://www.php.net/manual/en/language.constants.php) are set use the
[defined()](https://www.php.net/manual/en/function.defined.php) function.


> **Note**: Because this is a
> language construct and not a function, it cannot be called using
> [variable functions](https://www.php.net/manual/en/functions.variable-functions.php),
> or [named arguments](https://www.php.net/manual/en/functions.arguments.php#functions.named-arguments).

> **Note**:
>
>
> When using **isset()** on inaccessible object properties,
> the [\_\_isset()](https://www.php.net/manual/en/language.oop5.overloading.php#object.isset)
> overloading method will be called, if declared.

### See Also [¶](https://www.php.net/manual/en/function.isset.php\#refsect1-function.isset-seealso)

- [empty()](https://www.php.net/manual/en/function.empty.php) \- Determine whether a variable is empty
- [\_\_isset()](https://www.php.net/manual/en/language.oop5.overloading.php#object.isset)
- [unset()](https://www.php.net/manual/en/function.unset.php) \- unset a given variable
- [defined()](https://www.php.net/manual/en/function.defined.php) \- Checks whether a constant with the given name exists
- [the type comparison tables](https://www.php.net/manual/en/types.comparisons.php)
- [array\_key\_exists()](https://www.php.net/manual/en/function.array-key-exists.php) \- Checks if the given key or index exists in the array
- [is\_null()](https://www.php.net/manual/en/function.is-null.php) \- Finds whether a variable is null
- the error control [@](https://www.php.net/manual/en/language.operators.errorcontrol.php) operator

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/functions/isset.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.isset%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.isset&repo=en&redirect=https://www.php.net/manual/en/function.isset.php)

### User Contributed Notes 17 notes

[up](https://www.php.net/manual/vote-note.php?id=119993&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119993&page=function.isset&vote=down "Vote down!")

119


[**_p\_ignorethis\_lbowers at gmail dot com_**](https://www.php.net/manual/en/function.isset.php#119993) [¶](https://www.php.net/manual/en/function.isset.php#119993)

**9 years ago**

`I, too, was dismayed to find that isset($foo) returns false if ($foo == null). Here's an (awkward) way around it.
unset($foo);
if (compact('foo') != array()) {
do_your_thing();
}
Of course, that is very non-intuitive, long, hard-to-understand, and kludgy. Better to design your code so you don't depend on the difference between an unset variable and a variable with the value null. But "better" only because PHP has made this weird development choice.
In my thinking this was a mistake in the development of PHP. The name ("isset") should describe the function and not have the desciption be "is set AND is not null". If it was done properly a programmer could very easily do (isset($var) || is_null($var)) if they wanted to check for this!
A variable set to null is a different state than a variable not set - there should be some easy way to differentiate. Just my (pointless) $0.02.`

[up](https://www.php.net/manual/vote-note.php?id=120359&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120359&page=function.isset&vote=down "Vote down!")

46


[**_kurdtpage at gmail dot com_**](https://www.php.net/manual/en/function.isset.php#120359) [¶](https://www.php.net/manual/en/function.isset.php#120359)

**8 years ago**

`The new (as of PHP7) 'null coalesce operator' allows shorthand isset. You can use it like so:
<?php
// Fetches the value of $_GET['user'] and returns 'nobody'
// if it does not exist.
$username = $_GET['user'] ?? 'nobody';
// This is equivalent to:
$username = isset($_GET['user']) ? $_GET['user'] : 'nobody';
// Coalescing can be chained: this will return the first
// defined value out of $_GET['user'], $_POST['user'], and
// 'nobody'.
$username = $_GET['user'] ?? $_POST['user'] ?? 'nobody';
?>
Quoted from [http://php.net/manual/en/migration70.new-features.php#migration70.new-features.null-coalesce-op](http://php.net/manual/en/migration70.new-features.php#migration70.new-features.null-coalesce-op)`

[up](https://www.php.net/manual/vote-note.php?id=86313&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86313&page=function.isset&vote=down "Vote down!")

43


[**_a dot schaffhirt at sedna-soft dot de_**](https://www.php.net/manual/en/function.isset.php#86313) [¶](https://www.php.net/manual/en/function.isset.php#86313)

**17 years ago**

`You can safely use isset to check properties and subproperties of objects directly. So instead of writing
    isset($abc) && isset($abc->def) && isset($abc->def->ghi)
or in a shorter form
    isset($abc, $abc->def, $abc->def->ghi)
you can just write
    isset ($abc->def->ghi)
without raising any errors, warnings or notices.
Examples
<?php
    $abc = (object) array("def" => 123);
    var_dump(isset($abc));                // bool(true)
    var_dump(isset($abc->def));           // bool(true)
    var_dump(isset($abc->def->ghi));      // bool(false)
    var_dump(isset($abc->def->ghi->jkl)); // bool(false)
    var_dump(isset($def));                // bool(false)
    var_dump(isset($def->ghi));           // bool(false)
    var_dump(isset($def->ghi->jkl));      // bool(false)
    var_dump($abc);                       // object(stdClass)#1 (1) { ["def"] => int(123) }
    var_dump($abc->def);                  // int(123)
    var_dump($abc->def->ghi);             // null / E_NOTICE: Trying to get property of non-object
    var_dump($abc->def->ghi->jkl);        // null / E_NOTICE: Trying to get property of non-object
    var_dump($def);                       // null / E_NOTICE: Trying to get property of non-object
    var_dump($def->ghi);                  // null / E_NOTICE: Trying to get property of non-object
    var_dump($def->ghi->jkl);             // null / E_NOTICE: Trying to get property of non-object
?>`

[up](https://www.php.net/manual/vote-note.php?id=51113&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=51113&page=function.isset&vote=down "Vote down!")

29


[**_yaogzhan at gmail dot com_**](https://www.php.net/manual/en/function.isset.php#51113) [¶](https://www.php.net/manual/en/function.isset.php#51113)

**20 years ago**

`If you have
<?PHP
class Foo
{
    protected $data = array('bar' => null);
    function __get($p)
    {
        if( isset($this->data[$p]) ) return $this->data[$p];
    }
}
?>
and
<?PHP
$foo = new Foo;
echo isset($foo->bar);
?>
will always echo 'false'. because the isset() accepts VARIABLES as it parameters, but in this case, $foo->bar is NOT a VARIABLE. it is a VALUE returned from the __get() method of the class Foo. thus the isset($foo->bar) expreesion will always equal 'false'.`

[up](https://www.php.net/manual/vote-note.php?id=71803&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=71803&page=function.isset&vote=down "Vote down!")

27


[**_beuc at beuc dot net_**](https://www.php.net/manual/en/function.isset.php#71803) [¶](https://www.php.net/manual/en/function.isset.php#71803)

**18 years ago**

`"empty() is the opposite of (boolean) var, except that no warning is generated when the variable is not set."
So essentially
<?php
if (isset($var) && $var)
?>
is the same as
<?php
if (!empty($var))
?>
doesn't it? :)
!empty() mimics the chk() function posted before.`

[up](https://www.php.net/manual/vote-note.php?id=119050&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119050&page=function.isset&vote=down "Vote down!")

8


[**_ayyappan dot ashok at gmail dot com_**](https://www.php.net/manual/en/function.isset.php#119050) [¶](https://www.php.net/manual/en/function.isset.php#119050)

**9 years ago**

`Return Values :
Returns TRUE if var exists and has value other than NULL, FALSE otherwise.
<?php
$a=NULL;
$b=FALSE; //The out put was TRUE.
$c=TRUE;
$d='';
$e="";
if(isset($b)):
echo "TRUE";
else:
echo "FALSE";
endif;
?>
Could any one explain me in clarity.`

[up](https://www.php.net/manual/vote-note.php?id=84765&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84765&page=function.isset&vote=down "Vote down!")

17


[**_mandos78 AT mail from google_**](https://www.php.net/manual/en/function.isset.php#84765) [¶](https://www.php.net/manual/en/function.isset.php#84765)

**17 years ago**

`Careful with this function "ifsetfor" by soapergem, passing by reference means that if, like the example $_GET['id'], the argument is an array index, it will be created in the original array (with a null value), thus causing posible trouble with the following code. At least in PHP 5.
For example:
<?php
$a = array();
print_r($a);
ifsetor($a["unsetindex"], 'default');
print_r($a);
?>
will print
Array
(
)
Array
(
    [unsetindex] =>
)
Any foreach or similar will be different before and after the call.`

[up](https://www.php.net/manual/vote-note.php?id=64442&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=64442&page=function.isset&vote=down "Vote down!")

17


[**_soywiz at php dot net_**](https://www.php.net/manual/en/function.isset.php#64442) [¶](https://www.php.net/manual/en/function.isset.php#64442)

**19 years ago**

`Sometimes you have to check if an array has some keys. To achieve it you can use "isset" like this: isset($array['key1'], $array['key2'], $array['key3'], $array['key4'])
You have to write $array all times and it is reiterative if you use same array each time.
With this simple function you can check if an array has some keys:
<?php
function isset_array() {
    if (func_num_args() < 2) return true;
    $args = func_get_args();
    $array = array_shift($args);
    if (!is_array($array)) return false;
    foreach ($args as $n) if (!isset($array[$n])) return false;
    return true;
}
?>
Use: isset_array($array, 'key1', 'key2', 'key3', 'key4')
First parameter has the array; following parameters has the keys you want to check.`

[up](https://www.php.net/manual/vote-note.php?id=121461&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121461&page=function.isset&vote=down "Vote down!")

5


[**_Hayley Watson_**](https://www.php.net/manual/en/function.isset.php#121461) [¶](https://www.php.net/manual/en/function.isset.php#121461)

**8 years ago**

`If you regard isset() as indicating whether the given variable has a value or not, and recall that NULL is intended to indicate that a value is _absent_ (as said, somewhat awkwardly, on its manual page), then its behaviour is not at all inconsistent or confusing.
It's not just to check for uninitialised variables - a lot of the time those are just due to sloppy coding. There are other ways a variable could fail to have a value (e.g., it's meant to hold the value returned from a function call but the function didn't have a value to return) where uninitialising the variable would not be an option nor even make sense (e.g., depending on what was to be done with the returned value).`

[up](https://www.php.net/manual/vote-note.php?id=103061&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103061&page=function.isset&vote=down "Vote down!")

12


[**_Cuong Huy To_**](https://www.php.net/manual/en/function.isset.php#103061) [¶](https://www.php.net/manual/en/function.isset.php#103061)

**14 years ago**

`1) Note that isset($var) doesn't distinguish the two cases when $var is undefined, or is null. Evidence is in the following code.
<?php
unset($undefined);
$null = null;
if (true === isset($undefined)){echo 'isset($undefined) === true'} else {echo 'isset($undefined) === false'); // 'isset($undefined) === false'
if (true === isset($null)){echo 'isset($null) === true'} else {echo 'isset($null) === false');              // 'isset($null)      === false'
?>
2) If you want to distinguish undefined variable with a defined variable with a null value, then use array_key_exist
<?php
unset($undefined);
$null = null;
if (true !== array_key_exists('undefined', get_defined_vars())) {echo '$undefined does not exist';} else {echo '$undefined exists';} // '$undefined does not exist'
if (true === array_key_exists('null', get_defined_vars())) {echo '$null exists';} else {echo '$null does not exist';}                // '$null exists'
?>`

[up](https://www.php.net/manual/vote-note.php?id=80032&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80032&page=function.isset&vote=down "Vote down!")

11


[**_packard\_bell\_nec at hotmail dot com_**](https://www.php.net/manual/en/function.isset.php#80032) [¶](https://www.php.net/manual/en/function.isset.php#80032)

**17 years ago**

`Note: isset() only checks variables as anything else will result in a parse error. In other words, the following will not work: isset(trim($name)).
isset() is the opposite of is_null($var) , except that no warning is generated when the variable is not set.`

[up](https://www.php.net/manual/vote-note.php?id=52743&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=52743&page=function.isset&vote=down "Vote down!")

8


[**_Andrew Penry_**](https://www.php.net/manual/en/function.isset.php#52743) [¶](https://www.php.net/manual/en/function.isset.php#52743)

**20 years ago**

`The following is an example of how to test if a variable is set, whether or not it is NULL. It makes use of the fact that an unset variable will throw an E_NOTICE error, but one initialized as NULL will not.
<?php
function var_exists($var){
    if (empty($GLOBALS['var_exists_err'])) {
        return true;
    } else {
        unset($GLOBALS['var_exists_err']);
        return false;
    }
}
function var_existsHandler($errno, $errstr, $errfile, $errline) {
$GLOBALS['var_exists_err'] = true;
}
$l = NULL;
set_error_handler("var_existsHandler", E_NOTICE);
echo (var_exists($l)) ? "True " : "False ";
echo (var_exists($k)) ? "True " : "False ";
restore_error_handler();
?>
Outputs:
True False
The problem is, the set_error_handler and restore_error_handler calls can not be inside the function, which means you need 2 extra lines of code every time you are testing. And if you have any E_NOTICE errors caused by other code between the set_error_handler and restore_error_handler they will not be dealt with properly. One solution:
<?php
function var_exists($var){
if (empty($GLOBALS['var_exists_err'])) {
       return true;
} else {
       unset($GLOBALS['var_exists_err']);
       return false;
}
}
function var_existsHandler($errno, $errstr, $errfile, $errline) {
    $filearr = file($errfile);
    if (strpos($filearr[$errline-1], 'var_exists') !== false) {
        $GLOBALS['var_exists_err'] = true;
        return true;
    } else {
        return false;
    }
}
$l = NULL;
set_error_handler("var_existsHandler", E_NOTICE);
echo (var_exists($l)) ? "True " : "False ";
echo (var_exists($k)) ? "True " : "False ";
is_null($j);
restore_error_handler();
?>
Outputs:
True False
Notice: Undefined variable: j in filename.php on line 26
This will make the handler only handle var_exists, but it adds a lot of overhead. Everytime an E_NOTICE error happens, the file it originated from will be loaded into an array.`

[up](https://www.php.net/manual/vote-note.php?id=117266&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117266&page=function.isset&vote=down "Vote down!")

2


[**_andreasonny83 at gmail dot com_**](https://www.php.net/manual/en/function.isset.php#117266) [¶](https://www.php.net/manual/en/function.isset.php#117266)

**10 years ago**

`Here is an example with multiple parameters supplied
<?php
$var = array();
$var['val1'] = 'test';
$var['val2'] = 'on';
if ( isset( $var['val1'], $var['val2'] ) && $var['val2'] === 'on' ) {
    unset( $var['val1'] );
}
print_r( $var );
?>
This will output:
Array
(
    [val2] => on
)
The following code does the same calling "isset" 2 times:
<?php
$var = array();
$var['val1'] = 'test';
$var['val2'] = 'on';
if ( isset( $var['val1'] ) && isset( $var['val2'] ) && $var['val2'] === 'on' ) {
    unset( $var['val1'] );
}
print_r( $var );
?>`

[up](https://www.php.net/manual/vote-note.php?id=128771&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128771&page=function.isset&vote=down "Vote down!")

0


[**_eckoson at gmail dot com_**](https://www.php.net/manual/en/function.isset.php#128771) [¶](https://www.php.net/manual/en/function.isset.php#128771)

**2 years ago**

`If you are annoyed by the behavior of isset() concerning null values, here is a handy function for you. its similar to array_key_exists but, its a lot more flexible and can check for multiple array keys across multiple arrays.
Not recursive!
Tested on php 8.1.6, linux
<?php
/**
* is_set
* @author DJ Eckoson
* @link @eckosongh Facebook Page
* checks whether variable names are set within the global space or they exists as an key and return if they are set (even if their values are null)
* @param string $var_name
*   name of the first variable to check
* @param array|null|string
*   optional array to check for key (if null, checks from $GLOBALS) OR
*   other variable names to check OR
*   other variable names and their associated arrays to their right (use null for global variables, optional if its the last parameter)
* check examples below
*/
function is_set(string $var_name, array|null|string ... $args): bool {
$vars[$var_name] = null;
if (array_key_exists(0, $args)) {
    if (is_array($args[0])) {
      $vars[$var_name] = $args[0];
    } elseif (is_string($args[0])) {
      goto main;
    }
    unset($args[0]);
}
main:
if ($args) {
    $args = array_reverse($args);
    $cur_array = null;
    array_walk($args, function ($value) use (&$cur_array, &$vars): void {
      if (!is_string($value)) {
        $cur_array = $value;
      } else {
        $vars[$value] = $cur_array;
      }
    });
}
foreach ($vars as $name => $array) {
    if (!array_key_exists($name, $array??$GLOBALS)) return false;
}
return true;
}
// Examples
$arr1 = range(0, 5);
$arr2 = [\
'a' => 1,\
'b' => 2,\
'c' => 'hELLO wORLD!'\
];
$gender = 'male';
$age = 12;
var_dump(is_set('age')); // true
var_dump(is_set('age', null)); // true
var_dump(is_set('age', $arr1)); // false
var_dump(is_set('age', array())); // false
var_dump(is_set('age', array('age' => 48))); // true
var_dump(is_set('age', 'arr1', null, 'b', $arr2, 0, 3, 4, $arr1, 'gender')); // true
var_dump(is_set('age', 'arr1', null, 'b', $arr2, 0, 3, 4, $arr1, 'gender', null)); // true
$c=$d=$e=$a=2;
$arr = [1,4];
var_dump(is_set('a', 'c', null, 0, 1, $arr)); // true
var_dump(is_set('a', 'c', null, 0, 4, $arr)); // false
?>
Note:
it won't work for variables declared locally inside a function;
however you can use it for checking if array keys exists inside a function`

[up](https://www.php.net/manual/vote-note.php?id=87521&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87521&page=function.isset&vote=down "Vote down!")

5


[**_Ashus_**](https://www.php.net/manual/en/function.isset.php#87521) [¶](https://www.php.net/manual/en/function.isset.php#87521)

**16 years ago**

`Note that array keys are case sensitive.
<?php
$ar['w'] = true;
var_dump(isset($ar['w']),
      isset($ar['W']));
?>
will report:
bool(true) bool(false)`

[up](https://www.php.net/manual/vote-note.php?id=101536&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101536&page=function.isset&vote=down "Vote down!")

4


[**_francois vespa_**](https://www.php.net/manual/en/function.isset.php#101536) [¶](https://www.php.net/manual/en/function.isset.php#101536)

**14 years ago**

`Now this is how to achieve the same effect (ie, having isset() returning true even if variable has been set to null) for objects and arrays
<?php
// array
$array=array('foo'=>null);
return isset($array['foo']) || array_key_exists('foo',$array)
? true : false ; // return true
return isset($array['inexistent']) || array_key_exists('inexistent',$array)
? true : false ; // return false
// static class
class bar
{
static $foo=null;
}
return isset(bar::$foo) || array_key_exists('foo',get_class_vars('bar'))
? true : false ; // return true
return isset(bar::$inexistent) || array_key_exists('inexistent',get_class_vars('bar'))
? true : false ; // return false
// object
class bar
{
    public $foo=null;
}
$bar=new bar();
return isset($bar->foo) || array_key_exists('foo',get_object_vars($bar))
? true : false ; // return true
return isset($bar->inexistent) || array_key_exists('inexistent',get_object_vars($bar))
? true : false ; // return true
// stdClass
$bar=new stdClass;
$bar->foo=null;
return isset($bar->foo) || array_key_exists('foo',get_object_vars($bar))
? true : false ; // return true
return isset($bar->inexistent) || array_key_exists('inexistent',get_object_vars($bar))
? true : false ; // return true
?>`

[up](https://www.php.net/manual/vote-note.php?id=92926&page=function.isset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92926&page=function.isset&vote=down "Vote down!")

2


[**_Anl zselgin_**](https://www.php.net/manual/en/function.isset.php#92926) [¶](https://www.php.net/manual/en/function.isset.php#92926)

**16 years ago**

`Note: Because this is a language construct and not a function, it cannot be called using variable functions.
So why it is under "Variable handling Functions". Maybe there should be some good documentation field for language constructs.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.isset&repo=en&redirect=https://www.php.net/manual/en/function.isset.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google