---
url: https://www.php.net/manual/en/intro.stream.php
scraped_at: 2025-10-20T02:34:03.892Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Introduction [¶](https://www.php.net/manual/en/intro.stream.php\#intro.stream)

Streams are
the way of generalizing file, network, data compression, and other
operations which share a common set of functions and uses. In
its simplest definition, a `stream` is a
[resource](https://www.php.net/manual/en/language.types.resource.php) object which exhibits streamable
behavior. That is, it can be read from or written to in a linear
fashion, and may be able to [fseek()](https://www.php.net/manual/en/function.fseek.php) to an
arbitrary location within the stream.


A `wrapper` is additional code which tells the stream how to handle
specific protocols/encodings. For example, the `http`
wrapper knows how to translate a URL into an `HTTP/1.0`
request for a file on a remote server. There are many wrappers
built into PHP by default (See [Supported Protocols and Wrappers](https://www.php.net/manual/en/wrappers.php)),
and additional, custom wrappers may be added either within a
PHP script using [stream\_wrapper\_register()](https://www.php.net/manual/en/function.stream-wrapper-register.php),
or directly from an extension.
Because any variety of wrapper may be added to PHP,
there is no set limit on what can be done with them. To access the list
of currently registered wrappers, use [stream\_get\_wrappers()](https://www.php.net/manual/en/function.stream-get-wrappers.php).


A stream is referenced as: `scheme`:// `target`

- `scheme` (string) -
The name of the wrapper to be used. Examples include: file,
http, https, ftp, ftps, compress.zlib, compress.bz2, and php. See
[Supported Protocols and Wrappers](https://www.php.net/manual/en/wrappers.php) for a list of PHP built-in wrappers. If
no wrapper is specified, the function default is used (typically
`file`://).

- `target` \-
Depends on the wrapper used. For filesystem related streams this is
typically a path and filename of the desired file. For network related
streams this is typically a hostname, often with a path appended. Again, see
[Supported Protocols and Wrappers](https://www.php.net/manual/en/wrappers.php) for a description of targets for built-in streams.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/stream/book.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fintro.stream%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=intro.stream&repo=en&redirect=https://www.php.net/manual/en/intro.stream.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google