---
url: https://www.php.net/manual/en/function.zlib-encode.php
scraped_at: 2025-10-20T03:02:00.757Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# zlib\_encode

(PHP 5 >= 5.4.0, PHP 7, PHP 8)

zlib\_encode — Compress data with the specified encoding

### Description [¶](https://www.php.net/manual/en/function.zlib-encode.php\#refsect1-function.zlib-encode-description)

**zlib\_encode**([string](https://www.php.net/manual/en/language.types.string.php) `$data`, [int](https://www.php.net/manual/en/language.types.integer.php) `$encoding`, [int](https://www.php.net/manual/en/language.types.integer.php) `$level` = -1): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Compress data with the specified encoding.


**Warning**

This function is
currently not documented; only its argument list is available.

### Parameters [¶](https://www.php.net/manual/en/function.zlib-encode.php\#refsect1-function.zlib-encode-parameters)

`data`

The data to compress.


`encoding`

The compression algorithm. Either **`[ZLIB\_ENCODING\_RAW](https://www.php.net/manual/en/zlib.constants.php#constant.zlib-encoding-raw)`**,
**`[ZLIB\_ENCODING\_DEFLATE](https://www.php.net/manual/en/zlib.constants.php#constant.zlib-encoding-deflate)`** or
**`[ZLIB\_ENCODING\_GZIP](https://www.php.net/manual/en/zlib.constants.php#constant.zlib-encoding-gzip)`**.


`level`

### Return Values [¶](https://www.php.net/manual/en/function.zlib-encode.php\#refsect1-function.zlib-encode-returnvalues)

### Examples [¶](https://www.php.net/manual/en/function.zlib-encode.php\#refsect1-function.zlib-encode-examples)

**Example #1 **zlib\_encode()** example**

`<?php
$str = 'hello world';
$enc = zlib_encode($str, ZLIB_ENCODING_DEFLATE);
echo bin2hex($enc);
?>`

The above example will output:

```
789ccb48cdc9c95728cf2fca4901001a0b045d
```

### See Also [¶](https://www.php.net/manual/en/function.zlib-encode.php\#refsect1-function.zlib-encode-seealso)

- [zlib\_decode()](https://www.php.net/manual/en/function.zlib-decode.php) \- Uncompress any raw/gzip/zlib encoded data

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/zlib/functions/zlib-encode.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.zlib-encode%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.zlib-encode&repo=en&redirect=https://www.php.net/manual/en/function.zlib-encode.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=127759&page=function.zlib-encode&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127759&page=function.zlib-encode&vote=down "Vote down!")

3


[**_geniuszxy at outlook dot com_**](https://www.php.net/manual/en/function.zlib-encode.php#127759) [¶](https://www.php.net/manual/en/function.zlib-encode.php#127759)

**3 years ago**

`zlib_encode, gzcompress, gzdeflate and gzencode are the same functions besides the parameter order.
zlib_encode + ZLIB_ENCODING_RAW = gzdeflate
zlib_encode + ZLIB_ENCODING_DEFLATE = gzcompress
zlib_encode + ZLIB_ENCODING_GZIP = gzencode`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.zlib-encode&repo=en&redirect=https://www.php.net/manual/en/function.zlib-encode.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google