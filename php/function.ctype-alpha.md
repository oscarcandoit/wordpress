---
url: https://www.php.net/manual/en/function.ctype-alpha.php
scraped_at: 2025-10-20T02:54:27.799Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ctype\_alpha

(PHP 4 >= 4.0.4, PHP 5, PHP 7, PHP 8)

ctype\_alpha — Check for alphabetic character(s)

### Description [¶](https://www.php.net/manual/en/function.ctype-alpha.php\#refsect1-function.ctype-alpha-description)

**ctype\_alpha**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$text`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Checks if all of the characters in the provided [string](https://www.php.net/manual/en/language.types.string.php),
`text`, are alphabetic.
In the standard `C` locale letters are just
`[A-Za-z]` and **ctype\_alpha()** is
equivalent to `(ctype_upper($text) || ctype_lower($text))`
if $text is just a single character, but other languages have letters that
are considered neither upper nor lower case.


### Parameters [¶](https://www.php.net/manual/en/function.ctype-alpha.php\#refsect1-function.ctype-alpha-parameters)

`text`

The tested string.


> **Note**:
>
> If an [int](https://www.php.net/manual/en/language.types.integer.php) between -128 and 255 inclusive is provided, it is interpreted as
> the ASCII value of a single character (negative values have 256 added in order to allow
> characters in the Extended ASCII range). Any other integer is interpreted as a string
> containing the decimal digits of the integer.

**Warning**

As of PHP 8.1.0, passing a non-string argument is deprecated.
In the future, the argument will be interpreted as a string instead of an ASCII codepoint.
Depending on the intended behavior, the argument should either be cast to [string](https://www.php.net/manual/en/language.types.string.php)
or an explicit call to [chr()](https://www.php.net/manual/en/function.chr.php) should be made.

### Return Values [¶](https://www.php.net/manual/en/function.ctype-alpha.php\#refsect1-function.ctype-alpha-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if every character in `text` is
a letter from the current locale, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.
When called with an empty string the result will always be **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


### Examples [¶](https://www.php.net/manual/en/function.ctype-alpha.php\#refsect1-function.ctype-alpha-examples)

**Example #1 A **ctype\_alpha()** example (using the default locale)**

`<?php
$strings = array('KjgWZC', 'arf12');
foreach ($strings as $testcase) {
    if (ctype_alpha($testcase)) {
        echo "The string $testcase consists of all letters.\n";
    } else {
        echo "The string $testcase does not consist of all letters.\n";
    }
}
?>`

The above example will output:

```
The string KjgWZC consists of all letters.
The string arf12 does not consist of all letters.
```

### See Also [¶](https://www.php.net/manual/en/function.ctype-alpha.php\#refsect1-function.ctype-alpha-seealso)

- [ctype\_upper()](https://www.php.net/manual/en/function.ctype-upper.php) \- Check for uppercase character(s)
- [ctype\_lower()](https://www.php.net/manual/en/function.ctype-lower.php) \- Check for lowercase character(s)
- [setlocale()](https://www.php.net/manual/en/function.setlocale.php) \- Set locale information
- [IntlChar::isalpha()](https://www.php.net/manual/en/intlchar.isalpha.php) \- Check if code point is a letter character

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/ctype/functions/ctype-alpha.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.ctype-alpha%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ctype-alpha&repo=en&redirect=https://www.php.net/manual/en/function.ctype-alpha.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google