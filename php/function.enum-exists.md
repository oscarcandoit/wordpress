---
url: https://www.php.net/manual/en/function.enum-exists.php
scraped_at: 2025-10-20T02:53:28.061Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# enum\_exists

(PHP 8 >= 8.1.0)

enum\_exists — Checks if the enum has been defined

### Description [¶](https://www.php.net/manual/en/function.enum-exists.php\#refsect1-function.enum-exists-description)

**enum\_exists**([string](https://www.php.net/manual/en/language.types.string.php) `$enum`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$autoload` = **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**): [bool](https://www.php.net/manual/en/language.types.boolean.php)

This function checks whether or not the given [enum](https://www.php.net/manual/en/language.enumerations.php) has been defined.


### Parameters [¶](https://www.php.net/manual/en/function.enum-exists.php\#refsect1-function.enum-exists-parameters)

`enum`

The enum name. The name is matched in a case-insensitive manner.


`autoload`

Whether to [autoload](https://www.php.net/manual/en/language.oop5.autoload.php)
if not already loaded.


### Return Values [¶](https://www.php.net/manual/en/function.enum-exists.php\#refsect1-function.enum-exists-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if `enum` is a defined enum,
**`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.


### Examples [¶](https://www.php.net/manual/en/function.enum-exists.php\#refsect1-function.enum-exists-examples)

**Example #1 **enum\_exists()** example**

`<?php
// Check that the enum exists before trying to use it
if (enum_exists(Suit::class)) {
    $myclass = Suit::Hearts;
}
?>`

### See Also [¶](https://www.php.net/manual/en/function.enum-exists.php\#refsect1-function.enum-exists-seealso)

- [function\_exists()](https://www.php.net/manual/en/function.function-exists.php) \- Return true if the given function has been defined
- [class\_exists()](https://www.php.net/manual/en/function.class-exists.php) \- Checks if the class has been defined
- [interface\_exists()](https://www.php.net/manual/en/function.interface-exists.php) \- Checks if the interface has been defined
- [get\_declared\_classes()](https://www.php.net/manual/en/function.get-declared-classes.php) \- Returns an array with the name of the defined classes

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/classobj/functions/enum-exists.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.enum-exists%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.enum-exists&repo=en&redirect=https://www.php.net/manual/en/function.enum-exists.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google