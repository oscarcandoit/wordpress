---
url: https://www.php.net/manual/en/function.rtrim.php
scraped_at: 2025-10-20T02:49:08.155Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# rtrim

(PHP 4, PHP 5, PHP 7, PHP 8)

rtrim — Strip whitespace (or other characters) from the end of a string

### Description [¶](https://www.php.net/manual/en/function.rtrim.php\#refsect1-function.rtrim-description)

**rtrim**([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [string](https://www.php.net/manual/en/language.types.string.php) `$characters` = " \\n\\r\\t\\v\\x00"): [string](https://www.php.net/manual/en/language.types.string.php)

This function returns a string with whitespace (or other characters) stripped from the
end of `string`.


Without the second parameter,
**rtrim()** will strip these characters:


- `" "`: ASCIISP character
`0x20`, an ordinary space.

- `"\t"`: ASCIIHT character
`0x09`, a tab.

- `"\n"`: ASCIILF character
`0x0A`, a new line (line feed).

- `"\r"`: ASCIICR character
`0x0D`, a carriage return.

- `"\0"`: ASCIINUL character
`0x00`, the NUL-byte.

- `"\v"`: ASCIIVT
character `0x0B`, a vertical tab.


### Parameters [¶](https://www.php.net/manual/en/function.rtrim.php\#refsect1-function.rtrim-parameters)

`string`
The input string.
`characters`
Optionally, the stripped characters can also be specified using
the `characters` parameter.
Simply list all characters that need to be stripped.
With `..` it is possible to specify an incrementing range of characters.


### Return Values [¶](https://www.php.net/manual/en/function.rtrim.php\#refsect1-function.rtrim-returnvalues)

Returns the modified string.


### Examples [¶](https://www.php.net/manual/en/function.rtrim.php\#refsect1-function.rtrim-examples)

**Example #1 Usage example of **rtrim()****

`<?php
$text = "\t\tThese are a few words :) ...  ";
$binary = "\x09Example string\x0A";
$hello  = "Hello World";
var_dump($text, $binary, $hello);
print "\n";
$trimmed = rtrim($text);
var_dump($trimmed);
$trimmed = rtrim($text, " \t.");
var_dump($trimmed);
$trimmed = rtrim($hello, "Hdle");
var_dump($trimmed);
// trim the ASCII control characters at the end of $binary
// (from 0 to 31 inclusive)
$clean = rtrim($binary, "\x00..\x1F");
var_dump($clean);
?>`

Run code

The above example will output:

```
string(32) "        These are a few words :) ...  "
string(16) "    Example string
"
string(11) "Hello World"

string(30) "        These are a few words :) ..."
string(26) "        These are a few words :)"
string(9) "Hello Wor"
string(15) "    Example string"
```

### See Also [¶](https://www.php.net/manual/en/function.rtrim.php\#refsect1-function.rtrim-seealso)

- [trim()](https://www.php.net/manual/en/function.trim.php) \- Strip whitespace (or other characters) from the beginning and end of a string
- [ltrim()](https://www.php.net/manual/en/function.ltrim.php) \- Strip whitespace (or other characters) from the beginning of a string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/rtrim.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.rtrim%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.rtrim&repo=en&redirect=https://www.php.net/manual/en/function.rtrim.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=95802&page=function.rtrim&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95802&page=function.rtrim&vote=down "Vote down!")

46


[**_pinkgothic at gmail dot com_**](https://www.php.net/manual/en/function.rtrim.php#95802) [¶](https://www.php.net/manual/en/function.rtrim.php#95802)

**15 years ago**

`I have an obsessive love for php's array functions given how extremely easy they've made complex string handling for me in various situations... so, have another string-rtrim() variant:
<?php
function strrtrim($message, $strip) {
    // break message apart by strip string
    $lines = explode($strip, $message);
    $last  = '';
    // pop off empty strings at the end
    do {
        $last = array_pop($lines);
    } while (empty($last) && (count($lines)));
    // re-assemble what remains
    return implode($strip, array_merge($lines, array($last)));
}
?>
Astonishingly, something I didn't expect, but: It completely compares to harmor's rstrtrim below, execution time wise. o_o Whee!`

[up](https://www.php.net/manual/vote-note.php?id=62040&page=function.rtrim&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62040&page=function.rtrim&vote=down "Vote down!")

29


[**_gbelanger at exosecurity dot com_**](https://www.php.net/manual/en/function.rtrim.php#62040) [¶](https://www.php.net/manual/en/function.rtrim.php#62040)

**19 years ago**

`True, the Perl chomp() will only trim newline characters. There is, however, the Perl chop() function which is pretty much identical to the PHP rtrim()
---
Here's a quick way to recursively trim every element of an array, useful after the file() function :
<?php
# Reads /etc/passwd file an trims newlines on each entry
$aFileContent = file("/etc/passwd");
foreach ($aFileContent as $sKey => $sValue) {
    $aFileContent[$sKey] = rtrim($sValue);
}
print_r($aFileContent);
?>`

[up](https://www.php.net/manual/vote-note.php?id=35108&page=function.rtrim&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=35108&page=function.rtrim&vote=down "Vote down!")

27


[**_todd at magnifisites dot com_**](https://www.php.net/manual/en/function.rtrim.php#35108) [¶](https://www.php.net/manual/en/function.rtrim.php#35108)

**22 years ago**

`This shows how rtrim works when using the optional charlist parameter:
rtrim reads a character, one at a time, from the optional charlist parameter and compares it to the end of the str string. If the characters match, it trims it off and starts over again, looking at the "new" last character in the str string and compares it to the first character in the charlist again. If the characters do not match, it moves to the next character in the charlist parameter comparing once again. It continues until the charlist parameter has been completely processed, one at a time, and the str string no longer contains any matches. The newly "rtrimmed" string is returned.
<?php
// Example 1:
rtrim('This is a short short sentence', 'short sentence');
// returns 'This is a'
// If you were expecting the result to be 'This is a short ',
// then you're wrong; the exact string, 'short sentence',
// isn't matched.  Remember, character-by-character comparison!
// Example 2:
rtrim('This is a short short sentence', 'cents');
// returns 'This is a short short '
?>`

[up](https://www.php.net/manual/vote-note.php?id=112577&page=function.rtrim&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112577&page=function.rtrim&vote=down "Vote down!")

15


[**_pinkgothic at gmail dot com_**](https://www.php.net/manual/en/function.rtrim.php#112577) [¶](https://www.php.net/manual/en/function.rtrim.php#112577)

**12 years ago**

`On the recurring subject of string-stripping instead of character-stripping rtrim() implementations... the simplest (with a caveat) is probably the basename() function. It has a second parameter that functions as a right-trim using whole strings:
<?php
echo basename('MooFoo', 'Foo');
?>
...outputs 'Moo'.
Since it also strips anything that looks like a directory, it's not quite identical with hacking a string off the end:
<?php
echo basename('Zoo/MooFoo', 'Foo');
?>
...still outputs 'Moo'.
But sometimes it gets the job done.`

[up](https://www.php.net/manual/vote-note.php?id=49079&page=function.rtrim&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=49079&page=function.rtrim&vote=down "Vote down!")

18


[**_Unimagined at UnaimaginedDesigns dot Com_**](https://www.php.net/manual/en/function.rtrim.php#49079) [¶](https://www.php.net/manual/en/function.rtrim.php#49079)

**20 years ago**

`I needed a way to trim all white space and then a few chosen strings from the end of a string.  So I wrote this class to reuse when stuff needs to be trimmed.
<?php
class cleaner {
function cleaner ($cuts,$pinfo) {
$ucut = "0";
$lcut = "0";
while ($cuts[$ucut]) {
$lcut++;
$ucut++;
}
$lcut = $lcut - 1;
$ucut = "0";
$rcut = "0";
$wiy = "start";
while ($wiy) {
if ($so) {
$ucut = "0";
$rcut = "0";
unset($so);
}
if (!$cuts[$ucut]) {
$so = "restart";
} else {
$pinfo = rtrim($pinfo);
$bpinfol = strlen($pinfo);
$tcut = $cuts[$ucut];
$pinfo = rtrim($pinfo,"$tcut");
$pinfol = strlen($pinfo);
    if ($bpinfol == $pinfol) {
    $rcut++;
    if ($rcut == $lcut) {
    unset($wiy);
    }
    $ucut++;
    } else {
    $so = "restart";
    }
}
}
$this->cleaner = $pinfo;
}
}
$pinfo = "Well... I'm really bored...<br /><br>&nbsp;    \n\t&nbsp;<br><br /><br>&nbsp;    \r\r&nbsp;<br>\r<br /><br>\r&nbsp;    &nbsp;\n<br>      <br />\t";
$cuts = array('\n','\r','\t',' ',' ','&nbsp;','<br />','<br>','<br/>');
$pinfo = new cleaner($cuts,$pinfo);
$pinfo = $pinfo->cleaner;
print $pinfo;
?>
That class will take any string that you put in the $cust array and remove it from the end of the $pinfo string.  It's useful for cleaning up comments, articles, or mail that users post to your site, making it so there's no extra blank space or blank lines.`

[up](https://www.php.net/manual/vote-note.php?id=82307&page=function.rtrim&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82307&page=function.rtrim&vote=down "Vote down!")

3


[**_harmor_**](https://www.php.net/manual/en/function.rtrim.php#82307) [¶](https://www.php.net/manual/en/function.rtrim.php#82307)

**17 years ago**

`I'm sure there's a better way to strip strings from the end of strings.
<?php
/**
* Strip a string from the end of a string
*
* @param string $str      the input string
* @param string $remove   OPTIONAL string to remove
*
* @return string the modified string
*/
function rstrtrim($str, $remove=null)
{
    $str    = (string)$str;
    $remove = (string)$remove;

    if(empty($remove))
    {
        return rtrim($str);
    }

    $len = strlen($remove);
    $offset = strlen($str)-$len;
    while($offset > 0 && $offset == strpos($str, $remove, $offset))
    {
        $str = substr($str, 0, $offset);
        $offset = strlen($str)-$len;
    }

    return rtrim($str);

} //End of function rstrtrim($str, $remove=null)
echo rstrtrim('Hello World!!!', '!')   .'<br />'; //"Hello World"
echo rstrtrim('Hello World!!!', '!!')  .'<br />'; //"Hello World!"
echo rstrtrim('Hello World!!!', '!!!') .'<br />'; //"Hello World"
echo rstrtrim('Hello World!!!', '!!!!').'<br />'; //"Hello World!!!"
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.rtrim&repo=en&redirect=https://www.php.net/manual/en/function.rtrim.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google