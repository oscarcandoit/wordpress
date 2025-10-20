---
url: https://www.php.net/manual/en/function.mktime.php
scraped_at: 2025-10-20T02:57:26.966Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mktime

(PHP 4, PHP 5, PHP 7, PHP 8)

mktime — Get Unix timestamp for a date

### Description [¶](https://www.php.net/manual/en/function.mktime.php\#refsect1-function.mktime-description)

**mktime**(

[int](https://www.php.net/manual/en/language.types.integer.php) `$hour`,

[?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$minute` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$second` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$month` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$day` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$year` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**

): [int](https://www.php.net/manual/en/language.types.integer.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Returns the Unix timestamp corresponding to the arguments
given. This timestamp is a long integer containing the number of
seconds between the Unix Epoch (January 1 1970 00:00:00 GMT) and the time
specified.


Any optional
arguments omitted or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** will be set to the current value according
to the local date and time.


**Warning**

Please note that the ordering of arguments is in an odd order:
`month`, `day`,
`year`, and not in the more reasonable order of
`year`, `month`,
`day`.


Calling **mktime()** without arguments is not supported,
and will result in an [ArgumentCountError](https://www.php.net/manual/en/class.argumentcounterror.php).
[time()](https://www.php.net/manual/en/function.time.php) can be used to get the current timestamp.


### Parameters [¶](https://www.php.net/manual/en/function.mktime.php\#refsect1-function.mktime-parameters)

`hour`

The number of the hour relative to the start of the day determined by
`month`, `day` and `year`.
Negative values reference the hour before midnight of the day in question.
Values greater than 23 reference the appropriate hour in the following day(s).


`minute`

The number of the minute relative to the start of the `hour`.
Negative values reference the minute in the previous hour.
Values greater than 59 reference the appropriate minute in the following hour(s).


`second`

The number of seconds relative to the start of the `minute`.
Negative values reference the second in the previous minute.
Values greater than 59 reference the appropriate second in the following minute(s).


`month`

The number of the month relative to the end of the previous year.
Values 1 to 12 reference the normal calendar months of the year in question.
Values less than 1 (including negative values) reference the months in the previous year in reverse order, so 0 is December, -1 is November, etc.
Values greater than 12 reference the appropriate month in the following year(s).


`day`

The number of the day relative to the end of the previous month.
Values 1 to 28, 29, 30 or 31 (depending upon the month) reference the normal days in the relevant month.
Values less than 1 (including negative values) reference the days in the previous month, so 0 is the last day of the previous month, -1 is the day before that, etc.
Values greater than the number of days in the relevant month reference the appropriate day in the following month(s).


`year`

The number of the year, may be a two or four digit value,
with values between 0-69 mapping to 2000-2069 and 70-100 to
1970-2000. On systems where time\_t is a 32bit signed integer, as
most common today, the valid range for `year`
is somewhere between 1901 and 2038.


### Return Values [¶](https://www.php.net/manual/en/function.mktime.php\#refsect1-function.mktime-returnvalues)

**mktime()** returns the Unix timestamp of the arguments
given, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if the timestamp doesn't fit in a PHP integer.


### Changelog [¶](https://www.php.net/manual/en/function.mktime.php\#refsect1-function.mktime-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `hour` is no longer optional. If you need a Unix<br> timestamp, use [time()](https://www.php.net/manual/en/function.time.php). |
| 8.0.0 | `minute`, `second`, `month`,<br> `day` and `year` are nullable now. |

### Examples [¶](https://www.php.net/manual/en/function.mktime.php\#refsect1-function.mktime-examples)

**Example #1 **mktime()** basic example**

`<?php
// Set the default timezone to use.
date_default_timezone_set('UTC');
// Prints: July 1, 2000 is on a Saturday
echo "July 1, 2000 is on a " . date("l", mktime(0, 0, 0, 7, 1, 2000));
// Prints something like: 2006-04-05T01:02:03+00:00
echo date('c', mktime(1, 2, 3, 4, 5, 2006));
?>`

**Example #2 **mktime()** example**

**mktime()** is useful for doing date arithmetic
and validation, as it will automatically calculate the correct
value for out-of-range input. For example, each of the following
lines produces the string "Jan-01-1998".


`<?php
echo date("M-d-Y", mktime(0, 0, 0, 12, 32, 1997));
echo date("M-d-Y", mktime(0, 0, 0, 13, 1, 1997));
echo date("M-d-Y", mktime(0, 0, 0, 1, 1, 1998));
echo date("M-d-Y", mktime(0, 0, 0, 1, 1, 98));
?>`

**Example #3 Last day of a month**

The last day of any given month can be expressed as the "0" day
of the next month, not the -1 day. Both of the following examples
will produce the string "The last day in Feb 2000 is: 29".


`<?php
$lastday = mktime(0, 0, 0, 3, 0, 2000);
echo 'Last day in Feb 2000 is: ', date('d', $lastday);
$lastday = mktime(0, 0, 0, 4, -31, 2000);
echo 'Last day in Feb 2000 is: ', date('d', $lastday);
?>`

### See Also [¶](https://www.php.net/manual/en/function.mktime.php\#refsect1-function.mktime-seealso)

- The [DateTimeImmutable](https://www.php.net/manual/en/class.datetimeimmutable.php) class
- [checkdate()](https://www.php.net/manual/en/function.checkdate.php) \- Validate a Gregorian date
- [gmmktime()](https://www.php.net/manual/en/function.gmmktime.php) \- Get Unix timestamp for a GMT date
- [date()](https://www.php.net/manual/en/function.date.php) \- Format a Unix timestamp
- [time()](https://www.php.net/manual/en/function.time.php) \- Return current Unix timestamp

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/datetime/functions/mktime.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.mktime%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.mktime&repo=en&redirect=https://www.php.net/manual/en/function.mktime.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google