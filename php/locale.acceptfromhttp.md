---
url: https://www.php.net/manual/en/locale.acceptfromhttp.php
scraped_at: 2025-10-20T02:49:54.447Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Locale::acceptFromHttp

# locale\_accept\_from\_http

(PHP 5 >= 5.3.0, PHP 7, PHP 8, PECL intl >= 1.0.0)

Locale::acceptFromHttp \-\- locale\_accept\_from\_http — Tries to find out best available locale based on HTTP "Accept-Language" header

### Description [¶](https://www.php.net/manual/en/locale.acceptfromhttp.php\#refsect1-locale.acceptfromhttp-description)

Object-oriented style


publicstatic**Locale::acceptFromHttp**([string](https://www.php.net/manual/en/language.types.string.php) `$header`): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Procedural style


**locale\_accept\_from\_http**([string](https://www.php.net/manual/en/language.types.string.php) `$header`): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Tries to find locale that can satisfy the language list that is requested by the
HTTP "Accept-Language" header.


### Parameters [¶](https://www.php.net/manual/en/locale.acceptfromhttp.php\#refsect1-locale.acceptfromhttp-parameters)

`header`

The string containing the "Accept-Language" header according to format in RFC 2616.


### Return Values [¶](https://www.php.net/manual/en/locale.acceptfromhttp.php\#refsect1-locale.acceptfromhttp-returnvalues)

The corresponding locale identifier.


Returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** when the length of `header` exceeds
**`[INTL\_MAX\_LOCALE\_LEN](https://www.php.net/manual/en/intl.constants.php#constant.intl-max-locale-len)`**.


### Examples [¶](https://www.php.net/manual/en/locale.acceptfromhttp.php\#refsect1-locale.acceptfromhttp-examples)

**Example #1 **locale\_accept\_from\_http()** example**

`<?php
$locale = locale_accept_from_http($_SERVER['HTTP_ACCEPT_LANGUAGE']);
echo $locale;
?>`

**Example #2 OO example**

`<?php
$locale = Locale::acceptFromHttp($_SERVER['HTTP_ACCEPT_LANGUAGE']);
echo $locale;
?>`

The above example will output:

```
en_US
```

### See Also [¶](https://www.php.net/manual/en/locale.acceptfromhttp.php\#refsect1-locale.acceptfromhttp-seealso)

- [locale\_lookup()](https://www.php.net/manual/en/locale.lookup.php) \- Searches the language tag list for the best match to the language

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/intl/locale/accept-from-http.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flocale.acceptfromhttp%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=locale.acceptfromhttp&repo=en&redirect=https://www.php.net/manual/en/locale.acceptfromhttp.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=110350&page=locale.acceptfromhttp&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110350&page=locale.acceptfromhttp&vote=down "Vote down!")

46


[**_Adam Lange_**](https://www.php.net/manual/en/locale.acceptfromhttp.php#110350) [¶](https://www.php.net/manual/en/locale.acceptfromhttp.php#110350)

**13 years ago**

`It's good to mention that if user browser will not send HTTP_ACCEPT_LANGUAGE, the output from:
Locale::acceptFromHttp($_SERVER['HTTP_ACCEPT_LANGUAGE']);
Will be null.
So remember to set up a fail over scenario!`

[up](https://www.php.net/manual/vote-note.php?id=121900&page=locale.acceptfromhttp&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121900&page=locale.acceptfromhttp&vote=down "Vote down!")

11


[**_rasmus at mindplay dot dk_**](https://www.php.net/manual/en/locale.acceptfromhttp.php#121900) [¶](https://www.php.net/manual/en/locale.acceptfromhttp.php#121900)

**7 years ago**

`If you're struggling to figure out how to use this function in a project that only supports certain languages, move along.
Unfortunately, this function doesn't let you specify languages supported by your project - and since the internal header parsing and negotiation logic isn't exposed in any other way, you'll most likely want to ditch this function and go for a custom implementation of the same thing:
[https://github.com/willdurand/Negotiation](https://github.com/willdurand/Negotiation)`

[up](https://www.php.net/manual/vote-note.php?id=122623&page=locale.acceptfromhttp&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122623&page=locale.acceptfromhttp&vote=down "Vote down!")

1


[**_mollasadra at g dot com_**](https://www.php.net/manual/en/locale.acceptfromhttp.php#122623) [¶](https://www.php.net/manual/en/locale.acceptfromhttp.php#122623)

**7 years ago**

`Didn't see this being documented anywhere and the bug hasn't been addressed yet, so to save headache for otherS, this method does a little weird thing with these different locales:
php > echo locale_accept_from_http("zh_TW");
zh
php > echo locale_accept_from_http("zh_CN");
zh`

[up](https://www.php.net/manual/vote-note.php?id=128460&page=locale.acceptfromhttp&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128460&page=locale.acceptfromhttp&vote=down "Vote down!")

0


[**_bill at m$ dot com_**](https://www.php.net/manual/en/locale.acceptfromhttp.php#128460) [¶](https://www.php.net/manual/en/locale.acceptfromhttp.php#128460)

**2 years ago**

`A nice way to detect humans. Bots usually dont have this HTTP_ACCEPT_LANGUAGE set.`

[up](https://www.php.net/manual/vote-note.php?id=126809&page=locale.acceptfromhttp&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126809&page=locale.acceptfromhttp&vote=down "Vote down!")

0


[**_bohwaz_**](https://www.php.net/manual/en/locale.acceptfromhttp.php#126809) [¶](https://www.php.net/manual/en/locale.acceptfromhttp.php#126809)

**3 years ago**

`Please note that this method can throw IntlException in some cases when the passed header string is invalid AND you have enabled exceptions.  For example:
<?php
ini_set('intl.use_exceptions', 1);
$header = 'fr-FR,fr;q=0.9,fr;q=0.9;q=0.8,en-gb;q=0.8;q=0.7,en;q=0.6,en;q=0.7;q=0.5,*;q=0.5;q=0.4';
var_dump(locale_accept_from_http($header));
?>
Returns:
PHP Warning:  Uncaught IntlException: locale_accept_from_http: failed to find acceptable locale in ...`

[＋add a note](https://www.php.net/manual/add-note.php?sect=locale.acceptfromhttp&repo=en&redirect=https://www.php.net/manual/en/locale.acceptfromhttp.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google