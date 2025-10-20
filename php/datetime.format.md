---
url: https://www.php.net/manual/en/datetime.format.php
scraped_at: 2025-10-20T02:57:18.603Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# DateTimeInterface::format

# DateTimeImmutable::format

# DateTime::format

# date\_format

(PHP 5 >= 5.2.0, PHP 7, PHP 8)

DateTimeInterface::format \-\- DateTimeImmutable::format \-\- DateTime::format \-\- date\_format — Returns date formatted according to given format

### Description [¶](https://www.php.net/manual/en/datetime.format.php\#refsect1-datetime.format-description)

Object-oriented style

public**DateTimeInterface::format**([string](https://www.php.net/manual/en/language.types.string.php) `$format`): [string](https://www.php.net/manual/en/language.types.string.php)

public**DateTimeImmutable::format**([string](https://www.php.net/manual/en/language.types.string.php) `$format`): [string](https://www.php.net/manual/en/language.types.string.php)

public**DateTime::format**([string](https://www.php.net/manual/en/language.types.string.php) `$format`): [string](https://www.php.net/manual/en/language.types.string.php)

Procedural style

[date\_format](https://www.php.net/manual/en/function.date-format.php)([DateTimeInterface](https://www.php.net/manual/en/class.datetimeinterface.php) `$object`, [string](https://www.php.net/manual/en/language.types.string.php) `$format`): [string](https://www.php.net/manual/en/language.types.string.php)

Returns date formatted according to given format.


### Parameters [¶](https://www.php.net/manual/en/datetime.format.php\#refsect1-datetime.format-parameters)

`object`

Procedural style only: A [DateTime](https://www.php.net/manual/en/class.datetime.php) object
returned by [date\_create()](https://www.php.net/manual/en/function.date-create.php)

`format`

The format of the outputted date [string](https://www.php.net/manual/en/language.types.string.php). See the formatting
options below. There are also several
[predefined date constants](https://www.php.net/manual/en/class.datetimeinterface.php#datetimeinterface.constants.types)
that may be used instead, so for example **`[DATE\_RSS](https://www.php.net/manual/en/datetime.constants.php#constant.date-rss)`**
contains the format string `'D, d M Y H:i:s'`.


| `format` character | Description | Example returned values |
| --- | --- | --- |
| _Day_ | \-\-\- | \-\-\- |
| `d` | Day of the month, 2 digits with leading zeros | `01` to `31` |
| `D` | A textual representation of a day, three letters | `Mon` through `Sun` |
| `j` | Day of the month without leading zeros | `1` to `31` |
| `l` (lowercase 'L') | A full textual representation of the day of the week | `Sunday` through `Saturday` |
| `N` | ISO 8601 numeric representation of the day of the week | `1` (for Monday) through `7` (for Sunday) |
| `S` | English ordinal suffix for the day of the month, 2 characters | `st`, `nd`, `rd` or<br> `th`. Works well with `j` |
| `w` | Numeric representation of the day of the week | `0` (for Sunday) through `6` (for Saturday) |
| `z` | The day of the year (starting from 0) | `0` through `365` |
| _Week_ | \-\-\- | \-\-\- |
| `W` | ISO 8601 week number of year, weeks starting on Monday | Example: `42` (the 42nd week in the year) |
| _Month_ | \-\-\- | \-\-\- |
| `F` | A full textual representation of a month, such as January or March | `January` through `December` |
| `m` | Numeric representation of a month, with leading zeros | `01` through `12` |
| `M` | A short textual representation of a month, three letters | `Jan` through `Dec` |
| `n` | Numeric representation of a month, without leading zeros | `1` through `12` |
| `t` | Number of days in the given month | `28` through `31` |
| _Year_ | \-\-\- | \-\-\- |
| `L` | Whether it's a leap year | `1` if it is a leap year, `0` otherwise. |
| `o` | ISO 8601 week-numbering year. This has the same value as<br> `Y`, except that if the ISO week number<br> ( `W`) belongs to the previous or next year, that year<br> is used instead. | Examples: `1999` or `2003` |
| `X` | An expanded full numeric representation of a year, at least 4 digits,<br> with `-` for years BCE, and `+`<br> for years CE. | Examples: `-0055`, `+0787`,<br> `+1999`, `+10191` |
| `x` | An expanded full numeric representation if required, or a<br> standard full numeral representation if possible (like<br> `Y`). At least four digits. Years BCE are prefixed<br> with a `-`. Years beyond (and including)<br> `10000` are prefixed by a<br> `+`. | Examples: `-0055`, `0787`,<br> `1999`, `+10191` |
| `Y` | A full numeric representation of a year, at least 4 digits,<br> with `-` for years BCE. | Examples: `-0055`, `0787`,<br> `1999`, `2003`,<br> `10191` |
| `y` | A two digit representation of a year | Examples: `99` or `03` |
| _Time_ | \-\-\- | \-\-\- |
| `a` | Lowercase Ante meridiem and Post meridiem | `am` or `pm` |
| `A` | Uppercase Ante meridiem and Post meridiem | `AM` or `PM` |
| `B` | Swatch Internet time | `000` through `999` |
| `g` | 12-hour format of an hour without leading zeros | `1` through `12` |
| `G` | 24-hour format of an hour without leading zeros | `0` through `23` |
| `h` | 12-hour format of an hour with leading zeros | `01` through `12` |
| `H` | 24-hour format of an hour with leading zeros | `00` through `23` |
| `i` | Minutes with leading zeros | `00` to `59` |
| `s` | Seconds with leading zeros | `00` through `59` |
| `u` | Microseconds. Note that<br> [date()](https://www.php.net/manual/en/function.date.php) will always generate<br> `000000` since it takes an [int](https://www.php.net/manual/en/language.types.integer.php)<br> parameter, whereas **DateTimeInterface::format()** does<br> support microseconds if an object of type<br> [DateTimeInterface](https://www.php.net/manual/en/class.datetimeinterface.php) was created with microseconds. | Example: `654321` |
| `v` | Milliseconds. Same note applies as for<br> `u`. | Example: `654` |
| _Timezone_ | \-\-\- | \-\-\- |
| `e` | Timezone identifier | Examples: `UTC`, `GMT`, `Atlantic/Azores` |
| `I` (capital i) | Whether or not the date is in daylight saving time | `1` if Daylight Saving Time, `0` otherwise. |
| `O` | Difference to Greenwich time (GMT) without colon between hours and minutes | Example: `+0200` |
| `P` | Difference to Greenwich time (GMT) with colon between hours and minutes | Example: `+02:00` |
| `p` | The same as `P`, but returns `Z` instead of `+00:00`<br> (available as of PHP 8.0.0) | Examples: `Z` or `+02:00` |
| `T` | Timezone abbreviation, if known; otherwise the GMT offset. | Examples: `EST`, `MDT`, `+05` |
| `Z` | Timezone offset in seconds. The offset for timezones west of UTC is always<br> negative, and for those east of UTC is always positive. | `-43200` through `50400` |
| _Full Date/Time_ | \-\-\- | \-\-\- |
| `c` | ISO 8601 date. Only compatible with the non-expanded format (up to year 9999). Later dates will result in an invalid string. For later dates and expanded format, see `x` and `X`. | 2004-02-12T15:19:21+00:00 |
| `r` | [» RFC 2822](https://datatracker.ietf.org/doc/html/rfc2822)/ [» RFC 5322](https://datatracker.ietf.org/doc/html/rfc5322) formatted date | Example: `Thu, 21 Dec 2000 16:01:07 +0200` |
| `U` | Seconds since the Unix Epoch (January 1 1970 00:00:00 GMT) | See also [time()](https://www.php.net/manual/en/function.time.php) |

**The following characters are recognized in the**
**`format` parameter string**

Unrecognized characters in the format string will be printed
as-is. The `Z` format will always return
`0` when using [gmdate()](https://www.php.net/manual/en/function.gmdate.php).


> **Note**:
>
>
> Since this function only accepts [int](https://www.php.net/manual/en/language.types.integer.php) timestamps the
> `u` format character is only useful when using the
> [date\_format()](https://www.php.net/manual/en/function.date-format.php) function with user based timestamps
> created with [date\_create()](https://www.php.net/manual/en/function.date-create.php).

### Return Values [¶](https://www.php.net/manual/en/datetime.format.php\#refsect1-datetime.format-returnvalues)

Returns the formatted date string on success.


### Changelog [¶](https://www.php.net/manual/en/datetime.format.php\#refsect1-datetime.format-changelog)

| Version | Description |
| --- | --- |
| 8.2.0 | The format characters `X` and `x`<br> have been added. |
| 8.0.0 | The format character `p` has been added. |

### Examples [¶](https://www.php.net/manual/en/datetime.format.php\#refsect1-datetime.format-examples)

**Example #1 **DateTimeInterface::format()** example**

Object-oriented style

`<?php
$date = new DateTimeImmutable('2000-01-01');
echo $date->format('Y-m-d H:i:s');
?>`

Procedural style

`<?php
$date = date_create('2000-01-01');
echo date_format($date, 'Y-m-d H:i:s');
?>`

The above example will output:

```
2000-01-01 00:00:00
```

**Example #2 More examples**

`<?php
// set the default timezone to use.
date_default_timezone_set('UTC');
// now
$date = new DateTimeImmutable();
// Prints something like: Wednesday
echo $date->format('l'), "\n";
// Prints something like: Wednesday 19th of October 2022 08:40:48 AM
echo $date->format('l jS \o\f F Y h:i:s A'), "\n";
/* use the constants in the format parameter */
// prints something like: Wed, 19 Oct 2022 08:40:48 +0000
echo $date->format(DateTimeInterface::RFC2822), "\n";
?>`

You can prevent a recognized character in the format string from being
expanded by escaping it with a preceding backslash. If the character with
a backslash is already a special sequence, you may need to also escape
the backslash.


**Example #3 Escaping characters while formatting**

`<?php
$date = new DateTimeImmutable();
// prints something like: Wednesday the 19th
echo $date->format('l \t\h\e jS');
?>`

To format dates in other languages,
[IntlDateFormatter::format()](https://www.php.net/manual/en/intldateformatter.format.php)
can be used instead of **DateTimeInterface::format()**.


### Notes [¶](https://www.php.net/manual/en/datetime.format.php\#refsect1-datetime.format-notes)

This method does not use locales. All output is in English.


### See Also [¶](https://www.php.net/manual/en/datetime.format.php\#refsect1-datetime.format-seealso)

- [IntlDateFormatter::format()](https://www.php.net/manual/en/intldateformatter.format.php) \- Format the date/time value as a string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/datetime/datetimeinterface/format.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fdatetime.format%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=datetime.format&repo=en&redirect=https://www.php.net/manual/en/datetime.format.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=129945&page=datetime.format&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129945&page=datetime.format&vote=down "Vote down!")

12


[**_jurchiks101 at gmail dot com_**](https://www.php.net/manual/en/datetime.format.php#129945) [¶](https://www.php.net/manual/en/datetime.format.php#129945)

**9 months ago**

``If you want to get the week of year + year of said week, you need to use `format('o-W'), otherwise you can stumble into a non-obvious gotcha (unless you RTFM and memorised it, that is).
Using `Y` instead of `o` can result in incorrect year values in the case of the first or last week of the year (depending on if January 4th falls into said week or not), such as the first week of 2025 between 2024-12-30 and 2025-01-05 - `(new DateTime('2024-12-30'))->format('o-W')` will return the correct value of `2025-01` (as per ISO-8601 definition of week of year), while `format('Y-W')` will return `2024-01`.
Because of this, I would personally recommend avoiding using week of year anywhere unless absolutely necessary, as it is easy to make this mistake and never realise it.``

[up](https://www.php.net/manual/vote-note.php?id=130502&page=datetime.format&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130502&page=datetime.format&vote=down "Vote down!")

0


[**_jpachta at NOSPAM dot centrum dot cz_**](https://www.php.net/manual/en/datetime.format.php#130502) [¶](https://www.php.net/manual/en/datetime.format.php#130502)

**10 days ago**

``Ad Escaping characters while formatting
To escape special characters, such as `\n`, `\t`, etc., is needed usage of multiple escaping to avoid expanding the formatting key or special character itself.
In my case I needed a new line sequence `\n` to be printed in the output as is i.e. as a plain text with backslash and letter n.
In the example bellow there are used letters `Y`, `n`, `W` that without escaping are recognized as format character representing full year (`Y`), month number(`n`) and week number (`W`).
<?php
/* Escaping new line special character \n to be a plain text */
// Now
$now = new DateTime();
// Prints something like: 2025\n41
echo $now->format('Y\\\\\nW');
/* Test of various escaping sequences */
// List of formats in single quotes
$formats = [\
    'YnW',  // 20251041\
    'Y\nW',  // 2025n41\
    'Y\\nW',  // 2025n41\
    'Y\\\nW',  // 2025\1041\
    'Y\\\\nW',  // 2025\1041\
    'Y\\\\\nW',  // 2025\n41\
    'Y\\\\\\nW',  // 2025\n41\
    'Y\\\\\\\nW',  // 2025\\1041\
    'Y\\\\\\\\nW',  // 2025\\1041\
    'Y\\\\\\\\\nW',  // 2025\\n41\
    'Y\\\\\\\\\\nW',  // 2025\\n41\
];
foreach($formats as $key => $format){
echo PHP_EOL . $key . '. format: '. var_export($format, true) ."\t".' output: '. $now->format($format);
}
?>
Prints something like:
0. format: 'YnW'  output: 20251041
1. format: 'Y\\nW'  output: 2025n41
2. format: 'Y\\nW'  output: 2025n41
3. format: 'Y\\\\nW'  output: 2025\1041
4. format: 'Y\\\\nW'  output: 2025\1041
5. format: 'Y\\\\\\nW'  output: 2025\n41
6. format: 'Y\\\\\\nW'  output: 2025\n41
7. format: 'Y\\\\\\\\nW'  output: 2025\\1041
8. format: 'Y\\\\\\\\nW'  output: 2025\\1041
9. format: 'Y\\\\\\\\\\nW'  output: 2025\\n41
10. format: 'Y\\\\\\\\\\nW'  output: 2025\\n41``

[＋add a note](https://www.php.net/manual/add-note.php?sect=datetime.format&repo=en&redirect=https://www.php.net/manual/en/datetime.format.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google