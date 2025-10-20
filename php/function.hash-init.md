---
url: https://www.php.net/manual/en/function.hash-init.php
scraped_at: 2025-10-20T02:41:48.162Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# hash\_init

(PHP 5 >= 5.1.2, PHP 7, PHP 8, PECL hash >= 1.1)

hash\_init — Initialize an incremental hashing context

### Description [¶](https://www.php.net/manual/en/function.hash-init.php\#refsect1-function.hash-init-description)

**hash\_init**(

[string](https://www.php.net/manual/en/language.types.string.php) `$algo`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$flags` = 0,

[#\[\\SensitiveParameter\]](https://www.php.net/manual/en/class.sensitiveparameter.php)[string](https://www.php.net/manual/en/language.types.string.php) `$key` = "",

[array](https://www.php.net/manual/en/language.types.array.php) `$options` = \[\]

): [HashContext](https://www.php.net/manual/en/class.hashcontext.php)

### Parameters [¶](https://www.php.net/manual/en/function.hash-init.php\#refsect1-function.hash-init-parameters)

`algo`

Name of selected hashing algorithm (e.g. `"sha256"`).
For a list of supported algorithms see [hash\_algos()](https://www.php.net/manual/en/function.hash-algos.php).


> **Note**:
>
>
> Non-cryptographic hash functions are not allowed if the **`[HASH\_HMAC](https://www.php.net/manual/en/hash.constants.php#constant.hash-hmac)`**
> flag is specified.

`flags`

Optional settings for hash generation, currently supports only one option:
**`[HASH\_HMAC](https://www.php.net/manual/en/hash.constants.php#constant.hash-hmac)`**. When specified, the `key` _must_ be specified.


`key`

When **`[HASH\_HMAC](https://www.php.net/manual/en/hash.constants.php#constant.hash-hmac)`** is specified for `flags`,
a shared secret key to be used with the HMAC hashing method must be supplied in this
parameter.


`options`

An array of options for the various hashing algorithms.
Currently, only the `"seed"` parameter is
supported by the MurmurHash variants.


### Return Values [¶](https://www.php.net/manual/en/function.hash-init.php\#refsect1-function.hash-init-returnvalues)

Returns a Hashing Context for use with [hash\_update()](https://www.php.net/manual/en/function.hash-update.php),
[hash\_update\_stream()](https://www.php.net/manual/en/function.hash-update-stream.php), [hash\_update\_file()](https://www.php.net/manual/en/function.hash-update-file.php),
and [hash\_final()](https://www.php.net/manual/en/function.hash-final.php).


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.hash-init.php\#refsect1-function.hash-init-errors)

- Throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) exception if
`algo` is unknown or is a non-cryptographic hash
function, or if `key` is empty.

- Passing configurations options of the wrong type in
`options` will now emit an
**`[E\_DEPRECATED](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-deprecated)`** error because they can be interpreted
incorrectly.
This will become a [ValueError](https://www.php.net/manual/en/class.valueerror.php) in the
future.


### Changelog [¶](https://www.php.net/manual/en/function.hash-init.php\#refsect1-function.hash-init-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Passing options of a wrong type is now deprecated. |
| 8.1.0 | The `options` parameter has been added. |
| 8.0.0 | Now throws an [ValueError](https://www.php.net/manual/en/class.valueerror.php) exception if the<br> `algo` is unknown or is a non-cryptographic hash<br> function, or if `key` is empty. Previously,<br> **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** was returned and an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** message was<br> emitted. |
| 7.2.0 | Usage of non-cryptographic hash functions (adler32, crc32, crc32b, fnv132, fnv1a32, fnv164, fnv1a64, joaat) with **`[HASH\_HMAC](https://www.php.net/manual/en/hash.constants.php#constant.hash-hmac)`** was disabled. |
| 7.2.0 | Return [HashContext](https://www.php.net/manual/en/class.hashcontext.php) instead of resource. |

### Examples [¶](https://www.php.net/manual/en/function.hash-init.php\#refsect1-function.hash-init-examples)

**Example #1 Incremental hashing example**

`<?php
$hash = hash('sha256', 'The quick brown fox jumped over the lazy dog.');
$ctx = hash_init('sha256');
hash_update($ctx, 'The quick brown fox ');
hash_update($ctx, 'jumped over the lazy dog.');
$incremental_hash = hash_final($ctx);
echo $incremental_hash, PHP_EOL;
var_dump($hash === $incremental_hash);
?>`

Run code

The above example will output:

```
68b1282b91de2c054c36629cb8dd447f12f096d3e3c587978dc2248444633483
bool(true)
```

### See Also [¶](https://www.php.net/manual/en/function.hash-init.php\#refsect1-function.hash-init-seealso)

- [hash\_algos()](https://www.php.net/manual/en/function.hash-algos.php) \- Return a list of registered hashing algorithms
- [hash\_update()](https://www.php.net/manual/en/function.hash-update.php) \- Pump data into an active hashing context
- [hash\_update\_file()](https://www.php.net/manual/en/function.hash-update-file.php) \- Pump data into an active hashing context from a file
- [hash\_update\_stream()](https://www.php.net/manual/en/function.hash-update-stream.php) \- Pump data into an active hashing context from an open stream
- [hash\_final()](https://www.php.net/manual/en/function.hash-final.php) \- Finalize an incremental hash and return resulting digest

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/hash/functions/hash-init.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.hash-init%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.hash-init&repo=en&redirect=https://www.php.net/manual/en/function.hash-init.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google