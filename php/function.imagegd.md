---
url: https://www.php.net/manual/en/function.imagegd.php
scraped_at: 2025-10-20T03:01:05.482Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imagegd

(PHP 4 >= 4.0.7, PHP 5, PHP 7, PHP 8)

imagegd — Output GD image to browser or file

### Description [¶](https://www.php.net/manual/en/function.imagegd.php\#refsect1-function.imagegd-description)

**imagegd**([GdImage](https://www.php.net/manual/en/class.gdimage.php) `$image`, [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$file` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Outputs or saves the given `image` in GD format.


### Parameters [¶](https://www.php.net/manual/en/function.imagegd.php\#refsect1-function.imagegd-parameters)

`image`

A [GdImage](https://www.php.net/manual/en/class.gdimage.php) object, returned by one of the image creation functions,
such as [imagecreatetruecolor()](https://www.php.net/manual/en/function.imagecreatetruecolor.php).

`file`

The path or an open stream resource (which is automatically closed after this function returns) to save the file to. If not set or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, the raw image stream will be output directly.

### Return Values [¶](https://www.php.net/manual/en/function.imagegd.php\#refsect1-function.imagegd-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


**Caution**

However, if libgd fails to output the image, this function returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.

### Changelog [¶](https://www.php.net/manual/en/function.imagegd.php\#refsect1-function.imagegd-changelog)

| Version | Description |
| --- | --- |
| 8.0.3 | `file` is now nullable. |
| 8.0.0 | `image` expects a [GdImage](https://www.php.net/manual/en/class.gdimage.php)<br> instance now; previously, a valid `gd` [resource](https://www.php.net/manual/en/language.types.resource.php) was expected. |
| 7.2.0 | **imagegd()** now allows to output truecolor images.<br> Formerly, these have been implicitly converted to palette. |

### Examples [¶](https://www.php.net/manual/en/function.imagegd.php\#refsect1-function.imagegd-examples)

**Example #1 Outputting a GD image**

`<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  "A Simple Text String", $text_color);
// Output the image
imagegd($im);
?>`

**Example #2 Saving a GD image**

`<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  "A Simple Text String", $text_color);
// Save the gd image
// The file format for GD images is .gd, see http://www.libgd.org/GdFileFormats
imagegd($im, 'simple.gd');
?>`

### Notes [¶](https://www.php.net/manual/en/function.imagegd.php\#refsect1-function.imagegd-notes)

> **Note**:
>
>
> The GD format is commonly used to allow fast loading of parts of images.
> Note that the GD format is only usable in GD-compatible applications.

**Warning**

The GD
and GD2 image formats are proprietary image formats of libgd. They have to be regarded
_obsolete_, and should only be used for development and testing
purposes.

### See Also [¶](https://www.php.net/manual/en/function.imagegd.php\#refsect1-function.imagegd-seealso)

- [imagegd2()](https://www.php.net/manual/en/function.imagegd2.php) \- Output GD2 image to browser or file

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/functions/imagegd.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imagegd%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagegd&repo=en&redirect=https://www.php.net/manual/en/function.imagegd.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google