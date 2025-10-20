---
url: https://www.php.net/manual/en/function.strftime.php
scraped_at: 2025-10-20T03:00:47.702Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# strftime

(PHP 4, PHP 5, PHP 7, PHP 8)

strftime — Format a local time/date according to locale settings

**Warning**

This function has been
_DEPRECATED_ as of PHP 8.1.0. Relying on this function
is highly discouraged.

Alternatives to this function include:

- [date()](https://www.php.net/manual/en/function.date.php)
- [IntlDateFormatter::format()](https://www.php.net/manual/en/intldateformatter.format.php)

### Description [¶](https://www.php.net/manual/en/function.strftime.php\#refsect1-function.strftime-description)

[#\[\\Deprecated\]](https://www.php.net/manual/en/class.deprecated.php)

**strftime**([string](https://www.php.net/manual/en/language.types.string.php) `$format`, [?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$timestamp` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Format the time and/or date according to locale settings. Month and weekday
names and other language-dependent strings respect the current locale set
with [setlocale()](https://www.php.net/manual/en/function.setlocale.php).


**Warning**

Not all conversion specifiers may be supported by your C library, in which
case they will not be supported by PHP's **strftime()**.
Additionally, not all platforms support negative timestamps, so your
date range may be limited to no earlier than the Unix epoch. This means that
%e, %T, %R and, %D (and possibly others) - as well as dates prior to
`Jan 1, 1970` \- will not work on Windows, some Linux
distributions, and a few other operating systems. For Windows systems, a
complete overview of supported conversion specifiers can be found at
[» MSDN](http://msdn.microsoft.com/en-us/library/fe06s4ak.aspx).
Instead use the
[IntlDateFormatter::format()](https://www.php.net/manual/en/intldateformatter.format.php) method.


### Parameters [¶](https://www.php.net/manual/en/function.strftime.php\#refsect1-function.strftime-parameters)

`format`

| `format` | Description | Example returned values |
| --- | --- | --- |
| _Day_ | \-\-\- | \-\-\- |
| `%a` | An abbreviated textual representation of the day | `Sun` through `Sat` |
| `%A` | A full textual representation of the day | `Sunday` through `Saturday` |
| `%d` | Two-digit day of the month (with leading zeros) | `01` to `31` |
| `%e` | Day of the month, with a space preceding single digits. Not <br> implemented as described on Windows. See below for more information. | ` 1` to `31` |
| `%j` | Day of the year, 3 digits with leading zeros | `001` to `366` |
| `%u` | ISO-8601 numeric representation of the day of the week | `1` (for Monday) through `7` (for Sunday) |
| `%w` | Numeric representation of the day of the week | `0` (for Sunday) through `6` (for Saturday) |
| _Week_ | \-\-\- | \-\-\- |
| `%U` | Week number of the given year, starting with the first<br> Sunday as the first week | `13` (for the 13th full week of the year) |
| `%V` | ISO-8601:1988 week number of the given year, starting with<br> the first week of the year with at least 4 weekdays, with Monday<br> being the start of the week | `01` through `53` (where 53<br> accounts for an overlapping week) |
| `%W` | A numeric representation of the week of the year, starting<br> with the first Monday as the first week | `46` (for the 46th week of the year beginning<br> with a Monday) |
| _Month_ | \-\-\- | \-\-\- |
| `%b` | Abbreviated month name, based on the locale | `Jan` through `Dec` |
| `%B` | Full month name, based on the locale | `January` through `December` |
| `%h` | Abbreviated month name, based on the locale (an alias of %b) | `Jan` through `Dec` |
| `%m` | Two digit representation of the month | `01` (for January) through `12` (for December) |
| _Year_ | \-\-\- | \-\-\- |
| `%C` | Two digit representation of the century (year divided by 100, truncated to an integer) | `19` for the 20th Century |
| `%g` | Two digit representation of the year going by ISO-8601:1988 standards (see %V) | Example: `09` for the week of January 6, 2009 |
| `%G` | The full four-digit version of %g | Example: `2008` for the week of January 3, 2009 |
| `%y` | Two digit representation of the year | Example: `09` for 2009, `79` for 1979 |
| `%Y` | Four digit representation for the year | Example: `2038` |
| _Time_ | \-\-\- | \-\-\- |
| `%H` | Two digit representation of the hour in 24-hour format | `00` through `23` |
| `%k` | Hour in 24-hour format, with a space preceding single digits | ` 0` through `23` |
| `%I` | Two digit representation of the hour in 12-hour format | `01` through `12` |
| `%l (lower-case 'L')` | Hour in 12-hour format, with a space preceding single digits | ` 1` through `12` |
| `%M` | Two digit representation of the minute | `00` through `59` |
| `%p` | UPPER-CASE 'AM' or 'PM' based on the given time | Example: `AM` for 00:31,<br> `PM` for 22:23. The exact result depends on the<br> Operating System, and they can also return lower-case variants, or<br> variants with dots (such as `a.m.`). |
| `%P` | lower-case 'am' or 'pm' based on the given time | Example: `am` for 00:31,<br> `pm` for 22:23. Not supported by all Operating<br> Systems. |
| `%r` | Same as "%I:%M:%S %p" | Example: `09:34:17 PM` for 21:34:17 |
| `%R` | Same as "%H:%M" | Example: `00:35` for 12:35 AM, `16:44` for 4:44 PM |
| `%S` | Two digit representation of the second | `00` through `59` |
| `%T` | Same as "%H:%M:%S" | Example: `21:34:17` for 09:34:17 PM |
| `%X` | Preferred time representation based on locale, without the date | Example: `03:59:16` or `15:59:16` |
| `%z` | The time zone offset. Not implemented as described on<br> Windows. See below for more information. | Example: `-0500` for US Eastern Time |
| `%Z` | The time zone abbreviation. Not implemented as described on<br> Windows. See below for more information. | Example: `EST` for Eastern Time |
| _Time and Date Stamps_ | \-\-\- | \-\-\- |
| `%c` | Preferred date and time stamp based on locale | Example: `Tue Feb  5 00:45:10 2009` for<br> February 5, 2009 at 12:45:10 AM |
| `%D` | Same as "%m/%d/%y" | Example: `02/05/09` for February 5, 2009 |
| `%F` | Same as "%Y-%m-%d" (commonly used in database datestamps) | Example: `2009-02-05` for February 5, 2009 |
| `%s` | Unix Epoch Time timestamp (same as the [time()](https://www.php.net/manual/en/function.time.php)<br> function) | Example: `305815200` for September 10, 1979 08:40:00 AM |
| `%x` | Preferred date representation based on locale, without the time | Example: `02/05/09` for February 5, 2009 |
| _Miscellaneous_ | \-\-\- | \-\-\- |
| `%n` | A newline character ("\\n") | \-\-\- |
| `%t` | A Tab character ("\\t") | \-\-\- |
| `%%` | A literal percentage character ("%") | \-\-\- |

**The following characters are recognized in the**
**`format` parameter string**

**Warning**

Contrary to ISO-9899:1999, Sun Solaris starts with Sunday as 1. As a
result, `%u` may not function as described in this
manual.


**Warning**

_Windows only:_

The `%e` modifier is not supported in the Windows
implementation of this function. To achieve this value, the
`%#d` modifier can be used instead. The example below
illustrates how to write a cross platform compatible function.


The `%z` and `%Z` modifiers both
return the time zone name instead of the offset or abbreviation.


**Warning**

_macOS and musl only:_ The `%P` modifier
is not supported in the macOS implementation of this function.


`timestamp`

The optional `timestamp` parameter is an
[int](https://www.php.net/manual/en/language.types.integer.php) Unix timestamp that defaults to the current
local time if `timestamp` is omitted or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**. In other
words, it defaults to the value of [time()](https://www.php.net/manual/en/function.time.php).

### Return Values [¶](https://www.php.net/manual/en/function.strftime.php\#refsect1-function.strftime-returnvalues)

Returns a string formatted according `format`
using the given `timestamp` or the current
local time if no timestamp is given. Month and weekday names and
other language-dependent strings respect the current locale set
with [setlocale()](https://www.php.net/manual/en/function.setlocale.php).
The function returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if `format` is empty, contains unsupported
conversion specifiers, or if the length of the returned string would be greater than
`4095`.


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.strftime.php\#refsect1-function.strftime-errors)

Every call to a date/time function will generate a **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**
if the time zone is not valid. See also [date\_default\_timezone\_set()](https://www.php.net/manual/en/function.date-default-timezone-set.php)

As the output is dependent upon the underlying C library, some conversion
specifiers are not supported. On Windows, supplying unknown conversion
specifiers will result in 5 **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** messages and
return **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**. On other operating systems you may not get any
**`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** messages and the output may contain the
conversion specifiers unconverted.


### Changelog [¶](https://www.php.net/manual/en/function.strftime.php\#refsect1-function.strftime-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `timestamp` is nullable now. |

### Examples [¶](https://www.php.net/manual/en/function.strftime.php\#refsect1-function.strftime-examples)

This example will work if you have the respective locales installed
in your system.


**Example #1 **strftime()** locale examples**

`<?php
setlocale(LC_TIME, "C");
echo strftime("%A");
setlocale(LC_TIME, "fi_FI");
echo strftime(" in Finnish is %A,");
setlocale(LC_TIME, "fr_FR");
echo strftime(" in French %A and");
setlocale(LC_TIME, "de_DE");
echo strftime(" in German %A.\n");
?>`

**Example #2 ISO 8601:1988 week number example**

`<?php
/*     December 2002 / January 2003
ISOWk  M   Tu  W   Thu F   Sa  Su
----- ----------------------------
51     16  17  18  19  20  21  22
52     23  24  25  26  27  28  29
1      30  31   1   2   3   4   5
2       6   7   8   9  10  11  12
3      13  14  15  16  17  18  19   */
// Outputs: 12/28/2002 - %V,%G,%Y = 52,2002,2002
echo "12/28/2002 - %V,%G,%Y = " . strftime("%V,%G,%Y", strtotime("12/28/2002")) . "\n";
// Outputs: 12/30/2002 - %V,%G,%Y = 1,2003,2002
echo "12/30/2002 - %V,%G,%Y = " . strftime("%V,%G,%Y", strtotime("12/30/2002")) . "\n";
// Outputs: 1/3/2003 - %V,%G,%Y = 1,2003,2003
echo "1/3/2003 - %V,%G,%Y = " . strftime("%V,%G,%Y",strtotime("1/3/2003")) . "\n";
// Outputs: 1/10/2003 - %V,%G,%Y = 2,2003,2003
echo "1/10/2003 - %V,%G,%Y = " . strftime("%V,%G,%Y",strtotime("1/10/2003")) . "\n";
/*     December 2004 / January 2005
ISOWk  M   Tu  W   Thu F   Sa  Su
----- ----------------------------
51     13  14  15  16  17  18  19
52     20  21  22  23  24  25  26
53     27  28  29  30  31   1   2
1       3   4   5   6   7   8   9
2      10  11  12  13  14  15  16   */
// Outputs: 12/23/2004 - %V,%G,%Y = 52,2004,2004
echo "12/23/2004 - %V,%G,%Y = " . strftime("%V,%G,%Y",strtotime("12/23/2004")) . "\n";
// Outputs: 12/31/2004 - %V,%G,%Y = 53,2004,2004
echo "12/31/2004 - %V,%G,%Y = " . strftime("%V,%G,%Y",strtotime("12/31/2004")) . "\n";
// Outputs: 1/2/2005 - %V,%G,%Y = 53,2004,2005
echo "1/2/2005 - %V,%G,%Y = " . strftime("%V,%G,%Y",strtotime("1/2/2005")) . "\n";
// Outputs: 1/3/2005 - %V,%G,%Y = 1,2005,2005
echo "1/3/2005 - %V,%G,%Y = " . strftime("%V,%G,%Y",strtotime("1/3/2005")) . "\n";
?>`

**Example #3 Cross platform compatible example using the `%e` modifier**

`<?php
// Jan 1: results in: '%e%1%' (%%, e, %%, %e, %%)
$format = '%%e%%%e%%';
// Check for Windows to find and replace the %e
// modifier correctly
if (strtoupper(substr(PHP_OS, 0, 3)) == 'WIN') {
    $format = preg_replace('#(?<!%)((?:%%)*)%e#', '\1%#d', $format);
}
echo strftime($format);
?>`

**Example #4 Display all known and unknown formats**

`<?php
// Describe the formats
$strftimeFormats = array(
    'A' => 'A full textual representation of the day',
    'B' => 'Full month name, based on the locale',
    'C' => 'Two digit representation of the century (year divided by 100, truncated to an integer)',
    'D' => 'Same as "%m/%d/%y"',
    'E' => '',
    'F' => 'Same as "%Y-%m-%d"',
    'G' => 'The full four-digit version of %g',
    'H' => 'Two digit representation of the hour in 24-hour format',
    'I' => 'Two digit representation of the hour in 12-hour format',
    'J' => '',
    'K' => '',
    'L' => '',
    'M' => 'Two digit representation of the minute',
    'N' => '',
    'O' => '',
    'P' => 'lower-case "am" or "pm" based on the given time',
    'Q' => '',
    'R' => 'Same as "%H:%M"',
    'S' => 'Two digit representation of the second',
    'T' => 'Same as "%H:%M:%S"',
    'U' => 'Week number of the given year, starting with the first Sunday as the first week',
    'V' => 'ISO-8601:1988 week number of the given year, starting with the first week of the year with at least 4 weekdays, with Monday being the start of the week',
    'W' => 'A numeric representation of the week of the year, starting with the first Monday as the first week',
    'X' => 'Preferred time representation based on locale, without the date',
    'Y' => 'Four digit representation for the year',
    'Z' => 'The time zone offset/abbreviation option NOT given by %z (depends on operating system)',
    'a' => 'An abbreviated textual representation of the day',
    'b' => 'Abbreviated month name, based on the locale',
    'c' => 'Preferred date and time stamp based on local',
    'd' => 'Two-digit day of the month (with leading zeros)',
    'e' => 'Day of the month, with a space preceding single digits',
    'f' => '',
    'g' => 'Two digit representation of the year going by ISO-8601:1988 standards (see %V)',
    'h' => 'Abbreviated month name, based on the locale (an alias of %b)',
    'i' => '',
    'j' => 'Day of the year, 3 digits with leading zeros',
    'k' => 'Hour in 24-hour format, with a space preceding single digits',
    'l' => 'Hour in 12-hour format, with a space preceding single digits',
    'm' => 'Two digit representation of the month',
    'n' => 'A newline character ("\n")',
    'o' => '',
    'p' => 'UPPER-CASE "AM" or "PM" based on the given time',
    'q' => '',
    'r' => 'Same as "%I:%M:%S %p"',
    's' => 'Unix Epoch Time timestamp',
    't' => 'A Tab character ("\t")',
    'u' => 'ISO-8601 numeric representation of the day of the week',
    'v' => '',
    'w' => 'Numeric representation of the day of the week',
    'x' => 'Preferred date representation based on locale, without the time',
    'y' => 'Two digit representation of the year',
    'z' => 'Either the time zone offset from UTC or the abbreviation (depends on operating system)',
    '%' => 'A literal percentage character ("%")',
);
// Results
$strftimeValues = array();
// Evaluate the formats whilst suppressing any errors
foreach ($strftimeFormats as $format => $description) {
    if (false !== ($value = @strftime("%{$format}"))) {
        $strftimeValues[$format] = $value;
    }
}
// Find the longest value
$maxValueLength = 2 + max(array_map('strlen', $strftimeValues));
// Report known formats
foreach ($strftimeValues as $format => $value) {
    echo "Known format   : '{$format}' = ", str_pad("'{$value}'", $maxValueLength), " ( {$strftimeFormats[$format]} )\n";
}
// Report unknown formats
foreach (array_diff_key($strftimeFormats, $strftimeValues) as $format => $description) {
    echo "Unknown format : '{$format}'   ", str_pad(' ', $maxValueLength), ($description ? " ( {$description} )" : ''), "\n";
}
?>`

The above example will output
something similar to:

```
Known format   : 'A' = 'Friday'            ( A full textual representation of the day )
Known format   : 'B' = 'December'          ( Full month name, based on the locale )
Known format   : 'H' = '11'                ( Two digit representation of the hour in 24-hour format )
Known format   : 'I' = '11'                ( Two digit representation of the hour in 12-hour format )
Known format   : 'M' = '24'                ( Two digit representation of the minute )
Known format   : 'S' = '44'                ( Two digit representation of the second )
Known format   : 'U' = '48'                ( Week number of the given year, starting with the first Sunday as the first week )
Known format   : 'W' = '48'                ( A numeric representation of the week of the year, starting with the first Monday as the first week )
Known format   : 'X' = '11:24:44'          ( Preferred time representation based on locale, without the date )
Known format   : 'Y' = '2010'              ( Four digit representation for the year )
Known format   : 'Z' = 'GMT Standard Time' ( The time zone offset/abbreviation option NOT given by %z (depends on operating system) )
Known format   : 'a' = 'Fri'               ( An abbreviated textual representation of the day )
Known format   : 'b' = 'Dec'               ( Abbreviated month name, based on the locale )
Known format   : 'c' = '12/03/10 11:24:44' ( Preferred date and time stamp based on local )
Known format   : 'd' = '03'                ( Two-digit day of the month (with leading zeros) )
Known format   : 'j' = '337'               ( Day of the year, 3 digits with leading zeros )
Known format   : 'm' = '12'                ( Two digit representation of the month )
Known format   : 'p' = 'AM'                ( UPPER-CASE "AM" or "PM" based on the given time )
Known format   : 'w' = '5'                 ( Numeric representation of the day of the week )
Known format   : 'x' = '12/03/10'          ( Preferred date representation based on locale, without the time )
Known format   : 'y' = '10'                ( Two digit representation of the year )
Known format   : 'z' = 'GMT Standard Time' ( Either the time zone offset from UTC or the abbreviation (depends on operating system) )
Known format   : '%' = '%'                 ( A literal percentage character ("%") )
Unknown format : 'C'                       ( Two digit representation of the century (year divided by 100, truncated to an integer) )
Unknown format : 'D'                       ( Same as "%m/%d/%y" )
Unknown format : 'E'
Unknown format : 'F'                       ( Same as "%Y-%m-%d" )
Unknown format : 'G'                       ( The full four-digit version of %g )
Unknown format : 'J'
Unknown format : 'K'
Unknown format : 'L'
Unknown format : 'N'
Unknown format : 'O'
Unknown format : 'P'                       ( lower-case "am" or "pm" based on the given time )
Unknown format : 'Q'
Unknown format : 'R'                       ( Same as "%H:%M" )
Unknown format : 'T'                       ( Same as "%H:%M:%S" )
Unknown format : 'V'                       ( ISO-8601:1988 week number of the given year, starting with the first week of the year with at least 4 weekdays, with Monday being the start of the week )
Unknown format : 'e'                       ( Day of the month, with a space preceding single digits )
Unknown format : 'f'
Unknown format : 'g'                       ( Two digit representation of the year going by ISO-8601:1988 standards (see %V) )
Unknown format : 'h'                       ( Abbreviated month name, based on the locale (an alias of %b) )
Unknown format : 'i'
Unknown format : 'k'                       ( Hour in 24-hour format, with a space preceding single digits )
Unknown format : 'l'                       ( Hour in 12-hour format, with a space preceding single digits )
Unknown format : 'n'                       ( A newline character ("\n") )
Unknown format : 'o'
Unknown format : 'q'
Unknown format : 'r'                       ( Same as "%I:%M:%S %p" )
Unknown format : 's'                       ( Unix Epoch Time timestamp )
Unknown format : 't'                       ( A Tab character ("\t") )
Unknown format : 'u'                       ( ISO-8601 numeric representation of the day of the week )
Unknown format : 'v'
```

### Notes [¶](https://www.php.net/manual/en/function.strftime.php\#refsect1-function.strftime-notes)

> **Note**:
>
> %G and %V, which are based on ISO 8601:1988 week numbers can
> give unexpected (albeit correct) results if the numbering system
> is not thoroughly understood. See %V examples in this manual page.

### See Also [¶](https://www.php.net/manual/en/function.strftime.php\#refsect1-function.strftime-seealso)

- [IntlDateFormatter::format()](https://www.php.net/manual/en/intldateformatter.format.php) \- Format the date/time value as a string
- [DateTimeInterface::format()](https://www.php.net/manual/en/datetime.format.php) \- Returns date formatted according to given format
- [» Online strftime() format design tool](http://strftime.net/)
- [setlocale()](https://www.php.net/manual/en/function.setlocale.php) \- Set locale information
- [mktime()](https://www.php.net/manual/en/function.mktime.php) \- Get Unix timestamp for a date
- [strptime()](https://www.php.net/manual/en/function.strptime.php) \- Parse a time/date generated with strftime
- [gmstrftime()](https://www.php.net/manual/en/function.gmstrftime.php) \- Format a GMT/UTC time/date according to locale settings
- [» Open Group specification of **strftime()**](http://www.opengroup.org/onlinepubs/007908799/xsh/strftime.html)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/datetime/functions/strftime.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.strftime%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.strftime&repo=en&redirect=https://www.php.net/manual/en/function.strftime.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=128095&page=function.strftime&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128095&page=function.strftime&vote=down "Vote down!")

4


[**_divinity76+spam at gmail dot com_**](https://www.php.net/manual/en/function.strftime.php#128095) [¶](https://www.php.net/manual/en/function.strftime.php#128095)

**2 years ago**

`there is a strftime compatibility package for php>=8.1 at [https://github.com/alphp/strftime](https://github.com/alphp/strftime)`

[up](https://www.php.net/manual/vote-note.php?id=130286&page=function.strftime&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130286&page=function.strftime&vote=down "Vote down!")

0


[**_oriadam at example dot g dot com_**](https://www.php.net/manual/en/function.strftime.php#130286) [¶](https://www.php.net/manual/en/function.strftime.php#130286)

**5 months ago**

``Some formats can be replaced with the `date` function, for example:
    strftime("%Y-%m-%d", $time);
can be replaced with
    date("Y-m-d", $time);``

[up](https://www.php.net/manual/vote-note.php?id=129941&page=function.strftime&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129941&page=function.strftime&vote=down "Vote down!")

0


[**_kanif dot ahire at gmail dot com_**](https://www.php.net/manual/en/function.strftime.php#129941) [¶](https://www.php.net/manual/en/function.strftime.php#129941)

**9 months ago**

`Year is being displayed wrongly. It is displaying 2025 instead of 2024
E.g.   strftime("%G-%B-%d %H:%M:%S", strtotime(date('2024-12-30 10:10:10')));
Output: 2025-December-30 10:10:10

Here G represents 4-digit year corresponding to the ISO week number. Based on this ISO week number year value will be displayed
Here B represents full month name
Here d represents day of the month (01 to 31)

Now because of this %G value we are getting the issue as ISO week number is calculated wrongly.
For example, If 30th December is falling on Monday, Tuesday, or Wednesday it is in W01 of the next year.
If it is on a Thursday, it is in W53 of the year just ending.
If on a Friday it is in W52 of the year just ending in common years and W53 in leap years.
If on a Saturday or Sunday, it is in W52 of the year just ending.
In this way week calculation happens and as 30th falls on Monday it is taking as W01 of the next year and it displays wrong year output.
For previous year no issue for this error because 30 and 31st Dec falls on sat or Sunday .

This same error occurs even if the Jan 1st falls on Friday. Then it will calculate it as W53 and displays the previous year value instead of current year.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.strftime&repo=en&redirect=https://www.php.net/manual/en/function.strftime.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google