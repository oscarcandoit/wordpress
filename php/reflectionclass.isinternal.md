---
url: https://www.php.net/manual/en/reflectionclass.isinternal.php
scraped_at: 2025-10-20T02:56:24.391Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ReflectionClass::isInternal

(PHP 5, PHP 7, PHP 8)

ReflectionClass::isInternal — Checks if class is defined internally by an extension, or the core

### Description [¶](https://www.php.net/manual/en/reflectionclass.isinternal.php\#refsect1-reflectionclass.isinternal-description)

public**ReflectionClass::isInternal**(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Checks if the class is defined internally by an extension, or the core, as opposed to user-defined.


### Parameters [¶](https://www.php.net/manual/en/reflectionclass.isinternal.php\#refsect1-reflectionclass.isinternal-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/reflectionclass.isinternal.php\#refsect1-reflectionclass.isinternal-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if the class is defined internally by an extension or core, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.


### Examples [¶](https://www.php.net/manual/en/reflectionclass.isinternal.php\#refsect1-reflectionclass.isinternal-examples)

**Example #1 Basic usage of **ReflectionClass::isInternal()****

`<?php
$internalclass = new ReflectionClass('ReflectionClass');
class Apple {}
$userclass = new ReflectionClass('Apple');
var_dump($internalclass->isInternal());
var_dump($userclass->isInternal());
?>`

Run code

The above example will output:

```
bool(true)
bool(false)
```

### See Also [¶](https://www.php.net/manual/en/reflectionclass.isinternal.php\#refsect1-reflectionclass.isinternal-seealso)

- [ReflectionClass::isUserDefined()](https://www.php.net/manual/en/reflectionclass.isuserdefined.php) \- Checks if user defined

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/reflection/reflectionclass/isinternal.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Freflectionclass.isinternal%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=reflectionclass.isinternal&repo=en&redirect=https://www.php.net/manual/en/reflectionclass.isinternal.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google