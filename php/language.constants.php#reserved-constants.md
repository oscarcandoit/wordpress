---
url: https://www.php.net/manual/en/language.constants.php#reserved-constants
scraped_at: 2025-10-20T02:30:52.615Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Constants [¶](https://www.php.net/manual/en/language.constants.php\#language.constants)

## Table of Contents [¶](https://www.php.net/manual/en/language.constants.php\#language.constants)

- [Syntax](https://www.php.net/manual/en/language.constants.syntax.php)
- [Predefined constants](https://www.php.net/manual/en/language.constants.predefined.php)
- [Magic constants](https://www.php.net/manual/en/language.constants.magic.php)

A constant is an identifier (name) for a simple value. As the name
suggests, that value cannot change during the execution of the
script (except for [magic constants](https://www.php.net/manual/en/language.constants.magic.php), which aren't actually constants).
Constants are case-sensitive. By convention, constant
identifiers are always uppercase.


> **Note**:
>
>
> Prior to PHP 8.0.0, constants defined using the [define()](https://www.php.net/manual/en/function.define.php)
> function may be case-insensitive.

The name of a constant follows the same rules as any label in PHP. A
valid constant name starts with a letter or underscore, followed
by any number of letters, numbers, or underscores. As a regular
expression, it would be expressed thusly:
`^[a-zA-Z_\x80-\xff][a-zA-Z0-9_\x80-\xff]*$`

It is possible to [define()](https://www.php.net/manual/en/function.define.php) constants with reserved or even
invalid names, whose value can only be retrieved with the
[constant()](https://www.php.net/manual/en/function.constant.php) function. However, doing so is not recommended.


**Tip**

See also the
[Userland Naming Guide](https://www.php.net/manual/en/userlandnaming.php).

**Example #1 Valid and invalid constant names**

`<?php
// Valid constant names
define("FOO",     "something");
define("FOO2",    "something else");
define("FOO_BAR", "something more");
// Invalid constant names
define("2FOO",    "something");
// This is valid, but should be avoided:
// PHP may one day provide a magical constant
// that will break your script
define("__FOO__", "something");
?>`

> **Note**:
>
> For our purposes here, a letter is a-z, A-Z, and the ASCII
> characters from 128 through 255 (0x80-0xff).

Like [superglobals](https://www.php.net/manual/en/language.variables.predefined.php), the scope of a constant is global.
Constants can be accessed from anywhere in a script without regard to scope.
For more information on scope, read the manual section on
[variable scope](https://www.php.net/manual/en/language.variables.scope.php).


> **Note**:
>
> As of PHP 7.1.0, class constant may declare a visibility of protected
> or private, making them only available in the hierarchical scope of the
> class in which it is defined.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/constants.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.constants%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.constants&repo=en&redirect=https://www.php.net/manual/en/language.constants.php)

### User Contributed Notes 10 notes

[up](https://www.php.net/manual/vote-note.php?id=108717&page=language.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=108717&page=language.constants&vote=down "Vote down!")

260


[**_wbcarts at juno dot com_**](https://www.php.net/manual/en/language.constants.php#108717) [¶](https://www.php.net/manual/en/language.constants.php#108717)

**13 years ago**

`11/14/2016 - note updated by sobak
-----
CONSTANTS and PHP Class Definitions
Using "define('MY_VAR', 'default value')" INSIDE a class definition does not work as expected. You have to use the PHP keyword 'const' and initialize it with a scalar value -- boolean, int, float, string (or array in PHP 5.6+) -- right away.
<?php
define('MIN_VALUE', '0.0');   // RIGHT - Works OUTSIDE of a class definition.
define('MAX_VALUE', '1.0');   // RIGHT - Works OUTSIDE of a class definition.
//const MIN_VALUE = 0.0;         RIGHT - Works both INSIDE and OUTSIDE of a class definition.
//const MAX_VALUE = 1.0;         RIGHT - Works both INSIDE and OUTSIDE of a class definition.
class Constants
{
//define('MIN_VALUE', '0.0');  WRONG - Works OUTSIDE of a class definition.
//define('MAX_VALUE', '1.0');  WRONG - Works OUTSIDE of a class definition.
const MIN_VALUE = 0.0;      // RIGHT - Works INSIDE of a class definition.
const MAX_VALUE = 1.0;      // RIGHT - Works INSIDE of a class definition.
public static function getMinValue()
{
    return self::MIN_VALUE;
}
public static function getMaxValue()
{
    return self::MAX_VALUE;
}
}
?>
#Example 1:
You can access these constants DIRECTLY like so:
* type the class name exactly.
* type two (2) colons.
* type the const name exactly.
#Example 2:
Because our class definition provides two (2) static functions, you can also access them like so:
* type the class name exactly.
* type two (2) colons.
* type the function name exactly (with the parentheses).
<?php
#Example 1:
$min = Constants::MIN_VALUE;
$max = Constants::MAX_VALUE;
#Example 2:
$min = Constants::getMinValue();
$max = Constants::getMaxValue();
?>
Once class constants are declared AND initialized, they cannot be set to different values -- that is why there are no setMinValue() and setMaxValue() functions in the class definition -- which means they are READ-ONLY and STATIC (shared by all instances of the class).`

[up](https://www.php.net/manual/vote-note.php?id=125120&page=language.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125120&page=language.constants&vote=down "Vote down!")

24


[**_warwick dot jm dot barnes at gmail dot com_**](https://www.php.net/manual/en/language.constants.php#125120) [¶](https://www.php.net/manual/en/language.constants.php#125120)

**5 years ago**

`The documentation says, "You can access constants anywhere in your script without regard to scope", but it's worth keeping in mind that a const declaration must appear in the source file before the place where it's used.
This doesn't work (using PHP 5.4):
<?php
foo();
const X = 1;
function foo() {
    echo "Value of X: " . X;
}
?>
Result: "Value of X: X"
But this works:
<?php
const X = 1;
foo();
function foo() {
    echo "Value of X: " . X;
}
?>
Result: "Value of X: 1"
This is potentially confusing because you can refer to a function that occurs later in your source file, but not a constant. Even though the const declaration is processed at compile time, it behaves a bit like it's being processed at run time.`

[up](https://www.php.net/manual/vote-note.php?id=118671&page=language.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118671&page=language.constants&vote=down "Vote down!")

27


[**_gried at NOSPAM dot nsys dot by_**](https://www.php.net/manual/en/language.constants.php#118671) [¶](https://www.php.net/manual/en/language.constants.php#118671)

**9 years ago**

`Lets expand comment of 'storm' about usage of undefined constants. His claim that 'An undefined constant evaluates as true...' is wrong and right at same time. As said further in documentation ' If you use an undefined constant, PHP assumes that you mean the name of the constant itself, just as if you called it as a string...'. So yeah, undefined global constant when accessed directly will be resolved as string equal to name of sought constant (as thought PHP supposes that programmer had forgot apostrophes and autofixes it) and non-zero non-empty string converts to True.
There are two ways to prevent this:
1. always use function constant('CONST_NAME') to get constant value (BTW it also works for class constants - constant('CLASS_NAME::CONST_NAME') );
2. use only class constants (that are defined inside of class using keyword const) because they are not converted to string when not found but throw exception instead (Fatal error: Undefined class constant).`

[up](https://www.php.net/manual/vote-note.php?id=19363&page=language.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=19363&page=language.constants&vote=down "Vote down!")

30


[**_katana at katana-inc dot com_**](https://www.php.net/manual/en/language.constants.php#19363) [¶](https://www.php.net/manual/en/language.constants.php#19363)

**23 years ago**

`Warning, constants used within the heredoc syntax ( [http://www.php.net/manual/en/language.types.string.php](http://www.php.net/manual/en/language.types.string.php)) are not interpreted!
Editor's Note: This is true. PHP has no way of recognizing the constant from any other string of characters within the heredoc block.`

[up](https://www.php.net/manual/vote-note.php?id=52133&page=language.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=52133&page=language.constants&vote=down "Vote down!")

20


[**_hafenator2000 at yahoo dot com_**](https://www.php.net/manual/en/language.constants.php#52133) [¶](https://www.php.net/manual/en/language.constants.php#52133)

**20 years ago**

`PHP Modules also define constants.  Make sure to avoid constant name collisions.  There are two ways to do this that I can think of.
First: in your code make sure that the constant name is not already used.  ex. <?php if (! defined("CONSTANT_NAME")) { Define("CONSTANT_NAME","Some Value"); } ?>  This can get messy when you start thinking about collision handling, and the implications of this.
Second: Use some off prepend to all your constant names without exception  ex. <?php Define("SITE_CONSTANT_NAME","Some Value"); ?>
Perhaps the developers or documentation maintainers could recommend a good prepend and ask module writers to avoid that prepend in modules.`

[up](https://www.php.net/manual/vote-note.php?id=74836&page=language.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74836&page=language.constants&vote=down "Vote down!")

17


[**_Andreas R._**](https://www.php.net/manual/en/language.constants.php#74836) [¶](https://www.php.net/manual/en/language.constants.php#74836)

**18 years ago**

`If you are looking for predefined constants like
* PHP_OS (to show the operating system, PHP was compiled for; php_uname('s') might be more suitable),
* DIRECTORY_SEPARATOR ("\\" on Win, '/' Linux,...)
* PATH_SEPARATOR (';' on Win, ':' on Linux,...)
they are buried in 'Predefined Constants' under 'List of Reserved Words' in the appendix:
[http://www.php.net/manual/en/reserved.constants.php](http://www.php.net/manual/en/reserved.constants.php)
while the latter two are also mentioned in 'Directory Functions'
[http://www.php.net/manual/en/ref.dir.php](http://www.php.net/manual/en/ref.dir.php)`

[up](https://www.php.net/manual/vote-note.php?id=35064&page=language.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=35064&page=language.constants&vote=down "Vote down!")

23


[**_ewspencer at industrex dot com_**](https://www.php.net/manual/en/language.constants.php#35064) [¶](https://www.php.net/manual/en/language.constants.php#35064)

**22 years ago**

`I find using the concatenation operator helps disambiguate value assignments with constants. For example, setting constants in a global configuration file:
<?php
define('LOCATOR',   "/locator");
define('CLASSES',   LOCATOR."/code/classes");
define('FUNCTIONS', LOCATOR."/code/functions");
define('USERDIR',   LOCATOR."/user");
?>
Later, I can use the same convention when invoking a constant's value for static constructs such as require() calls:
<?php
require_once(FUNCTIONS."/database.fnc");
require_once(FUNCTIONS."/randchar.fnc");
?>
as well as dynamic constructs, typical of value assignment to variables:
<?php
$userid  = randchar(8,'anc','u');
$usermap = USERDIR."/".$userid.".png";
?>
The above convention works for me, and helps produce self-documenting code.
-- Erich`

[up](https://www.php.net/manual/vote-note.php?id=116749&page=language.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116749&page=language.constants&vote=down "Vote down!")

13


[**_Raheel Khan_**](https://www.php.net/manual/en/language.constants.php#116749) [¶](https://www.php.net/manual/en/language.constants.php#116749)

**10 years ago**

`class constant are by default public in nature but they cannot be assigned visibility factor and in turn gives syntax error
<?php
class constants {
    const MAX_VALUE = 10;
        public const MIN_VALUE =1;
}
// This will work
echo constants::MAX_VALUE;
// This will return syntax error
echo constants::MIN_VALUE;
?>`

[up](https://www.php.net/manual/vote-note.php?id=52008&page=language.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=52008&page=language.constants&vote=down "Vote down!")

13


[**_storm_**](https://www.php.net/manual/en/language.constants.php#52008) [¶](https://www.php.net/manual/en/language.constants.php#52008)

**20 years ago**

`An undefined constant evaluates as true when not used correctly. Say for example you had something like this:
settings.php
<?php
// Debug mode
define('DEBUG',false);
?>
test.php
<?php
include('settings.php');
if (DEBUG) {
// echo some sensitive data.
}
?>
If for some reason settings.php doesn't get included and the DEBUG constant is not set, PHP will STILL print the sensitive data. The solution is to evaluate it. Like so:
settings.php
<?php
// Debug mode
define('DEBUG',0);
?>
test.php
<?php
include('settings.php');
if (DEBUG == 1) {
// echo some sensitive data.
}
?>
Now it works correctly.`

[up](https://www.php.net/manual/vote-note.php?id=130476&page=language.constants&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130476&page=language.constants&vote=down "Vote down!")

0


[**_kawewong at gmail dot com_**](https://www.php.net/manual/en/language.constants.php#130476) [¶](https://www.php.net/manual/en/language.constants.php#130476)

**1 month ago**

``To set constant using `define()` will not work with `namespace` unlike using `const`.
Example:
<?php
namespace MyProject;
const IS_IT_CONNECTED = true; // will be able to access via `\MyProject\IS_IT_CONNECTED`
define('START_TIME', time());// will be able to access via `START_TIME` only, not be able to access via ---`\MyProject\START_TIME`---
?>
Call:
<?php
var_dump(\MyProject\IS_IT_CONNECTED);// true
var_dump(START_TIME);// numbers
var_dump(\MyProject\START_TIME);// Fatal error: Uncaught Error: Undefined constant...
?>``

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.constants&repo=en&redirect=https://www.php.net/manual/en/language.constants.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google