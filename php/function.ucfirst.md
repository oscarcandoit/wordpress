---
url: https://www.php.net/manual/en/function.ucfirst.php
scraped_at: 2025-10-20T02:48:29.396Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ucfirst

(PHP 4, PHP 5, PHP 7, PHP 8)

ucfirst — Make a string's first character uppercase

### Description [¶](https://www.php.net/manual/en/function.ucfirst.php\#refsect1-function.ucfirst-description)

**ucfirst**([string](https://www.php.net/manual/en/language.types.string.php) `$string`): [string](https://www.php.net/manual/en/language.types.string.php)

Returns a string with the first character of
`string` capitalized, if that character is
an ASCII character in the range from `"a"` (0x61) to
`"z"` (0x7a).


### Parameters [¶](https://www.php.net/manual/en/function.ucfirst.php\#refsect1-function.ucfirst-parameters)

`string`

The input string.


### Return Values [¶](https://www.php.net/manual/en/function.ucfirst.php\#refsect1-function.ucfirst-returnvalues)

Returns the resulting string.


### Changelog [¶](https://www.php.net/manual/en/function.ucfirst.php\#refsect1-function.ucfirst-changelog)

| Version | Description |
| --- | --- |
| 8.2.0 | Case conversion no longer depends on the locale set with<br> [setlocale()](https://www.php.net/manual/en/function.setlocale.php). Only ASCII characters will be converted. |

### Examples [¶](https://www.php.net/manual/en/function.ucfirst.php\#refsect1-function.ucfirst-examples)

**Example #1 **ucfirst()** example**

`<?php
$foo = 'hello world!';
echo ucfirst($foo), PHP_EOL;             // Hello world!
$bar = 'HELLO WORLD!';
echo ucfirst($bar), PHP_EOL;             // HELLO WORLD!
echo ucfirst(strtolower($bar)), PHP_EOL; // Hello world!
?>`

Run code

### See Also [¶](https://www.php.net/manual/en/function.ucfirst.php\#refsect1-function.ucfirst-seealso)

- [lcfirst()](https://www.php.net/manual/en/function.lcfirst.php) \- Make a string's first character lowercase
- [strtolower()](https://www.php.net/manual/en/function.strtolower.php) \- Make a string lowercase
- [strtoupper()](https://www.php.net/manual/en/function.strtoupper.php) \- Make a string uppercase
- [ucwords()](https://www.php.net/manual/en/function.ucwords.php) \- Uppercase the first character of each word in a string
- [mb\_convert\_case()](https://www.php.net/manual/en/function.mb-convert-case.php) \- Perform case folding on a string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/ucfirst.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.ucfirst%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ucfirst&repo=en&redirect=https://www.php.net/manual/en/function.ucfirst.php)

### User Contributed Notes 34 notes

[up](https://www.php.net/manual/vote-note.php?id=57298&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=57298&page=function.ucfirst&vote=down "Vote down!")

77


[**_plemieux_**](https://www.php.net/manual/en/function.ucfirst.php#57298) [¶](https://www.php.net/manual/en/function.ucfirst.php#57298)

**20 years ago**

`Simple multi-bytes ucfirst():
<?php
function my_mb_ucfirst($str) {
    $fc = mb_strtoupper(mb_substr($str, 0, 1));
    return $fc.mb_substr($str, 1);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=84122&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84122&page=function.ucfirst&vote=down "Vote down!")

33


[**_prokur.net - there is my email_**](https://www.php.net/manual/en/function.ucfirst.php#84122) [¶](https://www.php.net/manual/en/function.ucfirst.php#84122)

**17 years ago**

`I believe that mb_ucfirst will be soon added in PHP, but for now this could be useful
<?php
if (!function_exists('mb_ucfirst') && function_exists('mb_substr')) {
    function mb_ucfirst($string) {
        $string = mb_strtoupper(mb_substr($string, 0, 1)) . mb_substr($string, 1);
        return $string;
    }
}
?>
it also check is mb support enabled or not`

[up](https://www.php.net/manual/vote-note.php?id=125312&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125312&page=function.ucfirst&vote=down "Vote down!")

4


[**_Ekin_**](https://www.php.net/manual/en/function.ucfirst.php#125312) [¶](https://www.php.net/manual/en/function.ucfirst.php#125312)

**5 years ago**

`Using this function for Turkish language is won't work because of multi-byte characters. But you can use some tricks:
<?php
function ucfirst_tr($str) {
    $trMap = ['Ğ'=>'ğ','Ü'=>'ü','Ş'=>'ş','İ'=>'i','Ö'=>'ö','Ç'=>'ç','I'=>'ı'];
    $str = mb_strtolower(strtr($str, $trMap));
    $first = mb_substr($str, 0, 1);
    $first = strtr($first, array_flip($trMap));
    $first = mb_strtoupper($first);
    return $first . mb_substr($str, 1);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=86902&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86902&page=function.ucfirst&vote=down "Vote down!")

22


[**_mattalexxpub at gmail dot com_**](https://www.php.net/manual/en/function.ucfirst.php#86902) [¶](https://www.php.net/manual/en/function.ucfirst.php#86902)

**16 years ago**

`This is what I use for converting strings to sentence case:
<?php
function sentence_case($string) {
    $sentences = preg_split('/([.?!]+)/', $string, -1, PREG_SPLIT_NO_EMPTY|PREG_SPLIT_DELIM_CAPTURE);
    $new_string = '';
    foreach ($sentences as $key => $sentence) {
        $new_string .= ($key & 1) == 0?
            ucfirst(strtolower(trim($sentence))) :
            $sentence.' ';
    }
    return trim($new_string);
}
print sentence_case('HMM. WOW! WHAT?');
// Outputs: "Hmm. Wow! What?"
?>`

[up](https://www.php.net/manual/vote-note.php?id=113806&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113806&page=function.ucfirst&vote=down "Vote down!")

7


[**_mingalevme at gmail dot com_**](https://www.php.net/manual/en/function.ucfirst.php#113806) [¶](https://www.php.net/manual/en/function.ucfirst.php#113806)

**11 years ago**

`Implementation of multi-bytes ucfirst for "multiword"-strings (module mbstring is required):
<?php
public static function ucfirst($str)
{
    $str = mb_strtolower($str);
    $words = preg_split('/\b/u', $str, -1, PREG_SPLIT_NO_EMPTY);
    foreach ($words as $word) {
        $ucword = mb_strtoupper(mb_substr($word, 0, 1)) . mb_substr($word, 1);
        $str = str_replace($word, $ucword, $str);
    }
    return $str;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=107700&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107700&page=function.ucfirst&vote=down "Vote down!")

14


[**_qeremy \[atta\] gmail \[dotta\] com_**](https://www.php.net/manual/en/function.ucfirst.php#107700) [¶](https://www.php.net/manual/en/function.ucfirst.php#107700)

**13 years ago**

`A proper Turkish solution;
<?php
function ucfirst_turkish($str) {
    $tmp = preg_split("//u", $str, 2, PREG_SPLIT_NO_EMPTY);
    return mb_convert_case(
        str_replace("i", "İ", $tmp[0]), MB_CASE_TITLE, "UTF-8").
        $tmp[1];
}
$str = "iyilik güzelLİK";
echo ucfirst($str) ."\n";   // Iyilik güzelLİK
echo ucfirst_turkish($str); // İyilik güzelLİK
?>`

[up](https://www.php.net/manual/vote-note.php?id=81258&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81258&page=function.ucfirst&vote=down "Vote down!")

10


[**_charliefortune_**](https://www.php.net/manual/en/function.ucfirst.php#81258) [¶](https://www.php.net/manual/en/function.ucfirst.php#81258)

**17 years ago**

`Here's a function to capitalize segments of a name, and put the rest into lower case. You can pass the characters you want to use as delimiters.
i.e. <?php echo nameize("john o'grady-smith"); ?>
returns John O'Grady-Smith
<?php
function nameize($str,$a_char = array("'","-"," ")){
    //$str contains the complete raw name string
    //$a_char is an array containing the characters we use as separators for capitalization. If you don't pass anything, there are three in there as default.
    $string = strtolower($str);
    foreach ($a_char as $temp){
        $pos = strpos($string,$temp);
        if ($pos){
            //we are in the loop because we found one of the special characters in the array, so lets split it up into chunks and capitalize each one.
            $mend = '';
            $a_split = explode($temp,$string);
            foreach ($a_split as $temp2){
                //capitalize each portion of the string which was separated at a special character
                $mend .= ucfirst($temp2).$temp;
                }
            $string = substr($mend,0,-1);
            }
        }
    return ucfirst($string);
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=120689&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120689&page=function.ucfirst&vote=down "Vote down!")

5


[**_nospam at nospam dot com_**](https://www.php.net/manual/en/function.ucfirst.php#120689) [¶](https://www.php.net/manual/en/function.ucfirst.php#120689)

**8 years ago**

`Improved method of capitalizing first characters of sentences.
The first two manipulations (double spaces & all caps) are optional so can be removed without harm.
<?php
// return string with first letters of sentences capitalized
function ucsentence($str) {
if ($str) { // input
    $str = preg_replace('/'.chr(32).chr(32).'+/', chr(32), $str); // recursively replaces all double spaces with a space
    if (($x = substr($str, 0, 10)) && ($x == strtoupper($x))) $str = strtolower($str); // sample of first 10 chars is ALLCAPS so convert $str to lowercase; if always done then any proper capitals would be lost
    $na = array('. ', '! ', '? '); // punctuation needles
    foreach ($na as $n) { // each punctuation needle
      if (strpos($str, $n) !== false) { // punctuation needle found
        $sa = explode($n, $str); // split
        foreach ($sa as $s) $ca[] = ucfirst($s); // capitalize
        $str = implode($n, $ca); // replace $str with rebuilt version
        unset($ca); //  clear for next loop
      }
    }
    return ucfirst(trim($str)); // capitalize first letter in case no punctuation needles found
}
}
?>
"heLLo EarthLing!" >> "HeLLo EarthLing!"
"I'M MOSTLY. caps!  " >> "I'm mostly. Caps!"
"ALLCAPS" >> "Allcaps"
"i haVe neST.ed punct,u.ation!  sp    A  c es.  and CAPs..  " >> "I haVe neST.ed punct,u.ation! Sp A c es. And CAPs.."`

[up](https://www.php.net/manual/vote-note.php?id=121552&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121552&page=function.ucfirst&vote=down "Vote down!")

2


[**_Anonymous_**](https://www.php.net/manual/en/function.ucfirst.php#121552) [¶](https://www.php.net/manual/en/function.ucfirst.php#121552)

**8 years ago**

`Format the input string:
<?php
function ucsentences($string){
    $parts = preg_split('/([^\.\!\?;]+[\.\!\?;"]+)/', strtolower($string), (-1), PREG_SPLIT_DELIM_CAPTURE|PREG_SPLIT_NO_EMPTY);
    $r = '';
    foreach($parts as $key=>$sentence){
        $r .= ucfirst(trim($sentence)) . ' ';
    }
    $r = preg_replace('/\bi\b/', 'I', $r);
    $r = preg_replace_callback('/("[a-z])/', function($m){ return strtoupper($m[0]);}, $r);
    return rtrim($r);
}
$str = 'i\'m not sure. if this is good enough, but i thought: "hey, who know\'s. maybe i am right."';
?>
Outputs:
I'm not sure. If this is good enough, but I thought: "Hey, who know's. Maybe I am right."`

[up](https://www.php.net/manual/vote-note.php?id=72185&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72185&page=function.ucfirst&vote=down "Vote down!")

3


[**_Carel at divers information with dotcom_**](https://www.php.net/manual/en/function.ucfirst.php#72185) [¶](https://www.php.net/manual/en/function.ucfirst.php#72185)

**18 years ago**

`I made a small change. Now it takes care of points in numbers
function ucsentence ($string){
$string = explode ('.', $string);
$count = count ($string);
for ($i = 0; $i < $count; $i++){
       $string[$i]  = ucfirst (trim ($string[$i]));
       if ($i > 0){
           if ((ord($string[$i]{0})<48) || (ord($string[$i]{0})>57)) {
              $string[$i] = ' ' . $string[$i];
           }
       }
}
$string = implode ('.', $string);
return $string;
}`

[up](https://www.php.net/manual/vote-note.php?id=62371&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62371&page=function.ucfirst&vote=down "Vote down!")

3


[**_Bartuc_**](https://www.php.net/manual/en/function.ucfirst.php#62371) [¶](https://www.php.net/manual/en/function.ucfirst.php#62371)

**19 years ago**

`Here is the fixed function for Turkish alphabet..
<?php
function uc_first($str){
$str[0] = strtr($str,
"abcdefgh?ijklmnopqrstuvwxyz".
"\x9C\x9A\xE0\xE1\xE2\xE3".
"\xE4\xE5\xE6\xE7\xE8\xE9".
"\xEA\xEB\xEC\xED\xEE\xEF".
"\xF0\xF1\xF2\xF3\xF4\xF5".
"\xF6\xF8\xF9\xFA\xFB\xFC".
"\xFE\xFF",
"ABCDEFGHI?JKLMNOPQRSTUVWXYZ".
"\x8C\x8A\xC0\xC1\xC2\xC3\xC4".
"\xC5\xC6\xC7\xC8\xC9\xCA\xCB".
"\xCC\xCD\xCE\xCF\xD0\xD1\xD2".
"\xD3\xD4\xD5\xD6\xD8\xD9\xDA".
"\xDB\xDC\xDE\x9F");
return $str;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=103907&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103907&page=function.ucfirst&vote=down "Vote down!")

4


[**_Quicker_**](https://www.php.net/manual/en/function.ucfirst.php#103907) [¶](https://www.php.net/manual/en/function.ucfirst.php#103907)

**14 years ago**

`if you want to ucfirst for utf8 try this one:
<?php
function ucfirst_utf8($stri){
if($stri{0}>="\xc3")
     return (($stri{1}>="\xa0")?
     ($stri{0}.chr(ord($stri{1})-32)):
     ($stri{0}.$stri{1})).substr($stri,2);
else return ucfirst($stri);
}
?>
It is quick, not language (but utf8) dependend and does not use any mb-functions such as mb_ucfirst.`

[up](https://www.php.net/manual/vote-note.php?id=97277&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=97277&page=function.ucfirst&vote=down "Vote down!")

3


[**_pete at namecube dot net_**](https://www.php.net/manual/en/function.ucfirst.php#97277) [¶](https://www.php.net/manual/en/function.ucfirst.php#97277)

**15 years ago**

`for anyone wanting to ucfirst each word in a sentence this works for me:
<?php
function ucfirst_sentence($str)
{
    return preg_replace('/\b(\w)/e', 'strtoupper("$1")', $str);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=93763&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93763&page=function.ucfirst&vote=down "Vote down!")

3


[**_octavius_**](https://www.php.net/manual/en/function.ucfirst.php#93763) [¶](https://www.php.net/manual/en/function.ucfirst.php#93763)

**16 years ago**

`For lithuanian text with utf-8 encoding I use two functions (thanks [mattalexxpub at gmail dot com] and Svetoslav Marinov)
<?php
function my_ucfirst($string, $e ='utf-8') {
    if (function_exists('mb_strtoupper') && function_exists('mb_substr') && !empty($string)) {
        $string = mb_strtolower($string, $e);
        $upper = mb_strtoupper($string, $e);
            preg_match('#(.)#us', $upper, $matches);
            $string = $matches[1] . mb_substr($string, 1, mb_strlen($string, $e), $e);
    }
    else {
        $string = ucfirst($string);
    }
    return $string;
}
function sentence_case($string) {
    $sentences = preg_split('/([.?!]+)/', $string, -1, PREG_SPLIT_NO_EMPTY|PREG_SPLIT_DELIM_CAPTURE);
    $new_string = '';
    foreach ($sentences as $key => $sentence) {
        $new_string .= ($key & 1) == 0?
            my_ucfirst(strtolower(trim($sentence))) :
            $sentence.' ';
    }
    return trim($new_string);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=105435&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105435&page=function.ucfirst&vote=down "Vote down!")

2


[**_vlknmtn at gmail dot com_**](https://www.php.net/manual/en/function.ucfirst.php#105435) [¶](https://www.php.net/manual/en/function.ucfirst.php#105435)

**14 years ago**

`Turkish solution:
<?php
mb_internal_encoding("UTF-8");
mb_regex_encoding("UTF-8");
function tr_ilkbuyuk($text)
{
    $text = str_replace("I","ı",$text);
    $text = mb_strtolower($text, 'UTF-8');

    if($text[0] == "i")
        $tr_text = "İ".substr($text, 1);
    else
        $tr_text = mb_convert_case($text, MB_CASE_TITLE, "UTF-8");

    return trim($tr_text);
}
function tr_ucwords($text)
{
    $p = explode(" ",$text);
    if(is_array($p))
    {
        $tr_text = "";
        foreach($p AS $item)
            $tr_text .= " ".tr_ilkbuyuk($item);

        return trim($tr_text);
    }
    else
        return tr_ilkbuyuk($text);
}
$deger = "ıişllşlsdg";
echo tr_ucwords($deger);
?>`

[up](https://www.php.net/manual/vote-note.php?id=60620&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60620&page=function.ucfirst&vote=down "Vote down!")

2


[**_Markus Ernst_**](https://www.php.net/manual/en/function.ucfirst.php#60620) [¶](https://www.php.net/manual/en/function.ucfirst.php#60620)

**19 years ago**

`plemieux' function did not work for me without passing the encoding to every single mb function (despite ini_set('default_charset', 'utf-8') at the top of the script). This is the example that works in my application (PHP 4.3):
<?php
function my_mb_ucfirst($str, $e='utf-8') {
    $fc = mb_strtoupper(mb_substr($str, 0, 1, $e), $e);
    return $fc.mb_substr($str, 1, mb_strlen($str, $e), $e);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=87133&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87133&page=function.ucfirst&vote=down "Vote down!")

4


[**_svetoslavm at gmail dot com_**](https://www.php.net/manual/en/function.ucfirst.php#87133) [¶](https://www.php.net/manual/en/function.ucfirst.php#87133)

**16 years ago**

`For some reason this worked for me.
Mac OS 10.5.1
PHP 5.2.6
<?php
/**
     * ucfirst UTF-8 aware function
     *
     * @param string $string
     * @return string
     * @see [http://ca.php.net/ucfirst](http://ca.php.net/ucfirst)
     */
    function my_ucfirst($string, $e ='utf-8') {
        if (function_exists('mb_strtoupper') && function_exists('mb_substr') && !empty($string)) {
            $string = mb_strtolower($string, $e);
            $upper = mb_strtoupper($string, $e);
            preg_match('#(.)#us', $upper, $matches);
            $string = $matches[1] . mb_substr($string, 1, mb_strlen($string, $e), $e);
        } else {
            $string = ucfirst($string);
        }
        return $string;
    }
?>
Svetoslav Marinov
[http://slavi.biz](http://slavi.biz/)`

[up](https://www.php.net/manual/vote-note.php?id=92584&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92584&page=function.ucfirst&vote=down "Vote down!")

1


[**_bgschool_**](https://www.php.net/manual/en/function.ucfirst.php#92584) [¶](https://www.php.net/manual/en/function.ucfirst.php#92584)

**16 years ago**

`Simple function for use ucfirst with utf-8 encoded cyrylic text
<?php
    public function capitalize_first($str) {
        $line = iconv("UTF-8", "Windows-1251", $str); // convert to windows-1251
        $line = ucfirst($line);
        $line = iconv("Windows-1251", "UTF-8", $line); // convert back to utf-8

        return $line;
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=95796&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95796&page=function.ucfirst&vote=down "Vote down!")

1


[**_wilfried dot loche at fr dot adp dot com_**](https://www.php.net/manual/en/function.ucfirst.php#95796) [¶](https://www.php.net/manual/en/function.ucfirst.php#95796)

**15 years ago**

`If someone looks for the equivalent on Oracle DB, here it is: INITCAP. Hope this helps!`

[up](https://www.php.net/manual/vote-note.php?id=115039&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115039&page=function.ucfirst&vote=down "Vote down!")

0


[**_kiprasbal at gmail dot com_**](https://www.php.net/manual/en/function.ucfirst.php#115039) [¶](https://www.php.net/manual/en/function.ucfirst.php#115039)

**11 years ago**

`My version, converst first letter of the first word in the string to uppercase
public function mb_ucfirst($str) {
        $aParts = explode(" ",$str);
        $firstWord = mb_convert_case($aParts[0],MB_CASE_TITLE,"UTF-8");
        unset($aParts[0]);
        return $firstWord." ".implode(" ",$aParts);
    }`

[up](https://www.php.net/manual/vote-note.php?id=81018&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81018&page=function.ucfirst&vote=down "Vote down!")

0


[**_webmaster at onmyway dot cz_**](https://www.php.net/manual/en/function.ucfirst.php#81018) [¶](https://www.php.net/manual/en/function.ucfirst.php#81018)

**17 years ago**

`Inspired by the lcfirst function a simple mb_lcfirst to cope with multibyte strings:
<?php
function mb_lcfirst($str, $enc = null)
{
if($enc === null) $enc = mb_internal_encoding();
return mb_strtolower(mb_substr($str, 0, 1, $enc), $enc).mb_substr($str, 1, mb_strlen($str, $enc), $enc);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=76384&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76384&page=function.ucfirst&vote=down "Vote down!")

0


[**_adefoor at gmail dot com_**](https://www.php.net/manual/en/function.ucfirst.php#76384) [¶](https://www.php.net/manual/en/function.ucfirst.php#76384)

**18 years ago**

`Ken and zee
One thing I would do to make this more unviersally work would be to add strtolower() around your $sentence.  Doing this will allow you to convert an all caps text block as well as an all lowercase text block.
<?php
function sentence_cap($impexp, $sentence_split) {
    $textbad=explode($impexp, $sentence_split);
    $newtext = array();
    foreach ($textbad as $sentence) {
        $sentencegood=ucfirst(strtolower($sentence));
        $newtext[] = $sentencegood;
    }
    $textgood = implode($impexp, $newtext);
    return $textgood;
}
$text = "this is a sentence. this is another sentence! this is the fourth sentence? no, this is the fourth sentence.";
$text = sentence_cap(". ",$text);
$text = sentence_cap("! ",$text);
$text = sentence_cap("? ",$text);
echo $text; // This is a sentence. This is another sentence! This is the fourth sentence? No, this is the fourth sentence.
?>`

[up](https://www.php.net/manual/vote-note.php?id=63799&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=63799&page=function.ucfirst&vote=down "Vote down!")

0


[**_Markus Ernst_**](https://www.php.net/manual/en/function.ucfirst.php#63799) [¶](https://www.php.net/manual/en/function.ucfirst.php#63799)

**19 years ago**

`A combination of the below functions to enable ucfirst for multibyte strings in a shared hosting environment (where you can not always count on mbstring to be installed):
<?php
function my_mb_ucfirst($str, $e='utf-8') {
    if (function_exists('mb_strtoupper')) {
        $fc = mb_strtoupper(mb_substr($str, 0, 1, $e), $e);
        return $fc.mb_substr($str, 1, mb_strlen($str, $e), $e);
    }
    else {
        $str = utf8_decode($str);
        $str[0] = strtr($str[0],
            "abcdefghýijklmnopqrstuvwxyz".
            "\x9C\x9A\xE0\xE1\xE2\xE3".
            "\xE4\xE5\xE6\xE7\xE8\xE9".
            "\xEA\xEB\xEC\xED\xEE\xEF".
            "\xF0\xF1\xF2\xF3\xF4\xF5".
            "\xF6\xF8\xF9\xFA\xFB\xFC".
            "\xFE\xFF",
            "ABCDEFGHÝIJKLMNOPQRSTUVWXYZ".
            "\x8C\x8A\xC0\xC1\xC2\xC3\xC4".
            "\xC5\xC6\xC7\xC8\xC9\xCA\xCB".
            "\xCC\xCD\xCE\xCF\xD0\xD1\xD2".
            "\xD3\xD4\xD5\xD6\xD8\xD9\xDA".
            "\xDB\xDC\xDE\x9F");
        return utf8_encode($str);
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=54076&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=54076&page=function.ucfirst&vote=down "Vote down!")

0


[**_info \[at\] spwdesign \[dot\] com_**](https://www.php.net/manual/en/function.ucfirst.php#54076) [¶](https://www.php.net/manual/en/function.ucfirst.php#54076)

**20 years ago**

`This is a simple code to get all the 'bad words', stored in a database, out of the text. You could use str_ireplace but since that's installed on PHP5 only, this works as well. It strtolowers the text first then places capitals with ucfirst() where it thinks a capital should be placed, at a new sentence. The previous sentence is ended by '. ' then.
<?php
function filter($text){
    $filters=mysql_query("SELECT word,result FROM filter");
    while($filter=mysql_fetch_array($filters)){
        $text=str_replace($filter[word],$filter[result],strtolower($text));
        $parts=explode(". ",$text);
        for($i=0;$i<count($parts);$i++){
            $parts[$i]=ucfirst($parts[$i]);
        }
        $text=implode(". ",$parts);
    }
    return $text;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=50884&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=50884&page=function.ucfirst&vote=down "Vote down!")

0


[**_Anonymous_**](https://www.php.net/manual/en/function.ucfirst.php#50884) [¶](https://www.php.net/manual/en/function.ucfirst.php#50884)

**20 years ago**

`Ah, the last code were spoiled, here is the fixed one:
<?php
function uc_first($str){
    $str[0] = strtr($str,
    "abcdefghijklmnopqrstuvwxyz".
    "\x9C\x9A\xE0\xE1\xE2\xE3".
    "\xE4\xE5\xE6\xE7\xE8\xE9".
    "\xEA\xEB\xEC\xED\xEE\xEF".
    "\xF0\xF1\xF2\xF3\xF4\xF5".
    "\xF6\xF8\xF9\xFA\xFB\xFC".
    "\xFD\xFE\xFF",
    "ABCDEFGHIJKLMNOPQRSTUVWXYZ".
    "\x8C\x8A\xC0\xC1\xC2\xC3\xC4".
    "\xC5\xC6\xC7\xC8\xC9\xCA\xCB".
    "\xCC\xCD\xCE\xCF\xD0\xD1\xD2".
    "\xD3\xD4\xD5\xD6\xD8\xD9\xDA".
    "\xDB\xDC\xDD\xDE\x9F");
    return $str;
}
?>
So, this function changes also other letters into uppercase, ucfirst() does only change: a-z to: A-Z.`

[up](https://www.php.net/manual/vote-note.php?id=43435&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=43435&page=function.ucfirst&vote=down "Vote down!")

0


[**_steven at tux dot appstate dot edu_**](https://www.php.net/manual/en/function.ucfirst.php#43435) [¶](https://www.php.net/manual/en/function.ucfirst.php#43435)

**21 years ago**

`Note: the return for this function changed in versions 4.3 when a string is passed of length 0.  In <4.2 false is returned and in >4.3 a string of length 0 is returned.
Example:
$name = ucfirst("");
var_dump($name);
$name = ucfirst("owen");
var_dump($name);
Results for <4.2:
bool(false) string(4) "Owen"
Results for >4.3:
string(0) "" string(4) "Owen"`

[up](https://www.php.net/manual/vote-note.php?id=41376&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=41376&page=function.ucfirst&vote=down "Vote down!")

0


[**_Ami Hughes (ami at mistress dot name)_**](https://www.php.net/manual/en/function.ucfirst.php#41376) [¶](https://www.php.net/manual/en/function.ucfirst.php#41376)

**21 years ago**

`In the event you sort of need multiple delimiters to apply the same action to, you can preg_replace this "second delimiter" enveloping it with your actual delimiter.

A for instance, would be if you wanted to use something like Lee's FormatName function in an input box designed for their full name as this script was only designed to check the last name as if it were the entire string.  The problem is that you still want support for double-barreled names and you still want to be able to support the possibility that if the second part of the double-barreled name starts with "mc", that it will still be formatted correctly.
This example does a preg_replace that surrounds the separator with your actual delimiter.  This is just a really quick alternative to writing some bigger fancier blah-blah function.  If there's a shorter, simpler way to do it, feel free to inform me.  (Emphasis on shorter and simpler because that was the whole point of this.) :D
Here's the example.  I've removed Lee's comments as not to confuse them with my own.
<?php
function FormatName($name=NULL)
{
       if (empty($name))
           return false;
       $name = strtolower($name);
       $name = preg_replace("[\-]", " - ",$name); // Surround hyphens with our delimiter so our strncmp is accurate
       if (preg_match("/^[a-z]{2,}$/i",$name))  // Simple preg_match if statement
       {

           $names_array = explode(' ',$name);  // Set the delimiter as a space.

           for ($i = 0; $i < count($names_array); $i++)
           {
               if (strncmp($names_array[$i],'mc',2) == 0 || ereg('^[oO]\'[a-zA-Z]',$names_array[$i]))
               {
                   $names_array[$i][2] = strtoupper($names_array[$i][2]);
               }
               $names_array[$i] = ucfirst($names_array[$i]);

           }

           $name = implode(' ',$names_array);
           $name = preg_replace("[ \- ]", "-",$name); //  Remove the extra instances of our delimiter
           return ucwords($name);

       }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=32844&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=32844&page=function.ucfirst&vote=down "Vote down!")

0


[**_bkimble at ebaseweb dot com_**](https://www.php.net/manual/en/function.ucfirst.php#32844) [¶](https://www.php.net/manual/en/function.ucfirst.php#32844)

**22 years ago**

`Here is a handy function that makes the first letter of everything in a sentence upercase. I used it to deal with titles of events posted on my website ... I've added exceptions for uppercase words and lowercase words so roman numeral "IV" doesn't get printed as "iv" and words like "a" and "the" and "of" stay lowercase.
function RemoveShouting($string)
{
$lower_exceptions = array(
        "to" => "1", "a" => "1", "the" => "1", "of" => "1"
);

$higher_exceptions = array(
        "I" => "1", "II" => "1", "III" => "1", "IV" => "1",
        "V" => "1", "VI" => "1", "VII" => "1", "VIII" => "1",
        "XI" => "1", "X" => "1"
);
$words = split(" ", $string);
$newwords = array();

foreach ($words as $word)
{
        if (!$higher_exceptions[$word])
                $word = strtolower($word);
        if (!$lower_exceptions[$word])
                $word = ucfirst($word);
         array_push($newwords, $word);

}

return join(" ", $newwords);
}`

[up](https://www.php.net/manual/vote-note.php?id=110261&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110261&page=function.ucfirst&vote=down "Vote down!")

 -1


[**_Nethor_**](https://www.php.net/manual/en/function.ucfirst.php#110261) [¶](https://www.php.net/manual/en/function.ucfirst.php#110261)

**13 years ago**

`Simple but workable solution:
<?php
mb_internal_encoding("UTF-8");  // before calling the function
function utf8_ucfirst($str){
    preg_match_all("~^(.)(.*)$~u", $str, $arr);
    return mb_strtoupper($arr[1][0]).$arr[2][0];
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=73895&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73895&page=function.ucfirst&vote=down "Vote down!")

 -1


[**_Ken Kehler_**](https://www.php.net/manual/en/function.ucfirst.php#73895) [¶](https://www.php.net/manual/en/function.ucfirst.php#73895)

**18 years ago**

`@ zee: this should solve your !, ?, and any punctuations you want to add. It can probably be cleaned up a bit.
<?php
function sentence_cap($impexp, $sentence_split) {
    $textbad=explode($impexp, $sentence_split);
    $newtext = array();
    foreach ($textbad as $sentence) {
        $sentencegood=ucfirst($sentence);
        $newtext[] = $sentencegood;
    }
    $textgood = implode($impexp, $newtext);
    return $textgood;
}
$text = "this is a sentence. this is another sentence! this is the fourth sentence? no, this is the fourth sentence.";
$text = sentence_cap(". ",$text);
$text = sentence_cap("! ",$text);
$text = sentence_cap("? ",$text);
echo $text; // This is a sentence. This is another sentence! This is the fourth sentence? No, this is the fourth sentence.
?>`

[up](https://www.php.net/manual/vote-note.php?id=76694&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76694&page=function.ucfirst&vote=down "Vote down!")

 -1


[**_Uwe_**](https://www.php.net/manual/en/function.ucfirst.php#76694) [¶](https://www.php.net/manual/en/function.ucfirst.php#76694)

**18 years ago**

`@adefoor, Ken and Zee
Changing the case can only be done by understanding the text. Take for example "USA", "Sunday", "March", "I am ...", abbreviations like "prob." and so on.`

[up](https://www.php.net/manual/vote-note.php?id=70752&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70752&page=function.ucfirst&vote=down "Vote down!")

 -2


[**_Anonymous_**](https://www.php.net/manual/en/function.ucfirst.php#70752) [¶](https://www.php.net/manual/en/function.ucfirst.php#70752)

**18 years ago**

`Some simple function for cyrillic and latin letters both:
function rucfirst($str) {
    if(ord(substr($str,0,1))<192) return ucfirst($str);
    else
    return chr(ord(substr($str,0,1))-32).substr($str,1);
}`

[up](https://www.php.net/manual/vote-note.php?id=69602&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=69602&page=function.ucfirst&vote=down "Vote down!")

 -4


[**_Michael_**](https://www.php.net/manual/en/function.ucfirst.php#69602) [¶](https://www.php.net/manual/en/function.ucfirst.php#69602)

**19 years ago**

`This is what you would expect php to deliver if there was a built-in function named ucsentence.
function ucsentence ($string){
    $string = explode ('.', $string);
    $count = count ($string);
    for ($i = 0; $i < $count; $i++){
        $string[$i]  = ucfirst (trim ($string[$i]));
        if ($i > 0){
            $string[$i] = '&nbsp;&nbsp;' . $string[$i];
        }
    }
    $string = implode ('.', $string);
    return $string;
}`

[up](https://www.php.net/manual/vote-note.php?id=124408&page=function.ucfirst&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124408&page=function.ucfirst&vote=down "Vote down!")

 -2


[**_divinity76 at gmail dot com_**](https://www.php.net/manual/en/function.ucfirst.php#124408) [¶](https://www.php.net/manual/en/function.ucfirst.php#124408)

**5 years ago**

`here is how mb_ucfirst should be implemented in userland
<?php
function mb_ucfirst(string $str, string $encoding = null): string
{
    if ($encoding === null) {
        $encoding = mb_internal_encoding();
    }
    return mb_strtoupper(mb_substr($str, 0, 1, $encoding), $encoding) . mb_substr($str, 1, null, $encoding);
}
?>
(when i wrote this comment, everybody else's attempt got it wrong for one reason or another, for example: some don't allow you to specify encoding, and some defaulted to utf-8 instead of defaulting to mb_internal_encoding() )`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ucfirst&repo=en&redirect=https://www.php.net/manual/en/function.ucfirst.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google