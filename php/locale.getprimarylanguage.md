---
url: https://www.php.net/manual/en/locale.getprimarylanguage.php
scraped_at: 2025-10-20T02:48:14.216Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Locale::getPrimaryLanguage

# locale\_get\_primary\_language

(PHP 5 >= 5.3.0, PHP 7, PHP 8, PECL intl >= 1.0.0)

Locale::getPrimaryLanguage \-\- locale\_get\_primary\_language — Gets the primary language for the input locale

### Description [¶](https://www.php.net/manual/en/locale.getprimarylanguage.php\#refsect1-locale.getprimarylanguage-description)

Object-oriented style


publicstatic**Locale::getPrimaryLanguage**([string](https://www.php.net/manual/en/language.types.string.php) `$locale`): [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php)

Procedural style


**locale\_get\_primary\_language**([string](https://www.php.net/manual/en/language.types.string.php) `$locale`): [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php)

Gets the primary language for the input locale


### Parameters [¶](https://www.php.net/manual/en/locale.getprimarylanguage.php\#refsect1-locale.getprimarylanguage-parameters)

`locale`

The locale to extract the primary language code from


### Return Values [¶](https://www.php.net/manual/en/locale.getprimarylanguage.php\#refsect1-locale.getprimarylanguage-returnvalues)

The language code associated with the language.


Returns **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** when the length of `locale` exceeds **`[INTL\_MAX\_LOCALE\_LEN](https://www.php.net/manual/en/intl.constants.php#constant.intl-max-locale-len)`**.

### Examples [¶](https://www.php.net/manual/en/locale.getprimarylanguage.php\#refsect1-locale.getprimarylanguage-examples)

**Example #1 **locale\_get\_primary\_language()** example**

`<?php
echo locale_get_primary_language('zh-Hant');
?>`

**Example #2 OO example**

`<?php
echo Locale::getPrimaryLanguage('zh-Hant');
?>`

The above example will output:

```
zh
```

### See Also [¶](https://www.php.net/manual/en/locale.getprimarylanguage.php\#refsect1-locale.getprimarylanguage-seealso)

- [locale\_get\_script()](https://www.php.net/manual/en/locale.getscript.php) \- Gets the script for the input locale
- [locale\_get\_region()](https://www.php.net/manual/en/locale.getregion.php) \- Gets the region for the input locale
- [locale\_get\_all\_variants()](https://www.php.net/manual/en/locale.getallvariants.php) \- Gets the variants for the input locale

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/intl/locale/get-primary-language.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flocale.getprimarylanguage%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=locale.getprimarylanguage&repo=en&redirect=https://www.php.net/manual/en/locale.getprimarylanguage.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=117250&page=locale.getprimarylanguage&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117250&page=locale.getprimarylanguage&vote=down "Vote down!")

16


[**_Mahn_**](https://www.php.net/manual/en/locale.getprimarylanguage.php#117250) [¶](https://www.php.net/manual/en/locale.getprimarylanguage.php#117250)

**10 years ago**

`The behaviour when a falsy value is passed as the $locale is undocumented, but it appears that it returns the primary language of the default system language. In my case:
    Locale::getPrimaryLanguage(null);
Returns 'en'. So make sure to test $locale before passing it to the method.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=locale.getprimarylanguage&repo=en&redirect=https://www.php.net/manual/en/locale.getprimarylanguage.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google