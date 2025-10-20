---
url: https://www.php.net/manual/en/function.imagecolorat.php
scraped_at: 2025-10-20T02:48:11.223Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imagecolorat

(PHP 4, PHP 5, PHP 7, PHP 8)

imagecolorat — Get the index of the color of a pixel

### Description [¶](https://www.php.net/manual/en/function.imagecolorat.php\#refsect1-function.imagecolorat-description)

**imagecolorat**([GdImage](https://www.php.net/manual/en/class.gdimage.php) `$image`, [int](https://www.php.net/manual/en/language.types.integer.php) `$x`, [int](https://www.php.net/manual/en/language.types.integer.php) `$y`): [int](https://www.php.net/manual/en/language.types.integer.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Returns the index of the color of the pixel at the
specified location in the image specified by `image`.


If the image is a
truecolor image, this function returns the RGB value of that pixel as
integer. Use bitshifting and masking to access the distinct red, green and blue
component values:


### Parameters [¶](https://www.php.net/manual/en/function.imagecolorat.php\#refsect1-function.imagecolorat-parameters)

`image`

A [GdImage](https://www.php.net/manual/en/class.gdimage.php) object, returned by one of the image creation functions,
such as [imagecreatetruecolor()](https://www.php.net/manual/en/function.imagecreatetruecolor.php).

`x`

x-coordinate of the point.


`y`

y-coordinate of the point.


### Return Values [¶](https://www.php.net/manual/en/function.imagecolorat.php\#refsect1-function.imagecolorat-returnvalues)

Returns the index of the color or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


**Warning**

This function may
return Boolean **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**, but may also return a non-Boolean value which
evaluates to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**. Please read the section on [Booleans](https://www.php.net/manual/en/language.types.boolean.php) for more
information. Use [the ===\\
operator](https://www.php.net/manual/en/language.operators.comparison.php) for testing the return value of this
function.

### Changelog [¶](https://www.php.net/manual/en/function.imagecolorat.php\#refsect1-function.imagecolorat-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `image` expects a [GdImage](https://www.php.net/manual/en/class.gdimage.php)<br> instance now; previously, a valid `gd` [resource](https://www.php.net/manual/en/language.types.resource.php) was expected. |

### Examples [¶](https://www.php.net/manual/en/function.imagecolorat.php\#refsect1-function.imagecolorat-examples)

**Example #1 Access distinct RGB values**

`<?php
$im = imagecreatefrompng("php.png");
$rgb = imagecolorat($im, 10, 15);
$r = ($rgb >> 16) & 0xFF;
$g = ($rgb >> 8) & 0xFF;
$b = $rgb & 0xFF;
var_dump($r, $g, $b);
?>`

The above example will output
something similar to:

```
int(119)
int(123)
int(180)
```

**Example #2 Human-readable RGB values using [imagecolorsforindex()](https://www.php.net/manual/en/function.imagecolorsforindex.php)**

`<?php
$im = imagecreatefrompng("php.png");
$rgb = imagecolorat($im, 10, 15);
$colors = imagecolorsforindex($im, $rgb);
var_dump($colors);
?>`

The above example will output
something similar to:

```
array(4) {
  ["red"]=>
  int(119)
  ["green"]=>
  int(123)
  ["blue"]=>
  int(180)
  ["alpha"]=>
  int(127)
}
```

### See Also [¶](https://www.php.net/manual/en/function.imagecolorat.php\#refsect1-function.imagecolorat-seealso)

- [imagecolorset()](https://www.php.net/manual/en/function.imagecolorset.php) \- Set the color for the specified palette index
- [imagecolorsforindex()](https://www.php.net/manual/en/function.imagecolorsforindex.php) \- Get the colors for an index
- [imagesetpixel()](https://www.php.net/manual/en/function.imagesetpixel.php) \- Set a single pixel

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/functions/imagecolorat.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imagecolorat%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagecolorat&repo=en&redirect=https://www.php.net/manual/en/function.imagecolorat.php)

### User Contributed Notes 22 notes

[up](https://www.php.net/manual/vote-note.php?id=70783&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70783&page=function.imagecolorat&vote=down "Vote down!")

15


[**_Luciano Ropero_**](https://www.php.net/manual/en/function.imagecolorat.php#70783) [¶](https://www.php.net/manual/en/function.imagecolorat.php#70783)

**18 years ago**

`I made a function that calculates the average color of a given image resource and returns it in "#rrggbb" format (hex):
function average($img) {
    $w = imagesx($img);
    $h = imagesy($img);
    $r = $g = $b = 0;
    for($y = 0; $y < $h; $y++) {
        for($x = 0; $x < $w; $x++) {
            $rgb = imagecolorat($img, $x, $y);
            $r += $rgb >> 16;
            $g += $rgb >> 8 & 255;
            $b += $rgb & 255;
        }
    }
    $pxls = $w * $h;
    $r = dechex(round($r / $pxls));
    $g = dechex(round($g / $pxls));
    $b = dechex(round($b / $pxls));
    if(strlen($r) < 2) {
        $r = 0 . $r;
    }
    if(strlen($g) < 2) {
        $g = 0 . $g;
    }
    if(strlen($b) < 2) {
        $b = 0 . $b;
    }
    return "#" . $r . $g . $b;
}
Although, I've noticed that you can also get a fairly good average color generating a 1px by 1px copy with imagecopyresampled (the pixel generated is colored with the average color).`

[up](https://www.php.net/manual/vote-note.php?id=79116&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=79116&page=function.imagecolorat&vote=down "Vote down!")

8


[**_alan hogan dot com slash contact_**](https://www.php.net/manual/en/function.imagecolorat.php#79116) [¶](https://www.php.net/manual/en/function.imagecolorat.php#79116)

**17 years ago**

`As creamdog noted before, the alpha channel IS available from this function! (The manual should probably be updated to include this!)
$rgba = imagecolorat($im,$x,$y);
$alpha = ($rgba & 0x7F000000) >> 24;
$alpha will then contain the TRANSPARENCY (NOT OPACITY) level. So 127, the max, would be completely transparent, and 0 would be completely opaque.
Using this information, it is possible to write a dithering png-to-gif function like the completely working simple one below:
<?php
$im = imagecreatefrompng($pngRel);
        $transparentColor = imagecolorallocate($im, 0xfe, 0x3, 0xf4 );
        $height = imagesy($im);
        $width = imagesx($im);
        for($x = 0; $x < $width; $x++){
            for($y = 0; $y < $height; $y++) {
                $alpha = (imagecolorat($im,$x,$y) & 0x7F000000) >> 24;
                //DITHER!
                if ($alpha > 3 && (
                        $alpha >=127-3 ||
                        (rand(0,127))>=(127-$alpha)
                    )){
                    imagesetpixel($im,$x,$y,$transparentColor);
                }
            }
        }
        imagecolortransparent($im, $transparentColor);
        imagegif($im, $gifRel);//save
        header("Content-type: image/gif");
        readfile($gifRel); //pass thru to browser
?>`

[up](https://www.php.net/manual/vote-note.php?id=40284&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=40284&page=function.imagecolorat&vote=down "Vote down!")

5


[**_mumig at poczta dot onet dot pl_**](https://www.php.net/manual/en/function.imagecolorat.php#40284) [¶](https://www.php.net/manual/en/function.imagecolorat.php#40284)

**21 years ago**

`imagecolorat() works differently for png's with true color and for paletted png's - for true color it returns value of color, for paletted it returns index number and you have to use  imagecolorsforindex() to get rgb color value.`

[up](https://www.php.net/manual/vote-note.php?id=107970&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107970&page=function.imagecolorat&vote=down "Vote down!")

7


[**_justin at hoogs dot com dot au_**](https://www.php.net/manual/en/function.imagecolorat.php#107970) [¶](https://www.php.net/manual/en/function.imagecolorat.php#107970)

**13 years ago**

`trimImage ( resource $image , int $colour , int $tolerance )
trimImage() will return top-most, right-most, bottom-most and left-most positions of wanted pixels for an image (i.e. find minimum image area so you can then trim given colour from the outer edges of an image).
Parameters
image
An image resource, returned by one of the image creation functions, such as imagecreatetruecolor().
colour
colour to be 'trimmed'.  Allowable range 0 (black) to 255 (white).  if null (or outside 0 - 255) will use top/left corner colour as default.
tolerance
Acceptable range +- from colour.  0 (trim only exact colour) to 255 (trim all colours).
Return Values
Returns an array of outermost pixels which are outside the tolerance range from colour.
array( int $top, int $right, int $bottom, int $left )
Example (and actual function)
<?php
function trimImage($im,$c,$t) {
// if trim colour ($c) isn't a number between 0 - 255
if (!is_numeric($c) || $c < 0 || $c > 255) {
    // grab the colour from the top left corner and use that as default
    $rgb = imagecolorat($im, 2, 2); // 2 pixels in to avoid messy edges
    $r = ($rgb >> 16) & 0xFF;
    $g = ($rgb >> 8) & 0xFF;
    $b = $rgb & 0xFF;
    $c = round(($r+$g+$b)/3); // average of rgb is good enough for a default
}
// if tolerance ($t) isn't a number between 0 - 255 use 10 as default
if (!is_numeric($t) || $t < 0 || $t > 255) $t = 10;
$w = imagesx($im); // image width
$h = imagesy($im); // image height
for($x = 0; $x < $w; $x++) {
    for($y = 0; $y < $h; $y++) {
      $rgb = imagecolorat($im, $x, $y);
      $r = ($rgb >> 16) & 0xFF;
      $g = ($rgb >> 8) & 0xFF;
      $b = $rgb & 0xFF;
      if (
      ($r < $c-$t || $r > $c+$t) && // red not within tolerance of trim colour
      ($g < $c-$t || $g > $c+$t) && // green not within tolerance of trim colour
      ($b < $c-$t || $b > $c+$t) // blue not within tolerance of trim colour
      ) {
        // using x and y as keys condenses all rows and all columns
        // into just one X array and one Y array.
        // however, the keys are treated as literal and therefore are not in
        // numeric order, so we need to sort them in order to get the first
        // and last X and Y occurances of wanted pixels.
        // normal sorting will remove keys so we also use x and y as values,
        // this way they are still available without preserving keys.
        $y_axis[$y] = $y;
        $x_axis[$x] = $x;
        // note: $y_axis[] = $y; and $x_axis[] = $x; works just as well
        // but results in much much larger arrays than is necessary
        // array_unique would reduce size again but this method is quicker
      }
    }
}
// sort them so first and last occurances are at start and end
sort($y_axis);
sort($x_axis);
$top = array_shift($y_axis); // first wanted pixel on Y axis
$right = array_pop($x_axis); // last wanted pixel on X axis
$bottom = array_pop($y_axis); // last wanted pixel on Y axis
$left = array_shift($x_axis); // first wanted pixel on X axis
return array($top,$right,$bottom,$left);
}
$image='test.jpg';
$im = imagecreatefromjpeg($image); // we need resource
$c = (isset($_GET[c])) ? $_GET[c] : null; // set trim colour via GET
$t = (isset($_GET[t])) ? $_GET[t] : null; // set tolerance via GET
list($t,$r,$b,$l) = trimImage($im,$c,$t); // find top, right, bottom and left
$w = $r-$l; // find width
$h = $b-$t; // find height
imagedestroy($im); // free resource
// below is just for visually testing function ---------------------------------
$html_display = <<<HTM
<style type="text/css">
#stage {
position: relative;
float: left; // so it is the same size as the image it contains
}
#canvas {
border: solid 1px #FC3;
width: {$w}px;
height: {$h}px;
position: absolute;
top: {$t}px;
left: {$l}px;
}
img { border: solid 1px #EEE; }
</style>
HTM;
?>
<html>
<head>
<?=$html_display?>
</head>
<body>
<div id="stage">
<div id="canvas"></div>
<img src="test.jpg" />
</div>
</body>
</html>`

[up](https://www.php.net/manual/vote-note.php?id=120592&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120592&page=function.imagecolorat&vote=down "Vote down!")

1


[**_Ray.Paseur sometimes uses Gmail_**](https://www.php.net/manual/en/function.imagecolorat.php#120592) [¶](https://www.php.net/manual/en/function.imagecolorat.php#120592)

**8 years ago**

`imageColorAt() issues a Notice and returns FALSE for pixel coordinates that are out of bounds.`

[up](https://www.php.net/manual/vote-note.php?id=113503&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113503&page=function.imagecolorat&vote=down "Vote down!")

3


[**_justin at hoogs dot com dot au_**](https://www.php.net/manual/en/function.imagecolorat.php#113503) [¶](https://www.php.net/manual/en/function.imagecolorat.php#113503)

**11 years ago**

`This improves upon to my previous function (which only really worked on a few greyscale colours). Colour should now be a hexadecimal colour value. Colour and tolerance are now optional parameters.
trimImage ( resource $image [, str $colour [, int $tolerance]] )
trimImage() will return top-most, right-most, bottom-most and left-most positions of wanted pixels for an image (i.e. find minimum image area so you can then trim given colour from the outer edges of an image).
Parameters
image
An image resource, returned by one of the image creation functions, such as imagecreatetruecolor().
colour
Hexadecimal value of colour to be 'trimmed'.  If omitted the top/left corner colour will be used as default.
tolerance
Acceptable range +- from colour.  Allowable range 0 to 255. If omitted 10 will be used as default.
Return Values
Returns an array of outermost pixels which are beyond the tolerance range from colour.
array( int $top, int $right, int $bottom, int $left )
function trimImage($im,$c=null,$t=10) {
// if hex colour ($c) exists attempt to convert to decimal
if ($c) $rgb = @hexdec($c);
// if hexdec failed to get a value between black (0) and white (16777215)
// grab the colour from the top left corner (2 pixels in to avoid messy edges)
if (!is_numeric($rgb) || $rgb < 0 || $rgb > 16777215) $rgb = imagecolorat($im, 2, 2);
// split $rgb into red, green and blue
$r = ($rgb >> 16) & 0xFF;
$g = ($rgb >> 8) & 0xFF;
$b = $rgb & 0xFF;
// make sure tolerance ($t) is a number between 0 - 255
if (!is_numeric($t) || $t < 0) $t = 0;
elseif ($t > 255) $t = 255;
$w = imagesx($im); $h = imagesy($im); // image width and height
for($x = 0; $x < $w; $x++) {
    for($y = 0; $y < $h; $y++) {
      $rgb = imagecolorat($im, $x, $y);
      $red = ($rgb >> 16) & 0xFF;
      $grn = ($rgb >> 8) & 0xFF;
      $blu = $rgb & 0xFF;
      if (
        $red < $r-$t || $red > $r+$t || // not trim red (nor within tolerance)
        $grn < $g-$t || $grn > $g+$t || // not trim green (nor within tolerance)
        $blu < $b-$t || $blu > $b+$t // not trim blue (nor within tolerance)
      ) {
        $y_axis[$y] = $y; $x_axis[$x] = $x; // wanted pixel coordinates stored
      }
    }
}
if (!$y_axis) $y_axis = $x_axis = array(0); // avoid errors if all pixels are trimmed
// sort so first and last occurances are at start and end
sort($y_axis); sort($x_axis);
$t = array_shift($y_axis); // first wanted pixel on Y axis (top)
$r = array_pop($x_axis); // last wanted pixel on X axis (right)
$b = array_pop($y_axis); // last wanted pixel on Y axis (bottom)
$l = array_shift($x_axis); // first wanted pixel on X axis (left)
return array($t,$r,$b,$l);
}`

[up](https://www.php.net/manual/vote-note.php?id=115609&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115609&page=function.imagecolorat&vote=down "Vote down!")

1


[**_dewi at dewimorgan dot com_**](https://www.php.net/manual/en/function.imagecolorat.php#115609) [¶](https://www.php.net/manual/en/function.imagecolorat.php#115609)

**11 years ago**

`To test whether to handle the return value of this function as RGB or a palette index, see either imageistruecolor(), or (for GD < 2.0.1, or PHP 4 < 4.3.2) imagecolorstotal() == 0.
It seems that a number of comments here take many lines to convert RGB or RGBA values to hex strings #AARRGGBB. This is a one-liner in most cases:
$hex = sprintf("#%08X", imagecolorat($im32, $x, $y));
$hex = sprintf("#%08X", $rgb);
$hex = sprintf("#%08X", $argb);
$hex = sprintf("#%02X%06X", $rgba >> 24, $rgba & 0xFF000000);
$hex = sprintf("#00%02X%02X%02X", $r, $g, $b);
$hex = sprintf("#%02X%02X%02X%02X", $a, $r, $g, $b);
For paletted images, it's two lines:
$cols = imagecolorsforindex($imPal, imagecolorat($imPal, $x, $y));
$hex = sprintf("#%08X", $cols['alpha'], $cols['red'], $cols['green'], $cols['blue']);`

[up](https://www.php.net/manual/vote-note.php?id=103132&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103132&page=function.imagecolorat&vote=down "Vote down!")

1


[**_chandrachur at elegantsystems dot net_**](https://www.php.net/manual/en/function.imagecolorat.php#103132) [¶](https://www.php.net/manual/en/function.imagecolorat.php#103132)

**14 years ago**

`Here is a fun code for making images with white bg transparent. Well it can work with any bg but you need to adjust the color values accordingly. Works best with plain dual colors. I searched for this kind of code a lot but unable to find one ...see if this helps someone.
<?php
function transparentImage($src){  //making images with white bg transparent
$r1=80;
$g1=80;
$b1=80;
for($x = 0; $x < imagesx($src); ++$x)
        {
            for($y = 0; $y < imagesy($src); ++$y)
            {
                $color=imagecolorat($src, $x, $y);
                $r = ($color >> 16) & 0xFF;
                $g = ($color >> 8) & 0xFF;
                $b = $color & 0xFF;
                for($i=0;$i<270;$i++){
                    if($r.$g.$b==($r1+$i).($g1+$i).($b1+$i)){
                        $trans_colour = imagecolorallocatealpha($src, 0, 0, 0, 127);
                        imagefill($src, $x, $y, $trans_colour);
                    }
                }
            }
        }

        return $src;
}
$image='abc/abc.jpg';
$src = imagecreatefromjpeg($image);
$src=transparentImage($src); //Lets make the jpegs transparent
?>`

[up](https://www.php.net/manual/vote-note.php?id=58215&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=58215&page=function.imagecolorat&vote=down "Vote down!")

1


[**_T. Dekker_**](https://www.php.net/manual/en/function.imagecolorat.php#58215) [¶](https://www.php.net/manual/en/function.imagecolorat.php#58215)

**19 years ago**

`In GD 2.x there is support for true color images complete with an alpha channel. GD 2.x has a 7-bit (0-127) alpha channel.
While most people are used to an 8-bit (0-255) alpha channel, it is actually quite handy that GD's is 7-bit (0-127). Each pixel is represented by a 32-bit signed integer, with the four 8-bit bytes arranged like this:
High Byte <--> Low Byte
{Alpha Channel} {Red} {Green} {Blue}
For a signed integer, the leftmost bit, or the highest bit, is used to indicate whether the value is negative, thus leaving only 31 bits of actual information. PHP's default integer value is a signed long into which we can store a single GD palette entry. Whether that integer is positive or negative tells us whether antialiasing is enabled for that palette entry.`

[up](https://www.php.net/manual/vote-note.php?id=56243&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56243&page=function.imagecolorat&vote=down "Vote down!")

1


[**_Super Moi_**](https://www.php.net/manual/en/function.imagecolorat.php#56243) [¶](https://www.php.net/manual/en/function.imagecolorat.php#56243)

**20 years ago**

`Here is a contribution for change tint.
function colorize($path_image, $red, $green, $blue)
{
      $im = imagecreatefrompng($path_image);
    $pixel = array();

    $n_im = imagecreatetruecolor(imagesx($im),imagesy($im));
    $fond = imagecolorallocatealpha($n_im, 255, 255, 255, 0);
    imagefill($n_im, 0, 0, $fond);

    for($y=0;$y<imagesy($n_im);$y++)
    {
        for($x=0;$x<imagesx($n_im);$x++)
        {
            $rgb = imagecolorat($im, $x, $y);
            $pixel = imagecolorsforindex($im, $rgb);

            $r = min(round($red*$pixel['red']/169),255);
            $g = min(round($green*$pixel['green']/169),255);
            $b = min(round($blue*$pixel['blue']/169),255);
            $a = $pixel['alpha'];
            //echo('red : '.$pixel['red'].' => '.$r.', green : '.$pixel['green'].' => '.$g.', blue : '.$pixel['blue'].' => '.$b.', alpha : '.$pixel['alpha'].' => '.$a.'<br>');

            $pixelcolor = imagecolorallocatealpha($n_im, $r, $g, $b, $a);

            imagealphablending($n_im, TRUE);
            imagesetpixel($n_im, $x, $y, $pixelcolor);
        }
    }

       imagepng($n_im,'test.png');
       imagedestroy($n_im);
}`

[up](https://www.php.net/manual/vote-note.php?id=102328&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=102328&page=function.imagecolorat&vote=down "Vote down!")

0


[**_Kae Cyphet_**](https://www.php.net/manual/en/function.imagecolorat.php#102328) [¶](https://www.php.net/manual/en/function.imagecolorat.php#102328)

**14 years ago**

`If you are getting inconsistent results or results that dont make any sense when trying to retrieve a black pixel eg:
(Red,Green,Blue)
0,0,0
0,0,0
0,0,2
0,0,4
0,0,6
0,0,7
0,0,0
0,0,10
0,0,8
0,0,9
0,0,0
0,0,12
0,0,13
0,0,0
switch from using imagecreate() to imagecreatetruecolor()
issue found when creating a graph where a pixel would increase in color based on the previous color and new data.`

[up](https://www.php.net/manual/vote-note.php?id=99282&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99282&page=function.imagecolorat&vote=down "Vote down!")

0


[**_madtrader117 at gmail dot com_**](https://www.php.net/manual/en/function.imagecolorat.php#99282) [¶](https://www.php.net/manual/en/function.imagecolorat.php#99282)

**15 years ago**

`Here's a function I made for finding the size of the black border surrounding some movie thumbnails where the movie itself has had black padding added in order to maintain aspect ratio.
<?php
    define("DEBUG_OUT",TRUE);
    $border_size = find_border_size($path);
    print_r($border_size);
    /*
     * $border = max(find_border_size("img.jpg"));
     * $thumb_size_x = 180+(2*$border);
     * $thumb_size_y = 240+(2*$border);
     * $thumb_size = $thumb_size_x . "x" . $thumb_size_y; (String to use in the -s param of ffmpeg)
     * $crop_cmd = "-croptop $border -cropbottom $border -cropright $border -cropleft $border";
     */
    function find_border_size($path)
    {
        /* The pad var is essentially a 'feather' value. Unless one of the RGB values rises
         * above $pad we are saying to continue. You can try different values but with 10 I
         * would still get a decent sized border due to the bleedover of the movie into
         * the hat.
         */
        $pad = 20;
        $border_y = 0;
        $border_x = 0;
        if(!file_exists($path))
        {
            if(DEBUG_OUT) echo("Error: $path not found.\n");
            return FALSE;
        }
        else
        {
            if(DEBUG_OUT) echo("Opening: $path ...\n");
        }
        $im = @imagecreatefromjpeg($path);
        if(!$im) return FALSE;
        $height = imagesy($im);
        $width = imagesx($im);
        /* Let's start at 0, 0 and keep going till we hit a color */
        if(DEBUG_OUT) echo("Image - Height: $height / Width: $width\n");
        /* Border Height(Y) */
        $center_width = ceil($width/2);
        for($i=0; $i<$height; $i++)
        {
            $rgb = imagecolorat($im,$center_width,$i);
            $r = ($rgb >> 16) & 0xFF;
            $g = ($rgb >> 8) & 0xFF;
            $b = $rgb & 0xFF;
            if(DEBUG_OUT) echo("Height: ($center_width,$i) R: $r / G: $g / B: $b\n");
            if($r >= $pad || $g >= $pad || $b >= $pad)
            {
                $border_y = $i;
                if($border_y == $height) $border_y = 0;
                break;
            }
        }
        /* Border Width(X) */
        $center_height = ceil($height/2);
        for($i=0; $i<$width; $i++)
        {
            $rgb = imagecolorat($im,$i,$center_height);
            $r = ($rgb >> 16) & 0xFF;
            $g = ($rgb >> 8) & 0xFF;
            $b = $rgb & 0xFF;
            if(DEBUG_OUT) echo("Width: ($i,$center_width) R: $r / G: $g / B: $b\n");
            if($r >= $pad || $g >= $pad || $b >= $pad)
            {
                $border_x = $i;
                if($border_x == $width) $border_x = 0;
                break;
            }
        }
        /* I am making the border a multiple of 2 since I am sending these values to FFMpeg */
        if($border_x != 0)
        {
            $border_x /= 2;
            $border_x = round($border_x);
            $border_x *= 2;
        }
        if($border_y != 0)
        {
            $border_y /= 2;
            $border_y = round($border_y);
            $border_y *= 2;
        }
        if(DEBUG_OUT) echo("Border Width: $border_x / Border Height: $border_y\n");
        return array($border_x,$border_y);
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=85849&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85849&page=function.imagecolorat&vote=down "Vote down!")

0


[**_Richard_**](https://www.php.net/manual/en/function.imagecolorat.php#85849) [¶](https://www.php.net/manual/en/function.imagecolorat.php#85849)

**17 years ago**

`With the following functions you can not only convert a 24 bit RGB integer to its corresponding red, green, and blue values, but also 32 bit RGBA integers to its corresponding red, green, blue, and ALPHA values.
Not only that, but I even threw in a function for converting those red, green, blue, and alpha values back into a 32 bit RGBA integer.
Sample usage:
<?php
$int = rgba2int(255, 255, 255, 16);
echo $int . "<br>";
$rgba = int2rgba($int);
print_r($rgba);
?>
What it should output:
285212671
Array
(
    [r] => 255
    [g] => 255
    [b] => 255
    [a] => 16
)
<?php
function rgba2int($r, $g, $b, $a=1) {
    /*
    This function builds a 32 bit integer from 4 values which must be 0-255 (8 bits)
    Example 32 bit integer: 00100000010001000000100000010000
    The first 8 bits define the alpha
    The next 8 bits define the blue
    The next 8 bits define the green
    The next 8 bits define the red
    */
    return ($a << 24) + ($b << 16) + ($g << 8) + $r;
}
function int2rgba($int) {
    $a = ($int >> 24) & 0xFF;
    $r = ($int >> 16) & 0xFF;
    $g = ($int >> 8) & 0xFF;
    $b = $int & 0xFF;
    return array('r'=>$r, 'g'=>$g, 'b'=>$b, 'a'=>$a);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=82556&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82556&page=function.imagecolorat&vote=down "Vote down!")

0


[**_Scott Thompson (VBAssassin)_**](https://www.php.net/manual/en/function.imagecolorat.php#82556) [¶](https://www.php.net/manual/en/function.imagecolorat.php#82556)

**17 years ago**

`I've found this function very useful when wanting to manipulate an existing image. An example would be to simply flip an image (source code here: [http://www.coderprofile.com/source-code/372/](http://www.coderprofile.com/source-code/372/) )
The principle i use a lot is to scan through an image pixel by pixel performing some kind of action on that pixel... and then saving the newly created pixel on to a new canvas ready to display to the browser.
The only problem i find is speed... so some kind of caching mechanism and dimensions limitation on images that are processed is recommended for high traffic use.
Kind regards,
Scott`

[up](https://www.php.net/manual/vote-note.php?id=79316&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=79316&page=function.imagecolorat&vote=down "Vote down!")

0


[**_p h o c i s \[a-t\] g m a i l c o m_**](https://www.php.net/manual/en/function.imagecolorat.php#79316) [¶](https://www.php.net/manual/en/function.imagecolorat.php#79316)

**17 years ago**

`I believe GD has an issue with transparent mattes and alpha blending. It seems GD thinks that some images have a black matte transparency (meaning that the image is built on a black matte instead of transparent).
And while "alan hogan dot com slash contact" solution does deal with this, the results seem to be... glitchy. you get different results each time you do it, and they are not always the best.
So I made a different solution that, while it looks better on a white background and is consistent, still sort of mangles the image just a bit by merging all blended pixels with the transparent color.
// Load image
$img = imagecreatefrompng('my_broken_png.png');
// Make matte canvas
$matte = imagecreatetruecolor(16,16);
$trans_color = imagecolorallocatealpha($matte,254,254,254,0);
imagefill($matte, 0,0,$trans_color);
// Put the old image on the matte
imagecopy($matte,$img,0,0,0,0,16,16);
// Turn the matte color into full alpha (blended pixels will not be affected)
imagecolortransparent($matte,$trans_color);
// Display image
header('Content-Type: image/gif');
imagegif($matte);`

[up](https://www.php.net/manual/vote-note.php?id=77842&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77842&page=function.imagecolorat&vote=down "Vote down!")

0


[**_pocze\_zsolt at hotmail dot com_**](https://www.php.net/manual/en/function.imagecolorat.php#77842) [¶](https://www.php.net/manual/en/function.imagecolorat.php#77842)

**18 years ago**

`This is a histogram-stretching function to get a better contrast:
function contrast_stretch( $img ) {
    $x = imagesx($img);
    $y = imagesy($img);
    $min=255.0;
    $max=0.0;
    for($i=0; $i<$y; $i++) {
    for($j=0; $j<$x; $j++) {
        $pos = imagecolorat($img, $j, $i);
        $f = imagecolorsforindex($img, $pos);
        $gst = $f["red"]*0.15 + $f["green"]*0.5 + $f["blue"]*0.35;
        if($gst>$max) $max=$gst;
        if($gst<$min) $min=$gst;
    }
    }
    $distance = $max-$min;
    for($i=0; $i<$y; $i++) {
    for($j=0; $j<$x; $j++) {
        $pos = imagecolorat($img, $j, $i);
        $f = imagecolorsforindex($img, $pos);
        $red = 255*($f["red"]-$min)/$distance;
        $green = 255*($f["green"]-$min)/$distance;
        $blue = 255*($f["blue"]-$min)/$distance;
        if($red<0) $red = 0.0;
        elseif($red>255) $red=255.0;
        if($green<0) $green = 0.0;
        elseif($green>255) $green=255.0;
        if($blue<0) $blue = 0.0;
        elseif($blue>255) $blue=255.0;
        $color = imagecolorresolve($img, $red, $green, $blue);
        imagesetpixel($img, $j, $i, $color);
    }
    }
}`

[up](https://www.php.net/manual/vote-note.php?id=71444&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=71444&page=function.imagecolorat&vote=down "Vote down!")

0


[**_Anonymous_**](https://www.php.net/manual/en/function.imagecolorat.php#71444) [¶](https://www.php.net/manual/en/function.imagecolorat.php#71444)

**18 years ago**

`//test if a Jpeg is greyscale or color
function iscolor($pic_adress){

// A Pixel is Greyscale if the r = B = G
    //example: colorpixel R=250, G=140 , B=19  Greyscale Pixel R=110, G= 110, B=110

    //we do a check of 10 Pixels to find out if the Picture is Greyscale
    $tocheck = 10;

    $iscolor=false;

    $temp= getimagesize($pic_adress);

    $x= $temp[0];
    $y= $temp[1];

    $im= imagecreatefromjpeg($pic_adress);
    //now check out the Pixels
    for( $i = 0 ; $i< $tocheck && !$iscolor; $i++){


    // Here a Random Pixel is chosen
    $color = imagecolorat($im,rand(0,$x),rand(0,$y));

    //Problem color is an int
    //The Hex view on the number is RRGGBB
    // Here we get the blue part of the Pixel
    $blue = 0x0000ff & $color;

    $green = 0x00ff00 & $color;
//The Green part we have to push 8 bits to the right to get an Compareable result
    $green = $green >> 8;
    $red =0xff0000 & $color;
    //red part needs to be pushed 16 bit
    $red = $red >> 16;
    // if one of the Pixels isnt Greyscale it breaks an you know this is a color picture
    if( $red!= $green || $green!= $blue){
        $iscolor = true;
        break;
        }
    }
    return $iscolor;
}`

[up](https://www.php.net/manual/vote-note.php?id=56427&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56427&page=function.imagecolorat&vote=down "Vote down!")

0


[**_swimgod_**](https://www.php.net/manual/en/function.imagecolorat.php#56427) [¶](https://www.php.net/manual/en/function.imagecolorat.php#56427)

**20 years ago**

`this function i made will compare two($start-$finish) images and change the pixels with diffrent colors in the "finish" image
then displays them both next to each other in one image
another feature is "display" which will echo text
"50% on
50% off"-% count(if the number is lower then 1 it will go into one decamil count
or type "2" will be
"10023 on
3000 off"-pixel count
one last feature is "color"
which you define in an array
$color = array("r" => "244","g" => "122","b" => "100");
to finish up the discrpition im gonna show this "map" of my function
compare($start, $finish[, $color[, $display[, $type]]])
image-url($start) - base image URL
image-url($finish) - compare image URL
array($color) - array with keys "r", "g", "b" r being RED 0-255 g being GREEN 0-255 b being BLUE 0-255
bool($display) - 1 OR TRUE will return text stats from compare
int($type) - 1 OR 0 | 1 being % results | 0 being pixel results
<?
function compare($start, $finish, $color, $display, $type){
$im = ImageCreateFrompng($start);
$im2 = ImageCreateFrompng($finish);
$img['x'] = imagesx($im);
$img['y'] = imagesy($im);
$img2['x'] = imagesx($im2);
$img2['y'] = imagesy($im2);
if(($img['x'] == $img2['x']) && ($img['y'] == $img2['y'])){
//get and set image hieght and width
$i = array("width" =>  $img['x']*2, "height" => $img['y']);
$im3 = imagecreatetruecolor($i['width'], $i['height']);
if($color){
$color = imagecolorallocate($im3, $color['r'], $color['g'], $color['b']);
}else{
$color = imagecolorallocate($im3, 255, 255, 255);
}
for($y = $img['y'];$y > 0; $y--){
for($x = $img['x'];$x > 0; $x--){
if(ImageColorAt($im, $x, $y) == ImageColorAt($im2, $x, $y)){
$on = $on+1;
$rgb = ImageColorAt($im, $x, $y);
Imagesetpixel($im3, $img['x']+$x, $y, $rgb);
}else{
$off = $off+1;
imagesetpixel($im3, $img['x']+$x, $y , $color);
}
}
}
if($display == true){
if(($type == "1") || (!$type)){
$off2 = (round(($off / $on)*10));
if(($off2 == 0) && ($off > 0)){
$off2 = round(($off / $on)*10)*10;
}
$on2 = (100-$off2);
$off2 .="%";
$on2 .="%";
}else{
$off2 = $off;
$on2 = $on;
}
echo $off2 ." off<br>". $on2 ." on";
}else{
imagecopy($im3, $im, 0, 0, 0, 0, $img['x'], $img['y']);
@header("Content-type: image/png");
imagepng($im3);
imagedestroy($im3);
}
imagedestroy($im);
imagedestroy($im2);
return TRUE;
}else{
return False;
}
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=117748&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117748&page=function.imagecolorat&vote=down "Vote down!")

 -1


[**_Levi Cole_**](https://www.php.net/manual/en/function.imagecolorat.php#117748) [¶](https://www.php.net/manual/en/function.imagecolorat.php#117748)

**10 years ago**

`So I have written the most pointless use I could think of for this function (imagecolorat).
Basically it converts every pixel in the given image for an <i> tag. You can set the rendered pixel size with $p
<?php
    $p = 4; // Set pixel width/height
?>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Image to DOM</title>
    <style>
        .canvas {position: relative;}
        .pixel {width: <?= 1*$p; ?>px; height: <?= 1*$p; ?>px; position: absolute; display: block;}
    </style>
</head>
<body>

    <form action="/" method="post" enctype="multipart/form-data">
        <input type="file" name="image">
        <input type="submit">
    </form>

    <?php
        if ($_FILES) {
            $post_img = $_FILES['image'];
            $filename = $post_img['name'];
            $tmp_img = $post_img['tmp_name'];
            if(preg_match('/[.](jpg)$/', $filename)) {
                $img = imagecreatefromjpeg($tmp_img);
            } else if (preg_match('/[.](gif)$/', $filename)) {
                $img = imagecreatefromgif($tmp_img);
            } else if (preg_match('/[.](png)$/', $filename)) {
                $img = imagecreatefrompng($tmp_img);
            }
            list($width, $height) = getimagesize($tmp_img);
            echo '<div class="canvas" style="width: '.$width*$p.'px; height: '.$height*$p.'px;">';
            for ($i = 0; $i < $height; $i++) {
                $y = $i; // Get Y coords
                for ($j = 0; $j < $width; $j++) {
                    $x = $j; // Get X coords
                    $rgb = imagecolorat($img, $x, $y); // Get pixel color
                    $rgba = imagecolorsforindex($img, $rgb);
                    unset($rgba['alpha']); // Remove Alpha channel
                    $bg_color = implode(', ', $rgba);
                    ?>
                        <i class="pixel" style="background: rgb(<?= $bg_color; ?>); top: <?= $i*$p; ?>px; left: <?= $j*$p; ?>px;"></i>
                    <?php
                }
            }
            echo '</div>';
        }
    ?>
</body>
</html>`

[up](https://www.php.net/manual/vote-note.php?id=69575&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=69575&page=function.imagecolorat&vote=down "Vote down!")

 -1


[**_morten at nilsen dot com_**](https://www.php.net/manual/en/function.imagecolorat.php#69575) [¶](https://www.php.net/manual/en/function.imagecolorat.php#69575)

**19 years ago**

`A better way of encoding a color value to #rrggbb:
<?php
printf('#%06x',$c);
?>
or
<?php
$rgb = sprintf('#%06x',$c);
?>`

[up](https://www.php.net/manual/vote-note.php?id=59797&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=59797&page=function.imagecolorat&vote=down "Vote down!")

 -1


[**_robert at future-vision dot nl_**](https://www.php.net/manual/en/function.imagecolorat.php#59797) [¶](https://www.php.net/manual/en/function.imagecolorat.php#59797)

**19 years ago**

`Look mom, no tables :)
I made some changes to the code from 'hazard AT krankteil DOTTILLYDO de' so the function would output a div that displays the image.
As for the size of the outputted file I can say the original png file was lots smaller, but maybe its a nice feature for small buttons or such.
The way you can use it is the same as the code from 'hazard AT krankteil DOTTILLYDO de'.
litle note: each div contains a bogus image. When this is not in IE will screw up the output.
<?
    function hexcolor($c) {
        $r = ($c >> 16) & 0xFF;
        $g = ($c >> 8) & 0xFF;
        $b = $c & 0xFF;
        return '#'.str_pad(dechex($r), 2, '0', STR_PAD_LEFT).str_pad(dechex($g), 2, '0', STR_PAD_LEFT).str_pad(dechex($b), 2, '0', STR_PAD_LEFT);
    }


    function png2div($filename) {
        $img = imagecreatefrompng($filename);
        $width = imagesx($img);
        $height = imagesy($img);
        $div_width = 1;
        $previous_color = 0;

        $output = '<div style="position:relative;width:' . $width . 'px;height:'. $height .'px;">';

        for($y = 0;$y < $height;++$y){

            for($x = 0;$x < $width;++$x){
                $current_color = ImageColorAt($img, $x, $y);

                if($current_color == $previous_color && $x < $width-1){
                    ++$div_width;
                }
                else{
                    $output .= '<div style="position:relative;float:left;width:' . $div_width . 'px;height:1px;background-color:' . hexcolor((($div_width > 1)? $previous_color:$current_color)) . '"><img src="bogus.gif" alt="" width="1" height="1" /></div>';
                    $previous_color = $current_color;
                    $div_width = 1;
                }
            }
            ob_flush();
        }

        $output .= '</div>';

        return $output;

    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=97957&page=function.imagecolorat&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=97957&page=function.imagecolorat&vote=down "Vote down!")

 -1


[**_black at scene-si dot org_**](https://www.php.net/manual/en/function.imagecolorat.php#97957) [¶](https://www.php.net/manual/en/function.imagecolorat.php#97957)

**15 years ago**

`If an image is filled with a solid color (rgb 0,0,0) the average color will be 0,0,0, and the histogram will have the maximum values at r[0], g[0], and b[0]. Since we remove those values with the tolerance (+- 16), we are only left with colors outside of average.
If the removed colors represent more than 90% of the image (we remove 6.25-12.5% of the histogram based on the average color), then we asume the image is blank.
This detects solid filled images of any color, and with images of very little color variance (blank wall, blue sky with no clouds, nearly faded images, very low contrast and low color range images). The function is perfect for checking if a frame from a video is blank or not (in case you are generating thumbnails).
<?php
function isBlank($gd_resource, $tolerance, $percent)
{
        list($w,$h) = array(imagesx($gd_resource), imagesy($gd_resource));
        $count = 0;
        $hr = $hg = $hb = array();
        for ($i=0; $i<$h; $i++) {
                for ($j=0; $j<$w; $j++) {
                        $pos = imagecolorat($gd_resource, $j, $i);
                        $f = imagecolorsforindex($gd_resource, $pos);
                        $hr[$f['red']] = issetor($hr[$f['red']],0) + 1;
                        $hg[$f['green']] = issetor($hg[$f['green']],0) + 1;
                        $hb[$f['blue']] = issetor($hb[$f['blue']],0) + 1;
                        $count ++;
                }
        }
        $rc = array_sum($hr);
        $gc = array_sum($hg);
        $bc = array_sum($hb);
        $r = $rc/$count;
        $g = $gc/$count;
        $b = $bc/$count;
        $ra = range(max(0,$r-$tolerance), min(255,$r+$tolerance));
        $ga = range(max(0,$g-$tolerance), min(255,$g+$tolerance));
        $ba = range(max(0,$b-$tolerance), min(255,$b+$tolerance));
        foreach ($ra as $rx) {
                unset($hr[$rx]);
        }
        foreach ($ga as $gx) {
                unset($hg[$gx]);
        }
        foreach ($ba as $bx) {
                unset($hb[$bx]);
        }
        $red = floatval(array_sum($hr)+1) / floatval($rc);
        $green = floatval(array_sum($hg)+1) / floatval($gc);
        $blue = floatval(array_sum($hb)+1) / floatval($bc);
        if ($red<$percent && $green<$percent && $blue<$percent) {
                return true;
        }
        return false;
}
// Example;
isBlank($gd_resource, 16, 0.1);
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagecolorat&repo=en&redirect=https://www.php.net/manual/en/function.imagecolorat.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google