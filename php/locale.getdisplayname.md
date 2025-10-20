---
url: https://www.php.net/manual/en/locale.getdisplayname.php
scraped_at: 2025-10-20T02:52:56.025Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Locale::getDisplayName

# locale\_get\_display\_name

(PHP 5 >= 5.3.0, PHP 7, PHP 8, PECL intl >= 1.0.0)

Locale::getDisplayName \-\- locale\_get\_display\_name — Returns an appropriately localized display name for the input locale

### Description [¶](https://www.php.net/manual/en/locale.getdisplayname.php\#refsect1-locale.getdisplayname-description)

Object-oriented style


publicstatic**Locale::getDisplayName**([string](https://www.php.net/manual/en/language.types.string.php) `$locale`, [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$displayLocale` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Procedural style


**locale\_get\_display\_name**([string](https://www.php.net/manual/en/language.types.string.php) `$locale`, [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$displayLocale` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Returns an appropriately localized display name for the input locale. If `locale` is
**`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** then the default locale is used.


### Parameters [¶](https://www.php.net/manual/en/locale.getdisplayname.php\#refsect1-locale.getdisplayname-parameters)

`locale`

The locale to return a display name for.


`displayLocale`

optional format locale

### Return Values [¶](https://www.php.net/manual/en/locale.getdisplayname.php\#refsect1-locale.getdisplayname-returnvalues)

Display name of the locale in the format appropriate for `displayLocale`, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Changelog [¶](https://www.php.net/manual/en/locale.getdisplayname.php\#refsect1-locale.getdisplayname-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `displayLocale` is nullable now. |

### Examples [¶](https://www.php.net/manual/en/locale.getdisplayname.php\#refsect1-locale.getdisplayname-examples)

**Example #1 **locale\_get\_display\_name()** example**

`<?php
echo locale_get_display_name('sl-Latn-IT-nedis', 'en');
echo ";\n";
echo locale_get_display_name('sl-Latn-IT-nedis', 'fr');
echo ";\n";
echo locale_get_display_name('sl-Latn-IT-nedis', 'de');
?>`

**Example #2 OO example**

`<?php
echo Locale::getDisplayName('sl-Latn-IT-nedis', 'en');
echo ";\n";
echo Locale::getDisplayName('sl-Latn-IT-nedis', 'fr');
echo ";\n";
echo Locale::getDisplayName('sl-Latn-IT-nedis', 'de');
?>`

The above example will output:

```
Slovenian (Latin, Italy, Natisone dialect);
slov\xc3\xa8ne (latin, Italie, dialecte de Natisone;
Slowenisch (Lateinisch, Italien, NEDIS)
```

### See Also [¶](https://www.php.net/manual/en/locale.getdisplayname.php\#refsect1-locale.getdisplayname-seealso)

- [locale\_get\_display\_language()](https://www.php.net/manual/en/locale.getdisplaylanguage.php) \- Returns an appropriately localized display name for language of the inputlocale
- [locale\_get\_display\_script()](https://www.php.net/manual/en/locale.getdisplayscript.php) \- Returns an appropriately localized display name for script of the input locale
- [locale\_get\_display\_region()](https://www.php.net/manual/en/locale.getdisplayregion.php) \- Returns an appropriately localized display name for region of the input locale
- [locale\_get\_display\_variant()](https://www.php.net/manual/en/locale.getdisplayvariant.php) \- Returns an appropriately localized display name for variants of the input locale

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/intl/locale/get-display-name.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flocale.getdisplayname%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=locale.getdisplayname&repo=en&redirect=https://www.php.net/manual/en/locale.getdisplayname.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google