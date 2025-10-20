---
url: https://www.php.net/manual/en/spltempfileobject.construct.php
scraped_at: 2025-10-20T02:51:35.224Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# SplTempFileObject::\_\_construct

(PHP 5 >= 5.1.2, PHP 7, PHP 8)

SplTempFileObject::\_\_construct — Construct a new temporary file object

### Description [¶](https://www.php.net/manual/en/spltempfileobject.construct.php\#refsect1-spltempfileobject.construct-description)

public**SplTempFileObject::\_\_construct**([int](https://www.php.net/manual/en/language.types.integer.php) `$maxMemory` = 2 \* 1024 \* 1024)

Construct a new temporary file object.


### Parameters [¶](https://www.php.net/manual/en/spltempfileobject.construct.php\#refsect1-spltempfileobject.construct-parameters)

`maxMemory`

The maximum amount of memory (in bytes, default is 2 MB) for
the temporary file to use. If the temporary file exceeds this
size, it will be moved to a file in the system's temp directory.


If `maxMemory` is negative, only memory
will be used. If `maxMemory` is zero,
no memory will be used.


### Errors/Exceptions [¶](https://www.php.net/manual/en/spltempfileobject.construct.php\#refsect1-spltempfileobject.construct-errors)

Throws a [RuntimeException](https://www.php.net/manual/en/class.runtimeexception.php) if an error occurs.


### Examples [¶](https://www.php.net/manual/en/spltempfileobject.construct.php\#refsect1-spltempfileobject.construct-examples)

**Example #1 **SplTempFileObject()** example**

This example writes a temporary file in memory which can be written to and read from.

`<?php
$temp = new SplTempFileObject();
$temp->fwrite("This is the first line\n");
$temp->fwrite("And this is the second.\n");
echo "Written " . $temp->ftell() . " bytes to temporary file.\n\n";
// Rewind and read what was written
$temp->rewind();
foreach ($temp as $line) {
    echo $line;
}
?>`

The above example will output
something similar to:

```
Written 47 bytes to temporary file.

This is the first line
And this is the second.
```

### See Also [¶](https://www.php.net/manual/en/spltempfileobject.construct.php\#refsect1-spltempfileobject.construct-seealso)

- [SplFileObject](https://www.php.net/manual/en/class.splfileobject.php)
- [PHP input/output streams](https://www.php.net/manual/en/wrappers.php.php)
(for `php://temp` and `php://memory`)


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/spl/spltempfileobject/construct.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fspltempfileobject.construct%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=spltempfileobject.construct&repo=en&redirect=https://www.php.net/manual/en/spltempfileobject.construct.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=117282&page=spltempfileobject.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117282&page=spltempfileobject.construct&vote=down "Vote down!")

19


[**_larry dot laski at gmail dot com_**](https://www.php.net/manual/en/spltempfileobject.construct.php#117282) [¶](https://www.php.net/manual/en/spltempfileobject.construct.php#117282)

**10 years ago**

`Noting that when the tmp file exceeds memory limitations and is written to the system temp directory, it is deleted upon completion of the script it was initially created in. At least that is what I have seen and wanted to document for others since it wasn't clear.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=spltempfileobject.construct&repo=en&redirect=https://www.php.net/manual/en/spltempfileobject.construct.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google