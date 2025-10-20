---
url: https://www.php.net/manual/en/function.get-loaded-extensions.php
scraped_at: 2025-10-20T02:35:47.896Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# get\_loaded\_extensions

(PHP 4, PHP 5, PHP 7, PHP 8)

get\_loaded\_extensions — Returns an array with the names of all modules compiled and loaded

### Description [¶](https://www.php.net/manual/en/function.get-loaded-extensions.php\#refsect1-function.get-loaded-extensions-description)

**get\_loaded\_extensions**([bool](https://www.php.net/manual/en/language.types.boolean.php) `$zend_extensions` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**): [array](https://www.php.net/manual/en/language.types.array.php)

This function returns the names of all the modules compiled and
loaded in the PHP interpreter.


### Parameters [¶](https://www.php.net/manual/en/function.get-loaded-extensions.php\#refsect1-function.get-loaded-extensions-parameters)

`zend_extensions`

Only return Zend extensions, if not then regular extensions, like
mysqli are listed. Defaults to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** (return regular extensions).


### Return Values [¶](https://www.php.net/manual/en/function.get-loaded-extensions.php\#refsect1-function.get-loaded-extensions-returnvalues)

Returns an indexed array of all the modules names.


### Examples [¶](https://www.php.net/manual/en/function.get-loaded-extensions.php\#refsect1-function.get-loaded-extensions-examples)

**Example #1 **get\_loaded\_extensions()** Example**

`<?php
print_r(get_loaded_extensions());
?>`

The above example will output
something similar to:

```
Array
(
    [0] => Core
    [1] => date
    [2] => libxml
    [3] => pcre
    [4] => sqlite3
    [5] => zlib
    [6] => ctype
    [7] => dom
    [8] => fileinfo
    [9] => filter
    [10] => hash
    [11] => json
    [12] => mbstring
    [13] => SPL
    [14] => PDO
    [15] => session
    [16] => posix
    [17] => Reflection
    [18] => standard
    [19] => SimpleXML
    [20] => pdo_sqlite
    [21] => Phar
    [22] => tokenizer
    [23] => xml
    [24] => xmlreader
    [25] => xmlwriter
    [26] => gmp
    [27] => iconv
    [28] => intl
    [29] => bcmath
    [30] => sodium
    [31] => Zend OPcache
)
```

### See Also [¶](https://www.php.net/manual/en/function.get-loaded-extensions.php\#refsect1-function.get-loaded-extensions-seealso)

- [get\_extension\_funcs()](https://www.php.net/manual/en/function.get-extension-funcs.php) \- Returns an array with the names of the functions of a module
- [extension\_loaded()](https://www.php.net/manual/en/function.extension-loaded.php) \- Find out whether an extension is loaded
- [dl()](https://www.php.net/manual/en/function.dl.php) \- Loads a PHP extension at runtime
- [phpinfo()](https://www.php.net/manual/en/function.phpinfo.php) \- Outputs information about PHP's configuration

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/info/functions/get-loaded-extensions.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.get-loaded-extensions%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.get-loaded-extensions&repo=en&redirect=https://www.php.net/manual/en/function.get-loaded-extensions.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google