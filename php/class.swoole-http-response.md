---
url: https://www.php.net/manual/en/class.swoole-http-response.php
scraped_at: 2025-10-20T02:47:28.428Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\Http\\Response class [¶](https://www.php.net/manual/en/class.swoole-http-response.php\#class.swoole-http-response)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-http-response.php\#swoole-http-response.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-http-response.php\#swoole-http-response.synopsis)

class **Swoole\\Http\\Response**
{

/\\* Methods \*/

public[cookie](https://www.php.net/manual/en/swoole-http-response.cookie.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$name`,

[string](https://www.php.net/manual/en/language.types.string.php) `$value` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$expires` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$path` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$domain` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$secure` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$httponly` = ?

): [string](https://www.php.net/manual/en/language.types.string.php)

public[\_\_destruct](https://www.php.net/manual/en/swoole-http-response.destruct.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[end](https://www.php.net/manual/en/swoole-http-response.end.php)([string](https://www.php.net/manual/en/language.types.string.php) `$content` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

public[gzip](https://www.php.net/manual/en/swoole-http-response.gzip.php)([string](https://www.php.net/manual/en/language.types.string.php) `$compress_level` = ?): ReturnType

public[header](https://www.php.net/manual/en/swoole-http-response.header.php)([string](https://www.php.net/manual/en/language.types.string.php) `$key`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$ucwords` = ?): [void](https://www.php.net/manual/en/language.types.void.php)

public[initHeader](https://www.php.net/manual/en/swoole-http-response.initheader.php)(): ReturnType

public[rawcookie](https://www.php.net/manual/en/swoole-http-response.rawcookie.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$name`,

[string](https://www.php.net/manual/en/language.types.string.php) `$value` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$expires` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$path` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$domain` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$secure` = ?,

[string](https://www.php.net/manual/en/language.types.string.php) `$httponly` = ?

): ReturnType

public[sendfile](https://www.php.net/manual/en/swoole-http-response.sendfile.php)([string](https://www.php.net/manual/en/language.types.string.php) `$filename`, [int](https://www.php.net/manual/en/language.types.integer.php) `$offset` = ?): ReturnType

public[status](https://www.php.net/manual/en/swoole-http-response.status.php)([string](https://www.php.net/manual/en/language.types.string.php) `$http_code`): ReturnType

public[write](https://www.php.net/manual/en/swoole-http-response.write.php)([string](https://www.php.net/manual/en/language.types.string.php) `$content`): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-http-response.php\#class.swoole-http-response)

- [Swoole\\Http\\Response::cookie](https://www.php.net/manual/en/swoole-http-response.cookie.php) — Set the cookies of the HTTP response.
- [Swoole\\Http\\Response::\_\_destruct](https://www.php.net/manual/en/swoole-http-response.destruct.php) — Destruct the HTTP response.
- [Swoole\\Http\\Response::end](https://www.php.net/manual/en/swoole-http-response.end.php) — Send data for the HTTP request and finish the response.
- [Swoole\\Http\\Response::gzip](https://www.php.net/manual/en/swoole-http-response.gzip.php) — Enable the gzip of response content.
- [Swoole\\Http\\Response::header](https://www.php.net/manual/en/swoole-http-response.header.php) — Set the HTTP response headers.
- [Swoole\\Http\\Response::initHeader](https://www.php.net/manual/en/swoole-http-response.initheader.php) — Init the HTTP response header.
- [Swoole\\Http\\Response::rawcookie](https://www.php.net/manual/en/swoole-http-response.rawcookie.php) — Set the raw cookies to the HTTP response.
- [Swoole\\Http\\Response::sendfile](https://www.php.net/manual/en/swoole-http-response.sendfile.php) — Send file through the HTTP response.
- [Swoole\\Http\\Response::status](https://www.php.net/manual/en/swoole-http-response.status.php) — Set the status code of the HTTP response.
- [Swoole\\Http\\Response::write](https://www.php.net/manual/en/swoole-http-response.write.php) — Append HTTP body content to the HTTP response.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.http.response.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-http-response%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-http-response&repo=en&redirect=https://www.php.net/manual/en/class.swoole-http-response.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google