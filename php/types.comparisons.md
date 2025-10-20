---
url: https://www.php.net/manual/en/types.comparisons.php
scraped_at: 2025-10-20T02:35:02.406Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# PHP type comparison tables [¶](https://www.php.net/manual/en/types.comparisons.php\#types.comparisons)

The following tables demonstrate behaviors of PHP
[types](https://www.php.net/manual/en/language.types.php) and
[comparison \\
operators](https://www.php.net/manual/en/language.operators.comparison.php), for both loose and strict comparisons. This
supplemental is also related to the manual section on
[type juggling](https://www.php.net/manual/en/language.types.type-juggling.php).
Inspiration was provided by various user comments and by the work over at
[» BlueShoes](http://www.blueshoes.org/en/developer/php_cheat_sheet/).


Before utilizing these tables, it's important to understand types and their
meanings. For example, `"42"` is a [string](https://www.php.net/manual/en/language.types.string.php)
while `42` is an [int](https://www.php.net/manual/en/language.types.integer.php). **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** is a
[bool](https://www.php.net/manual/en/language.types.boolean.php) while `"false"` is a
[string](https://www.php.net/manual/en/language.types.string.php).


> **Note**:
>
>
> HTML Forms do not pass integers, floats, or booleans; they pass strings.
> To find out if a string is numeric, you may use
> [is\_numeric()](https://www.php.net/manual/en/function.is-numeric.php).

> **Note**:
>
>
> Simply doing `if ($x)` while $x is
> undefined will generate an error of level **`[E\_NOTICE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-notice)`**.
> Instead, consider using [empty()](https://www.php.net/manual/en/function.empty.php) or
> [isset()](https://www.php.net/manual/en/function.isset.php) and/or initialize your variables.

> **Note**:
>
>
> Some numeric operations can result in a value represented by the constant
> **`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`**. Any loose or strict comparisons of this value
> against any other value, including itself, but except **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, will have a result of **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.
> (i.e. `NAN != NAN` and `NAN !== NAN`)
> Examples of operations that produce **`[NAN](https://www.php.net/manual/en/math.constants.php#constant.nan)`** include
> `sqrt(-1)`, `asin(2)`, and
> `acosh(0)`.

| Expression | [gettype()](https://www.php.net/manual/en/function.gettype.php) | [empty()](https://www.php.net/manual/en/function.empty.php) | [is\_null()](https://www.php.net/manual/en/function.is-null.php) | [isset()](https://www.php.net/manual/en/function.isset.php) | [bool](https://www.php.net/manual/en/language.types.boolean.php) : `if($x)` |
| --- | --- | --- | --- | --- | --- |
| `$x = "";` | [string](https://www.php.net/manual/en/language.types.string.php) | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `$x = null;` | [NULL](https://www.php.net/manual/en/language.types.null.php) | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `var $x;` | [NULL](https://www.php.net/manual/en/language.types.null.php) | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| $x is undefined | [NULL](https://www.php.net/manual/en/language.types.null.php) | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `$x = [];` | [array](https://www.php.net/manual/en/language.types.array.php) | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `$x = ['a', 'b'];` | [array](https://www.php.net/manual/en/language.types.array.php) | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |
| `$x = false;` | [bool](https://www.php.net/manual/en/language.types.boolean.php) | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `$x = true;` | [bool](https://www.php.net/manual/en/language.types.boolean.php) | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |
| `$x = 1;` | [int](https://www.php.net/manual/en/language.types.integer.php) | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |
| `$x = 42;` | [int](https://www.php.net/manual/en/language.types.integer.php) | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |
| `$x = 0;` | [int](https://www.php.net/manual/en/language.types.integer.php) | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `$x = -1;` | [int](https://www.php.net/manual/en/language.types.integer.php) | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |
| `$x = "1";` | [string](https://www.php.net/manual/en/language.types.string.php) | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |
| `$x = "0";` | [string](https://www.php.net/manual/en/language.types.string.php) | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `$x = "-1";` | [string](https://www.php.net/manual/en/language.types.string.php) | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |
| `$x = "php";` | [string](https://www.php.net/manual/en/language.types.string.php) | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |
| `$x = "true";` | [string](https://www.php.net/manual/en/language.types.string.php) | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |
| `$x = "false";` | [string](https://www.php.net/manual/en/language.types.string.php) | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |

**Comparisons of $x with PHP functions**

|  | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | `1` | `0` | `-1` | `"1"` | `"0"` | `"-1"` | **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** | `[]` | `"php"` | `""` |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |
| `1` | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `0` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**\* | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**\* |
| `-1` | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `"1"` | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `"0"` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `"-1"` | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |
| `[]` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `"php"` | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**\* | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `""` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**\* | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |

**Loose comparisons with `==`**

\\* **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** prior to PHP 8.0.0.


|  | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | `1` | `0` | `-1` | `"1"` | `"0"` | `"-1"` | **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** | `[]` | `"php"` | `""` |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `1` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `0` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `-1` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `"1"` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `"0"` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `"-1"` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `[]` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `"php"` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** |
| `""` | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** | **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** |

**Strict comparisons with `===`**

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/appendices/comparisons.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ftypes.comparisons%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=types.comparisons&repo=en&redirect=https://www.php.net/manual/en/types.comparisons.php)

### User Contributed Notes 8 notes

[up](https://www.php.net/manual/vote-note.php?id=96215&page=types.comparisons&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96215&page=types.comparisons&vote=down "Vote down!")

56


[**_php at benizi dot com_**](https://www.php.net/manual/en/types.comparisons.php#96215) [¶](https://www.php.net/manual/en/types.comparisons.php#96215)

**15 years ago**

`It's interesting to note that 'empty()' and 'boolean : if($x)'
are paired as logical opposites, as are 'is_null()' and 'isset()'.`

[up](https://www.php.net/manual/vote-note.php?id=60202&page=types.comparisons&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60202&page=types.comparisons&vote=down "Vote down!")

25


[**_Jan_**](https://www.php.net/manual/en/types.comparisons.php#60202) [¶](https://www.php.net/manual/en/types.comparisons.php#60202)

**19 years ago**

`Note that php comparison is not transitive:
"php" == 0 => true
0 == null => true
null == "php" => false`

[up](https://www.php.net/manual/vote-note.php?id=77093&page=types.comparisons&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77093&page=types.comparisons&vote=down "Vote down!")

23


[**_frank_**](https://www.php.net/manual/en/types.comparisons.php#77093) [¶](https://www.php.net/manual/en/types.comparisons.php#77093)

**18 years ago**

`A comparison table for <=,<,=>,> would be nice...
Following are TRUE (tested PHP4&5):
NULL <= -1
NULL <= 0
NULL <= 1
!(NULL >= -1)
NULL >= 0
!(NULL >= 1)
That was a surprise for me (and it is not like SQL, I would like to have the option to have SQL semantics with NULL...).`

[up](https://www.php.net/manual/vote-note.php?id=95141&page=types.comparisons&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95141&page=types.comparisons&vote=down "Vote down!")

10


[**_edgar at goodforall dot eu_**](https://www.php.net/manual/en/types.comparisons.php#95141) [¶](https://www.php.net/manual/en/types.comparisons.php#95141)

**15 years ago**

`Some function to write out your own comparisson table in tsv format. Can be easily modified to add more testcases and/or binary functions. It will test all comparables against each other with all functions.
<?php
$funcs = array(
        /* Testing equality */
        'eq' => '==',
        'ne' => '!=',
        'gt' => '>',
        'lt' => '<',
        'ne2' => '<>',
        'lte' => '<=',
        'gte' => '>=',
        /* Testing identity */
        'id' => '===',
        'nid' => '!=='
);
class Test {
        protected $a;
        public $b;
        public function __construct($a,$b){
                $this->a = $a;
                $this->b = $b;
        }
        public function getab(){
                return $this->a.",". $this->b;
        }
}
$tst1 = new Test(1,2);
$tst2 = new Test(1,2);
$tst3 = new Test(2,2);
$tst4 = new Test(1,1);
$arr1 = array(1,2,3);
$arr2 = array(2,3,4);
$arr3 = array('a','b','c','d');
$arr4 = array('a','b','c');
$arr5 = array();
$comp1 = array(
        'ints' => array(-1,0,1,2),
        'floats' => array(-1.1,0.0,1.1,2.0),
        'string' => array('str', 'str1', '', '1'),
        'bools' => array(true, false),
        'null' => array(null),
        'objects' => array($tst1,$tst2,$tst3,$tst4),
        'arrays' => array($arr1, $arr2, $arr3, $arr4, $arr5)
);
$fbody = array();
foreach($funcs as $name => $op){
        $fbody[$name] = create_function('$a,$b', 'return $a ' . $op . ' $b;');
}
$table = array(array('function', 'comp1', 'comp2', 'f comp1 comp2', 'type'));
/* Do comparisons */
$comp2  = array();
foreach($comp1 as $type => $val){
        $comp2[$type] = $val;
}
foreach($comp1 as $key1 => $val1){
        foreach($comp2 as $key2 => $val2){
                addTableEntry($key1, $key2, $val1, $val2);
        }
}
$out = '';
foreach($table as $row){
        $out .= sprintf("%-20s\t%-20s\t%-20s\t%-20s\t%-20s\n", $row[0], $row[1], $row[2], $row[3], $row[4]);
}
print $out;
exit;
function addTableEntry($n1, $n2, $comp1, $comp2){
        global $table, $fbody;
        foreach($fbody as $fname => $func){
                        foreach($comp1 as $val1){
foreach($comp2 as $val2){
                                        $val = $func($val1,$val2);
                                                $table[] = array($fname, gettype($val1) . ' => ' . sprintval($val1), gettype($val2) .' => ' . sprintval($val2), gettype($val) . ' => ' . sprintval($val), gettype($val1) . "-" . gettype($val2) . '-' . $fname);
                                        }
                        }
        }
}
function sprintval($val){
        if(is_object($val)){
                return 'object-' . $val->getab();
        }
        if(is_array($val)){
                return implode(',', $val);
        }
        if(is_bool($val)){
                if($val){
                        return 'true';
                }
                return 'false';
        }
        return strval($val);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=115681&page=types.comparisons&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115681&page=types.comparisons&vote=down "Vote down!")

8


[**_blue dot hirano at gmail dot com_**](https://www.php.net/manual/en/types.comparisons.php#115681) [¶](https://www.php.net/manual/en/types.comparisons.php#115681)

**11 years ago**

`The truth tables really ought to be colorized; they're very hard to read as they are right now (just big arrays of TRUE and FALSE).
Also, something to consider: clustering the values which compare similarly (like is done on qntm.org/equality) would make the table easier to read as well. (This can be done simply by hand by rearranging the order of headings to bring related values closer together).`

[up](https://www.php.net/manual/vote-note.php?id=55161&page=types.comparisons&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=55161&page=types.comparisons&vote=down "Vote down!")

3


[**_jerryschwartz at comfortable dot com_**](https://www.php.net/manual/en/types.comparisons.php#55161) [¶](https://www.php.net/manual/en/types.comparisons.php#55161)

**20 years ago**

`In some languages, a boolean is promoted to an integer (with a value of 1 or -1, typically) if used in an expression with an integer. I found that PHP has it both ways:
If you add a boolean with a value of true to an integer with a value of 3, the result will be 4 (because the boolean is cast as an integer).
On the other hand, if you test a boolean with a value of true for equality with an integer with a value of three, the result will be true (because the integer is cast as a boolean).
Surprisingly, at first glance, if you use either < or > as the comparison operator the result is always false (again, because the integer as cast as a boolean, and true is neither greater nor less than true).`

[up](https://www.php.net/manual/vote-note.php?id=128737&page=types.comparisons&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128737&page=types.comparisons&vote=down "Vote down!")

0


[**_Jeroen_**](https://www.php.net/manual/en/types.comparisons.php#128737) [¶](https://www.php.net/manual/en/types.comparisons.php#128737)

**2 years ago**

`Be aware of the difference between checking the *value* of an array item, and checking the *existence* of an array item:
<?php
$arr = [\
'x' => 0,\
'y' => null,\
];
isset($arr['x']); // true, same as isset(0)
isset($arr['y']); // false, same as isset(null)
array_key_exists('y', $arr); // true, though the value is null
array_key_exists('z', $arr); // false`

[up](https://www.php.net/manual/vote-note.php?id=122567&page=types.comparisons&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122567&page=types.comparisons&vote=down "Vote down!")

 -2


[**_mark at theanti dot social_**](https://www.php.net/manual/en/types.comparisons.php#122567) [¶](https://www.php.net/manual/en/types.comparisons.php#122567)

**7 years ago**

`There is also 0.0 which is not identical to 0.
$x = 0.0;
gettype($x); // double
empty($x); // true
is_null($x); //false
isset($x); // true
is_numeric($x); // true
$x ? true : false; // false
$x == 0; // true
$x == "0"; // true
$x == "0.0"; // true
$x == false; // true
$x == null; // true
$x === 0; // false
$x === false; // false
$x === null; // false
$x === "0"; // false
$x === "0.0"; // false`

[＋add a note](https://www.php.net/manual/add-note.php?sect=types.comparisons&repo=en&redirect=https://www.php.net/manual/en/types.comparisons.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google