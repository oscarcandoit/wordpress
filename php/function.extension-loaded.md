---
url: https://www.php.net/manual/en/function.extension-loaded.php
scraped_at: 2025-10-20T02:53:24.317Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# extension\_loaded

(PHP 4, PHP 5, PHP 7, PHP 8)

extension\_loaded — Find out whether an extension is loaded

### Description [¶](https://www.php.net/manual/en/function.extension-loaded.php\#refsect1-function.extension-loaded-description)

**extension\_loaded**([string](https://www.php.net/manual/en/language.types.string.php) `$extension`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Finds out whether the extension is loaded.


### Parameters [¶](https://www.php.net/manual/en/function.extension-loaded.php\#refsect1-function.extension-loaded-parameters)

`extension`

The extension name. This parameter is case-insensitive.


You can see the names of various extensions by using
[phpinfo()](https://www.php.net/manual/en/function.phpinfo.php) or if you're using the
`CGI` or `CLI` version of
PHP you can use the **-m** switch to
list all available extensions:


```
$ php -m
[PHP Modules]
xml
tokenizer
standard
sockets
session
posix
pcre
overload
mysql
mbstring
ctype

[Zend Modules]
```

### Return Values [¶](https://www.php.net/manual/en/function.extension-loaded.php\#refsect1-function.extension-loaded-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if the extension identified by `extension`
is loaded, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.


### Examples [¶](https://www.php.net/manual/en/function.extension-loaded.php\#refsect1-function.extension-loaded-examples)

**Example #1 **extension\_loaded()** example**

`<?php
if (!extension_loaded('gd')) {
    if (!dl('gd.so')) {
        exit;
    }
}
?>`

### See Also [¶](https://www.php.net/manual/en/function.extension-loaded.php\#refsect1-function.extension-loaded-seealso)

- [get\_loaded\_extensions()](https://www.php.net/manual/en/function.get-loaded-extensions.php) \- Returns an array with the names of all modules compiled and loaded
- [get\_extension\_funcs()](https://www.php.net/manual/en/function.get-extension-funcs.php) \- Returns an array with the names of the functions of a module
- [phpinfo()](https://www.php.net/manual/en/function.phpinfo.php) \- Outputs information about PHP's configuration
- [dl()](https://www.php.net/manual/en/function.dl.php) \- Loads a PHP extension at runtime
- [function\_exists()](https://www.php.net/manual/en/function.function-exists.php) \- Return true if the given function has been defined

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/info/functions/extension-loaded.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.extension-loaded%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.extension-loaded&repo=en&redirect=https://www.php.net/manual/en/function.extension-loaded.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google