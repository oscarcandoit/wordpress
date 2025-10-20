---
url: https://www.php.net/manual/en/function.htmlentities.php
scraped_at: 2025-10-20T02:38:47.161Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# htmlentities

(PHP 4, PHP 5, PHP 7, PHP 8)

htmlentities — Convert all applicable characters to HTML entities

### Description [¶](https://www.php.net/manual/en/function.htmlentities.php\#refsect1-function.htmlentities-description)

**htmlentities**(

[string](https://www.php.net/manual/en/language.types.string.php) `$string`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$flags` = ENT\_QUOTES \| ENT\_SUBSTITUTE \| ENT\_HTML401,

[?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$encoding` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$double_encode` = **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**

): [string](https://www.php.net/manual/en/language.types.string.php)

This function is identical to [htmlspecialchars()](https://www.php.net/manual/en/function.htmlspecialchars.php) in all
ways, except with **htmlentities()**, all characters which
have HTML character entity equivalents are translated into these entities.
The [get\_html\_translation\_table()](https://www.php.net/manual/en/function.get-html-translation-table.php) function can be used
to return the translation table used dependent upon the provided
`flags` constants.


If you want to decode instead (the reverse) you can use
[html\_entity\_decode()](https://www.php.net/manual/en/function.html-entity-decode.php).


### Parameters [¶](https://www.php.net/manual/en/function.htmlentities.php\#refsect1-function.htmlentities-parameters)

`string`

The input string.


`flags`

A bitmask of one or more of the following flags, which specify how to handle quotes,
invalid code unit sequences and the used document type. The default is
`ENT_QUOTES | ENT_SUBSTITUTE | ENT_HTML401`.


| Constant Name | Description |
| --- | --- |
| **`[ENT\_COMPAT](https://www.php.net/manual/en/string.constants.php#constant.ent-compat)`** | Will convert double-quotes and leave single-quotes alone. |
| **`[ENT\_QUOTES](https://www.php.net/manual/en/string.constants.php#constant.ent-quotes)`** | Will convert both double and single quotes. |
| **`[ENT\_NOQUOTES](https://www.php.net/manual/en/string.constants.php#constant.ent-noquotes)`** | Will leave both double and single quotes unconverted. |
| **`[ENT\_IGNORE](https://www.php.net/manual/en/string.constants.php#constant.ent-ignore)`** | Silently discard invalid code unit sequences instead of returning<br> an empty string. Using this flag is discouraged as it<br> [» may have security implications](http://unicode.org/reports/tr36/#Deletion_of_Noncharacters). |
| **`[ENT\_SUBSTITUTE](https://www.php.net/manual/en/string.constants.php#constant.ent-substitute)`** | Replace invalid code unit sequences with a Unicode Replacement Character<br> U+FFFD (UTF-8) or &#FFFD; (otherwise) instead of returning an empty string. |
| **`[ENT\_DISALLOWED](https://www.php.net/manual/en/string.constants.php#constant.ent-disallowed)`** | Replace invalid code points for the given document type with a<br> Unicode Replacement Character U+FFFD (UTF-8) or &#FFFD;<br> (otherwise) instead of leaving them as is. This may be useful, for<br> instance, to ensure the well-formedness of XML documents with<br> embedded external content. |
| **`[ENT\_HTML401](https://www.php.net/manual/en/string.constants.php#constant.ent-html401)`** | Handle code as HTML 4.01. |
| **`[ENT\_XML1](https://www.php.net/manual/en/string.constants.php#constant.ent-xml1)`** | Handle code as XML 1. |
| **`[ENT\_XHTML](https://www.php.net/manual/en/string.constants.php#constant.ent-xhtml)`** | Handle code as XHTML. |
| **`[ENT\_HTML5](https://www.php.net/manual/en/string.constants.php#constant.ent-html5)`** | Handle code as HTML 5. |

**Available `flags` constants**`encoding`

An optional argument defining the encoding used when converting characters.


If omitted, `encoding` defaults to the value of the
[default\_charset](https://www.php.net/manual/en/ini.core.php#ini.default-charset) configuration
option.


Although this argument is technically optional, you are highly encouraged to
specify the correct value for your code
if the [default\_charset](https://www.php.net/manual/en/ini.core.php#ini.default-charset)
configuration option may be set incorrectly for the given input.


The following character sets are supported:


| Charset | Aliases | Description |
| --- | --- | --- |
| ISO-8859-1 | ISO8859-1 | Western European, Latin-1. |
| ISO-8859-5 | ISO8859-5 | Little used cyrillic charset (Latin/Cyrillic). |
| ISO-8859-15 | ISO8859-15 | Western European, Latin-9. Adds the Euro sign, French and Finnish<br> letters missing in Latin-1 (ISO-8859-1). |
| UTF-8 |  | ASCII compatible multi-byte 8-bit Unicode. |
| cp866 | ibm866, 866 | DOS-specific Cyrillic charset. |
| cp1251 | Windows-1251, win-1251, 1251 | Windows-specific Cyrillic charset. |
| cp1252 | Windows-1252, 1252 | Windows specific charset for Western European. |
| KOI8-R | koi8-ru, koi8r | Russian. |
| BIG5 | 950 | Traditional Chinese, mainly used in Taiwan. |
| GB2312 | 936 | Simplified Chinese, national standard character set. |
| BIG5-HKSCS |  | Big5 with Hong Kong extensions, Traditional Chinese. |
| Shift\_JIS | SJIS, SJIS-win, cp932, 932 | Japanese |
| EUC-JP | EUCJP, eucJP-win | Japanese |
| MacRoman |  | Charset that was used by Mac OS. |
| `''` |  | An empty string activates detection from script encoding (Zend multibyte),<br> [default\_charset](https://www.php.net/manual/en/ini.core.php#ini.default-charset) and current<br> locale (see [nl\_langinfo()](https://www.php.net/manual/en/function.nl-langinfo.php) and<br> [setlocale()](https://www.php.net/manual/en/function.setlocale.php)), in this order. Not recommended. |

**Supported charsets**

> **Note**:
>
> Any other character sets are not recognized. The default encoding will be
> used instead and a warning will be emitted.

`double_encode`

When `double_encode` is turned off PHP will not
encode existing html entities. The default is to convert everything.


### Return Values [¶](https://www.php.net/manual/en/function.htmlentities.php\#refsect1-function.htmlentities-returnvalues)

Returns the encoded string.


If the input `string` contains an invalid code unit
sequence within the given `encoding` an empty string
will be returned, unless either the **`[ENT\_IGNORE](https://www.php.net/manual/en/string.constants.php#constant.ent-ignore)`** or
**`[ENT\_SUBSTITUTE](https://www.php.net/manual/en/string.constants.php#constant.ent-substitute)`** flags are set.


### Changelog [¶](https://www.php.net/manual/en/function.htmlentities.php\#refsect1-function.htmlentities-changelog)

| Version | Description |
| --- | --- |
| 8.1.0 | `flags` changed from **`[ENT\_COMPAT](https://www.php.net/manual/en/string.constants.php#constant.ent-compat)`** to **`[ENT\_QUOTES](https://www.php.net/manual/en/string.constants.php#constant.ent-quotes)`** \| **`[ENT\_SUBSTITUTE](https://www.php.net/manual/en/string.constants.php#constant.ent-substitute)`** \| **`[ENT\_HTML401](https://www.php.net/manual/en/string.constants.php#constant.ent-html401)`**. |
| 8.0.0 | `encoding` is nullable now. |

### Examples [¶](https://www.php.net/manual/en/function.htmlentities.php\#refsect1-function.htmlentities-examples)

**Example #1 A **htmlentities()** example**

`<?php
$str = "A 'quote' is <b>bold</b>";
echo htmlentities($str);
echo "\n\n";
echo htmlentities($str, ENT_COMPAT);
?>`

Run code

The above example will output:

```
A &#039;quote&#039; is &lt;b&gt;bold&lt;/b&gt;

A 'quote' is &lt;b&gt;bold&lt;/b&gt
```

**Example #2 Usage of `[ENT\_IGNORE](https://www.php.net/manual/en/string.constants.php#constant.ent-ignore)`**

`<?php
$str = "\x8F!!!";
// Outputs an empty string
echo htmlentities($str, ENT_QUOTES, "UTF-8");
// Outputs "!!!"
echo htmlentities($str, ENT_QUOTES | ENT_IGNORE, "UTF-8");
?>`

Run code

### See Also [¶](https://www.php.net/manual/en/function.htmlentities.php\#refsect1-function.htmlentities-seealso)

- [html\_entity\_decode()](https://www.php.net/manual/en/function.html-entity-decode.php) \- Convert HTML entities to their corresponding characters
- [get\_html\_translation\_table()](https://www.php.net/manual/en/function.get-html-translation-table.php) \- Returns the translation table used by htmlspecialchars and htmlentities
- [htmlspecialchars()](https://www.php.net/manual/en/function.htmlspecialchars.php) \- Convert special characters to HTML entities
- [nl2br()](https://www.php.net/manual/en/function.nl2br.php) \- Inserts HTML line breaks before all newlines in a string
- [urlencode()](https://www.php.net/manual/en/function.urlencode.php) \- URL-encodes string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/htmlentities.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.htmlentities%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.htmlentities&repo=en&redirect=https://www.php.net/manual/en/function.htmlentities.php)

### User Contributed Notes 22 notes

[up](https://www.php.net/manual/vote-note.php?id=99896&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99896&page=function.htmlentities&vote=down "Vote down!")

166


[**_Sijmen Ruwhof_**](https://www.php.net/manual/en/function.htmlentities.php#99896) [¶](https://www.php.net/manual/en/function.htmlentities.php#99896)

**15 years ago**

`An important note below about using this function to secure your application against Cross Site Scripting (XSS) vulnerabilities.
When printing user input in an attribute of an HTML tag, the default configuration of htmlEntities() doesn't protect you against XSS, when using single quotes to define the border of the tag's attribute-value. XSS is then possible by injecting a single quote:
<?php
$_GET['a'] = "#000' onload='alert(document.cookie)";
?>
XSS possible (insecure):
<?php
$href = htmlEntities($_GET['a']);
print "<body bgcolor='$href'>"; # results in: <body bgcolor='#000' onload='alert(document.cookie)'>
?>
Use the 'ENT_QUOTES' quote style option, to ensure no XSS is possible and your application is secure:
<?php
$href = htmlEntities($_GET['a'], ENT_QUOTES);
print "<body bgcolor='$href'>"; # results in: <body bgcolor='#000&#039; onload=&#039;alert(document.cookie)'>
?>
The 'ENT_QUOTES' option doesn't protect you against javascript evaluation in certain tag's attributes, like the 'href' attribute of the 'a' tag. When clicked on the link below, the given JavaScript will get executed:
<?php
$_GET['a'] = 'javascript:alert(document.cookie)';
$href = htmlEntities($_GET['a'], ENT_QUOTES);
print "<a href='$href'>link</a>"; # results in: <a href='javascript:alert(document.cookie)'>link</a>
?>`

[up](https://www.php.net/manual/vote-note.php?id=127026&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127026&page=function.htmlentities&vote=down "Vote down!")

6


[**_j2teamnnl at gmail dot com_**](https://www.php.net/manual/en/function.htmlentities.php#127026) [¶](https://www.php.net/manual/en/function.htmlentities.php#127026)

**3 years ago**

`The answer above is not correct for multiple languages like France
I had correct it
function xml_entities($strIn)
    {
        if (is_numeric($strIn)) {
            return $strIn;
        }
        $strOut = null;
        $arrStr = mb_str_split($strIn);
        foreach ($arrStr as $char) {
            $ord = mb_ord($char);
            if (($ord > 0 && $ord < 32) || ($ord >= 127)) {
                $strOut .= "&amp;#{$ord};";
            }
            else {
                switch ($char) {
                    case '<':
                        $strOut .= '&lt;';
                        break;
                    case '>':
                        $strOut .= '&gt;';
                        break;
                    case '&':
                        $strOut .= '&amp;';
                        break;
                    case '"':
                        $strOut .= '&quot;';
                        break;
                    default:
                        $strOut .= $char;
                }
            }
        }
        return $strOut;
    }`

[up](https://www.php.net/manual/vote-note.php?id=73708&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73708&page=function.htmlentities&vote=down "Vote down!")

27


[**_q (dot) rendeiro (at) gmail (dot) com_**](https://www.php.net/manual/en/function.htmlentities.php#73708) [¶](https://www.php.net/manual/en/function.htmlentities.php#73708)

**18 years ago**

`I've seen lots of functions to convert all the entities, but I needed to do a fulltext search in a db field that had named entities instead of numeric entities (edited by tinymce), so I searched the tinymce source and found a string with the value->entity mapping. So, i wrote the following function to encode the user's query with named entities.
The string I used is different of the original, because i didn't want to convert ' or ". The string is too long, so I had to cut it. To get the original check TinyMCE source and search for nbsp or other entity ;)
<?php
$entities_unmatched = explode(',', '160,nbsp,161,iexcl,162,cent, [...] ');
$even = 1;
foreach($entities_unmatched as $c) {
    if($even) {
        $ord = $c;
    } else {
        $entities_table[$ord] = $c;
    }
    $even = 1 - $even;
}
function encode_named_entities($str) {
    global $entities_table;

    $encoded_str = '';
    for($i = 0; $i < strlen($str); $i++) {
        $ent = @$entities_table[ord($str{$i})];
        if($ent) {
            $encoded_str .= "&$ent;";
        } else {
            $encoded_str .= $str{$i};
        }
    }
    return $encoded_str;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=123190&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123190&page=function.htmlentities&vote=down "Vote down!")

6


[**_2962051004 at qq dot com_**](https://www.php.net/manual/en/function.htmlentities.php#123190) [¶](https://www.php.net/manual/en/function.htmlentities.php#123190)

**7 years ago**

`<?php
/**
* 将中文转为Html实体
* Convert Chinese in HTML to entity
* Author QiangGe
* Mail 2962051004@qq.com
*
*/
$str = <<<EOT
你好 world
EOT;
function ChineseToEntity($str) {
return preg_replace_callback(
        '/[\x{4e00}-\x{9fa5}]/u', // utf-8
        // '/[\x7f-\xff]+/', // if gb2312
        function ($matches) {
            $json = json_encode(array($matches[0]));
            preg_match('/\[\"(.*)\"\]/', $json, $arr);
            /*
             * 通过json_encode函数将中文转为unicode
             * 然后用正则取出unicode
             * Turn the Chinese into Unicode through the json_encode function, then extract Unicode from regular.
             * I think this idea is seamless.
            */
            return '&#x'. str_replace('\\u', '', $arr[1]). ';';
        }, $str
);
}
echo ChineseToEntity($str);
// &#x4f60;&#x597d; world`

[up](https://www.php.net/manual/vote-note.php?id=70964&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70964&page=function.htmlentities&vote=down "Vote down!")

14


[**_realcj at g mail dt com_**](https://www.php.net/manual/en/function.htmlentities.php#70964) [¶](https://www.php.net/manual/en/function.htmlentities.php#70964)

**18 years ago**

`If you are building a loadvars page for Flash and have problems with special chars such as " & ", " ' " etc, you should escape them for flash:
Try trace(escape("&")); in flash' actionscript to see the escape code for &;
% = %25
& = %26
' = %27
<?php
function flashentities($string){
return str_replace(array("&","'"),array("%26","%27"),$string);
}
?>
Those are the two that concerned me. YMMV.`

[up](https://www.php.net/manual/vote-note.php?id=97215&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=97215&page=function.htmlentities&vote=down "Vote down!")

17


[**_phil at lavin dot me dot uk_**](https://www.php.net/manual/en/function.htmlentities.php#97215) [¶](https://www.php.net/manual/en/function.htmlentities.php#97215)

**15 years ago**

`The following will make a string completely safe for XML:
<?php
function philsXMLClean($strin) {
        $strout = null;
        for ($i = 0; $i < strlen($strin); $i++) {
                $ord = ord($strin[$i]);
                if (($ord > 0 && $ord < 32) || ($ord >= 127)) {
                        $strout .= "&amp;#{$ord};";
                }
                else {
                        switch ($strin[$i]) {
                                case '<':
                                        $strout .= '&lt;';
                                        break;
                                case '>':
                                        $strout .= '&gt;';
                                        break;
                                case '&':
                                        $strout .= '&amp;';
                                        break;
                                case '"':
                                        $strout .= '&quot;';
                                        break;
                                default:
                                        $strout .= $strin[$i];
                        }
                }
        }
        return $strout;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=114041&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114041&page=function.htmlentities&vote=down "Vote down!")

12


[**_hajo-p_**](https://www.php.net/manual/en/function.htmlentities.php#114041) [¶](https://www.php.net/manual/en/function.htmlentities.php#114041)

**11 years ago**

`The flag ENT_HTML5 also strips newline chars like \n with htmlentities while htmlspecialchars is not affected by that.
If you want to use nl2br on that string afterwards you might end up searching the problem like i did. This does not apply to other flags like e.g. ENT_XHTML which confused me.
Tested this with PHP 5.4 / 5.5 / 5.6-dev with same results, so it seems that this is an intended "feature".`

[up](https://www.php.net/manual/vote-note.php?id=108222&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=108222&page=function.htmlentities&vote=down "Vote down!")

14


[**_ustimenko dot alexander at gmail dot com_**](https://www.php.net/manual/en/function.htmlentities.php#108222) [¶](https://www.php.net/manual/en/function.htmlentities.php#108222)

**13 years ago**

`For those Spanish (and not only) folks, that want their national letters back after htmlentities :)
<?php
protected function _decodeAccented($encodedValue, $options = array()) {
    $options += array(
        'quote'     => ENT_NOQUOTES,
        'encoding'  => 'UTF-8',
    );
    return preg_replace_callback(
        '/&\w(acute|uml|tilde);/',
        create_function(
            '$m',
            'return html_entity_decode($m[0], ' . $options['quote'] . ', "' .
            $options['encoding'] . '");'
        ),
        $encodedValue
    );
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=106929&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106929&page=function.htmlentities&vote=down "Vote down!")

12


[**_wd at NOSPAMwd dot it_**](https://www.php.net/manual/en/function.htmlentities.php#106929) [¶](https://www.php.net/manual/en/function.htmlentities.php#106929)

**13 years ago**

`Hi there,
after several and several tests, I figured out that dot:
- htmlentities() function remove characters like "à","è",etc when you specify a flag and a charset
- htmlentities() function DOES NOT remove characters like those above when you DO NOT specify anything
So, let's assume that..
<?php
$str = "Hèèèllooo";
$res_1 = htmlentities($str, ENT_QUOTES, "UTF-8");
$res_2 = htmlentities($str);
echo var_dump($res_1); // Result: string '' (length=0)
echo var_dump($res_2); // string 'H&egrave;&egrave;&egrave;llooo' (length=30)
?>
I used this for a textarea content for comments. Anyway, note that using the "$res_2" form the function will leave unconverted single/double quotes. At this point you should use str_replace() function to perform the characters but be careful because..
<?php
$str = "'Hèèèllooo'";
$res_2 = str_replace("'","&#039;",$str);
$res_2 = htmlentities($str);
echo var_dump($res_2); // string '&amp;#039;H&egrave;&egrave;&egrave;llooo&amp;#039;'
$res_3 = htmlentities($str);
$res_3 = str_replace("'","&#039;",$res_3);
echo var_dump($res_3); // string '&#039;H&egrave;&egrave;&egrave;llooo&#039;' --> Nice
?>
Hope it will helps you.
Regards,
W.D.`

[up](https://www.php.net/manual/vote-note.php?id=28197&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=28197&page=function.htmlentities&vote=down "Vote down!")

7


[**_Bassie (:_**](https://www.php.net/manual/en/function.htmlentities.php#28197) [¶](https://www.php.net/manual/en/function.htmlentities.php#28197)

**22 years ago**

`Note that you'll have use htmlentities() before any other function who'll edit text like nl2br().
If you use nl2br() first, the htmlentities() function will change < br > to &lt;br&gt;.`

[up](https://www.php.net/manual/vote-note.php?id=107985&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107985&page=function.htmlentities&vote=down "Vote down!")

14


[**_n at erui dot eu_**](https://www.php.net/manual/en/function.htmlentities.php#107985) [¶](https://www.php.net/manual/en/function.htmlentities.php#107985)

**13 years ago**

`html entities does not encode all unicode characters. It encodes what it can [all of latin1], and the others slip through. &#1033; is the nasty I use. I have searched for a function which encodes everything, but in the end I wrote this. This is as simple as I can get it. Consult an ansii table to custom include/omit chars you want/don't. I'm sure it's not that fast.
// Unicode-proof htmlentities.
// Returns 'normal' chars as chars and weirdos as numeric html entites.
function superentities( $str ){
    // get rid of existing entities else double-escape
    $str = html_entity_decode(stripslashes($str),ENT_QUOTES,'UTF-8');
    $ar = preg_split('/(?<!^)(?!$)/u', $str );  // return array of every multi-byte character
    foreach ($ar as $c){
        $o = ord($c);
        if ( (strlen($c) > 1) || /* multi-byte [unicode] */
            ($o <32 || $o > 126) || /* <- control / latin weirdos -> */
            ($o >33 && $o < 40) ||/* quotes + ambersand */
            ($o >59 && $o < 63) /* html */
        ) {
            // convert to numeric entity
            $c = mb_encode_numericentity($c,array (0x0, 0xffff, 0, 0xffff), 'UTF-8');
        }
        $str2 .= $c;
    }
    return $str2;
}`

[up](https://www.php.net/manual/vote-note.php?id=104288&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104288&page=function.htmlentities&vote=down "Vote down!")

9


[**_Waygood_**](https://www.php.net/manual/en/function.htmlentities.php#104288) [¶](https://www.php.net/manual/en/function.htmlentities.php#104288)

**14 years ago**

`When putting values inside comment tags <!-- --> you should replace -- with &#45;&#45; too, as this would end your tag and show the rest of the comment.`

[up](https://www.php.net/manual/vote-note.php?id=103486&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103486&page=function.htmlentities&vote=down "Vote down!")

8


[**_robin at robinwinslow dot co dot uk_**](https://www.php.net/manual/en/function.htmlentities.php#103486) [¶](https://www.php.net/manual/en/function.htmlentities.php#103486)

**14 years ago**

`htmlentities seems to have changed at some point between version 5.1.6 and 5.3.3, such that it now returns an empty string for anything containing a pound sign:
$ php -v
PHP 5.1.6 (cli) (built: May 22 2008 09:08:44)
$ php -r "echo htmlentities('£hello', null, 'utf-8');"
&pound;hello
$
$ php -v
PHP 5.3.3 (cli) (built: Aug 19 2010 12:07:49)
$ php -r "echo htmlentities('£hello', null, 'utf-8');"
$
(Returns an empty string the second time)
Just a heads up.`

[up](https://www.php.net/manual/vote-note.php?id=102621&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=102621&page=function.htmlentities&vote=down "Vote down!")

6


[**_admin at wapforum dot rs_**](https://www.php.net/manual/en/function.htmlentities.php#102621) [¶](https://www.php.net/manual/en/function.htmlentities.php#102621)

**14 years ago**

`A useful little function to convert the symbols in the different inputs.
<?php
function ConvertSimbols($var, $ConvertQuotes = 0) {
if ($ConvertQuotes > 0) {
$var = htmlentities($var, ENT_NOQUOTES, 'UTF-8');
$var = str_replace('\"', '', $var);
$var = str_replace("\'", '', $var);
} else {
$var = htmlentities($var, ENT_QUOTES, 'UTF-8');
}
return $var;
}
?>
Usage with quotes for example message:
$message = ConvertSimbols($message);
Usage without quotes for example link:
$link = ConvertSimbols($link, 1);`

[up](https://www.php.net/manual/vote-note.php?id=122790&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122790&page=function.htmlentities&vote=down "Vote down!")

4


[**_Jeff_**](https://www.php.net/manual/en/function.htmlentities.php#122790) [¶](https://www.php.net/manual/en/function.htmlentities.php#122790)

**7 years ago**

`There is a feature when writing to XML using an AJAX call to PHP that rarely is mentioned. I struggled for many hours using htmlentities() because what was getting written to my XML document was not as expected. I naturally assumed that I should be converting my strings before writing them to XML to adhere to XML rules on illegal characters. To my surprise, when converting with htmlentities() or htmlspecialchars() and then writing to an XML file, the resulting ampersands get converted afterwards! Consider the following example:
<?php
$str = "<b>I am cool</b>" ;
$str = htmlentities($str) ;
?>
When you append $str to an XML element and save() the document, you would expect the XML document's source code to look something like this:
<ele>&lt;b&gt;I am cool&lt;/b&gt;</ele>
But that is not what happens. The resulting ampersands get converted by PHP automatically to &amp; and your source code ends up looking like this:
<ele>&amp;lt;b&amp;gt;I am cool&amp;lt;/b&amp;gt;</ele>
As you can see, this creates problems when trying to output the XML data back to HTML. It is important to remember that when writing to XML this way, special characters like ">" and "<"; PHP converts them automatically and there becomes no need to use htmlentities() in certain cases. I assume this feature is in place to aid with passing data through header queries, to avoid reserved characters conflicting with others in a header query (e.g. & or =). Now I understand this may not be the case with older versions of PHP and that this might be a feature of my version (PHP version 5.6.32). With older versions, I assume using htmlentities() or htmlspecialchars() is a must, as stated with previous notes here. Also I use the charset UTF-8 in my HTML and XML and am not sure if this also effects the results I get.
Anyway, I struggled for many hours with using htmlentities() to convert strings for XML writing and saving, when all I had to do was simply not use the function and let PHP convert my strings for me. I hope this helps because I would think I am not the only one who has struggled with this situation.`

[up](https://www.php.net/manual/vote-note.php?id=86409&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86409&page=function.htmlentities&vote=down "Vote down!")

4


[**_Tom Walter_**](https://www.php.net/manual/en/function.htmlentities.php#86409) [¶](https://www.php.net/manual/en/function.htmlentities.php#86409)

**17 years ago**

`Note that as of 5.2.5 it appears that if the input string contains a character that is not valid for the output encoding you've specified, then this function returns null.
You might expect it to just strip the invalid char, but it doesn't.
You can strip the chars yourself like so:
iconv('utf-8','utf-8',$str);
You can combine that with htmlentities also:
$str = htmlentities(iconv('UTF-8', 'UTF-8//IGNORE', $str, ENT_QUOTES, 'UTF-8');
Should give you a string with htmlentities encoded to utf-8, and any unsupported chars stripped.`

[up](https://www.php.net/manual/vote-note.php?id=106535&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106535&page=function.htmlentities&vote=down "Vote down!")

2


[**_steve at mcdragonsoftware dot com_**](https://www.php.net/manual/en/function.htmlentities.php#106535) [¶](https://www.php.net/manual/en/function.htmlentities.php#106535)

**13 years ago**

`I'm glad 5.4 has xml support, but many of us are working with older installations, some of us still have to use PHP4. If you're like me you've been frustrated with trying to use htmlentites/htmlspecial chars with xml output. I was hoping to find an option to force numeric encoding, lacking that, I have written my own xmlencode function, which I now offer:
usage:
$string xmlencode( $string )
it will use htmlspecialchars for the valid xml entities amp, quote, lt, gt, (apos) and return the numeric entity for all other non alpha-numeric characters.
-------------------------------------------
<?php
if( !function_exists( 'xmlentities' ) ) {
    function xmlentities( $string ) {
        $not_in_list = "A-Z0-9a-z\s_-";
        return preg_replace_callback( "/[^{$not_in_list}]/" , 'get_xml_entity_at_index_0' , $string );
    }
    function get_xml_entity_at_index_0( $CHAR ) {
        if( !is_string( $CHAR[0] ) || ( strlen( $CHAR[0] ) > 1 ) ) {
            die( "function: 'get_xml_entity_at_index_0' requires data type: 'char' (single character). '{$CHAR[0]}' does not match this type." );
        }
        switch( $CHAR[0] ) {
            case "'":    case '"':    case '&':    case '<':    case '>':
                return htmlspecialchars( $CHAR[0], ENT_QUOTES );    break;
            default:
                return numeric_entity_4_char($CHAR[0]);                break;
        }
    }
    function numeric_entity_4_char( $char ) {
        return "&#".str_pad(ord($char), 3, '0', STR_PAD_LEFT).";";
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=42020&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=42020&page=function.htmlentities&vote=down "Vote down!")

3


[**_jake\_mcmahon at hotmail dot com_**](https://www.php.net/manual/en/function.htmlentities.php#42020) [¶](https://www.php.net/manual/en/function.htmlentities.php#42020)

**21 years ago**

`This fuction is particularly useful against XSS (cross-site-scripting-). XSS makes use of holes in code, whether it be in Javascript or PHP. XSS often, if not always, uses HTML entities to do its evil deeds, so this function in co-operation with your scripts (particularly search or submitting scripts) is a very useful tool in combatting "H4X0rz".`

[up](https://www.php.net/manual/vote-note.php?id=99984&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99984&page=function.htmlentities&vote=down "Vote down!")

2


[**_h\_guillaume at hotmail dot com_**](https://www.php.net/manual/en/function.htmlentities.php#99984) [¶](https://www.php.net/manual/en/function.htmlentities.php#99984)

**15 years ago**

`I use this function to encode all the xml entities and also all the &something; that are not defined in xml like &trade;
You can also decode what you encode with my decode function.
My function works a little like the htmlentities.
You can also add other string to the array if you want to exclude them from the encoding.
<?php
function xml_entity_decode($text, $charset = 'Windows-1252'){
    // Double decode, so if the value was &amp;trade; it will become Trademark
    $text = html_entity_decode($text, ENT_COMPAT, $charset);
    $text = html_entity_decode($text, ENT_COMPAT, $charset);
    return $text;
}
function xml_entities($text, $charset = 'Windows-1252'){
     // Debug and Test
    // $text = "test &amp; &trade; &amp;trade; abc &reg; &amp;reg; &#45;";

    // First we encode html characters that are also invalid in xml
    $text = htmlentities($text, ENT_COMPAT, $charset, false);

    // XML character entity array from Wiki
    // Note: &apos; is useless in UTF-8 or in UTF-16
    $arr_xml_special_char = array("&quot;","&amp;","&apos;","&lt;","&gt;");

    // Building the regex string to exclude all strings with xml special char
    $arr_xml_special_char_regex = "(?";
    foreach($arr_xml_special_char as $key => $value){
        $arr_xml_special_char_regex .= "(?!$value)";
    }
    $arr_xml_special_char_regex .= ")";

    // Scan the array for &something_not_xml; syntax
    $pattern = "/$arr_xml_special_char_regex&([a-zA-Z0-9]+;)/";

    // Replace the &something_not_xml; with &amp;something_not_xml;
    $replacement = '&amp;${1}';
    return preg_replace($pattern, $replacement, $text);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=82534&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82534&page=function.htmlentities&vote=down "Vote down!")

1


[**_za at byza dot it_**](https://www.php.net/manual/en/function.htmlentities.php#82534) [¶](https://www.php.net/manual/en/function.htmlentities.php#82534)

**17 years ago**

`Trouble when using files with different charset?
htmlentities and html_entity_decode can be used to translate between charset!
Sample function:
<?php
function utf2latin($text) {
$text=htmlentities($text,ENT_COMPAT,'UTF-8');
return html_entity_decode($text,ENT_COMPAT,'ISO-8859-1');
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=120958&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120958&page=function.htmlentities&vote=down "Vote down!")

 -1


[**_chris at ocproducts dot com_**](https://www.php.net/manual/en/function.htmlentities.php#120958) [¶](https://www.php.net/manual/en/function.htmlentities.php#120958)

**8 years ago**

`This function throws a warning on bad input even if ENT_SUBSTITUTE is set, so be prepared for this.`

[up](https://www.php.net/manual/vote-note.php?id=100186&page=function.htmlentities&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100186&page=function.htmlentities&vote=down "Vote down!")

 -2


[**_drallen at cs dot uwaterloo dot ca_**](https://www.php.net/manual/en/function.htmlentities.php#100186) [¶](https://www.php.net/manual/en/function.htmlentities.php#100186)

**15 years ago**

`A pointer to [http://www.php.net/manual/en/function.mb-convert-encoding.php](http://www.php.net/manual/en/function.mb-convert-encoding.php) if your intention is to translate *all* characters in a charset to their corresponding HTML entities, not just named characters. Non-named characters will be replaced with HTML numeric encoding. eg:
$text = mb_convert_encoding($text, 'HTML-ENTITIES', "UTF-8");`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.htmlentities&repo=en&redirect=https://www.php.net/manual/en/function.htmlentities.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google