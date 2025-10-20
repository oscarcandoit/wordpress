---
url: https://www.php.net/manual/en/function.imagesetthickness.php
scraped_at: 2025-10-20T02:49:11.554Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imagesetthickness

(PHP 4 >= 4.0.6, PHP 5, PHP 7, PHP 8)

imagesetthickness — Set the thickness for line drawing

### Description [¶](https://www.php.net/manual/en/function.imagesetthickness.php\#refsect1-function.imagesetthickness-description)

**imagesetthickness**([GdImage](https://www.php.net/manual/en/class.gdimage.php) `$image`, [int](https://www.php.net/manual/en/language.types.integer.php) `$thickness`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**imagesetthickness()** sets the thickness of the lines
drawn when drawing rectangles, polygons, arcs etc. to
`thickness` pixels.


### Parameters [¶](https://www.php.net/manual/en/function.imagesetthickness.php\#refsect1-function.imagesetthickness-parameters)

`image`

A [GdImage](https://www.php.net/manual/en/class.gdimage.php) object, returned by one of the image creation functions,
such as [imagecreatetruecolor()](https://www.php.net/manual/en/function.imagecreatetruecolor.php).

`thickness`

Thickness, in pixels.


### Return Values [¶](https://www.php.net/manual/en/function.imagesetthickness.php\#refsect1-function.imagesetthickness-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Changelog [¶](https://www.php.net/manual/en/function.imagesetthickness.php\#refsect1-function.imagesetthickness-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `image` expects a [GdImage](https://www.php.net/manual/en/class.gdimage.php)<br> instance now; previously, a valid `gd` [resource](https://www.php.net/manual/en/language.types.resource.php) was expected. |

### Examples [¶](https://www.php.net/manual/en/function.imagesetthickness.php\#refsect1-function.imagesetthickness-examples)

**Example #1 **imagesetthickness()** example**

`<?php
// Create a 200x100 image
$im = imagecreatetruecolor(200, 100);
$white = imagecolorallocate($im, 0xFF, 0xFF, 0xFF);
$black = imagecolorallocate($im, 0x00, 0x00, 0x00);
// Set the background to be white
imagefilledrectangle($im, 0, 0, 299, 99, $white);
// Set the line thickness to 5
imagesetthickness($im, 5);
// Draw the rectangle
imagerectangle($im, 14, 14, 185, 85, $black);
// Output image to the browser
header('Content-Type: image/png');
imagepng($im);
?>`

The above example will output
something similar to:

![Output of example : imagesetthickness()](https://www.php.net/manual/en/images/21009b70229598c6a80eef8b45bf282b-imagesetthickness.png)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/functions/imagesetthickness.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imagesetthickness%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagesetthickness&repo=en&redirect=https://www.php.net/manual/en/function.imagesetthickness.php)

### User Contributed Notes 9 notes

[up](https://www.php.net/manual/vote-note.php?id=86007&page=function.imagesetthickness&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86007&page=function.imagesetthickness&vote=down "Vote down!")

11


[**_bpatru at gmail dot com_**](https://www.php.net/manual/en/function.imagesetthickness.php#86007) [¶](https://www.php.net/manual/en/function.imagesetthickness.php#86007)

**17 years ago**

`Apparently imagesetthickness doesn't work if antialiasing is set to true.`

[up](https://www.php.net/manual/vote-note.php?id=112855&page=function.imagesetthickness&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112855&page=function.imagesetthickness&vote=down "Vote down!")

5


[**_azinkey at gmail dot com_**](https://www.php.net/manual/en/function.imagesetthickness.php#112855) [¶](https://www.php.net/manual/en/function.imagesetthickness.php#112855)

**12 years ago**

`thanks circle14,
just change the line & see its solved what we need for ellipse
while ($line < $thickness) {
        $line++;
        $elipse_w--;
        imageellipse($image, $pos_x, $pos_y, $elipse_w, $elipse_h, $color);
        $elipse_h--;
    }`

[up](https://www.php.net/manual/vote-note.php?id=76036&page=function.imagesetthickness&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76036&page=function.imagesetthickness&vote=down "Vote down!")

1


[**_ab at cd dot com_**](https://www.php.net/manual/en/function.imagesetthickness.php#76036) [¶](https://www.php.net/manual/en/function.imagesetthickness.php#76036)

**18 years ago**

`Note: Also, for me (working under PHP 5.0.2) this function ONLY seems to work with imageline...`

[up](https://www.php.net/manual/vote-note.php?id=93994&page=function.imagesetthickness&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93994&page=function.imagesetthickness&vote=down "Vote down!")

1


[**_fred at nowhere dot fr_**](https://www.php.net/manual/en/function.imagesetthickness.php#93994) [¶](https://www.php.net/manual/en/function.imagesetthickness.php#93994)

**16 years ago**

`One thing worse to mention is that imagesetthikness() works on the next object you draw.
For ex : you can draw a grid within a grapg with a thickness of 1
by invoking imagesetthickness($image, 1);
... script to draw your grid...
and then invoke imagesetthikness with a draw your graph lines with a thickness of 3
imagesetthickness($image, 3);
... script to draw your graph lines...
Hope this helps...`

[up](https://www.php.net/manual/vote-note.php?id=91866&page=function.imagesetthickness&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91866&page=function.imagesetthickness&vote=down "Vote down!")

1


[**_jean-raymond dot chauviere at gmail dot com_**](https://www.php.net/manual/en/function.imagesetthickness.php#91866) [¶](https://www.php.net/manual/en/function.imagesetthickness.php#91866)

**16 years ago**

`An easier to manage thickness is, before to draw in the ellipse to play with 2 ellipse with different color :
<?php
        imagefilledellipse  ($this->image,60,42,57,57,$drawColor);
        imagefilledellipse  ($this->image,60,42,45,45,$backColor);
?>
The first line draw a filled ellipse with the wanted color, and the 2nd one, draw an ellipse with the background color from the same center, but is smaller.
The drawback of this method is that you erase everything in the middle of the ellipse.`

[up](https://www.php.net/manual/vote-note.php?id=119174&page=function.imagesetthickness&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119174&page=function.imagesetthickness&vote=down "Vote down!")

0


[**_gmail.com@mspreij_**](https://www.php.net/manual/en/function.imagesetthickness.php#119174) [¶](https://www.php.net/manual/en/function.imagesetthickness.php#119174)

**9 years ago**

`As you can see in the example image, the left and right sides are 1 px wider than they should be, this is the case for every width > 1.
Wrote this function to fix that bit.. probably not a drop-in replacement though. It draws a rectangle *around* the given coordinates, for any width line.
<?php
// draw a $width-wide line AROUND the given coordinates, keeping in mind 0,0,1,1 yields a 2×2 square
function imagelinerectangle($img, $x1, $y1, $x2, $y2, $color, $width=1) {
    imagefilledrectangle($img, $x1-$width, $y1-$width, $x2+$width, $y1-1, $color);
    imagefilledrectangle($img, $x2+1, $y1-$width, $x2+$width, $y2+$width, $color);
    imagefilledrectangle($img, $x1-$width, $y2+1, $x2+$width, $y2+$width, $color);
    imagefilledrectangle($img, $x1-$width, $y1-$width, $x1-1, $y2+$width, $color);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=88639&page=function.imagesetthickness&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88639&page=function.imagesetthickness&vote=down "Vote down!")

0


[**_admin at circle14 dot net_**](https://www.php.net/manual/en/function.imagesetthickness.php#88639) [¶](https://www.php.net/manual/en/function.imagesetthickness.php#88639)

**16 years ago**

`Here is a custom function I wrote that addresses the line thickness issues with ellipses :
<?php
function draw_oval ($image, $pos_x, $pos_y, $elipse_width, $elipse_height, $color, $px_thick) {
    $line = 0;
    $thickness = $px_thick;
    $elipse_w = $elipse_width;
    $elipse_h = $elipse_height;
    while ($line < $thickness) {
        imageellipse($image, $pos_x, $pos_y, $elipse_w, $elipse_h, $color);
        $line++;
        $elipse_w--;
        $elipse_h--;
    }
}
?>
I hope you find this useful.`

[up](https://www.php.net/manual/vote-note.php?id=81741&page=function.imagesetthickness&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81741&page=function.imagesetthickness&vote=down "Vote down!")

 -1


[**_baldurien at bbnwn dot eu_**](https://www.php.net/manual/en/function.imagesetthickness.php#81741) [¶](https://www.php.net/manual/en/function.imagesetthickness.php#81741)

**17 years ago**

`The way that imagesetthickness works with imagerectangle() is pretty strange.
<?php
imagesetthickness(1);
imagerectangle($im, 10, 10, 50, 50, $red);
?>
This will draw a 41x41 square (because gd need the bottom right pixel, inclusive. 50 should get replaced by 49). This will "work" like:
<?php
imageline($im, 10, 10, 10, 50, $red);
imageline($im, 10, 10, 50, 10, $red);
imageline($im, 50, 10, 50, 50, $red);
imageline($im, 10, 50, 50, 50, $red);
?>
The second example:
<?php
imagesetthickness(2);
imagerectangle($im, 10, 10, 50, 50, $red);
?>
This will draw a 43x43 square because the border (thickness) is set to 2. *however* this is not a "regular" border of 2 pixels around the 41x41 original square!
On the left and right, there will be a thickness of 3, while there we be a thickness of 2.
If you take the imageline example, but set the thickness before to 2, this will *almost* do the trick: the left most pixel of the square will not be drawn.
To conclude:
1) do not forget that (width, height) of drawn rectangle is (x2-x1+1, y2-y1+1)
2) thickness is bad implemented (or at least, the behavior i s not documented) on rectangle, as the left/right thickness is not the wanted one.
3) 4*imageline() should do the trick, but after "patching" the top left pixel.`

[up](https://www.php.net/manual/vote-note.php?id=74166&page=function.imagesetthickness&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74166&page=function.imagesetthickness&vote=down "Vote down!")

 -5


[**_-private-_**](https://www.php.net/manual/en/function.imagesetthickness.php#74166) [¶](https://www.php.net/manual/en/function.imagesetthickness.php#74166)

**18 years ago**

`There is a known bug. Imagesetthickness is NOT working on ellipse.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagesetthickness&repo=en&redirect=https://www.php.net/manual/en/function.imagesetthickness.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google