---
url: https://www.php.net/manual/en/imagick.cropimage.php
scraped_at: 2025-10-20T02:56:35.218Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Imagick::cropImage

(PECL imagick 2, PECL imagick 3)

Imagick::cropImage — Extracts a region of the image

### Description [¶](https://www.php.net/manual/en/imagick.cropimage.php\#refsect1-imagick.cropimage-description)

public**Imagick::cropImage**(

[int](https://www.php.net/manual/en/language.types.integer.php) `$width`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$height`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$x`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$y`

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Extracts a region of the image.


### Parameters [¶](https://www.php.net/manual/en/imagick.cropimage.php\#refsect1-imagick.cropimage-parameters)

`width`

The width of the crop


`height`

The height of the crop


`x`

The X coordinate of the cropped region's top left corner


`y`

The Y coordinate of the cropped region's top left corner


### Return Values [¶](https://www.php.net/manual/en/imagick.cropimage.php\#refsect1-imagick.cropimage-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success.


### Errors/Exceptions [¶](https://www.php.net/manual/en/imagick.cropimage.php\#refsect1-imagick.cropimage-errors)

Throws ImagickException on error.


### Examples [¶](https://www.php.net/manual/en/imagick.cropimage.php\#refsect1-imagick.cropimage-examples)

**Example #1 **Imagick::cropImage()****

`<?php
function cropImage($imagePath, $startX, $startY, $width, $height) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->cropImage($width, $height, $startX, $startY);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}
?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/imagick/imagick/cropimage.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fimagick.cropimage%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=imagick.cropimage&repo=en&redirect=https://www.php.net/manual/en/imagick.cropimage.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=97232&page=imagick.cropimage&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=97232&page=imagick.cropimage&vote=down "Vote down!")

17


[**_Christian Dehning_**](https://www.php.net/manual/en/imagick.cropimage.php#97232) [¶](https://www.php.net/manual/en/imagick.cropimage.php#97232)

**15 years ago**

`When cropping gif-images (I had no problems with jpg and png images), the canvas is not removed. Please run the following command on the cropped gif, to remove the blank space:
$im->setImagePage(0, 0, 0, 0);`

[up](https://www.php.net/manual/vote-note.php?id=119086&page=imagick.cropimage&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119086&page=imagick.cropimage&vote=down "Vote down!")

5


[**_olav at schettler dot net_**](https://www.php.net/manual/en/imagick.cropimage.php#119086) [¶](https://www.php.net/manual/en/imagick.cropimage.php#119086)

**9 years ago**

`Here is a simple function to create a thumbnail. It accepts an additional parameter to set the focus point of the generated thumbnail:
<?php
function thumbnail($image, $new_w, $new_h, $focus = 'center')
{
    $w = $image->getImageWidth();
    $h = $image->getImageHeight();
    if ($w > $h) {
        $resize_w = $w * $new_h / $h;
        $resize_h = $new_h;
    }
    else {
        $resize_w = $new_w;
        $resize_h = $h * $new_w / $w;
    }
    $image->resizeImage($resize_w, $resize_h, Imagick::FILTER_LANCZOS, 0.9);
    switch ($focus) {
        case 'northwest':
            $image->cropImage($new_w, $new_h, 0, 0);
            break;
        case 'center':
            $image->cropImage($new_w, $new_h, ($resize_w - $new_w) / 2, ($resize_h - $new_h) / 2);
            break;
        case 'northeast':
            $image->cropImage($new_w, $new_h, $resize_w - $new_w, 0);
            break;
        case 'southwest':
            $image->cropImage($new_w, $new_h, 0, $resize_h - $new_h);
            break;
        case 'southeast':
            $image->cropImage($new_w, $new_h, $resize_w - $new_w, $resize_h - $new_h);
            break;
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=100772&page=imagick.cropimage&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100772&page=imagick.cropimage&vote=down "Vote down!")

5


[**_ElPadre_**](https://www.php.net/manual/en/imagick.cropimage.php#100772) [¶](https://www.php.net/manual/en/imagick.cropimage.php#100772)

**14 years ago**

`Actually, the Imagick::setImagePage(0,0,0,0) is also handy with jpgs and pngs, if you plan to do any more changes on the cropped image that involves positioning and/or gravity (I created a script that does crop, face blur and watermarking in one go, and had a hell of a time determining why the blurs and the watermark text never showed up...).`

[up](https://www.php.net/manual/vote-note.php?id=117087&page=imagick.cropimage&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117087&page=imagick.cropimage&vote=down "Vote down!")

 -2


[**_oxxido at gmail dot com_**](https://www.php.net/manual/en/imagick.cropimage.php#117087) [¶](https://www.php.net/manual/en/imagick.cropimage.php#117087)

**10 years ago**

`I have a function that takes an image, resize and crop it, and save it as normal, then resize it again and crop it again to create the thumbnail. The numbers of the second crop were WAY off, and the calculations were perfect, the problem, was the second crop wasn't resetting the imagePage, so if you try to crop the same image twice, it will be a good idea to reset it first:
<?php
$thumb = new Imagick($file)
$thumb->resizeImage($r_w1,$r_h1,Imagick::FILTER_CATROM,0.9, false);
$thumb->cropImage($w1,$h1,$l1,$t1);
$thumb->writeImage($destinationPath.'/'.$fileName);
$thumb->resizeImage($r_w2,$r_h2,Imagick::FILTER_CATROM,0.9, false);
$thumb->setImagePage(0, 0, 0, 0);
$thumb->cropImage($w2,$h2,$l2,$t2);
$thumb->writeImage($destinationPath.'/'.$fileNameThumb);
?>
BTW, i needed perfect dimentions so i had to set the "bestfit" to false.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=imagick.cropimage&repo=en&redirect=https://www.php.net/manual/en/imagick.cropimage.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google