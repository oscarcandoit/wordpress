---
url: https://www.php.net/manual/en/function.ucwords.php
scraped_at: 2025-10-20T02:48:52.887Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ucwords

(PHP 4, PHP 5, PHP 7, PHP 8)

ucwords — Uppercase the first character of each word in a string

### Description [¶](https://www.php.net/manual/en/function.ucwords.php\#refsect1-function.ucwords-description)

**ucwords**([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [string](https://www.php.net/manual/en/language.types.string.php) `$separators` = " \\t\\r\\n\\f\\v"): [string](https://www.php.net/manual/en/language.types.string.php)

Returns a string with the first character of each word in
`string` capitalized, if that character is an ASCII
character between `"a"` (0x61) and `"z"`
(0x7a).


For this function, a word is a string of characters that are not listed in
the `separators` parameter. By default, these are:
space, horizontal tab, carriage return, newline, form-feed and vertical tab.


To do a similar conversion on multibyte strings, use
[mb\_convert\_case()](https://www.php.net/manual/en/function.mb-convert-case.php) with the **`[MB\_CASE\_TITLE](https://www.php.net/manual/en/mbstring.constants.php#constant.mb-case-title)`**
mode.


### Parameters [¶](https://www.php.net/manual/en/function.ucwords.php\#refsect1-function.ucwords-parameters)

`string`

The input string.


`separators`

The optional `separators` contains the word separator characters.


### Return Values [¶](https://www.php.net/manual/en/function.ucwords.php\#refsect1-function.ucwords-returnvalues)

Returns the modified string.


### Changelog [¶](https://www.php.net/manual/en/function.ucwords.php\#refsect1-function.ucwords-changelog)

| Version | Description |
| --- | --- |
| 8.2.0 | Case conversion no longer depends on the locale set with<br> [setlocale()](https://www.php.net/manual/en/function.setlocale.php). Only ASCII characters will be converted. |

### Examples [¶](https://www.php.net/manual/en/function.ucwords.php\#refsect1-function.ucwords-examples)

**Example #1 **ucwords()** example**

`<?php
$foo = 'hello world!';
echo ucwords($foo), PHP_EOL;             // Hello World!
$bar = 'HELLO WORLD!';
echo ucwords($bar), PHP_EOL;             // HELLO WORLD!
echo ucwords(strtolower($bar)), PHP_EOL; // Hello World!
?>`

Run code

**Example #2 **ucwords()** example with custom delimiter**

`<?php
$foo = 'hello|world!';
echo ucwords($foo), PHP_EOL;             // Hello|world!
echo ucwords($foo, "|"), PHP_EOL;        // Hello|World!
?>`

Run code

**Example #3 **ucwords()** example with additional delimiters**

`<?php
$foo = "mike o'hara";
echo ucwords($foo), PHP_EOL;                 // Mike O'hara
echo ucwords($foo, " \t\r\n\f\v'"), PHP_EOL; // Mike O'Hara
?>`

Run code

### Notes [¶](https://www.php.net/manual/en/function.ucwords.php\#refsect1-function.ucwords-notes)

> **Note**: This function is
> binary-safe.

### See Also [¶](https://www.php.net/manual/en/function.ucwords.php\#refsect1-function.ucwords-seealso)

- [strtoupper()](https://www.php.net/manual/en/function.strtoupper.php) \- Make a string uppercase
- [strtolower()](https://www.php.net/manual/en/function.strtolower.php) \- Make a string lowercase
- [ucfirst()](https://www.php.net/manual/en/function.ucfirst.php) \- Make a string's first character uppercase
- [mb\_convert\_case()](https://www.php.net/manual/en/function.mb-convert-case.php) \- Perform case folding on a string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/ucwords.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.ucwords%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ucwords&repo=en&redirect=https://www.php.net/manual/en/function.ucwords.php)

### User Contributed Notes 28 notes

[up](https://www.php.net/manual/vote-note.php?id=112795&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112795&page=function.ucwords&vote=down "Vote down!")

43


[**_antoniomax at antoniomax dot com_**](https://www.php.net/manual/en/function.ucwords.php#112795) [¶](https://www.php.net/manual/en/function.ucwords.php#112795)

**12 years ago**

`Para formatar nomes em pt-br:
<?php
    function titleCase($string, $delimiters = array(" ", "-", ".", "'", "O'", "Mc"), $exceptions = array("de", "da", "dos", "das", "do", "I", "II", "III", "IV", "V", "VI"))
    {
        /*
         * Exceptions in lower case are words you don't want converted
         * Exceptions all in upper case are any words you don't want converted to title case
         *   but should be converted to upper case, e.g.:
         *   king henry viii or king henry Viii should be King Henry VIII
         */
        $string = mb_convert_case($string, MB_CASE_TITLE, "UTF-8");
        foreach ($delimiters as $dlnr => $delimiter) {
            $words = explode($delimiter, $string);
            $newwords = array();
            foreach ($words as $wordnr => $word) {
                if (in_array(mb_strtoupper($word, "UTF-8"), $exceptions)) {
                    // check exceptions list for any words that should be in upper case
                    $word = mb_strtoupper($word, "UTF-8");
                } elseif (in_array(mb_strtolower($word, "UTF-8"), $exceptions)) {
                    // check exceptions list for any words that should be in upper case
                    $word = mb_strtolower($word, "UTF-8");
                } elseif (!in_array($word, $exceptions)) {
                    // convert to uppercase (non-utf8 only)
                    $word = ucfirst($word);
                }
                array_push($newwords, $word);
            }
            $string = join($delimiter, $newwords);
       }//foreach
       return $string;
    }
?>
Usage:
<?php
    $s = 'SÃO JOÃO DOS SANTOS';
    $v = titleCase($s); // 'São João dos Santos'
?>`

[up](https://www.php.net/manual/vote-note.php?id=96179&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96179&page=function.ucwords&vote=down "Vote down!")

45


[**_jmarois at ca dot ibm dot com_**](https://www.php.net/manual/en/function.ucwords.php#96179) [¶](https://www.php.net/manual/en/function.ucwords.php#96179)

**15 years ago**

`My quick and dirty ucname (Upper Case Name) function.
<?php
//FUNCTION
function ucname($string) {
    $string =ucwords(strtolower($string));
    foreach (array('-', '\'') as $delimiter) {
      if (strpos($string, $delimiter)!==false) {
        $string =implode($delimiter, array_map('ucfirst', explode($delimiter, $string)));
      }
    }
    return $string;
}
?>
<?php
//TEST
$names =array(
'JEAN-LUC PICARD',
'MILES O\'BRIEN',
'WILLIAM RIKER',
'geordi la forge',
'bEvErly CRuSHeR'
);
foreach ($names as $name) { print ucname("{$name}\n"); }
//PRINTS:
/*
Jean-Luc Picard
Miles O'Brien
William Riker
Geordi La Forge
Beverly Crusher
*/
?>
You can add more delimiters in the for-each loop array if you want to handle more characters.`

[up](https://www.php.net/manual/vote-note.php?id=92092&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92092&page=function.ucwords&vote=down "Vote down!")

20


[**_robert at broofa dot com_**](https://www.php.net/manual/en/function.ucwords.php#92092) [¶](https://www.php.net/manual/en/function.ucwords.php#92092)

**16 years ago**

`Some recipes for switching between underscore and camelcase naming:
<?php
// underscored to upper-camelcase
// e.g. "this_method_name" -> "ThisMethodName"
preg_replace('/(?:^|_)(.?)/e',"strtoupper('$1')",$string);
// underscored to lower-camelcase
// e.g. "this_method_name" -> "thisMethodName"
preg_replace('/_(.?)/e',"strtoupper('$1')",$string);
// camelcase (lower or upper) to underscored
// e.g. "thisMethodName" -> "this_method_name"
// e.g. "ThisMethodName" -> "this_method_name"
strtolower(preg_replace('/([^A-Z])([A-Z])/', "$1_$2", $string));
?>
Of course these aren't 100% symmetric.  For example...
* this_is_a_string -> ThisIsAString -> this_is_astring
* GetURLForString -> get_urlfor_string -> GetUrlforString`

[up](https://www.php.net/manual/vote-note.php?id=76786&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76786&page=function.ucwords&vote=down "Vote down!")

4


[**_kendsnyder at gmail dot com_**](https://www.php.net/manual/en/function.ucwords.php#76786) [¶](https://www.php.net/manual/en/function.ucwords.php#76786)

**18 years ago**

`Here is a function to capitalize a last name, accounting for hyphens, apostrophes, "Mc" and "Mac":
<?php
function CapitalizeLastName($name) {
    $name = strtolower($name);
    $name = join("'", array_map('ucwords', explode("'", $name)));
    $name = join("-", array_map('ucwords', explode("-", $name)));
    $name = join("Mac", array_map('ucwords', explode("Mac", $name)));
    $name = join("Mc", array_map('ucwords', explode("Mc", $name)));
    return $name;
}
?>
I speed tested it against functions that used preg_replace() with an "e" modifier, preg_replace_callback(), and a character-by-character parsing.  Unexpectedly, this function using join(), array_map() and explode() was fastest.`

[up](https://www.php.net/manual/vote-note.php?id=80718&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80718&page=function.ucwords&vote=down "Vote down!")

3


[**_blake at goinoutwest dot com_**](https://www.php.net/manual/en/function.ucwords.php#80718) [¶](https://www.php.net/manual/en/function.ucwords.php#80718)

**17 years ago**

`Relating to the mb_ucwords() function posted by Anonymous.  In order for this to actually be multi-byte compliant, you would also need to use mb_substr() and mb_strlen() instead of substr and strlen respectively.
Here it is corrected and extended even further to allow multiple word separators and a list of exceptions to correct after title casing. It's a bit tedious and inelegant, but things frequently are when dealing with human languages.
function mb_ucwords($str) {
    $exceptions = array();
    $exceptions['Hp'] = 'HP';
    $exceptions['Ibm'] = 'IBM';
    $exceptions['Gb'] = 'GB';
    $exceptions['Mb'] = 'MB';
    $exceptions['Cd'] = 'CD';
    $exceptions['Dvd'] = 'DVD';
    $exceptions['Usb'] = 'USB';
    $exceptions['Mm'] = 'mm';
    $exceptions['Cm'] = 'cm';
    //    etc.

    $separator = array(" ","-","+");

    $str = mb_strtolower(trim($str));
    foreach($separator as $s){
        $word = explode($s, $str);
        $return = "";
        foreach ($word as $val){
            $return .= $s . mb_strtoupper($val{0}) . mb_substr($val,1,mb_strlen($val)-1);
        }
        $str = mb_substr($return, 1);
    }
    foreach($exceptions as $find=>$replace){
        if (mb_strpos($return, $find) !== false){
            $return = str_replace($find, $replace, $return);
        }
    }
    return mb_substr($return, 1);
}`

[up](https://www.php.net/manual/vote-note.php?id=106174&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106174&page=function.ucwords&vote=down "Vote down!")

11


[**_ahmet363 at gmail dot com_**](https://www.php.net/manual/en/function.ucwords.php#106174) [¶](https://www.php.net/manual/en/function.ucwords.php#106174)

**14 years ago**

`Turkish character with the ucwords function...
<?php
function ucwords_tr($gelen){
$sonuc='';
$kelimeler=explode(" ", $gelen);
foreach ($kelimeler as $kelime_duz){
    $kelime_uzunluk=strlen($kelime_duz);
    $ilk_karakter=mb_substr($kelime_duz,0,1,'UTF-8');
    if($ilk_karakter=='Ç' or $ilk_karakter=='ç'){
      $ilk_karakter='Ç';
    }elseif ($ilk_karakter=='Ğ' or $ilk_karakter=='ğ') {
      $ilk_karakter='Ğ';
    }elseif($ilk_karakter=='I' or $ilk_karakter=='ı'){
      $ilk_karakter='I';
    }elseif ($ilk_karakter=='İ' or $ilk_karakter=='i'){
      $ilk_karakter='İ';
    }elseif ($ilk_karakter=='Ö' or $ilk_karakter=='ö'){
      $ilk_karakter='Ö';
    }elseif ($ilk_karakter=='Ş' or $ilk_karakter=='ş'){
      $ilk_karakter='Ş';
    }elseif ($ilk_karakter=='Ü' or $ilk_karakter=='ü'){
      $ilk_karakter='Ü';
    }else{
      $ilk_karakter=strtoupper($ilk_karakter);
    }
    $digerleri=mb_substr($kelime_duz,1,$kelime_uzunluk,'UTF-8');
    $sonuc.=$ilk_karakter.kucuk_yap($digerleri).' ';
}
$son=trim(str_replace('  ', ' ', $sonuc));
return $son;
}
function kucuk_yap($gelen){
$gelen=str_replace('Ç', 'ç', $gelen);
$gelen=str_replace('Ğ', 'ğ', $gelen);
$gelen=str_replace('I', 'ı', $gelen);
$gelen=str_replace('İ', 'i', $gelen);
$gelen=str_replace('Ö', 'ö', $gelen);
$gelen=str_replace('Ş', 'ş', $gelen);
$gelen=str_replace('Ü', 'ü', $gelen);
$gelen=strtolower($gelen);
return $gelen;
}
echo ucwords_tr('ŞEKardi ŞEMŞİYE ĞELENÖ ÖMER'); // Şekardi Şemşiye Ğelenö Ömer
echo ucwords_tr('şEKER iMSAK şÖLEN'); // Şeker İmsak Şölen`

[up](https://www.php.net/manual/vote-note.php?id=112079&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112079&page=function.ucwords&vote=down "Vote down!")

10


[**_hrvoj3e at gmail dot com_**](https://www.php.net/manual/en/function.ucwords.php#112079) [¶](https://www.php.net/manual/en/function.ucwords.php#112079)

**12 years ago**

`UTF-8 Title Case that works for me even with hyphens involved!
$str = 'ĐaaČaa-AAAaaa, BBbb';
$str = mb_convert_case($str, MB_CASE_TITLE, "UTF-8");
echo($str): 'Đaačaa-Aaaaaa, Bbbb'`

[up](https://www.php.net/manual/vote-note.php?id=65712&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=65712&page=function.ucwords&vote=down "Vote down!")

6


[**_lev at phpfox dot com_**](https://www.php.net/manual/en/function.ucwords.php#65712) [¶](https://www.php.net/manual/en/function.ucwords.php#65712)

**19 years ago**

`In the function ucsmart() posted by ieure at php dot net on 04-Dec-2005 11:57, I found a similar problem in this function to what he found in igua's.
<?php
function ucsmart($text)
{
return preg_replace('/([^a-z]|^)([a-z])/e', '"$1".strtoupper("$2")',
                       strtolower($text));
}
?>
"igua's code adds a backslash in front of the first single quote for me. This doesn't alter the content in any way other than changing case."
Actually, it did end up changing the content for me (php 5.0.4) in the way that this function escapes a single quotation (apostrophe) in the MIDDLE of a word.
For example:
who's online?
Became:
Who\'s Online?
The fix is simple however, and merely requires fine-tuning the regular expression:
<?php
function ucsmart($text)
{
return preg_replace('/([^a-z\']|^)([a-z])/e', '"$1".strtoupper("$2")',
                       strtolower($text));
}
?>
(note: while previewing this note before adding it, I am noticing php's website is not correctly displaying the change I made as I wrote it. After the first a-z in the expression, the single quotation should be escaped... If it isn't you will get a parse error! And apoligies if my text here is colored as php code; not my fault!)
This will not escape a single quotation mark which occurs in the middle of a word... Though, you may find that might need to add other characters inside the regular expression if you use other special characters inside your words and if you get funky output.
It's a great expression though! Simple, yet very powerful. Kudos!`

[up](https://www.php.net/manual/vote-note.php?id=118926&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118926&page=function.ucwords&vote=down "Vote down!")

4


[**_almino dot melo at gmail dot com_**](https://www.php.net/manual/en/function.ucwords.php#118926) [¶](https://www.php.net/manual/en/function.ucwords.php#118926)

**9 years ago**

`ucwords for human names in Brazil.
ucwords personalizada para nomes próprios brasileiros.
<?php
    /**
     * ucwords for human names in Brazil
     * Edit from [http://php.net/manual/pt\_BR/function.ucwords.php#112795](http://php.net/manual/pt_BR/function.ucwords.php#112795)
     * @param string $str
     * @param array $delimiters
     * @param array $exceptions Exceptions are words you don't want converted
     * @return string
     */
    function name($str, $delimiters = array(
        " ",
        "-",
        ".",
        "'",
        "O'",
        "Mc",
    ), $exceptions = array(
        "de",
        "do",
        "da",
        "dos",
        "das",
    )) {
        $result = '';
        foreach ($delimiters as $delimiter) {
            # If string has a delimiter
            if (strstr($str, $delimiter)) {
                $ucfirst = array();
                # Apply ucfirst to every word
                foreach (explode($delimiter, mb_strtolower($str)) as $word) {
                    $word = mb_convert_case($word, MB_CASE_TITLE);
                    # Working with exceptions
                    if (in_array(mb_strtoupper($word), $exceptions)) {
                        $word = mb_strtoupper($word);
                    } elseif (in_array(mb_strtolower($word), $exceptions)) {
                        $word = mb_strtolower($word);
                    } elseif (preg_match('/^M{0,4}(CM|CD|D?C{0,3})(XC|XL|L?X{0,3})(IX|IV|V?I{0,3})$/', mb_strtoupper($word))) {
                        # Is roman numerals? # [http://stackoverflow.com/a/267405/437459](http://stackoverflow.com/a/267405/437459)
                        $word = mb_strtoupper($word);
                    }
                    $ucfirst[] = $word;
                }
                # string's first character uppercased
                $result = implode($delimiter, $ucfirst);
            }
        }
        return $result;
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=110002&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110002&page=function.ucwords&vote=down "Vote down!")

12


[**_Luca Borrione luca -a email -d c\_o\_m_**](https://www.php.net/manual/en/function.ucwords.php#110002) [¶](https://www.php.net/manual/en/function.ucwords.php#110002)

**13 years ago**

`Features:
- multi byte compatible
- handles multiple delimiters
<?php
function ucwords_specific ($string, $delimiters = '', $encoding = NULL)
{
    if ($encoding === NULL) { $encoding = mb_internal_encoding();}
    if (is_string($delimiters))
    {
        $delimiters =  str_split( str_replace(' ', '', $delimiters));
    }
    $delimiters_pattern1 = array();
    $delimiters_replace1 = array();
    $delimiters_pattern2 = array();
    $delimiters_replace2 = array();
    foreach ($delimiters as $delimiter)
    {
        $uniqid = uniqid();
        $delimiters_pattern1[]   = '/'. preg_quote($delimiter) .'/';
        $delimiters_replace1[]   = $delimiter.$uniqid.' ';
        $delimiters_pattern2[]   = '/'. preg_quote($delimiter.$uniqid.' ') .'/';
        $delimiters_replace2[]   = $delimiter;
    }
    // $return_string = mb_strtolower($string, $encoding);
    $return_string = $string;
    $return_string = preg_replace($delimiters_pattern1, $delimiters_replace1, $return_string);
    $words = explode(' ', $return_string);
    foreach ($words as $index => $word)
    {
        $words[$index] = mb_strtoupper(mb_substr($word, 0, 1, $encoding), $encoding).mb_substr($word, 1, mb_strlen($word, $encoding), $encoding);
    }
    $return_string = implode(' ', $words);
    $return_string = preg_replace($delimiters_pattern2, $delimiters_replace2, $return_string);
    return $return_string;
}
?>
Params:
1. string: The string being converted
2. delimiters: a string with all wanted delimiters written one after the other e.g. "-'"
3. encoding: Is the character encoding. If it is omitted, the internal character encoding value will be used.
Example Usage:
<?php
mb_internal_encoding('UTF-8');
$string = "JEAN-PAUL d'artagnan şŠ-òÀ-éÌ hello - world";
echo ucwords_specific( mb_strtolower($string, 'UTF-8'), "-'");
?>
Output:
Jean-Paul D'Artagnan Şš-Òà-Éì Hello - World`

[up](https://www.php.net/manual/vote-note.php?id=125209&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125209&page=function.ucwords&vote=down "Vote down!")

2


[**_NOSPAM dot php at my dot jrklein dot com_**](https://www.php.net/manual/en/function.ucwords.php#125209) [¶](https://www.php.net/manual/en/function.ucwords.php#125209)

**5 years ago**

`Based on code sample originally posted by "Anonymous" on 2005-12-14. The /e modifier is no longer supported by preg_replace(). Rewritten to use preg_replace_callback() instead. Tested with PHP 7.3.
The function below will standardize the capitalization on people's names, addresses, and the titles of reports and essays . Adapt the lists in "$all_uppercase" and "$all_lowercase" to suit the data that you are working with.
function ucwords_title($string, $is_name = false) {
    // Exceptions to standard case conversion
    if ($is_name) {
        $all_uppercase = '';
        $all_lowercase = 'De La|De Las|Der|Van De|Van Der|Vit De|Von|Or|And';
    } else {
        // Addresses, essay titles ... and anything else
        $all_uppercase = 'Us|Ca|Mx|Po|Rr|Se|Sw|Ne|Nw';
        $all_lowercase = 'A|And|As|By|In|Of|Or|To';
    }
    $prefixes = 'Mac|Mc';
    $suffixes = "'S";
    // Trim whitespace and convert to lowercase
    $str = strtolower(trim($string));
    // Capitalize all first letters
    $str = preg_replace_callback('/\\b(\\w)/', function ($m) {
        return strtoupper($m[1]);
    }, $str);
    if ($all_uppercase) {
        // Capitalize acronyms and initialisms (e.g. PHP)
        $str = preg_replace_callback('/\\b(' . $all_uppercase . ')\\b/', function ($m) {
            return strtoupper($m[1]);
        }, $str);
    }
    if ($all_lowercase) {
        // Decapitalize short words (e.g. and)
        if ($is_name) {
            // All occurrences will be changed to lowercase
            $str = preg_replace_callback('/\\b(' . $all_lowercase . ')\\b/', function ($m) {
                return strtolower($m[1]);
            }, $str);
        } else {
            // First and last word will not be changed to lower case (i.e. titles)
            $str = preg_replace_callback('/(?<=\\W)(' . $all_lowercase . ')(?=\\W)/', function ($m) {
                return strtolower($m[1]);
            }, $str);
        }
    }
    if ($prefixes) {
        // Capitalize letter after certain name prefixes (e.g 'Mc')
        $str = preg_replace_callback('/\\b(' . $prefixes . ')(\\w)/', function ($m) {
            return $m[1] . strtoupper($m[2]);
        }, $str);
    }
    if ($suffixes) {
        // Decapitalize certain word suffixes (e.g. 's)
        $str = preg_replace_callback('/(\\w)(' . $suffixes . ')\\b/', function ($m) {
            return $m[1] . strtolower($m[2]);
        }, $str);
    }
    return $str;
}
// A name example
print ucwords_title("MARIE-LOU VAN DER PLANCK-ST.JOHN", true);
// Output: Marie-Lou van der Planc-St.John
// A title example
print ucwords_title("to be or not to be");
// Output: "To Be or Not to Be"`

[up](https://www.php.net/manual/vote-note.php?id=86732&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86732&page=function.ucwords&vote=down "Vote down!")

4


[**_strazds at gmail dot com_**](https://www.php.net/manual/en/function.ucwords.php#86732) [¶](https://www.php.net/manual/en/function.ucwords.php#86732)

**16 years ago**

`ucwords for UTF-8 strings:
<?php
function mb_ucwords($str) {
    $str = mb_convert_case($str, MB_CASE_TITLE, "UTF-8");
    return ($str);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=74938&page=function.ucwords&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74938&page=function.ucwords&vote=down "Vote down!")

4


[**_Q1712 at online dot ms_**](https://www.php.net/manual/en/function.ucwords.php#74938) [¶](https://www.php.net/manual/en/function.ucwords.php#74938)

**18 years ago**

`ucwords() only excepts whitespace in front of a word, although some chars like '"' or '(' normally have no space between them and the following word:
<?php
$title = 'ELVIS "THE KING" PRESLEY - (LET ME BE YOUR) TEDDY BEAR';
echo ucwords(strtolower($title));
?>
prints: Elvis "the King" Presley - (let Me Be Your) Teddy Bear
To avoid this i use a small function adding and deleting blanks behind these chars, and using ucwords() in between:
<?php
function my_ucwords($string)
{
    $noletters='"([/'; //add more if u need to\
    for($i=0; $i<strlen($noletters); $i++)\
      $string = str_replace($noletters[$i], $noletters[$i].' ', $string);\
    $string=ucwords($string);\
    for($i=0; $i<strlen($noletters); $i++)\
      $string = str_replace($noletters[$i].' ', $noletters[$i], $string);\
    return $string;\
}\
$title = 'ELVIS "THE KING" PRESLEY - (LET ME BE YOUR) TEDDY BEAR';\
echo my_ucwords(strtolower($title));\
?>\
prints: Elvis "The King" Presley - (Let Me Be Your) Teddy Bear`\
\
[up](https://www.php.net/manual/vote-note.php?id=18341&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=18341&page=function.ucwords&vote=down "Vote down!")\
\
2\
\
\
[**_Anonymous_**](https://www.php.net/manual/en/function.ucwords.php#18341) [¶](https://www.php.net/manual/en/function.ucwords.php#18341)\
\
**23 years ago**\
\
`This seems to be what people want:\
function uc_all($string) {\
    $temp = preg_split('/(\W)/', $string, -1, PREG_SPLIT_DELIM_CAPTURE );\
    foreach ($temp as $key=>$word) {\
        $temp[$key] = ucfirst(strtolower($word));\
    }\
    return join ('', $temp);\
}\
[ed note: fixed the code to be correct]`\
\
[up](https://www.php.net/manual/vote-note.php?id=60064&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=60064&page=function.ucwords&vote=down "Vote down!")\
\
4\
\
\
[**_Anonymous_**](https://www.php.net/manual/en/function.ucwords.php#60064) [¶](https://www.php.net/manual/en/function.ucwords.php#60064)\
\
**19 years ago**\
\
`"ieure at php dot net", your idea is pure poetry!\
The function below will standardize the capitalization on people's names and the titles of reports and essays . You may need to adapt the lists in "$all_uppercase" and "$all_lowercase" to suit the data that you are working with.\
function my_ucwords($str, $is_name=false) {\
// exceptions to standard case conversion\
if ($is_name) {\
       $all_uppercase = '';\
       $all_lowercase = 'De La|De Las|Der|Van De|Van Der|Vit De|Von|Or|And';\
} else {\
       // addresses, essay titles ... and anything else\
       $all_uppercase = 'Po|Rr|Se|Sw|Ne|Nw';\
       $all_lowercase = 'A|And|As|By|In|Of|Or|To';\
}\
$prefixes = 'Mc';\
$suffixes = "'S";\
// captialize all first letters\
$str = preg_replace('/\\b(\\w)/e', 'strtoupper("$1")', strtolower(trim($str)));\
if ($all_uppercase) {\
       // capitalize acronymns and initialisms e.g. PHP\
       $str = preg_replace("/\\b($all_uppercase)\\b/e", 'strtoupper("$1")', $str);\
}\
if ($all_lowercase) {\
       // decapitalize short words e.g. and\
       if ($is_name) {\
           // all occurences will be changed to lowercase\
           $str = preg_replace("/\\b($all_lowercase)\\b/e", 'strtolower("$1")', $str);\
       } else {\
           // first and last word will not be changed to lower case (i.e. titles)\
           $str = preg_replace("/(?<=\\W)($all_lowercase)(?=\\W)/e", 'strtolower("$1")', $str);\
       }\
}\
if ($prefixes) {\
       // capitalize letter after certain name prefixes e.g 'Mc'\
       $str = preg_replace("/\\b($prefixes)(\\w)/e", '"$1".strtoupper("$2")', $str);\
}\
if ($suffixes) {\
       // decapitalize certain word suffixes e.g. 's\
       $str = preg_replace("/(\\w)($suffixes)\\b/e", '"$1".strtolower("$2")', $str);\
}\
return $str;\
}\
// A name example\
print my_ucwords("MARIE-LOU VAN DER PLANCK-ST.JOHN", true);\
// Output: Marie-Lou van der Planc-St.John\
// A title example\
print my_ucwords("to be or not to be");\
// Output: "To Be or Not to Be"`\
\
[up](https://www.php.net/manual/vote-note.php?id=72123&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=72123&page=function.ucwords&vote=down "Vote down!")\
\
1\
\
\
[**_barnaby ritchley at exeye dot co dot uk_**](https://www.php.net/manual/en/function.ucwords.php#72123) [¶](https://www.php.net/manual/en/function.ucwords.php#72123)\
\
**18 years ago**\
\
`A very easy way to convert to title case:\
function titleCase($string)\
     {\
     return ucwords(strtolower($string));\
     }\
$myString = "SOME TEXT";\
echo titleCase($myString);\
//will print, "My Text"`\
\
[up](https://www.php.net/manual/vote-note.php?id=66845&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=66845&page=function.ucwords&vote=down "Vote down!")\
\
1\
\
\
[**_Ismet Togay_**](https://www.php.net/manual/en/function.ucwords.php#66845) [¶](https://www.php.net/manual/en/function.ucwords.php#66845)\
\
**19 years ago**\
\
`Response to arif:\
We do not need that long functions. In order to make ucwords() worked properly in Turkish words that contain speacial characters, we can use the following command in our php codes:\
setlocale(LC_ALL, 'tr_TR');\
This will set locale to Turkish.`\
\
[up](https://www.php.net/manual/vote-note.php?id=125047&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=125047&page=function.ucwords&vote=down "Vote down!")\
\
0\
\
\
[**_ganzales at inbox dot ru_**](https://www.php.net/manual/en/function.ucwords.php#125047) [¶](https://www.php.net/manual/en/function.ucwords.php#125047)\
\
**5 years ago**\
\
`<?php\
function mb_ucwords($string, $delimiter = ' (-"[') {\
    $result = $upper = '';\
    for ($i = 0; $i < mb_strlen($string); $i++) {\
        $letter = mb_substr($string, $i, 1);\
        $result .= $upper || $i == 0 ? mb_convert_case($letter, MB_CASE_TITLE) : $letter;\
        $upper = ($i + 1) < mb_strlen($string) && mb_strpos($delimiter, $letter) !== false ? 1 : 0;\
    }\
    return $result;\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=117270&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=117270&page=function.ucwords&vote=down "Vote down!")\
\
0\
\
\
[**_Alex Milkovskyi_**](https://www.php.net/manual/en/function.ucwords.php#117270) [¶](https://www.php.net/manual/en/function.ucwords.php#117270)\
\
**10 years ago**\
\
`Convert string to in camel-case, useful for class name patterns:\
<?php\
/**\
* Convert string to in camel-case, useful for class name patterns.\
*\
* @param $string\
*   Target string.\
*\
* @return string\
*   Camel-case string.\
*/\
function toCamelCase($string){\
    $string = str_replace('-', ' ', $string);\
    $string = str_replace('_', ' ', $string);\
    $string = ucwords(strtolower($string));\
    $string = str_replace(' ', '', $string);\
    return $string;\
}\
?>\
Example:\
toCamelCase(make_mE camel-case pLEase) will return:\
MakeMeCamelCasePlease`\
\
[up](https://www.php.net/manual/vote-note.php?id=85372&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=85372&page=function.ucwords&vote=down "Vote down!")\
\
1\
\
\
[**_Alex_**](https://www.php.net/manual/en/function.ucwords.php#85372) [¶](https://www.php.net/manual/en/function.ucwords.php#85372)\
\
**17 years ago**\
\
`A modified sentenceNormalizer by gregomm\
\
Features:\
1- Removes duplicated question marks, exclamations and periods\
2- Capitalize first letter of a sentence.\
3- Split sentences not only with "." but also with "?" and "!"\
4- Puts a white space at the end of each sentence\
5- Retains newlines\
--removed from orginal function--\
undestand the meaning of "¡" and "¿" in languages like spanish.\
undestand the htmlentitity version of this simbols.\
--removed from orginal function--\
<?php\
function sentenceNormalizer($sentence_split) {\
    $sentence_split = preg_replace(array('/[!]+/','/[?]+/','/[.]+/'),\
                                   array('!','?','.'),$sentence_split);\
\
    $textbad = preg_split("/(\!|\.|\?|\n)/", $sentence_split,-1,PREG_SPLIT_DELIM_CAPTURE);\
    $newtext = array();\
    $count = sizeof($textbad);\
\
    foreach($textbad as $key => $string) {\
        if (!empty($string)) {\
            $text = trim($string, ' ');\
            $size = strlen($text);\
\
            if ($size > 1){\
                $newtext[] = ucfirst(strtolower($text));\
            }\
                elseif ($size == 1) {\
                    $newtext[] = ($text == "\n") ? $text : $text . ' ';\
                }\
        }\
    }\
\
    return implode($newtext);\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=123101&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=123101&page=function.ucwords&vote=down "Vote down!")\
\
 -1\
\
\
[**_@manzoorwanijk_**](https://www.php.net/manual/en/function.ucwords.php#123101) [¶](https://www.php.net/manual/en/function.ucwords.php#123101)\
\
**7 years ago**\
\
`for PHP < 5.4.32 with $delimiters\
function _ucwords( $str, $delimiters = " \t\r\n\f\v" ) {\
    $delims = preg_split( '//u', $delimiters, -1, PREG_SPLIT_NO_EMPTY );\
    foreach ( $delims as $delim ) {\
\
        if ( false !== strpos( $str, $delim ) ) {\
            $str = implode( $delim, array_map( 'ucfirst', explode( $delim, $str ) ) );\
        }\
    }\
    return $str;\
}`\
\
[up](https://www.php.net/manual/vote-note.php?id=107701&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=107701&page=function.ucwords&vote=down "Vote down!")\
\
0\
\
\
[**_qeremy \[atta\] gmail \[dotta\] com_**](https://www.php.net/manual/en/function.ucwords.php#107701) [¶](https://www.php.net/manual/en/function.ucwords.php#107701)\
\
**13 years ago**\
\
`A proper Turkish solution;\
<?php\
function ucfirst_turkish($str) {\
    $tmp = preg_split("//u", $str, 2, PREG_SPLIT_NO_EMPTY);\
    return mb_convert_case(\
        str_replace("i", "İ", $tmp[0]), MB_CASE_TITLE, "UTF-8").\
        $tmp[1];\
}\
function ucwords_turkish($str) {\
    return preg_replace("/(\\w+)/ue", "ucfirst_turkish('\\\\1').'$2'", $str);\
}\
$str = "iyilik güzelLİK şeker ";\
echo ucwords($str) ."\\n";   // Iyilik GüzelLİK şeker\
echo ucwords_turkish($str); // İyilik GüzelLİK Şeker\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=106598&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=106598&page=function.ucwords&vote=down "Vote down!")\
\
0\
\
\
[**_haijerome at gmail dot com_**](https://www.php.net/manual/en/function.ucwords.php#106598) [¶](https://www.php.net/manual/en/function.ucwords.php#106598)\
\
**13 years ago**\
\
`Thanks a lot brother.\
I tested it with a few variations. It works perfectly. Its really great and simple usage of the existing functions. It would be glad to all PHP folks and good to PHP if these kind of functions will be in PHP library on upcoming releases.\
<?php\
$name1 = "mark-yves robert";\
$name2 = "mark-yves robert-bryan";\
echo '<br/>Name 1 (mark-yves robert) =>'.\
ucwordspecific($name1,'-'); //returns Mark-Yves Robert\
echo '<br/>Name 2 (mark-yves robert-bryan)\
=>'.ucwordspecific($name2,'-');\
//returns Mark-Yves Robert-Bryan\
function ucwordspecific($str,$delimiter){\
$delimiter_space = '- ';\
return str_replace($delimiter_space,$delimiter,ucwords\
(str_replace($delimiter,$delimiter_space,$str)));\
}\
?>\
Proud to be a PHP enthusiast always :-)`\
\
[up](https://www.php.net/manual/vote-note.php?id=90521&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=90521&page=function.ucwords&vote=down "Vote down!")\
\
0\
\
\
[**_Greg S_**](https://www.php.net/manual/en/function.ucwords.php#90521) [¶](https://www.php.net/manual/en/function.ucwords.php#90521)\
\
**16 years ago**\
\
`I did the same thing as Catalin, but for French names.\
Here's what I'm doing :\
For each word (not considering the single-quote as a word boundary character) :\
- Put the word in lower case\
- If the word is "de", return, else, put the first letter in upper-case\
- See if the second character of the word is a single-quote\
- Yes ? Put the next char in upper case\
- And if the char before the single quote is D, put it back to lower case (-> d)\
This complies with the French rules for capitalization in names.\
Sample results :\
-d'Afoo Bar\
-de Foo Bar\
-O'Foo Bar\
-Foo'bar\
<?php\
function my_ucwords($s) {\
        $s = preg_replace_callback("/(\b[\w|']+\b)/s", fixcase_callback, $s);\
\
        return $s;\
\
    }\
\
    function fixcase_callback($word) {\
        $word = $word[1];\
\
        $word = strtolower($word);\
\
        if($word == "de")\
            return $word;\
\
        $word = ucfirst($word);\
\
        if(substr($word,1,1) == "'") {\
            if(substr($word,0,1) == "D") {\
                $word = strtolower($word);\
            }\
            $next = substr($word,2,1);\
            $next = strtoupper($next);\
            $word = substr_replace($word, $next, 2, 1);\
        }\
\
        return $word;\
    }\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=27537&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=27537&page=function.ucwords&vote=down "Vote down!")\
\
0\
\
\
[**_deepdene at email dot com_**](https://www.php.net/manual/en/function.ucwords.php#27537) [¶](https://www.php.net/manual/en/function.ucwords.php#27537)\
\
**22 years ago**\
\
`A function knowing about name case (i.e. caps on McDonald etc)\
function name_case($name)\
{\
    $newname = strtoupper($name[0]);\
    for ($i=1; $i < strlen($name); $i++)\
    {\
        $subed = substr($name, $i, 1);\
        if (((ord($subed) > 64) && (ord($subed) < 123)) ||\
            ((ord($subed) > 48) && (ord($subed) < 58)))\
        {\
            $word_check = substr($name, $i - 2, 2);\
            if (!strcasecmp($word_check, 'Mc') || !strcasecmp($word_check, "O'"))\
            {\
                $newname .= strtoupper($subed);\
            }\
            else if ($break)\
            {\
\
                $newname .= strtoupper($subed);\
            }\
            else\
            {\
                $newname .= strtolower($subed);\
            }\
             $break=0;\
        }\
        else\
        {\
            // not a letter - a boundary\
             $newname .= $subed;\
            $break=1;\
        }\
    }\
    return $newname;\
}`\
\
[up](https://www.php.net/manual/vote-note.php?id=12063&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=12063&page=function.ucwords&vote=down "Vote down!")\
\
0\
\
\
[**_neil at no-spam-ents24 dot com_**](https://www.php.net/manual/en/function.ucwords.php#12063) [¶](https://www.php.net/manual/en/function.ucwords.php#12063)\
\
**24 years ago**\
\
`The code posted above by Joerg Krause only works for a string which ends with one of the delimiters. A possible fix is:\
<?php\
$text = "What?No delimiters,shit happens here.this solves all problems.";\
preg_match_all("/(\w+[,. ?])+/U", $text, $words);\
preg_match("/(\w+)$/", $text, $lastword);\
$words[0][] = $lastword;\
foreach($words[0] as $part) $uwords[] = ucfirst($part);\
$text = implode("", $uwords);\
echo $text;\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=116729&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=116729&page=function.ucwords&vote=down "Vote down!")\
\
 -1\
\
\
[**_Florian_**](https://www.php.net/manual/en/function.ucwords.php#116729) [¶](https://www.php.net/manual/en/function.ucwords.php#116729)\
\
**10 years ago**\
\
`to convert first letters in a firstname like: "jean-pierre" to "Jean-Pierre":\
I simply replace the '-' with a vertical tabulation, because the ucwords() function replace the letter just after it.\
so, I use the sentence:\
$result=str_replace(chr(11),'-',ucwords(strtolower(str_replace('-',chr(11),$firstname))));`\
\
[up](https://www.php.net/manual/vote-note.php?id=117918&page=function.ucwords&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=117918&page=function.ucwords&vote=down "Vote down!")\
\
 -2\
\
\
[**_Lech_**](https://www.php.net/manual/en/function.ucwords.php#117918) [¶](https://www.php.net/manual/en/function.ucwords.php#117918)\
\
**10 years ago**\
\
`This will correct capitalisation in names taking note of special capitalisation for Mc..., Mac..., and O'... Other special cases, of which I am not aware, can be added easily.\
This is just a slight improvement on "deepdene at email dot com"'s name_case function... Thank you for original function.\
<?php\
function name_case($name) {\
    if( !$name ) return $name;\
    $newname = strtoupper($name[0]);\
    $break = false;\
    for( $i=1; $i<strlen($name); ++$i ) {\
      $subed = substr($name, $i, 1);\
      if( ord($subed) > 64 && ord($subed) < 123 || ord($subed) > 48 && ord($subed) < 58 ) {\
        if( $break ) {\
          $newname .= strtoupper($subed);\
        }\
        elseif( $i > 1 && in_array(substr($newname, $i-2, 2), array('Mc', 'O\'')) || $i > 2 && in_array(substr($newname, $i-3, 3), array('Mac')) ) {\
          $newname .= strtoupper($subed);\
        }\
        else {\
          $newname .= strtolower($subed);\
        }\
        $break = false;\
      }\
      else {\
        // not a letter - a boundary\
        $newname .= $subed;\
        $break = true;\
      }\
    }\
    return $newname;\
?>`\
\
[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ucwords&repo=en&redirect=https://www.php.net/manual/en/function.ucwords.php)\
\
![To Top](https://www.php.net/images/to-top@2x.png)\
\
`↑` and `↓` to navigate •\
`Enter` to select •\
`Esc` to close\
\
\
Press `Enter` without\
selection to search using Google