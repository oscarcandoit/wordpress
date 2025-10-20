---
url: https://www.php.net/manual/en/function.idate.php
scraped_at: 2025-10-20T03:01:08.929Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# idate

(PHP 5, PHP 7, PHP 8)

idate — Format a local time/date part as integer

### Description [¶](https://www.php.net/manual/en/function.idate.php\#refsect1-function.idate-description)

**idate**([string](https://www.php.net/manual/en/language.types.string.php) `$format`, [?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$timestamp` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [int](https://www.php.net/manual/en/language.types.integer.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Returns a number formatted according to the given format string using the
given integer `timestamp` or the current local time
if no timestamp is given. In other words, `timestamp`
is optional and defaults to the value of [time()](https://www.php.net/manual/en/function.time.php).


Unlike the function [date()](https://www.php.net/manual/en/function.date.php), **idate()**
accepts just one char in the `format` parameter.


### Parameters [¶](https://www.php.net/manual/en/function.idate.php\#refsect1-function.idate-parameters)

`format`

| `format` character | Description |
| --- | --- |
| `B` | Swatch Beat/Internet Time |
| `d` | Day of the month |
| `h` | Hour (12 hour format) |
| `H` | Hour (24 hour format) |
| `i` | Minutes |
| `I` (uppercase i) | returns `1` if DST is activated,<br> `0` otherwise |
| `L` (uppercase l) | returns `1` for leap year,<br> `0` otherwise |
| `m` | Month number |
| `N` | ISO-8601 day of the week ( `1` for Monday<br> through `7` for Sunday) |
| `o` | ISO-8601 year (4 digits) |
| `s` | Seconds |
| `t` | Days in current month |
| `U` | Seconds since the Unix Epoch - January 1 1970 00:00:00 UTC -<br> this is the same as [time()](https://www.php.net/manual/en/function.time.php) |
| `w` | Day of the week ( `0` on Sunday) |
| `W` | ISO-8601 week number of year, weeks starting on<br> Monday |
| `y` | Year (1 or 2 digits - check note below) |
| `Y` | Year (4 digits) |
| `z` | Day of the year |
| `Z` | Timezone offset in seconds |

**The following characters are recognized in the**
**`format` parameter string**`timestamp`

The optional `timestamp` parameter is an
[int](https://www.php.net/manual/en/language.types.integer.php) Unix timestamp that defaults to the current
local time if `timestamp` is omitted or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**. In other
words, it defaults to the value of [time()](https://www.php.net/manual/en/function.time.php).

### Return Values [¶](https://www.php.net/manual/en/function.idate.php\#refsect1-function.idate-returnvalues)

Returns an [int](https://www.php.net/manual/en/language.types.integer.php) on success, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


As **idate()** always returns an [int](https://www.php.net/manual/en/language.types.integer.php) and
as they can't start with a "0", **idate()** may return
fewer digits than you would expect. See the example below.


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.idate.php\#refsect1-function.idate-errors)

Every call to a date/time function will generate a **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**
if the time zone is not valid. See also [date\_default\_timezone\_set()](https://www.php.net/manual/en/function.date-default-timezone-set.php)

### Changelog [¶](https://www.php.net/manual/en/function.idate.php\#refsect1-function.idate-changelog)

| Version | Description |
| --- | --- |
| 8.2.0 | Adds the `N` (ISO-8601 day of the week) and<br> `o` (ISO-8601 year) format characters. |
| 8.0.0 | `timestamp` is nullable now. |

### Examples [¶](https://www.php.net/manual/en/function.idate.php\#refsect1-function.idate-examples)

**Example #1 **idate()** example**

`<?php
$timestamp = strtotime('1st January 2004'); //1072915200
// this prints the year in a two digit format
// however, as this would start with a "0", it
// only prints "4"
echo idate('y', $timestamp);
?>`

### See Also [¶](https://www.php.net/manual/en/function.idate.php\#refsect1-function.idate-seealso)

- [DateTimeInterface::format()](https://www.php.net/manual/en/datetime.format.php) \- Returns date formatted according to given format
- [date()](https://www.php.net/manual/en/function.date.php) \- Format a Unix timestamp
- [getdate()](https://www.php.net/manual/en/function.getdate.php) \- Get date/time information
- [time()](https://www.php.net/manual/en/function.time.php) \- Return current Unix timestamp

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/datetime/functions/idate.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.idate%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.idate&repo=en&redirect=https://www.php.net/manual/en/function.idate.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google