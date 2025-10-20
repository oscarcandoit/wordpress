---
url: https://www.php.net/manual/en/function.error-reporting.php
scraped_at: 2025-10-20T02:54:00.871Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# error\_reporting

(PHP 4, PHP 5, PHP 7, PHP 8)

error\_reporting — Sets which PHP errors are reported

### Description [¶](https://www.php.net/manual/en/function.error-reporting.php\#refsect1-function.error-reporting-description)

**error\_reporting**([?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$error_level` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [int](https://www.php.net/manual/en/language.types.integer.php)

The **error\_reporting()** function sets the
[error\_reporting](https://www.php.net/manual/en/errorfunc.configuration.php#ini.error-reporting)
directive at runtime. PHP has many levels of errors, using
this function sets that level for the duration (runtime) of
your script. If the optional `error_level` is
not set, **error\_reporting()** will just return
the current error reporting level.


### Parameters [¶](https://www.php.net/manual/en/function.error-reporting.php\#refsect1-function.error-reporting-parameters)

`error_level`

The new [error\_reporting](https://www.php.net/manual/en/errorfunc.configuration.php#ini.error-reporting)
level. It takes on either a bitmask, or named constants. Using named
constants is strongly encouraged to ensure compatibility for future
versions. As error levels are added, the range of integers increases,
so older integer-based error levels will not always behave as expected.


The available error level constants and the actual
meanings of these error levels are described in the
[predefined constants](https://www.php.net/manual/en/errorfunc.constants.php).


### Return Values [¶](https://www.php.net/manual/en/function.error-reporting.php\#refsect1-function.error-reporting-returnvalues)

Returns the [error\_reporting](https://www.php.net/manual/en/errorfunc.configuration.php#ini.error-reporting)
level, _before_ it is changed to
`error_level`.


> **Note**:
>
> The [error control](https://www.php.net/manual/en/language.operators.errorcontrol.php) `@`-operator changes the `error_level` during error handling.

### Changelog [¶](https://www.php.net/manual/en/function.error-reporting.php\#refsect1-function.error-reporting-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `error_level` is nullable now. |

### Examples [¶](https://www.php.net/manual/en/function.error-reporting.php\#refsect1-function.error-reporting-examples)

**Example #1 **error\_reporting()** examples**

`<?php
// Turn off all error reporting
error_reporting(0);
// Report simple running errors
error_reporting(E_ERROR | E_WARNING | E_PARSE);
// Reporting E_NOTICE can be good too (to report uninitialized
// variables or catch variable name misspellings ...)
error_reporting(E_ERROR | E_WARNING | E_PARSE | E_NOTICE);
// Report all errors except E_NOTICE
error_reporting(E_ALL & ~E_NOTICE);
// Report all PHP errors
error_reporting(E_ALL);
// Report all PHP errors
error_reporting(-1);
// Same as error_reporting(E_ALL);
ini_set('error_reporting', E_ALL);
?>`

### Notes [¶](https://www.php.net/manual/en/function.error-reporting.php\#refsect1-function.error-reporting-notes)

**Tip**

Passing in the value `-1` will show every possible error,
even when new levels and constants are added in future PHP versions. The
behavior is equivalent to passing **`[E\_ALL](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-all)`** constant.


### See Also [¶](https://www.php.net/manual/en/function.error-reporting.php\#refsect1-function.error-reporting-seealso)

- The [display\_errors](https://www.php.net/manual/en/errorfunc.configuration.php#ini.display-errors) directive
- The [html\_errors](https://www.php.net/manual/en/errorfunc.configuration.php#ini.html-errors) directive
- The [xmlrpc\_errors](https://www.php.net/manual/en/errorfunc.configuration.php#ini.xmlrpc-errors) directive
- The [error control](https://www.php.net/manual/en/language.operators.errorcontrol.php) operator
- [ini\_set()](https://www.php.net/manual/en/function.ini-set.php) \- Sets the value of a configuration option

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/errorfunc/functions/error-reporting.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.error-reporting%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.error-reporting&repo=en&redirect=https://www.php.net/manual/en/function.error-reporting.php)

### User Contributed Notes 28 notes

[up](https://www.php.net/manual/vote-note.php?id=85096&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85096&page=function.error-reporting&vote=down "Vote down!")

375


[**_info at hephoz dot de_**](https://www.php.net/manual/en/function.error-reporting.php#85096) [¶](https://www.php.net/manual/en/function.error-reporting.php#85096)

**17 years ago**

`If you just see a blank page instead of an error reporting and you have no server access so you can't edit php configuration files like php.ini try this:
- create a new file in which you include the faulty script:
<?php
error_reporting(E_ALL);
ini_set("display_errors", 1);
include("file_with_errors.php");
?>
- execute this file instead of the faulty script file
now errors of your faulty script should be reported.
this works fine with me. hope it solves your problem as well!`

[up](https://www.php.net/manual/vote-note.php?id=64060&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=64060&page=function.error-reporting&vote=down "Vote down!")

49


[**_dave at davidhbrown dot us_**](https://www.php.net/manual/en/function.error-reporting.php#64060) [¶](https://www.php.net/manual/en/function.error-reporting.php#64060)

**19 years ago**

`The example of E_ALL ^ E_NOTICE is a 'bit' confusing for those of us not wholly conversant with bitwise operators.
If you wish to remove notices from the current level, whatever that unknown level might be, use & ~ instead:
<?php
//....
$errorlevel=error_reporting();
error_reporting($errorlevel & ~E_NOTICE);
//...code that generates notices
error_reporting($errorlevel);
//...
?>
^ is the xor (bit flipping) operator and would actually turn notices *on* if they were previously off (in the error level on its left). It works in the example because E_ALL is guaranteed to have the bit for E_NOTICE set, so when ^ flips that bit, it is in fact turned off. & ~ (and not) will always turn off the bits specified by the right-hand parameter, whether or not they were on or off.`

[up](https://www.php.net/manual/vote-note.php?id=125674&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125674&page=function.error-reporting&vote=down "Vote down!")

7


[**_jcastromail at yahoo dot es_**](https://www.php.net/manual/en/function.error-reporting.php#125674) [¶](https://www.php.net/manual/en/function.error-reporting.php#125674)

**4 years ago**

`Under PHP 8.0, error_reporting() does not return 0 when then the code uses a @ character.
For example
<?php
$a=$array[20]; // error_reporting() returns 0 in php <8 and 4437 in PHP>=8
?>`

[up](https://www.php.net/manual/vote-note.php?id=124950&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124950&page=function.error-reporting&vote=down "Vote down!")

2


[**_&IT_**](https://www.php.net/manual/en/function.error-reporting.php#124950) [¶](https://www.php.net/manual/en/function.error-reporting.php#124950)

**5 years ago**

`error_reporting(E_ALL);
if (!ini_get('display_errors')) {
    ini_set('display_errors', '1');
}`

[up](https://www.php.net/manual/vote-note.php?id=124411&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124411&page=function.error-reporting&vote=down "Vote down!")

2


[**_lhenry at lhenry dot com_**](https://www.php.net/manual/en/function.error-reporting.php#124411) [¶](https://www.php.net/manual/en/function.error-reporting.php#124411)

**5 years ago**

`In php7,  what was generally a notice or a deprecated is now a warning : the same level of a mysql error …  unacceptable for me.
I do have dozen of old projects and I surely d'ont want to define every variable which I eventually wrote 20y ago.
So two option: let php7 degrade my expensive SSDs writing Gb/hours or implement smthing like server level monitoring ( with auto_[pre-ap]pend_file in php.ini) and turn off E_WARNING
Custom overriding the level of php errors should be super handy and flexible …`

[up](https://www.php.net/manual/vote-note.php?id=50228&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=50228&page=function.error-reporting&vote=down "Vote down!")

4


[**_vdephily at bluemetrix dot com_**](https://www.php.net/manual/en/function.error-reporting.php#50228) [¶](https://www.php.net/manual/en/function.error-reporting.php#50228)

**20 years ago**

`Note that E_NOTICE will warn you about uninitialized variables, but assigning a key/value pair counts as initialization, and will not trigger any error :
<?php
error_reporting(E_ALL);
$foo = $bar; //notice : $bar uninitialized
$bar['foo'] = 'hello'; // no notice, although $bar itself has never been initialized (with "$bar = array()" for example)
$bar = array('foobar' => 'barfoo');
$foo = $bar['foobar'] // ok
$foo = $bar['nope'] // notice : no such index
?>`

[up](https://www.php.net/manual/vote-note.php?id=89829&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=89829&page=function.error-reporting&vote=down "Vote down!")

5


[**_ecervetti at orupaca dot fr_**](https://www.php.net/manual/en/function.error-reporting.php#89829) [¶](https://www.php.net/manual/en/function.error-reporting.php#89829)

**16 years ago**

`It could save two minutes to someone:
E_ALL & ~E_NOTICE  integer value is 6135`

[up](https://www.php.net/manual/vote-note.php?id=120152&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120152&page=function.error-reporting&vote=down "Vote down!")

1


[**_chris at ocproducts dot com_**](https://www.php.net/manual/en/function.error-reporting.php#120152) [¶](https://www.php.net/manual/en/function.error-reporting.php#120152)

**8 years ago**

`The error_reporting() function will return 0 if error suppression is currently active somewhere in the call tree (via the @ operator).`

[up](https://www.php.net/manual/vote-note.php?id=130467&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130467&page=function.error-reporting&vote=down "Vote down!")

0


[**_ohcc at 163 dot com_**](https://www.php.net/manual/en/function.error-reporting.php#130467) [¶](https://www.php.net/manual/en/function.error-reporting.php#130467)

**1 month ago**

`As of PHP 8.0.0+, error_reporting() in an error handler function returns $error_reporting & (E_ERROR | E_CORE_ERROR | E_COMPILE_ERROR | E_USER_ERROR | E_RECOVERABLE_ERROR | E_PARSE), where $error_reporting is the value of the global error_reporting ini directive set, no matter it is set through ini or error_reporting().`

[up](https://www.php.net/manual/vote-note.php?id=98414&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=98414&page=function.error-reporting&vote=down "Vote down!")

3


[**_keithm at aoeex dot com_**](https://www.php.net/manual/en/function.error-reporting.php#98414) [¶](https://www.php.net/manual/en/function.error-reporting.php#98414)

**15 years ago**

`Some E_STRICT errors seem to be thrown during the page's compilation process.  This means they cannot be disabled by dynamically altering the error level at run time within that page.
The work-around for this was to rename the file and replace the original with a error_reporting() call and then a require() call.
Ex, rename index.php to index.inc.php, then re-create index.php as:
<?php
error_reporting(E_ALL & ~(E_STRICT|E_NOTICE));
require('index.inc.php');
?>
That allows you to alter the error reporting prior to the file being compiled.
I discovered this recently when I was given code from another development firm that triggered several E_STRICT errors and I wanted to disable E_STRICT on a per-page basis.`

[up](https://www.php.net/manual/vote-note.php?id=123154&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123154&page=function.error-reporting&vote=down "Vote down!")

0


[**_huhiko334 at yandex dot ru_**](https://www.php.net/manual/en/function.error-reporting.php#123154) [¶](https://www.php.net/manual/en/function.error-reporting.php#123154)

**7 years ago**

`If you get a weird mysql warnings like "Warning: mysql_query() : Your query requires a full tablescan...", don't look for error_reporting settings - it's set in php.ini.
You can turn it off with
ini_set("mysql.trace_mode","Off");
in your script
[http://tinymy.link/mctct](http://tinymy.link/mctct)`

[up](https://www.php.net/manual/vote-note.php?id=122624&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122624&page=function.error-reporting&vote=down "Vote down!")

0


[**_kevinson112 at yahoo dot com_**](https://www.php.net/manual/en/function.error-reporting.php#122624) [¶](https://www.php.net/manual/en/function.error-reporting.php#122624)

**7 years ago**

`I had the problem that if there was an error, php would just give me a blank page.  Any error at all forced a blank page instead of any output whatsoever, even though I made sure that I had error_reporting set to E_ALL, display_errors turned on, etc etc.  But simply running the file in a different directory allowed it to show errors!
Turns out that the error_log file in the one directory was full (2.0 Gb).  I erased the file and now errors are displayed normally.  It might also help to turn error logging off.
[https://techysupport.co/norton-tech-support/](https://techysupport.co/norton-tech-support/)`

[up](https://www.php.net/manual/vote-note.php?id=48147&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=48147&page=function.error-reporting&vote=down "Vote down!")

2


[**_Fernando Piancastelli_**](https://www.php.net/manual/en/function.error-reporting.php#48147) [¶](https://www.php.net/manual/en/function.error-reporting.php#48147)

**20 years ago**

`The error_reporting() function won't be effective if your display_errors directive in php.ini is set to "Off", regardless of level reporting you set. I had to set
display_errors = On
error_reporting = ~E_ALL
to keep no error reporting as default, but be able to change error reporting level in my scripts.
I'm using PHP 4.3.9 and Apache 2.0.`

[up](https://www.php.net/manual/vote-note.php?id=8866&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=8866&page=function.error-reporting&vote=down "Vote down!")

1


[**_j dot schriver at vindiou dot com_**](https://www.php.net/manual/en/function.error-reporting.php#8866) [¶](https://www.php.net/manual/en/function.error-reporting.php#8866)

**25 years ago**

`error_reporting() has no effect if you have defined your own error handler with set_error_handler()
[Editor's Note: This is not quite accurate.\
E_ERROR, E_PARSE, E_CORE_ERROR, E_CORE_WARNING, E_COMPILE_ERROR and E_COMPILE_WARNING error levels will be handled as per the error_reporting settings.\
All other levels of errors will be passed to the custom error handler defined by set_error_handler().\
Zeev Suraski suggests that a simple way to use the defined levels of error reporting with your custom error handlers is to add the following line to the top of your error handling function:\
if (!($type & error_reporting())) return;\
 -zak@php.net]`

[up](https://www.php.net/manual/vote-note.php?id=101260&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101260&page=function.error-reporting&vote=down "Vote down!")

 -1


[**_rojaro at gmail dot com_**](https://www.php.net/manual/en/function.error-reporting.php#101260) [¶](https://www.php.net/manual/en/function.error-reporting.php#101260)

**14 years ago**

`To enable error reporting for *ALL* error messages including every error level (including E_STRICT, E_NOTICE etc.), simply use:
<?php error_reporting(-1); ?>`

[up](https://www.php.net/manual/vote-note.php?id=120809&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120809&page=function.error-reporting&vote=down "Vote down!")

 -1


[**_adam at adamhahn dot com_**](https://www.php.net/manual/en/function.error-reporting.php#120809) [¶](https://www.php.net/manual/en/function.error-reporting.php#120809)

**8 years ago**

`To expand upon the note by chris at ocproducts dot com. If you prepend @ to error_reporting(), the function will always return 0.
<?php
error_reporting(E_ALL);
var_dump(
    error_reporting(), // value of E_ALL,
    @error_reporting() // value is 0
);
?>`

[up](https://www.php.net/manual/vote-note.php?id=85013&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85013&page=function.error-reporting&vote=down "Vote down!")

 -1


[**_kc8yds at gmail dot com_**](https://www.php.net/manual/en/function.error-reporting.php#85013) [¶](https://www.php.net/manual/en/function.error-reporting.php#85013)

**17 years ago**

`this is to show all errors for code that may be run on different versions
for php 5 it shows E_ALL^E_STRICT and for other versions just E_ALL
if anyone sees any problems with it please correct this post
<?php
ini_set('error_reporting', version_compare(PHP_VERSION,5,'>=') && version_compare(PHP_VERSION,6,'<') ?E_ALL^E_STRICT:E_ALL);
?>`

[up](https://www.php.net/manual/vote-note.php?id=89017&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=89017&page=function.error-reporting&vote=down "Vote down!")

 -2


[**_Daz Williams (The Northeast)_**](https://www.php.net/manual/en/function.error-reporting.php#89017) [¶](https://www.php.net/manual/en/function.error-reporting.php#89017)

**16 years ago**

`Only display php errors to the developer...
<?php
if($_SERVER['REMOTE_ADDR']=="00.00.00.00")
{
ini_set('display_errors','On');
}
else
{
ini_set('display_errors','Off');
}
?>
Just replace 00.00.00.00 with your ip address.`

[up](https://www.php.net/manual/vote-note.php?id=107447&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107447&page=function.error-reporting&vote=down "Vote down!")

 -2


[**_teynon1 at gmail dot com_**](https://www.php.net/manual/en/function.error-reporting.php#107447) [¶](https://www.php.net/manual/en/function.error-reporting.php#107447)

**13 years ago**

`It might be a good idea to include E_COMPILE_ERROR in error_reporting.
If you have a customer error handler that does not output warnings, you may get a white screen of death if a "require" fails.
Example:
<?php
error_reporting(E_ERROR | E_WARNING | E_PARSE);
function myErrorHandler($errno, $errstr, $errfile, $errline) {
    // Do something other than output message.
    return true;
}
$old_error_handler = set_error_handler("myErrorHandler");
require "this file does not exist";
?>
To prevent this, simply include E_COMPILE_ERROR in the error_reporting.
<?php
error_reporting(E_ERROR | E_WARNING | E_PARSE | E_COMPILE_ERROR);
?>`

[up](https://www.php.net/manual/vote-note.php?id=55985&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=55985&page=function.error-reporting&vote=down "Vote down!")

 -1


[**_DarkGool_**](https://www.php.net/manual/en/function.error-reporting.php#55985) [¶](https://www.php.net/manual/en/function.error-reporting.php#55985)

**20 years ago**

`In phpinfo() error reporting level display like a bit (such as 4095)
Maybe it is a simply method to understand what a level set on your host
if you are not have access to php.ini file
<?php
$bit = ini_get('error_reporting');
while ($bit > 0) {
    for($i = 0, $n = 0; $i <= $bit; $i = 1 * pow(2, $n), $n++) {
        $end = $i;
    }
    $res[] = $end;
    $bit = $bit - $end;
}
?>
In $res you will have all constants of error reporting
$res[]=int(16) // E_CORE_ERROR
$res[]=int(8)    // E_NOTICE
...`

[up](https://www.php.net/manual/vote-note.php?id=117071&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117071&page=function.error-reporting&vote=down "Vote down!")

 -2


[**_qeremy ! gmail_**](https://www.php.net/manual/en/function.error-reporting.php#117071) [¶](https://www.php.net/manual/en/function.error-reporting.php#117071)

**10 years ago**

`If you want to see all errors in your local environment, you can set your project URL like "foo.com.local" locally and put that in bootstrap file.
<?php
if (substr($_SERVER['SERVER_NAME'], -6) == '.local') {
    ini_set('display_errors', 1);
    ini_set('error_reporting', E_ALL);
    // or error_reporting(E_ALL);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=91412&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91412&page=function.error-reporting&vote=down "Vote down!")

 -3


[**_misplacedme at gmail dot com_**](https://www.php.net/manual/en/function.error-reporting.php#91412) [¶](https://www.php.net/manual/en/function.error-reporting.php#91412)

**16 years ago**

`I always code with E_ALL set.
After a couple of pages of
<?php
$username = (isset($_POST['username']) && !empty($_POST['username']))....
?>
I made this function to make things a little bit quicker.  Unset values passed by reference won't trigger a notice.
<?php
function test_ref(&$var,$test_function='',$negate=false) {
    $stat = true;
    if(!isset($var)) $stat = false;
    if (!empty($test_function) && function_exists($test_function)){
        $stat = $test_function($var);
        $stat = ($negate) ? $stat^1 : $stat;
    }
    elseif($test_function == 'empty') {
        $stat = empty($var);
        $stat = ($negate) ? $stat^1 : $stat;
    }
    elseif (!function_exists($test_function)) {
        $stat = false;
        trigger_error("$test_function() is not a valid function");
    }
    $stat = ($stat) ? true : false;
    return $stat;
}
$a = '';
$b = '15';
test_ref($a,'empty',true);  //False
test_ref($a,'is_int');  //False
test_ref($a,'is_numeric');  //False
test_ref($b,'empty',true);  //true
test_ref($b,'is_int');  //False
test_ref($b,'is_numeric');  //false
test_ref($unset,'is_numeric');  //false
test_ref($b,'is_number');  //returns false, with an error.
?>`

[up](https://www.php.net/manual/vote-note.php?id=72457&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72457&page=function.error-reporting&vote=down "Vote down!")

 -2


[**_Alex_**](https://www.php.net/manual/en/function.error-reporting.php#72457) [¶](https://www.php.net/manual/en/function.error-reporting.php#72457)

**18 years ago**

`error_reporting() may give unexpected results if the @ error suppression directive is used.
<?php
@include 'config.php';
include 'foo.bar';        // non-existent file
?>
config.php
<?php
error_reporting(0);
?>
will throw an error level E_WARNING in relation to the non-existent file (depending of course on your configuration settings).  If the suppressor is removed, this works as expected.
Alternatively using ini_set('display_errors', 0) in config.php will achieve the same result.  This is contrary to the note above which says that the two instructions are equivalent.`

[up](https://www.php.net/manual/vote-note.php?id=122774&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122774&page=function.error-reporting&vote=down "Vote down!")

 -2


[**_luisdev_**](https://www.php.net/manual/en/function.error-reporting.php#122774) [¶](https://www.php.net/manual/en/function.error-reporting.php#122774)

**7 years ago**

`This article refers to these two reporting levels:
// Report all PHP errors (see changelog)
error_reporting(E_ALL);
// Report all PHP errors
error_reporting(-1);
What is the difference between those two levels?
Please update this article with a clear explanation of the difference and the possible use cases.`

[up](https://www.php.net/manual/vote-note.php?id=113358&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113358&page=function.error-reporting&vote=down "Vote down!")

 -4


[**_forcemdt_**](https://www.php.net/manual/en/function.error-reporting.php#113358) [¶](https://www.php.net/manual/en/function.error-reporting.php#113358)

**12 years ago**

`Php >5.4
Creating a Custom Error Handler
set_error_handler("customError",E_ALL);
function customError($errno, $errstr)
{
echo "<b>Error:</b> [$errno] $errstr<br>";
echo "Ending Script";
die();
}`

[up](https://www.php.net/manual/vote-note.php?id=116441&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116441&page=function.error-reporting&vote=down "Vote down!")

 -3


[**_Rash_**](https://www.php.net/manual/en/function.error-reporting.php#116441) [¶](https://www.php.net/manual/en/function.error-reporting.php#116441)

**10 years ago**

``If you are using the PHP development server, run from the command line via `php -S servername:port`, every single error/notice/warning will be reported in the command line itself, with file name, and line number, and stack trace.
So if you want to keep a log of all the errors even after page reloads (for help in debugging, maybe), running the PHP development server can be useful.``

[up](https://www.php.net/manual/vote-note.php?id=95944&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95944&page=function.error-reporting&vote=down "Vote down!")

 -2


[**_roberto at spadim dot com dot br_**](https://www.php.net/manual/en/function.error-reporting.php#95944) [¶](https://www.php.net/manual/en/function.error-reporting.php#95944)

**15 years ago**

`see more information about php 5.3 deprecated errors
[http://php.net/manual/en/migration53.deprecated.php](http://php.net/manual/en/migration53.deprecated.php)`

[up](https://www.php.net/manual/vote-note.php?id=55035&page=function.error-reporting&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=55035&page=function.error-reporting&vote=down "Vote down!")

 -4


[**_fredrik at demomusic dot nu_**](https://www.php.net/manual/en/function.error-reporting.php#55035) [¶](https://www.php.net/manual/en/function.error-reporting.php#55035)

**20 years ago**

`Remember that the error_reporting value is an integer, not a string ie "E_ALL & ~E_NOTICE".
This is very useful to remember when setting error_reporting levels in httpd.conf:
Use the table above or:
<?php
ini_set("error_reporting", E_YOUR_ERROR_LEVEL);
echo ini_get("error_reporting");
?>
To get the appropriate integer for your error-level. Then use:
php_admin_value error_reporting YOUR_INT
in httpd.conf
I want to share this rather straightforward tip as it is rather annoying for new php users trying to understand why things are not working when the error-level is set to (int) "E_ALL" = 0...
Maybe the PHP-developers should make ie error_reporting("E_ALL"); output a E_NOTICE informative message about the mistake?`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.error-reporting&repo=en&redirect=https://www.php.net/manual/en/function.error-reporting.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google