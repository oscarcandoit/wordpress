---
url: https://www.php.net/manual/en/class.swoole-mysql.php
scraped_at: 2025-10-20T02:33:00.221Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\MySQL class [¶](https://www.php.net/manual/en/class.swoole-mysql.php\#class.swoole-mysql)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-mysql.php\#swoole-mysql.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-mysql.php\#swoole-mysql.synopsis)

class **Swoole\\MySQL**
{

/\\* Methods \*/

public[close](https://www.php.net/manual/en/swoole-mysql.close.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[connect](https://www.php.net/manual/en/swoole-mysql.connect.php)([array](https://www.php.net/manual/en/language.types.array.php) `$server_config`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[\_\_destruct](https://www.php.net/manual/en/swoole-mysql.destruct.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[getBuffer](https://www.php.net/manual/en/swoole-mysql.getbuffer.php)(): ReturnType

public[on](https://www.php.net/manual/en/swoole-mysql.on.php)([string](https://www.php.net/manual/en/language.types.string.php) `$event_name`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[query](https://www.php.net/manual/en/swoole-mysql.query.php)([string](https://www.php.net/manual/en/language.types.string.php) `$sql`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): ReturnType

}

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-mysql.php\#class.swoole-mysql)

- [Swoole\\MySQL::close](https://www.php.net/manual/en/swoole-mysql.close.php) — Close the async MySQL connection.
- [Swoole\\MySQL::connect](https://www.php.net/manual/en/swoole-mysql.connect.php) — Connect to the remote MySQL server.
- [Swoole\\MySQL::\_\_construct](https://www.php.net/manual/en/swoole-mysql.construct.php) — Construct an async MySQL client.
- [Swoole\\MySQL::\_\_destruct](https://www.php.net/manual/en/swoole-mysql.destruct.php) — Destroy the async MySQL client.
- [Swoole\\MySQL::getBuffer](https://www.php.net/manual/en/swoole-mysql.getbuffer.php) — Description
- [Swoole\\MySQL::on](https://www.php.net/manual/en/swoole-mysql.on.php) — Register callback function based on event name.
- [Swoole\\MySQL::query](https://www.php.net/manual/en/swoole-mysql.query.php) — Run the SQL query.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.mysql.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-mysql%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-mysql&repo=en&redirect=https://www.php.net/manual/en/class.swoole-mysql.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google