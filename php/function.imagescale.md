---
url: https://www.php.net/manual/en/function.imagescale.php
scraped_at: 2025-10-20T02:58:25.768Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imagescale

(PHP 5 >= 5.5.0, PHP 7, PHP 8)

imagescale — Scale an image using the given new width and height

### Description [¶](https://www.php.net/manual/en/function.imagescale.php\#refsect1-function.imagescale-description)

**imagescale**(

[GdImage](https://www.php.net/manual/en/class.gdimage.php) `$image`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$width`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$height` = -1,

[int](https://www.php.net/manual/en/language.types.integer.php) `$mode` = **`[IMG\_BILINEAR\_FIXED](https://www.php.net/manual/en/image.constants.php#constant.img-bilinear-fixed)`**

): [GdImage](https://www.php.net/manual/en/class.gdimage.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

**imagescale()** scales an image using the given
interpolation algorithm.


> **Note**:
>
>
> Unlike many of other image functions, **imagescale()** does
> not modify the passed `image`; instead, a
> _new_ image is returned.

### Parameters [¶](https://www.php.net/manual/en/function.imagescale.php\#refsect1-function.imagescale-parameters)

`image`

A [GdImage](https://www.php.net/manual/en/class.gdimage.php) object, returned by one of the image creation functions,
such as [imagecreatetruecolor()](https://www.php.net/manual/en/function.imagecreatetruecolor.php).

`width`

The width to scale the image to.


`height`

The height to scale the image to. If omitted or negative, the aspect
ratio will be preserved.


`mode`

One of **`[IMG\_NEAREST\_NEIGHBOUR](https://www.php.net/manual/en/image.constants.php#constant.img-nearest-neighbour)`**,
**`[IMG\_BILINEAR\_FIXED](https://www.php.net/manual/en/image.constants.php#constant.img-bilinear-fixed)`**,
**`[IMG\_BICUBIC](https://www.php.net/manual/en/image.constants.php#constant.img-bicubic)`**,
**`[IMG\_BICUBIC\_FIXED](https://www.php.net/manual/en/image.constants.php#constant.img-bicubic-fixed)`** or anything else (will use two
pass).


> **Note**:
> **`[IMG\_WEIGHTED4](https://www.php.net/manual/en/image.constants.php#constant.img-weighted4)`** is not yet supported.

### Return Values [¶](https://www.php.net/manual/en/function.imagescale.php\#refsect1-function.imagescale-returnvalues)

Return the scaled image object on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.imagescale.php\#refsect1-function.imagescale-errors)

Throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if `width`
or `height` would cause over-/underflow.


Throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if `mode` is invalid.


### Changelog [¶](https://www.php.net/manual/en/function.imagescale.php\#refsect1-function.imagescale-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Now throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if `width`<br> or `height` would cause over-/underflow. |
| 8.4.0 | Now throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if `mode` is invalid. |
| 8.0.0 | On success, this function returns a [GDImage](https://www.php.net/manual/en/class.gdimage.php) instance now;<br> previously, a [resource](https://www.php.net/manual/en/language.types.resource.php) was returned. |
| 8.0.0 | `image` expects a [GdImage](https://www.php.net/manual/en/class.gdimage.php)<br> instance now; previously, a valid `gd` [resource](https://www.php.net/manual/en/language.types.resource.php) was expected. |

### See Also [¶](https://www.php.net/manual/en/function.imagescale.php\#refsect1-function.imagescale-seealso)

- [imagecopyresized()](https://www.php.net/manual/en/function.imagecopyresized.php) \- Copy and resize part of an image
- [imagecopyresampled()](https://www.php.net/manual/en/function.imagecopyresampled.php) \- Copy and resize part of an image with resampling

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/functions/imagescale.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imagescale%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagescale&repo=en&redirect=https://www.php.net/manual/en/function.imagescale.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=128346&page=function.imagescale&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128346&page=function.imagescale&vote=down "Vote down!")

9


[**_Anonymous_**](https://www.php.net/manual/en/function.imagescale.php#128346) [¶](https://www.php.net/manual/en/function.imagescale.php#128346)

**2 years ago**

`Seemingly, you can't omit the width the same way you do with the height. If you write -1 for the width and specify a number for the height it will return false`

[up](https://www.php.net/manual/vote-note.php?id=130219&page=function.imagescale&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130219&page=function.imagescale&vote=down "Vote down!")

0


[**_cognettings at gmail dot com_**](https://www.php.net/manual/en/function.imagescale.php#130219) [¶](https://www.php.net/manual/en/function.imagescale.php#130219)

**6 months ago**

`To resize height without specifying a width you can rotate the image by 90 degrees, resize, then rotate by 270 degrees.
        $outputImage = imagerotate($image, 90, 0);
        $outputImage = imagescale($outputImage, $minSize);
        $outputImage = imagerotate($outputImage, 270, 0);`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagescale&repo=en&redirect=https://www.php.net/manual/en/function.imagescale.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google