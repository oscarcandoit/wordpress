---
url: https://www.php.net/manual/en/datetime.settimezone.php
scraped_at: 2025-10-20T02:50:25.334Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# DateTime::setTimezone

# date\_timezone\_set

(PHP 5 >= 5.2.0, PHP 7, PHP 8)

DateTime::setTimezone \-\- date\_timezone\_set — Sets the time zone for the DateTime object

### Description [¶](https://www.php.net/manual/en/datetime.settimezone.php\#refsect1-datetime.settimezone-description)

Object-oriented style

public**DateTime::setTimezone**([DateTimeZone](https://www.php.net/manual/en/class.datetimezone.php) `$timezone`): [DateTime](https://www.php.net/manual/en/class.datetime.php)

Procedural style

[date\_timezone\_set](https://www.php.net/manual/en/function.date-timezone-set.php)([DateTime](https://www.php.net/manual/en/class.datetime.php) `$object`, [DateTimeZone](https://www.php.net/manual/en/class.datetimezone.php) `$timezone`): [DateTime](https://www.php.net/manual/en/class.datetime.php)

Sets a new timezone for a [DateTime](https://www.php.net/manual/en/class.datetime.php)[object](https://www.php.net/manual/en/language.types.object.php).


Like [DateTimeImmutable::setTimezone()](https://www.php.net/manual/en/datetimeimmutable.settimezone.php) but works with
[DateTime](https://www.php.net/manual/en/class.datetime.php).


The procedural version takes the [DateTime](https://www.php.net/manual/en/class.datetime.php) object as
its first argument.


### Parameters [¶](https://www.php.net/manual/en/datetime.settimezone.php\#refsect1-datetime.settimezone-parameters)

`object`

Procedural style only: A [DateTime](https://www.php.net/manual/en/class.datetime.php) object
returned by [date\_create()](https://www.php.net/manual/en/function.date-create.php).
The function modifies this object.

`timezone`

A [DateTimeZone](https://www.php.net/manual/en/class.datetimezone.php) object representing the
desired time zone.


### Return Values [¶](https://www.php.net/manual/en/datetime.settimezone.php\#refsect1-datetime.settimezone-returnvalues)

Returns the [DateTime](https://www.php.net/manual/en/class.datetime.php) object for method chaining. The
underlaying point-in-time is not changed when calling this method.


### Examples [¶](https://www.php.net/manual/en/datetime.settimezone.php\#refsect1-datetime.settimezone-examples)

**Example #1 **DateTime::setTimeZone()** example**

Object-oriented style

`<?php
$date = new DateTime('2000-01-01', new DateTimeZone('Pacific/Nauru'));
echo $date->format('Y-m-d H:i:sP') . "\n";
$date->setTimezone(new DateTimeZone('Pacific/Chatham'));
echo $date->format('Y-m-d H:i:sP') . "\n";
?>`

Procedural style

`<?php
$date = date_create('2000-01-01', timezone_open('Pacific/Nauru'));
echo date_format($date, 'Y-m-d H:i:sP') . "\n";
date_timezone_set($date, timezone_open('Pacific/Chatham'));
echo date_format($date, 'Y-m-d H:i:sP') . "\n";
?>`

The above examples will output:

```
2000-01-01 00:00:00+12:00
2000-01-01 01:45:00+13:45
```

### See Also [¶](https://www.php.net/manual/en/datetime.settimezone.php\#refsect1-datetime.settimezone-seealso)

- [DateTimeImmutable::setTimezone()](https://www.php.net/manual/en/datetimeimmutable.settimezone.php) \- Sets the time zone
- [DateTime::getTimezone()](https://www.php.net/manual/en/datetime.gettimezone.php) \- Return time zone relative to given DateTime
- [DateTimeZone::\_\_construct()](https://www.php.net/manual/en/datetimezone.construct.php) \- Creates new DateTimeZone object

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/datetime/datetime/settimezone.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fdatetime.settimezone%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=datetime.settimezone&repo=en&redirect=https://www.php.net/manual/en/datetime.settimezone.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google