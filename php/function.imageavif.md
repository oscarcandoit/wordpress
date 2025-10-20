---
url: https://www.php.net/manual/en/function.imageavif.php
scraped_at: 2025-10-20T02:46:46.184Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imageavif

(PHP 8 >= 8.1.0)

imageavif — Output image to browser or file

### Description [¶](https://www.php.net/manual/en/function.imageavif.php\#refsect1-function.imageavif-description)

**imageavif**(

[GdImage](https://www.php.net/manual/en/class.gdimage.php) `$image`,

[resource](https://www.php.net/manual/en/language.types.resource.php)\|[string](https://www.php.net/manual/en/language.types.string.php)\|[null](https://www.php.net/manual/en/language.types.null.php) `$file` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[int](https://www.php.net/manual/en/language.types.integer.php) `$quality` = -1,

[int](https://www.php.net/manual/en/language.types.integer.php) `$speed` = -1

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Outputs or saves a AVIF Raster image from the given `image`.


### Parameters [¶](https://www.php.net/manual/en/function.imageavif.php\#refsect1-function.imageavif-parameters)

`image`

A [GdImage](https://www.php.net/manual/en/class.gdimage.php) object, returned by one of the image creation functions,
such as [imagecreatetruecolor()](https://www.php.net/manual/en/function.imagecreatetruecolor.php).

`file`

The path or an open stream resource (which is automatically closed after this function returns) to save the file to. If not set or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, the raw image stream will be output directly.


`quality`

`quality` is optional, and ranges from 0 (worst quality, smaller file)
to 100 (best quality, larger file).
If `-1` is provided, the default value `52` is used.


`speed`

`speed` is optional, and ranges from 0 (slow, smaller file)
to 10 (fast, larger file).
If `-1` is provided, the default value `6` is used.


### Return Values [¶](https://www.php.net/manual/en/function.imageavif.php\#refsect1-function.imageavif-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


**Caution**

However, if libgd fails to output the image, this function returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.

### Errors/Exceptions [¶](https://www.php.net/manual/en/function.imageavif.php\#refsect1-function.imageavif-errors)

Throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if `quality`
or `speed` is invalid.


### Changelog [¶](https://www.php.net/manual/en/function.imageavif.php\#refsect1-function.imageavif-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Now throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if `quality`<br> or `speed` is invalid. |

### See Also [¶](https://www.php.net/manual/en/function.imageavif.php\#refsect1-function.imageavif-seealso)

- [imagepng()](https://www.php.net/manual/en/function.imagepng.php) \- Output a PNG image to either the browser or a file
- [imagewbmp()](https://www.php.net/manual/en/function.imagewbmp.php) \- Output image to browser or file
- [imagejpeg()](https://www.php.net/manual/en/function.imagejpeg.php) \- Output image to browser or file
- [imagetypes()](https://www.php.net/manual/en/function.imagetypes.php) \- Return the image types supported by this PHP build

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/functions/imageavif.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imageavif%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imageavif&repo=en&redirect=https://www.php.net/manual/en/function.imageavif.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=127870&page=function.imageavif&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127870&page=function.imageavif&vote=down "Vote down!")

0


[**_avi at orons dot pro_**](https://www.php.net/manual/en/function.imageavif.php#127870) [¶](https://www.php.net/manual/en/function.imageavif.php#127870)

**2 years ago**

`Usage example:
$image = imagecreatefromjpeg('test.jpg');  //read a jpg file
imageavif($image, 'test.avif');  //save an avif file`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imageavif&repo=en&redirect=https://www.php.net/manual/en/function.imageavif.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google