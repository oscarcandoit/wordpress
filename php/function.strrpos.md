---
url: https://www.php.net/manual/en/function.strrpos.php
scraped_at: 2025-10-20T02:48:38.394Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# strrpos

(PHP 4, PHP 5, PHP 7, PHP 8)

strrpos — Find the position of the last occurrence of a substring in a string

### Description [¶](https://www.php.net/manual/en/function.strrpos.php\#refsect1-function.strrpos-description)

**strrpos**([string](https://www.php.net/manual/en/language.types.string.php) `$haystack`, [string](https://www.php.net/manual/en/language.types.string.php) `$needle`, [int](https://www.php.net/manual/en/language.types.integer.php) `$offset` = 0): [int](https://www.php.net/manual/en/language.types.integer.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Find the numeric position of the last occurrence of
`needle` in the `haystack` string.


### Parameters [¶](https://www.php.net/manual/en/function.strrpos.php\#refsect1-function.strrpos-parameters)

`haystack`

The string to search in.


`needle`

The string to search for.


Prior to PHP 8.0.0, if `needle` is not a string, it is converted
to an integer and applied as the ordinal value of a character.
This behavior is deprecated as of PHP 7.3.0, and relying on it is highly
discouraged. Depending on the intended behavior, the
`needle` should either be explicitly cast to string,
or an explicit call to [chr()](https://www.php.net/manual/en/function.chr.php) should be performed.


`offset`


If zero or positive, the search is performed left to right skipping the
first `offset` bytes of the
`haystack`.


If negative, the search starts `offset` bytes from
the right instead of from the beginning of `haystack`.
The search is performed right to left, searching for the first
occurrence of `needle` from the selected byte.


> **Note**:
>
>
> This is effectively looking for the last occurrence of
> `needle` at or before the last
> `offset` bytes.

### Return Values [¶](https://www.php.net/manual/en/function.strrpos.php\#refsect1-function.strrpos-returnvalues)

Returns the position where the needle exists relative to the beginning of
the `haystack` string (independent of search direction
or offset).


> **Note**:
>
> String positions start at 0, and not 1.

Returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if the needle was not found.


**Warning**

This function may
return Boolean **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**, but may also return a non-Boolean value which
evaluates to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**. Please read the section on [Booleans](https://www.php.net/manual/en/language.types.boolean.php) for more
information. Use [the ===\\
operator](https://www.php.net/manual/en/language.operators.comparison.php) for testing the return value of this
function.

### Changelog [¶](https://www.php.net/manual/en/function.strrpos.php\#refsect1-function.strrpos-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `needle` now accepts an empty string. |
| 8.0.0 | Passing an [int](https://www.php.net/manual/en/language.types.integer.php) as `needle` is no longer supported. |
| 7.3.0 | Passing an [int](https://www.php.net/manual/en/language.types.integer.php) as `needle` has been deprecated. |

### Examples [¶](https://www.php.net/manual/en/function.strrpos.php\#refsect1-function.strrpos-examples)

**Example #1 Checking if a needle is in the haystack**

It is easy to mistake the return values for "character found at
position 0" and "character not found". Here's how to detect
the difference:


`<?php
$mystring = 'Elephpant';
$pos = strrpos($mystring, "b");
if ($pos === false) { // note: three equal signs
    // not found...
}
?>`

Run code

**Example #2 Searching with offsets**

`<?php
$foo = "0123456789a123456789b123456789c";
// Looking for '0' from the 0th byte (from the beginning)
var_dump(strrpos($foo, '0', 0));
// Looking for '0' from the 1st byte (after byte "0")
var_dump(strrpos($foo, '0', 1));
// Looking for '7' from the 21th byte (after byte 20)
var_dump(strrpos($foo, '7', 20));
// Looking for '7' from the 29th byte (after byte 28)
var_dump(strrpos($foo, '7', 28));
// Looking for '7' right to left from the 5th byte from the end
var_dump(strrpos($foo, '7', -5));
// Looking for 'c' right to left from the 2nd byte from the end
var_dump(strrpos($foo, 'c', -2));
// Looking for '9c' right to left from the 2nd byte from the end
var_dump(strrpos($foo, '9c', -2));
?>`

Run code

The above example will output:

```
int(0)
bool(false)
int(27)
bool(false)
int(17)
bool(false)
int(29)
```

### See Also [¶](https://www.php.net/manual/en/function.strrpos.php\#refsect1-function.strrpos-seealso)

- [strpos()](https://www.php.net/manual/en/function.strpos.php) \- Find the position of the first occurrence of a substring in a string
- [stripos()](https://www.php.net/manual/en/function.stripos.php) \- Find the position of the first occurrence of a case-insensitive substring in a string
- [strripos()](https://www.php.net/manual/en/function.strripos.php) \- Find the position of the last occurrence of a case-insensitive substring in a string
- [strrchr()](https://www.php.net/manual/en/function.strrchr.php) \- Find the last occurrence of a character in a string
- [substr()](https://www.php.net/manual/en/function.substr.php) \- Return part of a string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/strrpos.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.strrpos%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.strrpos&repo=en&redirect=https://www.php.net/manual/en/function.strrpos.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=76447&page=function.strrpos&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76447&page=function.strrpos&vote=down "Vote down!")

78


[**_brian at enchanter dot net_**](https://www.php.net/manual/en/function.strrpos.php#76447) [¶](https://www.php.net/manual/en/function.strrpos.php#76447)

**18 years ago**

`The documentation for 'offset' is misleading.
It says, "offset may be specified to begin searching an arbitrary number of characters into the string. Negative values will stop searching at an arbitrary point prior to the end of the string."
This is confusing if you think of strrpos as starting at the end of the string and working backwards.
A better way to think of offset is:
- If offset is positive, then strrpos only operates on the part of the string from offset to the end. This will usually have the same results as not specifying an offset, unless the only occurences of needle are before offset (in which case specifying the offset won't find the needle).
- If offset is negative, then strrpos only operates on that many characters at the end of the string. If the needle is farther away from the end of the string, it won't be found.
If, for example, you want to find the last space in a string before the 50th character, you'll need to do something like this:
strrpos($text, " ", -(strlen($text) - 50));
If instead you used strrpos($text, " ", 50), then you would find the last space between the 50th character and the end of the string, which may not have been what you were intending.`

[up](https://www.php.net/manual/vote-note.php?id=124027&page=function.strrpos&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124027&page=function.strrpos&vote=down "Vote down!")

5


[**_dave at pixelmetrics dot com_**](https://www.php.net/manual/en/function.strrpos.php#124027) [¶](https://www.php.net/manual/en/function.strrpos.php#124027)

**6 years ago**

`The description of offset is wrong. Here’s how it works, with supporting examples.
Offset effects both the starting point and stopping point of the search. The direction is always right to left. (The description wrongly says PHP searches left to right when offset is positive.)
Here’s how it works:
When offset is positive, PHP searches right to left from the end of haystack to offset. This ignores the left side of haystack.
When offset is negative, PHP searches right to left, starting offset bytes from the end, to the start of haystack. This ignores the right side of haystack.
Example 1:
$foo = ‘aaaaaaaaaa’;
var_dump(strrpos($foo, 'a', 5));
Result: int(10)
Example 2:
$foo = "aaaaaa67890";
var_dump(strrpos($foo, 'a', 5));
Result: int(5)
Conclusion: When offset is positive, PHP searches right to left from the end of haystack.
Example 3:
$foo = "aaaaa567890";
var_dump(strrpos($foo, 'a', 5));
Result: bool(false)
Conclusion: When offset is positive, PHP stops searching at offset.
Example 4:
$foo = ‘aaaaaaaaaa’;
var_dump(strrpos($foo, 'a', -5));
Result: int(6)
Conclusion: When offset is negative, PHP searches right to left, starting offset bytes from the end.
Example 5:
$foo = "a234567890";
var_dump(strrpos($foo, 'a', -5));
Result: int(0)
Conclusion: When offset is negative, PHP searches right to left, all the way to the start of haystack.`

[up](https://www.php.net/manual/vote-note.php?id=122559&page=function.strrpos&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122559&page=function.strrpos&vote=down "Vote down!")

3


[**_david dot mann at djmann dot co dot uk_**](https://www.php.net/manual/en/function.strrpos.php#122559) [¶](https://www.php.net/manual/en/function.strrpos.php#122559)

**7 years ago**

`Ten years on, Brian's note is still a good overview of how offsets work, but a shorter and simpler summary is:
    strrpos($x, $y, 50);  // 1: this tells strrpos() when to STOP, counting from the START of $x
    strrpos($x, $y, -50); // 2: this tells strrpos() when to START, counting from the END of $x
Or to put it another way, a positive number lets you search the rightmost section of the string, while a negative number lets you search the leftmost section of the string.
Both these variations are useful, but picking the wrong one can cause some highly confusing results!`

[up](https://www.php.net/manual/vote-note.php?id=78499&page=function.strrpos&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78499&page=function.strrpos&vote=down "Vote down!")

6


[**_Daniel Brinca_**](https://www.php.net/manual/en/function.strrpos.php#78499) [¶](https://www.php.net/manual/en/function.strrpos.php#78499)

**18 years ago**

`Here is a simple function to find the position of the next occurrence of needle in haystack, but searching backwards  (lastIndexOf type function):
//search backwards for needle in haystack, and return its position
function rstrpos ($haystack, $needle, $offset){
    $size = strlen ($haystack);
    $pos = strpos (strrev($haystack), $needle, $size - $offset);

    if ($pos === false)
        return false;

    return $size - $pos;
}
Note: supports full strings as needle`

[up](https://www.php.net/manual/vote-note.php?id=130438&page=function.strrpos&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130438&page=function.strrpos&vote=down "Vote down!")

0


[**_Anonymous_**](https://www.php.net/manual/en/function.strrpos.php#130438) [¶](https://www.php.net/manual/en/function.strrpos.php#130438)

**2 months ago**

`I just found out the hard way, that PHP 8.1 and 8.2 throw fatal errors if the offset is negative, and the string is too short.  Maybe ? also if the offset is positive and the string is too short?
I don't have complete documentation, but I believe the source string was either a null-string "" or "/" (representing the document's root).  The offset was (-2).  That threw a fatal error, but not using PHP 5.3 on my other server (old software there that's not getting updated).
So at what version does PHP start throwing fatal errors and shutting down your website?  When does PHP start forcing you to perform manual checks and write additional code to work?  I don't know.  Anybody else have a clue?`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.strrpos&repo=en&redirect=https://www.php.net/manual/en/function.strrpos.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google