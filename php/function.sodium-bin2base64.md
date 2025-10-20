---
url: https://www.php.net/manual/en/function.sodium-bin2base64.php
scraped_at: 2025-10-20T02:54:43.049Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# sodium\_bin2base64

(PHP 7 >= 7.2.0, PHP 8)

sodium\_bin2base64 — Encodes a raw binary string with base64.

### Description [¶](https://www.php.net/manual/en/function.sodium-bin2base64.php\#refsect1-function.sodium-bin2base64-description)

**sodium\_bin2base64**([#\[\\SensitiveParameter\]](https://www.php.net/manual/en/class.sensitiveparameter.php)[string](https://www.php.net/manual/en/language.types.string.php) `$string`, [int](https://www.php.net/manual/en/language.types.integer.php) `$id`): [string](https://www.php.net/manual/en/language.types.string.php)

Converts a raw binary string into a base64-encoded string. Unlike [base64\_encode()](https://www.php.net/manual/en/function.base64-encode.php),
**sodium\_bin2base64()** is constant-time (a property that is important for any code that
touches cryptographic inputs, such as plaintexts or keys) and supports multiple character sets.


### Parameters [¶](https://www.php.net/manual/en/function.sodium-bin2base64.php\#refsect1-function.sodium-bin2base64-parameters)

`string`

Raw binary string.


`id`

- **`[SODIUM\_BASE64\_VARIANT\_ORIGINAL](https://www.php.net/manual/en/sodium.constants.php#constant.sodium-base64-variant-original)`** for standard ( `A-Za-z0-9/\+`)
Base64 encoding.

- **`[SODIUM\_BASE64\_VARIANT\_ORIGINAL\_NO\_PADDING](https://www.php.net/manual/en/sodium.constants.php#constant.sodium-base64-variant-original-no-padding)`** for standard ( `A-Za-z0-9/\+`)
Base64 encoding, without `=` padding characters.

- **`[SODIUM\_BASE64\_VARIANT\_URLSAFE](https://www.php.net/manual/en/sodium.constants.php#constant.sodium-base64-variant-urlsafe)`** for URL-safe ( `A-Za-z0-9\-_`) Base64 encoding.

- **`[SODIUM\_BASE64\_VARIANT\_URLSAFE\_NO\_PADDING](https://www.php.net/manual/en/sodium.constants.php#constant.sodium-base64-variant-urlsafe-no-padding)`** for URL-safe ( `A-Za-z0-9\-_`)
Base64 encoding, without `=` padding characters.


### Return Values [¶](https://www.php.net/manual/en/function.sodium-bin2base64.php\#refsect1-function.sodium-bin2base64-returnvalues)

Base64-encoded string.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/sodium/functions/sodium-bin2base64.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.sodium-bin2base64%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.sodium-bin2base64&repo=en&redirect=https://www.php.net/manual/en/function.sodium-bin2base64.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=123728&page=function.sodium-bin2base64&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123728&page=function.sodium-bin2base64&vote=down "Vote down!")

7


[**_davidw at example dot com_**](https://www.php.net/manual/en/function.sodium-bin2base64.php#123728) [¶](https://www.php.net/manual/en/function.sodium-bin2base64.php#123728)

**6 years ago**

`bin: The data you wish to encode
id: The variant of encoding to use, which can be one of the following constants. You'll need to reuse this value when decoding with sodium_base642bin.
SODIUM_BASE64_VARIANT_ORIGINAL            = 1
SODIUM_BASE64_VARIANT_ORIGINAL_NO_PADDING = 3
SODIUM_BASE64_VARIANT_URLSAFE             = 5
SODIUM_BASE64_VARIANT_URLSAFE_NO_PADDING  = 7`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.sodium-bin2base64&repo=en&redirect=https://www.php.net/manual/en/function.sodium-bin2base64.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google