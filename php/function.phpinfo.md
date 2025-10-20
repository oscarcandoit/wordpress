---
url: https://www.php.net/manual/en/function.phpinfo.php
scraped_at: 2025-10-20T02:39:31.299Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# phpinfo

(PHP 4, PHP 5, PHP 7, PHP 8)

phpinfo — Outputs information about PHP's configuration

### Description [¶](https://www.php.net/manual/en/function.phpinfo.php\#refsect1-function.phpinfo-description)

**phpinfo**([int](https://www.php.net/manual/en/language.types.integer.php) `$flags` = **`[INFO\_ALL](https://www.php.net/manual/en/info.constants.php#constant.info-all)`**): [true](https://www.php.net/manual/en/language.types.singleton.php)

Outputs a large amount of information about the current state of PHP.
This includes information about PHP compilation options and extensions,
the PHP version, server information and environment (if compiled as a
module), the PHP environment, OS version information, paths, master and
local values of configuration options, HTTP headers, and the PHP License.


Because every system is setup differently, **phpinfo()** is
commonly used to check [configuration settings](https://www.php.net/manual/en/configuration.php) and for available
[predefined variables](https://www.php.net/manual/en/language.variables.predefined.php)
on a given system.


**phpinfo()** is also a valuable debugging tool as it
contains all EGPCS (Environment, GET, POST, Cookie, Server) data.


### Parameters [¶](https://www.php.net/manual/en/function.phpinfo.php\#refsect1-function.phpinfo-parameters)

`flags`

The output may be customized by passing one or more of the
following _constants_ bitwise values summed
together in the optional `flags` parameter.
One can also combine the respective constants or bitwise values
together with the [bitwise or operator](https://www.php.net/manual/en/language.operators.bitwise.php).


| Name (constant) | Value | Description |
| --- | --- | --- |
| INFO\_GENERAL | 1 | The configuration line, php.ini location, build date, Web<br> Server, System and more. |
| INFO\_CREDITS | 2 | PHP Credits. See also [phpcredits()](https://www.php.net/manual/en/function.phpcredits.php). |
| INFO\_CONFIGURATION | 4 | Current Local and Master values for PHP directives. See<br> also [ini\_get()](https://www.php.net/manual/en/function.ini-get.php). |
| INFO\_MODULES | 8 | Loaded modules and their respective settings. See also<br> [get\_loaded\_extensions()](https://www.php.net/manual/en/function.get-loaded-extensions.php). |
| INFO\_ENVIRONMENT | 16 | Environment Variable information that's also available in<br> [$\_ENV](https://www.php.net/manual/en/reserved.variables.environment.php). |
| INFO\_VARIABLES | 32 | Shows all [predefined variables](https://www.php.net/manual/en/language.variables.predefined.php) from EGPCS (Environment, GET,<br> POST, Cookie, Server). |
| INFO\_LICENSE | 64 | PHP License information. See also the [» license FAQ](https://www.php.net/license/). |
| INFO\_ALL | -1 | Shows all of the above. |

****phpinfo()** options**

### Return Values [¶](https://www.php.net/manual/en/function.phpinfo.php\#refsect1-function.phpinfo-returnvalues)

Always returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.


### Examples [¶](https://www.php.net/manual/en/function.phpinfo.php\#refsect1-function.phpinfo-examples)

**Example #1 **phpinfo()** Example**

`<?php
// Show all information, defaults to INFO_ALL
phpinfo();
// Show just the module information.
// phpinfo(8) yields identical results.
phpinfo(INFO_MODULES);
?>`

### Notes [¶](https://www.php.net/manual/en/function.phpinfo.php\#refsect1-function.phpinfo-notes)

> **Note**:
>
>
> In versions of PHP before 5.5, parts of the information displayed are
> disabled when the [expose\_php](https://www.php.net/manual/en/ini.core.php#ini.expose-php)
> configuration setting is set to `off`. This includes the
> PHP and Zend logos, and the credits.

> **Note**:
>
>
> **phpinfo()** outputs plain text instead of HTML when
> using the CLI mode.

### See Also [¶](https://www.php.net/manual/en/function.phpinfo.php\#refsect1-function.phpinfo-seealso)

- [phpversion()](https://www.php.net/manual/en/function.phpversion.php) \- Gets the current PHP version
- [phpcredits()](https://www.php.net/manual/en/function.phpcredits.php) \- Prints out the credits for PHP
- [ini\_get()](https://www.php.net/manual/en/function.ini-get.php) \- Gets the value of a configuration option
- [ini\_set()](https://www.php.net/manual/en/function.ini-set.php) \- Sets the value of a configuration option
- [get\_loaded\_extensions()](https://www.php.net/manual/en/function.get-loaded-extensions.php) \- Returns an array with the names of all modules compiled and loaded
- [Predefined Variables](https://www.php.net/manual/en/language.variables.predefined.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/info/functions/phpinfo.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.phpinfo%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.phpinfo&repo=en&redirect=https://www.php.net/manual/en/function.phpinfo.php)

### User Contributed Notes 18 notes

[up](https://www.php.net/manual/vote-note.php?id=87287&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87287&page=function.phpinfo&vote=down "Vote down!")

17


[**_Phelon Dudras_**](https://www.php.net/manual/en/function.phpinfo.php#87287) [¶](https://www.php.net/manual/en/function.phpinfo.php#87287)

**16 years ago**

`A simple method to style your own phpinfo() output.
<style type="text/css">
#phpinfo {}
#phpinfo pre {}
#phpinfo a:link {}
#phpinfo a:hover {}
#phpinfo table {}
#phpinfo .center {}
#phpinfo .center table {}
#phpinfo .center th {}
#phpinfo td, th {}
#phpinfo h1 {}
#phpinfo h2 {}
#phpinfo .p {}
#phpinfo .e {}
#phpinfo .h {}
#phpinfo .v {}
#phpinfo .vr {}
#phpinfo img {}
#phpinfo hr {}
</style>
<div id="phpinfo">
<?php
ob_start () ;
phpinfo () ;
$pinfo = ob_get_contents () ;
ob_end_clean () ;
// the name attribute "module_Zend Optimizer" of an anker-tag is not xhtml valide, so replace it with "module_Zend_Optimizer"
echo ( str_replace ( "module_Zend Optimizer", "module_Zend_Optimizer", preg_replace ( '%^.*<body>(.*)</body>.*$%ms', '$1', $pinfo ) ) ) ;
?>
</div>`

[up](https://www.php.net/manual/vote-note.php?id=128042&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128042&page=function.phpinfo&vote=down "Vote down!")

4


[**_alec dot hewitt at gmail dot com_**](https://www.php.net/manual/en/function.phpinfo.php#128042) [¶](https://www.php.net/manual/en/function.phpinfo.php#128042)

**2 years ago**

``Simple JS snippet to print phpinfo() inline with it's styles renamed. Thus leaving the container page unaffected and pretty.
<script>
document.write(`<div id="phpinfo"><?php phpinfo(61) ?></div>`);
var x = document.querySelector('#phpinfo > style');
x.innerText = x.innerText.replaceAll('\n', '#phpinfo ');
</script>``

[up](https://www.php.net/manual/vote-note.php?id=59573&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=59573&page=function.phpinfo&vote=down "Vote down!")

10


[**_code at adspeed dot com_**](https://www.php.net/manual/en/function.phpinfo.php#59573) [¶](https://www.php.net/manual/en/function.phpinfo.php#59573)

**19 years ago**

`This function parses the phpinfo output to get details about a PHP module.
<?php
/** parse php modules from phpinfo */
function parsePHPModules() {
ob_start();
phpinfo(INFO_MODULES);
$s = ob_get_contents();
ob_end_clean();

$s = strip_tags($s,'<h2><th><td>');
$s = preg_replace('/<th[^>]*>([^<]+)<\/th>/',"<info>\\1</info>",$s);
$s = preg_replace('/<td[^>]*>([^<]+)<\/td>/',"<info>\\1</info>",$s);
$vTmp = preg_split('/(<h2>[^<]+<\/h2>)/',$s,-1,PREG_SPLIT_DELIM_CAPTURE);
$vModules = array();
for ($i=1;$i<count($vTmp);$i++) {
if (preg_match('/<h2>([^<]+)<\/h2>/',$vTmp[$i],$vMat)) {
$vName = trim($vMat[1]);
$vTmp2 = explode("\n",$vTmp[$i+1]);
foreach ($vTmp2 AS $vOne) {
    $vPat = '<info>([^<]+)<\/info>';
    $vPat3 = "/$vPat\s*$vPat\s*$vPat/";
    $vPat2 = "/$vPat\s*$vPat/";
    if (preg_match($vPat3,$vOne,$vMat)) { // 3cols
     $vModules[$vName][trim($vMat[1])] = array(trim($vMat[2]),trim($vMat[3]));
    } elseif (preg_match($vPat2,$vOne,$vMat)) { // 2cols
     $vModules[$vName][trim($vMat[1])] = trim($vMat[2]);
    }
}
}
}
return $vModules;
}
?>
Sample Output:
[gd] => Array
(
[GD Support] => enabled
[GD Version] => bundled (2.0.28 compatible)
[FreeType Support] => enabled
[FreeType Linkage] => with freetype
[FreeType Version] => 2.1.9
[T1Lib Support] => enabled
[GIF Read Support] => enabled
[GIF Create Support] => enabled
[JPG Support] => enabled
[PNG Support] => enabled
[WBMP Support] => enabled
[XBM Support] => enabled
)
[date] => Array (
[date/time support] => enabled
[Timezone Database Version] => 2005.14
[Timezone Database] => internal
[Default timezone] => America/Los_Angeles
[Directive] => Array (
     [0] => Local Value
     [1] => Master Value
)
[date.timezone] => Array (
     [0] => no value
     [1] => no value
)
)
<?php
/** get a module setting */
function getModuleSetting($pModuleName,$pSetting) {
$vModules = parsePHPModules();
return $vModules[$pModuleName][$pSetting];
}
?>
Example: getModuleSetting('gd','GD Version'); returns "bundled (2.0.28 compatible)"`

[up](https://www.php.net/manual/vote-note.php?id=114915&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114915&page=function.phpinfo&vote=down "Vote down!")

7


[**_cbar at vmait dot com_**](https://www.php.net/manual/en/function.phpinfo.php#114915) [¶](https://www.php.net/manual/en/function.phpinfo.php#114915)

**11 years ago**

`<?php
// NOTE: When accessing a element from the above phpinfo_array(), you can do:
$array = phpinfo_array();
// This will work
echo $array["General"]["System "];
// This should work also, but it doesn't because there is a space after System in the array.
echo $array["General"]["System"];
// I hope the coder will fix it, so as to save someone else from wasting time. Otherwise, nice script.

?>`

[up](https://www.php.net/manual/vote-note.php?id=57532&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=57532&page=function.phpinfo&vote=down "Vote down!")

8


[**_Helpful Harry_**](https://www.php.net/manual/en/function.phpinfo.php#57532) [¶](https://www.php.net/manual/en/function.phpinfo.php#57532)

**20 years ago**

`check out this cool and fantastic colourful phpinfo()!
<?php
ob_start();
phpinfo();
$phpinfo = ob_get_contents();
ob_end_clean();
preg_match_all('/#[0-9a-fA-F]{6}/', $phpinfo, $rawmatches);
for ($i = 0; $i < count($rawmatches[0]); $i++)
$matches[] = $rawmatches[0][$i];
$matches = array_unique($matches);
$hexvalue = '0123456789abcdef';
$j = 0;
foreach ($matches as $match)
{
$r = '#';
$searches[$j] = $match;
for ($i = 0; $i < 6; $i++)
      $r .= substr($hexvalue, mt_rand(0, 15), 1);
$replacements[$j++] = $r;
unset($r);
}
for ($i = 0; $i < count($searches); $i++)
$phpinfo = str_replace($searches, $replacements, $phpinfo);
echo $phpinfo;
?>`

[up](https://www.php.net/manual/vote-note.php?id=84000&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84000&page=function.phpinfo&vote=down "Vote down!")

5


[**_yurkins_**](https://www.php.net/manual/en/function.phpinfo.php#84000) [¶](https://www.php.net/manual/en/function.phpinfo.php#84000)

**17 years ago**

`big thanx 2 Mardy dot Hutchinson at gmail dot com
very good!
some fixes to correct result displaying:
1. we need to trim $matches [1], 'cause there can be empty lines;
2. not bad to remove <body> tag 'cause styles for it not apply correctly...
3. ...and change styles a little (remove "body" selector)
we need to change two lines:
<?php
preg_match ('%<style type="text/css">(.*?)</style>.*?(<body>.*</body>)%s', ob_get_clean(), $matches);
?>
to
<?php
preg_match ('%<style type="text/css">(.*?)</style>.*?<body>(.*?)</body>%s', ob_get_clean(), $matches);
?>
and
<?php
preg_split( '/\n/', $matches[1] )
?>
to
<?php
preg_split( '/\n/', trim(preg_replace( "/\nbody/", "\n", $matches[1])) )
?>
That's all! Now we have a really flexible addition to phpinfo();`

[up](https://www.php.net/manual/vote-note.php?id=84259&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84259&page=function.phpinfo&vote=down "Vote down!")

6


[**_jon at sitewizard dot ca_**](https://www.php.net/manual/en/function.phpinfo.php#84259) [¶](https://www.php.net/manual/en/function.phpinfo.php#84259)

**17 years ago**

`To extract all of the data from phpinfo into a nested array:
<?php
ob_start();
phpinfo();
$phpinfo = array('phpinfo' => array());
if(preg_match_all('#(?:<h2>(?:<a name=".*?">)?(.*?)(?:</a>)?</h2>)|(?:<tr(?: class=".*?")?><t[hd](?: class=".*?")?>(.*?)\s*</t[hd]>(?:<t[hd](?: class=".*?")?>(.*?)\s*</t[hd]>(?:<t[hd](?: class=".*?")?>(.*?)\s*</t[hd]>)?)?</tr>)#s', ob_get_clean(), $matches, PREG_SET_ORDER))
    foreach($matches as $match)
        if(strlen($match[1]))
            $phpinfo[$match[1]] = array();
        elseif(isset($match[3]))
            $phpinfo[end(array_keys($phpinfo))][$match[2]] = isset($match[4]) ? array($match[3], $match[4]) : $match[3];
        else
            $phpinfo[end(array_keys($phpinfo))][] = $match[2];
?>
Some examples of using individual values from the array:
<?php
    echo "System: {$phpinfo['phpinfo']['System']}<br />\n";
    echo "Safe Mode: {$phpinfo['PHP Core']['safe_mode'][0]}<br />\n";
    echo "License: {$phpinfo['PHP License'][0]}<br />\n";
?>
To display everything:
<?php
    foreach($phpinfo as $name => $section) {
        echo "<h3>$name</h3>\n<table>\n";
        foreach($section as $key => $val) {
            if(is_array($val))
                echo "<tr><td>$key</td><td>$val[0]</td><td>$val[1]</td></tr>\n";
            elseif(is_string($key))
                echo "<tr><td>$key</td><td>$val</td></tr>\n";
            else
                echo "<tr><td>$val</td></tr>\n";
        }
        echo "</table>\n";
    }
?>
Note: In order to properly retrieve all of the data, the regular expression matches table headers as well as table data, resulting in 'Local Value' and 'Global Value' showing up as 'Directive' entries.`

[up](https://www.php.net/manual/vote-note.php?id=70306&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70306&page=function.phpinfo&vote=down "Vote down!")

5


[**_jb2386 at hotmail dot com_**](https://www.php.net/manual/en/function.phpinfo.php#70306) [¶](https://www.php.net/manual/en/function.phpinfo.php#70306)

**19 years ago**

`This is a slight modification to the previous code by "code at adspeed dot com" that extracts the PHP modules as an array. I used it on PHP 4.1.2 and it failed as the <h2> tags also had an align="center". So this update changes the regex for those tags:
<?php
/* parse php modules from phpinfo */
function parsePHPModules() {
ob_start();
phpinfo(INFO_MODULES);
$s = ob_get_contents();
ob_end_clean();
$s = strip_tags($s,'<h2><th><td>');
$s = preg_replace('/<th[^>]*>([^<]+)<\/th>/',"<info>\\1</info>",$s);
$s = preg_replace('/<td[^>]*>([^<]+)<\/td>/',"<info>\\1</info>",$s);
$vTmp = preg_split('/(<h2[^>]*>[^<]+<\/h2>)/',$s,-1,PREG_SPLIT_DELIM_CAPTURE);
$vModules = array();
for ($i=1;$i<count($vTmp);$i++) {
if (preg_match('/<h2[^>]*>([^<]+)<\/h2>/',$vTmp[$i],$vMat)) {
$vName = trim($vMat[1]);
$vTmp2 = explode("\n",$vTmp[$i+1]);
foreach ($vTmp2 AS $vOne) {
$vPat = '<info>([^<]+)<\/info>';
$vPat3 = "/$vPat\s*$vPat\s*$vPat/";
$vPat2 = "/$vPat\s*$vPat/";
if (preg_match($vPat3,$vOne,$vMat)) { // 3cols
     $vModules[$vName][trim($vMat[1])] = array(trim($vMat[2]),trim($vMat[3]));
} elseif (preg_match($vPat2,$vOne,$vMat)) { // 2cols
     $vModules[$vName][trim($vMat[1])] = trim($vMat[2]);
}
}
}
}
return $vModules;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=121679&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121679&page=function.phpinfo&vote=down "Vote down!")

4


[**_keinwort at hotmail dot com_**](https://www.php.net/manual/en/function.phpinfo.php#121679) [¶](https://www.php.net/manual/en/function.phpinfo.php#121679)

**8 years ago**

`REMARK/INFO: if Content-Security-Policy HTTP header
is
Content-Security-Policy "default-src 'self';";
phpinfo() is shown without a table`

[up](https://www.php.net/manual/vote-note.php?id=100809&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100809&page=function.phpinfo&vote=down "Vote down!")

3


[**_arimbourg at ariworld dot eu_**](https://www.php.net/manual/en/function.phpinfo.php#100809) [¶](https://www.php.net/manual/en/function.phpinfo.php#100809)

**14 years ago**

`This is necessary to obtain a W3C validation (XHTML1.0 Transitionnal)...
phpinfo's output is declared with that DTD :
- "System ID" has the wrong url to validate : "DTD/xhtml1-transitional.dtd" rather than " [http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd](http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd)"
- Some module names contains space and the function's output use the name in anchors as ID and NAME. these attributes can't be validated like that (unique name only).
<?php
ob_start ();
ob_start ();                              // Capturing
phpinfo ();                               // phpinfo ()
$info = trim (ob_get_clean ());           // output
// Replace white space in ID and NAME attributes... if exists
$info = preg_replace ('/(id|name)(=["\'][^ "\']+) ([^ "\']*["\'])/i', '$1$2_$3', $info);
$imp = new DOMImplementation ();
$dtd = $imp->createDocumentType (
    'html',
    '-//W3C//DTD XHTML 1.0 Transitional//EN',
    ' [http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd](http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd)'
);
$doc = $imp->createDocument (
    ' [http://www.w3.org/1999/xhtml](http://www.w3.org/1999/xhtml)',
    'html',
    $dtd
);
$doc->encoding = 'utf-8';
$info_doc = new DOMDocument ('1.0', 'utf-8');
/* Parse phpinfo's output
* operator @ used to avoid messages about undefined entities
* or use loadHTML instead
*/
@$info_doc->loadXML ($info);
$doc->documentElement->appendChild ( // Adding HEAD element to HTML
    $doc->importNode (
        $info_doc->getElementsByTagName ('head')->item (0),
        true                         // With all the subtree
    )
);
$doc->documentElement->appendChild ( // Adding BODY element to HTML
    $doc->importNode (
        $info_doc->getElementsByTagName ('body')->item (0),
        true                         // With all the subtree
    )
);
// Now you get a clean output and you are able to validate...
/*
echo ($doc->saveXML ());
//      OR
echo ($doc->saveHTML ());
*/
// By that way it's easy to add some style declaration :
$style = $doc->getElementsByTagName ('style')->item (0);
$style->appendChild (
    $doc->createTextNode (
        '/* SOME NEW CSS RULES TO ADD TO THE FUNCTION OUTPUT */'
    )
);
// to add some more informations to display :
$body = $doc->getElementsByTagName ('body')->item (0);
$element = $doc->createElement ('p');
$element->appendChild (
    $doc->createTextNode (
        'SOME NEW CONTENT TO DISPLAY'
    )
);
$body->appendChild ($element);
// to add a new header :
$head = $doc->getElementsByTagName ('head')->item (0);
$meta = $doc->createElement ('meta');
$meta->setAttribute ('name', 'author');
$meta->setAttribute ('content', 'arimbourg at ariworld dot eu');
$head->appendChild ($meta);
// As you wish, take the rest of the output and add it for debugging
$out = ob_get_clean ();
$pre = $doc->createElement ('div'); // or pre
$pre->setAttribute ('style', 'white-space: pre;'); // for a div element, useless with pre
$pre->appendChild ($doc->createTextNode ($out));
$body->appendChild ($pre);
$doc->formatOutput = true; // For a nice indentation
$doc->saveXML ();
?>
All that could be done with only RegExp but I prefer the use of DOM for manipulating documents`

[up](https://www.php.net/manual/vote-note.php?id=112019&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112019&page=function.phpinfo&vote=down "Vote down!")

2


[**_SimonD_**](https://www.php.net/manual/en/function.phpinfo.php#112019) [¶](https://www.php.net/manual/en/function.phpinfo.php#112019)

**12 years ago**

`Removes sensitive data like AUTH_USER and AUTH_PASSWORD from the phpinfo output:
<?php
// start output buffering
ob_start();
// send phpinfo content
phpinfo();
// get phpinfo content
$html = ob_get_contents();
// flush the output buffer
ob_end_clean();
// remove auth data
if (isset($_SERVER['AUTH_USER'])) $html = str_replace($_SERVER['AUTH_USER'], '<i>no value</i>', $html);
if (isset($_SERVER['AUTH_PASSWORD'])) $html = str_replace($_SERVER['AUTH_PASSWORD'], '<i>no value</i>', $html);
echo $html;`

[up](https://www.php.net/manual/vote-note.php?id=116869&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116869&page=function.phpinfo&vote=down "Vote down!")

2


[**_Joseph Reilly_**](https://www.php.net/manual/en/function.phpinfo.php#116869) [¶](https://www.php.net/manual/en/function.phpinfo.php#116869)

**10 years ago**

`One note on the very useful example by "jon at sitewizard dot ca".
The following statements:
Statement 1:
$phpinfo[end(array_keys($phpinfo))][$match[2]] = isset($match[4]) ? array($match[3], $match[4]) : $match[3];
Statement 2:
$phpinfo[end(array_keys($phpinfo))][] = $match[2];
These two lines will produce the error "Strict Standards:  Only variables should be passed by reference in...".  The root of the error is in the incorrect use of the end() function. The code works but thows the said error.
To address this try using the following statements:
Statement 1 revision:
$keys = array_keys($phpinfo);
$phpinfo[end($keys)][$match[2]] = isset($match[4]) ? array($match[3], $match[4]) : $match[3];
Statement 2 revision:
$keys = array_keys($phpinfo);
$phpinfo[end($keys)][] = $match[2];
This fixes the error.
To wrap it all in an example:
<?php
function quick_dev_insights_phpinfo() {
ob_start();
phpinfo(11);
$phpinfo = array('phpinfo' => array());
    if(preg_match_all('#(?:<h2>(?:<a name=".*?">)?(.*?)(?:</a>)?</h2>)|(?:<tr(?: class=".*?")?><t[hd](?: class=".*?")?>(.*?)\s*</t[hd]>(?:<t[hd](?: class=".*?")?>(.*?)\s*</t[hd]>(?:<t[hd](?: class=".*?")?>(.*?)\s*</t[hd]>)?)?</tr>)#s', ob_get_clean(), $matches, PREG_SET_ORDER)){
        foreach($matches as $match){
        if(strlen($match[1])){
            $phpinfo[$match[1]] = array();
        }elseif(isset($match[3])){
        $keys1 = array_keys($phpinfo);
        $phpinfo[end($keys1)][$match[2]] = isset($match[4]) ? array($match[3], $match[4]) : $match[3];
        }else{
            $keys1 = array_keys($phpinfo);
            $phpinfo[end($keys1)][] = $match[2];

        }

        }
}
    if(! empty($phpinfo)){
        foreach($phpinfo as $name => $section) {
            echo "<h3>$name</h3>\n<table class='wp-list-table widefat fixed pages'>\n";
            foreach($section as $key => $val){
                    if(is_array($val)){
                    echo "<tr><td>$key</td><td>$val[0]</td><td>$val[1]</td></tr>\n";
                    }elseif(is_string($key)){
                    echo "<tr><td>$key</td><td>$val</td></tr>\n";
                    }else{
                    echo "<tr><td>$val</td></tr>\n";
                }
            }
        }
            echo "</table>\n";
        }else{
    echo "<h3>Sorry, the phpinfo() function is not accessable. Perhaps, it is disabled<a href=' [http://php.net/manual/en/function.phpinfo.php](http://php.net/manual/en/function.phpinfo.php)'>See the documentation.</a></h3>";
    }
}
?>
Frankly, I went thought the trouble of adding this note because the example by "jon at sitewizard dot ca"  is probably the best on the web, and thought it unfortunate that it throws errors. Hope this is useful to someone.`

[up](https://www.php.net/manual/vote-note.php?id=106862&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106862&page=function.phpinfo&vote=down "Vote down!")

2


[**_Ken_**](https://www.php.net/manual/en/function.phpinfo.php#106862) [¶](https://www.php.net/manual/en/function.phpinfo.php#106862)

**13 years ago**

`Hi.
Here my version of saving php_info into an array:
<?php
function phpinfo_array()
{
    ob_start();
    phpinfo();
    $info_arr = array();
    $info_lines = explode("\n", strip_tags(ob_get_clean(), "<tr><td><h2>"));
    $cat = "General";
    foreach($info_lines as $line)
    {
        // new cat?
        preg_match("~<h2>(.*)</h2>~", $line, $title) ? $cat = $title[1] : null;
        if(preg_match("~<tr><td[^>]+>([^<]*)</td><td[^>]+>([^<]*)</td></tr>~", $line, $val))
        {
            $info_arr[$cat][$val[1]] = $val[2];
        }
        elseif(preg_match("~<tr><td[^>]+>([^<]*)</td><td[^>]+>([^<]*)</td><td[^>]+>([^<]*)</td></tr>~", $line, $val))
        {
            $info_arr[$cat][$val[1]] = array("local" => $val[2], "master" => $val[3]);
        }
    }
    return $info_arr;
}
// example:
echo "<pre>".print_r(phpinfo_array(), 1)."</pre>";
?>`

[up](https://www.php.net/manual/vote-note.php?id=116715&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116715&page=function.phpinfo&vote=down "Vote down!")

0


[**_LewisR_**](https://www.php.net/manual/en/function.phpinfo.php#116715) [¶](https://www.php.net/manual/en/function.phpinfo.php#116715)

**10 years ago**

`Building on SimonD's elegant example to hide the logged-in username and password, which otherwise appear in plain text, the following should work for PHP 5.4+:
<?php
    // start output buffering
    ob_start();
    // send phpinfo content
    phpinfo();
    // get phpinfo content
    $html = ob_get_contents();
    // flush the output buffer
    ob_end_clean();
    // remove auth data
    if ( isset( $_SERVER[ 'PHP_AUTH_USER' ] ) ) $html = str_replace( $_SERVER[ 'PHP_AUTH_USER' ], '[ protected ]' , $html);
    if ( isset( $_SERVER[ 'PHP_AUTH_PW' ] ) ) $html = str_replace( $_SERVER[ 'PHP_AUTH_PW' ], '[ protected ]' , $html);
    echo $html;
?>
To remove additional items, just add them as above.`

[up](https://www.php.net/manual/vote-note.php?id=77705&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77705&page=function.phpinfo&vote=down "Vote down!")

0


[**_Mardy dot Hutchinson at gmail dot com_**](https://www.php.net/manual/en/function.phpinfo.php#77705) [¶](https://www.php.net/manual/en/function.phpinfo.php#77705)

**18 years ago**

`Embedding phpinfo within your page, that already has style information:
The phpinfo output is wrapped within a <div class='phpinfodisplay'>, and we privatize all the style selectors that phpinfo() creates.
Yes, we cheat on preparing the selector list.
<?php
ob_start();
phpinfo();
preg_match ('%<style type="text/css">(.*?)</style>.*?(<body>.*</body>)%s', ob_get_clean(), $matches);
# $matches [1]; # Style information
# $matches [2]; # Body information
echo "<div class='phpinfodisplay'><style type='text/css'>\n",
    join( "\n",
        array_map(
            create_function(
                '$i',
                'return ".phpinfodisplay " . preg_replace( "/,/", ",.phpinfodisplay ", $i );'
                ),
            preg_split( '/\n/', $matches[1] )
            )
        ),
    "</style>\n",
    $matches[2],
    "\n</div>\n";
?>
Perhaps one day the phpinfo() function will be modified to output such a safe string on its own.`

[up](https://www.php.net/manual/vote-note.php?id=117961&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117961&page=function.phpinfo&vote=down "Vote down!")

 -2


[**_Calin S._**](https://www.php.net/manual/en/function.phpinfo.php#117961) [¶](https://www.php.net/manual/en/function.phpinfo.php#117961)

**10 years ago**

`After reading and trying various functions, I couldn't find one that correctly parses all the configurations, strips any left-over html tag and converts special characters into UTF8 (e.g. &#039; into '), so I created my own by improving on the existing ones:
function phpinfo2array() {
    $entitiesToUtf8 = function($input) {
        // [http://php.net/manual/en/function.html-entity-decode.php#104617](http://php.net/manual/en/function.html-entity-decode.php#104617)
        return preg_replace_callback("/(&#[0-9]+;)/", function($m) { return mb_convert_encoding($m[1], "UTF-8", "HTML-ENTITIES"); }, $input);
    };
    $plainText = function($input) use ($entitiesToUtf8) {
        return trim(html_entity_decode($entitiesToUtf8(strip_tags($input))));
    };
    $titlePlainText = function($input) use ($plainText) {
        return '# '.$plainText($input);
    };

    ob_start();
    phpinfo(-1);

    $phpinfo = array('phpinfo' => array());
    // Strip everything after the <h1>Configuration</h1> tag (other h1's)
    if (!preg_match('#(.*<h1[^>]*>\s*Configuration.*)<h1#s', ob_get_clean(), $matches)) {
        return array();
    }

    $input = $matches[1];
    $matches = array();
    if(preg_match_all(
        '#(?:<h2.*?>(?:<a.*?>)?(.*?)(?:<\/a>)?<\/h2>)|'.
        '(?:<tr.*?><t[hd].*?>(.*?)\s*</t[hd]>(?:<t[hd].*?>(.*?)\s*</t[hd]>(?:<t[hd].*?>(.*?)\s*</t[hd]>)?)?</tr>)#s',
        $input,
        $matches,
        PREG_SET_ORDER
    )) {
        foreach ($matches as $match) {
            $fn = strpos($match[0], '<th') === false ? $plainText : $titlePlainText;
            if (strlen($match[1])) {
                $phpinfo[$match[1]] = array();
            } elseif (isset($match[3])) {
                $keys1 = array_keys($phpinfo);
                $phpinfo[end($keys1)][$fn($match[2])] = isset($match[4]) ? array($fn($match[3]), $fn($match[4])) : $fn($match[3]);
            } else {
                $keys1 = array_keys($phpinfo);
                $phpinfo[end($keys1)][] = $fn($match[2]);
            }
        }
    }

    return $phpinfo;
}
The output looks something like this (note the headers are also included but are prefixed with '# ', e.g. '# Directive'):
Array
(
    [phpinfo] => Array
        (
            [0] => PHP Version 5.6.5
            [System] => Darwin Calins-MBP 15.0.0 Darwin Kernel Version 15.0.0: Wed Aug 26 19:41:34 PDT 2015; root:xnu-3247.1.106~5/RELEASE_X86_64 x86_64
            [Build Date] => Feb 19 2015 18:34:18
            [Registered Stream Socket Transports] => tcp, udp, unix, udg, ssl, sslv3, sslv2, tls, tlsv1.0
            [Registered Stream Filters] => zlib.*, bzip2.*, convert.iconv.*, string.rot13, string.toupper, string.tolower, string.strip_tags, convert.*, consumed, dechunk
            [1] => This program makes use of the Zend Scripting Language Engine:Zend Engine...
        )
    [apache2handler] => Array
        (
            [Apache Version] => Apache/2.4.16 (Unix) PHP/5.6.5 OpenSSL/0.9.8zg
            [Apache API Version] => 20120211
            [Server Administrator] => webmaster@dummy-host2.example.com
            [Hostname:Port] => sitestacker.local:0
            [# Directive] => Array
                (
                    [0] => # Local Value
                    [1] => # Master Value
                )
            [engine] => Array
                (
                    [0] => 1
                    [1] => 1
                )
            [last_modified] => Array
                (
                    [0] => 0
                    [1] => 0
                )`

[up](https://www.php.net/manual/vote-note.php?id=77692&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77692&page=function.phpinfo&vote=down "Vote down!")

 -1


[**_Andrew dot Boag at catalyst dot net dot nz_**](https://www.php.net/manual/en/function.phpinfo.php#77692) [¶](https://www.php.net/manual/en/function.phpinfo.php#77692)

**18 years ago**

`One note on the above functions for cleaning up the phpinfo() HTML and throwing it into an array data structure. In order to catch all of the info tidbits the preg_match_all has to be tweaked to deal with 2 and 3 column tables.
I have changed the preg_match_all() here so that the last <td></td> is optional
<?php
function parsePHPConfig() {
    ob_start();
    phpinfo(-1);
    $s = ob_get_contents();
    ob_end_clean();
    $a = $mtc = array();
    if (preg_match_all('/<tr><td class="e">(.*?)<\/td><td class="v">(.*?)<\/td>(:?<td class="v">(.*?)<\/td>)?<\/tr>/',$s,$mtc,PREG_SET_ORDER))
        foreach($mtc as $v){
            if($v[2] == '<i>no value</i>') continue;
            $a[$v[1]] = $v[2];
        }
    }
    return $a;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=87463&page=function.phpinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87463&page=function.phpinfo&vote=down "Vote down!")

 -3


[**_webmaster at askapache dot com_**](https://www.php.net/manual/en/function.phpinfo.php#87463) [¶](https://www.php.net/manual/en/function.phpinfo.php#87463)

**16 years ago**

`I wanted a simple *function* to convert the output of phpinfo into an array.  Here's what I came up with thanks to alot of the previous authors tips, and the source file: php-5.2.6/ext/standard/info.c
Call this function like phpinfo_array() prints the array, phpinfo_array(1) returns the array for your own processing.
== Sample Output ==
[PHP Configuration] => Array
(
[PHP Version] => 5.2.6
[PHP Egg] => PHPE9568F34-D428-11d2-A769-00AA001ACF42
[System] => Linux askapache 2.6.22.19-grsec3
[Build Date] => Nov 11 2008 13:09:07
[Configure Command] =>  ./configure --prefix=/home/grsec/bin/php
[Server API] => FastCGI
[IPv6 Support] => enabled
[Zend Egg] => PHPE9568F35-D428-11d2-A769-00AA001ACF42
[PHP Credits Egg] => PHPB8B5F2A0-3C92-11d3-A3A9-4C7B08C10000
)
[mbstring] => Array
(
[mbstring.http_input] => pass
[mbstring.internal_encoding] => Array
    (
     [0] => ISO-8859-1
     [1] => no value
    )
[mbstring.language] => neutral
)
[mcrypt] => Array
(
[Version] => 3.5.7
[Api No] => 20031217
)
<?php
function phpinfo_array($return=false){
/* Andale!  Andale!  Yee-Hah! */
ob_start();
phpinfo(-1);

$pi = preg_replace(
array('#^.*<body>(.*)</body>.*$#ms', '#<h2>PHP License</h2>.*$#ms',
'#<h1>Configuration</h1>#',  "#\r?\n#", "#</(h1|h2|h3|tr)>#", '# +<#',
"#[ \t]+#", '#&nbsp;#', '#  +#', '# class=".*?"#', '%&#039;%',
'#<tr>(?:.*?)" src="(?:.*?)=(.*?)" alt="PHP Logo" /></a>'
.'<h1>PHP Version (.*?)</h1>(?:\n+?)</td></tr>#',
'#<h1><a href="(?:.*?)\?=(.*?)">PHP Credits</a></h1>#',
'#<tr>(?:.*?)" src="(?:.*?)=(.*?)"(?:.*?)Zend Engine (.*?),(?:.*?)</tr>#',
"# +#", '#<tr>#', '#</tr>#'),
array('$1', '', '', '', '</$1>' . "\n", '<', ' ', ' ', ' ', '', ' ',
'<h2>PHP Configuration</h2>'."\n".'<tr><td>PHP Version</td><td>$2</td></tr>'.
"\n".'<tr><td>PHP Egg</td><td>$1</td></tr>',
'<tr><td>PHP Credits Egg</td><td>$1</td></tr>',
'<tr><td>Zend Engine</td><td>$2</td></tr>' . "\n" .
'<tr><td>Zend Egg</td><td>$1</td></tr>', ' ', '%S%', '%E%'),
ob_get_clean());
$sections = explode('<h2>', strip_tags($pi, '<h2><th><td>'));
unset($sections[0]);
$pi = array();
foreach($sections as $section){
$n = substr($section, 0, strpos($section, '</h2>'));
preg_match_all(
'#%S%(?:<td>(.*?)</td>)?(?:<td>(.*?)</td>)?(?:<td>(.*?)</td>)?%E%#',
     $section, $askapache, PREG_SET_ORDER);
foreach($askapache as $m)
       $pi[$n][$m[1]]=(!isset($m[3])||$m[2]==$m[3])?$m[2]:array_slice($m,2);
}
return ($return === false) ? print_r($pi) : $pi;
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.phpinfo&repo=en&redirect=https://www.php.net/manual/en/function.phpinfo.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google