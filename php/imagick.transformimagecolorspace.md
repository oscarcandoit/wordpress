---
url: https://www.php.net/manual/en/imagick.transformimagecolorspace.php
scraped_at: 2025-10-20T02:51:25.640Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Imagick::transformImageColorspace

(PECL imagick 3)

Imagick::transformImageColorspace — Transforms an image to a new colorspace

### Description [¶](https://www.php.net/manual/en/imagick.transformimagecolorspace.php\#refsect1-imagick.transformimagecolorspace-description)

public**Imagick::transformImageColorspace**([int](https://www.php.net/manual/en/language.types.integer.php) `$colorspace`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Transforms an image to a new colorspace.


### Parameters [¶](https://www.php.net/manual/en/imagick.transformimagecolorspace.php\#refsect1-imagick.transformimagecolorspace-parameters)

`colorspace`

The colorspace the image should be transformed to, one of the [COLORSPACE constants](https://www.php.net/manual/en/imagick.constants.php#imagick.constants.colorspace) e.g. Imagick::COLORSPACE\_CMYK.


### Return Values [¶](https://www.php.net/manual/en/imagick.transformimagecolorspace.php\#refsect1-imagick.transformimagecolorspace-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success.


### Examples [¶](https://www.php.net/manual/en/imagick.transformimagecolorspace.php\#refsect1-imagick.transformimagecolorspace-examples)

**Example #1 **Imagick::transformImageColorspace()** example**

Transforms an image to a new colorspace, and then extracts a single channel so that the individual channel values can be viewed.


`<?php
function transformImageColorspace($imagePath, $colorSpace, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->transformimagecolorspace($colorSpace);
    //channel should be one of the channel constants e.g. \Imagick::CHANNEL_BLUE
    $imagick->separateImageChannel($channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}
?>`

### See Also [¶](https://www.php.net/manual/en/imagick.transformimagecolorspace.php\#refsect1-imagick.transformimagecolorspace-seealso)

- [Imagick::setColorSpace()](https://www.php.net/manual/en/imagick.setcolorspace.php) \- Set colorspace

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/imagick/imagick/transformimagecolorspace.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fimagick.transformimagecolorspace%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=imagick.transformimagecolorspace&repo=en&redirect=https://www.php.net/manual/en/imagick.transformimagecolorspace.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=117100&page=imagick.transformimagecolorspace&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117100&page=imagick.transformimagecolorspace&vote=down "Vote down!")

0


[**_A.Ross_**](https://www.php.net/manual/en/imagick.transformimagecolorspace.php#117100) [¶](https://www.php.net/manual/en/imagick.transformimagecolorspace.php#117100)

**10 years ago**

`This SO question and answer might help clarify why transformImageColorspace is useful: [http://stackoverflow.com/questions/29296779/convert-pdf-with-transparency-and-cmyk-to-jpg](http://stackoverflow.com/questions/29296779/convert-pdf-with-transparency-and-cmyk-to-jpg)
Also, there's a Github issue here that explains the difference between transformImageColorspace and setImageColorspace: [https://github.com/rmagick/rmagick/pull/75](https://github.com/rmagick/rmagick/pull/75)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=imagick.transformimagecolorspace&repo=en&redirect=https://www.php.net/manual/en/imagick.transformimagecolorspace.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google