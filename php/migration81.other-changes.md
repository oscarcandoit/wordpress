---
url: https://www.php.net/manual/en/migration81.other-changes.php
scraped_at: 2025-10-20T02:36:50.916Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Other Changes [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes)

### Changes in SAPI Modules [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.sapi)

#### CLI [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.sapi.cli)

Using **-a** without the [readline extension](https://www.php.net/manual/en/book.readline.php) will now result in an error.
Previously, **-a** without readline had the same behavior as
calling **php** without any arguments, apart from printing an additional
`"Interactive mode enabled"` message.
This mode was _not_ interactive.


#### PHPDBG [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.sapi.phpdbg)

Remote functionality from [phpdbg](https://www.php.net/manual/en/book.phpdbg.php) has been removed.


### Changed Functions [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.functions)

#### Core [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.functions.core)

The order of properties used in [`foreach`](https://www.php.net/manual/en/control-structures.foreach.php), [var\_dump()](https://www.php.net/manual/en/function.var-dump.php),
[serialize()](https://www.php.net/manual/en/function.serialize.php), object comparison, etc. was changed.
Properties are now ordered naturally according to their declaration
and inheritance. Properties declared in a base class are going
to be before the child properties.


This order is consistent with internal layout of properties in
`zend_object` structure and repeats the order in
`default_properties_table[]` and `properties_info_table[]`.
The old order was not documented and was caused by class inheritance implementation details.


#### Filter [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.functions.filter)

The **`[FILTER\_FLAG\_ALLOW\_OCTAL](https://www.php.net/manual/en/filter.constants.php#constant.filter-flag-allow-octal)`** flag of the
**`[FILTER\_VALIDATE\_INT](https://www.php.net/manual/en/filter.constants.php#constant.filter-validate-int)`** filter
now accept octal string with the leading octal prefix
( `"0o"`/ `"0O"`).


#### GMP [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.functions.gmp)

All [GMP](https://www.php.net/manual/en/book.gmp.php) functions now accept octal string with the leading octal prefix
( `"0o"`/ `"0O"`).


#### PDO ODBC [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.functions.pdo-odbc)

[PDO::getAttribute()](https://www.php.net/manual/en/pdo.getattribute.php) with
**`[PDO::ATTR\_SERVER\_INFO](https://www.php.net/manual/en/pdo.constants.php#pdo.constants.attr-server-info)`** and
**`[PDO::ATTR\_SERVER\_VERSION](https://www.php.net/manual/en/pdo.constants.php#pdo.constants.attr-server-version)`**
now return values instead of throwing [PDOException](https://www.php.net/manual/en/class.pdoexception.php).


#### Reflection [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.functions.reflection)

[ReflectionProperty::setAccessible()](https://www.php.net/manual/en/reflectionproperty.setaccessible.php) and
[ReflectionMethod::setAccessible()](https://www.php.net/manual/en/reflectionmethod.setaccessible.php)
no longer have an effect.
Properties and methods are now always considered accessible via Reflection.


#### Standard [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.functions.standard)

[syslog()](https://www.php.net/manual/en/function.syslog.php) is now binary safe.


### Other Changes to Extensions [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.extensions)

#### GD [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.extensions.gd)

[imagewebp()](https://www.php.net/manual/en/function.imagewebp.php) can now do lossless WebP encoding
by passing **`[IMG\_WEBP\_LOSSLESS](https://www.php.net/manual/en/image.constants.php#constant.img-webp-lossless)`** as the quality.


This constant is only defined, if the used libgd supports
lossless WebP encoding.


#### MySQLi [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.extensions.mysqli)

[mysqli\_stmt::next\_result()](https://www.php.net/manual/en/mysqli-stmt.next-result.php) and
**mysqli::fetch\_all()**
are now available when linking against libmysqlclient.


#### OpenSSL [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.extensions.openssl)

- The [OpenSSL extension](https://www.php.net/manual/en/book.openssl.php) now requires at least OpenSSL version 1.0.2.


- OpenSSL 3.0 is now supported. Be aware that many ciphers are no longer
enabled by default (part of the legacy provider), and that parameter
validation (e.g. minimum key sizes) is stricter now.



#### Phar [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.extensions.phar)

- SHA256 is now used by default for signatures.


- Added support for OpenSSL\_SHA256 and OpenSSL\_SHA512 signatures.



#### SNMP [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.extensions.snmp)

- Added support for SHA256 and SHA512 for the security protocol.



#### Standard [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.extensions.standard)

`--with-password-argon2` now uses pkg-config to detect libargon2.
As such, an alternative libargon2 location should now be specified using
PKG\_CONFIG\_PATH.


### Changes to INI File Handling [¶](https://www.php.net/manual/en/migration81.other-changes.php\#migration81.other-changes.ini)

- The [log\_errors\_max\_len](https://www.php.net/manual/en/errorfunc.configuration.php#ini.log-errors-max-len)
INI directive has been removed.
It no longer had an effect since PHP 8.0.0.


- A leading dollar in a quoted string can now be escaped: `"\${"` will now be
interpreted as a string with contents `${`.


- Backslashes in double quoted strings are now more consistently treated as
escape characters. Previously, `"foo\\"` followed by
something other than a newline was not considered as a terminated string.
It is now interpreted as a string with contents `foo\`.
However, as an exception, the string `"foo\"`
followed by a newline will continue to be treated as a valid string with
contents `foo\` rather than an unterminated string.
This exception exists to support naive uses of Windows file paths such as
`"C:\foo\"`.



### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/appendices/migration81/other-changes.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmigration81.other-changes%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=migration81.other-changes&repo=en&redirect=https://www.php.net/manual/en/migration81.other-changes.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google