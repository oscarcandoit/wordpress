---
url: https://www.php.net/manual/en/migration70.deprecated.php
scraped_at: 2025-10-20T02:51:38.475Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Deprecated features in PHP 7.0.x [¶](https://www.php.net/manual/en/migration70.deprecated.php\#migration70.deprecated)

### PHP 4 style constructors [¶](https://www.php.net/manual/en/migration70.deprecated.php\#migration70.deprecated.php4-constructors)

PHP 4 style constructors (methods that have the same name as the class they
are defined in) are deprecated, and will be removed in the future. PHP 7
will emit **`[E\_DEPRECATED](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-deprecated)`** if a PHP 4 constructor is the
only constructor defined within a class. Classes that implement a
**\_\_construct()** method are unaffected.


`<?php
class foo {
    function foo() {
        echo 'I am the constructor';
    }
}
?>`

The above example will output:

```
Deprecated: Methods with the same name as their class will not be constructors in a future version of PHP; foo has a deprecated constructor in example.php on line 3

```

### Static calls to non-static methods [¶](https://www.php.net/manual/en/migration70.deprecated.php\#migration70.deprecated.static-calls)

[Static](https://www.php.net/manual/en/language.oop5.static.php) calls to methods that
are not declared **static** are deprecated, and may be
removed in the future.


`<?php
class foo {
    function bar() {
        echo 'I am not static!';
    }
}
foo::bar();
?>`

The above example will output:

```
Deprecated: Non-static method foo::bar() should not be called statically in - on line 8
I am not static!

```

### [password\_hash()](https://www.php.net/manual/en/function.password-hash.php) salt option [¶](https://www.php.net/manual/en/migration70.deprecated.php\#migration70.deprecated.pwshash-salt-option)

The salt option for the [password\_hash()](https://www.php.net/manual/en/function.password-hash.php) function has been
deprecated to prevent developers from generating their own (usually insecure)
salts. The function itself generates a cryptographically secure salt when no
salt is provided by the developer - therefore custom salt generation should not
be needed.


### `capture_session_meta` SSL context option [¶](https://www.php.net/manual/en/migration70.deprecated.php\#migration70.deprecated.capture-session-meta)

The `capture_session_meta` SSL context option has been
deprecated. SSL metadata is now available through the
[stream\_get\_meta\_data()](https://www.php.net/manual/en/function.stream-get-meta-data.php) function.


### [LDAP](https://www.php.net/manual/en/book.ldap.php) deprecations [¶](https://www.php.net/manual/en/migration70.deprecated.php\#migration70.deprecated.ldap)

The following function has been deprecated:


- [ldap\_sort()](https://www.php.net/manual/en/function.ldap-sort.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/appendices/migration70/deprecated.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmigration70.deprecated%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=migration70.deprecated&repo=en&redirect=https://www.php.net/manual/en/migration70.deprecated.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google