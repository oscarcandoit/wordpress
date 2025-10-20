---
url: https://www.php.net/manual/en/locale.getdefault.php
scraped_at: 2025-10-20T02:49:43.955Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Locale::getDefault

# locale\_get\_default

(PHP 5 >= 5.3.0, PHP 7, PHP 8, PECL intl >= 1.0.0)

Locale::getDefault \-\- locale\_get\_default — Gets the default locale value from the INTL global 'default\_locale'

### Description [¶](https://www.php.net/manual/en/locale.getdefault.php\#refsect1-locale.getdefault-description)

Object-oriented style


publicstatic**Locale::getDefault**(): [string](https://www.php.net/manual/en/language.types.string.php)

Procedural style


**locale\_get\_default**(): [string](https://www.php.net/manual/en/language.types.string.php)

Gets the default locale value. At the PHP initialization this value is set
to 'intl.default\_locale' value from php.ini if that value exists or
from ICU's function uloc\_getDefault().


### Parameters [¶](https://www.php.net/manual/en/locale.getdefault.php\#refsect1-locale.getdefault-parameters)

### Return Values [¶](https://www.php.net/manual/en/locale.getdefault.php\#refsect1-locale.getdefault-returnvalues)

The current runtime locale


### Examples [¶](https://www.php.net/manual/en/locale.getdefault.php\#refsect1-locale.getdefault-examples)

**Example #1 **locale\_get\_default()** example**

`<?php
ini_set('intl.default_locale', 'de-DE');
echo locale_get_default();
echo '; ';
locale_set_default('fr');
echo locale_get_default();
?>`

**Example #2 OO example**

`<?php
ini_set('intl.default_locale', 'de-DE');
echo Locale::getDefault();
echo '; ';
Locale::setDefault('fr');
echo Locale::getDefault();
?>`

The above example will output:

```
de-DE; fr
```

### See Also [¶](https://www.php.net/manual/en/locale.getdefault.php\#refsect1-locale.getdefault-seealso)

- [locale\_set\_default()](https://www.php.net/manual/en/locale.setdefault.php) \- Sets the default runtime locale

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/intl/locale/get-default.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flocale.getdefault%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=locale.getdefault&repo=en&redirect=https://www.php.net/manual/en/locale.getdefault.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=123838&page=locale.getdefault&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123838&page=locale.getdefault&vote=down "Vote down!")

 -5


[**_tjsturos_**](https://www.php.net/manual/en/locale.getdefault.php#123838) [¶](https://www.php.net/manual/en/locale.getdefault.php#123838)

**6 years ago**

`If you don't do anything, you can still call these methods and get the server's default locale.
In the case of Linux (Ubuntu 16.04), it uses the $LANG global variable.
Using the REPL:
echo locale_get_default();   // en_US
and then resetting the $LANG:
tiikeri@ubuntu:~$ LANG="fi_FI.UTF-8"
and back to the REPL:
echo locale_get_default();   // fi_FI`

[＋add a note](https://www.php.net/manual/add-note.php?sect=locale.getdefault&repo=en&redirect=https://www.php.net/manual/en/locale.getdefault.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google