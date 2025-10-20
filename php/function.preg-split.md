---
url: https://www.php.net/manual/en/function.preg-split.php
scraped_at: 2025-10-20T02:58:44.207Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# preg\_split

(PHP 4, PHP 5, PHP 7, PHP 8)

preg\_split — Split string by a regular expression

### Description [¶](https://www.php.net/manual/en/function.preg-split.php\#refsect1-function.preg-split-description)

**preg\_split**(

[string](https://www.php.net/manual/en/language.types.string.php) `$pattern`,

[string](https://www.php.net/manual/en/language.types.string.php) `$subject`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$limit` = -1,

[int](https://www.php.net/manual/en/language.types.integer.php) `$flags` = 0

): [array](https://www.php.net/manual/en/language.types.array.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Split the given string by a regular expression.


### Parameters [¶](https://www.php.net/manual/en/function.preg-split.php\#refsect1-function.preg-split-parameters)

`pattern`

The pattern to search for, as a string.


`subject`

The input string.


`limit`

If specified, then only substrings up to `limit`
are returned with the rest of the string being placed in the last
substring. A `limit` of -1 or 0 means "no limit".


`flags`

`flags` can be any combination of the following
flags (combined with the `|` bitwise operator):


**`[PREG\_SPLIT\_NO\_EMPTY](https://www.php.net/manual/en/pcre.constants.php#constant.preg-split-no-empty)`**
If this flag is set, only non-empty pieces will be returned by
**preg\_split()**.
**`[PREG\_SPLIT\_DELIM\_CAPTURE](https://www.php.net/manual/en/pcre.constants.php#constant.preg-split-delim-capture)`**
If this flag is set, parenthesized expression in the delimiter pattern
will be captured and returned as well.
**`[PREG\_SPLIT\_OFFSET\_CAPTURE](https://www.php.net/manual/en/pcre.constants.php#constant.preg-split-offset-capture)`**

If this flag is set, for every occurring match the appendant string
offset will also be returned. Note that this changes the return
value in an array where every element is an array consisting of the
matched string at offset `0` and its string offset
into `subject` at offset `1`.


### Return Values [¶](https://www.php.net/manual/en/function.preg-split.php\#refsect1-function.preg-split-returnvalues)

Returns an array containing substrings of `subject`
split along boundaries matched by `pattern`, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.preg-split.php\#refsect1-function.preg-split-errors)

If the regex pattern passed does not compile to a valid regex, an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is emitted.

### Examples [¶](https://www.php.net/manual/en/function.preg-split.php\#refsect1-function.preg-split-examples)

**Example #1 **preg\_split()** example : Get the parts of a search string**

`<?php
// split the phrase by any number of commas or space characters,
// which include " ", \r, \t, \n and \f
$keywords = preg_split("/[\s,]+/", "hypertext language, programming");
print_r($keywords);
?>`

Run code

The above example will output:

```
Array
(
    [0] => hypertext
    [1] => language
    [2] => programming
)
```

**Example #2 Splitting a string into component characters**

`<?php
$str = 'string';
$chars = preg_split('//', $str, -1, PREG_SPLIT_NO_EMPTY);
print_r($chars);
?>`

Run code

The above example will output:

```
Array
(
    [0] => s
    [1] => t
    [2] => r
    [3] => i
    [4] => n
    [5] => g
)
```

**Example #3 Splitting a string into matches and their offsets**

`<?php
$str = 'hypertext language programming';
$chars = preg_split('/ /', $str, -1, PREG_SPLIT_OFFSET_CAPTURE);
print_r($chars);
?>`

Run code

The above example will output:

```
Array
(
    [0] => Array
        (
            [0] => hypertext
            [1] => 0
        )

    [1] => Array
        (
            [0] => language
            [1] => 10
        )

    [2] => Array
        (
            [0] => programming
            [1] => 19
        )

)
```

### Notes [¶](https://www.php.net/manual/en/function.preg-split.php\#refsect1-function.preg-split-notes)

**Tip**

If you don't need the power of regular expressions, you can choose
faster (albeit simpler) alternatives like [explode()](https://www.php.net/manual/en/function.explode.php)
or [str\_split()](https://www.php.net/manual/en/function.str-split.php).


**Tip**

If matching fails, an array with a single element containing the input string will be returned.


### See Also [¶](https://www.php.net/manual/en/function.preg-split.php\#refsect1-function.preg-split-seealso)

- [PCRE Patterns](https://www.php.net/manual/en/pcre.pattern.php)
- [preg\_quote()](https://www.php.net/manual/en/function.preg-quote.php) \- Quote regular expression characters
- [explode()](https://www.php.net/manual/en/function.explode.php) \- Split a string by a string
- [preg\_match()](https://www.php.net/manual/en/function.preg-match.php) \- Perform a regular expression match
- [preg\_match\_all()](https://www.php.net/manual/en/function.preg-match-all.php) \- Perform a global regular expression match
- [preg\_replace()](https://www.php.net/manual/en/function.preg-replace.php) \- Perform a regular expression search and replace
- [preg\_last\_error()](https://www.php.net/manual/en/function.preg-last-error.php) \- Returns the error code of the last PCRE regex execution

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/pcre/functions/preg-split.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.preg-split%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.preg-split&repo=en&redirect=https://www.php.net/manual/en/function.preg-split.php)

### User Contributed Notes 19 notes

[up](https://www.php.net/manual/vote-note.php?id=94238&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94238&page=function.preg-split&vote=down "Vote down!")

45


[**_jan dot sochor at icebolt dot info_**](https://www.php.net/manual/en/function.preg-split.php#94238) [¶](https://www.php.net/manual/en/function.preg-split.php#94238)

**15 years ago**

`Sometimes PREG_SPLIT_DELIM_CAPTURE does strange results.
<?php
$content = '<strong>Lorem ipsum dolor</strong> sit <img src="test.png" />amet <span class="test" style="color:red">consec<i>tet</i>uer</span>.';
$chars = preg_split('/<[^>]*[^\/]>/i', $content, -1, PREG_SPLIT_NO_EMPTY | PREG_SPLIT_DELIM_CAPTURE);
print_r($chars);
?>
Produces:
Array
(
    [0] => Lorem ipsum dolor
    [1] =>  sit <img src="test.png" />amet
    [2] => consec
    [3] => tet
    [4] => uer
)
So that the delimiter patterns are missing. If you wanna get these patters remember to use parentheses.
<?php
$chars = preg_split('/(<[^>]*[^\/]>)/i', $content, -1, PREG_SPLIT_NO_EMPTY | PREG_SPLIT_DELIM_CAPTURE);
print_r($chars); //parentheses added
?>
Produces:
Array
(
    [0] => <strong>
    [1] => Lorem ipsum dolor
    [2] => </strong>
    [3] =>  sit <img src="test.png" />amet
    [4] => <span class="test" style="color:red">
    [5] => consec
    [6] => <i>
    [7] => tet
    [8] => </i>
    [9] => uer
    [10] => </span>
    [11] => .
)`

[up](https://www.php.net/manual/vote-note.php?id=92632&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92632&page=function.preg-split&vote=down "Vote down!")

19


[**_buzoganylaszlo at yahoo dot com_**](https://www.php.net/manual/en/function.preg-split.php#92632) [¶](https://www.php.net/manual/en/function.preg-split.php#92632)

**16 years ago**

`Extending m.timmermans's solution, you can use the following code as a search expression parser:
<?php
$search_expression = "apple bear \"Tom Cruise\" or 'Mickey Mouse' another word";
$words = preg_split("/[\s,]*\\\"([^\\\"]+)\\\"[\s,]*|" . "[\s,]*'([^']+)'[\s,]*|" . "[\s,]+/", $search_expression, 0, PREG_SPLIT_NO_EMPTY | PREG_SPLIT_DELIM_CAPTURE);
print_r($words);
?>
The result will be:
Array
(
    [0] => apple
    [1] => bear
    [2] => Tom Cruise
    [3] => or
    [4] => Mickey Mouse
    [5] => another
    [6] => word
)
1. Accepted delimiters: white spaces (space, tab, new line etc.) and commas.
2. You can use either simple (') or double (") quotes for expressions which contains more than one word.`

[up](https://www.php.net/manual/vote-note.php?id=124158&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124158&page=function.preg-split&vote=down "Vote down!")

9


[**_Hayley Watson_**](https://www.php.net/manual/en/function.preg-split.php#124158) [¶](https://www.php.net/manual/en/function.preg-split.php#124158)

**6 years ago**

`Assuming you're using UTF-8, this function can be used to separate Unicode text into individual codepoints without the need for the multibyte extension.
<?php
preg_split('//u', $text, -1, PREG_SPLIT_NO_EMPTY);
?>
The words "English", "Español", and "Русский" are all seven letters long. But strlen would report string lengths 7, 8 and 14, respectively. The preg_split above would return a seven-element array in all three cases.
It splits '한국어' into the array ['한', '국', '어'] instead of the 9-character array that str_split($text) would produce.`

[up](https://www.php.net/manual/vote-note.php?id=118326&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118326&page=function.preg-split&vote=down "Vote down!")

10


[**_canadian dot in dot exile at gmail dot com_**](https://www.php.net/manual/en/function.preg-split.php#118326) [¶](https://www.php.net/manual/en/function.preg-split.php#118326)

**9 years ago**

`This regular expression will split a long string of words into an array of sub-strings, of some maximum length, but only on word-boundries.
I use the reg-ex with preg_match_all(); but, I'm posting this example here (on the page for preg_split()) because that's where I looked when I wanted to find a way to do this.
Hope it saves someone some time.
<?php
// example of a long string of words
$long_string = 'Your IP Address will be logged with the submitted note and made public on the PHP manual user notes mailing list. The IP address is logged as part of the notes moderation process, and won\'t be shown within the PHP manual itself.';
// "word-wrap" at, for example, 60 characters or less
$max_len = 60;
// this regular expression will split $long_string on any sub-string of
// 1-or-more non-word characters (spaces or punctuation)
if(preg_match_all("/.{1,{$max_len}}(?=\W+)/", $long_string, $lines) !== False) {
    // $lines now contains an array of sub-strings, each will be approx.
    // $max_len characters - depending on where the last word ended and
    // the number of 'non-word' characters found after the last word
    for ($i=0; $i < count($lines[0]); $i++) {
        echo "[$i] {$lines[0][$i]}\n";
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=100729&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100729&page=function.preg-split&vote=down "Vote down!")

15


[**_Daniel Schroeder_**](https://www.php.net/manual/en/function.preg-split.php#100729) [¶](https://www.php.net/manual/en/function.preg-split.php#100729)

**14 years ago**

`If you want to split by a char, but want to ignore that char in case it is escaped, use a lookbehind assertion.
In this example a string will be split by ":" but "\:" will be ignored:
<?php
$string='a:b:c\:d';
$array=preg_split('#(?<!\\\)\:#',$string);
print_r($array);
?>
Results into:
Array
(
    [0] => a
    [1] => b
    [2] => c\:d
)`

[up](https://www.php.net/manual/vote-note.php?id=104602&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104602&page=function.preg-split&vote=down "Vote down!")

13


[**_eric at clarinova dot com_**](https://www.php.net/manual/en/function.preg-split.php#104602) [¶](https://www.php.net/manual/en/function.preg-split.php#104602)

**14 years ago**

`Here is another way to split a CamelCase string, which is a simpler expression than the one using lookaheads and lookbehinds:
preg_split('/([[:upper:]][[:lower:]]+)/', $last, null, PREG_SPLIT_DELIM_CAPTURE|PREG_SPLIT_NO_EMPTY)
It makes the entire CamelCased word the delimiter, then returns the delimiters (PREG_SPLIT_DELIM_CAPTURE) and omits the empty values between the delimiters (PREG_SPLIT_NO_EMPTY)`

[up](https://www.php.net/manual/vote-note.php?id=126520&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126520&page=function.preg-split&vote=down "Vote down!")

1


[**_dewi at dewimorgan dot com_**](https://www.php.net/manual/en/function.preg-split.php#126520) [¶](https://www.php.net/manual/en/function.preg-split.php#126520)

**3 years ago**

`Beware that it is not safe to assume there are no empty values returned by PREG_SPLIT_NO_EMPTY, nor that you will see no delimiters if you use PREG_SPLIT_DELIM_CAPTURE, as there are some edge cases where these are not true.
<?php
# As expected, splitting a string by itself returns two empty strings:
var_export(preg_split("/x/", "x"));
array (
0 => '',
1 => '',
)
# But if we add PREG_SPLIT_NO_EMPTY, then instead of an empty array, we get the delimiter.
var_export(preg_split("/x/", "x", PREG_SPLIT_NO_EMPTY));
array (
0 => 'x',
)
And if we try to split an empty string, then instead of an empty array, we get an empty string even with PREG_SPLIT_NO_EMPTY.
var_export(preg_split("/x/", "", PREG_SPLIT_NO_EMPTY));
array (
0 => '',
)
?>`

[up](https://www.php.net/manual/vote-note.php?id=101109&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101109&page=function.preg-split&vote=down "Vote down!")

6


[**_PhoneixSegovia at gmail dot com_**](https://www.php.net/manual/en/function.preg-split.php#101109) [¶](https://www.php.net/manual/en/function.preg-split.php#101109)

**14 years ago**

`You must be caution when using lookbehind to a variable match.
For example:
'/(?<!\\\)\r?\n)/'
to match a new line when not \ is before it don't go as spected as it match \r as the lookbehind (becouse isn't a \) and is optional before \n.
You must use this for example:
'/((?<!\\\|\r)\n)|((?<!\\\)\r\n)/'
That match a alone \n (not preceded by \r or \) or a \r\n not preceded by a \.`

[up](https://www.php.net/manual/vote-note.php?id=51209&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=51209&page=function.preg-split&vote=down "Vote down!")

4


[**_Steve_**](https://www.php.net/manual/en/function.preg-split.php#51209) [¶](https://www.php.net/manual/en/function.preg-split.php#51209)

**20 years ago**

`preg_split() behaves differently from perl's split() if the string ends with a delimiter. This perl snippet will print 5:
my @a = split(/ /, "a b c d e ");
print scalar @a;
The corresponding php code prints 6:
<?php print count(preg_split("/ /", "a b c d e ")); ?>
This is not necessarily a bug (nowhere does the documentation say that preg_split() behaves the same as perl's split()) but it might surprise perl programmers.`

[up](https://www.php.net/manual/vote-note.php?id=93907&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93907&page=function.preg-split&vote=down "Vote down!")

4


[**_php at dmi dot me dot uk_**](https://www.php.net/manual/en/function.preg-split.php#93907) [¶](https://www.php.net/manual/en/function.preg-split.php#93907)

**16 years ago**

`To split a camel-cased string using preg_split() with lookaheads and lookbehinds:
<?php
function splitCamelCase($str) {
return preg_split('/(?<=\\w)(?=[A-Z])/', $str);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=45982&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=45982&page=function.preg-split&vote=down "Vote down!")

7


[**_jetsoft at iinet.net.au_**](https://www.php.net/manual/en/function.preg-split.php#45982) [¶](https://www.php.net/manual/en/function.preg-split.php#45982)

**21 years ago**

`To clarify the "limit" parameter and the PREG_SPLIT_DELIM_CAPTURE option,
<?php
$preg_split('(/ /)', '1 2 3 4 5 6 7 8', 4 ,PREG_SPLIT_DELIM_CAPTURE );
?>
returns:
('1', ' ', '2', ' ' , '3', ' ', '4 5 6 7 8')
So you actually get 7 array items not 4`

[up](https://www.php.net/manual/vote-note.php?id=89649&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=89649&page=function.preg-split&vote=down "Vote down!")

3


[**_csaba at alum dot mit dot edu_**](https://www.php.net/manual/en/function.preg-split.php#89649) [¶](https://www.php.net/manual/en/function.preg-split.php#89649)

**16 years ago**

`If the task is too complicated for preg_split, preg_match_all might come in handy, since preg_split is essentially a special case.
I wanted to split a string on a certain character (asterisk), but only if it wasn't escaped (by a preceding backslash).  Thus, I should ensure an even number of backslashes before any asterisk meant as a splitter.  Look-behind in a regular expression wouldn't work since the length of the preceding backslash sequence can't be fixed.  So I turned to preg_match_all:
<?php
// split a string at unescaped asterisks
// where backslash is the escape character
$splitter = "/\\*((?:[^\\\\*]|\\\\.)*)/";
preg_match_all($splitter, "*$string", $aPieces, PREG_PATTERN_ORDER);
$aPieces = $aPieces[1];
// $aPieces now contains the exploded string
// and unescaping can be safely done on each piece
foreach ($aPieces as $idx=>$piece)
$aPieces[$idx] = preg_replace("/\\\\(.)/s", "$1", $piece);
?>`

[up](https://www.php.net/manual/vote-note.php?id=104618&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104618&page=function.preg-split&vote=down "Vote down!")

3


[**_david dot binovec at gmail dot com_**](https://www.php.net/manual/en/function.preg-split.php#104618) [¶](https://www.php.net/manual/en/function.preg-split.php#104618)

**14 years ago**

`Limit = 1 may be confusing. The important thing is that in case of limit equals to 1 will produce only ONE substring. Ergo the only one substring will be the first one as well as the last one. Tnat the rest of the string (after the first delimiter) will be placed to the last substring. But last is the first and only one.
<?php
$output = $preg_split('(/ /)', '1 2 3 4 5 6 7 8', 1);
echo $output[0] //will return whole string!;
$output = $preg_split('(/ /)', '1 2 3 4 5 6 7 8', 2);
echo $output[0] //will return 1;
echo $output[1] //will return '2 3 4 5 6 7 8';
?>`

[up](https://www.php.net/manual/vote-note.php?id=114474&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114474&page=function.preg-split&vote=down "Vote down!")

1


[**_Miller_**](https://www.php.net/manual/en/function.preg-split.php#114474) [¶](https://www.php.net/manual/en/function.preg-split.php#114474)

**11 years ago**

`This is a function to truncate a string of text while preserving the whitespace (for instance, getting an excerpt from an article while maintaining newlines). It will not jive well with HTML, of course.
<?php
/**
* Truncates a string of text by word count
* @param string $text The text to truncate
* @param int $max_words The maximum number of words
* @return string The truncated text
*/
function limit_words ($text, $max_words) {
    $split = preg_split('/(\s+)/', $text, -1, PREG_SPLIT_DELIM_CAPTURE);
    $truncated = '';
    for ($i = 0; $i < min(count($split), $max_words*2); $i += 2) {
        $truncated .= $split[$i].$split[$i+1];
    }
    return trim($truncated);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=130187&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130187&page=function.preg-split&vote=down "Vote down!")

1


[**_virtualryzen at gmail dot com_**](https://www.php.net/manual/en/function.preg-split.php#130187) [¶](https://www.php.net/manual/en/function.preg-split.php#130187)

**6 months ago**

`Using the flags requires passing a limit option even if you desire no limit, use 0 or -1.
Otherwise the result is unexpected, as the flags, being predefined constants, are integers and will be taken as the split limit not the  flag as intended.
echo PREG_SPLIT_DELIM_CAPTURE,' ', PREG_SPLIT_NO_EMPTY,' ', PREG_SPLIT_OFFSET_CAPTURE,"\n";
echos:  2 1 4
print_r(preg_split('//', '131.95M', PREG_SPLIT_NO_EMPTY) );
produces array: [ '131.95M']
as limit is actually set to 1
print_r( preg_split('//', '131.95M', 0, PREG_SPLIT_NO_EMPTY) );
produces array: [ "1", "3", "1", ".", "9", "5", "M"]
print_r( preg_split('/([[:alpha:]])/', '131.95M', PREG_SPLIT_DELIM_CAPTURE | PREG_SPLIT_NO_EMPTY) );
produces array:  [ '131.95', '']
print_r( preg_split('/([[:alpha:]])/', '131.95M', -1, PREG_SPLIT_DELIM_CAPTURE | PREG_SPLIT_NO_EMPTY) );
produces array: [ '131.95', 'M']`

[up](https://www.php.net/manual/vote-note.php?id=127151&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127151&page=function.preg-split&vote=down "Vote down!")

0


[**_Walf_**](https://www.php.net/manual/en/function.preg-split.php#127151) [¶](https://www.php.net/manual/en/function.preg-split.php#127151)

**3 years ago**

`Using PREG_SPLIT_DELIM_CAPTURE without PREG_SPLIT_NO_EMPTY guarantees that all the odd-numbered keys in the result will contain the delimiters. This makes further processing more predictable, and empty strings can always be filtered out at the end.`

[up](https://www.php.net/manual/vote-note.php?id=91067&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91067&page=function.preg-split&vote=down "Vote down!")

0


[**_kenorb at gmail dot com_**](https://www.php.net/manual/en/function.preg-split.php#91067) [¶](https://www.php.net/manual/en/function.preg-split.php#91067)

**16 years ago**

`If you need convert function arguments without default default values and references, you can try this code:
<?php
    $func_args = '$node, $op, $a3 = NULL, $form = array(), $a4 = NULL'
    $call_arg = preg_match_all('@(?<func_arg>\$[^,= ]+)@i', $func_args, $matches);
    $call_arg = implode(',', $matches['func_arg']);
?>
Result: string = "$node,$op,$a3,$form,$a4"`

[up](https://www.php.net/manual/vote-note.php?id=116490&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116490&page=function.preg-split&vote=down "Vote down!")

 -2


[**_markac_**](https://www.php.net/manual/en/function.preg-split.php#116490) [¶](https://www.php.net/manual/en/function.preg-split.php#116490)

**10 years ago**

`Split string into words.
<?php
$string = 'This - is a, very dirty "string" :-)';
// split into words
$wordlist = preg_split('/\W/', $string, 0, PREG_SPLIT_NO_EMPTY);
// returns only words that have minimum 2 chars
$wordlist = array_filter($wordlist, function($val) {
return strlen($val) >= 2;
});
// print
var_dump($wordlist);
?>
Result:
array (size=5)
0 => string 'This' (length=4)
1 => string 'is' (length=2)
3 => string 'very' (length=4)
4 => string 'dirty' (length=5)
5 => string 'string' (length=6)`

[up](https://www.php.net/manual/vote-note.php?id=120149&page=function.preg-split&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120149&page=function.preg-split&vote=down "Vote down!")

 -4


[**_php at haravikk dot me_**](https://www.php.net/manual/en/function.preg-split.php#120149) [¶](https://www.php.net/manual/en/function.preg-split.php#120149)

**8 years ago**

`When using the PREG_SPLIT_OFFSET_CAPTURE option you will end up with all results in a single array, which is often undesirable as it means you then have to filter out any delimiters you wanted to check for but not keep.
To get around this you can instead use preg_match_all() to perform the split. For comparison, here are two examples, both splitting around colon and semi-colon characters:
<?php $pieces_with_delimiters = preg_split('/[;:]/', $input, -1, PREG_SPLIT_OFFSET_CAPTURE); ?>
<?php preg_match_all('/([^;:]*)([;:]|$)/', $input, $matches);
list(, $pieces, $delimiters) = $matches ?>
The latter requires a more complex pattern, but produces a much more convenient set of results to work with, depending upon what you want to do with them.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.preg-split&repo=en&redirect=https://www.php.net/manual/en/function.preg-split.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google