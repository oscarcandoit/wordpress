---
url: https://www.php.net/manual/en/function.imagecolorset.php
scraped_at: 2025-10-20T02:56:38.389Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imagecolorset

(PHP 4, PHP 5, PHP 7, PHP 8)

imagecolorset — Set the color for the specified palette index

### Description [¶](https://www.php.net/manual/en/function.imagecolorset.php\#refsect1-function.imagecolorset-description)

**imagecolorset**(

[GdImage](https://www.php.net/manual/en/class.gdimage.php) `$image`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$color`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$red`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$green`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$blue`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$alpha` = 0

): [?](https://www.php.net/manual/en/language.types.null.php)[false](https://www.php.net/manual/en/language.types.singleton.php)

This sets the specified index in the palette to the specified
color. This is useful for creating flood-fill-like effects in
palleted images without the overhead of performing the actual
flood-fill.


### Parameters [¶](https://www.php.net/manual/en/function.imagecolorset.php\#refsect1-function.imagecolorset-parameters)

`image`

A [GdImage](https://www.php.net/manual/en/class.gdimage.php) object, returned by one of the image creation functions,
such as [imagecreatetruecolor()](https://www.php.net/manual/en/function.imagecreatetruecolor.php).

`color`

An index in the palette.


`red`

Value of red component.

`green`

Value of green component.

`blue`

Value of blue component.

`alpha`

Value of alpha component.


### Return Values [¶](https://www.php.net/manual/en/function.imagecolorset.php\#refsect1-function.imagecolorset-returnvalues)

The function returns **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** on success, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Changelog [¶](https://www.php.net/manual/en/function.imagecolorset.php\#refsect1-function.imagecolorset-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `image` expects a [GdImage](https://www.php.net/manual/en/class.gdimage.php)<br> instance now; previously, a valid `gd` [resource](https://www.php.net/manual/en/language.types.resource.php) was expected. |

### Examples [¶](https://www.php.net/manual/en/function.imagecolorset.php\#refsect1-function.imagecolorset-examples)

**Example #1 **imagecolorset()** example**

`<?php
// Create a 300x100 image
$im = imagecreate(300, 100);
// Set the background to be red
imagecolorallocate($im, 255, 0, 0);
// Get the color index for the background
$bg = imagecolorat($im, 0, 0);
// Set the background to be blue
imagecolorset($im, $bg, 0, 0, 255);
// Output the image to the browser
header('Content-Type: image/png');
imagepng($im);
?>`

### See Also [¶](https://www.php.net/manual/en/function.imagecolorset.php\#refsect1-function.imagecolorset-seealso)

- [imagecolorat()](https://www.php.net/manual/en/function.imagecolorat.php) \- Get the index of the color of a pixel

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/functions/imagecolorset.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imagecolorset%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagecolorset&repo=en&redirect=https://www.php.net/manual/en/function.imagecolorset.php)

### User Contributed Notes 10 notes

[up](https://www.php.net/manual/vote-note.php?id=70156&page=function.imagecolorset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70156&page=function.imagecolorset&vote=down "Vote down!")

4


[**_moxleystratton.com_**](https://www.php.net/manual/en/function.imagecolorset.php#70156) [¶](https://www.php.net/manual/en/function.imagecolorset.php#70156)

**19 years ago**

`If you want to convert a Color image to Grayscale without creating a blotchy image, use this color calculation:
<?php
function imagetograyscale($im)
{
    if (imageistruecolor($im)) {
        imagetruecolortopalette($im, false, 256);
    }
    for ($c = 0; $c < imagecolorstotal($im); $c++) {
        $col = imagecolorsforindex($im, $c);
        $gray = round(0.299 * $col['red'] + 0.587 * $col['green'] + 0.114 * $col['blue']);
        imagecolorset($im, $c, $gray, $gray, $gray);
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=81252&page=function.imagecolorset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81252&page=function.imagecolorset&vote=down "Vote down!")

3


[**_heavyraptor2 at hotmail dot com_**](https://www.php.net/manual/en/function.imagecolorset.php#81252) [¶](https://www.php.net/manual/en/function.imagecolorset.php#81252)

**17 years ago**

`I've been looking for a simple function which "colorizes" an image, without any success ... it looks like a lot of people mean something different with "colorizing" an image, because actually colorzing means multiplying the old color's grayscale with the new color. So a white pixel would become 100% of the colorize-to-color and a black pixel would stay black (I know I can't explain well ... I hope you understood, otherwise take a look at the example below the functions' code).
<?php
function image_colorize(&$img,$rgb) {
imageTrueColorToPalette($img,true,256);
$numColors = imageColorsTotal($img);
for ($x = 0; $x < $numColors; $x++) {
    list($r,$g,$b) = array_values(imageColorsForIndex($img,$x));
    // calculate grayscale in percent
    $grayscale = ($r + $g + $b) / 3 / 0xff;
    imageColorSet($img,$x,
      $grayscale * $rgb[0],
      $grayscale * $rgb[1],
      $grayscale * $rgb[2]
    );
}
return true;
}
?>
Example of usage:
<?php
$color = array(0xff,0xaa,0x2a); // color to convert to
$url = ' [http://sundog.net/images/uploads/1\_google\_logo.jpg](http://sundog.net/images/uploads/1_google_logo.jpg)';
$img = imageCreateFromJpeg($url);
image_colorize($img,$color);
header('Content-type: image/gif');
imageGif($img);
exit;
?>
Enjoy`

[up](https://www.php.net/manual/vote-note.php?id=46219&page=function.imagecolorset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=46219&page=function.imagecolorset&vote=down "Vote down!")

2


[**_dade dot c at email dot it_**](https://www.php.net/manual/en/function.imagecolorset.php#46219) [¶](https://www.php.net/manual/en/function.imagecolorset.php#46219)

**21 years ago**

`this is helpful if you would like to implement a color theme system in your website... try it out
Davide Candiloro Italy
function colorize ($pngpath, $r, $g, $b)
/*
REQUIRES: $pngpath to be a valid path of a greyscale PNG-8 image with 64 colors palette
          $r, $g, $b to be integers in the range 0..255
EFFECTS: returns the png image colorized with the color represented by $r, $g, $b.
*/
{
    header("Content-type: image/png");
    $im = imagecreatefrompng("images/table.png");
    imagetruecolortopalette($im, FALSE, 256);

      for ($c = 0; $c < 64; $c++){ /*64 is the number of colors in the PNG-8 palette*/
        $col = imagecolorsforindex($im, $c);
        imagecolorset ( $im, $c, $r*$col['red']/256, $g*$col['green']/256, $b*$col['blue']/256); /*replaces original greyscale palette with a colorized one*/
     }
    imagepng($im);
    imagedestroy($im);
}`

[up](https://www.php.net/manual/vote-note.php?id=41841&page=function.imagecolorset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=41841&page=function.imagecolorset&vote=down "Vote down!")

2


[**_m4551 at abasoft dot it_**](https://www.php.net/manual/en/function.imagecolorset.php#41841) [¶](https://www.php.net/manual/en/function.imagecolorset.php#41841)

**21 years ago**

`here's a function to greyscale an image even from a truecolor source (jpeg or png).
slightly poor quality, but very fast...
function imagegreyscale(&$img, $dither=1) {
    if (!($t = imagecolorstotal($img))) {
        $t = 256;
        imagetruecolortopalette($img, $dither, $t);
    }
    for ($c = 0; $c < $t; $c++) {
        $col = imagecolorsforindex($img, $c);
        $min = min($col['red'],$col['green'],$col['blue']);
        $max = max($col['red'],$col['green'],$col['blue']);
        $i = ($max+$min)/2;
        imagecolorset($img, $c, $i, $i, $i);
    }
}`

[up](https://www.php.net/manual/vote-note.php?id=82729&page=function.imagecolorset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82729&page=function.imagecolorset&vote=down "Vote down!")

1


[**_Thomas Mueller_**](https://www.php.net/manual/en/function.imagecolorset.php#82729) [¶](https://www.php.net/manual/en/function.imagecolorset.php#82729)

**17 years ago**

`Here is a function to colorize a picture gradient style.
All you have to do is to pass an img-object and an array of colors.
e.g.
$arr = array('#000000', '#990000', '#00FFFF', '#FFFFDD');
colorize ($img, $arr);
<?php
function colorize($imgdata, $palette)
{
    imageTrueColorToPalette($imgdata,false,0xFF);
    $l = count($palette)-1;
    $i = imagecolorstotal($imgdata);
    while ($i--)
    {
        list($r,$g,$b) = array_values(imageColorsForIndex($imgdata,$i));

        $grayscale = ($r*.3 + $g*.59 +$b*.11) / 0xFF;

        $pos = $l*$grayscale;

        $perc = $pos-floor($pos);

        $tbase = str_replace("#", '', $palette[$pos]);
        $baseR = hexdec(substr($tbase,0,2));
        $baseG = hexdec(substr($tbase,2,2));
        $baseB = hexdec(substr($tbase,4,2));

        $tmix = str_replace("#", '', $palette[$pos+1]);
        $mixR = hexdec(substr($tmix,0,2));
        $mixG = hexdec(substr($tmix,2,2));
        $mixB = hexdec(substr($tmix,4,2));

        $resR = $baseR+($mixR-$baseR)*$perc;
        $resG = $baseG+($mixG-$baseG)*$perc;
        $resB = $baseB+($mixB-$baseB)*$perc;

        imagecolorset($imgdata, $i, $resR, $resG, $resB);
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=117574&page=function.imagecolorset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117574&page=function.imagecolorset&vote=down "Vote down!")

1


[**_Daniel Klein_**](https://www.php.net/manual/en/function.imagecolorset.php#117574) [¶](https://www.php.net/manual/en/function.imagecolorset.php#117574)

**10 years ago**

`If you are creating a palette image from scratch you have to use imagecolorallocate() for each index before you can use imagecolorset() on it.`

[up](https://www.php.net/manual/vote-note.php?id=93134&page=function.imagecolorset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93134&page=function.imagecolorset&vote=down "Vote down!")

0


[**_Bartman_**](https://www.php.net/manual/en/function.imagecolorset.php#93134) [¶](https://www.php.net/manual/en/function.imagecolorset.php#93134)

**16 years ago**

`I had the same problem as heavyraptor2 so i made this function...
<?php
function imagecolorize($im,$endcolor){
    //funcion takes image and turns black into $endcolor, white to white and
    //everything in between in corresponding gradient
    //$endcolor should be 6 char html color
    //make sure it has usable palette
    if (imageistruecolor($im)) {
        imagetruecolortopalette($im, false, 256);
    }
    //first make it gray to be sure of even results (thanks moxleystratton.com)
    //comment this loop if you want the output based on, for example,
    //the red channel (for this take a look at the $gray-var in the last loop)
    for ($c = 0; $c < imagecolorstotal($im); $c++) {
        $col = imagecolorsforindex($im, $c);
        $gray = round(0.299 * $col['red'] + 0.587 * $col['green'] + 0.114 * $col['blue']);
        imagecolorset($im, $c, $gray, $gray, $gray);
    }
    //determine end-colors in hexdec
    $EndcolorRGB['r'] = hexdec( substr($endcolor, 0, 2));
    $EndcolorRGB['g'] = hexdec( substr($endcolor, 2, 2));
    $EndcolorRGB['b'] = hexdec( substr($endcolor, 4, 2));
    //determine gradient-delta's
    $stepR = (255-$EndcolorRGB['r'])/255.0;
    $stepG = (255-$EndcolorRGB['g'])/255.0;
    $stepB = (255-$EndcolorRGB['b'])/255.0;
    //aColor contains the 256 gradations between endcolor(i=0) and white(i=255)
    $aColor = array();
    for ($i = 0; $i<=255; $i++){
        $aColor[$i]['r'] = $EndcolorRGB['r'] + ($i*$stepR);
        $aColor[$i]['g'] = $EndcolorRGB['g'] + ($i*$stepG);
        $aColor[$i]['b'] = $EndcolorRGB['b'] + ($i*$stepB);
    }
    //for every color-index we now replace $gray-values for $aColor
    for ($c = 0; $c < imagecolorstotal($im); $c++){
        $currentColorRGB = imagecolorsforindex($im, $c);
        $gray = $currentColorRGB['red'];//image is grayscale, so red,green and blue
        // should be equal. We use this number as key of aColor
        imagecolorset($im,$c,(int)$aColor[$gray]['r'], (int)$aColor[$gray]['g'], (int)$aColor[$gray]['b']);
    }
}?>`

[up](https://www.php.net/manual/vote-note.php?id=13963&page=function.imagecolorset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=13963&page=function.imagecolorset&vote=down "Vote down!")

 -1


[**_olivier at moostik dot net_**](https://www.php.net/manual/en/function.imagecolorset.php#13963) [¶](https://www.php.net/manual/en/function.imagecolorset.php#13963)

**24 years ago**

`This function change colors of an image with ranges 0>100 for each primary color:
int ImageSelectiveColor (int im, int red, int green, int blue)
im is image pointer
red, green and blue are ranges 0->100
function ImageSelectiveColor($im,$red,$green,$blue)
{
for($i=0;$i<imagecolorstotal($im);$i++)
{
    $col=ImageColorsForIndex($im,$i);
    $red_set=$red/100*$col['red'];
    $green_set=$green/100*$col['green'];
    $blue_set=$blue/100*$col['blue'];
    if($red_set>255)$red_set=255;
    if($green_set>255)$green_set=255;
    if($blue_set>255)$blue_set=255;
    imagecolorset($im,$i,$red_set,$green_set,$blue_set);

}
return $im;

}`

[up](https://www.php.net/manual/vote-note.php?id=77351&page=function.imagecolorset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77351&page=function.imagecolorset&vote=down "Vote down!")

 -2


[**_admin at phpgfx dot com_**](https://www.php.net/manual/en/function.imagecolorset.php#77351) [¶](https://www.php.net/manual/en/function.imagecolorset.php#77351)

**18 years ago**

`Here is a function to turn an image into pure black and white
<?php
function imagepurebw( $img, $amount = 383 ) {
    $total = imagecolorstotal( $img );
    for ( $i = 0; $i < $total; $i++ ) {
        $index = imagecolorsforindex( $img, $i );
        array_pop( $index );
        $color = ( array_sum( $index ) > $amount ) ? 255 : 0;
        imagecolorset( $img, $i, $color, $color, $color );
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=24186&page=function.imagecolorset&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=24186&page=function.imagecolorset&vote=down "Vote down!")

 -2


[**_info at devking dot com_**](https://www.php.net/manual/en/function.imagecolorset.php#24186) [¶](https://www.php.net/manual/en/function.imagecolorset.php#24186)

**23 years ago**

`here's a simple function to greyscale an image...
function imagecolorgrey( &$img ) {
for( $i=0; $i<imagecolorstotal( $img ); $i++ ) {
$c = ImageColorsForIndex( $img, $i );
$t = ($c["red"]+$c["green"]+$c["blue"])/3;
imagecolorset( $img, $i, $t, $t, $t );
}
}`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagecolorset&repo=en&redirect=https://www.php.net/manual/en/function.imagecolorset.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google