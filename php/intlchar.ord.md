---
url: https://www.php.net/manual/en/intlchar.ord.php
scraped_at: 2025-10-20T02:48:21.013Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# IntlChar::ord

(PHP 7, PHP 8)

IntlChar::ord — Return Unicode code point value of character

### Description [¶](https://www.php.net/manual/en/intlchar.ord.php\#refsect1-intlchar.ord-description)

publicstatic**IntlChar::ord**([int](https://www.php.net/manual/en/language.types.integer.php)\|[string](https://www.php.net/manual/en/language.types.string.php) `$character`): [?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php)

Returns the Unicode code point value of the given character.


This function complements [IntlChar::chr()](https://www.php.net/manual/en/intlchar.chr.php).


### Parameters [¶](https://www.php.net/manual/en/intlchar.ord.php\#refsect1-intlchar.ord-parameters)

`character`

The [int](https://www.php.net/manual/en/language.types.integer.php) codepoint value (e.g. `0x2603` for _U+2603 SNOWMAN_), or the character encoded as a UTF-8 [string](https://www.php.net/manual/en/language.types.string.php) (e.g. `"\u{2603}"`)

### Return Values [¶](https://www.php.net/manual/en/intlchar.ord.php\#refsect1-intlchar.ord-returnvalues)

Returns the Unicode code point value as an integer.


### Examples [¶](https://www.php.net/manual/en/intlchar.ord.php\#refsect1-intlchar.ord-examples)

**Example #1 Testing different code points**

`<?php
var_dump(IntlChar::ord("A"));
var_dump(IntlChar::ord(" "));
var_dump(IntlChar::ord("\u{2603}"));
?>`

The above example will output:

```
int(65)
int(32)
int(9731)
```

### See Also [¶](https://www.php.net/manual/en/intlchar.ord.php\#refsect1-intlchar.ord-seealso)

- [IntlChar::chr()](https://www.php.net/manual/en/intlchar.chr.php) \- Return Unicode character by code point value
- [mb\_ord()](https://www.php.net/manual/en/function.mb-ord.php) \- Get Unicode code point of character
- [ord()](https://www.php.net/manual/en/function.ord.php) \- Convert the first byte of a string to a value between 0 and 255

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/intl/intlchar/ord.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fintlchar.ord%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=intlchar.ord&repo=en&redirect=https://www.php.net/manual/en/intlchar.ord.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google