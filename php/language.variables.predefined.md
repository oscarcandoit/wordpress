---
url: https://www.php.net/manual/en/language.variables.predefined.php
scraped_at: 2025-10-20T02:31:18.780Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Predefined Variables [¶](https://www.php.net/manual/en/language.variables.predefined.php\#language.variables.predefined)

PHP provides a number of
[predefined variables](https://www.php.net/manual/en/reserved.variables.php).
PHP also provides an additional set of predefined arrays
containing variables from the web server (if applicable), the
environment, and user input. These arrays are automatically available in
every scope. For this reason, they are often known as
"superglobals". (There is no mechanism in PHP for
user-defined superglobals.) Refer to the
[list of superglobals](https://www.php.net/manual/en/language.variables.superglobals.php)
for details.


> **Note**:
> **Variable variables**
>
> Superglobals cannot be used as
> [variable variables](https://www.php.net/manual/en/language.variables.variable.php)
> inside functions or class methods.

If certain variables in [variables\_order](https://www.php.net/manual/en/ini.core.php#ini.variables-order) are not set, their
appropriate PHP predefined arrays are also left empty.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/variables.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.variables.predefined%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.variables.predefined&repo=en&redirect=https://www.php.net/manual/en/language.variables.predefined.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=64336&page=language.variables.predefined&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=64336&page=language.variables.predefined&vote=down "Vote down!")

120


[**_johnphayes at gmail dot com_**](https://www.php.net/manual/en/language.variables.predefined.php#64336) [¶](https://www.php.net/manual/en/language.variables.predefined.php#64336)

**19 years ago**

`I haven't found it anywhere else in the manual, so I'll make a note of it here - PHP will automatically replace any dots ('.') in an incoming variable name with underscores ('_'). So if you have dots in your incoming variables, e.g.:
example.com/page.php?chuck.norris=nevercries
you can not reference them by the name used in the URI:
//INCORRECT
echo $_GET['chuck.norris'];
instead you must use:
//CORRECT
echo $_GET['chuck_norris'];`

[up](https://www.php.net/manual/vote-note.php?id=28614&page=language.variables.predefined&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=28614&page=language.variables.predefined&vote=down "Vote down!")

7


[**_lopez dot on dot the dot lists at yellowspace dot net_**](https://www.php.net/manual/en/language.variables.predefined.php#28614) [¶](https://www.php.net/manual/en/language.variables.predefined.php#28614)

**22 years ago**

`- Security Issue and workaround -
If You use "eval()" to execute code stored in a database or elsewhere, you might find this tip useful.
Issue:
By default, all superglobals are known in every function.
Thus, if you eval database- or dynamically generated code (let's call it "potentially unsafe code"), it can use _all_ the values stored in _any_ superglobal.
Workaround:
Whenever you want to hide superglobals from use in evaluated code, wrap that eval() in an own function within which you unset() all the superglobals. The superglobals are not deleted by php in all scopes - just within that function. eg:
function safeEval($evalcode) {
    unset($GLOBALS);
    unset($_ENV);
    // unset any other superglobal...
    return eval($evalcode);
}
(This example assumes that the eval returns something with 'return')
In addition, by defining such a function outside classes, in the global scope, you'll make sure as well that the evaluated ('unsafe') code doesn't have access to the object variables ($this-> ...).`

[up](https://www.php.net/manual/vote-note.php?id=30678&page=language.variables.predefined&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=30678&page=language.variables.predefined&vote=down "Vote down!")

2


[**_LouisGreen at pljg dot freeserve dot co dot uk_**](https://www.php.net/manual/en/language.variables.predefined.php#30678) [¶](https://www.php.net/manual/en/language.variables.predefined.php#30678)

**22 years ago**

`It seems that when you wish to export a varible, you can do it as return $varible, return an array(), or globalise it. If you return something, information for that varible can only travel one way when the script is running, and that is out of the function.
function fn() {
$varible = "something";
return $variable;
}
echo fn();
OR
$newvariable = fn();
Although if global was used, it creates a pointer to a varible, whether it existed or not, and makes whatever is created in the function linked to that global pointer. So if the pointer was global $varible, and then you set a value to $varible, it would then be accessible in the global scope. But then what if you later on in the script redefine that global to equal something else. This means that whatever is put into the global array, the information that is set in the pointer, can be set at any point (overiden). Here is an example that might make this a little clearer:
function fn1() {
global $varible; // Pointer to the global array
$varible = "something";
}
fn1();
echo $varible; // Prints something
$varible = "12345";
echo $varible; // Prints 12345
function fn2() {
global $varible; // Pointer to the global array
echo $varible;
}
fn2(); // echos $varible which contains "12345"
Basically when accessing the global array, you can set it refer to something already defined or set it to something, (a pointer) such as varible you plan to create in the function, and later possibly over ride the pointer with something else.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.variables.predefined&repo=en&redirect=https://www.php.net/manual/en/language.variables.predefined.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google