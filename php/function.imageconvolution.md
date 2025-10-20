---
url: https://www.php.net/manual/en/function.imageconvolution.php
scraped_at: 2025-10-20T02:47:51.288Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imageconvolution

(PHP 5 >= 5.1.0, PHP 7, PHP 8)

imageconvolution — Apply a 3x3 convolution matrix, using coefficient and offset

### Description [¶](https://www.php.net/manual/en/function.imageconvolution.php\#refsect1-function.imageconvolution-description)

**imageconvolution**(

[GdImage](https://www.php.net/manual/en/class.gdimage.php) `$image`,

[array](https://www.php.net/manual/en/language.types.array.php) `$matrix`,

[float](https://www.php.net/manual/en/language.types.float.php) `$divisor`,

[float](https://www.php.net/manual/en/language.types.float.php) `$offset`

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Applies a convolution matrix on the image, using the given coefficient and
offset.


### Parameters [¶](https://www.php.net/manual/en/function.imageconvolution.php\#refsect1-function.imageconvolution-parameters)

`image`

A [GdImage](https://www.php.net/manual/en/class.gdimage.php) object, returned by one of the image creation functions,
such as [imagecreatetruecolor()](https://www.php.net/manual/en/function.imagecreatetruecolor.php).

`matrix`

A 3x3 matrix: an array of three arrays of three floats.


`divisor`

The divisor of the result of the convolution, used for normalization.


`offset`

Color offset.


### Return Values [¶](https://www.php.net/manual/en/function.imageconvolution.php\#refsect1-function.imageconvolution-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Changelog [¶](https://www.php.net/manual/en/function.imageconvolution.php\#refsect1-function.imageconvolution-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `image` expects a [GdImage](https://www.php.net/manual/en/class.gdimage.php)<br> instance now; previously, a valid `gd` [resource](https://www.php.net/manual/en/language.types.resource.php) was expected. |

### Examples [¶](https://www.php.net/manual/en/function.imageconvolution.php\#refsect1-function.imageconvolution-examples)

**Example #1 Embossing the PHP.net logo**

`<?php
$image = imagecreatefromgif('http://www.php.net/images/php.gif');
$emboss = array(array(2, 0, 0), array(0, -1, 0), array(0, 0, -1));
imageconvolution($image, $emboss, 1, 127);
header('Content-Type: image/png');
imagepng($image, null, 9);
?>`

The above example will output:

![Output of example : Embossing the PHP.net logo](https://www.php.net/manual/en/images/21009b70229598c6a80eef8b45bf282b-imageconvolution_emboss.png)

**Example #2 Gaussian blur**

`<?php
$image = imagecreatetruecolor(180,40);
// Writes the text and apply a gaussian blur on the image
imagestring($image, 5, 10, 8, 'Gaussian Blur Text', 0x00ff00);
$gaussian = array(array(1.0, 2.0, 1.0), array(2.0, 4.0, 2.0), array(1.0, 2.0, 1.0));
imageconvolution($image, $gaussian, 16, 0);
// Rewrites the text for comparison
imagestring($image, 5, 10, 18, 'Gaussian Blur Text', 0x00ff00);
header('Content-Type: image/png');
imagepng($image, null, 9);
?>`

The above example will output:

![Output of example : Gaussian blur](https://www.php.net/manual/en/images/21009b70229598c6a80eef8b45bf282b-imageconvolution_gaussian.png)

### See Also [¶](https://www.php.net/manual/en/function.imageconvolution.php\#refsect1-function.imageconvolution-seealso)

- [imagefilter()](https://www.php.net/manual/en/function.imagefilter.php) \- Applies a filter to an image

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/functions/imageconvolution.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imageconvolution%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imageconvolution&repo=en&redirect=https://www.php.net/manual/en/function.imageconvolution.php)

### User Contributed Notes 10 notes

[up](https://www.php.net/manual/vote-note.php?id=104006&page=function.imageconvolution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104006&page=function.imageconvolution&vote=down "Vote down!")

12


[**_magilvia_**](https://www.php.net/manual/en/function.imageconvolution.php#104006) [¶](https://www.php.net/manual/en/function.imageconvolution.php#104006)

**14 years ago**

`Here's a good sharpen setting for thumbnail creation:
<?php
            $sharpenMatrix = array
            (
                array(-1.2, -1, -1.2),
                array(-1, 20, -1),
                array(-1.2, -1, -1.2)
            );
            // calculate the sharpen divisor
            $divisor = array_sum(array_map('array_sum', $sharpenMatrix));
            $offset = 0;

            // apply the matrix
            imageconvolution($img, $sharpenMatrix, $divisor, $offset);
?>`

[up](https://www.php.net/manual/vote-note.php?id=96601&page=function.imageconvolution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96601&page=function.imageconvolution&vote=down "Vote down!")

3


[**_fabien dot snauwaert at gmail dot com_**](https://www.php.net/manual/en/function.imageconvolution.php#96601) [¶](https://www.php.net/manual/en/function.imageconvolution.php#96601)

**15 years ago**

`Normalization is necessary to keep the image balanced (else any filter may quickly turn the image almost completely black or white).
Here is a short, easy-to-use, class to handle normalization automatically and make for easier input of the 3x3 matrix:
The code respects the "array of three arrays" syntax for use with the imageconvolution() function and automatically calculates the necesarry divisor for normalization.
<?php
class ConvolutionFilter {
    public $matrix;
    public $div;

    public function computeDiv() {
        $this->div = array_sum ($this->matrix[0]) + array_sum ($this->matrix[1]) + array_sum ($this->matrix[2]);
    }
    function __construct() {
        $matrix = func_get_args();
        $this->matrix = array(    array($matrix[0], $matrix[1], $matrix[2]),
                                array($matrix[3], $matrix[4], $matrix[5]),
                                array($matrix[6], $matrix[7], $matrix[8])
                                );
        $this->computeDiv();
    }
}
?>
Example usage:
<?php
$gaussianFilter =    new ConvolutionFilter(    1.0,    2.0,    1.0,
                                             2.0,    3.0,    2.0,
                                             1.0,    2.0,    1.0        );
imageconvolution($image, $gaussianFilter->matrix, $gaussianFilter->div, 0);
?>
Some common filters:
<?php
$identityFilter =    new ConvolutionFilter(    0.0,    0.0,    0.0,
                                             0.0,    1.0,    0.0,
                                             0.0,    0.0,    0.0        );
$sharpenFilter =    new ConvolutionFilter(    0.0,    -1.0,    0.0,
                                             -1.0,    5.0,    -1.0,
                                             0.0,    -1.0,    0.0        );
$edgeFilter =        new ConvolutionFilter(    0.0,    1.0,    0.0,
                                             1.0,    -4.0,    1.0,
                                             0.0,    1.0,    0.0        );
$findEdgesFilter =    new ConvolutionFilter(    -1.0,    -1.0,    -1.0,
                                             -2.0,    8.0,    -1.0,
                                             -1.0,    -1.0,    -1.0        );
?>
Remember you can use imagefilter() for such basic needs but the above class will make it easier for you when you want to create your own filters.`

[up](https://www.php.net/manual/vote-note.php?id=58187&page=function.imageconvolution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=58187&page=function.imageconvolution&vote=down "Vote down!")

1


[**_Anonymous_**](https://www.php.net/manual/en/function.imageconvolution.php#58187) [¶](https://www.php.net/manual/en/function.imageconvolution.php#58187)

**19 years ago**

`The example below didn't provide a 3x3 matrix. Correctly, it's a multidimensional array.
<?php
    $matrix = array(    array( -1, -1, -1 ),
                        array( -1, 16, -1 ),
                        array( -1, -1, -1 ) );
?>`

[up](https://www.php.net/manual/vote-note.php?id=63377&page=function.imageconvolution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=63377&page=function.imageconvolution&vote=down "Vote down!")

1


[**_mlconnor at yahoo dot com_**](https://www.php.net/manual/en/function.imageconvolution.php#63377) [¶](https://www.php.net/manual/en/function.imageconvolution.php#63377)

**19 years ago**

`I've seen many people come up with ways to do a drop shadow behind a rectangle such as a picture.  I haven't found one yet that was fast, PHP 4 complaint, and nice looking.  Here is one I came up with last night.  It takes an image, fills it with the background, and creates a blurred drop shadow at the specified coords using the colors and the distance offset specified.  It looks great!!!
function blurRect(&$image, $distance, $rectX1, $rectY1, $rectX2, $rectY2, $shadowR, $shadowG, $shadowB, $backR, $backG, $backB) {
    $potentialOverlap = ($distance * 2) * ($distance * 2);
    $backgroundColor = imagecolorallocate($image, $backR, $backG, $backB);
    $shadowColor = imagecolorallocate($image, $shadowR, $shadowG, $shadowB);
    $imageWidth = imagesx($image);
    $imageHeight = imagesy($image);
    imageFilledRectangle($image, 0, 0, $imageWidth - 1, $imageHeight - 1, $backgroundColor);
    imageFilledRectangle($image, $rectX1, $rectY1, $rectX2, $rectY2, $shadowColor);
    for ( $pointX = $rectX1 - $distance; $pointX < $imageWidth; $pointX++ ) {
      for ( $pointY = $rectY1 - $distance; $pointY < $imageHeight; $pointY++ ) {
        if ( $pointX > $rectX1 + $distance &&
             $pointX < $rectX2 - $distance &&
             $pointY > $rectY1 + $distance &&
             $pointY < $rectY2 - $distance ) {
          $pointY = $rectY2 - $distance;
        }
        $boxX1 = $pointX - $distance;
        $boxY1 = $pointY - $distance;
        $boxX2 = $pointX + $distance;
        $boxY2 = $pointY + $distance;
        $xOverlap = max(0, min($boxX2, $rectX2) - max($boxX1, $rectX1));
        $yOverlap = max(0, min($boxY2, $rectY2) - max($boxY1, $rectY1));
        $totalOverlap = $xOverlap * $yOverlap;
        $shadowPcnt = $totalOverlap / $potentialOverlap;
        $backPcnt = 1.0 - $shadowPcnt;
        $newR = $shadowR * $shadowPcnt + $backR * $backPcnt;
        $newG = $shadowG * $shadowPcnt + $backG * $backPcnt;
        $newB = $shadowB * $shadowPcnt + $backB * $backPcnt;
        $newcol = imagecolorallocate($image, $newR, $newG, $newB);
        imagesetpixel($image, $pointX, $pointY, $newcol);
      }
    }
}`

[up](https://www.php.net/manual/vote-note.php?id=56145&page=function.imageconvolution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56145&page=function.imageconvolution&vote=down "Vote down!")

1


[**_timeshifting at gmail dot com_**](https://www.php.net/manual/en/function.imageconvolution.php#56145) [¶](https://www.php.net/manual/en/function.imageconvolution.php#56145)

**20 years ago**

`Matrices can be used for sharpening, blurring, edge detection, etc, ala Photoshop.
A sharpening example:
<?php
$sharpenMatrix = array(-1,-1,-1,-1,16,-1,-1,-1,-1);
$divisor = 8;
$offset = 0;
imageconvolution($myImage, $sharpenMatrix, $divisor, $offset);
?>
Below is some information on building different kinds of matrices. (If you have photoshop (or PSP, GIMP) you can test out your matrices before applying them in PHP)
[http://loriweb.pair.com/8udf-basics.html](http://loriweb.pair.com/8udf-basics.html) (covers blurs)
[http://loriweb.pair.com/8udf-sharpen.html](http://loriweb.pair.com/8udf-sharpen.html)
[http://loriweb.pair.com/8udf-edges.html](http://loriweb.pair.com/8udf-edges.html)
[http://loriweb.pair.com/8udf-emboss.html](http://loriweb.pair.com/8udf-emboss.html)`

[up](https://www.php.net/manual/vote-note.php?id=73551&page=function.imageconvolution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73551&page=function.imageconvolution&vote=down "Vote down!")

0


[**_mgcclx at gmail dot com_**](https://www.php.net/manual/en/function.imageconvolution.php#73551) [¶](https://www.php.net/manual/en/function.imageconvolution.php#73551)

**18 years ago**

`imageconvolution() does not appear in PHP with non-bundled GD libraries. It is a rare situation, but it still happens. That's why I wrote a replication of imageconvolution() in PHP. Compare to the post below, this one makes the use of offset and 30% faster.
Because it's written in PHP, it is 50 times slower than the bundled version.
Actually, this is a replication of gdimageconvolutaion() of GD library, it does not support data validating feature imageconvolution() have. But I guess people who uses this function knows their stuff.
THE SCRIPT:
<?php
//include this file whenever you have to use imageconvolution...
//you can use in your project, but keep the comment below :)
//great for any image manipulation library
//Made by Chao Xu(Mgccl) 2/28/07
//www.webdevlogs.com
//V 1.0
if(!function_exists('imageconvolution')){
function imageconvolution($src, $filter, $filter_div, $offset){
    if ($src==NULL) {
        return 0;
    }

    $sx = imagesx($src);
    $sy = imagesy($src);
    $srcback = ImageCreateTrueColor ($sx, $sy);
    ImageCopy($srcback, $src,0,0,0,0,$sx,$sy);

    if($srcback==NULL){
        return 0;
    }

    for ($y=0; $y<$sy; ++$y){
        for($x=0; $x<$sx; ++$x){
            $new_r = $new_g = $new_b = 0;
            $alpha = imagecolorat($srcback, $pxl[0], $pxl[1]);
            $new_a = $alpha >> 24;

            for ($j=0; $j<3; ++$j) {
                $yv = min(max($y - 1 + $j, 0), $sy - 1);
                for ($i=0; $i<3; ++$i) {
                        $pxl = array(min(max($x - 1 + $i, 0), $sx - 1), $yv);
                    $rgb = imagecolorat($srcback, $pxl[0], $pxl[1]);
                    $new_r += (($rgb >> 16) & 0xFF) * $filter[$j][$i];
                    $new_g += (($rgb >> 8) & 0xFF) * $filter[$j][$i];
                    $new_b += ($rgb & 0xFF) * $filter[$j][$i];
                }
            }
            $new_r = ($new_r/$filter_div)+$offset;
            $new_g = ($new_g/$filter_div)+$offset;
            $new_b = ($new_b/$filter_div)+$offset;
            $new_r = ($new_r > 255)? 255 : (($new_r < 0)? 0:$new_r);
            $new_g = ($new_g > 255)? 255 : (($new_g < 0)? 0:$new_g);
            $new_b = ($new_b > 255)? 255 : (($new_b < 0)? 0:$new_b);
            $new_pxl = ImageColorAllocateAlpha($src, (int)$new_r, (int)$new_g, (int)$new_b, $new_a);
            if ($new_pxl == -1) {
                $new_pxl = ImageColorClosestAlpha($src, (int)$new_r, (int)$new_g, (int)$new_b, $new_a);
            }
            if (($y >= 0) && ($y < $sy)) {
                imagesetpixel($src, $x, $y, $new_pxl);
            }
        }
    }
    imagedestroy($srcback);
    return 1;
}
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=97921&page=function.imageconvolution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=97921&page=function.imageconvolution&vote=down "Vote down!")

 -1


[**_phunction.sf.net_**](https://www.php.net/manual/en/function.imageconvolution.php#97921) [¶](https://www.php.net/manual/en/function.imageconvolution.php#97921)

**15 years ago**

`You don't need any custom function to calculate the $divisor of the $matrix, using array_map() and array_sum() does the trick:
<?php
$matrix = array
(
    array(-1, -1, -1),
    array(-1, 16, -1),
    array(-1, -1, -1),
);
$divisor = array_sum(array_map('array_sum', $matrix)); // 8
?>`

[up](https://www.php.net/manual/vote-note.php?id=77818&page=function.imageconvolution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77818&page=function.imageconvolution&vote=down "Vote down!")

 -1


[**_Jase_**](https://www.php.net/manual/en/function.imageconvolution.php#77818) [¶](https://www.php.net/manual/en/function.imageconvolution.php#77818)

**18 years ago**

`The comment below is an extremely good workaround
however, php did throw lots of warnings at me when i had error reporting set to E_ALL
this can be avoided with one line of code and no impact (as i can see) to the rest of the function
<?php
//include this file whenever you have to use imageconvolution...
//you can use in your project, but keep the comment below :)
//great for any image manipulation library
//Made by Chao Xu(Mgccl) 2/28/07
//www.webdevlogs.com
//V 1.0
if(!function_exists('imageconvolution')){
function imageconvolution($src, $filter, $filter_div, $offset){
    if ($src==NULL) {
        return 0;
    }

    $sx = imagesx($src);
    $sy = imagesy($src);
    $srcback = ImageCreateTrueColor ($sx, $sy);
    ImageCopy($srcback, $src,0,0,0,0,$sx,$sy);

    if($srcback==NULL){
        return 0;
    }

    #FIX HERE
    #$pxl array was the problem so simply set it with very low values
    $pxl = array(1,1);
    #this little fix worked for me as the undefined array threw out errors
    for ($y=0; $y<$sy; ++$y){
        for($x=0; $x<$sx; ++$x){
            $new_r = $new_g = $new_b = 0;
            $alpha = imagecolorat($srcback, $pxl[0], $pxl[1]);
            $new_a = $alpha >> 24;

            for ($j=0; $j<3; ++$j) {
                $yv = min(max($y - 1 + $j, 0), $sy - 1);
                for ($i=0; $i<3; ++$i) {
                        $pxl = array(min(max($x - 1 + $i, 0), $sx - 1), $yv);
                    $rgb = imagecolorat($srcback, $pxl[0], $pxl[1]);
                    $new_r += (($rgb >> 16) & 0xFF) * $filter[$j][$i];
                    $new_g += (($rgb >> 8) & 0xFF) * $filter[$j][$i];
                    $new_b += ($rgb & 0xFF) * $filter[$j][$i];
                }
            }
            $new_r = ($new_r/$filter_div)+$offset;
            $new_g = ($new_g/$filter_div)+$offset;
            $new_b = ($new_b/$filter_div)+$offset;
            $new_r = ($new_r > 255)? 255 : (($new_r < 0)? 0:$new_r);
            $new_g = ($new_g > 255)? 255 : (($new_g < 0)? 0:$new_g);
            $new_b = ($new_b > 255)? 255 : (($new_b < 0)? 0:$new_b);
            $new_pxl = ImageColorAllocateAlpha($src, (int)$new_r, (int)$new_g, (int)$new_b, $new_a);
            if ($new_pxl == -1) {
                $new_pxl = ImageColorClosestAlpha($src, (int)$new_r, (int)$new_g, (int)$new_b, $new_a);
            }
            if (($y >= 0) && ($y < $sy)) {
                imagesetpixel($src, $x, $y, $new_pxl);
            }
        }
    }
    imagedestroy($srcback);
    return 1;
}
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=63816&page=function.imageconvolution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=63816&page=function.imageconvolution&vote=down "Vote down!")

 -1


[**_interghost at crovortex dot com_**](https://www.php.net/manual/en/function.imageconvolution.php#63816) [¶](https://www.php.net/manual/en/function.imageconvolution.php#63816)

**19 years ago**

`an implementation of this function for PHP versions <5.1
<?php
if(!function_exists("imageconvolution"))
{
function imageconvolution(&$img,$mat,$div,$off)
{
if(!imageistruecolor($img) || !is_array($mat) || count($mat)!=3 || count($mat[0])!=3 || count($mat[1])!=3 || count($mat[2])!=3) return FALSE;
unset($bojainfo);
for($nx=0;$nx<imagesx($img)-1;$nx++)
{
     for($ny=0;$ny<imagesy($img)-1;$ny++)
     {
        $rgb=imagecolorat($img,$nx,$ny);
        $bojainfo[$nx][$ny][r]=($rgb>>16)&0xFF;
        $bojainfo[$nx][$ny][g]=($rgb>>8)&0xFF;
        $bojainfo[$nx][$ny][b]=$rgb&0xFF;
     }
}
for($nx=1;$nx<imagesx($img)-1;$nx++)
{
     for($ny=1;$ny<imagesy($img)-1;$ny++)
     {
        $nr=$mat[0][0]*$bojainfo[$nx-1][$ny-1][r] + $mat[0][1]*$bojainfo[$nx][$ny-1][r] + $mat[0][2]*$bojainfo[$nx+1][$ny-1][r] + $mat[1][0]*$bojainfo[$nx-1][$ny][r] + $mat[1][1]*$bojainfo[$nx][$ny][r] + $mat[1][2]*$bojainfo[$nx+1][$ny][r] + $mat[2][0]*$bojainfo[$nx-1][$ny+1][r] + $mat[2][1]*$bojainfo[$nx][$ny+1][r] + $mat[2][2]*$bojainfo[$nx+1][$ny+1][r];
        $nr=intval(round($nr/$div));
        if($nr<0) $nr=0;
        elseif($nr>255) $nr=255;
        $ng=$mat[0][0]*$bojainfo[$nx-1][$ny-1][g]  + $mat[0][1]*$bojainfo[$nx][$ny-1][g] + $mat[0][2]*$bojainfo[$nx+1][$ny-1][g] + $mat[1][0]*$bojainfo[$nx-1][$ny][g] + $mat[1][1]*$bojainfo[$nx][$ny][g] + $mat[1][2]*$bojainfo[$nx+1][$ny][g] + $mat[2][0]*$bojainfo[$nx-1][$ny+1][g] + $mat[2][1]*$bojainfo[$nx][$ny+1][g] + $mat[2][2]*$bojainfo[$nx+1][$ny+1][g];
        $ng=intval(round($ng/$div));
        if($ng<0) $ng=0;
        elseif($ng>255) $ng=255;
        $nb=$mat[0][0]*$bojainfo[$nx-1][$ny-1][b] + $mat[0][1]*$bojainfo[$nx][$ny-1][b] + $mat[0][2]*$bojainfo[$nx+1][$ny-1][b] + $mat[1][0]*$bojainfo[$nx-1][$ny][b] + $mat[1][1]*$bojainfo[$nx][$ny][b] + $mat[1][2]*$bojainfo[$nx+1][$ny][b] + $mat[2][0]*$bojainfo[$nx-1][$ny+1][b] + $mat[2][1]*$bojainfo[$nx][$ny+1][b] + $mat[2][2]*$bojainfo[$nx+1][$ny+1][b];
        $nb=intval(round($nb/$div));
        if($nb<0) $nb=0;
        elseif($nb>255) $nb=255;
        $nrgb=($nr<<16)+($ng<<8)+$nb;
        if(!imagesetpixel($img,$nx,$ny,$nrgb)) return FALSE;
     }
}
return TRUE;
}
}
?>
it's a bit slowish so I wouldn't recommend big images, also offset is not implemented (don't know what it's suppose to do)`

[up](https://www.php.net/manual/vote-note.php?id=60449&page=function.imageconvolution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60449&page=function.imageconvolution&vote=down "Vote down!")

 -3


[**_dyer85 at gmail dot com_**](https://www.php.net/manual/en/function.imageconvolution.php#60449) [¶](https://www.php.net/manual/en/function.imageconvolution.php#60449)

**19 years ago**

`Took me a while, but thanks to a couple of the user notes on the array_values PHP documentation page, I was able to come up with a way to dynamically compute the divisor.
I'm using PHP 5.1.0b2 on Win32 with the bundled GD library. When I try and use the imageconvolution function, whether normally, or via the functions below, the resulting image (I've only tried JPEGs and GIFs), always comes out far too bright, even when the divisor makes matrix sum equal to 1. The only thing that would reduce the brightness was to make the offset argument ridiculously large. So, I'm not sure if this effects anyone else.
Here are the functions with an example:
<?php
$im = imagecreatefromjpeg('path/to/pic.jpg');
$matrix = array(   array(5,5,5),
                   array(5,15,5),
                   array(5,5,5) );
makeFilter($im, $matrix);
header ( 'Content-Type: image/jpeg' );
imagejpeg($im);
imagedestroy($im);
/**
* functions
*/
// This flattens the 3X3 array matrix, so we can get the sum of all the values
function array_flatten($array) {
    (array)$tempArray = array();
    foreach ( $array as $value ) {
        if ( is_array($value) ) {
            $tempArray = array_merge($tempArray, array_flatten($value));
        } else {
            $tempArray[] = $value;
        }
    }
    return $tempArray;
}
// Creates the divisor value dynamically, and passes offset
function makeFilter($resource, $matrix, $offset=1.0) {
    global $$resource;
    (float)$divisor = array_sum(array_flatten($matrix));
    return imageconvolution($resource, $matrix, $divisor, $offset) ? true : false;
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imageconvolution&repo=en&redirect=https://www.php.net/manual/en/function.imageconvolution.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google