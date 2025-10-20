---
url: https://www.php.net/manual/en/functions.variable-functions.php
scraped_at: 2025-10-20T02:31:50.654Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Variable functions [¶](https://www.php.net/manual/en/functions.variable-functions.php\#functions.variable-functions)

PHP supports the concept of variable functions. This means that if
a variable name has parentheses appended to it, PHP will look for
a function with the same name as whatever the variable evaluates
to, and will attempt to execute it. Among other things, this can
be used to implement callbacks, function tables, and so forth.


Variable functions won't work with language constructs such
as [echo](https://www.php.net/manual/en/function.echo.php), [print](https://www.php.net/manual/en/function.print.php),
[unset()](https://www.php.net/manual/en/function.unset.php), [isset()](https://www.php.net/manual/en/function.isset.php),
[empty()](https://www.php.net/manual/en/function.empty.php), [include](https://www.php.net/manual/en/function.include.php),
[require](https://www.php.net/manual/en/function.require.php) and the like. Utilize wrapper functions to make
use of any of these constructs as variable functions.


**Example #1 Variable function example**

`<?php
function foo() {
    echo "In foo()<br />\n";
}
function bar($arg = '')
{
    echo "In bar(); argument was '$arg'.<br />\n";
}
// This is a wrapper function around echo
function echoit($string)
{
    echo $string;
}
$func = 'foo';
$func();        // This calls foo()
$func = 'bar';
$func('test');  // This calls bar()
$func = 'echoit';
$func('test');  // This calls echoit()
?>`

Object methods can also be called with the variable functions syntax.


**Example #2 Variable method example**

`<?php
class Foo
{
    function Variable()
    {
        $name = 'Bar';
        $this->$name(); // This calls the Bar() method
    }

    function Bar()
    {
        echo "This is Bar";
    }
}
$foo = new Foo();
$funcname = "Variable";
$foo->$funcname();  // This calls $foo->Variable()
?>`

When calling static methods, the function call is stronger than the static property operator:


**Example #3 Variable method example with static properties**

`<?php
class Foo
{
    static $variable = 'static property';
    static function Variable()
    {
        echo 'Method Variable called';
    }
}
echo Foo::$variable; // This prints 'static property'. It does need a $variable in this scope.
$variable = "Variable";
Foo::$variable();  // This calls $foo->Variable() reading $variable in this scope.
?>`

**Example #4 Complex callables**

`<?php
class Foo
{
    static function bar()
    {
        echo "bar\n";
    }
    function baz()
    {
        echo "baz\n";
    }
}
$func = array("Foo", "bar");
$func(); // prints "bar"
$func = array(new Foo, "baz");
$func(); // prints "baz"
$func = "Foo::bar";
$func(); // prints "bar"
?>`

### See Also

- [is\_callable()](https://www.php.net/manual/en/function.is-callable.php)
- [call\_user\_func()](https://www.php.net/manual/en/function.call-user-func.php)
- [function\_exists()](https://www.php.net/manual/en/function.function-exists.php)
- [variable variables](https://www.php.net/manual/en/language.variables.variable.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/functions.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunctions.variable-functions%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=functions.variable-functions&repo=en&redirect=https://www.php.net/manual/en/functions.variable-functions.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=123706&page=functions.variable-functions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123706&page=functions.variable-functions&vote=down "Vote down!")

24


[**_niemans at pbsolo dot nl_**](https://www.php.net/manual/en/functions.variable-functions.php#123706) [¶](https://www.php.net/manual/en/functions.variable-functions.php#123706)

**6 years ago**

`While the documentation suggests that the use of a constant is similar to the use of a variable, there is an exception regarding variable functions. You cannot use a constant as the function name to call a variable function.
const DEBUGME ='func';
function func($s) { echo $s. "\n"; }
DEBUGME('abc');  // results in a syntax error
$call = DEBUGME;
$call('abc');          // does the job
But you can use a constant as an argument to a function. Here's a simple workaround when you need to call a variable constant function:
function dynamic($what, $with)
{
     $what($with);
}
dynamic(DEBUGME, 'abc');
This makes sense to me to hide API's and/or long (complicated) static calls.
Enjoy!`

[up](https://www.php.net/manual/vote-note.php?id=104641&page=functions.variable-functions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104641&page=functions.variable-functions&vote=down "Vote down!")

4


[**_Anonymous_**](https://www.php.net/manual/en/functions.variable-functions.php#104641) [¶](https://www.php.net/manual/en/functions.variable-functions.php#104641)

**14 years ago**

`$ wget [http://www.php.net/get/php\_manual\_en.tar.gz/from/a/mirror](http://www.php.net/get/php_manual_en.tar.gz/from/a/mirror)
$ grep -l "\$\.\.\." php-chunked-xhtml/function.*.html
List of functions that accept variable arguments.
<?php
array_diff_assoc()
array_diff_key()
array_diff_uassoc()
array()
array_intersect_ukey()
array_map()
array_merge()
array_merge_recursive()
array_multisort()
array_push()
array_replace()
array_replace_recursive()
array_unshift()
call_user_func()
call_user_method()
compact()
dba_open()
dba_popen()
echo()
forward_static_call()
fprintf()
fscanf()
httprequestpool_construct()
ibase_execute()
ibase_set_event_handler()
ibase_wait_event()
isset()
list()
maxdb_stmt_bind_param()
maxdb_stmt_bind_result()
mb_convert_variables()
newt_checkbox_tree_add_item()
newt_grid_h_close_stacked()
newt_grid_h_stacked()
newt_grid_v_close_stacked()
newt_grid_v_stacked()
newt_win_choice()
newt_win_entries()
newt_win_menu()
newt_win_message()
newt_win_ternary()
pack()
printf()
register_shutdown_function()
register_tick_function()
session_register()
setlocale()
sprintf()
sscanf()
unset()
var_dump()
w32api_deftype()
w32api_init_dtype()
w32api_invoke_function()
wddx_add_vars()
wddx_serialize_vars()
?>`

[up](https://www.php.net/manual/vote-note.php?id=125017&page=functions.variable-functions&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125017&page=functions.variable-functions&vote=down "Vote down!")

1


[**_rnealxp at yahoo dot com_**](https://www.php.net/manual/en/functions.variable-functions.php#125017) [¶](https://www.php.net/manual/en/functions.variable-functions.php#125017)

**5 years ago**

`<?php
/*
You might have found yourself at this php variable functions page because, like me, you wanted to pass functions
around like objects to client objects as you can in JavaScript. The issue I ran into was although
I could call a function using a variable like this " $v(); "...I could not do it like this " $obj->p() " where
'p' is a property containing the name of the method to call. Did not want to save my property off to a variable prior
to making my call: " $v = $obj->p; $v(); "; even if one finds a way, the below applies...
I credit this expanded work to this person: tatarynowicz at gmail dot com;
without them I would not have gotten here.
*/
interface iface_dynamic_members{
    //Use of this interface enables type-hinting for objects that implement it.
    public function __call($name, $args);
    public function __set($name, $value);
    public function quietly_fail():bool;
}
trait trait_has_dynamic_members{
    //Implementing these magic methods in the form of a trait, frees the client object up
    //so it can still inherit from a parent-class.
    public function __call($name, $args) {
        if (is_callable($this->$name)) {
            return call_user_func($this->$name, $args);
        }
        else {
            //Your dynamic-membered object can declare itself as willing to ignore non-existent method calls or not.
            if($this->quietly_fail()===true){
                echo 'Method does not exist, but I do not mind.';
            }else{
                echo 'Method does not exist, I consider this a bug.';
            }
        }
    }
    public function __set($name, $value) {
        $this->$name = is_callable($value) ? $value->bindTo($this, $this): $value; //Assignment using ternary operator.
    }
}
abstract class MBR_ATTR{
    //A class full of attributes that objects can take on; abstract since not to be instantiated (If I could make it "final" as well, I would).
    public static function is_a_walker(iface_dynamic_members $obj, ?string $walker_type='normal pace'){
        $obj->walker_type = $walker_type;
        $obj->walker_walk = function() {
            return "I am walking {$this->walker_type}.";
        };
    }
    public static function is_a_runner(iface_dynamic_members $obj, string $runner_type){
        $obj->runner_type = $runner_type;
        $obj->runner_run = function() {
            return "I am running {$this->runner_type}.";
        };
        self::is_a_walker($obj); //If can run, also can walk.
    }
}
class cls_partly_dynamic implements iface_dynamic_members{
    use trait_has_dynamic_members;
    public function quietly_fail():bool{
        return true;
    }
}
// Report all errors except E_NOTICE
error_reporting(E_ALL & ~E_NOTICE); //Enable all error-reporting except notices.
//----
//config runner object...
$obj_runner = new cls_partly_dynamic();
MBR_ATTR::is_a_runner($obj_runner, 'fast');
$obj_runner->runner_type = 'a bit slow';
//----
//config walker object...
$obj_walker = new cls_partly_dynamic();
MBR_ATTR::is_a_walker($obj_walker, 'slow');
$obj_walker->walker_type = 'super fast';
//----
//Do stuff...
echo 'walker in action...' . '<br>';
echo $obj_walker->walker_walk() . '<br>';
echo '<br>';
echo 'runner in action...' . '<br>';
echo $obj_runner->walker_walk() . '<br>';
echo $obj_runner->runner_run() . '<br>';
echo $obj_runner->xxx() . '<br>'; //Try calling a non-existent method.
//I would agree that the above approach/technique is not always ideal, particulary due to the loss of code-completion in your
//IDE of choice; I would tend to use this approach for dynamic-programming in response to the user dictating processing steps via a UI.
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=functions.variable-functions&repo=en&redirect=https://www.php.net/manual/en/functions.variable-functions.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google