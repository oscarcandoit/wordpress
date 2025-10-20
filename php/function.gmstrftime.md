---
url: https://www.php.net/manual/en/function.gmstrftime.php
scraped_at: 2025-10-20T02:50:40.847Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# gmstrftime

(PHP 4, PHP 5, PHP 7, PHP 8)

gmstrftime — Format a GMT/UTC time/date according to locale settings

**Warning**

This function has been
_DEPRECATED_ as of PHP 8.1.0. Relying on this function
is highly discouraged.

Alternatives to this function include:

- [gmdate()](https://www.php.net/manual/en/function.gmdate.php)
- [IntlDateFormatter::format()](https://www.php.net/manual/en/intldateformatter.format.php)

### Description [¶](https://www.php.net/manual/en/function.gmstrftime.php\#refsect1-function.gmstrftime-description)

[#\[\\Deprecated\]](https://www.php.net/manual/en/class.deprecated.php)

**gmstrftime**([string](https://www.php.net/manual/en/language.types.string.php) `$format`, [?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$timestamp` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Behaves the same as [strftime()](https://www.php.net/manual/en/function.strftime.php) except that the
time returned is Greenwich Mean Time (GMT). For example, when run
in Eastern Standard Time (GMT -0500), the first line below prints
"Dec 31 1998 20:00:00", while the second prints "Jan 01 1999
01:00:00".


**Warning**

This function depends on operating system locale information, which might
be inconsistent with each other, or not available at all. Instead use the
[IntlDateFormatter::format()](https://www.php.net/manual/en/intldateformatter.format.php) method.


### Parameters [¶](https://www.php.net/manual/en/function.gmstrftime.php\#refsect1-function.gmstrftime-parameters)

`format`

See description in [strftime()](https://www.php.net/manual/en/function.strftime.php).


`timestamp`

The optional `timestamp` parameter is an
[int](https://www.php.net/manual/en/language.types.integer.php) Unix timestamp that defaults to the current
local time if `timestamp` is omitted or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**. In other
words, it defaults to the value of [time()](https://www.php.net/manual/en/function.time.php).

### Return Values [¶](https://www.php.net/manual/en/function.gmstrftime.php\#refsect1-function.gmstrftime-returnvalues)

Returns a string formatted according to the given format string
using the given `timestamp` or the current
local time if no timestamp is given. Month and weekday names and
other language dependent strings respect the current locale set
with [setlocale()](https://www.php.net/manual/en/function.setlocale.php).
On failure, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** is returned.


### Changelog [¶](https://www.php.net/manual/en/function.gmstrftime.php\#refsect1-function.gmstrftime-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `timestamp` is nullable now. |

### Examples [¶](https://www.php.net/manual/en/function.gmstrftime.php\#refsect1-function.gmstrftime-examples)

**Example #1 **gmstrftime()** example**

`<?php
setlocale(LC_TIME, 'en_US');
echo strftime("%b %d %Y %H:%M:%S", mktime(20, 0, 0, 12, 31, 98)) . "\n";
echo gmstrftime("%b %d %Y %H:%M:%S", mktime(20, 0, 0, 12, 31, 98)) . "\n";
?>`

### See Also [¶](https://www.php.net/manual/en/function.gmstrftime.php\#refsect1-function.gmstrftime-seealso)

- [IntlDateFormatter::format()](https://www.php.net/manual/en/intldateformatter.format.php) \- Format the date/time value as a string
- [DateTimeInterface::format()](https://www.php.net/manual/en/datetime.format.php) \- Returns date formatted according to given format
- [strftime()](https://www.php.net/manual/en/function.strftime.php) \- Format a local time/date according to locale settings

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/datetime/functions/gmstrftime.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.gmstrftime%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.gmstrftime&repo=en&redirect=https://www.php.net/manual/en/function.gmstrftime.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google