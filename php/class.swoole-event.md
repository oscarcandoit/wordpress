---
url: https://www.php.net/manual/en/class.swoole-event.php
scraped_at: 2025-10-20T02:32:06.259Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\Event class [¶](https://www.php.net/manual/en/class.swoole-event.php\#class.swoole-event)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-event.php\#swoole-event.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-event.php\#swoole-event.synopsis)

class **Swoole\\Event**
{

/\\* Methods \*/

publicstatic[add](https://www.php.net/manual/en/swoole-event.add.php)(

[int](https://www.php.net/manual/en/language.types.integer.php) `$fd`,

[callable](https://www.php.net/manual/en/language.types.callable.php) `$read_callback`,

[callable](https://www.php.net/manual/en/language.types.callable.php) `$write_callback` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$events` = ?

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[defer](https://www.php.net/manual/en/swoole-event.defer.php)([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

publicstatic[del](https://www.php.net/manual/en/swoole-event.del.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fd`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[exit](https://www.php.net/manual/en/swoole-event.exit.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

publicstatic[set](https://www.php.net/manual/en/swoole-event.set.php)(

[int](https://www.php.net/manual/en/language.types.integer.php) `$fd`,

[string](https://www.php.net/manual/en/language.types.string.php) `$read_callback` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$write_callback` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$events` = ?

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[wait](https://www.php.net/manual/en/swoole-event.wait.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

publicstatic[write](https://www.php.net/manual/en/swoole-event.write.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fd`, [string](https://www.php.net/manual/en/language.types.string.php) `$data`): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-event.php\#class.swoole-event)

- [Swoole\\Event::add](https://www.php.net/manual/en/swoole-event.add.php) — Add new callback functions of a socket into the EventLoop.
- [Swoole\\Event::defer](https://www.php.net/manual/en/swoole-event.defer.php) — Add a callback function to the next event loop.
- [Swoole\\Event::del](https://www.php.net/manual/en/swoole-event.del.php) — Remove all event callback functions of a socket.
- [Swoole\\Event::exit](https://www.php.net/manual/en/swoole-event.exit.php) — Exit the eventloop, only available at client side.
- [Swoole\\Event::set](https://www.php.net/manual/en/swoole-event.set.php) — Update the event callback functions of a socket.
- [Swoole\\Event::wait](https://www.php.net/manual/en/swoole-event.wait.php) — Description
- [Swoole\\Event::write](https://www.php.net/manual/en/swoole-event.write.php) — Write data to the socket.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.event.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-event%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-event&repo=en&redirect=https://www.php.net/manual/en/class.swoole-event.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google