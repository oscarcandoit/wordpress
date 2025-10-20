---
url: https://www.php.net/manual/en/function.ctype-cntrl.php
scraped_at: 2025-10-20T02:54:07.773Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ctype\_cntrl

(PHP 4 >= 4.0.4, PHP 5, PHP 7, PHP 8)

ctype\_cntrl — Check for control character(s)

### Description [¶](https://www.php.net/manual/en/function.ctype-cntrl.php\#refsect1-function.ctype-cntrl-description)

**ctype\_cntrl**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$text`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Checks if all of the characters in the provided [string](https://www.php.net/manual/en/language.types.string.php),
`text`, are control characters.
Control characters are e.g. line feed, tab, escape.


### Parameters [¶](https://www.php.net/manual/en/function.ctype-cntrl.php\#refsect1-function.ctype-cntrl-parameters)

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

### Return Values [¶](https://www.php.net/manual/en/function.ctype-cntrl.php\#refsect1-function.ctype-cntrl-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if every character in `text` is
a control character from the current locale, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.
When called with an empty string the result will always be **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


### Examples [¶](https://www.php.net/manual/en/function.ctype-cntrl.php\#refsect1-function.ctype-cntrl-examples)

**Example #1 A **ctype\_cntrl()** example**

`<?php
$strings = array('string1' => "\n\r\t", 'string2' => 'arf12');
foreach ($strings as $name => $testcase) {
    if (ctype_cntrl($testcase)) {
        echo "The string '$name' consists of all control characters.\n";
    } else {
        echo "The string '$name' does not consist of all control characters.\n";
    }
}
?>`

The above example will output:

```
The string 'string1' consists of all control characters.
The string 'string2' does not consist of all control characters.
```

### See Also [¶](https://www.php.net/manual/en/function.ctype-cntrl.php\#refsect1-function.ctype-cntrl-seealso)

- [ctype\_print()](https://www.php.net/manual/en/function.ctype-print.php) \- Check for printable character(s)
- [IntlChar::iscntrl()](https://www.php.net/manual/en/intlchar.iscntrl.php) \- Check if code point is a control character

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/ctype/functions/ctype-cntrl.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.ctype-cntrl%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ctype-cntrl&repo=en&redirect=https://www.php.net/manual/en/function.ctype-cntrl.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=111625&page=function.ctype-cntrl&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111625&page=function.ctype-cntrl&vote=down "Vote down!")

2


[**_Tor_**](https://www.php.net/manual/en/function.ctype-cntrl.php#111625) [¶](https://www.php.net/manual/en/function.ctype-cntrl.php#111625)

**12 years ago**

`Returns true if bytes are in the range of \x00-\x1f or \x7f (del). Returns false if bytes are in the range of \x20-\x7e or \x80-\xff.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ctype-cntrl&repo=en&redirect=https://www.php.net/manual/en/function.ctype-cntrl.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google