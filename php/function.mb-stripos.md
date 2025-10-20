---
url: https://www.php.net/manual/en/function.mb-stripos.php
scraped_at: 2025-10-20T02:59:17.959Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# mb\_stripos

(PHP 5 >= 5.2.0, PHP 7, PHP 8)

mb\_stripos — Finds position of first occurrence of a string within another, case insensitive

### Description [¶](https://www.php.net/manual/en/function.mb-stripos.php\#refsect1-function.mb-stripos-description)

**mb\_stripos**(

[string](https://www.php.net/manual/en/language.types.string.php) `$haystack`,

[string](https://www.php.net/manual/en/language.types.string.php) `$needle`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$offset` = 0,

[?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$encoding` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**

): [int](https://www.php.net/manual/en/language.types.integer.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

**mb\_stripos()** returns the numeric position of
the first occurrence of `needle` in the
`haystack` string.
Unlike [mb\_strpos()](https://www.php.net/manual/en/function.mb-strpos.php),
**mb\_stripos()** is case-insensitive.
If `needle` is not found, it returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


### Parameters [¶](https://www.php.net/manual/en/function.mb-stripos.php\#refsect1-function.mb-stripos-parameters)

`haystack`

The string from which to get the position of the first occurrence
of `needle`

`needle`

The string to find in `haystack`

`offset`

The position in `haystack`
to start searching.
A negative offset counts from the end of the string.


`encoding`

Character encoding name to use.
If it is omitted, internal character encoding is used.


### Return Values [¶](https://www.php.net/manual/en/function.mb-stripos.php\#refsect1-function.mb-stripos-returnvalues)

Return the numeric position of the first occurrence of
`needle` in the `haystack`
string, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if `needle` is not found.


### Changelog [¶](https://www.php.net/manual/en/function.mb-stripos.php\#refsect1-function.mb-stripos-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `needle` now accepts an empty string. |
| 8.0.0 | `encoding` is nullable now. |
| 7.1.0 | Support for negative `offset` s has been added. |

### See Also [¶](https://www.php.net/manual/en/function.mb-stripos.php\#refsect1-function.mb-stripos-seealso)

- [stripos()](https://www.php.net/manual/en/function.stripos.php) \- Find the position of the first occurrence of a case-insensitive substring in a string
- [strpos()](https://www.php.net/manual/en/function.strpos.php) \- Find the position of the first occurrence of a substring in a string
- [mb\_strpos()](https://www.php.net/manual/en/function.mb-strpos.php) \- Find position of first occurrence of string in a string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mbstring/functions/mb-stripos.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.mb-stripos%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.mb-stripos&repo=en&redirect=https://www.php.net/manual/en/function.mb-stripos.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=124142&page=function.mb-stripos&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124142&page=function.mb-stripos&vote=down "Vote down!")

1


[**_FangTS\__**](https://www.php.net/manual/en/function.mb-stripos.php#124142) [¶](https://www.php.net/manual/en/function.mb-stripos.php#124142)

**6 years ago**

`How works on examples mb_stripos:
First we will watch example on symbols(..?).
<?php
$text = "Look! It's a text! Wow!"; //simple text
$spaceIsHere = mb_stripos($text," "); //you can replace " " on something what you need or want
$text2 = mb_substr($text,$spaceIsHere); //cutting text with $spaceIsHere
print ($text2);
/* Print will show that result:
" It's a text! Wow!"
Look. That " " wasn't cutted, because mb_substr don't write in var position after " " - he write WHERE is " " in string. */
?>
Also it can work on words, sentences...
Here's one of examples:
<?php
$text = "Look! It's a text! Wow!"; //familiar text, right?)
$afterNeededWord = mb_stripos($text,"text!"); //you can replace "text!" on something else what you need
$text3 = mb_substr($text, $afterNeededWord); //cutting string (it is string? im stupid in that question xD)
print ($text3);
/* Print will show that result:
"text! Wow!"
Explaining the same. */
?>
I hope it was useful with my "good" English skills. ;D
Have a nice day, coder.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.mb-stripos&repo=en&redirect=https://www.php.net/manual/en/function.mb-stripos.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google