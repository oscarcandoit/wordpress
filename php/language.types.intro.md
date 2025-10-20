---
url: https://www.php.net/manual/en/language.types.intro.php
scraped_at: 2025-10-20T02:34:39.469Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Introduction [¶](https://www.php.net/manual/en/language.types.intro.php\#language.types.intro)

Every single expression in PHP has one of the following
built-in types depending on its value:


- [null](https://www.php.net/manual/en/language.types.null.php)
- [bool](https://www.php.net/manual/en/language.types.boolean.php)
- [int](https://www.php.net/manual/en/language.types.integer.php)
- [float](https://www.php.net/manual/en/language.types.float.php) (floating-point number)
- [string](https://www.php.net/manual/en/language.types.string.php)
- [array](https://www.php.net/manual/en/language.types.array.php)
- [object](https://www.php.net/manual/en/language.types.object.php)
- [callable](https://www.php.net/manual/en/language.types.callable.php)
- [resource](https://www.php.net/manual/en/language.types.resource.php)

PHP is a dynamically typed language, which means that by default there is
no need to specify the type of a variable, as this will be determined at
runtime. However, it is possible to statically type some aspect of the
language via the use of
[type declarations](https://www.php.net/manual/en/language.types.declarations.php).
Different types that are supported by PHP's type system can be found at the
[type system](https://www.php.net/manual/en/language.types.type-system.php) page.


Types restrict the kind of operations that can be performed on them.
However, if an expression/variable is used in an operation which
its type does not support, PHP will attempt to
[type juggle](https://www.php.net/manual/en/language.types.type-juggling.php)
the value into a type that supports the operation.
This process depends on the context in which the value is used.
For more information, see the section on
[Type Juggling](https://www.php.net/manual/en/language.types.type-juggling.php).


**Tip**

[The type comparison tables](https://www.php.net/manual/en/types.comparisons.php)
may also be useful, as various examples of comparison between values of
different types are present.


> **Note**:
>
> It is possible to force an expression to be evaluated to a certain type by
> using a [type cast](https://www.php.net/manual/en/language.types.type-juggling.php#language.types.typecasting).
> A variable can also be type cast in-place by using the
> [settype()](https://www.php.net/manual/en/function.settype.php) function on it.

To check the value and type of an
[expression](https://www.php.net/manual/en/language.expressions.php),
use the [var\_dump()](https://www.php.net/manual/en/function.var-dump.php) function.
To retrieve the type of an
[expression](https://www.php.net/manual/en/language.expressions.php),
use the [get\_debug\_type()](https://www.php.net/manual/en/function.get-debug-type.php) function.
However, to check if an expression is of a certain type use the

`is_type` functions instead.



**Example #1 Different Types**

`<?php
$a_bool = true;   // a bool
$a_str  = "foo";  // a string
$a_str2 = 'foo';  // a string
$an_int = 12;     // an int
echo get_debug_type($a_bool), "\n";
echo get_debug_type($a_str), "\n";
// If this is an integer, increment it by four
if (is_int($an_int)) {
    $an_int += 4;
}
var_dump($an_int);
// If $a_bool is a string, print it out
if (is_string($a_bool)) {
    echo "String: $a_bool";
}
?>`

Run code

Output of the above example in PHP 8:

```
bool
string
int(16)

```

> **Note**:
>
> Prior to PHP 8.0.0, where the [get\_debug\_type()](https://www.php.net/manual/en/function.get-debug-type.php) is not
> available, the [gettype()](https://www.php.net/manual/en/function.gettype.php) function can be used instead.
> However, it doesn't use the canonical type names.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.intro%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.intro&repo=en&redirect=https://www.php.net/manual/en/language.types.intro.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google