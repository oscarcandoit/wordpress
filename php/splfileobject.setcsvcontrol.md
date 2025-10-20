---
url: https://www.php.net/manual/en/splfileobject.setcsvcontrol.php
scraped_at: 2025-10-20T02:56:12.497Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# SplFileObject::setCsvControl

(PHP 5 >= 5.2.0, PHP 7, PHP 8)

SplFileObject::setCsvControl — Set the delimiter, enclosure and escape character for CSV

### Description [¶](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php\#refsect1-splfileobject.setcsvcontrol-description)

public**SplFileObject::setCsvControl**([string](https://www.php.net/manual/en/language.types.string.php) `$separator` = ",", [string](https://www.php.net/manual/en/language.types.string.php) `$enclosure` = "\\"", [string](https://www.php.net/manual/en/language.types.string.php) `$escape` = "\\\"): [void](https://www.php.net/manual/en/language.types.void.php)

Sets the delimiter, enclosure and escape character for
parsing CSV fields.


### Parameters [¶](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php\#refsect1-splfileobject.setcsvcontrol-parameters)

`separator`

The `separator` parameter sets the field separator.
It must be a single byte character.


`enclosure`

The `enclosure` parameter sets the field enclosure character.
It must be a single byte character.


`escape`

The `escape` parameter sets the escape character.
It must be a single byte character or the empty string.
The empty string ( `""`) disables the proprietary escape mechanism.


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
of [named arguments](https://www.php.net/manual/en/functions.arguments.php#functions.named-arguments).


**Warning**

When `escape` is set to anything other than an empty string
( `""`) it can result in CSV that is not compliant with
[» RFC 4180](https://datatracker.ietf.org/doc/html/rfc4180) or unable to survive a roundtrip
through the PHP CSV functions. The default for `escape` is
`"\\"` so it is recommended to set it to the empty string explicitly.
The default value will change in a future version of PHP, no earlier than PHP 9.0.

### Return Values [¶](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php\#refsect1-splfileobject.setcsvcontrol-returnvalues)

No value is returned.


### Errors/Exceptions [¶](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php\#refsect1-splfileobject.setcsvcontrol-errors)

Throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if
`separator` or `enclosure`
is not one byte long.


Throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if
`escape` is not one byte long or the empty string.


### Changelog [¶](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php\#refsect1-splfileobject.setcsvcontrol-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Relying on the default value of `escape` is now<br> deprecated. |
| 7.4.0 | The `escape` parameter now also accepts an empty<br> string to disable the proprietary escape mechanism. |

### Examples [¶](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php\#refsect1-splfileobject.setcsvcontrol-examples)

**Example #1 **SplFileObject::setCsvControl()** example**

`<?php
$file = new SplFileObject("data.csv");
$file->setFlags(SplFileObject::READ_CSV);
$file->setCsvControl('|');
foreach ($file as $row) {
    list ($fruit, $quantity) = $row;
    // Do something with values
}
?>`

Contents of data.csv

```
<?php
apples|20
bananas|14
cherries|87
?>
```

### See Also [¶](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php\#refsect1-splfileobject.setcsvcontrol-seealso)

- [SplFileObject::getCsvControl()](https://www.php.net/manual/en/splfileobject.getcsvcontrol.php) \- Get the delimiter, enclosure and escape character for CSV
- [SplFileObject::fgetcsv()](https://www.php.net/manual/en/splfileobject.fgetcsv.php) \- Gets line from file and parse as CSV fields
- [SplFileObject::fputcsv()](https://www.php.net/manual/en/splfileobject.fputcsv.php) \- Write a field array as a CSV line
- [fputcsv()](https://www.php.net/manual/en/function.fputcsv.php) \- Format line as CSV and write to file pointer
- [fgetcsv()](https://www.php.net/manual/en/function.fgetcsv.php) \- Gets line from file pointer and parse for CSV fields
- [str\_getcsv()](https://www.php.net/manual/en/function.str-getcsv.php) \- Parse a CSV string into an array

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/spl/splfileobject/setcsvcontrol.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsplfileobject.setcsvcontrol%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=splfileobject.setcsvcontrol&repo=en&redirect=https://www.php.net/manual/en/splfileobject.setcsvcontrol.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google