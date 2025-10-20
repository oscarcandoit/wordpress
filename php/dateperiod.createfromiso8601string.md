---
url: https://www.php.net/manual/en/dateperiod.createfromiso8601string.php
scraped_at: 2025-10-20T02:48:45.869Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# DatePeriod::createFromISO8601String

(PHP 8 >= 8.3.0)

DatePeriod::createFromISO8601String — Creates a new DatePeriod object from an ISO8601 string

### Description [¶](https://www.php.net/manual/en/dateperiod.createfromiso8601string.php\#refsect1-dateperiod.createfromiso8601string-description)

publicstatic**DatePeriod::createFromISO8601String**([string](https://www.php.net/manual/en/language.types.string.php) `$specification`, [int](https://www.php.net/manual/en/language.types.integer.php) `$options` = 0): static

Creates a new DatePeriod object from an ISO8601 string, as specified with
`specification`.


### Parameters [¶](https://www.php.net/manual/en/dateperiod.createfromiso8601string.php\#refsect1-dateperiod.createfromiso8601string-parameters)

`specification`

A subset of the [» ISO 8601 repeating\\
interval specification](http://en.wikipedia.org/wiki/Iso8601#Repeating_intervals).


An example of an accepted ISO 8601 interval specifications is
`R5/2008-03-01T13:00:00Z/P1Y2M10DT2H30M`, which
specifies:


- 5 iterations ( `R5/`)

- Starting at `2008-03-01T13:00:00Z`.

- Each iteration is an 1 year, 2 months, 10 days, 2 hours, and 30 minute interval
( `/P1Y2M10DT2H30M`).


Examples of some ISO 8601 interval specification features that PHP does
not support are:


1. zero occurrences ( `R0/`)

2. time offsets other than UTC ( `Z`), such as `+02:00`.


`options`

A bit field which can be used to control certain behaviour with start-
and end- dates.


With **`[DatePeriod::EXCLUDE\_START\_DATE](https://www.php.net/manual/en/class.dateperiod.php#dateperiod.constants.exclude-start-date)`** you
exclude the start date from the set of recurring dates within the
period.


With **`[DatePeriod::INCLUDE\_END\_DATE](https://www.php.net/manual/en/class.dateperiod.php#dateperiod.constants.include-end-date)`** you
include the end date in the set of recurring dates within the
period.


### Return Values [¶](https://www.php.net/manual/en/dateperiod.createfromiso8601string.php\#refsect1-dateperiod.createfromiso8601string-returnvalues)

Creates a new DatePeriod object.


[DatePeriod](https://www.php.net/manual/en/class.dateperiod.php) objects created with this method can be
used as an iterator to generate a number of
[DateTimeImmutable](https://www.php.net/manual/en/class.datetimeimmutable.php) objects.


### Errors/Exceptions [¶](https://www.php.net/manual/en/dateperiod.createfromiso8601string.php\#refsect1-dateperiod.createfromiso8601string-errors)

Throws an [DateMalformedPeriodStringException](https://www.php.net/manual/en/class.datemalformedperiodstringexception.php) when
the `specification` cannot be parsed as a valid ISO 8601
period.


### Examples [¶](https://www.php.net/manual/en/dateperiod.createfromiso8601string.php\#refsect1-dateperiod.createfromiso8601string-examples)

**Example #1 DatePeriod::createFromISO8601String example**

`<?php
$iso = 'R4/2023-07-01T00:00:00Z/P7D';
$period = DatePeriod::createFromISO8601String($iso);
// By iterating over the DatePeriod object, all of the
// recurring dates within that period are printed.
foreach ($period as $date) {
    echo $date->format('Y-m-d'), "\n";
}
?>`

The above example will output:

```
2023-07-01
2023-07-08
2023-07-15
2023-07-22
2023-07-29
```

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/datetime/dateperiod/createfromiso8601string.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fdateperiod.createfromiso8601string%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=dateperiod.createfromiso8601string&repo=en&redirect=https://www.php.net/manual/en/dateperiod.createfromiso8601string.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google