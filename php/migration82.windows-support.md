---
url: https://www.php.net/manual/en/migration82.windows-support.php
scraped_at: 2025-10-20T02:36:03.264Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Windows Support [¶](https://www.php.net/manual/en/migration82.windows-support.php\#migration82.windows-support)

### Core [¶](https://www.php.net/manual/en/migration82.windows-support.php\#migration82.windows-support.core)

Windows specific error messages are no longer localized, but instead
always displayed in English to better match PHP error messages.


Preliminary and highly experimental support for building on ARM64 has been added.


### OCI8 [¶](https://www.php.net/manual/en/migration82.windows-support.php\#migration82.windows-support.oci8)

Because building against Oracle Client 10g is no longer supported anyway,
the configuration option **--with-oci8** has been dropped.
The **--with-oci8-11g**, **--with-oci8-12c** and
**--with-oci8-19** configuration options are still supported.


### Zip [¶](https://www.php.net/manual/en/migration82.windows-support.php\#migration82.windows-support.zip)

The Zip extension is upgraded to version 1.21.0,
and is now built as shared library (DLL) by default.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/appendices/migration82/windows-support.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmigration82.windows-support%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=migration82.windows-support&repo=en&redirect=https://www.php.net/manual/en/migration82.windows-support.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google