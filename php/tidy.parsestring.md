---
url: https://www.php.net/manual/en/tidy.parsestring.php
scraped_at: 2025-10-20T02:48:42.097Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# tidy::parseString

# tidy\_parse\_string

(PHP 5, PHP 7, PHP 8, PECL tidy >= 0.5.2)

tidy::parseString \-\- tidy\_parse\_string — Parse a document stored in a string

### Description [¶](https://www.php.net/manual/en/tidy.parsestring.php\#refsect1-tidy.parsestring-description)

Object-oriented style

public**tidy::parseString**([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php)\|[null](https://www.php.net/manual/en/language.types.null.php) `$config` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$encoding` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Procedural style

**tidy\_parse\_string**([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php)\|[null](https://www.php.net/manual/en/language.types.null.php) `$config` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$encoding` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [tidy](https://www.php.net/manual/en/class.tidy.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Parses a document stored in a string.


### Parameters [¶](https://www.php.net/manual/en/tidy.parsestring.php\#refsect1-tidy.parsestring-parameters)

`string`

The data to be parsed.


`config`

The config `config` can be passed either as an
array or as a string. If a string is passed, it is interpreted as the
name of the configuration file, otherwise, it is interpreted as the
options themselves.


For an explanation about each option, visit [» http://api.html-tidy.org/#quick-reference](http://api.html-tidy.org/#quick-reference).


`encoding`

The `encoding` parameter sets the encoding for
input/output documents. The possible values for encoding are:
`ascii`, `latin0`, `latin1`,
`raw`, `utf8`, `iso2022`,
`mac`, `win1252`, `ibm858`,
`utf16`, `utf16le`, `utf16be`,
`big5`, and `shiftjis`.


### Return Values [¶](https://www.php.net/manual/en/tidy.parsestring.php\#refsect1-tidy.parsestring-returnvalues)

**tidy::parseString()** returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success.
**tidy\_parse\_string()** returns a new [tidy](https://www.php.net/manual/en/class.tidy.php)
instance on success.
Both, the method and the function return **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Changelog [¶](https://www.php.net/manual/en/tidy.parsestring.php\#refsect1-tidy.parsestring-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `config` and `encoding` are nullable now. |

### Examples [¶](https://www.php.net/manual/en/tidy.parsestring.php\#refsect1-tidy.parsestring-examples)

**Example #1 **tidy::parseString()** example**

`<?php
ob_start();
?>
<html>
<head>
<title>test</title>
</head>
<body>
<p>error<br>another line</i>
</body>
</html>
<?php
$buffer = ob_get_clean();
$config = array('indent' => TRUE,
                'output-xhtml' => TRUE,
                'wrap' => 200);
$tidy = tidy_parse_string($buffer, $config, 'UTF8');
$tidy->cleanRepair();
echo $tidy;
?>`

The above example will output:

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
  <head>
    <title>
      test
    </title>
  </head>
  <body>
    <p>
      error<br />
      another line
    </p>
  </body>
</html>
```

### See Also [¶](https://www.php.net/manual/en/tidy.parsestring.php\#refsect1-tidy.parsestring-seealso)

- [tidy::parseFile()](https://www.php.net/manual/en/tidy.parsefile.php) \- Parse markup in file or URI
- [tidy::repairFile()](https://www.php.net/manual/en/tidy.repairfile.php) \- Repair a file and return it as a string
- [tidy::repairString()](https://www.php.net/manual/en/tidy.repairstring.php) \- Repair a string using an optionally provided configuration file

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/tidy/tidy/parsestring.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ftidy.parsestring%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=tidy.parsestring&repo=en&redirect=https://www.php.net/manual/en/tidy.parsestring.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=129529&page=tidy.parsestring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129529&page=tidy.parsestring&vote=down "Vote down!")

0


[**_gbirch at tech-tamer dot com_**](https://www.php.net/manual/en/tidy.parsestring.php#129529) [¶](https://www.php.net/manual/en/tidy.parsestring.php#129529)

**1 year ago**

`The configuration reference for Tidy has moved to [https://api.html-tidy.org/](https://api.html-tidy.org/)`

[up](https://www.php.net/manual/vote-note.php?id=123021&page=tidy.parsestring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123021&page=tidy.parsestring&vote=down "Vote down!")

0


[**_steven at nevvix dot com_**](https://www.php.net/manual/en/tidy.parsestring.php#123021) [¶](https://www.php.net/manual/en/tidy.parsestring.php#123021)

**7 years ago**

`<?php
/**
* Simpler version without pretty print config options.
*/
function tidy_html5($html, array $config = [], $encoding = 'utf8') {
    $config += [\
        'doctype' => '<!DOCTYPE html>',\
        'drop-empty-elements' => 0,\
        'new-blocklevel-tags' => 'article aside audio bdi canvas details dialog figcaption figure footer header hgroup main menu menuitem nav section source summary template track video',\
        'new-empty-tags' => 'command embed keygen source track wbr',\
        'new-inline-tags' => 'audio command datalist embed keygen mark menuitem meter output progress source time video wbr',\
        'tidy-mark' => 0,\
    ];
    $html = tidy_parse_string($html, $config, $encoding); // doctype not inserted
    tidy_clean_repair($html); // doctype inserted
    return $html;
}
$html = '</z><p><a href="#">Link</a></p><p><img src="logo.png"/>Seçond para</p><i class="fa"></i><p></p>';
echo tidy_html5($html);
<!DOCTYPE html>
<html>
<head>
<title></title>
</head>
<body>
<p><a href="#">Link</a></p>
<p><img src="logo.png">Seçond para</p>
<i class="fa"></i>
<p></p>
</body>
</html>
echo tidy_html5($html, ['indent'=>2, 'indent-spaces'=>4]);
<!DOCTYPE html>
<html>
<head>
    <title></title>
</head>
<body>
    <p><a href="#">Link</a></p>
    <p><img src="logo.png">Seçond para</p><i class="fa"></i>
    <p></p>
</body>
</html>
echo tidy_html5($html, ['indent'=>1], 'ascii');
<!DOCTYPE html>
<html>
<head>
    <title></title>
</head>
<body>
    <p>
      <a href="#">Link</a>
    </p>
    <p>
      <img src="logo.png">Se&Atilde;&sect;ond para
    </p><i class="fa"></i>
    <p></p>
</body>
</html>
echo tidy_html5($html, ['show-body-only'=>1]);
<p><a href="#">Link</a></p>
<p><img src="logo.png">Seçond para</p>
<i class="fa"></i>
<p></p>`

[up](https://www.php.net/manual/vote-note.php?id=123020&page=tidy.parsestring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123020&page=tidy.parsestring&vote=down "Vote down!")

0


[**_steven at nevvix dot com_**](https://www.php.net/manual/en/tidy.parsestring.php#123020) [¶](https://www.php.net/manual/en/tidy.parsestring.php#123020)

**7 years ago**

`<?php
/**
* UTF-8 HTML5-compatible Tidy
*
* @param string $html
* @param array $config
* @param string $encoding
* @link [http://tidy.sourceforge.net/docs/quickref.html](http://tidy.sourceforge.net/docs/quickref.html)
*/
function tidy_html5($html, array $config = [], $encoding = 'utf8') {
    $config += [\
        'clean'       => TRUE,\
        'doctype'     => 'omit',\
        'indent'      => 2, // auto\
        'output-html' => TRUE,\
        'tidy-mark'   => FALSE,\
        'wrap'        => 0,\
        // HTML5 tags\
        'new-blocklevel-tags' => 'article aside audio bdi canvas details dialog figcaption figure footer header hgroup main menu menuitem nav section source summary template track video',\
        'new-empty-tags' => 'command embed keygen source track wbr',\
        'new-inline-tags' => 'audio command datalist embed keygen mark menuitem meter output progress source time video wbr',\
    ];
    $html = tidy_parse_string($html, $config, $encoding);
    tidy_clean_repair($html);
    return '<!DOCTYPE html>' . PHP_EOL . $html;
}
$html = '</z><p><a href="#">Link</a></p><p>Second para</p>';
echo tidy_html5($html);
Output:
<!DOCTYPE html>
<html>
<head>
<title></title>
</head>
<body>
<p><a href="#">Link</a></p>
<p>Second para</p>
</body>
</html>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=tidy.parsestring&repo=en&redirect=https://www.php.net/manual/en/tidy.parsestring.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google