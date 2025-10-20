---
url: https://www.php.net/manual/en/function.func-num-args.php
scraped_at: 2025-10-20T02:33:38.447Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# func\_num\_args

(PHP 4, PHP 5, PHP 7, PHP 8)

func\_num\_args — Returns the number of arguments passed to the function

### Description [¶](https://www.php.net/manual/en/function.func-num-args.php\#refsect1-function.func-num-args-description)

**func\_num\_args**(): [int](https://www.php.net/manual/en/language.types.integer.php)

Gets the number of arguments passed to the function.


This function may be used in conjunction with
[func\_get\_arg()](https://www.php.net/manual/en/function.func-get-arg.php) and [func\_get\_args()](https://www.php.net/manual/en/function.func-get-args.php)
to allow user-defined functions to accept variable-length argument lists.


### Parameters [¶](https://www.php.net/manual/en/function.func-num-args.php\#refsect1-function.func-num-args-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/function.func-num-args.php\#refsect1-function.func-num-args-returnvalues)

Returns the number of arguments passed into the current user-defined
function.


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.func-num-args.php\#refsect1-function.func-num-args-errors)

Generates a warning if called from outside of a user-defined function.


### Examples [¶](https://www.php.net/manual/en/function.func-num-args.php\#refsect1-function.func-num-args-examples)

**Example #1 **func\_num\_args()** example**

`<?php
function foo()
{
    echo "Number of arguments: ", func_num_args(), PHP_EOL;
}
foo(1, 2, 3);
?>`

The above example will output:

```
Number of arguments: 3
```

### Notes [¶](https://www.php.net/manual/en/function.func-num-args.php\#refsect1-function.func-num-args-notes)

> **Note**:
>
> As of PHP 8.0.0, the func\_\*() family of
> functions is intended to be mostly transparent with regard to named arguments,
> by treating the arguments as if they were all passed positionally,
> and missing arguments are replaced with their defaults.
> This function ignores the collection of unknown named variadic arguments.
> Unknown named arguments which are collected can only be accessed through the variadic parameter.

### See Also [¶](https://www.php.net/manual/en/function.func-num-args.php\#refsect1-function.func-num-args-seealso)

- [`...` syntax](https://www.php.net/manual/en/functions.arguments.php#functions.variable-arg-list)
- [func\_get\_arg()](https://www.php.net/manual/en/function.func-get-arg.php) \- Return an item from the argument list
- [func\_get\_args()](https://www.php.net/manual/en/function.func-get-args.php) \- Returns an array comprising a function's argument list
- [ReflectionFunctionAbstract::getNumberOfParameters()](https://www.php.net/manual/en/reflectionfunctionabstract.getnumberofparameters.php) \- Gets number of parameters

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/funchand/functions/func-num-args.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.func-num-args%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.func-num-args&repo=en&redirect=https://www.php.net/manual/en/function.func-num-args.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=56534&page=function.func-num-args&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56534&page=function.func-num-args&vote=down "Vote down!")

41


[**_jared at ws-db dot com_**](https://www.php.net/manual/en/function.func-num-args.php#56534) [¶](https://www.php.net/manual/en/function.func-num-args.php#56534)

**20 years ago**

`Just a note for anyone wondering. This function doesn't include params that have a default value, unless you pass one in to overwrite the default param value. Not sure if that makes sense, so here's an example:
<?php
function helloWorld($ArgA, $ArgB="HelloWorld!") {
return func_num_args();
}
// The following will return 1
$Returns1 = helloWorld("HelloWorld!");
// The following will return 2
$Returns2 = helloWorld("HelloWorld!", "HowdyWorld!");
?>`

[up](https://www.php.net/manual/vote-note.php?id=91863&page=function.func-num-args&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91863&page=function.func-num-args&vote=down "Vote down!")

10


[**_Dennis Robinson from basnetworks dot net_**](https://www.php.net/manual/en/function.func-num-args.php#91863) [¶](https://www.php.net/manual/en/function.func-num-args.php#91863)

**16 years ago**

`This function comes in handy, and I believe is the only solution, when you have an optional parameter that can take any type of data.
For example:
<?php
// $data can be of any type, including null
function my_function($name, $data = null)
{
    if ($data !== null)
    {
        // Do something with $data
        // If you call my_function('something'), this WILL NOT be reached
        // If you call my_function('something', null), this WILL NOT be reached
    }
}
?>
The problem with the above function is that you will never be able to use null as the value for $data.  To fix this, use func_num_args() like so:
<?php
// $data can be of any type, including null
function my_function($name, $data = null)
{
    if (func_num_args() >= 2)
    {
        // Do something with $data
        // If you call my_function('something'), this WILL NOT be reached
        // If you call my_function('something', null), this WILL be reached
    }
}
?>
This solution works because func_num_args() reports exactly how many arguments were passed when the function was called.  It does not take into account when default argument values are used.`

[up](https://www.php.net/manual/vote-note.php?id=107883&page=function.func-num-args&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107883&page=function.func-num-args&vote=down "Vote down!")

4


[**_luisguillermo dot quevedovelez at gmail dot com_**](https://www.php.net/manual/en/function.func-num-args.php#107883) [¶](https://www.php.net/manual/en/function.func-num-args.php#107883)

**13 years ago**

`I had defined a function function_name(){ ...} as a drupal callback.
I try to get how many params where passed
I got a Error and my Site falls down
I've replaced func_get_args() instead func_num_args() and my Site was restored.
I conclude you can not use  func_num_args() in callbacks.
Hope it helps.`

[up](https://www.php.net/manual/vote-note.php?id=20315&page=function.func-num-args&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=20315&page=function.func-num-args&vote=down "Vote down!")

1


[**_thalis at NOSPAMcs dot pitt dot edu_**](https://www.php.net/manual/en/function.func-num-args.php#20315) [¶](https://www.php.net/manual/en/function.func-num-args.php#20315)

**23 years ago**

`The idea of func_get_args() is to construct functions of variable number of parameters like
<?php
function var_param_func(){
    if(func_num_args()==0){
        //do one thing
    }
    if(func_num_args()==1)
        //do another thing
        //get the args with func_get_args()
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=20815&page=function.func-num-args&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=20815&page=function.func-num-args&vote=down "Vote down!")

1


[**_ashley at dcs dot warwick dot ac dot uk_**](https://www.php.net/manual/en/function.func-num-args.php#20815) [¶](https://www.php.net/manual/en/function.func-num-args.php#20815)

**23 years ago**

`If you want to pass the parameters on intact to another function, use func_get_args and call_user_func_array (careful - this one is only available in recent PHP versions).  For example:
<?php
/* Print an HTML tag.  This accepts a variable number of arguments:
the first should be the name of the tag, followed by pairs of
arguments that describe keys and values.  The values are printed
with surrounding double quote characters.  */
function printTag() {
$numArgs = func_num_args();
if ($numArgs < 1) die("printTag given no arguments");

echo "<" . func_get_arg(0);
for ($i = 1; $i < $numArgs; $i+=2) {
    echo " " . func_get_arg($i);
    if ($i+1 < $numArgs)
      echo "=\"" . func_get_arg($i+1) . "\"";
}
echo ">";

}
/* Print an HTML tag with a newline on the end */
function printTagNL() {
$args = func_get_args();
call_user_func_array("printTag", $args);
echo "\n";
}
printTagNL("input", "type", "hidden", "name", "SORTORDER", "value", $columnNo);
?>`

[up](https://www.php.net/manual/vote-note.php?id=121253&page=function.func-num-args&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121253&page=function.func-num-args&vote=down "Vote down!")

0


[**_tongcheong77 at gmail dot com_**](https://www.php.net/manual/en/function.func-num-args.php#121253) [¶](https://www.php.net/manual/en/function.func-num-args.php#121253)

**8 years ago**

`If you are using PHP 7 and func_num_args is in your base class which you extended, you can pass your arguments with the 'spat' operator.
class Sql {
public function doGetWhere(...$args) {
$num_args = func_num_args();
      $args_list = func_get_args();
      echo '<pre>';
      var_dump($args_list);
      echo '<pre>';
}
}
class Member extends Sql {
public function getWhere(...$args) {
$this->doGetWhere(...$args);
      }
}
$member = new Member();
$member->getWhere('first_name','last_name','userlevel','email','where','email','=',$sub_email);
However, take note that if you 'new up' the 'Sql' class in your 'Member' class above, instead of extending it, you will not need to pass your arguments as a variable. Just my two cents. -Bruce tong`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.func-num-args&repo=en&redirect=https://www.php.net/manual/en/function.func-num-args.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google