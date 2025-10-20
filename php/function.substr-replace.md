---
url: https://www.php.net/manual/en/function.substr-replace.php
scraped_at: 2025-10-20T02:37:05.637Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# substr\_replace

(PHP 4, PHP 5, PHP 7, PHP 8)

substr\_replace — Replace text within a portion of a string

### Description [¶](https://www.php.net/manual/en/function.substr-replace.php\#refsect1-function.substr-replace-description)

**substr\_replace**(

[array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php) `$string`,

[array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php) `$replace`,

[array](https://www.php.net/manual/en/language.types.array.php)\|[int](https://www.php.net/manual/en/language.types.integer.php) `$offset`,

[array](https://www.php.net/manual/en/language.types.array.php)\|[int](https://www.php.net/manual/en/language.types.integer.php)\|[null](https://www.php.net/manual/en/language.types.null.php) `$length` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**

): [string](https://www.php.net/manual/en/language.types.string.php)\|[array](https://www.php.net/manual/en/language.types.array.php)

**substr\_replace()** replaces a copy of
`string` delimited by the
`offset` and (optionally)
`length` parameters with the string given in
`replace`.


### Parameters [¶](https://www.php.net/manual/en/function.substr-replace.php\#refsect1-function.substr-replace-parameters)

`string`

The input string.


An [array](https://www.php.net/manual/en/language.types.array.php) of [string](https://www.php.net/manual/en/language.types.string.php)s can be provided, in which
case the replacements will occur on each string in turn. In this case,
the `replace`, `offset`
and `length` parameters may be provided either as
scalar values to be applied to each input string in turn, or as
[array](https://www.php.net/manual/en/language.types.array.php)s, in which case the corresponding array element will
be used for each input string.


`replace`

The replacement string.


`offset`

If `offset` is non-negative, the replacing will
begin at the `offset`'th offset into
`string`.


If `offset` is negative, the replacing will
begin at the `offset`'th character from the
end of `string`.


`length`

If given and is positive, it represents the length of the portion of
`string` which is to be replaced. If it is
negative, it represents the number of characters from the end of
`string` at which to stop replacing. If it
is not given, then it will default to strlen(
`string` ); i.e. end the replacing at the
end of `string`. Of course, if
`length` is zero then this function will have the
effect of inserting `replace` into
`string` at the given
`offset` offset.


### Return Values [¶](https://www.php.net/manual/en/function.substr-replace.php\#refsect1-function.substr-replace-returnvalues)

The result string is returned. If `string` is an
array then array is returned.


### Changelog [¶](https://www.php.net/manual/en/function.substr-replace.php\#refsect1-function.substr-replace-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `length` is nullable now. |

### Examples [¶](https://www.php.net/manual/en/function.substr-replace.php\#refsect1-function.substr-replace-examples)

**Example #1 Simple **substr\_replace()** examples**

`<?php
$var = 'ABCDEFGH:/MNRPQR/';
echo "Original: $var<hr />\n";
/* These two examples replace all of $var with 'bob'. */
echo substr_replace($var, 'bob', 0) . "<br />\n";
echo substr_replace($var, 'bob', 0, strlen($var)) . "<br />\n";
/* Insert 'bob' right at the beginning of $var. */
echo substr_replace($var, 'bob', 0, 0) . "<br />\n";
/* These next two replace 'MNRPQR' in $var with 'bob'. */
echo substr_replace($var, 'bob', 10, -1) . "<br />\n";
echo substr_replace($var, 'bob', -7, -1) . "<br />\n";
/* Delete 'MNRPQR' from $var. */
echo substr_replace($var, '', 10, -1) . "<br />\n";
?>`

Run code

**Example #2**
**Using **substr\_replace()** to replace multiple strings at**
**once**

`<?php
$input = array('A: XXX', 'B: XXX', 'C: XXX');
// A simple case: replace XXX in each string with YYY.
echo implode('; ', substr_replace($input, 'YYY', 3, 3))."\n";
// A more complicated case where each replacement is different.
$replace = array('AAA', 'BBB', 'CCC');
echo implode('; ', substr_replace($input, $replace, 3, 3))."\n";
// Replace a different number of characters each time.
$length = array(1, 2, 3);
echo implode('; ', substr_replace($input, $replace, 3, $length))."\n";
?>`

Run code

The above example will output:

```
A: YYY; B: YYY; C: YYY
A: AAA; B: BBB; C: CCC
A: AAAXX; B: BBBX; C: CCC
```

### Notes [¶](https://www.php.net/manual/en/function.substr-replace.php\#refsect1-function.substr-replace-notes)

> **Note**: This function is
> binary-safe.

### See Also [¶](https://www.php.net/manual/en/function.substr-replace.php\#refsect1-function.substr-replace-seealso)

- [str\_replace()](https://www.php.net/manual/en/function.str-replace.php) \- Replace all occurrences of the search string with the replacement string
- [substr()](https://www.php.net/manual/en/function.substr.php) \- Return part of a string
- [String access and modification by character](https://www.php.net/manual/en/language.types.string.php#language.types.string.substr)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/substr-replace.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.substr-replace%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.substr-replace&repo=en&redirect=https://www.php.net/manual/en/function.substr-replace.php)

### User Contributed Notes 30 notes

[up](https://www.php.net/manual/vote-note.php?id=97401&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=97401&page=function.substr-replace&vote=down "Vote down!")

20


[**_elloromtz at gmail dot com_**](https://www.php.net/manual/en/function.substr-replace.php#97401) [¶](https://www.php.net/manual/en/function.substr-replace.php#97401)

**15 years ago**

`It's worth noting that when start and length are both negative -and- the length is less than or equal to start, the length will have the effect of being set as 0.
<?php
substr_replace('eggs','x',-1,-1); //eggxs
substr_replace('eggs','x',-1,-2); //eggxs
substr_replace('eggs','x',-1,-2); //eggxs
?>
Same as:
<?php
substr_replace('eggs','x',-1,0); //eggxs
?>
<?php
substr_replace('huevos','x',-2,-2); //huevxos
substr_replace('huevos','x',-2,-3); //huevxos
substr_replace('huevos','x',-2,-3); //huevxos
?>
Same as:
<?php
substr_replace('huevos','x',-2,0); //huevxos
?>
Another note, if length is negative and start offsets the same position as length, length (yet again) will have the effect as being set as 0. (Of course, as mentioned in the manual, when length is negative it actually represents the position before it)
<?php
substr_replace('abcd', 'x', 0, -4); //xabcd
?>
Same as:
<?php
substr_replace('abcd','x',0,0); //xabcd
?>
<?php
substr_replace('abcd', 'x', 1, -3); //axbcd
?>
Same as:
<?php
substr_replace('abcd', 'x', 1, 0); //axbcd
?>`

[up](https://www.php.net/manual/vote-note.php?id=124557&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124557&page=function.substr-replace&vote=down "Vote down!")

5


[**_shaman\_master at list dot ru_**](https://www.php.net/manual/en/function.substr-replace.php#124557) [¶](https://www.php.net/manual/en/function.substr-replace.php#124557)

**5 years ago**

`Add prefix to strings:
<?php
substr_replace($strings, '_prefix', 0, 0);
?>
Add suffix/postfix to strings:
<?php
substr_replace($strings, '_suffix', array_map('strlen', $strings), 0);
?>`

[up](https://www.php.net/manual/vote-note.php?id=90146&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90146&page=function.substr-replace&vote=down "Vote down!")

12


[**_billg AT microsoft.com_**](https://www.php.net/manual/en/function.substr-replace.php#90146) [¶](https://www.php.net/manual/en/function.substr-replace.php#90146)

**16 years ago**

`Forget all of the mb_substr_replace() implementations mentioned in this page, they're all buggy.
Here is a version that mimics the behavior of substr_replace() exactly:
<?php
if (function_exists('mb_substr_replace') === false)
{
    function mb_substr_replace($string, $replacement, $start, $length = null, $encoding = null)
    {
        if (extension_loaded('mbstring') === true)
        {
            $string_length = (is_null($encoding) === true) ? mb_strlen($string) : mb_strlen($string, $encoding);

            if ($start < 0)
            {
                $start = max(0, $string_length + $start);
            }

            else if ($start > $string_length)
            {
                $start = $string_length;
            }

            if ($length < 0)
            {
                $length = max(0, $string_length - $start + $length);
            }

            else if ((is_null($length) === true) || ($length > $string_length))
            {
                $length = $string_length;
            }

            if (($start + $length) > $string_length)
            {
                $length = $string_length - $start;
            }

            if (is_null($encoding) === true)
            {
                return mb_substr($string, 0, $start) . $replacement . mb_substr($string, $start + $length, $string_length - $start - $length);
            }

            return mb_substr($string, 0, $start, $encoding) . $replacement . mb_substr($string, $start + $length, $string_length - $start - $length, $encoding);
        }

        return (is_null($length) === true) ? substr_replace($string, $replacement, $start) : substr_replace($string, $replacement, $start, $length);
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=48066&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=48066&page=function.substr-replace&vote=down "Vote down!")

7


[**_danieldoorduin at hotmail dot com_**](https://www.php.net/manual/en/function.substr-replace.php#48066) [¶](https://www.php.net/manual/en/function.substr-replace.php#48066)

**20 years ago**

`Using substr_replace() can be avoided by using substr() instead:
<?
$string = substr($string, 0, $position_needle).$replace.substr($string, $position_needle+$length_needle);
?>
This can be useful when you need to replace parts of multibyte strings like strings encoded with utf-8. There isn't a multibute variant for substr_replace(), but for php substr() there is mb_substr(). For more information on multibyte strings see [http://nl3.php.net/manual/en/ref.mbstring.php](http://nl3.php.net/manual/en/ref.mbstring.php)`

[up](https://www.php.net/manual/vote-note.php?id=83614&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=83614&page=function.substr-replace&vote=down "Vote down!")

4


[**_eblejr AT phrebh DOT com_**](https://www.php.net/manual/en/function.substr-replace.php#83614) [¶](https://www.php.net/manual/en/function.substr-replace.php#83614)

**17 years ago**

`PHP version of Java's removeCharAt() function:
<?php
function removeCharAt($str, $int){
return substr_replace($str,"",$int,1);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=114553&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114553&page=function.substr-replace&vote=down "Vote down!")

5


[**_ivijan dot stefan at gmail dot com_**](https://www.php.net/manual/en/function.substr-replace.php#114553) [¶](https://www.php.net/manual/en/function.substr-replace.php#114553)

**11 years ago**

`I have a little function that works like substr_replace ()  what I use for some purpose. Maybe someone needs it.
<?php
function putinplace($string=NULL, $put=NULL, $position=false)
{
    $d1=$d2=$i=false;
    $d=array(strlen($string), strlen($put));
    if($position > $d[0]) $position=$d[0];
    for($i=$d[0]; $i >= $position; $i--) $string[$i+$d[1]]=$string[$i];
    for($i=0; $i<$d[1]; $i++) $string[$position+$i]=$put[$i];
    return $string;
}
// Explanation
$string='My dog dont love postman'; // string
$put="'"; // put ' on position
$position=10; // number of characters (position)
print_r( putinplace($string, $put, $position) );
?>
RESULT: My dog don't love postman
This is a small powerful function that performs its job flawlessly.`

[up](https://www.php.net/manual/vote-note.php?id=121687&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121687&page=function.substr-replace&vote=down "Vote down!")

3


[**_Hayley Watson_**](https://www.php.net/manual/en/function.substr-replace.php#121687) [¶](https://www.php.net/manual/en/function.substr-replace.php#121687)

**8 years ago**

`See array_splice if you want to do this sort of thing to an array.`

[up](https://www.php.net/manual/vote-note.php?id=93993&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93993&page=function.substr-replace&vote=down "Vote down!")

3


[**_kalim dot fleet at gmail dot com_**](https://www.php.net/manual/en/function.substr-replace.php#93993) [¶](https://www.php.net/manual/en/function.substr-replace.php#93993)

**16 years ago**

`This will truncate a longer string to a smaller string of specified length while replacing the middle portion with a separator exactly in the middle.
<?php
$longString = 'abcdefghijklmnopqrstuvwxyz0123456789z.jpg';
$separator = '/.../';
$separatorlength = strlen($separator) ;
$maxlength = 25 - $separatorlength;
$start = $maxlength / 2 ;
$trunc =  strlen($longString) - $maxlength;
echo substr_replace($longString, $separator, $start, $trunc);
//prints "abcdefghij/.../56789z.jpg"
?>`

[up](https://www.php.net/manual/vote-note.php?id=89848&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=89848&page=function.substr-replace&vote=down "Vote down!")

4


[**_juichenieder-phnet at yahoo dot co dot uk_**](https://www.php.net/manual/en/function.substr-replace.php#89848) [¶](https://www.php.net/manual/en/function.substr-replace.php#89848)

**16 years ago**

`I've just taken a look at the post by ntoniazzi and I have a very small correction to make.
In the second if statement, it should be a triple equals, so:
<?php if ($length === null) ?>
It requires the triple equals, for the case of pure insertion, where $length = 0, the double equals, will catch this, causing the string to be cut short.  I hope this helps someone.`

[up](https://www.php.net/manual/vote-note.php?id=82733&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82733&page=function.substr-replace&vote=down "Vote down!")

2


[**_William Barry_**](https://www.php.net/manual/en/function.substr-replace.php#82733) [¶](https://www.php.net/manual/en/function.substr-replace.php#82733)

**17 years ago**

`I recently ran across a situation where I need to strip a heavily nested html list such that only the top level was preserved.  I started with a regular expression solution, but found that I kept matching the wrong closing ul with an outer opening ul.
This was my alternative solution, and it seems to work well:
<?php
function stripNestedLists($str)
{
    $str2 = $str;
    $lastStr = $str2;

    do
    {
        // Find the first closing ul
        $cul = strpos($str2, '</ul>');
        $ul = 0;
        $lastUL = 0;
        do
        {
            // Find the next opening ul
            $lastUL = $ul;
            $ul = strpos($str2, '<ul', $ul+1);
        }
        while ($ul !== false && $ul < $cul);

        $lastStr = $str2;
        $str2 = substr_replace($str2, '', $lastUL, $cul-$lastUL+5);
        $str2 = trim($str2);
    }
    while (strlen($str2) > 0);

    return $lastStr;
}
?>
Hope this helps someone.`

[up](https://www.php.net/manual/vote-note.php?id=19015&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=19015&page=function.substr-replace&vote=down "Vote down!")

2


[**_klaas at group94 dot com_**](https://www.php.net/manual/en/function.substr-replace.php#19015) [¶](https://www.php.net/manual/en/function.substr-replace.php#19015)

**23 years ago**

`THE DOT DOT DOT ISSUE
PROBLEM:
You want to abbreviate a string.
E.g. You want "BritneySpears" to show as "BritneySpe...", being only the ten first characters followed by "..."
SOLUTION:
<?
$oRIGINAL = "BritneySpears";
$sHORTER = substr_replace($oRIGINAL, '...', 10);
echo ($sHORTER);
?>
This will result in BritneySpe...`

[up](https://www.php.net/manual/vote-note.php?id=76951&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76951&page=function.substr-replace&vote=down "Vote down!")

1


[**_alishahnovin at hotmail dot com_**](https://www.php.net/manual/en/function.substr-replace.php#76951) [¶](https://www.php.net/manual/en/function.substr-replace.php#76951)

**18 years ago**

`I like the truncate function below...however, I found a few issues. Particularly if you have content that may have any kind of punctuation in it (?, !, ?!?, --, ..., .., ;, etc.)
The older function would end up looking like "blah blah?..." or "blah blah,..." which doesn't look so nice to me...
Here's my fix. It removes all trailing punctuation (that you include in the $punctuation string below) and then adds an ellipse. So even if it has an ellipse with 3 dots, 2 dots, 4 dots, it'll be removed, then re-added.
<?php
function truncate($text,$numb,$etc = "...") {
$text = html_entity_decode($text, ENT_QUOTES);
if (strlen($text) > $numb) {
$text = substr($text, 0, $numb);
$text = substr($text,0,strrpos($text," "));
$punctuation = ".!?:;,-"; //punctuation you want removed
$text = (strspn(strrev($text),  $punctuation)!=0)
        ?
        substr($text, 0, -strspn(strrev($text),  $punctuation))
        :
$text;
$text = $text.$etc;
}
$text = htmlentities($text, ENT_QUOTES);
return $text;
}
?>
I also needed a sort of "middle" truncate. The above function truncates around the end, but if you want to truncate around the middle (ie "Hello this is a long string." --> "Hello this ... long string.") you can use this (requires the truncate function):
<?php
function mtruncate($text, $numb, $etc = " ... ") {
    $first_part = truncate(truncate($text, strlen($text)/2, ""), $numb/2, "");
    $second_part = truncate(strrev(truncate(strrev($text), strlen($text)/2, "")), $numb/2, "");
    return $first_part.$etc.$second_part;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=123686&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123686&page=function.substr-replace&vote=down "Vote down!")

0


[**_bkline at rksystems dot com_**](https://www.php.net/manual/en/function.substr-replace.php#123686) [¶](https://www.php.net/manual/en/function.substr-replace.php#123686)

**6 years ago**

`I imagine the description of the parameters really means "number of bytes" where it says "number of characters" (confirmed by testing).`

[up](https://www.php.net/manual/vote-note.php?id=123316&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123316&page=function.substr-replace&vote=down "Vote down!")

0


[**_yeyijelud at amadamus dot com_**](https://www.php.net/manual/en/function.substr-replace.php#123316) [¶](https://www.php.net/manual/en/function.substr-replace.php#123316)

**6 years ago**

`First Example can be simplified =>
$input = array('A: XXX', 'B: XXX', 'C: XXX');
substr_replace($input, 'YYY', -3);
output: Array ( [0] => A: YYY [1] => B: YYY [2] => C: YYY )`

[up](https://www.php.net/manual/vote-note.php?id=56223&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56223&page=function.substr-replace&vote=down "Vote down!")

0


[**_hermes at andycostell dot com_**](https://www.php.net/manual/en/function.substr-replace.php#56223) [¶](https://www.php.net/manual/en/function.substr-replace.php#56223)

**20 years ago**

`I suggest changing the function suggested by Guru Evi slightly. I found that it doesn't work as written here.
Original:
function add_3dots($string,$repl,$start,$limit) {
if(strlen($string) > $limit) {
       return substr_replace(strip_tags($string),$repl,$start,$limit);
} else {
       return $string;
};
};
I suggest:
function add_3dots($string,$repl,$limit) {
       if(strlen($string) > $limit) {
           return substr_replace(strip_tags($string),$repl,$limit-strlen($repl));
       } else {
           return $string;
       }
    }
Usage:
$max_length=10;//the max number of characters you want to display
$too_long_string="BLAH BLAH BLAH BLAH BLAH etc.";//the string you want to shorten (if it's longer than the $limit)
$shorter_string=add_3_dots($too_long_string,"...",$max_length);`

[up](https://www.php.net/manual/vote-note.php?id=54703&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=54703&page=function.substr-replace&vote=down "Vote down!")

0


[**_Guru Evi_**](https://www.php.net/manual/en/function.substr-replace.php#54703) [¶](https://www.php.net/manual/en/function.substr-replace.php#54703)

**20 years ago**

`If your string is not long enough to meet what you specify in start and length then the replacement string is added towards the end of the string.
I wanted to replace the end of the string with ... if the string was too long to display (for instance article preview on a website). The problem was that my string was sometimes not that long and it still added the replacement string. So I wrote a function to replace substr_replace in my website:
function add_3dots($string,$repl,$start,$limit) {
    if(strlen($string) > $limit) {
        return substr_replace(strip_tags($string),$repl,$start,$limit);
    } else {
        return $string;
    };
};
I use strip_tags to strip out the HTML otherwise you might get a screwed up HTML (when a tags open in the string, but because you cut-off it doesn't)`

[up](https://www.php.net/manual/vote-note.php?id=59544&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=59544&page=function.substr-replace&vote=down "Vote down!")

 -1


[**_chuayw2000 at hotmail dot com_**](https://www.php.net/manual/en/function.substr-replace.php#59544) [¶](https://www.php.net/manual/en/function.substr-replace.php#59544)

**19 years ago**

`I don't know if this function is multibyte safe but I've written a function that will do the same in multibyte mode.
<?php
//Check to see if it exists in case PHP has this function later
if (!function_exists("mb_substr_replace")){
//Same parameters as substr_replace with the extra encoding parameter.
    function mb_substr_replace($string,$replacement,$start,$length=null,$encoding = null){
        if ($encoding == null){
            if ($length == null){
                return mb_substr($string,0,$start).$replacement;
            }
            else{
                return mb_substr($string,0,$start).$replacement.mb_substr($string,$start + $length);
            }
        }
        else{
            if ($length == null){
                return mb_substr($string,0,$start,$encoding).$replacement;
            }
            else{
                return mb_substr($string,0,$start,$encoding). $replacement. mb_substr($string,$start + $length,mb_strlen($string,$encoding),$encoding);
            }
        }
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=86254&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86254&page=function.substr-replace&vote=down "Vote down!")

 -1


[**_NiX0n at fragfest dot cx_**](https://www.php.net/manual/en/function.substr-replace.php#86254) [¶](https://www.php.net/manual/en/function.substr-replace.php#86254)

**17 years ago**

`The preemptive test to see if $string is "too long" shouldn't add strlen($replacement) to $max.  $max should represent the absolute maximum length of string returned.  The size of the $replacement is irrelevant in that determination.
The rest of the function (unchanged below) operates as defined above.  Meaning, the size of the $replacement is subtracted from the $max, so that the returned string is exactly the length of $max.
<?php
function truncate($string, $max = 20, $replacement = '')
{
    if (strlen($string) <= $max)
    {
        return $string;
    }
    $leave = $max - strlen ($replacement);
    return substr_replace($string, $replacement, $leave);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=118705&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118705&page=function.substr-replace&vote=down "Vote down!")

 -1


[**_nospam at nospam dot com_**](https://www.php.net/manual/en/function.substr-replace.php#118705) [¶](https://www.php.net/manual/en/function.substr-replace.php#118705)

**9 years ago**

`<?php
// shortens a long string to a max length while inserting a string into the exact middle
function strShorten($str, $maxlen = 10, $insert = '/.../') {
if ($str && !is_array($str)) { // valid string
    if ($maxlen && is_numeric($maxlen) && $maxlen < strlen($str)) { // string needs shortening
      if ($insert && ($ilen = strlen($insert))) { // insert string and length
        if ($ilen >= $maxlen) { // insert string too long so use default insert
          $insert = '**'; // short default so works even when a very small $maxlen
          $ilen = 2;
        }
      }
      $chars = $maxlen - $ilen; // number of $str chars to keep
      $start = ceil($chars/2); // position to start cutting
      $end = floor($chars/2); // position from end to stop cutting
      return substr_replace($str, $insert, $start, -$end); // first.insert.last
    } else { // string already short enough
      return $str; // return original string
    }
}
}
echo strShorten('123456789', 6, ''); // outputs 123789
echo strShorten('123456789', 6, '-'); // outputs 123-89
echo strShorten('123456789', 6, 'longstring'); // outputs 12**89
echo strShorten('abcdefghijklmnopqrstuvwxyz', 10, '..'); // outputs abcd..wxyz
echo strShorten('abcdefghijklmnopqrstuvwxyz'); // outputs abc/.../yz
?>`

[up](https://www.php.net/manual/vote-note.php?id=82056&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82056&page=function.substr-replace&vote=down "Vote down!")

 -1


[**_jaimthorn at yahoo dot com_**](https://www.php.net/manual/en/function.substr-replace.php#82056) [¶](https://www.php.net/manual/en/function.substr-replace.php#82056)

**17 years ago**

`I recently needed a routine that would remove the characters in one string from another, like the regex
<?php
$result = preg_replace("/[$chars]/", "", $string);
?>
and I needed it to be fast, and accept pretty much all input.  The regex above won't work when strlen($chars) == 0.  I came up with this, admittedly pretty horrible-looking code, that is quite fast:
<?php
function RemoveChars($string, $chars)
{
    return isset($chars{0}) ? str_replace($chars{0}, "", strtr($string, $chars, str_pad($chars{0}, strlen($chars), $chars{0}))) : $string;
}
?>
According to my own measurements, the regex in ONLY faster for when strlen($chars) == 1; for longer strings, my routine is faster.  What does it do?  Let's say you want to remove the period, the comma and the exclamation mark from a string, like so:
$result = RemoveChars("Isn't this, like, totally neat..!?", ".?!");
The str_pad function creates a string equal in length to the string that contains the character to be removed, but consisting only of the first character of that string:
The input is ".,!"
The output is "..."
The strtr function translates all characters in the string-to-be-processed ("Isn't this...") that also occur in the input (".,!") to the characters in the same position in the output ("...").  In other words:
Isn't this, like, totally neat..!?
becomes
Isn't this. like. totally neat....
Finally, the first character from the input (".,!") which happens to be, again, the period, is removed from that string by the str_replace call:
Isn't this like totally neat?
The function needs to check is $chars has at least one character, or else the str_pad function will fail.  If it's empty, then the unprocessed string is returned.`

[up](https://www.php.net/manual/vote-note.php?id=33736&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=33736&page=function.substr-replace&vote=down "Vote down!")

 -1


[**_david at ethinkn dot com_**](https://www.php.net/manual/en/function.substr-replace.php#33736) [¶](https://www.php.net/manual/en/function.substr-replace.php#33736)

**22 years ago**

`Here is a simple function to shorten a string and add an ellipsis
<?php
/**
* truncate() Simple function to shorten a string and add an ellipsis
*
* @param string $string Origonal string
* @param integer $max Maximum length
* @param string $rep Replace with... (Default = '' - No elipsis -)
* @return string
* @author David Duong
**/
function truncate ($string, $max = 50, $rep = '') {
    $leave = $max - strlen ($rep);
    return substr_replace($string, $rep, $leave);
}
echo truncate ('akfhslakdhglksjdgh', 10, '...');
// Returns akfhsla... (10 chrs)
?>`

[up](https://www.php.net/manual/vote-note.php?id=12483&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=12483&page=function.substr-replace&vote=down "Vote down!")

 -1


[**_mrbrown8 at juno dot com_**](https://www.php.net/manual/en/function.substr-replace.php#12483) [¶](https://www.php.net/manual/en/function.substr-replace.php#12483)

**24 years ago**

`Just to add to the examples, if replacement is longer than length, only the length number of chars are removed from string and all of replacement is put in its place, and therefor strlen($string) is inreased.
$var = 'ABCDEFGH:/MNRPQR/';
/*  Should return ABCDEFGH:/testingRPQR/   */
echo substr_replace ($var, 'testing', 10, 2);`

[up](https://www.php.net/manual/vote-note.php?id=40141&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=40141&page=function.substr-replace&vote=down "Vote down!")

 -1


[**_geniusdex ( at ) brz ( dot ) nu_**](https://www.php.net/manual/en/function.substr-replace.php#40141) [¶](https://www.php.net/manual/en/function.substr-replace.php#40141)

**21 years ago**

`This is my version of making dotted strings:
<?php
function dot($str, $len, $dots = "...") {
    if (strlen($str) > $len) {
        $dotlen = strlen($dots);
        substr_replace($str, $dots, $len - $dotlen);
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=43338&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=43338&page=function.substr-replace&vote=down "Vote down!")

 -1


[**_dmron_**](https://www.php.net/manual/en/function.substr-replace.php#43338) [¶](https://www.php.net/manual/en/function.substr-replace.php#43338)

**21 years ago**

`Regarding "...", even the short functions are too long and complicated, and there's no need to use substr_replace. substr() works better and is  way faster prior to 4.3.5 as the below poster stated.
function shorten( $str, $num = 100 ) {
if( strlen( $str ) > $num ) $str = substr( $str, 0, $num ) . "...";
return $str;
}`

[up](https://www.php.net/manual/vote-note.php?id=96308&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96308&page=function.substr-replace&vote=down "Vote down!")

 -2


[**_den dot gierling at web dot de_**](https://www.php.net/manual/en/function.substr-replace.php#96308) [¶](https://www.php.net/manual/en/function.substr-replace.php#96308)

**15 years ago**

`My problem was that substr_replace() always added $replacement, so i wrote my own function.
This function only adds $replacement, if substr() took action.
The parameter $length is optional - like substr()'s.
Or I was too stupid using $start and $length...
<?php
function substr_replace_provided($string,$replacement,$start,$length=NULL)
{
    $tmp=substr($string,$start,$length);
    if($string!==$tmp) {
        $string = $tmp.$replacement;
    }
    return $string;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=39200&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=39200&page=function.substr-replace&vote=down "Vote down!")

 -2


[**_Thijs Wijnmaalen (thijs\[at\]nllinux.nl)_**](https://www.php.net/manual/en/function.substr-replace.php#39200) [¶](https://www.php.net/manual/en/function.substr-replace.php#39200)

**21 years ago**

`I wrote a function that you can use for example in combination with a search script to cut off the articles that are too long.
<?php
function substr_index($text, $maxChars = 20, $splitter
= '...') {
$theReturn = $text;
$lastSpace = false;
if (strlen($text) > $maxChars) {
$theReturn = substr($text, 0, $maxChars - 1);
if (in_array(substr($text, $maxChars - 1, 1),
array(' ', '.', '!', '?'))) {
$theReturn .= substr($text, $maxChars, 1);
} else {
$theReturn = substr($theReturn, 0, $maxChars -
strlen($splitter));
$lastSpace = strrpos($theReturn, ' ');
if ($lastSpace !== false) {
$theReturn = substr($theReturn, 0, $lastSpace);
}
if (in_array(substr($theReturn, -1, 1), array(','))) {
$theReturn = substr($theReturn, 0, -1);
}
$theReturn .= $splitter;
}
}
return $theReturn;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=125126&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125126&page=function.substr-replace&vote=down "Vote down!")

 -1


[**_meg dot phillips91 at gmail dot com_**](https://www.php.net/manual/en/function.substr-replace.php#125126) [¶](https://www.php.net/manual/en/function.substr-replace.php#125126)

**5 years ago**

`This may be obvious to others, but I just spent hours and my feeble brain only caught up to it after a long break.
If you are looping through a string which has multiple substrings that need to be replaced, you have to add an offset factor to each original offset before you replaced any strings. Here is a real world example:
From draft.js we get paragraphs with multiple links designated only with offset, anchor text length, url, target. So each anchor text must be wrapped in the <a href="url" target="target">anchortext</a> to save proper content in the database.
Here is the implementation of offset factor:
$offset_factor = 0;
foreach($content->links->links as $index=>$link){
            $replacement = '<a href="'.$link->href.'"  target="$link->target">'.$link->anchorText.'</a>';
            $new_offset = $link->offset + $offset_factor;
            $newtext = \substr_replace($content->text, $replacement, $new_offset, $link->length);
            //now we reset the original paragraph text with newtext
            $content->text = $newtext;

            //calculate the new offset by calculating the difference in replacement length and original length and add that to the offset_factor
            $additional_characters = strlen($replacement) - $link->length;
            $offset_factor =  $offset_factor + $additional_characters;
        }
I hope this helps a noobie :) If there is another easier way, I would love to hear about it.`

[up](https://www.php.net/manual/vote-note.php?id=84728&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84728&page=function.substr-replace&vote=down "Vote down!")

 -3


[**_spcl dot delivery at gmail dot com_**](https://www.php.net/manual/en/function.substr-replace.php#84728) [¶](https://www.php.net/manual/en/function.substr-replace.php#84728)

**17 years ago**

`the version of my predecessor will add $rep even if the string is shorter than max. fixed version:
<?php
function truncate($string, $max = 20, $rep = '')
{
    if (strlen($string) <= ($max + strlen($rep)))
    {
        return $string;
    }
    $leave = $max - strlen ($rep);
    return substr_replace($string, $rep, $leave);
}
?>
To preserve the filename extension you can call it like this:
truncate([filename], 30, '...' . end(explode('.', [filename])))`

[up](https://www.php.net/manual/vote-note.php?id=15744&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=15744&page=function.substr-replace&vote=down "Vote down!")

 -5


[**_Anonymous_**](https://www.php.net/manual/en/function.substr-replace.php#15744) [¶](https://www.php.net/manual/en/function.substr-replace.php#15744)

**24 years ago**

`If you would like to remove characters from the start or end of a string, try the substr() function.
For example, to remove the last three characters from a string:
$string = "To be or not to be.";
$string = substr ($string, 0, -3);`

[up](https://www.php.net/manual/vote-note.php?id=118243&page=function.substr-replace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118243&page=function.substr-replace&vote=down "Vote down!")

 -5


[**_olav at schettler dot net_**](https://www.php.net/manual/en/function.substr-replace.php#118243) [¶](https://www.php.net/manual/en/function.substr-replace.php#118243)

**9 years ago**

`Please note that the function array_slice(), which has a similar functionality but for arrays rather than for strings, has its parameters in a different order.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.substr-replace&repo=en&redirect=https://www.php.net/manual/en/function.substr-replace.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google