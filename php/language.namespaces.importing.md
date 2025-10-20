---
url: https://www.php.net/manual/en/language.namespaces.importing.php
scraped_at: 2025-10-20T02:53:17.370Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Using namespaces: Aliasing/Importing [¶](https://www.php.net/manual/en/language.namespaces.importing.php\#language.namespaces.importing)

(PHP 5 >= 5.3.0, PHP 7, PHP 8)

The ability to refer to an external fully qualified name with an alias, or importing,
is an important feature of namespaces. This is similar to the
ability of unix-based filesystems to create symbolic links to a file or to a directory.


PHP can alias(/import) constants, functions, classes, interfaces, traits, enums and namespaces.


Aliasing is accomplished with the `use` operator.
Here is an example showing all 5 kinds of importing:


**Example #1 importing/aliasing with the use operator**

`<?php
namespace foo;
use My\Full\Classname as Another;
// this is the same as use My\Full\NSname as NSname
use My\Full\NSname;
// importing a global class
use ArrayObject;
// importing a function
use function My\Full\functionName;
// aliasing a function
use function My\Full\functionName as func;
// importing a constant
use const My\Full\CONSTANT;
$obj = new namespace\Another; // instantiates object of class foo\Another
$obj = new Another; // instantiates object of class My\Full\Classname
NSname\subns\func(); // calls function My\Full\NSname\subns\func
$a = new ArrayObject(array(1)); // instantiates object of class ArrayObject
// without the "use ArrayObject" we would instantiate an object of class foo\ArrayObject
func(); // calls function My\Full\functionName
echo CONSTANT; // echoes the value of My\Full\CONSTANT
?>`

Note that for namespaced names (fully qualified namespace names containing
namespace separator, such as `Foo\Bar` as opposed to global names that
do not, such as `FooBar`), the leading backslash is unnecessary and not
recommended, as import names
must be fully qualified, and are not processed relative to the current namespace.


PHP additionally supports a convenience shortcut to place multiple use statements
on the same line


**Example #2 importing/aliasing with the use operator, multiple use statements combined**

`<?php
use My\Full\Classname as Another, My\Full\NSname;
$obj = new Another; // instantiates object of class My\Full\Classname
NSname\subns\func(); // calls function My\Full\NSname\subns\func
?>`

Importing is performed at compile-time, and so does not affect dynamic class, function
or constant names.


**Example #3 Importing and dynamic names**

`<?php
use My\Full\Classname as Another, My\Full\NSname;
$obj = new Another; // instantiates object of class My\Full\Classname
$a = 'Another';
$obj = new $a;      // instantiates object of class Another
?>`

In addition, importing only affects unqualified and qualified names. Fully qualified
names are absolute, and unaffected by imports.


**Example #4 Importing and fully qualified names**

`<?php
use My\Full\Classname as Another, My\Full\NSname;
$obj = new Another; // instantiates object of class My\Full\Classname
$obj = new \Another; // instantiates object of class Another
$obj = new Another\thing; // instantiates object of class My\Full\Classname\thing
$obj = new \Another\thing; // instantiates object of class Another\thing
?>`

### Scoping rules for importing [¶](https://www.php.net/manual/en/language.namespaces.importing.php\#language.namespaces.importing.scope)

The `use` keyword must be declared in the
outermost scope of a file (the global scope) or inside namespace
declarations. This is because the importing is done at compile
time and not runtime, so it cannot be block scoped. The following
example will show an illegal use of the `use`
keyword:


**Example #5 Illegal importing rule**

`<?php
namespace Languages;
function toGreenlandic()
{
    use Languages\Danish;
    // ...
}
?>`

> **Note**:
>
>
> Importing rules are per file basis, meaning included files will
> _NOT_ inherit the parent file's importing rules.

### Group `use` declarations [¶](https://www.php.net/manual/en/language.namespaces.importing.php\#language.namespaces.importing.group)

Classes, functions and constants being imported from
the same [`namespace`](https://www.php.net/manual/en/language.namespaces.definition.php) can be grouped together in a single [`use`](https://www.php.net/manual/en/language.namespaces.importing.php)
statement.


`<?php
use some\namespace\ClassA;
use some\namespace\ClassB;
use some\namespace\ClassC as C;
use function some\namespace\fn_a;
use function some\namespace\fn_b;
use function some\namespace\fn_c;
use const some\namespace\ConstA;
use const some\namespace\ConstB;
use const some\namespace\ConstC;
// is equivalent to the following groupped use declaration
use some\namespace\{ClassA, ClassB, ClassC as C};
use function some\namespace\{fn_a, fn_b, fn_c};
use const some\namespace\{ConstA, ConstB, ConstC};`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/namespaces.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.namespaces.importing%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.namespaces.importing&repo=en&redirect=https://www.php.net/manual/en/language.namespaces.importing.php)

### User Contributed Notes 17 notes

[up](https://www.php.net/manual/vote-note.php?id=119919&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119919&page=language.namespaces.importing&vote=down "Vote down!")

200


[**_dominic\_mayers at yahoo dot com_**](https://www.php.net/manual/en/language.namespaces.importing.php#119919) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#119919)

**9 years ago**

`The keyword "use" has been recycled for three distinct applications:
1- to import/alias classes, traits, constants, etc. in namespaces,
2- to insert traits in classes,
3- to inherit variables in closures.
This page is only about the first application: importing/aliasing. Traits can be inserted in classes, but this is different from importing a trait in a namespace, which cannot be done in a block scope, as pointed out in example 5. This can be confusing, especially since all searches for the keyword "use" are directed to the documentation here on importing/aliasing.`

[up](https://www.php.net/manual/vote-note.php?id=114265&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114265&page=language.namespaces.importing&vote=down "Vote down!")

159


[**_anon_**](https://www.php.net/manual/en/language.namespaces.importing.php#114265) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#114265)

**11 years ago**

`The <?php use ?> statement does not load the class file. You have to do this with the <?php require ?> statement or by using an autoload function.`

[up](https://www.php.net/manual/vote-note.php?id=121785&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121785&page=language.namespaces.importing&vote=down "Vote down!")

58


[**_Mawia HL_**](https://www.php.net/manual/en/language.namespaces.importing.php#121785) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#121785)

**7 years ago**

`Here is a handy way of importing classes, functions and conts using a single use keyword:
<?php
use Mizo\Web\ {
Php\WebSite,
Php\KeyWord,
Php\UnicodePrint,
JS\JavaScript,
function JS\printTotal,
function JS\printList,
const JS\BUAIKUM,
const JS\MAUTAM
};
?>`

[up](https://www.php.net/manual/vote-note.php?id=111874&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111874&page=language.namespaces.importing&vote=down "Vote down!")

82


[**_k at webnfo dot com_**](https://www.php.net/manual/en/language.namespaces.importing.php#111874) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#111874)

**12 years ago**

`Note that you can not alias global namespace:
use \ as test;
echo test\strlen('');
won't work.`

[up](https://www.php.net/manual/vote-note.php?id=121045&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121045&page=language.namespaces.importing&vote=down "Vote down!")

33


[**_xzero at elite7hackers dot net_**](https://www.php.net/manual/en/language.namespaces.importing.php#121045) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#121045)

**8 years ago**

`I couldn't find answer to this question so I tested myself.
I think it's worth noting:
<?php
use ExistingNamespace\NonExsistingClass;
use ExistingNamespace\NonExsistingClass as whatever;
use NonExistingNamespace\NonExsistingClass;
use NonExistingNamespace\NonExsistingClass as whatever;
?>
None of above will actually cause errors unless you actually try to use class you tried to import.
<?php
// And this code will issue standard PHP error for non existing class.
use ExistingNamespace\NonExsistingClass as whatever;
$whatever = new whatever();
?>`

[up](https://www.php.net/manual/vote-note.php?id=119091&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119091&page=language.namespaces.importing&vote=down "Vote down!")

23


[**_me at ruslanbes dot com_**](https://www.php.net/manual/en/language.namespaces.importing.php#119091) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#119091)

**9 years ago**

``Note the code `use ns1\c1` may refer to importing class `c1` from namespace `ns1` as well as importing whole namespace `ns1\c1` or even import both of them in one line. Example:
<?php
namespace ns1;
class c1{}
namespace ns1\c1;
class c11{}
namespace main;
use ns1\c1;
$c1 = new c1();
$c11 = new c1\c11();
var_dump($c1); // object(ns1\c1)#1 (0) { }
var_dump($c11); // object(ns1\c1\c11)#2 (0) { }``

[up](https://www.php.net/manual/vote-note.php?id=105394&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105394&page=language.namespaces.importing&vote=down "Vote down!")

29


[**_c dot 1 at smithies dot org_**](https://www.php.net/manual/en/language.namespaces.importing.php#105394) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#105394)

**14 years ago**

`If you are testing your code at the CLI, note that namespace aliases do not work!
(Before I go on, all the backslashes in this example are changed to percent signs because I cannot get sensible results to display in the posting preview otherwise. Please mentally translate all percent signs henceforth as backslashes.)
Suppose you have a class you want to test in myclass.php:
<?php
namespace my%space;
class myclass {
// ...
}
?>
and you then go into the CLI to test it. You would like to think that this would work, as you type it line by line:
require 'myclass.php';
use my%space%myclass; // should set 'myclass' as alias for 'my%space%myclass'
$x = new myclass; // FATAL ERROR
I believe that this is because aliases are only resolved at compile time, whereas the CLI simply evaluates statements; so use statements are ineffective in the CLI.
If you put your test code into test.php:
<?php
require 'myclass.php';
use my%space%myclass;
$x = new myclass;
//...
?>
it will work fine.
I hope this reduces the number of prematurely bald people.`

[up](https://www.php.net/manual/vote-note.php?id=110978&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110978&page=language.namespaces.importing&vote=down "Vote down!")

18


[**_x at d dot a dot r dot k dot REMOVEDOTSANDTHIS dot gray dot org_**](https://www.php.net/manual/en/language.namespaces.importing.php#110978) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#110978)

**12 years ago**

`You are allowed to "use" the same resource multiple times as long as it is imported under a different alias at each invocation.
For example:
<?php
use Lend;
use Lend\l1;
use Lend\l1 as l3;
use Lend\l2;
use Lend\l1\Keller;
use Lend\l1\Keller as Stellar;
use Lend\l1\Keller as Zellar;
use Lend\l2\Keller as Dellar;
...
?>
In the above example, "Keller", "Stellar", and "Zellar" are all references to "\Lend\l1\Keller", as are "Lend\l1\Keller", "l1\Keller", and "l3\Keller".`

[up](https://www.php.net/manual/vote-note.php?id=111634&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111634&page=language.namespaces.importing&vote=down "Vote down!")

16


[**_cl_**](https://www.php.net/manual/en/language.namespaces.importing.php#111634) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#111634)

**12 years ago**

`Something that is not immediately obvious, particular with PHP 5.3, is that namespace resolutions within an import are not resolved recursively.  i.e.: if you alias an import and then use that alias in another import then this latter import will not be fully resolved with the former import.
For example:
use \Controllers as C;
use C\First;
use C\Last;
Both the First and Last namespaces are NOT resolved as \Controllers\First or \Controllers\Last as one might intend.`

[up](https://www.php.net/manual/vote-note.php?id=119970&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119970&page=language.namespaces.importing&vote=down "Vote down!")

4


[**_ultimater at gmail dot com_**](https://www.php.net/manual/en/language.namespaces.importing.php#119970) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#119970)

**9 years ago**

`Note that "use" importing/aliasing only applies to the current namespace block.
<?php
namespace SuperCoolLibrary
{
    class Meta
    {
        static public function getVersion()
        {
            return '2.7.1';
        }
    }
}
namespace
{
    use SuperCoolLibrary\Meta;
    echo Meta::getVersion();//outputs 2.7.1
}
namespace
{
    echo Meta::getVersion();//fatal error
}
?>
To get the expected behavior, you'd use:
class_alias('SuperCoolLibrary\Meta','Meta');`

[up](https://www.php.net/manual/vote-note.php?id=120644&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120644&page=language.namespaces.importing&vote=down "Vote down!")

1


[**_ZhangLiang_**](https://www.php.net/manual/en/language.namespaces.importing.php#120644) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#120644)

**8 years ago**

`In Chinese,there is an error in translation:
// 如果不使用 "use \ArrayObject" ，则实例化一个 foo\ArrayObject 对象
it should be
// 如果不使用 "use ArrayObject" ，则实例化一个 foo\ArrayObject 对象
/*********************************************/
中文下翻译有错误
// 如果不使用 "use \ArrayObject" ，则实例化一个 foo\ArrayObject 对象
这句话应该是
// 如果不使用 "use ArrayObject" ，则实例化一个 foo\ArrayObject 对象`

[up](https://www.php.net/manual/vote-note.php?id=125931&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125931&page=language.namespaces.importing&vote=down "Vote down!")

0


[**_eithed at google mail_**](https://www.php.net/manual/en/language.namespaces.importing.php#125931) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#125931)

**4 years ago**

`Bear in mind that it's perfectly fine to alias namespaces, ie:
<?php
use A\B\C\D\E\User;
new User();
?>
can be also written as:
<?php
use A\B\C\D\E as ENamespace;
new ENamespace\User();
?>
however following will not work:
<?php
use A\B\C\D\E as ENamespace;
use ENamespace\User;
new User();
?>
> PHP Error:  Class "ENamespace\User" not found`

[up](https://www.php.net/manual/vote-note.php?id=101199&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101199&page=language.namespaces.importing&vote=down "Vote down!")

3


[**_thinice at gmail.com_**](https://www.php.net/manual/en/language.namespaces.importing.php#101199) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#101199)

**14 years ago**

`Because imports happen at compile time, there's no polymorphism potential by embedding the use keyword in a conditonal.
e.g.:
<?php
if ($objType == 'canine') {
use Animal\Canine as Beast;
}
if ($objType == 'bovine') {
use Animal\Bovine as Beast;
}
$oBeast = new Beast;
$oBeast->feed();
?>`

[up](https://www.php.net/manual/vote-note.php?id=119920&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119920&page=language.namespaces.importing&vote=down "Vote down!")

 -1


[**_dominic\_mayers at yahoo dot com_**](https://www.php.net/manual/en/language.namespaces.importing.php#119920) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#119920)

**9 years ago**

`To clarify the distinction between inserting a trait in a class and importing a trait in a namespace, here is an example where we first import and then insert a trait.
<?php
namespace ns1;
trait T {
static $a = "In T";
}
namespace ns2;
use ns1\T; // Importing the name of trait ns1\T  in the namespace ns2
class C {
use T; // Inserting trait T in the class C, making use of the imported name.
}
namespace main;
use ns2\C;
echo C::$a; // In T;`

[up](https://www.php.net/manual/vote-note.php?id=116852&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116852&page=language.namespaces.importing&vote=down "Vote down!")

 -4


[**_kelerest123 at gmail dot com_**](https://www.php.net/manual/en/language.namespaces.importing.php#116852) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#116852)

**10 years ago**

`For the fifth example (example #5):
When in block scope, it is not an illegal use of use keyword, because it is used for sharing things with traits.`

[up](https://www.php.net/manual/vote-note.php?id=125337&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125337&page=language.namespaces.importing&vote=down "Vote down!")

 -5


[**_info at ensostudio dot ru_**](https://www.php.net/manual/en/language.namespaces.importing.php#125337) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#125337)

**5 years ago**

`Note: you can import not existed items without errors:
<?php
use UndefinedClass;
use function undefined_fn;
use const UNDEFINED_CONST;
?>
but you cant use/call they:
<?php
$new UndefinedClass; // Error: Use of undefined class
use function undefined_fn; // Error: Use of undefined function
use const UNDEFINED_CONST; // Error: Use of undefined constant
?>`

[up](https://www.php.net/manual/vote-note.php?id=127140&page=language.namespaces.importing&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127140&page=language.namespaces.importing&vote=down "Vote down!")

 -4


[**_tuxedobob_**](https://www.php.net/manual/en/language.namespaces.importing.php#127140) [¶](https://www.php.net/manual/en/language.namespaces.importing.php#127140)

**3 years ago**

`Note that because this is processed at compile time, this doesn't work when running PHP in interactive mode. use commands won't throw an error, but they won't do anything, either.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.namespaces.importing&repo=en&redirect=https://www.php.net/manual/en/language.namespaces.importing.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google