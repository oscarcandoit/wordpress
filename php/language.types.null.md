---
url: https://www.php.net/manual/en/language.types.null.php
scraped_at: 2025-10-20T02:33:17.434Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## NULL [¶](https://www.php.net/manual/en/language.types.null.php\#language.types.null)

The [null](https://www.php.net/manual/en/language.types.null.php) type is PHP's unit type, i.e. it has only one value:
**`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**.


Undefined, and [unset()](https://www.php.net/manual/en/function.unset.php) variables will resolve to the
value **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**.


### Syntax [¶](https://www.php.net/manual/en/language.types.null.php\#language.types.null.syntax)

There is only one value of type [null](https://www.php.net/manual/en/language.types.null.php), and that is the
case-insensitive constant **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**.


`<?php
$var = NULL;
?>`

Run code

### Casting to **`[null](https://www.php.net/manual/en/reserved.constants.php\#constant.null)`** [¶](https://www.php.net/manual/en/language.types.null.php\#language.types.null.casting)

**Warning**

This feature has been
_DEPRECATED_ as of PHP 7.2.0, and _REMOVED_ as of PHP 8.0.0. Relying on this feature
is highly discouraged.

Casting a variable to [null](https://www.php.net/manual/en/language.types.null.php) using `(unset) $var`
will _not_ remove the variable or unset its value.
It will only return a **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** value.


### See Also

- [is\_null()](https://www.php.net/manual/en/function.is-null.php)
- [unset()](https://www.php.net/manual/en/function.unset.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/null.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.null%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.null&repo=en&redirect=https://www.php.net/manual/en/language.types.null.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=103620&page=language.types.null&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103620&page=language.types.null&vote=down "Vote down!")

69


[**_quickpick_**](https://www.php.net/manual/en/language.types.null.php#103620) [¶](https://www.php.net/manual/en/language.types.null.php#103620)

**14 years ago**

`Note: empty array is converted to null by non-strict equal '==' comparison. Use is_null() or '===' if there is possible of getting empty array.
$a = array();
$a == null  <== return true
$a === null < == return false
is_null($a) <== return false`

[up](https://www.php.net/manual/vote-note.php?id=121995&page=language.types.null&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121995&page=language.types.null&vote=down "Vote down!")

41


[**_Hayley Watson_**](https://www.php.net/manual/en/language.types.null.php#121995) [¶](https://www.php.net/manual/en/language.types.null.php#121995)

**7 years ago**

`NULL is supposed to indicate the absence of a value, rather than being thought of as a value itself. It's the empty slot, it's the missing information, it's the unanswered question. It's not a jumped-up zero or empty set.
This is why a variable containing a NULL is considered to be unset: it doesn't have a value. Setting a variable to NULL is telling it to forget its value without providing a replacement value to remember instead. The variable remains so that you can give it a proper value to remember later; this is especially important when the variable is an array element or object property.
It's a bit of semantic awkwardness to speak of a "null value", but if a variable can exist without having a value, the language and implementation have to have something to represent that situation. Because someone will ask. If only to see if the slot has been filled.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.null&repo=en&redirect=https://www.php.net/manual/en/language.types.null.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google