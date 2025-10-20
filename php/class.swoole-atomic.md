---
url: https://www.php.net/manual/en/class.swoole-atomic.php
scraped_at: 2025-10-20T02:32:13.547Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\Atomic class [¶](https://www.php.net/manual/en/class.swoole-atomic.php\#class.swoole-atomic)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-atomic.php\#swoole-atomic.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-atomic.php\#swoole-atomic.synopsis)

class **Swoole\\Atomic**
{

/\\* Methods \*/

public[add](https://www.php.net/manual/en/swoole-atomic.add.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$add_value` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[cmpset](https://www.php.net/manual/en/swoole-atomic.cmpset.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$cmp_value`, [int](https://www.php.net/manual/en/language.types.integer.php) `$new_value`): [int](https://www.php.net/manual/en/language.types.integer.php)

public[get](https://www.php.net/manual/en/swoole-atomic.get.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[set](https://www.php.net/manual/en/swoole-atomic.set.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [int](https://www.php.net/manual/en/language.types.integer.php)

public[sub](https://www.php.net/manual/en/swoole-atomic.sub.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$sub_value` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-atomic.php\#class.swoole-atomic)

- [Swoole\\Atomic::add](https://www.php.net/manual/en/swoole-atomic.add.php) — Add a number to the value to the atomic object.
- [Swoole\\Atomic::cmpset](https://www.php.net/manual/en/swoole-atomic.cmpset.php) — Compare and set the value of the atomic object.
- [Swoole\\Atomic::\_\_construct](https://www.php.net/manual/en/swoole-atomic.construct.php) — Construct a swoole atomic object.
- [Swoole\\Atomic::get](https://www.php.net/manual/en/swoole-atomic.get.php) — Get the current value of the atomic object.
- [Swoole\\Atomic::set](https://www.php.net/manual/en/swoole-atomic.set.php) — Set a new value to the atomic object.
- [Swoole\\Atomic::sub](https://www.php.net/manual/en/swoole-atomic.sub.php) — Subtract a number to the value of the atomic object.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.atomic.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-atomic%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-atomic&repo=en&redirect=https://www.php.net/manual/en/class.swoole-atomic.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google