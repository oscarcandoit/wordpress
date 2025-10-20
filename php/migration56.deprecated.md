---
url: https://www.php.net/manual/en/migration56.deprecated.php
scraped_at: 2025-10-20T02:49:40.243Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Deprecated features in PHP 5.6.x [¶](https://www.php.net/manual/en/migration56.deprecated.php\#migration56.deprecated)

### Calls from incompatible context [¶](https://www.php.net/manual/en/migration56.deprecated.php\#migration56.deprecated.incompatible-context)

Methods called from an incompatible context are now deprecated, and will
generate **`[E\_DEPRECATED](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-deprecated)`** errors when invoked instead of
**`[E\_STRICT](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-strict)`**. Support for these calls will be removed in
a future version of PHP.


An example of such a call is:


`<?php
class A {
    function f() { echo get_class($this); }
}
class B {
    function f() { A::f(); }
}
(new B)->f();
?>`

The above example will output:

```
Deprecated: Non-static method A::f() should not be called statically, assuming $this from incompatible context in - on line 7
B

```

### $HTTP\_RAW\_POST\_DATA and `always_populate_raw_post_data` [¶](https://www.php.net/manual/en/migration56.deprecated.php\#migration56.deprecated.raw-post-data)

`always_populate_raw_post_data`
will now generate an **`[E\_DEPRECATED](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-deprecated)`** error when
$HTTP\_RAW\_POST\_DATA is populated.
New code should use
[`php://input`](https://www.php.net/manual/en/wrappers.php.php#wrappers.php.input)
instead of $HTTP\_RAW\_POST\_DATA, which will be removed
in a future release. You can opt in for the new behaviour (in which
$HTTP\_RAW\_POST\_DATA is never defined hence no
**`[E\_DEPRECATED](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-deprecated)`** error will be generated) by setting
`always_populate_raw_post_data`
to `-1`.


### [iconv](https://www.php.net/manual/en/book.iconv.php) and [mbstring](https://www.php.net/manual/en/book.mbstring.php) encoding settings [¶](https://www.php.net/manual/en/migration56.deprecated.php\#migration56.deprecated.iconv-mbstring-encoding)

The [iconv](https://www.php.net/manual/en/book.iconv.php) and
[mbstring](https://www.php.net/manual/en/book.mbstring.php) configuration options related
to encoding have been deprecated in favour of
[`default_charset`](https://www.php.net/manual/en/ini.core.php#ini.default-charset).
The deprecated options are:


- [`iconv.input_encoding`](https://www.php.net/manual/en/iconv.configuration.php#ini.iconv.input-encoding)
- [`iconv.output_encoding`](https://www.php.net/manual/en/iconv.configuration.php#ini.iconv.output-encoding)
- [`iconv.internal_encoding`](https://www.php.net/manual/en/iconv.configuration.php#ini.iconv.internal-encoding)
- [`mbstring.http_input`](https://www.php.net/manual/en/mbstring.configuration.php#ini.mbstring.http-input)
- [`mbstring.http_output`](https://www.php.net/manual/en/mbstring.configuration.php#ini.mbstring.http-output)
- [`mbstring.internal_encoding`](https://www.php.net/manual/en/mbstring.configuration.php#ini.mbstring.internal-encoding)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/appendices/migration56/deprecated.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmigration56.deprecated%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=migration56.deprecated&repo=en&redirect=https://www.php.net/manual/en/migration56.deprecated.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google