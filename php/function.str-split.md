---
url: https://www.php.net/manual/en/function.str-split.php
scraped_at: 2025-10-20T02:58:13.233Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# str\_split

(PHP 5, PHP 7, PHP 8)

str\_split — Convert a string to an array

### Description [¶](https://www.php.net/manual/en/function.str-split.php\#refsect1-function.str-split-description)

**str\_split**([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [int](https://www.php.net/manual/en/language.types.integer.php) `$length` = 1): [array](https://www.php.net/manual/en/language.types.array.php)

Converts a string to an array.


### Parameters [¶](https://www.php.net/manual/en/function.str-split.php\#refsect1-function.str-split-parameters)

`string`

The input string.


`length`

Maximum length of the chunk.


### Return Values [¶](https://www.php.net/manual/en/function.str-split.php\#refsect1-function.str-split-returnvalues)

If the optional `length` parameter is
specified, the returned array will be broken down into chunks with each
being `length` in length, except the final chunk
which may be shorter if the string does not divide evenly. The default
`length` is `1`, meaning every chunk will be one byte in size.


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.str-split.php\#refsect1-function.str-split-errors)

If `length` is less than `1`,
a [ValueError](https://www.php.net/manual/en/class.valueerror.php) will be thrown.


### Changelog [¶](https://www.php.net/manual/en/function.str-split.php\#refsect1-function.str-split-changelog)

| Version | Description |
| --- | --- |
| 8.2.0 | If `string` is empty an empty [array](https://www.php.net/manual/en/language.types.array.php) is now returned.<br> Previously an [array](https://www.php.net/manual/en/language.types.array.php) containing a single empty string was returned. |
| 8.0.0 | If `length` is less than `1`,<br> a [ValueError](https://www.php.net/manual/en/class.valueerror.php) will be thrown now;<br> previously, an error of level **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**<br> has been raised instead, and the function returned **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**. |

### Examples [¶](https://www.php.net/manual/en/function.str-split.php\#refsect1-function.str-split-examples)

**Example #1 Example uses of **str\_split()****

`<?php
$str = "Hello Friend";
$arr1 = str_split($str);
$arr2 = str_split($str, 3);
print_r($arr1);
print_r($arr2);
?>`

Run code

The above example will output:

```
Array
(
    [0] => H
    [1] => e
    [2] => l
    [3] => l
    [4] => o
    [5] =>
    [6] => F
    [7] => r
    [8] => i
    [9] => e
    [10] => n
    [11] => d
)

Array
(
    [0] => Hel
    [1] => lo
    [2] => Fri
    [3] => end
)
```

### Notes [¶](https://www.php.net/manual/en/function.str-split.php\#refsect1-function.str-split-notes)

> **Note**:
>
>
> **str\_split()** will split into bytes, rather than characters when dealing with a multi-byte encoded string.
> [mb\_str\_split()](https://www.php.net/manual/en/function.mb-str-split.php) can be used to split the string into code points.
> [grapheme\_str\_split()](https://www.php.net/manual/en/function.grapheme-str-split.php) can be used to split the string into grapheme clusters.

### See Also [¶](https://www.php.net/manual/en/function.str-split.php\#refsect1-function.str-split-seealso)

- [mb\_str\_split()](https://www.php.net/manual/en/function.mb-str-split.php) \- Given a multibyte string, return an array of its characters
- [grapheme\_str\_split()](https://www.php.net/manual/en/function.grapheme-str-split.php) \- Split a string into an array
- [chunk\_split()](https://www.php.net/manual/en/function.chunk-split.php) \- Split a string into smaller chunks
- [preg\_split()](https://www.php.net/manual/en/function.preg-split.php) \- Split string by a regular expression
- [explode()](https://www.php.net/manual/en/function.explode.php) \- Split a string by a string
- [count\_chars()](https://www.php.net/manual/en/function.count-chars.php) \- Return information about characters used in a string
- [str\_word\_count()](https://www.php.net/manual/en/function.str-word-count.php) \- Return information about words used in a string
- [for](https://www.php.net/manual/en/control-structures.for.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/str-split.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.str-split%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.str-split&repo=en&redirect=https://www.php.net/manual/en/function.str-split.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=128219&page=function.str-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128219&page=function.str-split&vote=down "Vote down!")

5


[**_Julian_**](https://www.php.net/manual/en/function.str-split.php#128219) [¶](https://www.php.net/manual/en/function.str-split.php#128219)

**2 years ago**

`The function str_split() is not 'aware' of words. Here is an adaptation of str_split() that is 'word-aware'.
<?php
$array =  str_split_word_aware(
    'In the beginning God created the heaven and the earth. And the earth was without form, and void; and darkness was upon the face of the deep.',
    32
);
var_dump($array);
/**
* This function is similar to str_split() but this function keeps words intact; it never splits through a word.
*
* @return array<int, string>
*/
function str_split_word_aware(string $string, int $maxLengthOfLine): array
{
    if ($maxLengthOfLine <= 0) {
        throw new RuntimeException(sprintf('The function %s() must have a max length of line at least greater than one', __FUNCTION__));
    }

    $lines = [];
    $words = explode(' ', $string);
    $currentLine = '';
    $lineAccumulator = '';
    foreach ($words as $currentWord) {
        $currentWordWithSpace = sprintf('%s ', $currentWord);
        $lineAccumulator .= $currentWordWithSpace;
        if (strlen($lineAccumulator) < $maxLengthOfLine) {
            $currentLine = $lineAccumulator;
            continue;
        }
        $lines[] = $currentLine;
        // Overwrite the current line and accumulator with the current word
        $currentLine = $currentWordWithSpace;
        $lineAccumulator = $currentWordWithSpace;
    }
    if ($currentLine !== '') {
        $lines[] = $currentLine;
    }
    return $lines;
}
?>
OUTPUT:
<?php
array(5) {
[0]=> string(29) "In the beginning God created "
[1]=> string(30) "the heaven and the earth. And "
[2]=> string(28) "the earth was without form, "
[3]=> string(27) "and void; and darkness was "
[4]=> string(27) "upon the face of the deep. "
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.str-split&repo=en&redirect=https://www.php.net/manual/en/function.str-split.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google