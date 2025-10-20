---
url: https://www.php.net/manual/en/function.mb-lcfirst.php
scraped_at: 2025-10-20T02:54:50.919Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mb\_lcfirst

(PHP 8 >= 8.4.0)

mb\_lcfirst — Make a string's first character lowercase

### Description [¶](https://www.php.net/manual/en/function.mb-lcfirst.php\#refsect1-function.mb-lcfirst-description)

**mb\_lcfirst**([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$encoding` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [string](https://www.php.net/manual/en/language.types.string.php)

Performs a multi-byte safe [lcfirst()](https://www.php.net/manual/en/function.lcfirst.php) operation,
and returns a string with the first character of
`string` lowercased.


### Parameters [¶](https://www.php.net/manual/en/function.mb-lcfirst.php\#refsect1-function.mb-lcfirst-parameters)

`string`
The input string.
`encoding`

The `encoding`
parameter is the character encoding. If it is omitted or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, the internal character
encoding value will be used.

### Return Values [¶](https://www.php.net/manual/en/function.mb-lcfirst.php\#refsect1-function.mb-lcfirst-returnvalues)

Returns the resulting string.


### See Also [¶](https://www.php.net/manual/en/function.mb-lcfirst.php\#refsect1-function.mb-lcfirst-seealso)

- [mb\_ucfirst()](https://www.php.net/manual/en/function.mb-ucfirst.php) \- Make a string's first character uppercase
- [lcfirst()](https://www.php.net/manual/en/function.lcfirst.php) \- Make a string's first character lowercase

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mbstring/functions/mb-lcfirst.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.mb-lcfirst%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.mb-lcfirst&repo=en&redirect=https://www.php.net/manual/en/function.mb-lcfirst.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google