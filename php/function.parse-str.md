---
url: https://www.php.net/manual/en/function.parse-str.php
scraped_at: 2025-10-20T02:57:42.151Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# parse\_str

(PHP 4, PHP 5, PHP 7, PHP 8)

parse\_str — Parse a string as a URL query string

### Description [¶](https://www.php.net/manual/en/function.parse-str.php\#refsect1-function.parse-str-description)

**parse\_str**([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [array](https://www.php.net/manual/en/language.types.array.php) `&$result`): [void](https://www.php.net/manual/en/language.types.void.php)

Parses `string` as if it were the query string
passed via a URL and sets keys in the provided `result`
array. If no `result` is passed, values are instead
set as variables in the current scope.


### Parameters [¶](https://www.php.net/manual/en/function.parse-str.php\#refsect1-function.parse-str-parameters)

`string`

The input string.


`result`

A variable passed by reference, which will be set to an array
containing the key-value pairs extracted from `string`.
If the `result` parameter is not passed,
a separate variable is set in the local scope for each key.


**Warning**

Using this function without the `result` parameter is highly
_DISCOURAGED_ and _DEPRECATED_ as of PHP 7.2.
As of PHP 8.0.0, the `result` parameter is _mandatory_.


### Return Values [¶](https://www.php.net/manual/en/function.parse-str.php\#refsect1-function.parse-str-returnvalues)

No value is returned.


### Changelog [¶](https://www.php.net/manual/en/function.parse-str.php\#refsect1-function.parse-str-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `result` is no longer optional. |
| 7.2.0 | Usage of **parse\_str()** without a second parameter<br> now emits an **`[E\_DEPRECATED](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-deprecated)`** notice. |

### Examples [¶](https://www.php.net/manual/en/function.parse-str.php\#refsect1-function.parse-str-examples)

**Example #1 Using **parse\_str()****

`<?php
$str = "first=value&arr[]=foo+bar&arr[]=baz";
// Recommended
parse_str($str, $output);
echo $output['first'], PHP_EOL;  // value
echo $output['arr'][0], PHP_EOL; // foo bar
echo $output['arr'][1], PHP_EOL; // baz
?>`

Run code

Any spaces and dots in parameter names are converted to underscores
when creating array keys or local variables.
This is because variable names in PHP are not allowed to contain spaces
or dots, but applies even when using this function with the recommended
`result` parameter.


**Example #2 **parse\_str()** name mangling**

`<?php
parse_str("My Value=Something", $output);
echo $output['My_Value']; // Something
?>`

Run code

### Notes [¶](https://www.php.net/manual/en/function.parse-str.php\#refsect1-function.parse-str-notes)

> **Note**:
>
>
> **parse\_str()** is affected by the [max\_input\_vars](https://www.php.net/manual/en/info.configuration.php#ini.max-input-vars)
> directive. Exceeding this limit triggers an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**,
> and any variables beyond the limit are not added to the result array.
> The default is 1000; adjust [max\_input\_vars](https://www.php.net/manual/en/info.configuration.php#ini.max-input-vars) as needed.

> **Note**:
>
>
> All values populated in the `result` array
> (or variables created if second parameter is not set)
> are already URL-decoded using the same rules as [urldecode()](https://www.php.net/manual/en/function.urldecode.php).

> **Note**:
>
>
> To get the query string of the current request, you may use the variable
> [$\_SERVER\['QUERY\_STRING'\]](https://www.php.net/manual/en/reserved.variables.server.php).
> Also, you may want to read the section on
> [variables from external\\
> sources](https://www.php.net/manual/en/language.variables.external.php).

### See Also [¶](https://www.php.net/manual/en/function.parse-str.php\#refsect1-function.parse-str-seealso)

- [parse\_url()](https://www.php.net/manual/en/function.parse-url.php) \- Parse a URL and return its components
- [pathinfo()](https://www.php.net/manual/en/function.pathinfo.php) \- Returns information about a file path
- [http\_build\_query()](https://www.php.net/manual/en/function.http-build-query.php) \- Generate URL-encoded query string
- [urldecode()](https://www.php.net/manual/en/function.urldecode.php) \- Decodes URL-encoded string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/parse-str.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.parse-str%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.parse-str&repo=en&redirect=https://www.php.net/manual/en/function.parse-str.php)

### User Contributed Notes 32 notes

[up](https://www.php.net/manual/vote-note.php?id=76792&page=function.parse-str&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76792&page=function.parse-str&vote=down "Vote down!")

129


[**_Evan K_**](https://www.php.net/manual/en/function.parse-str.php#76792) [¶](https://www.php.net/manual/en/function.parse-str.php#76792)

**18 years ago**

`It bears mentioning that the parse_str builtin does NOT process a query string in the CGI standard way, when it comes to duplicate fields.  If multiple fields of the same name exist in a query string, every other web processing language would read them into an array, but PHP silently overwrites them:
<?php
# silently fails to handle multiple values
parse_str('foo=1&foo=2&foo=3');
# the above produces:
$foo = array('foo' => '3');
?>
Instead, PHP uses a non-standards compliant practice of including brackets in fieldnames to achieve the same effect.
<?php
# bizarre php-specific behavior
parse_str('foo[]=1&foo[]=2&foo[]=3');
# the above produces:
$foo = array('foo' => array('1', '2', '3') );
?>
This can be confusing for anyone who's used to the CGI standard, so keep it in mind.  As an alternative, I use a "proper" querystring parser function:
<?php
function proper_parse_str($str) {
# result array
$arr = array();
# split on outer delimiter
$pairs = explode('&', $str);
# loop through each pair
foreach ($pairs as $i) {
    # split into name and value
    list($name,$value) = explode('=', $i, 2);

    # if name already exists
    if( isset($arr[$name]) ) {
      # stick multiple values into an array
      if( is_array($arr[$name]) ) {
        $arr[$name][] = $value;
      }
      else {
        $arr[$name] = array($arr[$name], $value);
      }
    }
    # otherwise, simply stick it in a scalar
    else {
      $arr[$name] = $value;
    }
}
# return result array
return $arr;
}
$query = proper_parse_str($_SERVER['QUERY_STRING']);
?>`

[up](https://www.php.net/manual/vote-note.php?id=126789&page=function.parse-str&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126789&page=function.parse-str&vote=down "Vote down!")

6


[**_Roemer Lievaart_**](https://www.php.net/manual/en/function.parse-str.php#126789) [¶](https://www.php.net/manual/en/function.parse-str.php#126789)

**3 years ago**

`If you need the key names preserved and don't want spaces or . or unmatched [ or ] replaced by an underscore, yet you want all the other goodies of parse_str(), like turning matched [] into array elements, you can use this code as a base for that.
<?php
const periodPlaceholder = 'QQleQPunT';
const spacePlaceholder = 'QQleQSpaTIE';
function parse_str_clean($querystr): array {
    // without the converting of spaces and dots etc to underscores.
    $qquerystr = str_ireplace(['.','%2E','+',' ','%20'], [periodPlaceholder,periodPlaceholder,spacePlaceholder,spacePlaceholder,spacePlaceholder], $querystr);
    $arr = null ; parse_str($qquerystr, $arr);
    sanitizeKeys($arr, $querystr);
    return $arr;
}
function sanitizeKeys(&$arr, $querystr) {
    foreach($arr as $key=>$val) {
        // restore values to original
        $newval = $val ;
        if ( is_string($val)) {
            $newval = str_replace([periodPlaceholder,spacePlaceholder], ["."," "], $val);
        }
        $newkey = str_replace([periodPlaceholder,spacePlaceholder], ["."," "], $key);

        if ( str_contains($newkey, '_') ) {
            // periode of space or [ or ] converted to _. Restore with querystring
            $regex = '/&('.str_replace('_', '[ \.\[\]]', preg_quote($newkey, '/')).')=/';
            $matches = null ;
            if ( preg_match_all($regex, "&".urldecode($querystr), $matches) ) {
                if ( count(array_unique($matches[1])) === 1 && $key != $matches[1][0] ) {
                    $newkey = $matches[1][0] ;
                }
            }
        }
        if ( $newkey != $key ) {
            unset($arr[$key]);
            $arr[$newkey] = $newval ;
        } elseif( $val != $newval )
            $arr[$key] = $newval;
        if ( is_array($val)) {
            sanitizeKeys($arr[$newkey], $querystr);
        }
    }
}
?>
For example:
parse_str_clean("code.1=printr%28hahaha&code 1=448044&test.mijn%5B%5D%5B2%5D=test%20Roemer&test%5Bmijn=test%202e%20Roemer");
Produces:
array(4) {
["code.1"]=>
string(13) "printr(hahaha"
["code 1"]=>
string(6) "448044"
["test.mijn"]=>
array(1) {
    [0]=>
    array(1) {
      [2]=>
      string(11) "test Roemer"
    }
}
["test[mijn"]=>\
string(14) "test 2e Roemer"\
}\
Whereas if you feed the same querystring to parse_str, you will get\
array(2) {\
["code_1"]=>\
string(6) "448044"\
["test_mijn"]=>\
string(14) "test 2e Roemer"\
}`\
\
[up](https://www.php.net/manual/vote-note.php?id=108642&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=108642&page=function.parse-str&vote=down "Vote down!")\
\
36\
\
\
[**_shagshag_**](https://www.php.net/manual/en/function.parse-str.php#108642) [¶](https://www.php.net/manual/en/function.parse-str.php#108642)\
\
**13 years ago**\
\
`That's not says in the description but max_input_vars directive affects this function. If there are more input variables on the string than specified by this directive, an E_WARNING is issued, and further input variables are truncated from the request.`\
\
[up](https://www.php.net/manual/vote-note.php?id=117183&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=117183&page=function.parse-str&vote=down "Vote down!")\
\
18\
\
\
[**_zweibieren at yahoo dot com_**](https://www.php.net/manual/en/function.parse-str.php#117183) [¶](https://www.php.net/manual/en/function.parse-str.php#117183)\
\
**10 years ago**\
\
`If the arr argument is provided, all its existing elements are removed.`\
\
[up](https://www.php.net/manual/vote-note.php?id=119484&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=119484&page=function.parse-str&vote=down "Vote down!")\
\
18\
\
\
[**_alxcube at gmail dot com_**](https://www.php.net/manual/en/function.parse-str.php#119484) [¶](https://www.php.net/manual/en/function.parse-str.php#119484)\
\
**9 years ago**\
\
`if you need custom arg separator, you can use this function. it returns parsed  query as associative array.\
<?php\
/**\
* Parses http query string into an array\
*\
* @author Alxcube <alxcube@gmail.com>\
*\
* @param string $queryString String to parse\
* @param string $argSeparator Query arguments separator\
* @param integer $decType Decoding type\
* @return array\
*/\
function http_parse_query($queryString, $argSeparator = '&', $decType = PHP_QUERY_RFC1738) {\
        $result             = array();\
        $parts              = explode($argSeparator, $queryString);\
        foreach ($parts as $part) {\
                list($paramName, $paramValue)   = explode('=', $part, 2);\
                switch ($decType) {\
                        case PHP_QUERY_RFC3986:\
                                $paramName      = rawurldecode($paramName);\
                                $paramValue     = rawurldecode($paramValue);\
                                break;\
                        case PHP_QUERY_RFC1738:\
                        default:\
                                $paramName      = urldecode($paramName);\
                                $paramValue     = urldecode($paramValue);\
                                break;\
                }\
\
                if (preg_match_all('/\[([^\]]*)\]/m', $paramName, $matches)) {
                        $paramName      = substr($paramName, 0, strpos($paramName, '['));\
                        $keys           = array_merge(array($paramName), $matches[1]);\
                } else {\
                        $keys           = array($paramName);\
                }\
\
                $target         = &$result;\
\
                foreach ($keys as $index) {\
                        if ($index === '') {\
                                if (isset($target)) {\
                                        if (is_array($target)) {\
                                                $intKeys        = array_filter(array_keys($target), 'is_int');\
                                                $index  = count($intKeys) ? max($intKeys)+1 : 0;\
                                        } else {\
                                                $target = array($target);\
                                                $index  = 1;\
                                        }\
                                } else {\
                                        $target         = array();\
                                        $index          = 0;\
                                }\
                        } elseif (isset($target[$index]) && !is_array($target[$index])) {\
                                $target[$index] = array($target[$index]);\
                        }\
                        $target         = &$target[$index];\
                }\
                if (is_array($target)) {\
                        $target[]   = $paramValue;\
                } else {\
                        $target     = $paramValue;\
                }\
        }\
        return $result;\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=73719&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=73719&page=function.parse-str&vote=down "Vote down!")\
\
2\
\
\
[**_php at voodoolabs dot net_**](https://www.php.net/manual/en/function.parse-str.php#73719) [¶](https://www.php.net/manual/en/function.parse-str.php#73719)\
\
**18 years ago**\
\
`This is probably a better solution than below. The first line makes sure the file doesn't exist then the second line directs all requests to a script. No need to output a 200 header with this method either.\
RewriteEngine On\
RewriteCond %{REQUEST_FILENAME} !-f\
RewriteRule ^ index.php      [L]`\
\
[up](https://www.php.net/manual/vote-note.php?id=52588&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=52588&page=function.parse-str&vote=down "Vote down!")\
\
5\
\
\
[**_kent at nospam dot ioflux dot com_**](https://www.php.net/manual/en/function.parse-str.php#52588) [¶](https://www.php.net/manual/en/function.parse-str.php#52588)\
\
**20 years ago**\
\
`You may want to parse the query string into an array.\
<?php\
/**\
* Similar to parse_str. Returns false if the query string or URL is empty. Because we're not parsing to\
* variables but to array key entries, this function will handle ?[]=1&[]=2 "correctly."\
*\
* @return array Similar to the $_GET formatting that PHP does automagically.\
* @param string $url A query string or URL\
* @param boolean $qmark Find and strip out everything before the question mark in the string\
*/\
function parse_query_string($url, $qmark=true)\
{\
    if ($qmark) {\
        $pos = strpos($url, "?");\
        if ($pos !== false) {\
            $url = substr($url, $pos + 1);\
        }\
    }\
    if (empty($url))\
        return false;\
    $tokens = explode("&", $url);\
    $urlVars = array();\
    foreach ($tokens as $token) {\
        $value = string_pair($token, "=", "");\
        if (preg_match('/^([^\[]*)(\[.*\])$/', $token, $matches)) {\
            parse_query_string_array($urlVars, $matches[1], $matches[2], $value);\
        } else {\
            $urlVars[urldecode($token)] = urldecode($value);\
        }\
    }\
    return $urlVars;\
}\
/**\
* Utility function for parse_query_string. Given a result array, a starting key, and a set of keys formatted like "[a][b][c]"\
* and the final value, updates the result array with the correct PHP array keys.\
*\
* @return void\
* @param array $result A result array to populate from the query string\
* @param string $k The starting key to populate in $result\
* @param string $arrayKeys The key list to parse in the form "[][a][what%20ever]"\
* @param string $value The value to place at the destination array key\
*/\
function parse_query_string_array(&$result, $k, $arrayKeys, $value)\
{\
    if (!preg_match_all('/\[([^\]]*)\]/', $arrayKeys, $matches))\
        return $value;\
    if (!isset($result[$k])) {\
        $result[urldecode($k)] = array();\
    }\
    $temp =& $result[$k];\
    $last = urldecode(array_pop($matches[1]));\
    foreach ($matches[1] as $k) {\
        $k = urldecode($k);\
        if ($k === "") {\
            $temp[] = array();\
            $temp =& $temp[count($temp)-1];\
        } else if (!isset($temp[$k])) {\
            $temp[$k] = array();\
            $temp =& $temp[$k];\
        }\
    }\
    if ($last === "") {\
        $temp[] = $value;\
    } else {\
        $temp[urldecode($last)] = $value;\
    }\
}\
/**\
* Breaks a string into a pair for a common parsing function.\
*\
* The string passed in is truncated to the left half of the string pair, if any, and the right half, if anything, is returned.\
*\
* An example of using this would be:\
* <code>\
* $path = "Account.Balance";\
* $field = string_pair($path);\
*\
* $path is "Account"\
* $field is "Balance"\
*\
* $path = "Account";\
* $field = string_pair($path);\
*\
* $path is "Account"\
* $field is false\
* </code>\
*\
* @return string The "right" portion of the string is returned if the delimiter is found.\
* @param string $a A string to break into a pair. The "left" portion of the string is returned here if the delimiter is found.\
* @param string $delim The characters used to delimit a string pair\
* @param mixed $default The value to return if the delimiter is not found in the string\
* @desc\
*/\
function string_pair(&$a, $delim='.', $default=false)\
{\
    $n = strpos($a, $delim);\
    if ($n === false)\
        return $default;\
    $result = substr($a, $n+strlen($delim));\
    $a = substr($a, 0, $n);\
    return $result;\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=54275&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=54275&page=function.parse-str&vote=down "Vote down!")\
\
9\
\
\
[**_Tore Bj?lseth_**](https://www.php.net/manual/en/function.parse-str.php#54275) [¶](https://www.php.net/manual/en/function.parse-str.php#54275)\
\
**20 years ago**\
\
`As of PHP 5, you can do the exact opposite with http_build_query(). Just remember to use the optional array output parameter.\
This is a very useful combination if you want to re-use a search string url, but also slightly modify it:\
Example:\
<?\
$url1 = "action=search&interest[]=sports&interest[]=music&sort=id";\
$str = parse_str($url1, $output);\
// Modifying criteria:\
$output['sort'] = "interest";\
$url2 = http_build_query($output);\
echo "<br>url1: ".$url1;\
echo "<br>url2: ".$url2;\
?>\
Results in:\
url1: action=search&interest[]=sports&interest[]=music&sort=id\
url2: action=search&interest[0]=sports&interest[1]=music&sort=interest\
(Array indexes are automatically created.)`\
\
[up](https://www.php.net/manual/vote-note.php?id=70234&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=70234&page=function.parse-str&vote=down "Vote down!")\
\
13\
\
\
[**_Olivier Mengué_**](https://www.php.net/manual/en/function.parse-str.php#70234) [¶](https://www.php.net/manual/en/function.parse-str.php#70234)\
\
**19 years ago**\
\
`Vladimir: the function is OK in how it deals with &amp;.\
&amp; must only be used when outputing URLs in HTML/XML data.\
You should ask yourself why you have &amp; in your URL when you give it to parse_str.`\
\
[up](https://www.php.net/manual/vote-note.php?id=84165&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=84165&page=function.parse-str&vote=down "Vote down!")\
\
4\
\
\
[**_tobsn at php dot net_**](https://www.php.net/manual/en/function.parse-str.php#84165) [¶](https://www.php.net/manual/en/function.parse-str.php#84165)\
\
**17 years ago**\
\
`just a heads up with the example above:\
?var[]=123 - the [] has to be urlencoded.\
var names and var values - both have to be urlencoded!`\
\
[up](https://www.php.net/manual/vote-note.php?id=56475&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=56475&page=function.parse-str&vote=down "Vote down!")\
\
3\
\
\
[**_avi at amarcus dot com_**](https://www.php.net/manual/en/function.parse-str.php#56475) [¶](https://www.php.net/manual/en/function.parse-str.php#56475)\
\
**20 years ago**\
\
`If you are trying to preserve a complex array, the function serialize might be better than http_build_query or other methods of making a query string.`\
\
[up](https://www.php.net/manual/vote-note.php?id=82837&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=82837&page=function.parse-str&vote=down "Vote down!")\
\
4\
\
\
[**_helpmepro1 at gmail dot com_**](https://www.php.net/manual/en/function.parse-str.php#82837) [¶](https://www.php.net/manual/en/function.parse-str.php#82837)\
\
**17 years ago**\
\
`<?\
//by shimon doodkin\
$url_form=url_to_form($url);\
echo '<form action="'.$url_form['action'].'" method="get">';\
echo $url_form['hidden'];\
echo '<input name="otherfiled" type="text">';\
echo '<input type="submit">';\
echo '</form>';\
function url_to_form($url)\
{\
$url=split('\?',$url,2);\
$action=$url[0];\
$hidden="";\
if(isset($url[1]))\
{\
$pairs=split('&',$url[1]);\
foreach($pairs as $pair)\
{\
    $pair=split('=',$pair,2);\
    $name=$pair[0];\
    if(isset($pair[1]))\
     $value=$pair[1];\
    else\
     $value='';\
    $name=$name;\
    $value=htmlspecialchars($value);\
    if($name!='')\
     $hidden.='<hidden name="'.$name.'" value="'.$value.'">';\
}\
}\
return array('action'=>$action,'hidden'=>$hidden);\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=118008&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=118008&page=function.parse-str&vote=down "Vote down!")\
\
2\
\
\
[**_StanE_**](https://www.php.net/manual/en/function.parse-str.php#118008) [¶](https://www.php.net/manual/en/function.parse-str.php#118008)\
\
**10 years ago**\
\
`Note that the characters "." and " " (empty space) will be converted to "_". The characters "[" and "]" have special meaning: They represent arrays but there seems to be some weird behaviour, which I don't really understand:\
<?php\
// Note: "[" = %5B, "]" = %5D\
/*\
"v][=a" produces ("[" gets replaced by "_"):\
Array\
(\
    [v]_] => a\
)\
*/\
parse_str("v%5D%5B=a", $r);\
print_r($r);\
/*\
"v][[=a" produces (first "[" gets replaced by "_", but not all following):\
Array\
(\
    [v]_[] => a\
)\
*/\
parse_str("v%5D%5B%5B=a", $r);\
print_r($r);\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=75505&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=75505&page=function.parse-str&vote=down "Vote down!")\
\
2\
\
\
[**_mike dot coley at inbox dot com_**](https://www.php.net/manual/en/function.parse-str.php#75505) [¶](https://www.php.net/manual/en/function.parse-str.php#75505)\
\
**18 years ago**\
\
`Here is a little function that does the opposite of the parse_str function. It will take an array and build a query string from it.\
<?php\
/* Converts an array of parameters into a query string to be appended to a URL.\
*\
* @return  string              : Query string to append to a URL.\
* @param   array    $array     : Array of parameters to append to the query string.\
* @param   string   $parent    : This should be left blank (it is used internally by the function).\
*/\
function append_params($array, $parent='')\
{\
    $params = array();\
    foreach ($array as $k => $v)\
    {\
        if (is_array($v))\
            $params[] = append_params($v, (empty($parent) ? urlencode($k) : $parent . '[' . urlencode($k) . ']'));\
        else\
            $params[] = (!empty($parent) ? $parent . '[' . urlencode($k) . ']' : urlencode($k)) . '=' . urlencode($v);\
    }\
    $sessid = session_id();\
    if (!empty($parent) || empty($sessid))\
        return implode('&', $params);\
    // Append the session ID to the query string if we have to.\
    $sessname = session_name();\
    if (ini_get('session.use_cookies'))\
    {\
        if (!ini_get('session.use_only_cookies') && (!isset($_COOKIE[$sessname]) || ($_COOKIE[$sessname] != $sessid)))\
            $params[] = $sessname . '=' . urlencode($sessid);\
    }\
    elseif (!ini_get('session.use_only_cookies'))\
        $params[] = $sessname . '=' . urlencode($sessid);\
    return implode('&', $params);\
}\
?>\
Note that the function will also append the session ID to the query string if it needs to be.`\
\
[up](https://www.php.net/manual/vote-note.php?id=109212&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=109212&page=function.parse-str&vote=down "Vote down!")\
\
4\
\
\
[**_jrgns at jadeit dot co dot za_**](https://www.php.net/manual/en/function.parse-str.php#109212) [¶](https://www.php.net/manual/en/function.parse-str.php#109212)\
\
**13 years ago**\
\
`The array to be populated does not need to be defined before calling the function:\
<?php\
error_reporting(E_ALL | E_STRICT);\
parse_str('var=value', $array);\
?>\
This will not produce a notice.`\
\
[up](https://www.php.net/manual/vote-note.php?id=79154&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=79154&page=function.parse-str&vote=down "Vote down!")\
\
2\
\
\
[**_chris at mcfadyen dot ca_**](https://www.php.net/manual/en/function.parse-str.php#79154) [¶](https://www.php.net/manual/en/function.parse-str.php#79154)\
\
**17 years ago**\
\
`I shouldn't've posted the original version, as it only worked with the most basic of query strings.\
This function will parse an html-safe query-like url string for variables and php-like ordered and associative arrays.  It places them into the global scope as parse_str does and adds minimal slashes for database insertions without the triple-slash problems that magic quotes can produce (the reason I had to write it in the first place).  If you don't need the slashes, they're easy enough to remove.\
<?php\
function parse_query($str) {\
\
    // Separate all name-value pairs\
    $pairs = explode('&', $str);\
\
    foreach($pairs as $pair) {\
\
        // Pull out the names and the values\
        list($name, $value) = explode('=', $pair, 2);\
\
        // Decode the variable name and look for arrays\
        list($name, $index) = split('[][]', urldecode($name));\
\
        // Arrays\
        if(isset($index)) {\
\
            // Declare or add to the global array defined by $name\
            global $$name;\
            if(!isset($$name)) $$name = array();\
\
            // Associative array\
            if($index != "") {\
                ${$name}[$index] = addslashes(urldecode($value));\
\
            // Ordered array\
            } else {\
                array_push($$name, addslashes(urldecode($value)));\
            }\
\
        // Variables\
        } else {\
\
            // Declare or overwrite the global variable defined by $name\
            global $$name;\
            $$name = addslashes(urldecode($value));\
        }\
    }\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=69254&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=69254&page=function.parse-str&vote=down "Vote down!")\
\
2\
\
\
[**_PEPE\_RIVAS at repixel dot net_**](https://www.php.net/manual/en/function.parse-str.php#69254) [¶](https://www.php.net/manual/en/function.parse-str.php#69254)\
\
**19 years ago**\
\
`CONVERT ANY FORMATTED STRING INTO VARIABLES\
I developed a online payment solution for credit cards using a merchant, and this merchant returns me an answer of the state of the transaction like this:\
estado=1,txnid=5555444-8454445-4455554,monto=100.00\
to have all that data into variables could be fine for me! so i use str_replace(), the problem is this function recognizes each group of variables with the & character... and i have  comma separated values... so i replace comma with &\
<?php\
$string = "estado=1,txnid=5555444-8454445-4455554,monto=100.00";\
$string = str_replace(",","&",$string);\
parse_str($string);\
echo $monto; // outputs 100.00\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=72745&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=72745&page=function.parse-str&vote=down "Vote down!")\
\
1\
\
\
[**_jgbreezer at gmail dot com_**](https://www.php.net/manual/en/function.parse-str.php#72745) [¶](https://www.php.net/manual/en/function.parse-str.php#72745)\
\
**18 years ago**\
\
`Vladimir Kornea wrote on 8 Sep 2006:\
"This function is confused by ampersands (&) being encoded as HTML entities (&amp;)"\
Well, it would be - it's not supposed to be passed html entities, that's a different encoding scheme. This function does correctly decode url encoded params for you though (with the rawurlencode rather than urlencode, ie '+' is translated to a space).`\
\
[up](https://www.php.net/manual/vote-note.php?id=78882&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=78882&page=function.parse-str&vote=down "Vote down!")\
\
1\
\
\
[**_chris at mcfadyen dot ca_**](https://www.php.net/manual/en/function.parse-str.php#78882) [¶](https://www.php.net/manual/en/function.parse-str.php#78882)\
\
**17 years ago**\
\
`If you wish a version of parse_str sans magic quotes, the following will do the trick:\
<?php\
function parse_query($str) {\
    $pairs = explode('&', $str);\
    foreach($pairs as $pair) {\
        list($name, $value) = explode('=', $pair, 2);\
        global $$name;\
        $$name = $value;\
    }\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=53175&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=53175&page=function.parse-str&vote=down "Vote down!")\
\
1\
\
\
[**_mortoray at ecircle-ag dot com_**](https://www.php.net/manual/en/function.parse-str.php#53175) [¶](https://www.php.net/manual/en/function.parse-str.php#53175)\
\
**20 years ago**\
\
`In Kent's solution you may wish to switch "urldecode" into "rawurldecode" if you'd like to get rid of the [annoying] plus '+' converted to space ' ' translation.`\
\
[up](https://www.php.net/manual/vote-note.php?id=130479&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=130479&page=function.parse-str&vote=down "Vote down!")\
\
0\
\
\
[**_jab\_creations at yahoo dot com_**](https://www.php.net/manual/en/function.parse-str.php#130479) [¶](https://www.php.net/manual/en/function.parse-str.php#130479)\
\
**1 month ago**\
\
`A simple though strict (and cleanly coded) version of the native function though without the pointless string replacement of periods with underscores:\
<?php\
function parse_query_string_mailto()\
{//2025-09-11; Used in place of PHP's native parse_str() which pointlessly replaces periods with underscores:\
$r = false;\
$qs = ((isset($_SERVER['QUERY_STRING'])) ? urldecode($_SERVER['QUERY_STRING']) : false);\
if ($qs && strpos($qs, ' [mailto:](mailto:)'))\
{\
$s = explode(' [mailto:](mailto:)', $qs, 2);\
if (count($s) == 2)\
{\
$r = array();\
$pairs = explode('&', $s[1]);\
foreach ($pairs as $pair)\
{\
    $p = explode('=', $pair, 2);\
    $r[$p[0]] = urldecode($p[1]);\
}\
}\
}\
return $r;\
}\
?>\
Example relative URL:\
mail/compose/?mailto%3Asubject%3DTest%2520Subject%26body%3DHello%2520World!%26from%3Duser%40example.com`\
\
[up](https://www.php.net/manual/vote-note.php?id=126160&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=126160&page=function.parse-str&vote=down "Vote down!")\
\
0\
\
\
[**_kawewong at gmail dot com_**](https://www.php.net/manual/en/function.parse-str.php#126160) [¶](https://www.php.net/manual/en/function.parse-str.php#126160)\
\
**4 years ago**\
\
``Warning: `parse_str()` can cause "Input variables exceeded 1000" error (1000 is default php.ini setting for `max_input_vars`).\
Test code.\
<?php\
$inputString = 'first=firstvalue';\
for ($i = 1; $i <= 1100; $i++) {\
    $inputString .= '&arrLoopNumber[]=' . $i;\
}\
unset($i);\
echo 'input string: <code>' . $inputString . '</code><br>' . PHP_EOL;\
echo '<h5>doing <code>parse_str()</code></h5>' . PHP_EOL;\
$output = [];\
parse_str($inputString, $output);\
// errors!!\
?>``\
\
[up](https://www.php.net/manual/vote-note.php?id=122294&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=122294&page=function.parse-str&vote=down "Vote down!")\
\
1\
\
\
[**_twiddly_**](https://www.php.net/manual/en/function.parse-str.php#122294) [¶](https://www.php.net/manual/en/function.parse-str.php#122294)\
\
**7 years ago**\
\
`proper_parse_str works great and I like that it doesn't replace spaces with underbars, but should urldecode $value`\
\
[up](https://www.php.net/manual/vote-note.php?id=99364&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=99364&page=function.parse-str&vote=down "Vote down!")\
\
 -1\
\
\
[**_Will Voelcker_**](https://www.php.net/manual/en/function.parse-str.php#99364) [¶](https://www.php.net/manual/en/function.parse-str.php#99364)\
\
**15 years ago**\
\
`If you need a function that does something similar to parse_str, but doesn't convert spaces and dots to underscores, try something like the following:\
<?php\
function parseQueryString($str) {\
    $op = array();\
    $pairs = explode("&", $str);\
    foreach ($pairs as $pair) {\
        list($k, $v) = array_map("urldecode", explode("=", $pair));\
        $op[$k] = $v;\
    }\
    return $op;\
}\
?>\
It may need adapting to handle various edge cases.`\
\
[up](https://www.php.net/manual/vote-note.php?id=64472&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=64472&page=function.parse-str&vote=down "Vote down!")\
\
 -1\
\
\
[**_motin at demomusic dot nu_**](https://www.php.net/manual/en/function.parse-str.php#64472) [¶](https://www.php.net/manual/en/function.parse-str.php#64472)\
\
**19 years ago**\
\
`When you have scripts run through the command-line (like locally via cron), you might want to be able to use _GET and _POST vars. Put this in top of your scheduled task files:\
<?\
    parse_str ($_SERVER['argv'][1], $GLOBALS['_GET']);\
    parse_str ($_SERVER['argv'][2], $GLOBALS['_POST']);\
?>\
And call your script by:\
/usr/local/bin/php /path/to/script.php "id=45&action=delete" "formsubmitted=true"\
Cheers!`\
\
[up](https://www.php.net/manual/vote-note.php?id=74818&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=74818&page=function.parse-str&vote=down "Vote down!")\
\
 -1\
\
\
[**_Michal Zalewski_**](https://www.php.net/manual/en/function.parse-str.php#74818) [¶](https://www.php.net/manual/en/function.parse-str.php#74818)\
\
**18 years ago**\
\
`Vladimir Kornea:\
Try use html_entity_decode()\
$str = 'first=value&amp;arr[]=foo+bar&amp;arr[]=baz';\
parse_str(html_entity_decode($str), $output);\
print_r($output);\
Array\
(\
    [first] => value\
    [arr] => Array\
        (\
            [0] => foo bar\
            [1] => baz\
        )\
)`\
\
[up](https://www.php.net/manual/vote-note.php?id=73151&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=73151&page=function.parse-str&vote=down "Vote down!")\
\
 -1\
\
\
[**_lenix.de_**](https://www.php.net/manual/en/function.parse-str.php#73151) [¶](https://www.php.net/manual/en/function.parse-str.php#73151)\
\
**18 years ago**\
\
`if you would like to get a nice url scheme with php/apache and and want to handle all requests in a central php script there's a simple solution/hack:\
create a .htaccess in your "basedir" where you've got your main script (in this example index.php) containing some lines like:\
"ErrorDocument 404 /index.php"\
inside index.php you can now do\
<?php\
    $virtual_path = substr(\
        $_SERVER['REQUEST_URI'],\
        strlen( dirname( $_SERVER['PHP_SELF'] ) ) + 1\
    );\
    if( ($pos = strpos( $virtual_path, '?' )) !== false ) {\
        parse_str( substr( $virtual_path, $pos + 1 ), $_GET );\
        $_REQUEST = array_merge( $_REQUEST, $_GET );\
        $virtual_path = substr( $virtual_path, 0, $pos );\
    }\
    // some code checking for a valid location, etc...\
    header( 'HTTP/1.1 200 OK' );\
    header( 'Content-Type: text/plain' );\
    echo $virtual_path."\n\n";\
    print_r( $_REQUEST );\
?>\
// guido 'lenix' boehm`\
\
[up](https://www.php.net/manual/vote-note.php?id=53346&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=53346&page=function.parse-str&vote=down "Vote down!")\
\
 -1\
\
\
[**_kerosuppi_**](https://www.php.net/manual/en/function.parse-str.php#53346) [¶](https://www.php.net/manual/en/function.parse-str.php#53346)\
\
**20 years ago**\
\
`This does not work as expected.\
<?php\
class someclass\
{\
    var $query_string;\
    function someclass($a_query_string)\
    {\
        $this->query_string = $a_query_string;\
        parse_str($this->query_string);\
    }\
    function output()\
    {\
        echo $this->action;\
    }\
}\
$a_class = new someclass("action=go");\
$a_class->output();\
?>\
Use this instead.\
<?php\
class someclass\
{\
    var $arr;\
    function someclass($a_query_string)\
    {\
        parse_str($a_query_string, $this->arr);\
    }\
    function output()\
    {\
        echo $this->arr['action'];\
    }\
}\
$a_class = new someclass("action=go");\
$a_class->output();\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=112568&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=112568&page=function.parse-str&vote=down "Vote down!")\
\
 -1\
\
\
[**_markc_**](https://www.php.net/manual/en/function.parse-str.php#112568) [¶](https://www.php.net/manual/en/function.parse-str.php#112568)\
\
**12 years ago**\
\
`Beware using parse_str in a function that has vars passed by reference. It seems that parse_str actually creates new vars even if vars of the same name exist. If you pass by ref vars of the same name as those in a query string being parsed new LOCAL vers will be created and you won't get any values passed back to the caller (relates to what Maikel mentioned below)\
An unrealistic example (vaguely related to what I was doing when I found this out)...\
function get_title($query,&$title)\
{\
parse_str($query);\
$title=str_replace("_"," ",$title);\
}\
$title="foo";\
$query = "context=something&title=Title_of_Something";\
get_title($query,$title);\
echo $title .... "foo"`\
\
[up](https://www.php.net/manual/vote-note.php?id=76481&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=76481&page=function.parse-str&vote=down "Vote down!")\
\
 -3\
\
\
[**_Vladimir Kornea_**](https://www.php.net/manual/en/function.parse-str.php#76481) [¶](https://www.php.net/manual/en/function.parse-str.php#76481)\
\
**18 years ago**\
\
`parse_str() is confused by ampersands (&) being encoded as HTML entities (&amp;). This is relevant if you're extracting your query string from an HTML page (scraping). The solution is to run the string through html_entity_decode() before running it through parse_str().\
(Editors: my original comment was a caution whose solution is obvious, but it has resulted in three replies ("so what?" "as intended" and "this is how to fix it"). Please remove the previous four posts dealing with this (69529, 70234, 72745, 74818) and leave just the above summary. This issue is too trivial to warrant the number of comments it has received.)`\
\
[up](https://www.php.net/manual/vote-note.php?id=46481&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=46481&page=function.parse-str&vote=down "Vote down!")\
\
 -2\
\
\
[**_anatilmizun at gmail dot com_**](https://www.php.net/manual/en/function.parse-str.php#46481) [¶](https://www.php.net/manual/en/function.parse-str.php#46481)\
\
**21 years ago**\
\
`I wrote a pair of functions using parse_str() that will write values in an array to a textfile and vice versa, read those values from the textfile back into the array. Quite useful if you need to store lots of data but don't have access to SQL.\
Save the array by calling cfg_save($filename,$array) and load it back using $array=cfg_load($filename)\
<?php\
$newline="?";\
function cfg_load($cfgfile){\
    global $newline;\
    $setting="";\
    if(file_exists($cfgfile)){\
        $setting=fopen($cfgfile, "r");\
        $ookk="";\
        while($ook=fgets($setting)){\
            #strip comment\
            $commt=strpos($ook,"##");\
            if($commt!==false) $ook=substr($ook,0,$commt);\
            #append\
            if($ook!="") $ookk=$ookk."&".    str_replace($newline,"\n",str_replace("&","%26",trim($ook)));\
        }\
        fclose($setting);\
        parse_str($ookk, $setting);\
    }\
    return $setting;\
}\
function cfg_save($cfgfile,$setting){\
    global $intArray;\
    $intArray="";\
    for($i=0;$i<2000;$i++)\
        $intArray[]=$i;\
    if(is_array($setting)){\
        $allkeys=array_keys($setting);\
        foreach($allkeys as $aKey)\
            cfg_recurse($setting[$aKey], $aKey, $outArray);\
    }\
    $cfgf=fopen($cfgfile,"w");\
    foreach($outArray as $aLine)\
        fputs($cfgf,stripslashes($aLine)."\r\n");\
    fclose($cfgf);\
}\
function cfg_recurse($stuffIn, $keysofar, &$toAppend){\
    global $intArray, $newline;\
    if(is_array($stuffIn)){\
        $allkeys=array_keys($stuffIn);\
        if(array_slice($intArray,0,sizeof($allkeys))==$allkeys)\
            $nokey=true;\
        else\
            $nokey=false;\
        foreach($allkeys as $aKey){\
            if(!$nokey) $toKey=$aKey;\
            cfg_recurse($stuffIn[$aKey], $keysofar."[".$toKey."]", $toAppend);\
        }\
    }else\
        $toAppend[]=$keysofar."=".str_replace("\n",$newline,$stuffIn);\
}\
?>\
Note that these functions support nested arrays of unlimited levels ;)`\
\
[up](https://www.php.net/manual/vote-note.php?id=108435&page=function.parse-str&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=108435&page=function.parse-str&vote=down "Vote down!")\
\
 -4\
\
\
[**_Benjamin Garcia_**](https://www.php.net/manual/en/function.parse-str.php#108435) [¶](https://www.php.net/manual/en/function.parse-str.php#108435)\
\
**13 years ago**\
\
`function like parse_str, but doesn't convert spaces and dots to underscores in $_GET AND $_POST\
/**\
* GET and POST input containing dots, etc.\
*/\
function getRealREQUEST() {\
    $vars = array();\
    $input    = $_SERVER['REDIRECT_QUERY_STRING'];\
    if(!empty($input)){\
        $pairs    = explode("&", $input);\
        foreach ($pairs     as $pair) {\
            $nv                = explode("=", $pair);\
\
            $name            = urldecode($nv[0]);\
            $nameSanitize    = preg_replace('/([^\[]*)\[.*$/','$1',$name);\
\
            $nameMatched    = str_replace('.','_',$nameSanitize);\
            $nameMatched    = str_replace(' ','_',$nameMatched);\
\
            $vars[$nameSanitize]    = $_REQUEST[$nameMatched];\
        }\
    }\
\
    $input    = file_get_contents("php://input");\
    if(!empty($input)){\
        $pairs    = explode("&", $input);\
        foreach ($pairs as $pair) {\
            $nv                = explode("=", $pair);\
\
            $name            = urldecode($nv[0]);\
            $nameSanitize    = preg_replace('/([^\[]*)\[.*$/','$1',$name);\
\
            $nameMatched    = str_replace('.','_',$nameSanitize);\
            $nameMatched    = str_replace(' ','_',$nameMatched);\
\
            $vars[$nameSanitize]    = $_REQUEST[$nameMatched];\
        }\
    }\
\
    return $vars;\
}`\
\
[＋add a note](https://www.php.net/manual/add-note.php?sect=function.parse-str&repo=en&redirect=https://www.php.net/manual/en/function.parse-str.php)\
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