---
url: https://www.php.net/manual/en/imagickdraw.setfontsize.php
scraped_at: 2025-10-20T02:58:37.401Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ImagickDraw::setFontSize

(PECL imagick 2, PECL imagick 3)

ImagickDraw::setFontSize — Sets the font pointsize to use when annotating with text

### Description [¶](https://www.php.net/manual/en/imagickdraw.setfontsize.php\#refsect1-imagickdraw.setfontsize-description)

public**ImagickDraw::setFontSize**([float](https://www.php.net/manual/en/language.types.float.php) `$point_size`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**Warning**

This function is
currently not documented; only its argument list is available.

Sets the font pointsize to use when annotating with text.


### Parameters [¶](https://www.php.net/manual/en/imagickdraw.setfontsize.php\#refsect1-imagickdraw.setfontsize-parameters)

`point_size`

the point size


### Return Values [¶](https://www.php.net/manual/en/imagickdraw.setfontsize.php\#refsect1-imagickdraw.setfontsize-returnvalues)

No value is returned.


### Examples [¶](https://www.php.net/manual/en/imagickdraw.setfontsize.php\#refsect1-imagickdraw.setfontsize-examples)

**Example #1 **ImagickDraw::setFontSize()** example**

`<?php
function setFontSize($fillColor, $strokeColor, $backgroundColor) {
    $draw = new \ImagickDraw();
    $draw->setStrokeOpacity(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(2);
    $draw->setFont("../fonts/Arial.ttf");
    $sizes = [24, 36, 48, 60, 72];
    foreach ($sizes as $size) {
        $draw->setFontSize($size);
        $draw->annotation(50, ($size * $size / 16), "Lorem Ipsum!");
    }
    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);
    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}
?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/imagick/imagickdraw/setfontsize.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fimagickdraw.setfontsize%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=imagickdraw.setfontsize&repo=en&redirect=https://www.php.net/manual/en/imagickdraw.setfontsize.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=92670&page=imagickdraw.setfontsize&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92670&page=imagickdraw.setfontsize&vote=down "Vote down!")

6


[**_hmkrox at gmail dot com_**](https://www.php.net/manual/en/imagickdraw.setfontsize.php#92670) [¶](https://www.php.net/manual/en/imagickdraw.setfontsize.php#92670)

**16 years ago**

`The font size taken in parameter is not the size in point (1 point = 1/72 inch) but the font's height in pixel.
Therefore you should do a conversion to have the correct font size if you want to modify a document destined to print.
For example, if your document's resolution is 300ppi, you should add a 25/6 multiplying factor to your fontsize in order to have a correct behaviour of the font.`

[up](https://www.php.net/manual/vote-note.php?id=92241&page=imagickdraw.setfontsize&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92241&page=imagickdraw.setfontsize&vote=down "Vote down!")

 -4


[**_jgsujith at in dot com_**](https://www.php.net/manual/en/imagickdraw.setfontsize.php#92241) [¶](https://www.php.net/manual/en/imagickdraw.setfontsize.php#92241)

**16 years ago**

`<?php
$sourceFile='in.jpg';
$textWrite='God is Great';
$x=50;
$y=50;
$fontColor='#000000';
$fontSize=34;

$colorPix=new ImagickPixel ($fontColor);
$image=new Imagick ($sourceFile);
$draw=new ImagickDraw();

$draw->setFontSize($fontSize);//Sets the font pointsize to use when annotating with text
$draw->setFillColor($colorPix);//Sets the fill color to be used for drawing filled objects

$image->annotateImage($draw,$x,$y,0,$textWrite);//Annotates an image with text
$image->writeImage('out.jpg');//Writes an image to the specified filename
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=imagickdraw.setfontsize&repo=en&redirect=https://www.php.net/manual/en/imagickdraw.setfontsize.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google