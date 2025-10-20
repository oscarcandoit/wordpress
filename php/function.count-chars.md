---
url: https://www.php.net/manual/en/function.count-chars.php
scraped_at: 2025-10-20T02:59:51.119Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# count\_chars

(PHP 4, PHP 5, PHP 7, PHP 8)

count\_chars — Return information about characters used in a string

### Description [¶](https://www.php.net/manual/en/function.count-chars.php\#refsect1-function.count-chars-description)

**count\_chars**([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [int](https://www.php.net/manual/en/language.types.integer.php) `$mode` = 0): [array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php)

Counts the number of occurrences of every byte-value (0..255) in
`string` and returns it in various ways.


### Parameters [¶](https://www.php.net/manual/en/function.count-chars.php\#refsect1-function.count-chars-parameters)

`string`

The examined string.


`mode`

See return values.


### Return Values [¶](https://www.php.net/manual/en/function.count-chars.php\#refsect1-function.count-chars-returnvalues)

Depending on `mode` **count\_chars()** returns one of the following:


- 0 - an array with the byte-value as key and the frequency of
every byte as value.

- 1 - same as 0 but only byte-values with a frequency greater
than zero are listed.

- 2 - same as 0 but only byte-values with a frequency equal to
zero are listed.

- 3 - a string containing all unique characters is returned.

- 4 - a string containing all unused characters is returned.


### Changelog [¶](https://www.php.net/manual/en/function.count-chars.php\#refsect1-function.count-chars-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | Prior to this version, the function returned **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure. |

### Examples [¶](https://www.php.net/manual/en/function.count-chars.php\#refsect1-function.count-chars-examples)

**Example #1 **count\_chars()** example**

`<?php
$data = "Two Ts and one F.";
foreach (count_chars($data, 1) as $i => $val) {
echo "There were $val instance(s) of \"" , chr($i) , "\" in the string.\n";
}
?>`

Run code

The above example will output:

```
There were 4 instance(s) of " " in the string.
There were 1 instance(s) of "." in the string.
There were 1 instance(s) of "F" in the string.
There were 2 instance(s) of "T" in the string.
There were 1 instance(s) of "a" in the string.
There were 1 instance(s) of "d" in the string.
There were 1 instance(s) of "e" in the string.
There were 2 instance(s) of "n" in the string.
There were 2 instance(s) of "o" in the string.
There were 1 instance(s) of "s" in the string.
There were 1 instance(s) of "w" in the string.
```

### See Also [¶](https://www.php.net/manual/en/function.count-chars.php\#refsect1-function.count-chars-seealso)

- [strpos()](https://www.php.net/manual/en/function.strpos.php) \- Find the position of the first occurrence of a substring in a string
- [substr\_count()](https://www.php.net/manual/en/function.substr-count.php) \- Count the number of substring occurrences

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/count-chars.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.count-chars%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.count-chars&repo=en&redirect=https://www.php.net/manual/en/function.count-chars.php)

### User Contributed Notes 8 notes

[up](https://www.php.net/manual/vote-note.php?id=107336&page=function.count-chars&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107336&page=function.count-chars&vote=down "Vote down!")

25


[**_marcus33cz_**](https://www.php.net/manual/en/function.count-chars.php#107336) [¶](https://www.php.net/manual/en/function.count-chars.php#107336)

**13 years ago**

`If you have problems using count_chars with a multibyte string, you can change the page encoding. Alternatively, you can also use this mb_count_chars version of the function. Basically it is mode "1" of the original function.
<?php
/**
* Counts character occurences in a multibyte string
* @param string $input UTF-8 data
* @return array associative array of characters.
*/
function mb_count_chars($input) {
    $l = mb_strlen($input, 'UTF-8');
    $unique = array();
    for($i = 0; $i < $l; $i++) {
        $char = mb_substr($input, $i, 1, 'UTF-8');
        if(!array_key_exists($char, $unique))
            $unique[$char] = 0;
        $unique[$char]++;
    }
    return $unique;
}
$input = "Let's try some Greek letters: αααααΕεΙιΜμΨψ, Russian: ЙЙЫЫЩН, Czech: ěščřžýáíé";
print_r( mb_count_chars($input) );
//returns: Array ( [L] => 1 [e] => 7 [t] => 4 ['] => 1 [s] => 5 [ ] => 9 [r] => 3 [y] => 1 [o] => 1 [m] => 1 [G] => 1 [k] => 1 [l] => 1 [:] => 3 [α] => 5 [Ε] => 1 [ε] => 1 [Ι] => 1 [ι] => 1 [Μ] => 1 [μ] => 1 [Ψ] => 1 [ψ] => 1 [,] => 2 [R] => 1 [u] => 1 [i] => 1 [a] => 1 [n] => 1 [Й] => 2 [Ы] => 2 [Щ] => 1 [Н] => 1 [C] => 1 [z] => 1 [c] => 1 [h] => 1 [ě] => 1 [š] => 1 [č] => 1 [ř] => 1 [ž] => 1 [ý] => 1 [á] => 1 [í] => 1 [é] => 1 )
?>`

[up](https://www.php.net/manual/vote-note.php?id=53280&page=function.count-chars&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=53280&page=function.count-chars&vote=down "Vote down!")

2


[**_Eric Pecoraro_**](https://www.php.net/manual/en/function.count-chars.php#53280) [¶](https://www.php.net/manual/en/function.count-chars.php#53280)

**20 years ago**

`<?php
// Require (n) unique characters in a string
// Modification of a function below which ads some flexibility in how many unique characters are required in a given string.
$pass = '123456' ; // true
$pass = '111222' ; // false
req_unique($pass,3);
function req_unique($string,$unique=3) {
    if ( count(count_chars($string,1)) < $unique) {
        echo 'false';
    }else{
        echo 'true';
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=42431&page=function.count-chars&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=42431&page=function.count-chars&vote=down "Vote down!")

2


[**_seb at synchrocide dot net_**](https://www.php.net/manual/en/function.count-chars.php#42431) [¶](https://www.php.net/manual/en/function.count-chars.php#42431)

**21 years ago**

`After much trial and error trying to create a function that finds the number of unique characters in a string I same across count_chars() - my 20+ lines of useless code were wiped for this:
<?
function unichar($string) {
$two= strtolower(str_replace(' ', '', $string));
$res = count(count_chars($two, 1));
return $res;
}
/* examples :: */
echo unichar("bob"); // 2
echo unichar("Invisibility"); //8
echo unichar("The quick brown fox slyly jumped over the lazy dog"); //26
?>
I have no idea where this could be used, but it's quite fun`

[up](https://www.php.net/manual/vote-note.php?id=118726&page=function.count-chars&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118726&page=function.count-chars&vote=down "Vote down!")

1


[**_Anonymous_**](https://www.php.net/manual/en/function.count-chars.php#118726) [¶](https://www.php.net/manual/en/function.count-chars.php#118726)

**9 years ago**

`count_chars for multibyte supported.
<?php
function mb_count_chars ($string, $mode = 0) {

    $result =  array_fill(0, 256, 0);

    for ($i = 0, $size = mb_strlen($string); $i < $size; $i++) {
        $char = mb_substr($string, $i, 1);
        if (strlen($char) > 1) {
            continue;
        }

        $code = ord($char);
        if ($code >= 0 && $code <= 255) {
            $result[$code]++;
        }
    }

    switch ($mode) {
        case 1: // same as 0 but only byte-values with a frequency greater than zero are listed.
            foreach ($result as $key => $value) {
                if ($value == 0) {
                    unset($result[$key]);
                }
            }
            break;
        case 2: // same as 0 but only byte-values with a frequency equal to zero are listed.
            foreach ($result as $key => $value) {
                if ($value > 0) {
                    unset($result[$key]);
                }
            }
            break;
        case 3: // a string containing all unique characters is returned.
            $buildString = '';
            foreach ($result as $key => $value) {
                if ($value > 0) {
                    $buildString .= chr($key);
                }
            }
            return $buildString;
        case 4: // a string containing all not used characters is returned.
            $buildString = '';
            foreach ($result as $key => $value) {
                if ($value == 0) {
                    $buildString .= chr($key);
                }
            }
            return $buildString;
    }

    // change key names...
    foreach ($result as $key => $value) {
        $result[chr($key)] = $value;
        unset($result[$key]);
    }

    return $result;

}
?>`

[up](https://www.php.net/manual/vote-note.php?id=124744&page=function.count-chars&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124744&page=function.count-chars&vote=down "Vote down!")

0


[**_Andrey G_**](https://www.php.net/manual/en/function.count-chars.php#124744) [¶](https://www.php.net/manual/en/function.count-chars.php#124744)

**5 years ago**

`Checking that two strings are anagram:
<?php
function isAnagram($string1, $string2)
{
return count_chars($string1, 1) === count_chars($string2, 1);
}
isAnagram('act', 'cat'); // true
?>`

[up](https://www.php.net/manual/vote-note.php?id=76746&page=function.count-chars&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76746&page=function.count-chars&vote=down "Vote down!")

0


[**_pzb at novell dot com_**](https://www.php.net/manual/en/function.count-chars.php#76746) [¶](https://www.php.net/manual/en/function.count-chars.php#76746)

**18 years ago**

`This function is great for input validation.  I frequently need to check that all characters in a string are 7-bit ASCII (and not null).  This is the fastest function I have found yet:
<?php
function is7bit($string) {
    // empty strings are 7-bit clean
    if (!strlen($string)) {
        return true;
    }
    // count_chars returns the characters in ascending octet order
    $str = count_chars($str, 3);
    // Check for null character
    if (!ord($str[0])) {
        return false;
    }
    // Check for 8-bit character
    if (ord($str[strlen($str)-1]) & 128) {
        return false;
    }
    return true;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=79583&page=function.count-chars&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=79583&page=function.count-chars&vote=down "Vote down!")

 -2


[**_phpC2007_**](https://www.php.net/manual/en/function.count-chars.php#79583) [¶](https://www.php.net/manual/en/function.count-chars.php#79583)

**17 years ago**

`Here's a function to count number of strings in a string. It can be used as a simple utf8-enabled count_chars (but limited to a single mode)...
<?php
function utf8_count_strings($stringChar)
{
    $num = -1;
    $lenStringChar = strlen($stringChar);

    for ($lastPosition = 0;
        $lastPosition !== false;
        $lastPosition = strpos($textSnippet, $stringChar, $lastPosition + $lenStringChar))
    {
        $num++;
    }

    return $num;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=18625&page=function.count-chars&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=18625&page=function.count-chars&vote=down "Vote down!")

 -3


[**_mlong at mlong dot org_**](https://www.php.net/manual/en/function.count-chars.php#18625) [¶](https://www.php.net/manual/en/function.count-chars.php#18625)

**23 years ago**

`// Usefulness of the two functions
<?php
$string="aaabbc";
// You just want to count the letter a
$acount=substr_count($string,"a");
// You want to count both letter a and letter b
$counts=count_chars($string,0);
$acount=$counts[ord("a")];
$bcount=$counts[ord("b")];
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.count-chars&repo=en&redirect=https://www.php.net/manual/en/function.count-chars.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google