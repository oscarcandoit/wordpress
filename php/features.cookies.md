---
url: https://www.php.net/manual/en/features.cookies.php
scraped_at: 2025-10-20T02:35:54.418Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Cookies [¶](https://www.php.net/manual/en/features.cookies.php\#features.cookies)

PHP transparently supports HTTP cookies. Cookies are a mechanism for
storing data in the remote browser and thus tracking or identifying return
users. You can set cookies using the [setcookie()](https://www.php.net/manual/en/function.setcookie.php) or
[setrawcookie()](https://www.php.net/manual/en/function.setrawcookie.php)
function. Cookies are part of the HTTP header, so
[setcookie()](https://www.php.net/manual/en/function.setcookie.php) must be called before any output is sent to
the browser. This is the same limitation that [header()](https://www.php.net/manual/en/function.header.php)
has. You can use the [output buffering\\
functions](https://www.php.net/manual/en/ref.outcontrol.php) to delay the script output until you have decided whether
or not to set any cookies or send any headers.


Any cookies sent to server from the client will automatically be included into
a [$\_COOKIE](https://www.php.net/manual/en/reserved.variables.cookies.php) auto-global
array if [variables\_order](https://www.php.net/manual/en/ini.core.php#ini.variables-order)
contains "C". If you wish to assign multiple values to a single
cookie, just add `[]` to the cookie name.


For more details, including notes on browser bugs, see the
[setcookie()](https://www.php.net/manual/en/function.setcookie.php) and [setrawcookie()](https://www.php.net/manual/en/function.setrawcookie.php)
function.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/features/cookies.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffeatures.cookies%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=features.cookies&repo=en&redirect=https://www.php.net/manual/en/features.cookies.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google