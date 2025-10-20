---
url: https://www.php.net/manual/en/class.swoole-websocket-server.php
scraped_at: 2025-10-20T02:42:46.405Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\WebSocket\\Server class [¶](https://www.php.net/manual/en/class.swoole-websocket-server.php\#class.swoole-websocket-server)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-websocket-server.php\#swoole-websocket-server.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-websocket-server.php\#swoole-websocket-server.synopsis)

class **Swoole\\WebSocket\\Server**extends [Swoole\\Http\\Server](https://www.php.net/manual/en/class.swoole-http-server.php)
{

/\\* Methods \*/

public[exist](https://www.php.net/manual/en/swoole-websocket-server.exist.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fd`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[on](https://www.php.net/manual/en/swoole-websocket-server.on.php)([string](https://www.php.net/manual/en/language.types.string.php) `$event_name`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): ReturnType

publicstatic[pack](https://www.php.net/manual/en/swoole-websocket-server.pack.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$data`,

[string](https://www.php.net/manual/en/language.types.string.php) `$opcode` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$finish` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$mask` = ?

): binary

public[push](https://www.php.net/manual/en/swoole-websocket-server.push.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$fd`,

[string](https://www.php.net/manual/en/language.types.string.php) `$data`,

[string](https://www.php.net/manual/en/language.types.string.php) `$opcode` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$finish` = ?

): [void](https://www.php.net/manual/en/language.types.void.php)

publicstatic[unpack](https://www.php.net/manual/en/swoole-websocket-server.unpack.php)(binary `$data`): [string](https://www.php.net/manual/en/language.types.string.php)

/\\* Inherited methods \*/

public[Swoole\\Http\\Server::on](https://www.php.net/manual/en/swoole-http-server.on.php)([string](https://www.php.net/manual/en/language.types.string.php) `$event_name`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[Swoole\\Http\\Server::start](https://www.php.net/manual/en/swoole-http-server.start.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-websocket-server.php\#class.swoole-websocket-server)

- [Swoole\\WebSocket\\Server::exist](https://www.php.net/manual/en/swoole-websocket-server.exist.php) — Check if the file descriptor exists.
- [Swoole\\WebSocket\\Server::on](https://www.php.net/manual/en/swoole-websocket-server.on.php) — Register event callback function
- [Swoole\\WebSocket\\Server::pack](https://www.php.net/manual/en/swoole-websocket-server.pack.php) — Get a pack of binary data to send in a single frame.
- [Swoole\\WebSocket\\Server::push](https://www.php.net/manual/en/swoole-websocket-server.push.php) — Push data to the remote client.
- [Swoole\\WebSocket\\Server::unpack](https://www.php.net/manual/en/swoole-websocket-server.unpack.php) — Unpack the binary data received from the client.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.websocket.server.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-websocket-server%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-websocket-server&repo=en&redirect=https://www.php.net/manual/en/class.swoole-websocket-server.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google