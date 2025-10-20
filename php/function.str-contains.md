---
url: https://www.php.net/manual/en/function.str-contains.php
scraped_at: 2025-10-20T02:54:56.418Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# str\_contains

(PHP 8)

str\_contains — Determine if a string contains a given substring

### Description [¶](https://www.php.net/manual/en/function.str-contains.php\#refsect1-function.str-contains-description)

**str\_contains**([string](https://www.php.net/manual/en/language.types.string.php) `$haystack`, [string](https://www.php.net/manual/en/language.types.string.php) `$needle`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Performs a case-sensitive check indicating if `needle` is contained
in `haystack`.


### Parameters [¶](https://www.php.net/manual/en/function.str-contains.php\#refsect1-function.str-contains-parameters)

`haystack`

The string to search in.


`needle`

The substring to search for in the `haystack`.


### Return Values [¶](https://www.php.net/manual/en/function.str-contains.php\#refsect1-function.str-contains-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if `needle` is in
`haystack`, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.


### Examples [¶](https://www.php.net/manual/en/function.str-contains.php\#refsect1-function.str-contains-examples)

**Example #1 Using the empty string `''`**

`<?php
if (str_contains('abc', '')) {
    echo "Checking the existence of the empty string will always return true";
}
?>`

Run code

The above example will output:

```
Checking the existence of the empty string will always return true
```

**Example #2 Showing case-sensitivity**

`<?php
$string = 'The lazy fox jumped over the fence';
if (str_contains($string, 'lazy')) {
    echo "The string 'lazy' was found in the string\n";
}
if (str_contains($string, 'Lazy')) {
    echo 'The string "Lazy" was found in the string';
} else {
    echo '"Lazy" was not found because the case does not match';
}
?>`

Run code

The above example will output:

```
The string 'lazy' was found in the string
"Lazy" was not found because the case does not match
```

### Notes [¶](https://www.php.net/manual/en/function.str-contains.php\#refsect1-function.str-contains-notes)

> **Note**: This function is
> binary-safe.

### See Also [¶](https://www.php.net/manual/en/function.str-contains.php\#refsect1-function.str-contains-seealso)

- [str\_ends\_with()](https://www.php.net/manual/en/function.str-ends-with.php) \- Checks if a string ends with a given substring
- [str\_starts\_with()](https://www.php.net/manual/en/function.str-starts-with.php) \- Checks if a string starts with a given substring
- [stripos()](https://www.php.net/manual/en/function.stripos.php) \- Find the position of the first occurrence of a case-insensitive substring in a string
- [strrpos()](https://www.php.net/manual/en/function.strrpos.php) \- Find the position of the last occurrence of a substring in a string
- [strripos()](https://www.php.net/manual/en/function.strripos.php) \- Find the position of the last occurrence of a case-insensitive substring in a string
- [strstr()](https://www.php.net/manual/en/function.strstr.php) \- Find the first occurrence of a string
- [strpbrk()](https://www.php.net/manual/en/function.strpbrk.php) \- Search a string for any of a set of characters
- [substr()](https://www.php.net/manual/en/function.substr.php) \- Return part of a string
- [preg\_match()](https://www.php.net/manual/en/function.preg-match.php) \- Perform a regular expression match

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/str-contains.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.str-contains%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.str-contains&repo=en&redirect=https://www.php.net/manual/en/function.str-contains.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=125977&page=function.str-contains&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125977&page=function.str-contains&vote=down "Vote down!")

117


[**_scm6079_**](https://www.php.net/manual/en/function.str-contains.php#125977) [¶](https://www.php.net/manual/en/function.str-contains.php#125977)

**4 years ago**

`For earlier versions of PHP, you can polyfill the str_contains function using the following snippet:
<?php
// based on original work from the PHP Laravel framework
if (!function_exists('str_contains')) {
    function str_contains($haystack, $needle) {
        return $needle !== '' && mb_strpos($haystack, $needle) !== false;
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=128796&page=function.str-contains&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128796&page=function.str-contains&vote=down "Vote down!")

13


[**_harl at gmail dot com_**](https://www.php.net/manual/en/function.str-contains.php#128796) [¶](https://www.php.net/manual/en/function.str-contains.php#128796)

**2 years ago**

`A couple of functions for checking if a string contains any of the strings in an array, or all of the strings in an array:
<?php
function str_contains_any(string $haystack, array $needles): bool
{
    return array_reduce($needles, fn($a, $n) => $a || str_contains($haystack, $n), false);
}
function str_contains_all(string $haystack, array $needles): bool
{
    return array_reduce($needles, fn($a, $n) => $a && str_contains($haystack, $n), true);
}
?>
str_contains_all() will return true if $needles is an empty array. If you think that's wrong, show me a string in $needles that DOESN'T appear in the $haystack, and then look up "vacuous truth".
(By swapping haystacks and needles in the body of these functions you can create versions that check if a needle appears in any/all of an array of haystacks.)`

[up](https://www.php.net/manual/vote-note.php?id=126806&page=function.str-contains&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126806&page=function.str-contains&vote=down "Vote down!")

17


[**_aisunny7 dot xy at gmail dot com_**](https://www.php.net/manual/en/function.str-contains.php#126806) [¶](https://www.php.net/manual/en/function.str-contains.php#126806)

**3 years ago**

``The polyfill that based on original work from the PHP Laravel framework had a different behavior;
when the $needle is `""` or `null`:
php8's will return `true`;
but, laravel'str_contains will return `false`;
when php8.1, null is deprecated, You can use `$needle ?: ""`;``

[up](https://www.php.net/manual/vote-note.php?id=128826&page=function.str-contains&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128826&page=function.str-contains&vote=down "Vote down!")

5


[**_Ancyker_**](https://www.php.net/manual/en/function.str-contains.php#128826) [¶](https://www.php.net/manual/en/function.str-contains.php#128826)

**2 years ago**

`This function doesn't always produce the expected results if you have a needle that isn't UTF-8 but are looking for it in a UTF-8 string. This won't be a concern for most people, but if you are mixing old and new data, especially if reading data from a file, it could be an issue.
Here's a "mb_*"-esque function that searches the string:
<?php
function mb_str_contains(string $haystack, string $needle, $encoding = null) {
    return $needle === '' || mb_substr_count($haystack, $needle, (empty($encoding) ? mb_internal_encoding() : $encoding)) > 0;
}
?>
I used mb_substr_count() instead of mb_strpos() because mb_strpos() will still match partial characters as it's doing a binary search.
We can compare str_contains to the above suggested function:
<?php
// Some Unicode Kanji (漢字はユニコード)
$string = hex2bin('e6bca2e5ad97e381afe383a6e3838be382b3e383bce38389');
// Some Windows-1252 characters (ãƒ)
$contains = hex2bin('e383');
// ^ file_get_contents() produces the same data when it is saved as "ANSI" in Notepad on Windows, so this is not that unrealistic. The only reason to use hex2bin here is to mix character sets without having to use multiple files.
// A character that actually exists in our string. (ー)
$contains2 = hex2bin('e383bc');
echo " = Haystack: ".var_export($string, true)."\r\n";
echo " = Needles:\r\n";
echo "   + Windows-1252 characters\r\n";
echo "     - Results:\r\n";
echo "       >    str_contains: ".var_export(str_contains($string, $contains), true)."\r\n";
echo "       > mb_str_contains: ".var_export(mb_str_contains($string, $contains), true)."\r\n";
echo "   + Valid UTF-8 character\r\n";
echo "     - Results:\r\n";
echo "       >    str_contains: ".var_export(str_contains($string, $contains2), true)."\r\n";
echo "       > mb_str_contains: ".var_export(mb_str_contains($string, $contains2), true)."\r\n";
echo "\r\n";
?>
Output:
= Haystack: '漢字はユニコード'
= Needles:
+ Windows-1252 characters
     - Results:
       >    str_contains: true
       > mb_str_contains: false
+ Valid UTF-8 character
     - Results:
       >    str_contains: true
       > mb_str_contains: true
It's not completely foolproof, however. For instance, ãƒ‰ in Windows-1252 will match ド from the above string. So it's still best to convert the encoding of the parameters to be the same first. But, if the character set isn't known/can't be detected and you have no choice but to deal with dirty data, this is probably the simplest solution.`

[up](https://www.php.net/manual/vote-note.php?id=125952&page=function.str-contains&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125952&page=function.str-contains&vote=down "Vote down!")

3


[**_olivertasche+nospam at gmail dot com_**](https://www.php.net/manual/en/function.str-contains.php#125952) [¶](https://www.php.net/manual/en/function.str-contains.php#125952)

**4 years ago**

`The code from "me at daz dot co dot uk" will not work if the word is
- at the start of the string
- at the end of the string
- at the end of a sentence (like "the ox." or "is that an ox?")
- in quotes
- and so on.
You should explode the string by whitespace, punctations, ... and check if the resulting array contains your word OR try to test with a RegEx like this:
(^|[\s\W])+word($|[\s\W])+
Disclaimer: The RegEx may need some tweaks`

[up](https://www.php.net/manual/vote-note.php?id=126277&page=function.str-contains&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126277&page=function.str-contains&vote=down "Vote down!")

3


[**_juliyvchirkov at gmail dot com_**](https://www.php.net/manual/en/function.str-contains.php#126277) [¶](https://www.php.net/manual/en/function.str-contains.php#126277)

**4 years ago**

`<?php
// Polyfill for PHP 4 - PHP 7, safe to utilize with PHP 8
if (!function_exists('str_contains')) {
    function str_contains (string $haystack, string $needle)
    {
        return empty($needle) || strpos($haystack, $needle) !== false;
    }
}`

[up](https://www.php.net/manual/vote-note.php?id=127007&page=function.str-contains&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127007&page=function.str-contains&vote=down "Vote down!")

0


[**_drupalista dot com dot br at gmail dot com_**](https://www.php.net/manual/en/function.str-contains.php#127007) [¶](https://www.php.net/manual/en/function.str-contains.php#127007)

**3 years ago**

`private function contains(array $needles, string $type, string $haystack = NULL, string $filename = NULL) : bool {
        if (empty($needles)) return FALSE;
        if ($filename)
            $haystack = file_get_contents($filename);
        $now_what = function(string $needle) use ($haystack, $type) : array {
            $has_needle = str_contains($haystack, $needle);
            if ($type === 'any' && $has_needle)
                return ['done' => TRUE, 'return' => TRUE];
            if ($type === 'all' && !$has_needle)
                return ['done' => TRUE, 'return' => FALSE];
            return ['done' => FALSE];
        };
        foreach ($needles as $needle) {
            $check = $now_what($needle);
            if ($check['done'])
                return $check['return'];
        }
        return TRUE;
    }
    function containsAny(array $needles, string $haystack = NULL, string $filename = NULL) : bool {
        return self::contains($needles, 'any', $haystack, $filename);
    }
    function containsAll(array $needles, string $haystack = NULL, string $filename = NULL) : bool {
        return self::contains($needles, 'all', $haystack, $filename);
    }`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.str-contains&repo=en&redirect=https://www.php.net/manual/en/function.str-contains.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google