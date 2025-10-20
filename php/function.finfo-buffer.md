---
url: https://www.php.net/manual/en/function.finfo-buffer.php
scraped_at: 2025-10-20T02:53:10.297Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# finfo\_buffer

# finfo::buffer

(PHP 5 >= 5.3.0, PHP 7, PHP 8, PECL fileinfo >= 0.1.0)

finfo\_buffer \-\- finfo::buffer — Return information about a string buffer

### Description [¶](https://www.php.net/manual/en/function.finfo-buffer.php\#refsect1-function.finfo-buffer-description)

Procedural style

**finfo\_buffer**(

[finfo](https://www.php.net/manual/en/class.finfo.php) `$finfo`,

[string](https://www.php.net/manual/en/language.types.string.php) `$string`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$flags` = **`[FILEINFO\_NONE](https://www.php.net/manual/en/fileinfo.constants.php#constant.fileinfo-none)`**,

[?](https://www.php.net/manual/en/language.types.null.php)[resource](https://www.php.net/manual/en/language.types.resource.php) `$context` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**

): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Object-oriented style

public[finfo::buffer](https://www.php.net/manual/en/finfo.buffer.php)([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [int](https://www.php.net/manual/en/language.types.integer.php) `$flags` = **`[FILEINFO\_NONE](https://www.php.net/manual/en/fileinfo.constants.php#constant.fileinfo-none)`**, [?](https://www.php.net/manual/en/language.types.null.php)[resource](https://www.php.net/manual/en/language.types.resource.php) `$context` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

This function is used to get information about binary data in a string.


### Parameters [¶](https://www.php.net/manual/en/function.finfo-buffer.php\#refsect1-function.finfo-buffer-parameters)

`finfo`

An [finfo](https://www.php.net/manual/en/class.finfo.php) instance, returned by [finfo\_open()](https://www.php.net/manual/en/function.finfo-open.php).

`string`

Content of a file to be checked.


`flags`

One or disjunction of more [Fileinfo\\
constants](https://www.php.net/manual/en/fileinfo.constants.php).


`context`

### Return Values [¶](https://www.php.net/manual/en/function.finfo-buffer.php\#refsect1-function.finfo-buffer-returnvalues)

Returns a textual description of the `string`
argument, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if an error occurred.


### Changelog [¶](https://www.php.net/manual/en/function.finfo-buffer.php\#refsect1-function.finfo-buffer-changelog)

| Version | Description |
| --- | --- |
| 8.1.0 | The `finfo` parameter expects an [finfo](https://www.php.net/manual/en/class.finfo.php)<br> instance now; previously, a [resource](https://www.php.net/manual/en/language.types.resource.php) was expected. |
| 8.0.0 | `context` is nullable now. |

### Examples [¶](https://www.php.net/manual/en/function.finfo-buffer.php\#refsect1-function.finfo-buffer-examples)

**Example #1 A **finfo\_buffer()** example**

`<?php
$finfo = new finfo(FILEINFO_MIME);
echo $finfo->buffer($_POST["script"]) . "\n";
?>`

The above example will output
something similar to:

```
application/x-sh; charset=us-ascii
```

### See Also [¶](https://www.php.net/manual/en/function.finfo-buffer.php\#refsect1-function.finfo-buffer-seealso)

- [finfo\_file()](https://www.php.net/manual/en/function.finfo-file.php) \- Return information about a file

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/fileinfo/functions/finfo-buffer.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.finfo-buffer%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.finfo-buffer&repo=en&redirect=https://www.php.net/manual/en/function.finfo-buffer.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=104520&page=function.finfo-buffer&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104520&page=function.finfo-buffer&vote=down "Vote down!")

22


[**_contact at ingnu dot fr_**](https://www.php.net/manual/en/function.finfo-buffer.php#104520) [¶](https://www.php.net/manual/en/function.finfo-buffer.php#104520)

**14 years ago**

`You can easily check mime type of an internet resource using this code :
<?php
function getUrlMimeType($url) {
    $buffer = file_get_contents($url);
    $finfo = new finfo(FILEINFO_MIME_TYPE);
    return $finfo->buffer($buffer);
}
?>
I'm using it to detect if an url given by a user is a HTML page (so I do some stuff with the HTML) or a file on Internet (so I show an icon accordingly to the mime type).`

[up](https://www.php.net/manual/vote-note.php?id=118313&page=function.finfo-buffer&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118313&page=function.finfo-buffer&vote=down "Vote down!")

9


[**_nimasdj \[AT\] yahoo \[DOT\] com_**](https://www.php.net/manual/en/function.finfo-buffer.php#118313) [¶](https://www.php.net/manual/en/function.finfo-buffer.php#118313)

**9 years ago**

`You should never rely on finfo::buffer to get the MimeType of a file, you must always save the file physically or temporariliy and use finfo_open to get MimeType. I tested it with an excell file, with buffer it says octet-stream that is not valid, with finfo_open it says ms-excell as correct.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.finfo-buffer&repo=en&redirect=https://www.php.net/manual/en/function.finfo-buffer.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google