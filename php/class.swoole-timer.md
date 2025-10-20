---
url: https://www.php.net/manual/en/class.swoole-timer.php
scraped_at: 2025-10-20T02:37:49.670Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\Timer class [¶](https://www.php.net/manual/en/class.swoole-timer.php\#class.swoole-timer)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-timer.php\#swoole-timer.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-timer.php\#swoole-timer.synopsis)

class **Swoole\\Timer**
{

/\\* Methods \*/

publicstatic[after](https://www.php.net/manual/en/swoole-timer.after.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$after_time_ms`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

publicstatic[clear](https://www.php.net/manual/en/swoole-timer.clear.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$timer_id`): [void](https://www.php.net/manual/en/language.types.void.php)

publicstatic[exists](https://www.php.net/manual/en/swoole-timer.exists.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$timer_id`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[tick](https://www.php.net/manual/en/swoole-timer.tick.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$interval_ms`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`, [string](https://www.php.net/manual/en/language.types.string.php) `$param` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-timer.php\#class.swoole-timer)

- [Swoole\\Timer::after](https://www.php.net/manual/en/swoole-timer.after.php) — Trigger a callback function after a period of time.
- [Swoole\\Timer::clear](https://www.php.net/manual/en/swoole-timer.clear.php) — Delete a timer by timer ID.
- [Swoole\\Timer::exists](https://www.php.net/manual/en/swoole-timer.exists.php) — Check if a timer is existed.
- [Swoole\\Timer::tick](https://www.php.net/manual/en/swoole-timer.tick.php) — Repeats a given function at every given time-interval.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.timer.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-timer%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-timer&repo=en&redirect=https://www.php.net/manual/en/class.swoole-timer.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google