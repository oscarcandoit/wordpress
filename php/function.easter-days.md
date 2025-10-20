---
url: https://www.php.net/manual/en/function.easter-days.php
scraped_at: 2025-10-20T02:54:20.883Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# easter\_days

(PHP 4, PHP 5, PHP 7, PHP 8)

easter\_days — Get number of days after March 21 on which Easter falls for a given year

### Description [¶](https://www.php.net/manual/en/function.easter-days.php\#refsect1-function.easter-days-description)

**easter\_days**([?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$year` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, [int](https://www.php.net/manual/en/language.types.integer.php) `$mode` = **`[CAL\_EASTER\_DEFAULT](https://www.php.net/manual/en/calendar.constants.php#constant.cal-easter-default)`**): [int](https://www.php.net/manual/en/language.types.integer.php)

Returns the number of days after March 21 on which Easter falls
for a given year. If no year is specified, the current year is
assumed.


This function can be used instead of
[easter\_date()](https://www.php.net/manual/en/function.easter-date.php) to calculate Easter for years
which fall outside the range of Unix timestamps (i.e. before 1970
or after 2037).


The date of Easter Day was defined by the Council of Nicaea in
AD325 as the Sunday after the first full moon which falls on or
after the Spring Equinox. The Equinox is assumed to always fall
on 21st March, so the calculation reduces to determining the date
of the full moon and the date of the following Sunday. The
algorithm used here was introduced around the year 532 by
Dionysius Exiguus. Under the Julian Calendar (for years before
1753) a simple 19-year cycle is used to track the phases of the
Moon. Under the Gregorian Calendar (for years after 1753 -
devised by Clavius and Lilius, and introduced by Pope Gregory
XIII in October 1582, and into Britain and its then colonies in
September 1752) two correction factors are added to make the
cycle more accurate.


### Parameters [¶](https://www.php.net/manual/en/function.easter-days.php\#refsect1-function.easter-days-parameters)

`year`

The year as a positive number. If omitted or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, defaults to the
current year according to the local time.


`mode`

Allows Easter dates to be calculated based
on the Gregorian calendar during the years 1582 - 1752 when set to
**`[CAL\_EASTER\_ROMAN](https://www.php.net/manual/en/calendar.constants.php#constant.cal-easter-roman)`**. See the [calendar constants](https://www.php.net/manual/en/calendar.constants.php) for more valid
constants.


### Return Values [¶](https://www.php.net/manual/en/function.easter-days.php\#refsect1-function.easter-days-returnvalues)

The number of days after March 21st that the Easter Sunday
is in the given `year`.


### Changelog [¶](https://www.php.net/manual/en/function.easter-days.php\#refsect1-function.easter-days-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `year` is nullable now. |

### Examples [¶](https://www.php.net/manual/en/function.easter-days.php\#refsect1-function.easter-days-examples)

**Example #1 **easter\_days()** example**

`<?php
echo easter_days(1999);        // 14, i.e. April 4
echo easter_days(1492);        // 32, i.e. April 22
echo easter_days(1913);        //  2, i.e. March 23
?>`

### See Also [¶](https://www.php.net/manual/en/function.easter-days.php\#refsect1-function.easter-days-seealso)

- [easter\_date()](https://www.php.net/manual/en/function.easter-date.php) \- Get Unix timestamp for local midnight on Easter of a given year

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/calendar/functions/easter-days.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.easter-days%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.easter-days&repo=en&redirect=https://www.php.net/manual/en/function.easter-days.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=117383&page=function.easter-days&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117383&page=function.easter-days&vote=down "Vote down!")

9


[**_p dot rijt at caesar dot nl_**](https://www.php.net/manual/en/function.easter-days.php#117383) [¶](https://www.php.net/manual/en/function.easter-days.php#117383)

**10 years ago**

`This function returns an array of timestamp corresponding to Dutch National holidays. Liberation Day (Bevrijdingsdag) is added as a National holiday once every five years (2000, 2005, 2010, ...).
<?php
function getHolidays($year = null) {
    if ($year === null) {
        $year = intval(date('Y'));
    }

    $easterDate  = easter_date($year);
    $easterDay   = date('j', $easterDate);
    $easterMonth = date('n', $easterDate);
    $easterYear   = date('Y', $easterDate);

    $holidays = array(
        // Nieuwjaarsdag
        mktime(0, 0, 0, 1,  1,  $year),
        // 1e Kerstdag
        mktime(0, 0, 0, 12, 25, $year),
        // 2e Kerstdag
        mktime(0, 0, 0, 12, 26, $year)
    );

    // Bevrijdingsdag
    if (($year % 5) == 0) {
        $holidays[] = mktime(0, 0, 0, 5, 5, $year);
    }

    // Koninginnedag (< 2014) of Koningsdag (>= 2014).
    // Verplaats naar zaterdag als het valt op zondag.
    if ($year <= 2013) { // Koninginnedag <= 2013
        if (date('w', mktime(0, 0, 0, 4, 30, $year)) == 0) { // Op zondag?
            $holidays[] = mktime(0, 0, 0, 4, 29, $year);  // Verplaats naar zaterdag
        } else {
            $holidays[] = mktime(0, 0, 0, 4, 30, $year);  // Koninginnedag
        }
    } else { // Koningsdag > 2014
        if (date('w', mktime(0, 0, 0, 4, 27, $year)) == 0) { // Op zondag?
            $holidays[] = mktime(0, 0, 0, 4, 26, $year);  // Verplaats naar zaterdag
        } else {
            $holidays[] = mktime(0, 0, 0, 4, 27, $year);  // Koningsdag
        }
    }

    // Onderstaande dagen hebben een datum afhankelijk van Pasen
    // Goede Vrijdag (= pasen - 2)
    $holidays[] = strtotime('-2 days', mktime(0, 0, 0, $easterMonth, $easterDay,  $easterYear));
    // 1e Paasdag
    $holidays[] = mktime(0, 0, 0, $easterMonth, $easterDay,  $easterYear);
    // 2e Paasdag (= pasen +1)
    $holidays[] = strtotime('+1 days', mktime(0, 0, 0, $easterMonth, $easterDay,  $easterYear));
    // Hemelvaartsdag (= pasen + 39)
    $holidays[] = strtotime('+39 days', mktime(0, 0, 0, $easterMonth, $easterDay,  $easterYear));
    // 1e Pinksterdag (= pasen + 49)
    $holidays[] = strtotime('+49 days', mktime(0, 0, 0, $easterMonth, $easterDay,  $easterYear));
    // 2e Pinksterdag (= pasen + 50)
    $holidays[] = strtotime('+50 days', mktime(0, 0, 0, $easterMonth, $easterDay,  $easterYear));
    sort($holidays);

    return $holidays;
}
$holidays = getHolidays(2014);
foreach ($holidays as $holiday) {
    echo date('d-M-Y', $holiday) . '<br>';
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=16932&page=function.easter-days&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=16932&page=function.easter-days&vote=down "Vote down!")

0


[**_ian at eiloart dot com-NOSPAM_**](https://www.php.net/manual/en/function.easter-days.php#16932) [¶](https://www.php.net/manual/en/function.easter-days.php#16932)

**23 years ago**

`Also, be aware that the eastern orthodox churches sometimes have different dates for easter. See, for example < [http://webexhibits.org/calendars/calendar-christian-easter.html>.](http://webexhibits.org/calendars/calendar-christian-easter.html%3E.) And note that the dates of easter a subject to change,  for example, the churches might some day decide to unify the dates.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.easter-days&repo=en&redirect=https://www.php.net/manual/en/function.easter-days.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google