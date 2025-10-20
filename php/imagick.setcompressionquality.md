---
url: https://www.php.net/manual/en/imagick.setcompressionquality.php
scraped_at: 2025-10-20T02:51:43.124Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Imagick::setCompressionQuality

(PECL imagick 2, PECL imagick 3)

Imagick::setCompressionQuality — Sets the object's default compression quality

### Description [¶](https://www.php.net/manual/en/imagick.setcompressionquality.php\#refsect1-imagick.setcompressionquality-description)

public**Imagick::setCompressionQuality**([int](https://www.php.net/manual/en/language.types.integer.php) `$quality`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Sets the object's default compression quality.


**Caution**

This method only works for new images e.g. those created through Imagick::newPseudoImage. For existing images you should use [Imagick::setImageCompressionQuality()](https://www.php.net/manual/en/imagick.setimagecompressionquality.php).


### Parameters [¶](https://www.php.net/manual/en/imagick.setcompressionquality.php\#refsect1-imagick.setcompressionquality-parameters)

`quality`

An [int](https://www.php.net/manual/en/language.types.integer.php) between 1 and 100, 1 = high compression, 100 low compression.


### Return Values [¶](https://www.php.net/manual/en/imagick.setcompressionquality.php\#refsect1-imagick.setcompressionquality-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success.


### Examples [¶](https://www.php.net/manual/en/imagick.setcompressionquality.php\#refsect1-imagick.setcompressionquality-examples)

**Example #1 **Imagick::setCompressionQuality()****

`<?php
function setCompressionQuality($imagePath, $quality) {
    $backgroundImagick = new \Imagick(realpath($imagePath));
    $imagick = new \Imagick();
    $imagick->setCompressionQuality($quality);
    $imagick->newPseudoImage(
        $backgroundImagick->getImageWidth(),
        $backgroundImagick->getImageHeight(),
        'canvas:white'
    );
    $imagick->compositeImage(
        $backgroundImagick,
        \Imagick::COMPOSITE_ATOP,
        0,
        0
    );

    $imagick->setFormat("jpg");
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}
?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/imagick/imagick/setcompressionquality.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fimagick.setcompressionquality%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=imagick.setcompressionquality&repo=en&redirect=https://www.php.net/manual/en/imagick.setcompressionquality.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=96836&page=imagick.setcompressionquality&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96836&page=imagick.setcompressionquality&vote=down "Vote down!")

31


[**_deeps chennai_**](https://www.php.net/manual/en/imagick.setcompressionquality.php#96836) [¶](https://www.php.net/manual/en/imagick.setcompressionquality.php#96836)

**15 years ago**

`A note for people who just couldn't get this working..
With PHP 5.1.6, the below works:
<?php
$img->setCompression(Imagick::COMPRESSION_JPEG);
$img->setCompressionQuality(80);
?>
However, with higher versions of PHP (I tried on PHP 5.2.10), the code has no effect (and there are no exceptions or warnings thrown by Imagick as well).
The code that works instead is:
<?php
$img->setImageCompression(Imagick::COMPRESSION_JPEG);
$img->setImageCompressionQuality(80);
?>
and this is backwards compatible (Works on PHP 5.1.6 as well as 5.2.10)`

[up](https://www.php.net/manual/vote-note.php?id=99209&page=imagick.setcompressionquality&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99209&page=imagick.setcompressionquality&vote=down "Vote down!")

5


[**_charles dot hall at sas dot com_**](https://www.php.net/manual/en/imagick.setcompressionquality.php#99209) [¶](https://www.php.net/manual/en/imagick.setcompressionquality.php#99209)

**15 years ago**

`I had to insert a call to "stripImage()" in order to actually see the filesize shrink.
<?php
$img = new Imagick();
$img->readImage($src);
$img->setImageCompression(imagick::COMPRESSION_JPEG);
$img->setImageCompressionQuality(90);
$img->stripImage();
$img->writeImage($dest);
?>`

[up](https://www.php.net/manual/vote-note.php?id=82080&page=imagick.setcompressionquality&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82080&page=imagick.setcompressionquality&vote=down "Vote down!")

 -4


[**_nVaux.com_**](https://www.php.net/manual/en/imagick.setcompressionquality.php#82080) [¶](https://www.php.net/manual/en/imagick.setcompressionquality.php#82080)

**17 years ago**

`Sebastian's example works excellent, just one minor spelling mistake, it will give you an error otherwise.
<?php
$img->setCompression(Imagick::COMPRESSION_JPEG);
$img->setCompressionQuality(80);
?>
I used Sebastians example, and made one that compresses all the images within a directory:
<?php
$images = new Imagick(glob('images/*.jpg'));
foreach($images as $image)
{
    // compression methods, see "Contants"-page for Imagick
    $image->setCompression(imagick::COMPRESSION_JPEG);
    // a value between 1 and 100, 1 = high compression, 100 low compression
    $image->setCompressionQuality(80);
    $image->writeImage();
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=imagick.setcompressionquality&repo=en&redirect=https://www.php.net/manual/en/imagick.setcompressionquality.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google