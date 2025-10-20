---
url: https://www.php.net/manual/en/function.mb-stristr.php
scraped_at: 2025-10-20T02:58:09.898Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mb\_stristr

(PHP 5 >= 5.2.0, PHP 7, PHP 8)

mb\_stristr — Finds first occurrence of a string within another, case insensitive

### Description [¶](https://www.php.net/manual/en/function.mb-stristr.php\#refsect1-function.mb-stristr-description)

**mb\_stristr**(

[string](https://www.php.net/manual/en/language.types.string.php) `$haystack`,

[string](https://www.php.net/manual/en/language.types.string.php) `$needle`,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$before_needle` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**,

[?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$encoding` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**

): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

**mb\_stristr()** finds the first occurrence of
`needle` in `haystack`
and returns the portion of `haystack`.
Unlike [mb\_strstr()](https://www.php.net/manual/en/function.mb-strstr.php),
**mb\_stristr()** is case-insensitive.
If `needle` is not found, it returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


### Parameters [¶](https://www.php.net/manual/en/function.mb-stristr.php\#refsect1-function.mb-stristr-parameters)

`haystack`

The string from which to get the first occurrence
of `needle`

`needle`

The string to find in `haystack`

`before_needle`

Determines which portion of `haystack`
this function returns.
If set to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, it returns all of `haystack`
from the beginning to the first occurrence of `needle` (excluding needle).
If set to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**, it returns all of `haystack`
from the first occurrence of `needle` to the end (including needle).


`encoding`

Character encoding name to use.
If it is omitted, internal character encoding is used.


### Return Values [¶](https://www.php.net/manual/en/function.mb-stristr.php\#refsect1-function.mb-stristr-returnvalues)

Returns the portion of `haystack`,
or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if `needle` is not found.


### Changelog [¶](https://www.php.net/manual/en/function.mb-stristr.php\#refsect1-function.mb-stristr-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `needle` now accepts an empty string. |
| 8.0.0 | `encoding` is nullable now. |

### See Also [¶](https://www.php.net/manual/en/function.mb-stristr.php\#refsect1-function.mb-stristr-seealso)

- [stristr()](https://www.php.net/manual/en/function.stristr.php) \- Case-insensitive strstr
- [strstr()](https://www.php.net/manual/en/function.strstr.php) \- Find the first occurrence of a string
- [mb\_strstr()](https://www.php.net/manual/en/function.mb-strstr.php) \- Finds first occurrence of a string within another

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mbstring/functions/mb-stristr.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.mb-stristr%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.mb-stristr&repo=en&redirect=https://www.php.net/manual/en/function.mb-stristr.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=127048&page=function.mb-stristr&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127048&page=function.mb-stristr&vote=down "Vote down!")

1


[**_nowfel dot terki at mailfence dot com_**](https://www.php.net/manual/en/function.mb-stristr.php#127048) [¶](https://www.php.net/manual/en/function.mb-stristr.php#127048)

**3 years ago**

`Be aware that if needle is an empty string, mb_stristr return the haystack by default.
For exemple:
<?php
if (mb_stristr("foo", "")) {
    echo "We enter in condition";
}
?>
Because in the above exemple the return of mb_stristr is "foo".
So if we do not want this kind of behaviour, we must set the third argument, ($before_needle) to true.
<?php
if (mb_stristr("foo", "", true)) {
    echo "We do not enter in condition";
}
?>
It can be useful to know it, specially when needle is dynamic.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.mb-stristr&repo=en&redirect=https://www.php.net/manual/en/function.mb-stristr.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google