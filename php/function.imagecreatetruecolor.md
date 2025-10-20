---
url: https://www.php.net/manual/en/function.imagecreatetruecolor.php
scraped_at: 2025-10-20T02:34:27.428Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imagecreatetruecolor

(PHP 4 >= 4.0.6, PHP 5, PHP 7, PHP 8)

imagecreatetruecolor — Create a new true color image

### Description [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php\#refsect1-function.imagecreatetruecolor-description)

**imagecreatetruecolor**([int](https://www.php.net/manual/en/language.types.integer.php) `$width`, [int](https://www.php.net/manual/en/language.types.integer.php) `$height`): [GdImage](https://www.php.net/manual/en/class.gdimage.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

**imagecreatetruecolor()** returns an image object
representing a black image of the specified size.


### Parameters [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php\#refsect1-function.imagecreatetruecolor-parameters)

`width`

Image width.


`height`

Image height.


### Return Values [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php\#refsect1-function.imagecreatetruecolor-returnvalues)

Returns an image object on success, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on errors.

### Changelog [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php\#refsect1-function.imagecreatetruecolor-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | On success, this function returns a [GDImage](https://www.php.net/manual/en/class.gdimage.php) instance now;<br> previously, a [resource](https://www.php.net/manual/en/language.types.resource.php) was returned. |

### Examples [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php\#refsect1-function.imagecreatetruecolor-examples)

**Example #1**
**Creating a new GD image stream and outputting an image.**

`<?php
header ('Content-Type: image/png');
$im = @imagecreatetruecolor(120, 20)
      or die('Cannot Initialize new GD image stream');
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  'A Simple Text String', $text_color);
imagepng($im);
?>`

The above example will output
something similar to:

![Output of example : Creating a new GD image stream and outputting an image.](https://www.php.net/manual/en/images/21009b70229598c6a80eef8b45bf282b-imagecreatetruecolor.png)

### See Also [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php\#refsect1-function.imagecreatetruecolor-seealso)

- [imagecreate()](https://www.php.net/manual/en/function.imagecreate.php) \- Create a new palette based image

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/functions/imagecreatetruecolor.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imagecreatetruecolor%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagecreatetruecolor&repo=en&redirect=https://www.php.net/manual/en/function.imagecreatetruecolor.php)

### User Contributed Notes 36 notes

[up](https://www.php.net/manual/vote-note.php?id=75298&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75298&page=function.imagecreatetruecolor&vote=down "Vote down!")

34


[**_Richard Davey rich at corephp dot co dot uk_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#75298) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#75298)

**18 years ago**

`If you want to create a *transparent* PNG image, where the background is fully transparent, and all draw operations happen on-top of this, then do the following:
<?php
    $png = imagecreatetruecolor(800, 600);
    imagesavealpha($png, true);
    $trans_colour = imagecolorallocatealpha($png, 0, 0, 0, 127);
    imagefill($png, 0, 0, $trans_colour);

    $red = imagecolorallocate($png, 255, 0, 0);
    imagefilledellipse($png, 400, 300, 400, 300, $red);

    header("Content-type: image/png");
    imagepng($png);
?>
What you do is create a true colour image, make sure that the alpha save-state is on, then fill the image with a colour that has had its alpha level set to fully transparent (127).
The resulting PNG from the code above will have a red circle on a fully transparent background (drag the image into Photoshop to see for yourself)`

[up](https://www.php.net/manual/vote-note.php?id=99623&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99623&page=function.imagecreatetruecolor&vote=down "Vote down!")

20


[**_arthur at kuhrmeier dot com_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#99623) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#99623)

**15 years ago**

`HOW THE CHECK THE MEMORY BEFORE CREATING AN IMAGE?
I worked on a script where I delt with large images. Very often the error "out of memory" occured. So I had to figure out, how to check the memory BEFORE creating an image. I didn't find a solution on the web, so I ran my own test script. It built lots of images to compute the needed memory. I found out, that the formula mem = x * y * channel was not enough. There was an additional multiplier that varied. As a result 1.7 worked best. So the formula is: mem = x * y * channel * 1.7.
I post this script here hoping it is useful to someone who will run into the same problems.
<?php
//-------------------------------------------------- DEFINE MAXMEM
define ("MAXMEM", 32*1024*1024);  //--- memory limit (32M) ---
//-------------------------------------------------- ENOUGH MEMORY ?
function enoughmem ($x, $y, $rgb=3) {
    return ( $x * $y * $rgb * 1.7 < MAXMEM - memory_get_usage() );
}
//-------------------------------------------------- SIMPLE EXAMPLE
list ($x, $y) = @getimagesize ('your_img.jpg');  //--- get size of img ---
if (enoughmem($x,$y)) {
    $img = @imagecreatefromjpeg ('your_img.jpg');  //--- open img file ---
    $thumb = 200;  //--- max. size of thumb ---
    if ($x > $y) {
        $tx = $thumb;  //--- landscape ---
        $ty = round($thumb / $x * $y);
    } else {
        $tx = round($thumb / $y * $x);  //--- portrait ---
        $ty = $thumb;
    }
    if (enoughmem($tx,$ty)) {
        $thb = imagecreatetruecolor ($tx, $ty);  //--- create thumbnail ---
        imagecopyresampled ($thb,$img, 0,0, 0,0, $tx,$ty, $x,$y);
        imagejpeg ($thb, 'your_thumbnail.jpg', 80);
        imagedestroy ($thb);
    }
    imagedestroy ($img);
}
//--------------------------------------------------
//--- to check the memory working with           ---
//--- b/w-image or gif use:                      ---
//--------------------------------------------------
$check = enoughmem ($x, $y, 1);
?>
Taking the opportunity, I thank everyone here at php.net for the great manual and the useful user scripts.`

[up](https://www.php.net/manual/vote-note.php?id=46341&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=46341&page=function.imagecreatetruecolor&vote=down "Vote down!")

7


[**_kai at meder dot info_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#46341) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#46341)

**21 years ago**

`using imagecolorallocate to specify the image's background color does not work with truecolor-image.
instead you have to use imagefill to force flood-filling the image with the backgorund-color previously allocated:
$bgColor = imagecolorallocate($img, 255,255,255);
imagefill($img , 0,0 , $bgColor);
kai`

[up](https://www.php.net/manual/vote-note.php?id=25487&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=25487&page=function.imagecreatetruecolor&vote=down "Vote down!")

4


[**_aaron at aaron-wright dot com_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#25487) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#25487)

**23 years ago**

`Actually GD <2.0 had imagecreattruecolor, it just didn't work :P
This is a better test:
function chkgd2(){
$testGD = get_extension_funcs("gd"); // Grab function list
if (!$testGD){ echo "GD not even installed."; exit; }
if (in_array ("imagegd2",$testGD)) $gd_version = "<2"; // Check
if ($gd_version == "<2") return false; else return true;
}
if (chkgd2()) echo "<h1>GD2+ is installed.</h1>"; // Test for GD2
else echo "<h1>GD2+ is not installed.</h1>";`

[up](https://www.php.net/manual/vote-note.php?id=54025&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=54025&page=function.imagecreatetruecolor&vote=down "Vote down!")

7


[**_Anonymous_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#54025) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#54025)

**20 years ago**

`// Creates a transparent image rather than the default black image
function imageCreateTransparent($x, $y) {
    $imageOut = imagecreate($x, $y);
    $colourBlack = imagecolorallocate($imageOut, 0, 0, 0);
    imagecolortransparent($imageOut, $colourBlack);
    return $imageOut;
}`

[up](https://www.php.net/manual/vote-note.php?id=125734&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125734&page=function.imagecreatetruecolor&vote=down "Vote down!")

1


[**_Hamza Ahmad_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#125734) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#125734)

**4 years ago**

`As of PHP 8, the return type for image creation functions is GdImage instead of a resource. Therefore, people can type hint.
<?php
class MyImage {
private GdImage $img;
};
?>
Similarly, <?php
function save_image(GdImage $img, string $name, string $directory = null) : bool
{
/*...*/
};
?>`

[up](https://www.php.net/manual/vote-note.php?id=113063&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113063&page=function.imagecreatetruecolor&vote=down "Vote down!")

5


[**_jessiedeer at hotmail dot com_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#113063) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#113063)

**12 years ago**

`There is no need to allocate colors with imagecreatetruecolor. All [256 x 256 x 256 x 128] true colors are already allocated, and you can use the color indexes directly.
Examples :
Blue => color index 255.
White => color index 16777215 (= 255*256² + 255*256+255).
Full transparent => color index 2130706432 (= 127*256^3).`

[up](https://www.php.net/manual/vote-note.php?id=66975&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=66975&page=function.imagecreatetruecolor&vote=down "Vote down!")

4


[**_d dot duquenoy at kdland dot org_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#66975) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#66975)

**19 years ago**

`My function to know how much bytes imagecreate or imagecreatetruecolor require before using it.
<?php
function getNeededMemoryForImageCreate($width, $height, $truecolor) {
return $width*$height*(2.2+($truecolor*3));
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=81699&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81699&page=function.imagecreatetruecolor&vote=down "Vote down!")

3


[**_weareexit at yahoo dot co dot uk_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#81699) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#81699)

**17 years ago**

`If you want to place an image on a larger canvas you've previously created with imagecreatetruecolor(), but you don't want the default black background to surround it: use imagefill() AFTER imagecopyresampled().
I have no idea why this should be the case, but it works!`

[up](https://www.php.net/manual/vote-note.php?id=54155&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=54155&page=function.imagecreatetruecolor&vote=down "Vote down!")

2


[**_send at mail dot 2aj dot net_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#54155) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#54155)

**20 years ago**

`If you want a simple way to mirror images, use the function I've included below.
<?php
function image_mirror ($input_image_resource)
{
    $width = imagesx ( $input_image_resource );
    $height = imagesy ( $input_image_resource );
    $output_image_resource = imagecreatetruecolor ( $width, $height );
    $y = 1;
    while ( $y < $height )
    {
        for ( $i = 1; $i <= $width; $i++ )
            imagesetpixel ( $output_image_resource, $i, $y, imagecolorat ( $input_image_resource, ( $i ), ( $height - $y ) ) );
        $y = $y + 1;
    }

    return $output_image_resource;
}
?>
Example Usage:
<?php
// A good use of this is when a user uploads a TGA file,
// on the completion screen show the image and have a link
// that asks if the image appears mirrored, and if so
// that link will execute these commands below.
// I suggest checking $HTTP_REFERER for security.
// $_GET['file'] in this case would be something along the lines
// of johndoe-img0001 (Basename is necessary to prevent
// abuse of this script!)
if ( isset( $_GET['file'] ) )
{
    $filename = "./" . basename ( $_GET['file'] ) . ".jpg";
// Making the image resource that needs to be mirrored
// Taking it from a previously exported to JPEG file.
    $output_resource_image = image_mirror ( imagecreatefromjpeg ( $filename ) );
    if ( imagejpeg ( $output_resource_image, $filename, 75 ) )
        echo "Image resaved successfully";
    else
        echo "Image couldn't be written over (Check permissions)!";
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=33890&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=33890&page=function.imagecreatetruecolor&vote=down "Vote down!")

3


[**_Jami_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#33890) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#33890)

**22 years ago**

`It's good to use the imagecopyresampled- function when creating thumbnails with true colors, it might look better than imagecopyresized..`

[up](https://www.php.net/manual/vote-note.php?id=38553&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=38553&page=function.imagecreatetruecolor&vote=down "Vote down!")

1


[**_fixxxer at php5 dot ru_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#38553) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#38553)

**21 years ago**

`A note to post by Justin Greer @ 18-Nov-2003 10:40:
While this information has already been posted by php at REMOVEreallynicejerk dot com @ 16-Sep-2002 12:01, I feel it neccesary to notice 'cause Justin's post is in the top and it can make people go the wrong way: Justin's way of detecting which imagecreate function to use is too complicated, while there's an easy standard way:
<?php
if (function_exists('imagecreatetruecolor') {
// use imagecreatetruecolor
} else {
// use imagecreate
}`

[up](https://www.php.net/manual/vote-note.php?id=28822&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=28822&page=function.imagecreatetruecolor&vote=down "Vote down!")

1


[**_marc at thewebguys dot com dot au_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#28822) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#28822)

**22 years ago**

`I discovered when installing GD 2+ that ImageCreate() doesn't work well with JPEGS, it makes a true colour JPEG into a 16 colour mess when combining ImageCreateFromJPEG(). If you have GD 2+ you must use ImageCreateTrueColor() for things like thumbnails, etc.`

[up](https://www.php.net/manual/vote-note.php?id=14729&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=14729&page=function.imagecreatetruecolor&vote=down "Vote down!")

1


[**_eric at spiderws dot com_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#14729) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#14729)

**24 years ago**

`This little function does it for you:
<?
$image_id = imageCreateFromJPEG($image);
for($a=0;$a<imagecolorstotal ($image_id);$a++)
        {
            $color = ImageColorsForIndex($image_id,$i);
            $R=.299 * ($color['red'])+ .587 * ($color['green'])+ .114 * ($color['blue']);
            $G=.299 * ($color['red'])+ .587 * ($color['green'])+ .114 * ($color['blue']);
            $B=.299 * ($color['red'])+ .587 * ($color['green'])+ .114 * ($color['blue']);
            ImageColorSet($image_id, $a, $R, $G, $B);
        }
imageJPEG($image_id,"$image");
?>
The .299 , .578 , .114 values are estimations, and add a gamma correction to the colors. For more or less luminace in the result, you can change these values.
Goodluck,
Eric Mulders, Netherlands`

[up](https://www.php.net/manual/vote-note.php?id=68299&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=68299&page=function.imagecreatetruecolor&vote=down "Vote down!")

0


[**_Florin \[ florin.at.flachi.dot.net \]_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#68299) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#68299)

**19 years ago**

`A very simple and efficient way to create RGB color from hexadecimal (HTML) notation:
<?php
    function color_hex2dec ($color) {
        return array (hexdec (substr ($color, 0, 2)), hexdec (substr ($color, 2, 2)), hexdec (substr ($color, 4, 2)));
    }
    list ($r, $g, $b) = color_hex2dec ('FFEECC');
?>`

[up](https://www.php.net/manual/vote-note.php?id=68045&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=68045&page=function.imagecreatetruecolor&vote=down "Vote down!")

0


[**_j.fenin \_At\_ seekport \[d0t\] biz_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#68045) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#68045)

**19 years ago**

`I had a strange bug occurring under Debian Linux with PHP5.
In file B (where I create the image) I included a file (file A). The image that was produced was always corrupt. When I did not include file A, everything was fine.
After 2 hours of searching I found that there were some extra spaces and linefeeds after the PHP closing tag ?> in file A. After removing those chars, everything works fine again.
Obviously those extra bytes of file A were added to the image and corrupted it.`

[up](https://www.php.net/manual/vote-note.php?id=38856&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=38856&page=function.imagecreatetruecolor&vote=down "Vote down!")

0


[**_Justin Greer_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#38856) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#38856)

**21 years ago**

`I know it's not a discussion board, but when incorrect info is posted, it should be corrected.
The function_exists() check does not work correctly because if PHP is compiled with an older GD library, the imagecreatetruecolor() function still exists -- it just gives a fatal error when called, stating that GD2 is required.  Therefore, the function_exists() method will fail on any new-ish copy of PHP that only has GD 1.x.  (That includes most of the 4.1.x and 4.2.x installs I've seen.)`

[up](https://www.php.net/manual/vote-note.php?id=37523&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=37523&page=function.imagecreatetruecolor&vote=down "Vote down!")

0


[**_Justin Greer_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#37523) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#37523)

**21 years ago**

`Unfortunately the @imagecreatetruecolor() method doesn't even work because php dies with a fatal error noting that GD 2 is required.  You can't even capture this error with a custom error handler.
I have come up with a function to get the GD version number that seems to work pretty well on every version of PHP and GD I've thrown at it (even CLI versions.)  It's obviously not the most efficient thing in the world, but it does cache the result in a static variable so calling it multiple times doesn't slow down further.
function gd_version() {
    static $gd_version_number = null;
    if ($gd_version_number === null) {
        // Use output buffering to get results from phpinfo()
        // without disturbing the page we're in.  Output
        // buffering is "stackable" so we don't even have to
        // worry about previous or encompassing buffering.
        ob_start();
        phpinfo(8);
        $module_info = ob_get_contents();
        ob_end_clean();
        if (preg_match("/\bgd\s+version\b[^\d\n\r]+?([\d\.]+)/i",
                $module_info,$matches)) {
            $gd_version_number = $matches[1];
        } else {
            $gd_version_number = 0;
        }
    }
    return $gd_version_number;
}
Then you can simply use it something like this:
if (gd_version() >= 2) {
    $image = ImageCreateTrueColor($width, $height);
} else {
    $image = ImageCreate($width, $height);
}`

[up](https://www.php.net/manual/vote-note.php?id=36915&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=36915&page=function.imagecreatetruecolor&vote=down "Vote down!")

0


[**_Hallvord RM Steen <phpnet at hallvord dot com>_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#36915) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#36915)

**21 years ago**

`Regarding choosing the TrueColor or the plain version of imagecreate automatically, I've found that the following works for me:
<?php
$newImg=@ImageCreateTrueColor($width, $height)
    or $newImg=ImageCreate($width, $height);
?>`

[up](https://www.php.net/manual/vote-note.php?id=32818&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=32818&page=function.imagecreatetruecolor&vote=down "Vote down!")

0


[**_bjorntje at hotmail dot com_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#32818) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#32818)

**22 years ago**

`I just fiddled around with Phpix, which had some problems using the GD lib
(washed out colours).
I changed the lines, which did the trick.
Just in case some of you are still having problems and
you can't change the PHP-install
on the hosting side:
$im = ImageCreateFromJPEG($source);
$new_im = ImageCreate($new_width,$new_height);

ImageCopyResized($new_im,$im,0,0,0,0,
$new_width,$new_height,ImageSX($im),ImageSY($im));
TO
$im = ImageCreateFromJPEG($source);
$new_im = ImageCreateTrueColor($new_width,$new_height);

ImageCopyResized($new_im,$im,0,0,0,0,$new_width,
$new_height,ImageSX($im),ImageSY($im));`

[up](https://www.php.net/manual/vote-note.php?id=29912&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=29912&page=function.imagecreatetruecolor&vote=down "Vote down!")

0


[**_Andreas from www.ems-p.de_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#29912) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#29912)

**22 years ago**

`The request of gdlib from brad at brwebdesign dot com won't work with PHP < 4.1 (version_compare).
Some phpinfo versions offer the version number without space so you better ask for the dot:
ob_start();
phpinfo(8);
$phpinfo=ob_get_contents();
ob_end_clean();
$phpinfo=strip_tags($phpinfo);
$phpinfo=stristr($phpinfo,"gd version");
$phpinfo=stristr($phpinfo,"version");
$end=strpos($phpinfo,".");
$phpinfo=substr($phpinfo,0,$end);
$length = strlen($phpinfo)-1;
$phpinfo=substr($phpinfo,$length);
if($phpinfo<2){
    $dst_img=ImageCreate($new_w,$new_h);}
else {
    $dst_img=ImageCreateTrueColor($new_w,$new_h);
}`

[up](https://www.php.net/manual/vote-note.php?id=28470&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=28470&page=function.imagecreatetruecolor&vote=down "Vote down!")

0


[**_billet\_jerome at yahoo dot fr_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#28470) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#28470)

**22 years ago**

`Because imagecreatetruecolor exist both in gd and gd2,
you can't use function_exists or get_extension_funcs to check for gd2 !
But ... there is a difference in imagettfbbox between gd and gd2:
gd use pixels and gd2 use points.
Then you can check gd2 with this function:
function sysB_chkgd2()
{
$rep=false;
if(isset($GLOBALS["gBGDVersion"]))
    {
    $rep=$GLOBALS["gBGDVersion"];
    }
else
    {
    if(function_exists("gd_info"))
       {
       $gdver=gd_info();
       if(strstr($gdver["GD Version"],"1.")!=false)
          {
          $rep=false;
          }
       else
           {
           $rep=true;
           }
       }
    else
        {
        $size=40;
        $font= your font file path here;
        $b=imagettfbbox ($size,0,$font,"abcdefghijklmnopqrstuvwxyz
ABCDEFGHIJKLMNOPQRSTUVWXYZ");
        if(($size+1)<abs($b[5]-$b[3]))
           {
           $rep=true;
           }
         }
    $GLOBALS["gBGDVersion"]=$rep;
    }
return $rep;
}`

[up](https://www.php.net/manual/vote-note.php?id=25234&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=25234&page=function.imagecreatetruecolor&vote=down "Vote down!")

0


[**_php at REMOVEreallynicejerk dot com_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#25234) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#25234)

**23 years ago**

`Why not just use function_exists?
[http://www.php.net/function\_exists](http://www.php.net/function_exists)
Just because they have version 2.0 GD doesn't mean that they haven't disabled that function.
Also instead of determining which one you have on your machine and then writing setup specific code, you can write a universal code usable on either setups.
::pseudo code::
if (function_exists(imagecreatetruecolor)){
use imagecreatetruecolor()
}else{
use imagecreate()
}`

[up](https://www.php.net/manual/vote-note.php?id=19385&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=19385&page=function.imagecreatetruecolor&vote=down "Vote down!")

0


[**_pmas7354 at artax dot karlin dot mff dot cuni dot cz_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#19385) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#19385)

**23 years ago**

`Here is answer for first question 'why do I need true color images'.
True color images you need when you want to work with images such as photos (snapshots), video frames and so on.
When you need to combine some these images for user, or to send him only small part of your image, and you try to use 256 colors, image will be ugly (try it if you want). Some colors will change dramatically.
"Antialias" lines which you may see are probably the result of using JPEG compression. JPEG is not looseless compression so "small image details may be changed" in order to reduce image size dramatically. On really true-color images such as your snapshots of landscape and so on and using small compression level you will hardly see differences. But on exact objects, such as lines, circles, which you draw on solid background using single color, you can see that if you save and load this image that some details are changed.`

[up](https://www.php.net/manual/vote-note.php?id=18462&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=18462&page=function.imagecreatetruecolor&vote=down "Vote down!")

0


[**_rossa at studioware dot net_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#18462) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#18462)

**23 years ago**

`function ConvertGreyscale($image){
# this file outputs a grey version of specified image
$total = ImageColorsTotal($image);
for( $i=0; $i<$total; $i++){
     $old = ImageColorsForIndex($image, $i);

     #trying to keep proper saturation when converting
     $commongrey = (int)(($old[red] + $old[green] + $old[blue]) / 3);
     ImageColorSet($image, $i, $commongrey, $commongrey, $commongrey);
}
}`

[up](https://www.php.net/manual/vote-note.php?id=54010&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=54010&page=function.imagecreatetruecolor&vote=down "Vote down!")

 -1


[**_send at mail dot 2aj dot net_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#54010) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#54010)

**20 years ago**

`Thanks to OverFlow636 at gmail dot com and kuya1284 at techie dot com for their original coding which this function is based upon.
PHP lacks an imagecreatefromtga function, so I have prepared a simple function to include in your library if you deal with TGA images. In addition to creating an image from TGA, it also, optionally, will output an array with the dimensions of the image because getimagesize() does not function with TGA files.
Hopefully this function will eventually be unneeded if GD is ever updated to support the TGA format.
Please keep in mind that TGA's come in many different compressions, color settings, and as a result this function will not work 100% of the time. Resulting images will fit the symptoms kuya1284 at techie dot com mentioned, and as a result you may need to create a second function. Keep in mind that using her code causes the "mirror" effect on images that load properly with the following function.
<?php
function imagecreatefromtga ( $filename, $return_array = 0 )
{
    $handle = fopen ( $filename, 'rb' );
    $data = fread ( $handle, filesize( $filename ) );
    fclose ( $handle );

    $pointer = 18;
    $x = 0;
    $y = 0;
    $w = base_convert ( bin2hex ( strrev ( substr ( $data, 12, 2 ) ) ), 16, 10 );
    $h = base_convert ( bin2hex ( strrev ( substr ( $data, 14, 2 ) ) ), 16, 10 );
    $img = imagecreatetruecolor( $w, $h );
    while ( $pointer < strlen ( $data ) )
    {
        imagesetpixel ( $img, $x, $y, base_convert ( bin2hex ( strrev ( substr ( $data, $pointer, 3 ) ) ), 16, 10 ) );
        $x++;
        if ($x == $w)
        {
            $y++;
            $x=0;
        }
        $pointer += 3;
    }

    if ( $return_array )
        return array ( $img, $w, $h );
    else
        return $img;
}
?>
Example Usage
<?php
// Get the image & its dimensions
$array = imagecreatefromtga("source_image.tga",1);
// the image ( resource image )
$image = $array[0];
// its dimensions ( integers )
$dimensions['width'] = $array[1];
$dimensions['height'] = $array[2];
// Delete the image resource array entry to free memory
imagedestroy($array[0]);
?>
The second variable, $return_array is optional. If you simply want to load a TGA, leave the variable off the function's call as such:
<?
// Return the resource image alone
$resource_image = imagecreatefromtga ( "source_image.tga" );
// Declare the content-type as a JPEG image.
header ( 'Content-type: image/jpeg' );
// Convert the image to JPEG for smaller file size and compatability
imagejpeg ( $resource_image, NULL, 100 );
imagedestroy ( $resource_image );
?>`

[up](https://www.php.net/manual/vote-note.php?id=69207&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=69207&page=function.imagecreatetruecolor&vote=down "Vote down!")

 -1


[**_behun at webconsult dot sk_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#69207) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#69207)

**19 years ago**

`imagecreatetruecolor() returns not only image identifier representing a black image of size x_size by y_size.
imagecreatetruecolor() is called to create truecolor images, with an essentially unlimited number of colors (also not only 256 colors).`

[up](https://www.php.net/manual/vote-note.php?id=47917&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=47917&page=function.imagecreatetruecolor&vote=down "Vote down!")

 -1


[**_termian_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#47917) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#47917)

**20 years ago**

`kai wrote:
//using imagecolorallocate to specify the image's background
//color does not work with truecolor-image.
//
//instead you have to use imagefill to force flood-filling the
//image with the backgorund-color previously allocated:
//
//$bgColor = imagecolorallocate($img, 255,255,255);
//imagefill($img , 0,0 , $bgColor);
even this doesn't work for my configuration - fedora core2, php 4.3.8 + gd bundled (2.0.23 compatible) and I have to do this:
$img = imagecreatetruecolor($x, $y);
$bgColor = imagecolorallocate($img, 255,255,255);
imagefilledrectangle($img, 0, 0, $x-1, $y-1, $bgColor);`

[up](https://www.php.net/manual/vote-note.php?id=91180&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91180&page=function.imagecreatetruecolor&vote=down "Vote down!")

 -2


[**_hemjesti at yahoo dot com_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#91180) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#91180)

**16 years ago**

`I put this together - combining two of the examples and then generated the text dynamically. but, with this set up, i was able to get the transparent background working as well.
<?php
// Set the content-type
header('Content-type: image/png');
// Create the image
$im = imagecreatetruecolor(175, 15);
imagesavealpha($im, true);
// Create some colors
$white = imagecolorallocate($im, 255, 255, 255);
$grey = imagecolorallocate($im, 128, 128, 128);
$black = imagecolorallocate($im, 0, 0, 0);
imagefilledrectangle($im, 0, 0, 150, 25, $black);
$trans_colour = imagecolorallocatealpha($im, 0, 0, 0, 127);
imagefill($im, 0, 0, $trans_colour);
// The text to draw
$text = $_GET['text'];
// Replace path by your own font path
$font = 'catriel regular.ttf';
// Add some shadow to the text
imagettftext($im, 9, 0, 13, 16, $black, $font, $text);
// Add the text
imagettftext($im, 9, 0, 12, 15, $white, $font, $text);
// Using imagepng() results in clearer text compared with imagejpeg()
imagepng($im);
imagedestroy($im);
?>`

[up](https://www.php.net/manual/vote-note.php?id=72993&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72993&page=function.imagecreatetruecolor&vote=down "Vote down!")

 -1


[**_phpnet at sjeiti dot com_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#72993) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#72993)

**18 years ago**

`Just a small rectification for the msg by '
thomas dot urban at toxa dot de' (23-May-2006 03:28) about transparency.
Line 3 in the example returns a 'wrong parameter warning': 'imagecolorallocate' should be replaced by 'imagecolorallocatealpha'.
(You better just alter that note and delete this one.)`

[up](https://www.php.net/manual/vote-note.php?id=48162&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=48162&page=function.imagecreatetruecolor&vote=down "Vote down!")

 -1


[**_OverFlow636 at gmail dot com_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#48162) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#48162)

**20 years ago**

`i dont know if there was an easyer way to do this, but heres my code to convert a .tga image to whatever you want to output it as
it works with basic tga files only
<?
$handle = fopen("xxx.tga","rb");
$data = fread($handle,filesize("xxx.tga"));
fclose($handle);
$pointer = 18;
$x = 0;
$y = 0;
$w = fileint(substr($data,12,2));
$h = fileint(substr($data,14,2));
$img = imagecreatetruecolor($w,$h);
while ($pointer < strlen($data))
{
imagesetpixel($img, $x,$y,fileint(substr($data,$pointer,3)));
$x++;
if ($x==$w)
{
$y++;
$x=0;
}
$pointer += 3;
}
header("Content-type: image/jpeg");
imagepng($img);
imagedestroy($img);
function fileint($str)
{
return base_convert(bin2hex(strrev($str)),16,10);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=21761&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=21761&page=function.imagecreatetruecolor&vote=down "Vote down!")

 -1


[**_brad at brwebdesign dot com_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#21761) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#21761)

**23 years ago**

`I came up with this today.  You need GD2.0 or greater to use imagecreatetruecolor so you can parse phpinfo to get the needed information.  this will have to go at the very top of the page with no whitespace above it
<?php
ob_start();
phpinfo(8);
$phpinfo=ob_get_contents();
ob_end_clean();
$phpinfo=strip_tags($phpinfo);
$phpinfo=stristr($phpinfo,"gd version");
$phpinfo=stristr($phpinfo,"version");
$end=strpos($phpinfo," ");
$phpinfo=substr($phpinfo,0,$end);
$phpinfo=substr($phpinfo,7);
if(version_compare("2.0", "$phpinfo")==1)
echo "you have a version less then 2";
?>
The if statement is for PHP 4.1 or greater, but you can use other methods of comparing the version numbers if the server you are on do not have that version of php`

[up](https://www.php.net/manual/vote-note.php?id=115048&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115048&page=function.imagecreatetruecolor&vote=down "Vote down!")

 -1


[**_smcjones at gmail dot com_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#115048) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#115048)

**11 years ago**

`Please note that if you are receiving a warning about incorrect dimensions in PHP, it could be because your values are being stored as strings. You can use intval() to change a string value into an integer value which will pass the correct information into this function.`

[up](https://www.php.net/manual/vote-note.php?id=30160&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=30160&page=function.imagecreatetruecolor&vote=down "Vote down!")

 -1


[**_Micke (micke dot prag at newstonight dot net)_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#30160) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#30160)

**22 years ago**

`Here is my solution for creating images with the same code for both GD < 2 and GD > 2:
$dst_img = @imageCreateTrueColor($width, $height);
if (!$dst_img) { $dst_img = imageCreate($width, $height); }`

[up](https://www.php.net/manual/vote-note.php?id=50400&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=50400&page=function.imagecreatetruecolor&vote=down "Vote down!")

 -2


[**_kuya1284 at techie dot com_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#50400) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#50400)

**20 years ago**

`OverFlow636,
It appears that your code was causing TGA's to be inverted horizontally and upside down.  I modified your code accordingly. The sample below is an example of what I did to convert a tga to jpg. The for loop was taken from the comment below (Eric Mulders) to properly render the image.
Nice job with the code buddy.
function tga2jpg ($image)
{
    $handle = fopen($image, "rb");
    $data = fread($handle, filesize($image));
    fclose($handle);
    $pointer = 18;
    $w = fileint (substr ($data, 12, 2));
    $h = fileint (substr ($data, 14, 2));
    $x = 0;
    $y = $h;
    $img = imagecreatetruecolor($w, $h);
    while ($pointer < strlen($data))
    {
        imagesetpixel ($img, $x, $y, fileint (substr ($data, $pointer, 3)));

        $x++;
        if ($x == $w)
        {
            $y--;
            $x = 0;
        }
        $pointer += 3;
    }

    for($a = 0; $a < imagecolorstotal ($img); $a++)
    {
        $color = imagecolorsforindex ($img, $a);

        $R=.299 * ($color['red'])+ .587 * ($color['green'])+ .114 * ($color['blue']);
        $G=.299 * ($color['red'])+ .587 * ($color['green'])+ .114 * ($color['blue']);
        $B=.299 * ($color['red'])+ .587 * ($color['green'])+ .114 * ($color['blue']);

        imagecolorset ($img, $a, $R, $G, $B);
    }

    imagejpeg ($img, 'test.jpg', 100);
    imagedestroy ($img);
}
function fileint($str)
{
    return base_convert (bin2hex (strrev ($str)), 16, 10);
}
tga2jpg ('test.tga');`

[up](https://www.php.net/manual/vote-note.php?id=42645&page=function.imagecreatetruecolor&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=42645&page=function.imagecreatetruecolor&vote=down "Vote down!")

 -3


[**_unigram at byair dot net_**](https://www.php.net/manual/en/function.imagecreatetruecolor.php#42645) [¶](https://www.php.net/manual/en/function.imagecreatetruecolor.php#42645)

**21 years ago**

`If your hosting system does not have imagecreatetruecolor() because of PHP<4.2 and GD<2.0 then a get around is
<?
$thumb = imagecreate ($width, $height);
imageJPEG($thumb,"images/temp.jpg");
$thumb = @imagecreatefromjpeg("images/temp.jpg");
?>
which creates a thumbnail of right size, saves as a jpeg and then reads it, in true color.
This corrected the degradation caused by using palette images as destination for imagecopyresized ()`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagecreatetruecolor&repo=en&redirect=https://www.php.net/manual/en/function.imagecreatetruecolor.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google