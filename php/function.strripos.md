---
url: https://www.php.net/manual/en/function.strripos.php
scraped_at: 2025-10-20T03:01:40.640Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# strripos

(PHP 5, PHP 7, PHP 8)

strripos — Find the position of the last occurrence of a case-insensitive substring in a string

### Description [¶](https://www.php.net/manual/en/function.strripos.php\#refsect1-function.strripos-description)

**strripos**([string](https://www.php.net/manual/en/language.types.string.php) `$haystack`, [string](https://www.php.net/manual/en/language.types.string.php) `$needle`, [int](https://www.php.net/manual/en/language.types.integer.php) `$offset` = 0): [int](https://www.php.net/manual/en/language.types.integer.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Find the numeric position of the last occurrence of
`needle` in the `haystack` string.



Unlike the [strrpos()](https://www.php.net/manual/en/function.strrpos.php), **strripos()** is
case-insensitive.


### Parameters [¶](https://www.php.net/manual/en/function.strripos.php\#refsect1-function.strripos-parameters)

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


If negative, the search is performed right to left skipping the
last `offset` bytes of the
`haystack` and searching for the first occurrence
of `needle`.


> **Note**:
>
>
> This is effectively looking for the last occurrence of
> `needle` before the last
> `offset` bytes.

### Return Values [¶](https://www.php.net/manual/en/function.strripos.php\#refsect1-function.strripos-returnvalues)

Returns the position where the needle exists relative to the beginnning of
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

### Changelog [¶](https://www.php.net/manual/en/function.strripos.php\#refsect1-function.strripos-changelog)

| Version | Description |
| --- | --- |
| 8.2.0 | Case folding no longer depends on the locale set with<br> [setlocale()](https://www.php.net/manual/en/function.setlocale.php). Only ASCII case folding will be done.<br> Non-ASCII bytes will be compared by their byte value. |
| 8.0.0 | `needle` now accepts an empty string. |
| 8.0.0 | Passing an [int](https://www.php.net/manual/en/language.types.integer.php) as `needle` is no longer supported. |
| 7.3.0 | Passing an [int](https://www.php.net/manual/en/language.types.integer.php) as `needle` has been deprecated. |

### Examples [¶](https://www.php.net/manual/en/function.strripos.php\#refsect1-function.strripos-examples)

**Example #1 A simple **strripos()** example**

`<?php
$haystack = 'ababcd';
$needle   = 'aB';
$pos      = strripos($haystack, $needle);
if ($pos === false) {
    echo "Sorry, we did not find ($needle) in ($haystack)";
} else {
    echo "Congratulations!\n";
    echo "We found the last ($needle) in ($haystack) at position ($pos)";
}
?>`

Run code

The above example will output:

```
Congratulations!
   We found the last (aB) in (ababcd) at position (2)
```

### See Also [¶](https://www.php.net/manual/en/function.strripos.php\#refsect1-function.strripos-seealso)

- [strpos()](https://www.php.net/manual/en/function.strpos.php) \- Find the position of the first occurrence of a substring in a string
- [stripos()](https://www.php.net/manual/en/function.stripos.php) \- Find the position of the first occurrence of a case-insensitive substring in a string
- [strrpos()](https://www.php.net/manual/en/function.strrpos.php) \- Find the position of the last occurrence of a substring in a string
- [strrchr()](https://www.php.net/manual/en/function.strrchr.php) \- Find the last occurrence of a character in a string
- [stristr()](https://www.php.net/manual/en/function.stristr.php) \- Case-insensitive strstr
- [substr()](https://www.php.net/manual/en/function.substr.php) \- Return part of a string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/strripos.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.strripos%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.strripos&repo=en&redirect=https://www.php.net/manual/en/function.strripos.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=76167&page=function.strripos&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76167&page=function.strripos&vote=down "Vote down!")

4


[**_Yanik Lupien_**](https://www.php.net/manual/en/function.strripos.php#76167) [¶](https://www.php.net/manual/en/function.strripos.php#76167)

**18 years ago**

`Simple way to implement this function in PHP 4
<?php
if (function_exists('strripos') == false) {
    function strripos($haystack, $needle) {
        return strlen($haystack) - strpos(strrev($haystack), $needle);
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=85941&page=function.strripos&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85941&page=function.strripos&vote=down "Vote down!")

2


[**_dimmav at in dot gr_**](https://www.php.net/manual/en/function.strripos.php#85941) [¶](https://www.php.net/manual/en/function.strripos.php#85941)

**17 years ago**

`Suppose you just need a stripos function working backwards expecting that strripos does this job, you better use the following code of a custom function named strbipos:
<?php
function strbipos($haystack="", $needle="", $offset=0) {
// Search backwards in $haystack for $needle starting from $offset and return the position found or false
    $len = strlen($haystack);
    $pos = stripos(strrev($haystack), strrev($needle), $len - $offset - 1);
    return ( ($pos === false) ? false : $len - strlen($needle) - $pos );
}
// Test
$body = "01234Xy7890XYz456xy90";
$str = "xY";
$len = strlen($body);
echo "TEST POSITIVE offset VALUES IN strbipos<br>";
for ($i = 0; $i < $len; $i++) {
    echo "Search in [$body] for [$str] starting from offset [$i]: [" . strbipos($body, $str, $i) . "]<br>";
}
?>
Note that this function does exactly what it says and its results are different comparing to PHP 5 strripos function.`

[up](https://www.php.net/manual/vote-note.php?id=78577&page=function.strripos&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78577&page=function.strripos&vote=down "Vote down!")

1


[**_peev\[dot\]alexander at gmail dot com_**](https://www.php.net/manual/en/function.strripos.php#78577) [¶](https://www.php.net/manual/en/function.strripos.php#78577)

**18 years ago**

`I think you shouldn't underestimate the length of $needle in the search of THE FIRST POSITION of it's last occurrence in the string. I improved the posted function, with added support for offset. I think this is an exact copy of the real function:
<?php
if(!function_exists("strripos")){
    function strripos($haystack, $needle, $offset=0) {
        if($offset<0){
            $temp_cut = strrev(  substr( $haystack, 0, abs($offset) )  );
        }
        else{
            $temp_cut = strrev(  substr( $haystack, $offset )  );
        }
        $pos = strlen($haystack) - (strpos($temp_cut, strrev($needle)) + $offset + strlen($needle));
        if ($pos == strlen($haystack)) { $pos = 0; }
        return $pos;
    }/* endfunction strripos*/
}/* endfunction exists strripos*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=82650&page=function.strripos&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82650&page=function.strripos&vote=down "Vote down!")

 -1


[**_peev\[dot\]alexander at gmail dot com_**](https://www.php.net/manual/en/function.strripos.php#82650) [¶](https://www.php.net/manual/en/function.strripos.php#82650)

**17 years ago**

`OK, I guess this will be the final function implementation for PHP 4.x versions ( my previous posts are invalid )
<?php
if(!function_exists("stripos")){
    function stripos(  $str, $needle, $offset = 0  ){
        return strpos(  strtolower( $str ), strtolower( $needle ), $offset  );
    }/* endfunction stripos */
}/* endfunction exists stripos */
if(!function_exists("strripos")){
    function strripos(  $haystack, $needle, $offset = 0  ) {
        if(  !is_string( $needle )  )$needle = chr(  intval( $needle )  );
        if(  $offset < 0  ){
            $temp_cut = strrev(  substr( $haystack, 0, abs($offset) )  );
        }
        else{
            $temp_cut = strrev(    substr(   $haystack, 0, max(  ( strlen($haystack) - $offset ), 0  )   )    );
        }
        if(   (  $found = stripos( $temp_cut, strrev($needle) )  ) === FALSE   )return FALSE;
        $pos = (   strlen(  $haystack  ) - (  $found + $offset + strlen( $needle )  )   );
        return $pos;
    }/* endfunction strripos */
}/* endfunction exists strripos */
?>`

[up](https://www.php.net/manual/vote-note.php?id=99704&page=function.strripos&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99704&page=function.strripos&vote=down "Vote down!")

 -2


[**_Anonymous_**](https://www.php.net/manual/en/function.strripos.php#99704) [¶](https://www.php.net/manual/en/function.strripos.php#99704)

**15 years ago**

`Generally speaking, linear searches are from start to end, not end to start - which makes sense from a human perspective. If you need to find strings in a string backwards, reverse your haystack and needle rather than manually chopping it up.`

[up](https://www.php.net/manual/vote-note.php?id=76862&page=function.strripos&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76862&page=function.strripos&vote=down "Vote down!")

 -3


[**_ElectroFox_**](https://www.php.net/manual/en/function.strripos.php#76862) [¶](https://www.php.net/manual/en/function.strripos.php#76862)

**18 years ago**

`Sorry, I made that last post a bit prematurely.  One more thing wrong with the simple php4 version is that it breaks if the string is not found.  It should actually look like this:
<?php
if (function_exists('strripos') == false) {
    function strripos($haystack, $needle) {
        $pos = strlen($haystack) - strpos(strrev($haystack), strrev($needle));
        if ($pos == strlen($haystack)) { $pos = 0; }
        return $pos;
    }
}
?>
Note, we now check to see if the $needle was found, and if it isn't, we return 0.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.strripos&repo=en&redirect=https://www.php.net/manual/en/function.strripos.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google