---
url: https://www.php.net/manual/en/splfileobject.fputcsv.php
scraped_at: 2025-10-20T02:32:19.527Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# SplFileObject::fputcsv

(PHP 5 >= 5.4.0, PHP 7, PHP 8)

SplFileObject::fputcsv — Write a field array as a CSV line

### Description [¶](https://www.php.net/manual/en/splfileobject.fputcsv.php\#refsect1-splfileobject.fputcsv-description)

public**SplFileObject::fputcsv**(

[array](https://www.php.net/manual/en/language.types.array.php) `$fields`,

[string](https://www.php.net/manual/en/language.types.string.php) `$separator` = ",",

[string](https://www.php.net/manual/en/language.types.string.php) `$enclosure` = "\\"",

[string](https://www.php.net/manual/en/language.types.string.php) `$escape` = "\\\",

[string](https://www.php.net/manual/en/language.types.string.php) `$eol` = "\\n"

): [int](https://www.php.net/manual/en/language.types.integer.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Writes the `fields` array to the file
as a CSV line.


### Parameters [¶](https://www.php.net/manual/en/splfileobject.fputcsv.php\#refsect1-splfileobject.fputcsv-parameters)

`fields`

An array of values.


`separator`

The field delimiter (one single-byte character only).
By default `,` or the value set by a prior call to
[SplFileObject::setCsvControl()](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php).


`enclosure`

The field enclosure character (one single-byte character only).
By default `"` or the value set by a prior call to
[SplFileObject::setCsvControl()](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php).


`escape`

The escape character (at most one single-byte character).
By default `\` or the value set by a prior call to
[SplFileObject::setCsvControl()](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php).
An empty string ( `""`) disables the proprietary escape mechanism.


> **Note**:
>
> Usually an `enclosure` character is escaped inside
> a field by doubling it; however, the `escape`
> character can be used as an alternative. So for the default parameter
> values `""` and `\"` have the same
> meaning. Other than allowing to escape the
> `enclosure` character the
> `escape` character has no special meaning; it isn't
> even meant to escape itself.

**Warning**

As of PHP 8.4.0, depending on the default value of
`escape` is deprecated.
It needs to be provided explicitly either positionally or by the use
of [Named Arguments](https://www.php.net/manual/en/functions.arguments.php#functions.named-arguments),
or by a call to [SplFileObject::setCsvControl()](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php).


`eol`

The optional `eol` parameter sets
a custom End of Line sequence.


**Warning**

When `escape` is set to anything other than an empty string
( `""`) it can result in CSV that is not compliant with
[» RFC 4180](https://datatracker.ietf.org/doc/html/rfc4180) or unable to survive a roundtrip
through the PHP CSV functions. The default for `escape` is
`"\\"` so it is recommended to set it to the empty string explicitly.
The default value will change in a future version of PHP, no earlier than PHP 9.0.

> **Note**:
>
>
> If an `enclosure` character is contained in a field,
> it will be escaped by doubling it, unless it is immediately preceded by an
> `escape`.

### Return Values [¶](https://www.php.net/manual/en/splfileobject.fputcsv.php\#refsect1-splfileobject.fputcsv-returnvalues)

Returns the length of the written string or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Errors/Exceptions [¶](https://www.php.net/manual/en/splfileobject.fputcsv.php\#refsect1-splfileobject.fputcsv-errors)

Throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if
`separator` or `enclosure`
is not one byte long.


Throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if
`escape` is not one byte long or the empty string.


### Changelog [¶](https://www.php.net/manual/en/splfileobject.fputcsv.php\#refsect1-splfileobject.fputcsv-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Relying on the default value of `escape` is now<br> deprecated. |
| 8.1.0 | The optional `eol` parameter has been added. |
| 7.4.0 | The `escape` parameter now also accepts an empty<br> string to disable the proprietary escape mechanism. |

### Examples [¶](https://www.php.net/manual/en/splfileobject.fputcsv.php\#refsect1-splfileobject.fputcsv-examples)

**Example #1 **SplFileObject::fputcsv()** example**

`<?php
$list = array (
    array('aaa', 'bbb', 'ccc', 'dddd'),
    array('123', '456', '789'),
    array('"aaa"', '"bbb"')
);
$file = new SplFileObject('file.csv', 'w');
foreach ($list as $fields) {
    $file->fputcsv($fields);
}
?>`

The above example will write the following to `file.csv`:

```
aaa,bbb,ccc,dddd
123,456,789
"""aaa""","""bbb"""
```

### See Also [¶](https://www.php.net/manual/en/splfileobject.fputcsv.php\#refsect1-splfileobject.fputcsv-seealso)

- [SplFileObject::fgetcsv()](https://www.php.net/manual/en/splfileobject.fgetcsv.php) \- Gets line from file and parse as CSV fields
- [SplFileObject::setCsvControl()](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php) \- Set the delimiter, enclosure and escape character for CSV
- [SplFileObject::getCsvControl()](https://www.php.net/manual/en/splfileobject.getcsvcontrol.php) \- Get the delimiter, enclosure and escape character for CSV
- [fputcsv()](https://www.php.net/manual/en/function.fputcsv.php) \- Format line as CSV and write to file pointer
- [fgetcsv()](https://www.php.net/manual/en/function.fgetcsv.php) \- Gets line from file pointer and parse for CSV fields
- [str\_getcsv()](https://www.php.net/manual/en/function.str-getcsv.php) \- Parse a CSV string into an array

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/spl/splfileobject/fputcsv.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsplfileobject.fputcsv%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=splfileobject.fputcsv&repo=en&redirect=https://www.php.net/manual/en/splfileobject.fputcsv.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google