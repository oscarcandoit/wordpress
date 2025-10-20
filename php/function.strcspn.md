---
url: https://www.php.net/manual/en/function.strcspn.php
scraped_at: 2025-10-20T03:01:43.891Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# strcspn

(PHP 4, PHP 5, PHP 7, PHP 8)

strcspn — Find length of initial segment not matching mask

### Description [¶](https://www.php.net/manual/en/function.strcspn.php\#refsect1-function.strcspn-description)

**strcspn**(

[string](https://www.php.net/manual/en/language.types.string.php) `$string`,

[string](https://www.php.net/manual/en/language.types.string.php) `$characters`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$offset` = 0,

[?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$length` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**

): [int](https://www.php.net/manual/en/language.types.integer.php)

Returns the length of the initial segment of
`string` which does _not_
contain any of the characters in `characters`.


If `offset` and `length`
are omitted, then all of `string` will be
examined. If they are included, then the effect will be the same as
calling `strcspn(substr($string, $offset, $length),
$characters)` (see [substr](https://www.php.net/manual/en/function.substr.php)
for more information).


### Parameters [¶](https://www.php.net/manual/en/function.strcspn.php\#refsect1-function.strcspn-parameters)

`string`

The string to examine.


`characters`

The string containing every disallowed character.


`offset`

The position in `string` to
start searching.


If `offset` is given and is non-negative,
then **strcspn()** will begin
examining `string` at
the `offset`'th position. For instance, in
the string ' `abcdef`', the character at
position `0` is ' `a`', the
character at position `2` is
' `c`', and so forth.


If `offset` is given and is negative,
then **strcspn()** will begin
examining `string` at
the `offset`'th position from the end
of `string`.


`length`

The length of the segment from `string`
to examine.


If `length` is given and is non-negative,
then `string` will be examined
for `length` characters after the starting
position.


If `length` is given and is negative,
then `string` will be examined from the
starting position up to `length`
characters from the end of `string`.


### Return Values [¶](https://www.php.net/manual/en/function.strcspn.php\#refsect1-function.strcspn-returnvalues)

Returns the length of the initial segment of `string`
which consists entirely of characters _not_ in `characters`.


> **Note**:
>
>
> When a `offset` parameter is set, the returned length
> is counted starting from this position, not from the beginning of
> `string`.

### Changelog [¶](https://www.php.net/manual/en/function.strcspn.php\#refsect1-function.strcspn-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Prior to PHP 8.4.0, when `characters` was the empty string,<br> the search would incorrectly stop at the first null byte in `string`. |
| 8.0.0 | `length` is nullable now. |

### Examples [¶](https://www.php.net/manual/en/function.strcspn.php\#refsect1-function.strcspn-examples)

**Example #1 **strcspn()** example**

`<?php
$a = strcspn('banana', 'a');
$b = strcspn('banana', 'abcd');
$c = strcspn('banana', 'z');
$d = strcspn('abcdhelloabcd', 'a', -9);
$e = strcspn('abcdhelloabcd', 'a', -9, -5);
var_dump($a);
var_dump($b);
var_dump($c);
var_dump($d);
var_dump($e);
?>`

Run code

The above example will output:

```
int(1)
int(0)
int(6)
int(5)
int(4)
```

### Notes [¶](https://www.php.net/manual/en/function.strcspn.php\#refsect1-function.strcspn-notes)

> **Note**: This function is
> binary-safe.

### See Also [¶](https://www.php.net/manual/en/function.strcspn.php\#refsect1-function.strcspn-seealso)

- [strspn()](https://www.php.net/manual/en/function.strspn.php) \- Finds the length of the initial segment of a string consisting
entirely of characters contained within a given mask

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/strcspn.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.strcspn%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.strcspn&repo=en&redirect=https://www.php.net/manual/en/function.strcspn.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=60118&page=function.strcspn&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60118&page=function.strcspn&vote=down "Vote down!")

13


[**_AT-HE (at\_he AT hotmai1 DOT com)_**](https://www.php.net/manual/en/function.strcspn.php#60118) [¶](https://www.php.net/manual/en/function.strcspn.php#60118)

**19 years ago**

`this function can be used like strspn(), except while that can be used to compare a string with an allowed pattern, this one can be use to compare a string with a FORBIDDEN pattern
so, to know if any forbidden character has a position inside our string, we can use (not tested with backslashes)...
<?php
// LARGE VERSION
$forbidden="\"\\?*:/@|<>";
if (strlen($filename) != strcspn($filename,$forbidden)) {
    echo "you cant create a file with that name!";
}
// SHORT VERSION
if (strlen($filename) - strcspn($filename,"\"\\?*:/@|<>")) {
    echo "i told you, you cant create that file";
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=57670&page=function.strcspn&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=57670&page=function.strcspn&vote=down "Vote down!")

10


[**_maskedcoder at hotmail dot com_**](https://www.php.net/manual/en/function.strcspn.php#57670) [¶](https://www.php.net/manual/en/function.strcspn.php#57670)

**20 years ago**

`useful for finding beginning of quotes and/or tags in a variable containing html.
    $pos = strcspn($data, '<"\'');
will find the first occurance of either the beginning of a tag, or a double- or single-quoted string.`

[up](https://www.php.net/manual/vote-note.php?id=101324&page=function.strcspn&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101324&page=function.strcspn&vote=down "Vote down!")

4


[**_legacyprog at routinz dot net_**](https://www.php.net/manual/en/function.strcspn.php#101324) [¶](https://www.php.net/manual/en/function.strcspn.php#101324)

**14 years ago**

`When you use the third parameter remember that the function will return the number of characters it bypassed, which will *not* be the position in your source string.  It's a simple fix to just add your third parameter value to the function result to get the position in the first string where the scan stopped, but I didn't think of it at first.`

[up](https://www.php.net/manual/vote-note.php?id=94110&page=function.strcspn&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94110&page=function.strcspn&vote=down "Vote down!")

4


[**_Anonymous_**](https://www.php.net/manual/en/function.strcspn.php#94110) [¶](https://www.php.net/manual/en/function.strcspn.php#94110)

**16 years ago**

`strcspn() can also be thought of as analogous to the following regular expression:
<?php
// where ... represents the mask of characters
preg_match('/[^ ...]/', substr($subject, $start, $length) );
?>
By this analogy, strcspn() can be used in place of some regular expressions to match a pattern without the overhead of a regex engine -- for example, ways to verify if an input string represents a binary value:
<?php
preg_match('/^[01]+$/i', $subject);
// or...
!preg_match('/[^01]/i', $subject);
// ...or using strcspn()
!strcspn($subject, '01');
?>`

[up](https://www.php.net/manual/vote-note.php?id=119826&page=function.strcspn&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119826&page=function.strcspn&vote=down "Vote down!")

2


[**_nospam at nospam dot com_**](https://www.php.net/manual/en/function.strcspn.php#119826) [¶](https://www.php.net/manual/en/function.strcspn.php#119826)

**9 years ago**

`It might not be clear from the example, that
strcspn('abcdhelloabcd', 'abcd', -9, -5) == 4
because it's only evaluating 'hell' which doesn't contain any mask, so returns strlen('hell').`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.strcspn&repo=en&redirect=https://www.php.net/manual/en/function.strcspn.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google