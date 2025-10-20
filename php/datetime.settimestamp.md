---
url: https://www.php.net/manual/en/datetime.settimestamp.php
scraped_at: 2025-10-20T02:56:50.474Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# DateTime::setTimestamp

# date\_timestamp\_set

(PHP 5 >= 5.3.0, PHP 7, PHP 8)

DateTime::setTimestamp \-\- date\_timestamp\_set — Sets the date and time based on an Unix timestamp

### Description [¶](https://www.php.net/manual/en/datetime.settimestamp.php\#refsect1-datetime.settimestamp-description)

Object-oriented style

public**DateTime::setTimestamp**([int](https://www.php.net/manual/en/language.types.integer.php) `$timestamp`): [DateTime](https://www.php.net/manual/en/class.datetime.php)

Procedural style

[date\_timestamp\_set](https://www.php.net/manual/en/function.date-timestamp-set.php)([DateTime](https://www.php.net/manual/en/class.datetime.php) `$object`, [int](https://www.php.net/manual/en/language.types.integer.php) `$timestamp`): [DateTime](https://www.php.net/manual/en/class.datetime.php)

Sets the date and time based on an Unix timestamp.


Like [DateTimeImmutable::setTimestamp()](https://www.php.net/manual/en/datetimeimmutable.settimestamp.php) but works with
[DateTime](https://www.php.net/manual/en/class.datetime.php).


The procedural version takes the [DateTime](https://www.php.net/manual/en/class.datetime.php) object as
its first argument.


### Parameters [¶](https://www.php.net/manual/en/datetime.settimestamp.php\#refsect1-datetime.settimestamp-parameters)

`object`

Procedural style only: A [DateTime](https://www.php.net/manual/en/class.datetime.php) object
returned by [date\_create()](https://www.php.net/manual/en/function.date-create.php).
The function modifies this object.

`timestamp`

Unix timestamp representing the date.
Setting timestamps outside the range of [int](https://www.php.net/manual/en/language.types.integer.php) is possible by using
[DateTimeImmutable::modify()](https://www.php.net/manual/en/datetimeimmutable.modify.php) with the `@` format.


### Return Values [¶](https://www.php.net/manual/en/datetime.settimestamp.php\#refsect1-datetime.settimestamp-returnvalues)

Returns the modified [DateTime](https://www.php.net/manual/en/class.datetime.php) object for method chaining.


### See Also [¶](https://www.php.net/manual/en/datetime.settimestamp.php\#refsect1-datetime.settimestamp-seealso)

- [DateTimeImmutable::setTimestamp()](https://www.php.net/manual/en/datetimeimmutable.settimestamp.php) \- Sets the date and time based on a Unix timestamp

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/datetime/datetime/settimestamp.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fdatetime.settimestamp%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=datetime.settimestamp&repo=en&redirect=https://www.php.net/manual/en/datetime.settimestamp.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google