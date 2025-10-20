---
url: https://www.php.net/manual/en/intldateformatter.setpattern.php
scraped_at: 2025-10-20T02:49:31.539Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# IntlDateFormatter::setPattern

# datefmt\_set\_pattern

(PHP 5 >= 5.3.0, PHP 7, PHP 8, PECL intl >= 1.0.0)

IntlDateFormatter::setPattern \-\- datefmt\_set\_pattern — Set the pattern used for the IntlDateFormatter

### Description [¶](https://www.php.net/manual/en/intldateformatter.setpattern.php\#refsect1-intldateformatter.setpattern-description)

Object-oriented style


public**IntlDateFormatter::setPattern**([string](https://www.php.net/manual/en/language.types.string.php) `$pattern`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Procedural style


**datefmt\_set\_pattern**([IntlDateFormatter](https://www.php.net/manual/en/class.intldateformatter.php) `$formatter`, [string](https://www.php.net/manual/en/language.types.string.php) `$pattern`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Set the pattern used for the IntlDateFormatter.


### Parameters [¶](https://www.php.net/manual/en/intldateformatter.setpattern.php\#refsect1-intldateformatter.setpattern-parameters)

`formatter`

The formatter resource.


`pattern`

New pattern string to use.
Possible patterns are documented at [» https://unicode-org.github.io/icu/userguide/format\_parse/datetime/](https://unicode-org.github.io/icu/userguide/format_parse/datetime/).


### Return Values [¶](https://www.php.net/manual/en/intldateformatter.setpattern.php\#refsect1-intldateformatter.setpattern-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.
Bad formatstrings are usually the cause of the failure.


### Examples [¶](https://www.php.net/manual/en/intldateformatter.setpattern.php\#refsect1-intldateformatter.setpattern-examples)

**Example #1 **datefmt\_set\_pattern()** example**

`<?php
$fmt = datefmt_create(
    'en_US',
    IntlDateFormatter::FULL,IntlDateFormatter::FULL,
    'America/Los_Angeles',
    IntlDateFormatter::GREGORIAN,
    'MM/dd/yyyy'
);
echo 'Pattern of the formatter is : ', datefmt_get_pattern($fmt), PHP_EOL;
echo 'First Formatted output with pattern is ', datefmt_format($fmt, 0), PHP_EOL;
datefmt_set_pattern($fmt, 'yyyyMMdd hh:mm:ss z');
echo 'Now pattern of the formatter is : ', datefmt_get_pattern($fmt), PHP_EOL;
echo 'Second Formatted output with pattern is ', datefmt_format($fmt, 0), PHP_EOL;
?>`

**Example #2 OO example**

`<?php
$fmt = new IntlDateFormatter(
    'en_US',
    IntlDateFormatter::FULL,IntlDateFormatter::FULL,
    'America/Los_Angeles',
    IntlDateFormatter::GREGORIAN,
    'MM/dd/yyyy'
);
echo 'Pattern of the formatter is : ', $fmt->getPattern(), PHP_EOL;
echo 'First Formatted output is ', $fmt->format(0), PHP_EOL;
$fmt->setPattern('yyyyMMdd hh:mm:ss z');
echo 'Now pattern of the formatter is : ', $fmt->getPattern(), PHP_EOL;
echo 'Second Formatted output is ', $fmt->format(0), PHP_EOL;
?>`

The above example will output:

```
Pattern of the formatter is : MM/dd/yyyy
First Formatted output is 12/31/1969
Now pattern of the formatter is : yyyyMMdd hh:mm:ss z
Second Formatted output is 19691231 04:00:00 PST
```

### See Also [¶](https://www.php.net/manual/en/intldateformatter.setpattern.php\#refsect1-intldateformatter.setpattern-seealso)

- [datefmt\_get\_pattern()](https://www.php.net/manual/en/intldateformatter.getpattern.php) \- Get the pattern used for the IntlDateFormatter
- [datefmt\_create()](https://www.php.net/manual/en/intldateformatter.create.php) \- Create a date formatter

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/intl/dateformatter/set-pattern.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fintldateformatter.setpattern%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=intldateformatter.setpattern&repo=en&redirect=https://www.php.net/manual/en/intldateformatter.setpattern.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=130518&page=intldateformatter.setpattern&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130518&page=intldateformatter.setpattern&vote=down "Vote down!")

0


[**_Anonymous_**](https://www.php.net/manual/en/intldateformatter.setpattern.php#130518) [¶](https://www.php.net/manual/en/intldateformatter.setpattern.php#130518)

**4 days ago**

`Completely useless, impossible to comprehend documentation. No examples whatsoever. PHP "collective" doing full-on Microsoft's bang-you-head-on-the-wall attitude.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=intldateformatter.setpattern&repo=en&redirect=https://www.php.net/manual/en/intldateformatter.setpattern.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google