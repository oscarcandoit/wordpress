---
url: https://www.php.net/manual/en/language.types.numeric-strings.php
scraped_at: 2025-10-20T02:34:21.385Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Numeric strings [¶](https://www.php.net/manual/en/language.types.numeric-strings.php\#language.types.numeric-strings)

A PHP [string](https://www.php.net/manual/en/language.types.string.php) is considered numeric if it can be interpreted as
an [int](https://www.php.net/manual/en/language.types.integer.php) or a [float](https://www.php.net/manual/en/language.types.float.php).


Formally as of PHP 8.0.0:


```
WHITESPACES      \s*
LNUM             [0-9]+
DNUM             ([0-9]*[\.]{LNUM}) | ({LNUM}[\.][0-9]*)
EXPONENT_DNUM    (({LNUM} | {DNUM}) [eE][+-]? {LNUM})
INT_NUM_STRING   {WHITESPACES} [+-]? {LNUM} {WHITESPACES}
FLOAT_NUM_STRING {WHITESPACES} [+-]? ({DNUM} | {EXPONENT_DNUM}) {WHITESPACES}
NUM_STRING       ({INT_NUM_STRING} | {FLOAT_NUM_STRING})

```

PHP also has a concept of _leading_ numeric strings.
This is simply a string which starts like a numeric string followed by
any characters.


> **Note**:
>
>
> Any string that contains the letter `E` (case insensitive)
> bounded by numbers will be seen as a number expressed in scientific notation.
> This can produce unexpected results.
>
>
> **Example #1 Scientific Notation Comparisons**
>
> `<?php
> var_dump("0D1" == "000"); // false, "0D1" is not scientific notation
> var_dump("0E1" == "000"); // true, "0E1" is 0 * (10 ^ 1), or 0
> var_dump("2E1" == "020"); // true, "2E1" is 2 * (10 ^ 1), or 20
> ?>`
>
> Run code

### Strings used in numeric contexts [¶](https://www.php.net/manual/en/language.types.numeric-strings.php\#language.types.numeric-string.conversion)

When a [string](https://www.php.net/manual/en/language.types.string.php) needs to be evaluated as number (e.g. arithmetic
operations, [int](https://www.php.net/manual/en/language.types.integer.php) type declaration, etc.) the following
steps are taken to determine the outcome:



1. If the [string](https://www.php.net/manual/en/language.types.string.php) is numeric, resolve to an [int](https://www.php.net/manual/en/language.types.integer.php) if
    the [string](https://www.php.net/manual/en/language.types.string.php) is an integer numeric string and fits into the
    limits of the [int](https://www.php.net/manual/en/language.types.integer.php) type limits (as defined by
    **`[PHP\_INT\_MAX](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-max)`**), otherwise resolve to a
    [float](https://www.php.net/manual/en/language.types.float.php).

2. If the context allows leading numeric strings and the [string](https://www.php.net/manual/en/language.types.string.php)
    is one, resolve to an [int](https://www.php.net/manual/en/language.types.integer.php) if the leading part of the
    [string](https://www.php.net/manual/en/language.types.string.php) is an integer numeric string and fits into the
    limits of the [int](https://www.php.net/manual/en/language.types.integer.php) type limits (as defined by
    **`[PHP\_INT\_MAX](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-max)`**), otherwise resolve to a
    [float](https://www.php.net/manual/en/language.types.float.php).
    Additionally an error of level **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is raised.

3. The [string](https://www.php.net/manual/en/language.types.string.php) is not numeric, throw a
    [TypeError](https://www.php.net/manual/en/class.typeerror.php).


### Behavior prior to PHP 8.0.0 [¶](https://www.php.net/manual/en/language.types.numeric-strings.php\#language.types.numeric-string.prior)

Prior to PHP 8.0.0, a [string](https://www.php.net/manual/en/language.types.string.php) was considered numeric only if it
had _leading_ whitespaces, if it had
_trailing_ whitespaces then the string was considered to
be leading numeric.


Prior to PHP 8.0.0, when a string was used in a numeric context it would
perform the same steps as above with the following differences:


- The usage of a leading numeric string would raise an
**`[E\_NOTICE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-notice)`** instead of an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**.

- If the string is not numeric, an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** was
raised and the value `0` would be returned.


Prior to PHP 7.1.0, neither **`[E\_NOTICE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-notice)`**
nor **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** was raised.


`<?php
$foo = 1 + "10.5";                // $foo is float (11.5)
$foo = 1 + "-1.3e3";              // $foo is float (-1299)
$foo = 1 + "bob-1.3e3";           // TypeError as of PHP 8.0.0, $foo is integer (1) previously
$foo = 1 + "bob3";                // TypeError as of PHP 8.0.0, $foo is integer (1) previously
$foo = 1 + "10 Small Pigs";       // $foo is integer (11) and an E_WARNING is raised in PHP 8.0.0, E_NOTICE previously
$foo = 4 + "10.2 Little Piggies"; // $foo is float (14.2) and an E_WARNING is raised in PHP 8.0.0, E_NOTICE previously
$foo = "10.0 pigs " + 1;          // $foo is float (11) and an E_WARNING is raised in PHP 8.0.0, E_NOTICE previously
$foo = "10.0 pigs " + 1.0;        // $foo is float (11) and an E_WARNING is raised in PHP 8.0.0, E_NOTICE previously
?>`

Run code

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/numeric-strings.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.numeric-strings%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.numeric-strings&repo=en&redirect=https://www.php.net/manual/en/language.types.numeric-strings.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google