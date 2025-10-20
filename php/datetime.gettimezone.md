---
url: https://www.php.net/manual/en/datetime.gettimezone.php
scraped_at: 2025-10-20T02:57:11.316Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# DateTimeInterface::getTimezone

# DateTimeImmutable::getTimezone

# DateTime::getTimezone

# date\_timezone\_get

(PHP 5 >= 5.2.0, PHP 7, PHP 8)

DateTimeInterface::getTimezone \-\- DateTimeImmutable::getTimezone \-\- DateTime::getTimezone \-\- date\_timezone\_get — Return time zone relative to given DateTime

### Description [¶](https://www.php.net/manual/en/datetime.gettimezone.php\#refsect1-datetime.gettimezone-description)

Object-oriented style

public**DateTimeInterface::getTimezone**(): [DateTimeZone](https://www.php.net/manual/en/class.datetimezone.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

public**DateTimeImmutable::getTimezone**(): [DateTimeZone](https://www.php.net/manual/en/class.datetimezone.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

public**DateTime::getTimezone**(): [DateTimeZone](https://www.php.net/manual/en/class.datetimezone.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Procedural style

[date\_timezone\_get](https://www.php.net/manual/en/function.date-timezone-get.php)([DateTimeInterface](https://www.php.net/manual/en/class.datetimeinterface.php) `$object`): [DateTimeZone](https://www.php.net/manual/en/class.datetimezone.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Return time zone relative to given DateTime.


### Parameters [¶](https://www.php.net/manual/en/datetime.gettimezone.php\#refsect1-datetime.gettimezone-parameters)

`object`

Procedural style only: A [DateTime](https://www.php.net/manual/en/class.datetime.php) object
returned by [date\_create()](https://www.php.net/manual/en/function.date-create.php)

### Return Values [¶](https://www.php.net/manual/en/datetime.gettimezone.php\#refsect1-datetime.gettimezone-returnvalues)

Returns a [DateTimeZone](https://www.php.net/manual/en/class.datetimezone.php) object on success
or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/datetime.gettimezone.php\#refsect1-datetime.gettimezone-examples)

**Example #1 **DateTime::getTimezone()** example**

Object-oriented style

`<?php
$date = new DateTimeImmutable(null, new DateTimeZone('Europe/London'));
$tz = $date->getTimezone();
echo $tz->getName();
?>`

Procedural style

`<?php
$date = date_create(null, timezone_open('Europe/London'));
$tz = date_timezone_get($date);
echo timezone_name_get($tz);
?>`

The above examples will output:

```
Europe/London
```

### See Also [¶](https://www.php.net/manual/en/datetime.gettimezone.php\#refsect1-datetime.gettimezone-seealso)

- [DateTime::setTimezone()](https://www.php.net/manual/en/datetime.settimezone.php) \- Sets the time zone for the DateTime object

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/datetime/datetimeinterface/gettimezone.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fdatetime.gettimezone%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=datetime.gettimezone&repo=en&redirect=https://www.php.net/manual/en/datetime.gettimezone.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google