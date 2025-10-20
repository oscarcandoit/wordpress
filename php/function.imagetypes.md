---
url: https://www.php.net/manual/en/function.imagetypes.php
scraped_at: 2025-10-20T02:56:20.674Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imagetypes

(PHP 4 >= 4.0.2, PHP 5, PHP 7, PHP 8)

imagetypes — Return the image types supported by this PHP build

### Description [¶](https://www.php.net/manual/en/function.imagetypes.php\#refsect1-function.imagetypes-description)

**imagetypes**(): [int](https://www.php.net/manual/en/language.types.integer.php)

Returns the image types supported by the current PHP installation.


### Parameters [¶](https://www.php.net/manual/en/function.imagetypes.php\#refsect1-function.imagetypes-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/function.imagetypes.php\#refsect1-function.imagetypes-returnvalues)

Returns a bit-field corresponding to the image formats supported by the
version of GD linked into PHP. The following bits are returned,
**`[IMG\_AVIF](https://www.php.net/manual/en/image.constants.php#constant.img-avif)`** \| **`[IMG\_BMP](https://www.php.net/manual/en/image.constants.php#constant.img-bmp)`** \|
**`[IMG\_GIF](https://www.php.net/manual/en/image.constants.php#constant.img-gif)`** \| **`[IMG\_JPG](https://www.php.net/manual/en/image.constants.php#constant.img-jpg)`** \|
**`[IMG\_PNG](https://www.php.net/manual/en/image.constants.php#constant.img-png)`** \| **`[IMG\_WBMP](https://www.php.net/manual/en/image.constants.php#constant.img-wbmp)`** \|
**`[IMG\_XPM](https://www.php.net/manual/en/image.constants.php#constant.img-xpm)`** \| **`[IMG\_WEBP](https://www.php.net/manual/en/image.constants.php#constant.img-webp)`**.


### Changelog [¶](https://www.php.net/manual/en/function.imagetypes.php\#refsect1-function.imagetypes-changelog)

| Version | Description |
| --- | --- |
| 8.1.0 | **`[IMG\_AVIF](https://www.php.net/manual/en/image.constants.php#constant.img-avif)`** added. |
| 7.2.0 | **`[IMG\_BMP](https://www.php.net/manual/en/image.constants.php#constant.img-bmp)`** added. |
| 7.0.10 | **`[IMG\_WEBP](https://www.php.net/manual/en/image.constants.php#constant.img-webp)`** added. |

### Examples [¶](https://www.php.net/manual/en/function.imagetypes.php\#refsect1-function.imagetypes-examples)

**Example #1 Checking for PNG support**

`<?php
if (imagetypes() & IMG_PNG) {
    echo "PNG Support is enabled";
}
?>`

### See Also [¶](https://www.php.net/manual/en/function.imagetypes.php\#refsect1-function.imagetypes-seealso)

- [gd\_info()](https://www.php.net/manual/en/function.gd-info.php) \- Retrieve information about the currently installed GD library

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/functions/imagetypes.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imagetypes%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagetypes&repo=en&redirect=https://www.php.net/manual/en/function.imagetypes.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google