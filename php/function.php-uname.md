---
url: https://www.php.net/manual/en/function.php-uname.php
scraped_at: 2025-10-20T02:59:01.931Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# php\_uname

(PHP 4 >= 4.0.2, PHP 5, PHP 7, PHP 8)

php\_uname — Returns information about the operating system PHP is running on

### Description [¶](https://www.php.net/manual/en/function.php-uname.php\#refsect1-function.php-uname-description)

**php\_uname**([string](https://www.php.net/manual/en/language.types.string.php) `$mode` = "a"): [string](https://www.php.net/manual/en/language.types.string.php)

**php\_uname()** returns a description of the operating
system PHP is running on. This is the same string you see at the very
top of the [phpinfo()](https://www.php.net/manual/en/function.phpinfo.php) output. For the name of just
the operating system, consider using the **`[PHP\_OS](https://www.php.net/manual/en/reserved.constants.php#constant.php-os)`**
constant, but keep in mind this constant will contain the operating
system PHP was _built_ on.


On some older UNIX platforms, it may not be able to determine the
current OS information in which case it will revert to displaying
the OS PHP was built on. This will only happen if your uname()
library call either doesn't exist or doesn't work.


### Parameters [¶](https://www.php.net/manual/en/function.php-uname.php\#refsect1-function.php-uname-parameters)

`mode`

`mode` is a single character that defines what
information is returned:


- `'a'`: This is the default. Returns the same
information as the individual modes
`'s'`, `'n'`, `'r'`, `'v'`, `'m'`
separated by spaces.


- `'s'`: Operating system name. eg.
`FreeBSD`.

- `'n'`: Host name. eg.
`localhost.example.com`.

- `'r'`: Release name. eg.
`5.1.2-RELEASE`.

- `'v'`: Version information. Varies a lot between
operating systems.

- `'m'`: Machine type. eg. `i386`.


### Return Values [¶](https://www.php.net/manual/en/function.php-uname.php\#refsect1-function.php-uname-returnvalues)

Returns the description, as a string.


### Changelog [¶](https://www.php.net/manual/en/function.php-uname.php\#refsect1-function.php-uname-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) when an invalid<br> `mode` is specified. |

### Examples [¶](https://www.php.net/manual/en/function.php-uname.php\#refsect1-function.php-uname-examples)

**Example #1 Some **php\_uname()** examples**

`<?php
echo php_uname();
echo PHP_OS;
/* Some possible outputs:
Linux localhost 2.4.21-0.13mdk #1 Fri Mar 14 15:08:06 EST 2003 i686
Linux
FreeBSD localhost 3.2-RELEASE #15: Mon Dec 17 08:46:02 GMT 2001
FreeBSD
Windows NT XN1 5.1 build 2600
WINNT
*/
if (strtoupper(substr(PHP_OS, 0, 3)) === 'WIN') {
    echo 'This is a server using Windows!';
} else {
    echo 'This is a server not using Windows!';
}
?>`

There are also some related [Predefined PHP constants](https://www.php.net/manual/en/language.constants.predefined.php) that may come in handy, for example:


**Example #2 A few OS related constant examples**

`<?php
// *nix
echo DIRECTORY_SEPARATOR; // /
echo PHP_SHLIB_SUFFIX;    // so
echo PATH_SEPARATOR;      // :
// Win*
echo DIRECTORY_SEPARATOR; // \
echo PHP_SHLIB_SUFFIX;    // dll
echo PATH_SEPARATOR;      // ;
?>`

### See Also [¶](https://www.php.net/manual/en/function.php-uname.php\#refsect1-function.php-uname-seealso)

- [phpversion()](https://www.php.net/manual/en/function.phpversion.php) \- Gets the current PHP version
- [php\_sapi\_name()](https://www.php.net/manual/en/function.php-sapi-name.php) \- Returns the type of interface between web server and PHP
- [phpinfo()](https://www.php.net/manual/en/function.phpinfo.php) \- Outputs information about PHP's configuration

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/info/functions/php-uname.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.php-uname%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.php-uname&repo=en&redirect=https://www.php.net/manual/en/function.php-uname.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=110199&page=function.php-uname&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110199&page=function.php-uname&vote=down "Vote down!")

7


[**_Grzechooo+php at gmail dot com_**](https://www.php.net/manual/en/function.php-uname.php#110199) [¶](https://www.php.net/manual/en/function.php-uname.php#110199)

**13 years ago**

`Note that PHP won't tell you that it reverted to displaying platform it was built on.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.php-uname&repo=en&redirect=https://www.php.net/manual/en/function.php-uname.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google