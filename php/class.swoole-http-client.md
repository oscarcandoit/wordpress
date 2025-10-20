---
url: https://www.php.net/manual/en/class.swoole-http-client.php
scraped_at: 2025-10-20T02:37:22.032Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\Http\\Client class [¶](https://www.php.net/manual/en/class.swoole-http-client.php\#class.swoole-http-client)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-http-client.php\#swoole-http-client.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-http-client.php\#swoole-http-client.synopsis)

class **Swoole\\Http\\Client**
{

/\\* Properties \*/

public[$errCode](https://www.php.net/manual/en/class.swoole-http-client.php#swoole-http-client.props.errcode);

public[$sock](https://www.php.net/manual/en/class.swoole-http-client.php#swoole-http-client.props.sock);

/\\* Methods \*/

public[addFile](https://www.php.net/manual/en/swoole-http-client.addfile.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$path`,

[string](https://www.php.net/manual/en/language.types.string.php) `$name`,

[string](https://www.php.net/manual/en/language.types.string.php) `$type` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$filename` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$offset` = ?

): [void](https://www.php.net/manual/en/language.types.void.php)

public[close](https://www.php.net/manual/en/swoole-http-client.close.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[\_\_destruct](https://www.php.net/manual/en/swoole-http-client.destruct.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[download](https://www.php.net/manual/en/swoole-http-client.download.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$path`,

[string](https://www.php.net/manual/en/language.types.string.php) `$file`,

[callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$offset` = ?

): [void](https://www.php.net/manual/en/language.types.void.php)

public[execute](https://www.php.net/manual/en/swoole-http-client.execute.php)([string](https://www.php.net/manual/en/language.types.string.php) `$path`, [string](https://www.php.net/manual/en/language.types.string.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[get](https://www.php.net/manual/en/swoole-http-client.get.php)([string](https://www.php.net/manual/en/language.types.string.php) `$path`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[isConnected](https://www.php.net/manual/en/swoole-http-client.isconnected.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[on](https://www.php.net/manual/en/swoole-http-client.on.php)([string](https://www.php.net/manual/en/language.types.string.php) `$event_name`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[post](https://www.php.net/manual/en/swoole-http-client.post.php)([string](https://www.php.net/manual/en/language.types.string.php) `$path`, [string](https://www.php.net/manual/en/language.types.string.php) `$data`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

public[push](https://www.php.net/manual/en/swoole-http-client.push.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`, [string](https://www.php.net/manual/en/language.types.string.php) `$opcode` = ?, [string](https://www.php.net/manual/en/language.types.string.php) `$finish` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

public[set](https://www.php.net/manual/en/swoole-http-client.set.php)([array](https://www.php.net/manual/en/language.types.array.php) `$settings`): [void](https://www.php.net/manual/en/language.types.void.php)

public[setCookies](https://www.php.net/manual/en/swoole-http-client.setcookies.php)([array](https://www.php.net/manual/en/language.types.array.php) `$cookies`): [void](https://www.php.net/manual/en/language.types.void.php)

public[setData](https://www.php.net/manual/en/swoole-http-client.setdata.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`): ReturnType

public[setHeaders](https://www.php.net/manual/en/swoole-http-client.setheaders.php)([array](https://www.php.net/manual/en/language.types.array.php) `$headers`): [void](https://www.php.net/manual/en/language.types.void.php)

public[setMethod](https://www.php.net/manual/en/swoole-http-client.setmethod.php)([string](https://www.php.net/manual/en/language.types.string.php) `$method`): [void](https://www.php.net/manual/en/language.types.void.php)

public[upgrade](https://www.php.net/manual/en/swoole-http-client.upgrade.php)([string](https://www.php.net/manual/en/language.types.string.php) `$path`, [string](https://www.php.net/manual/en/language.types.string.php) `$callback`): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Properties [¶](https://www.php.net/manual/en/class.swoole-http-client.php\#swoole-http-client.props)

errCode

sock

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-http-client.php\#class.swoole-http-client)

- [Swoole\\Http\\Client::addFile](https://www.php.net/manual/en/swoole-http-client.addfile.php) — Add a file to the post form.
- [Swoole\\Http\\Client::close](https://www.php.net/manual/en/swoole-http-client.close.php) — Close the http connection.
- [Swoole\\Http\\Client::\_\_construct](https://www.php.net/manual/en/swoole-http-client.construct.php) — Construct the async HTTP client.
- [Swoole\\Http\\Client::\_\_destruct](https://www.php.net/manual/en/swoole-http-client.destruct.php) — Destruct the HTTP client.
- [Swoole\\Http\\Client::download](https://www.php.net/manual/en/swoole-http-client.download.php) — Download a file from the remote server.
- [Swoole\\Http\\Client::execute](https://www.php.net/manual/en/swoole-http-client.execute.php) — Send the HTTP request after setting the parameters.
- [Swoole\\Http\\Client::get](https://www.php.net/manual/en/swoole-http-client.get.php) — Send GET http request to the remote server.
- [Swoole\\Http\\Client::isConnected](https://www.php.net/manual/en/swoole-http-client.isconnected.php) — Check if the HTTP connection is connected.
- [Swoole\\Http\\Client::on](https://www.php.net/manual/en/swoole-http-client.on.php) — Register callback function by event name.
- [Swoole\\Http\\Client::post](https://www.php.net/manual/en/swoole-http-client.post.php) — Send POST http request to the remote server.
- [Swoole\\Http\\Client::push](https://www.php.net/manual/en/swoole-http-client.push.php) — Push data to websocket client.
- [Swoole\\Http\\Client::set](https://www.php.net/manual/en/swoole-http-client.set.php) — Update the HTTP client parameters.
- [Swoole\\Http\\Client::setCookies](https://www.php.net/manual/en/swoole-http-client.setcookies.php) — Set the http request cookies.
- [Swoole\\Http\\Client::setData](https://www.php.net/manual/en/swoole-http-client.setdata.php) — Set the HTTP request body data.
- [Swoole\\Http\\Client::setHeaders](https://www.php.net/manual/en/swoole-http-client.setheaders.php) — Set the HTTP request headers.
- [Swoole\\Http\\Client::setMethod](https://www.php.net/manual/en/swoole-http-client.setmethod.php) — Set the HTTP request method.
- [Swoole\\Http\\Client::upgrade](https://www.php.net/manual/en/swoole-http-client.upgrade.php) — Upgrade to websocket protocol.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.http.client.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-http-client%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-http-client&repo=en&redirect=https://www.php.net/manual/en/class.swoole-http-client.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google