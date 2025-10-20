---
url: https://www.php.net/manual/en/changelog.misc.php
scraped_at: 2025-10-20T02:33:06.770Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Changelog [¶](https://www.php.net/manual/en/changelog.misc.php\#changelog.misc)

The following changes have been made to classes/functions/methods of this extension.

| Version | Function | Description |
| --- | --- | --- |
| 8.4.0 | [exit](https://www.php.net/manual/en/function.exit.php) | exit is now a proper function,<br> therefore it follows the usual<br> type juggling semantics<br> is affected by the<br> strict\_types<br> declare, can be called with named arguments, and be a<br> variable functions. |
|  | [highlight\_string](https://www.php.net/manual/en/function.highlight-string.php) | Return type changed from stringbool to stringtrue. |
| 8.3.0 | [highlight\_file](https://www.php.net/manual/en/function.highlight-file.php) | The resulting HTML has changed. |
|  | [highlight\_string](https://www.php.net/manual/en/function.highlight-string.php) | The resulting HTML has changed. |
| 8.1.0 | [define](https://www.php.net/manual/en/function.define.php) | value can now be an object. |
| 8.0.0 | [constant](https://www.php.net/manual/en/function.constant.php) | If the constant is not defined, constant now throws an<br> Error exception; previously an E\_WARNING<br> was generated, and null was returned. |
|  | [define](https://www.php.net/manual/en/function.define.php) | Passing true to case\_insensitive now emits an E\_WARNING. Passing false is still allowed. |
|  | [ignore\_user\_abort](https://www.php.net/manual/en/function.ignore-user-abort.php) | enable is nullable now. |
|  | [pack](https://www.php.net/manual/en/function.pack.php) | This function no longer returns false on failure. |
|  | [sapi\_windows\_vt100\_support](https://www.php.net/manual/en/function.sapi-windows-vt100-support.php) | enable is now nullable. |
|  | [sleep](https://www.php.net/manual/en/function.sleep.php) | The function throws a ValueError on negative seconds;<br> previously, an E\_WARNING was raised instead, and the function returned false. |
| 7.3.0 | [define](https://www.php.net/manual/en/function.define.php) | case\_insensitive has been deprecated and will be removed in version 8.0.0. |
| 7.2.0 | [pack](https://www.php.net/manual/en/function.pack.php) | float and double types supports both Big Endian and Little Endian. |
|  | [unpack](https://www.php.net/manual/en/function.unpack.php) | float and double types supports both Big Endian and Little Endian. |
| 7.1.1 | [pack](https://www.php.net/manual/en/function.pack.php) | The "e", "E", "g" and "G" codes were added to enable byte order support for float and double. |
| 7.1.0 | [unpack](https://www.php.net/manual/en/function.unpack.php) | The optional offset has been added. |
| 7.0.15 | [pack](https://www.php.net/manual/en/function.pack.php) | The "e", "E", "g" and "G" codes were added to enable byte order support for float and double. |

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/misc/book.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fchangelog.misc%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=changelog.misc&repo=en&redirect=https://www.php.net/manual/en/changelog.misc.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google