---
url: https://www.php.net/manual/en/class.swoole-client.php
scraped_at: 2025-10-20T02:37:47.577Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\Client class [¶](https://www.php.net/manual/en/class.swoole-client.php\#class.swoole-client)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-client.php\#swoole-client.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-client.php\#swoole-client.synopsis)

class **Swoole\\Client**
{

/\\* Constants \*/

const[int](https://www.php.net/manual/en/language.types.integer.php)[MSG\_OOB](https://www.php.net/manual/en/class.swoole-client.php#swoole-client.constants.msg-oob) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[MSG\_PEEK](https://www.php.net/manual/en/class.swoole-client.php#swoole-client.constants.msg-peek) = 2;

const[int](https://www.php.net/manual/en/language.types.integer.php)[MSG\_DONTWAIT](https://www.php.net/manual/en/class.swoole-client.php#swoole-client.constants.msg-dontwait) = 128;

const[int](https://www.php.net/manual/en/language.types.integer.php)[MSG\_WAITALL](https://www.php.net/manual/en/class.swoole-client.php#swoole-client.constants.msg-waitall) = 64;

/\\* Properties \*/

public[$errCode](https://www.php.net/manual/en/class.swoole-client.php#swoole-client.props.errcode);

public[$sock](https://www.php.net/manual/en/class.swoole-client.php#swoole-client.props.sock);

public[$reuse](https://www.php.net/manual/en/class.swoole-client.php#swoole-client.props.reuse);

public[$reuseCount](https://www.php.net/manual/en/class.swoole-client.php#swoole-client.props.reusecount);

/\\* Methods \*/

public[close](https://www.php.net/manual/en/swoole-client.close.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$force` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[connect](https://www.php.net/manual/en/swoole-client.connect.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$host`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$port` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$timeout` = ?,

[int](https://www.php.net/manual/en/language.types.integer.php) `$flag` = ?

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[\_\_destruct](https://www.php.net/manual/en/swoole-client.destruct.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[getpeername](https://www.php.net/manual/en/swoole-client.getpeername.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getsockname](https://www.php.net/manual/en/swoole-client.getsockname.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[isConnected](https://www.php.net/manual/en/swoole-client.isconnected.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[on](https://www.php.net/manual/en/swoole-client.on.php)([string](https://www.php.net/manual/en/language.types.string.php) `$event`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[pause](https://www.php.net/manual/en/swoole-client.pause.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[pipe](https://www.php.net/manual/en/swoole-client.pipe.php)([string](https://www.php.net/manual/en/language.types.string.php) `$socket`): [void](https://www.php.net/manual/en/language.types.void.php)

public[recv](https://www.php.net/manual/en/swoole-client.recv.php)([string](https://www.php.net/manual/en/language.types.string.php) `$size` = ?, [string](https://www.php.net/manual/en/language.types.string.php) `$flag` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

public[resume](https://www.php.net/manual/en/swoole-client.resume.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[send](https://www.php.net/manual/en/swoole-client.send.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`, [string](https://www.php.net/manual/en/language.types.string.php) `$flag` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[sendfile](https://www.php.net/manual/en/swoole-client.sendfile.php)([string](https://www.php.net/manual/en/language.types.string.php) `$filename`, [int](https://www.php.net/manual/en/language.types.integer.php) `$offset` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[sendto](https://www.php.net/manual/en/swoole-client.sendto.php)([string](https://www.php.net/manual/en/language.types.string.php) `$ip`, [int](https://www.php.net/manual/en/language.types.integer.php) `$port`, [string](https://www.php.net/manual/en/language.types.string.php) `$data`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[set](https://www.php.net/manual/en/swoole-client.set.php)([array](https://www.php.net/manual/en/language.types.array.php) `$settings`): [void](https://www.php.net/manual/en/language.types.void.php)

public[sleep](https://www.php.net/manual/en/swoole-client.sleep.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[wakeup](https://www.php.net/manual/en/swoole-client.wakeup.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Properties [¶](https://www.php.net/manual/en/class.swoole-client.php\#swoole-client.props)

errCode

sock

reuse

reuseCount

## Predefined Constants [¶](https://www.php.net/manual/en/class.swoole-client.php\#swoole-client.constants)

**`[Swoole\\Client::MSG\_OOB](https://www.php.net/manual/en/class.swoole-client.php#swoole-client.constants.msg-oob)`**

**`[Swoole\\Client::MSG\_PEEK](https://www.php.net/manual/en/class.swoole-client.php#swoole-client.constants.msg-peek)`**

**`[Swoole\\Client::MSG\_DONTWAIT](https://www.php.net/manual/en/class.swoole-client.php#swoole-client.constants.msg-dontwait)`**

**`[Swoole\\Client::MSG\_WAITALL](https://www.php.net/manual/en/class.swoole-client.php#swoole-client.constants.msg-waitall)`**

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-client.php\#class.swoole-client)

- [Swoole\\Client::close](https://www.php.net/manual/en/swoole-client.close.php) — Close the connection established.
- [Swoole\\Client::connect](https://www.php.net/manual/en/swoole-client.connect.php) — Connect to the remote TCP or UDP port.
- [Swoole\\Client::\_\_construct](https://www.php.net/manual/en/swoole-client.construct.php) — Create Swoole sync or async TCP/UDP client, with or without SSL.
- [Swoole\\Client::\_\_destruct](https://www.php.net/manual/en/swoole-client.destruct.php) — Destruct the Swoole client.
- [Swoole\\Client::getpeername](https://www.php.net/manual/en/swoole-client.getpeername.php) — Get the remote socket name of the connection.
- [Swoole\\Client::getsockname](https://www.php.net/manual/en/swoole-client.getsockname.php) — Get the local socket name of the connection.
- [Swoole\\Client::isConnected](https://www.php.net/manual/en/swoole-client.isconnected.php) — Check if the connection is established.
- [Swoole\\Client::on](https://www.php.net/manual/en/swoole-client.on.php) — Add callback functions triggered by events.
- [Swoole\\Client::pause](https://www.php.net/manual/en/swoole-client.pause.php) — Pause receiving data.
- [Swoole\\Client::pipe](https://www.php.net/manual/en/swoole-client.pipe.php) — Redirect the data to another file descriptor.
- [Swoole\\Client::recv](https://www.php.net/manual/en/swoole-client.recv.php) — Receive data from the remote socket.
- [Swoole\\Client::resume](https://www.php.net/manual/en/swoole-client.resume.php) — Resume receiving data.
- [Swoole\\Client::send](https://www.php.net/manual/en/swoole-client.send.php) — Send data to the remote TCP socket.
- [Swoole\\Client::sendfile](https://www.php.net/manual/en/swoole-client.sendfile.php) — Send file to the remote TCP socket.
- [Swoole\\Client::sendto](https://www.php.net/manual/en/swoole-client.sendto.php) — Send data to the remote UDP address.
- [Swoole\\Client::set](https://www.php.net/manual/en/swoole-client.set.php) — Set the Swoole client parameters before the connection is established.
- [Swoole\\Client::sleep](https://www.php.net/manual/en/swoole-client.sleep.php) — Remove the TCP client from system event loop.
- [Swoole\\Client::wakeup](https://www.php.net/manual/en/swoole-client.wakeup.php) — Add the TCP client back into the system event loop.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.client.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-client%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-client&repo=en&redirect=https://www.php.net/manual/en/class.swoole-client.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google