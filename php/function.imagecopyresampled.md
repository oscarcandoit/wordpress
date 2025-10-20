---
url: https://www.php.net/manual/en/function.imagecopyresampled.php
scraped_at: 2025-10-20T02:59:31.815Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imagecopyresampled

(PHP 4 >= 4.0.6, PHP 5, PHP 7, PHP 8)

imagecopyresampled — Copy and resize part of an image with resampling

### Description [¶](https://www.php.net/manual/en/function.imagecopyresampled.php\#refsect1-function.imagecopyresampled-description)

**imagecopyresampled**(

[GdImage](https://www.php.net/manual/en/class.gdimage.php) `$dst_image`,

[GdImage](https://www.php.net/manual/en/class.gdimage.php) `$src_image`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$dst_x`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$dst_y`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$src_x`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$src_y`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$dst_width`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$dst_height`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$src_width`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$src_height`

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**imagecopyresampled()** copies a rectangular
portion of one image to another image, smoothly interpolating pixel
values so that, in particular, reducing the size of an image still
retains a great deal of clarity.


In other words, **imagecopyresampled()** will take a
rectangular area from `src_image` of width
`src_width` and height `src_height` at
position ( `src_x`, `src_y`)
and place it in a rectangular area of `dst_image`
of width `dst_width` and height `dst_height`
at position ( `dst_x`, `dst_y`).


If the source and destination coordinates and width and heights
differ, appropriate stretching or shrinking of the image fragment
will be performed. The coordinates refer to the upper left
corner. This function can be used to copy regions within the
same image (if `dst_image` is the same as
`src_image`) but if the regions overlap the
results will be unpredictable.


### Parameters [¶](https://www.php.net/manual/en/function.imagecopyresampled.php\#refsect1-function.imagecopyresampled-parameters)

`dst_image`

Destination image resource.

`src_image`

Source image resource.

`dst_x`

x-coordinate of destination point.


`dst_y`

y-coordinate of destination point.


`src_x`

x-coordinate of source point.


`src_y`

y-coordinate of source point.


`dst_width`

Destination width.


`dst_height`

Destination height.


`src_width`

Source width.

`src_height`

Source height.

### Return Values [¶](https://www.php.net/manual/en/function.imagecopyresampled.php\#refsect1-function.imagecopyresampled-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Changelog [¶](https://www.php.net/manual/en/function.imagecopyresampled.php\#refsect1-function.imagecopyresampled-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `dst_image` and `src_image` expect<br> [GdImage](https://www.php.net/manual/en/class.gdimage.php) instances now; previously, [resource](https://www.php.net/manual/en/language.types.resource.php)s<br> were expected. |

### Examples [¶](https://www.php.net/manual/en/function.imagecopyresampled.php\#refsect1-function.imagecopyresampled-examples)

**Example #1 Simple example**

This example will resample an image to half its original size.


`<?php
// The file
$filename = 'test.jpg';
$percent = 0.5;
// Content type
header('Content-Type: image/jpeg');
// Get new dimensions
list($width, $height) = getimagesize($filename);
$new_width = $width * $percent;
$new_height = $height * $percent;
// Resample
$image_p = imagecreatetruecolor($new_width, $new_height);
$image = imagecreatefromjpeg($filename);
imagecopyresampled($image_p, $image, 0, 0, 0, 0, $new_width, $new_height, $width, $height);
// Output
imagejpeg($image_p, null, 100);
?>`

The above example will output
something similar to:

![Output of example : Simple example](https://www.php.net/manual/en/images/21009b70229598c6a80eef8b45bf282b-imagecopyresampled.jpg)

**Example #2 Resampling an image proportionally**

This example will display an image with the maximum width,
or height, of 200 pixels.


`<?php
// The file
$filename = 'test.jpg';
// Set a maximum height and width
$width = 200;
$height = 200;
// Content type
header('Content-Type: image/jpeg');
// Get new dimensions
list($width_orig, $height_orig) = getimagesize($filename);
$ratio_orig = $width_orig/$height_orig;
if ($width/$height > $ratio_orig) {
$width = $height*$ratio_orig;
} else {
$height = $width/$ratio_orig;
}
// Resample
$image_p = imagecreatetruecolor($width, $height);
$image = imagecreatefromjpeg($filename);
imagecopyresampled($image_p, $image, 0, 0, 0, 0, $width, $height, $width_orig, $height_orig);
// Output
imagejpeg($image_p, null, 100);
?>`

The above example will output
something similar to:

![Output of example : Resampling an image proportionally](https://www.php.net/manual/en/images/21009b70229598c6a80eef8b45bf282b-imagecopyresampled_2.jpg)

### Notes [¶](https://www.php.net/manual/en/function.imagecopyresampled.php\#refsect1-function.imagecopyresampled-notes)

> **Note**:
>
>
> There is a problem due to palette image limitations (255+1 colors).
> Resampling or filtering an image commonly needs more colors than 255, a
> kind of approximation is used to calculate the new resampled pixel and its
> color. With a palette image we try to allocate a new color, if that
> failed, we choose the closest (in theory) computed color. This is
> not always the closest visual color. That may produce a weird result, like
> blank (or visually blank) images. To skip this problem, please use a
> truecolor image as a destination image, such as one created by
> [imagecreatetruecolor()](https://www.php.net/manual/en/function.imagecreatetruecolor.php).

### See Also [¶](https://www.php.net/manual/en/function.imagecopyresampled.php\#refsect1-function.imagecopyresampled-seealso)

- [imagecopyresized()](https://www.php.net/manual/en/function.imagecopyresized.php) \- Copy and resize part of an image
- [imagescale()](https://www.php.net/manual/en/function.imagescale.php) \- Scale an image using the given new width and height
- [imagecrop()](https://www.php.net/manual/en/function.imagecrop.php) \- Crop an image to the given rectangle

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/functions/imagecopyresampled.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imagecopyresampled%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagecopyresampled&repo=en&redirect=https://www.php.net/manual/en/function.imagecopyresampled.php)

### User Contributed Notes 37 notes

[up](https://www.php.net/manual/vote-note.php?id=112742&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112742&page=function.imagecopyresampled&vote=down "Vote down!")

203


[**_wbcarts at juno dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#112742) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#112742)

**12 years ago**

`FOUR RECTANGLES
                  $src_image                                   $dst_image
+------------+---------------------------------+   +------------+--------------------+
|            |                                 |   |            |                    |
|            |                                 |   |         $dst_y                  |
|            |                                 |   |            |                    |
|         $src_y                               |   +-- $dst_x --+----$dst_width----+ |
|            |                                 |   |            |                  | |
|            |                                 |   |            |    Resampled     | |
|            |                                 |   |            |                  | |
+-- $src_x --+------ $src_width ------+        |   |       $dst_height             | |
|            |                        |        |   |            |                  | |
|            |                        |        |   |            |                  | |
|            |                        |        |   |            |                  | |
|            |                        |        |   |            +------------------+ |
|            |        Sample          |        |   |                                 |
|            |                        |        |   |                                 |
|            |                        |        |   |                                 |
|       $src_height                   |        |   |                                 |
|            |                        |        |   +---------------------------------+
|            |                        |        |
|            |                        |        |
|            +------------------------+        |
|                                              |
|                                              |
+----------------------------------------------+`

[up](https://www.php.net/manual/vote-note.php?id=104028&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104028&page=function.imagecopyresampled&vote=down "Vote down!")

79


[**_promaty at gmail dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#104028) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#104028)

**14 years ago**

`Here is my ultimate image resizer that preserves transparency for gif's and png's and has an option to crop images to fixed dimensions (preserves image proportions by default)
<?php
function image_resize($src, $dst, $width, $height, $crop=0){
if(!list($w, $h) = getimagesize($src)) return "Unsupported picture type!";
$type = strtolower(substr(strrchr($src,"."),1));
if($type == 'jpeg') $type = 'jpg';
switch($type){
    case 'bmp': $img = imagecreatefromwbmp($src); break;
    case 'gif': $img = imagecreatefromgif($src); break;
    case 'jpg': $img = imagecreatefromjpeg($src); break;
    case 'png': $img = imagecreatefrompng($src); break;
    default : return "Unsupported picture type!";
}
// resize
if($crop){
    if($w < $width or $h < $height) return "Picture is too small!";
    $ratio = max($width/$w, $height/$h);
    $h = $height / $ratio;
    $x = ($w - $width / $ratio) / 2;
    $w = $width / $ratio;
}
else{
    if($w < $width and $h < $height) return "Picture is too small!";
    $ratio = min($width/$w, $height/$h);
    $width = $w * $ratio;
    $height = $h * $ratio;
    $x = 0;
}
$new = imagecreatetruecolor($width, $height);
// preserve transparency
if($type == "gif" or $type == "png"){
    imagecolortransparent($new, imagecolorallocatealpha($new, 0, 0, 0, 127));
    imagealphablending($new, false);
    imagesavealpha($new, true);
}
imagecopyresampled($new, $img, 0, 0, $x, 0, $width, $height, $w, $h);
switch($type){
    case 'bmp': imagewbmp($new, $dst); break;
    case 'gif': imagegif($new, $dst); break;
    case 'jpg': imagejpeg($new, $dst); break;
    case 'png': imagepng($new, $dst); break;
}
return true;
}
?>
Example that I use when uploading new images to the server.
This saves the original picture in the form:
original.type
and creates a new thumbnail:
100x100.type
<?php
$pic_type = strtolower(strrchr($picture['name'],"."));
$pic_name = "original$pic_type";
move_uploaded_file($picture['tmp_name'], $pic_name);
if (true !== ($pic_error = @image_resize($pic_name, "100x100$pic_type", 100, 100, 1))) {
    echo $pic_error;
    unlink($pic_name);
}
else echo "OK!";
?>
Cheers!`

[up](https://www.php.net/manual/vote-note.php?id=85929&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85929&page=function.imagecopyresampled&vote=down "Vote down!")

15


[**_zorroswordsman at gmail dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#85929) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#85929)

**17 years ago**

`I've created a PHP5 image resize class, using ImageCopyResampled, that someone might find useful, with support for JPEG, PNG, and GIF formats. It retains the original image's aspect ratio when resizing, and doesn't resize or resample if the original width and height is smaller then the desired resize.
<?php
// Imaging
class imaging
{
    // Variables
    private $img_input;
    private $img_output;
    private $img_src;
    private $format;
    private $quality = 80;
    private $x_input;
    private $y_input;
    private $x_output;
    private $y_output;
    private $resize;
    // Set image
    public function set_img($img)
    {
        // Find format
        $ext = strtoupper(pathinfo($img, PATHINFO_EXTENSION));
        // JPEG image
        if(is_file($img) && ($ext == "JPG" OR $ext == "JPEG"))
        {
            $this->format = $ext;
            $this->img_input = ImageCreateFromJPEG($img);
            $this->img_src = $img;

        }
        // PNG image
        elseif(is_file($img) && $ext == "PNG")
        {
            $this->format = $ext;
            $this->img_input = ImageCreateFromPNG($img);
            $this->img_src = $img;
        }
        // GIF image
        elseif(is_file($img) && $ext == "GIF")
        {
            $this->format = $ext;
            $this->img_input = ImageCreateFromGIF($img);
            $this->img_src = $img;
        }
        // Get dimensions
        $this->x_input = imagesx($this->img_input);
        $this->y_input = imagesy($this->img_input);
    }
    // Set maximum image size (pixels)
    public function set_size($size = 100)
    {
        // Resize
        if($this->x_input > $size && $this->y_input > $size)
        {
            // Wide
            if($this->x_input >= $this->y_input)
            {
                $this->x_output = $size;
                $this->y_output = ($this->x_output / $this->x_input) * $this->y_input;
            }
            // Tall
            else
            {
                $this->y_output = $size;
                $this->x_output = ($this->y_output / $this->y_input) * $this->x_input;
            }
            // Ready
            $this->resize = TRUE;
        }
        // Don't resize
        else { $this->resize = FALSE; }
    }
    // Set image quality (JPEG only)
    public function set_quality($quality)
    {
        if(is_int($quality))
        {
            $this->quality = $quality;
        }
    }
    // Save image
    public function save_img($path)
    {
        // Resize
        if($this->resize)
        {
            $this->img_output = ImageCreateTrueColor($this->x_output, $this->y_output);
            ImageCopyResampled($this->img_output, $this->img_input, 0, 0, 0, 0, $this->x_output, $this->y_output, $this->x_input, $this->y_input);
        }
        // Save JPEG
        if($this->format == "JPG" OR $this->format == "JPEG")
        {
            if($this->resize) { imageJPEG($this->img_output, $path, $this->quality); }
            else { copy($this->img_src, $path); }
        }
        // Save PNG
        elseif($this->format == "PNG")
        {
            if($this->resize) { imagePNG($this->img_output, $path); }
            else { copy($this->img_src, $path); }
        }
        // Save GIF
        elseif($this->format == "GIF")
        {
            if($this->resize) { imageGIF($this->img_output, $path); }
            else { copy($this->img_src, $path); }
        }
    }
    // Get width
    public function get_width()
    {
        return $this->x_input;
    }
    // Get height
    public function get_height()
    {
        return $this->y_input;
    }
    // Clear image cache
    public function clear_cache()
    {
        @ImageDestroy($this->img_input);
        @ImageDestroy($this->img_output);
    }
}
##### DEMO #####
// Image
$src = "myimage.jpg";
// Begin
$img = new imaging;
$img->set_img($src);
$img->set_quality(80);
// Small thumbnail
$img->set_size(200);
$img->save_img("small_" . $src);
// Baby thumbnail
$img->set_size(50);
$img->save_img("baby_" . $src);
// Finalize
$img->clear_cache();
?>`

[up](https://www.php.net/manual/vote-note.php?id=81273&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81273&page=function.imagecopyresampled&vote=down "Vote down!")

3


[**_wm at violet dot bg_**](https://www.php.net/manual/en/function.imagecopyresampled.php#81273) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#81273)

**17 years ago**

`This is a fixed version of ImageCopyResampledBicubic posted by liviu.malaescu
The original version wasn't respecting src_x & src_y args
<?php
    function ImageCopyResampledBicubic(&$dst_image, &$src_image, $dst_x, $dst_y, $src_x, $src_y, $dst_w, $dst_h, $src_w, $src_h)  {
        // we should first cut the piece we are interested in from the source
        $src_img = ImageCreateTrueColor($src_w, $src_h);
        imagecopy($src_img, $src_image, 0, 0, $src_x, $src_y, $src_w, $src_h);
        // this one is used as temporary image
        $dst_img = ImageCreateTrueColor($dst_w, $dst_h);
        ImagePaletteCopy($dst_img, $src_img);
        $rX = $src_w / $dst_w;
        $rY = $src_h / $dst_h;
        $w = 0;
        for ($y = 0; $y < $dst_h; $y++)  {
            $ow = $w; $w = round(($y + 1) * $rY);
            $t = 0;
            for ($x = 0; $x < $dst_w; $x++)  {
                $r = $g = $b = 0; $a = 0;
                $ot = $t; $t = round(($x + 1) * $rX);
                for ($u = 0; $u < ($w - $ow); $u++)  {
                    for ($p = 0; $p < ($t - $ot); $p++)  {
                        $c = ImageColorsForIndex($src_img, ImageColorAt($src_img, $ot + $p, $ow + $u));
                        $r += $c['red'];
                        $g += $c['green'];
                        $b += $c['blue'];
                        $a++;
                    }
                }
                ImageSetPixel($dst_img, $x, $y, ImageColorClosest($dst_img, $r / $a, $g / $a, $b / $a));
            }
        }
        // apply the temp image over the returned image and use the destination x,y coordinates
        imagecopy($dst_image, $dst_img, $dst_x, $dst_y, 0, 0, $dst_w, $dst_h);
        // we should return true since ImageCopyResampled/ImageCopyResized do it
        return true;
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=83292&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=83292&page=function.imagecopyresampled&vote=down "Vote down!")

1


[**_mattura gmail com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#83292) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#83292)

**17 years ago**

`Here's a little function I wrote to resize images to a maximum dimension - based on what facebook does in the galleries. You put in a source, destination and a maximum dimension in pixels (eg 300), and for example if the image is long and thin, the longest edge will be 300px, yet the image retains proportions. A square image will become 300x300, a 6x4 (landscape) will become 300x200, a 4x6 (portrait) - 200x300 etc.
It works on jpg images, but other formats can easily be added.
<?php
function createThumb($spath, $dpath, $maxd) {
$src=@imagecreatefromjpeg($spath);
if (!$src) {return false;} else {
$srcw=imagesx($src);
$srch=imagesy($src);
if ($srcw<$srch) {$height=$maxd;$width=floor($srcw*$height/$srch);}
else {$width=$maxd;$height=floor($srch*$width/$srcw);}
if ($width>$srcw && $height>$srch) {$width=$srcw;$height=$srch;}  //if image is actually smaller than you want, leave small (remove this line to resize anyway)
$thumb=imagecreatetruecolor($width, $height);
if ($height<100) {imagecopyresized($thumb, $src, 0, 0, 0, 0, $width, $height, imagesx($src), imagesy($src));}
else {imagecopyresampled($thumb, $src, 0, 0, 0, 0, $width, $height, imagesx($src), imagesy($src));}
imagejpeg($thumb, $dpath);
return true;
}
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=79119&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=79119&page=function.imagecopyresampled&vote=down "Vote down!")

1


[**_Dave McCourt_**](https://www.php.net/manual/en/function.imagecopyresampled.php#79119) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#79119)

**17 years ago**

`This function is taken from lots of web sources so thanks to all for posting. It creates square or landscape thumbnails from .jpgs  from either portait or landscape original images. I decide in advance which way I want the thumbs to display for consistency. I usually sharpen the images as well post-upload, to save on server resources. I can post this code if anyone wants it. I hope this helps someone...
    # create thumbnails from jpgs
    # usage:
    # create_jpgthumb(uploaded file, final file (with path), thumb height, thumb width, jpg quality, scale thumb (true) or fixed size (false);
    function create_jpgthumb($original, $thumbnail, $max_width, $max_height, $quality, $scale = true) {

        list ($src_width, $src_height, $type, $w) = getimagesize($original);

        if (!$srcImage = @imagecreatefromjpeg($original)) {
            return false;
        }
        # image resizes to natural height and width
        if ($scale == true) {

            if ($src_width > $src_height ) {
                $thumb_width = $max_width;
                $thumb_height = floor($src_height * ($max_width / $src_width));
            } else if ($src_width < $src_height ) {
                $thumb_height = $max_height;
                $thumb_width = floor($src_width * ($max_height / $src_height));
            } else {
                $thumb_width = $max_height;
                $thumb_height = $max_height;
            }
            if (!@$destImage = imagecreatetruecolor($thumb_width, $thumb_height)) {
                return false;
            }

            if (!@imagecopyresampled($destImage, $srcImage, 0, 0, 0, 0, $thumb_width, $thumb_height, $src_width, $src_height)) {
                return false;
            }

        # image is fixed to supplied width and height and cropped
        } else if ($scale == false) {

            $ratio = $max_width / $max_height;

            # thumbnail is landscape
             if ($ratio > 1) {

                # uploaded pic is landscape
                if ($src_width > $src_height) {
                    $thumb_width = $max_width;
                    $thumb_height = ceil($max_width * ($src_height / $src_width));

                    if ($thumb_height > $max_width) {
                        $thumb_height = $max_width;
                        $thumb_width = ceil($max_width * ($src_width / $src_height));
                    }
                # uploaded pic is portrait
                } else {

                    $thumb_height = $max_width;
                    $thumb_width = ceil($max_width * ($src_height / $src_width));

                    if ($thumb_width > $max_width) {
                        $thumb_width = $max_width;
                        $thumb_height = ceil($max_width * ($src_height / $src_width));
                    }

                    $off_h = ($src_height - $src_width) / 2;

                }

                if (!@$destImage = imagecreatetruecolor($max_width, $max_height)) {
                    return false;
                }

                if (!@imagecopyresampled($destImage, $srcImage, 0, 0, 0, $off_h, $thumb_width, $thumb_height, $src_width, $src_height)) {
                    return false;
                }
            # thumbnail is square
             } else {

                if ($src_width > $src_height) {
                    $off_w = ($src_width - $src_height) / 2;
                    $off_h = 0;
                    $src_width = $src_height;
                } else if ($src_height > $src_width) {
                    $off_w = 0;
                    $off_h = ($src_height - $src_width) / 2;
                    $src_height = $src_width;
                } else {
                    $off_w = 0;
                    $off_h = 0;
                }
                if (!@$destImage = imagecreatetruecolor($max_width, $max_height)) {
                    return false;
                }

                if (!@imagecopyresampled($destImage, $srcImage, 0, 0, $off_w, $off_h, $max_width, $max_height, $src_width, $src_height)) {
                    return false;
                }
             }


        }

        @imagedestroy($srcImage);
        if (!@imageantialias($destImage, true)) {
            return false;
        }

        if (!@imagejpeg($destImage, $thumbnail, $quality)) {
            return false;
        }

        @imagedestroy($destImage);

        return true;
    }`

[up](https://www.php.net/manual/vote-note.php?id=114602&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114602&page=function.imagecopyresampled&vote=down "Vote down!")

3


[**_kazuya_**](https://www.php.net/manual/en/function.imagecopyresampled.php#114602) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#114602)

**11 years ago**

`<?php
$new_file = img_resize("./img/", "test.jpg","copy_test.jpg",300);
echo "<IMG src = '$new_file'>";
function img_resize($path,$tmp_name,$new_name,$new_width){
    if (!file_exists($path.$filename)){
        echo "file not found!";
        exit;
    }
    if (!is_writable($path)){
        echo "error:permission denied!";
        exit;
    }
    list($width, $height) = getimagesize($path . $tmp_name);
    $new_height = abs($new_width * $height / $width);
    $image_p = imagecreatetruecolor($new_width, $new_height);
    $image = imagecreatefromjpeg($path . $tmp_name);
    imagecopyresampled($image_p, $image, 0, 0, 0, 0,
                        $new_width, $new_height, $width, $height);
    imagejpeg($image_p, $path . $new_name);
    return $path.$new_name;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=54448&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=54448&page=function.imagecopyresampled&vote=down "Vote down!")

5


[**_Anonymous_**](https://www.php.net/manual/en/function.imagecopyresampled.php#54448) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#54448)

**20 years ago**

`It should be noted that the imagecopyresampled() function is much more blurry than Photoshop CS's default bicubic funtion. And looks similar to a blury version of Photoshop's bilinear function. The documentation fails to note which algorithm is used in resampling.`

[up](https://www.php.net/manual/vote-note.php?id=81898&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81898&page=function.imagecopyresampled&vote=down "Vote down!")

3


[**_bobbyboyojones at hotmail dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#81898) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#81898)

**17 years ago**

`I hated that enlarging an image resulted in giant pixels rather than a smoother look, so I wrote this function.  It takes longer, but gives a much nicer look.
<?php
function imagecopyresampledSMOOTH(&$dst_img, &$src_img, $dst_x, $dst_y, $src_x, $src_y, $dst_w, $dst_h, $src_w, $src_h, $mult=1.25){
    // don't use a $mult that's too close to an int or this function won't make much of a difference
    $tgt_w = round($src_w * $mult);
    $tgt_h = round($src_h * $mult);

    // using $mult <= 1 will make the current step w/h smaller (or the same), don't allow this, always resize by at least 1 pixel larger
    if($tgt_w <= $src_w){ $tgt_w += 1; }
    if($tgt_h <= $src_h){ $tgt_h += 1; }

    // if the current step w/h is larger than the final height, adjust it back to the final size
    // this check also makes it so that if we are doing a resize to smaller image, it happens in one step (since that's already smooth)
    if($tgt_w > $dst_w){ $tgt_w = $dst_w; }
    if($tgt_h > $dst_h){ $tgt_h = $dst_h; }
    $tmpImg = imagecreatetruecolor($tgt_w, $tgt_h);
    imagecopyresampled($tmpImg, $src_img, 0, 0, $src_x, $src_y, $tgt_w, $tgt_h, $src_w, $src_h);
    imagecopy($dst_img, $tmpImg, $dst_x, $dst_y, 0, 0, $tgt_w, $tgt_h);
    imagedestroy($tmpImg);
    // as long as the final w/h has not been reached, reep on resizing
    if($tgt_w < $dst_w OR $tgt_h < $dst_h){
        imagecopyresampledSMOOTH($dst_img, $dst_img, $dst_x, $dst_y, $dst_x, $dst_y, $dst_w, $dst_h, $tgt_w, $tgt_h, $mult);
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=90544&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90544&page=function.imagecopyresampled&vote=down "Vote down!")

3


[**_z3n666 at gmail dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#90544) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#90544)

**16 years ago**

`I was looking around and couldn't find a function that resizes images to any ratio without leaving a blank area, so i wrote this one. It's able to resize images to any size ratio, when the ratio is no match with the original it will crop proportional area on the original and resize it.
<?php
function _ckdir($fn) {
    if (strpos($fn,"/") !== false) {
        $p=substr($fn,0,strrpos($fn,"/"));
        if (!is_dir($p)) {
            _o("Mkdir: ".$p);
            mkdir($p,777,true);
        }
    }
}
function img_resizer($src,$quality,$w,$h,$saveas) {
    /* v2.5 with auto crop */
    $r=1;
    $e=strtolower(substr($src,strrpos($src,".")+1,3));
    if (($e == "jpg") || ($e == "peg")) {
        $OldImage=ImageCreateFromJpeg($src) or $r=0;
    } elseif ($e == "gif") {
        $OldImage=ImageCreateFromGif($src) or $r=0;
    } elseif ($e == "bmp") {
        $OldImage=ImageCreateFromwbmp($src) or $r=0;
    } elseif ($e == "png") {
        $OldImage=ImageCreateFromPng($src) or $r=0;
    } else {
        _o("Not a Valid Image! (".$e.") -- ".$src);$r=0;
    }
    if ($r) {
        list($width,$height)=getimagesize($src);
        // check if ratios match
        $_ratio=array($width/$height,$w/$h);
        if ($_ratio[0] != $_ratio[1]) { // crop image
            // find the right scale to use
            $_scale=min((float)($width/$w),(float)($height/$h));
            // coords to crop
            $cropX=(float)($width-($_scale*$w));
            $cropY=(float)($height-($_scale*$h));

            // cropped image size
            $cropW=(float)($width-$cropX);
            $cropH=(float)($height-$cropY);

            $crop=ImageCreateTrueColor($cropW,$cropH);
            // crop the middle part of the image to fit proportions
            ImageCopy(
                $crop,
                $OldImage,
                0,
                0,
                (int)($cropX/2),
                (int)($cropY/2),
                $cropW,
                $cropH
            );
        }

        // do the thumbnail
        $NewThumb=ImageCreateTrueColor($w,$h);
        if (isset($crop)) { // been cropped
            ImageCopyResampled(
                $NewThumb,
                $crop,
                0,
                0,
                0,
                0,
                $w,
                $h,
                $cropW,
                $cropH
            );
            ImageDestroy($crop);
        } else { // ratio match, regular resize
            ImageCopyResampled(
                $NewThumb,
                $OldImage,
                0,
                0,
                0,
                0,
                $w,
                $h,
                $width,
                $height
            );
        }
        _ckdir($saveas);
        ImageJpeg($NewThumb,$saveas,$quality);
        ImageDestroy($NewThumb);
        ImageDestroy($OldImage);
    }
    return $r;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=90038&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90038&page=function.imagecopyresampled&vote=down "Vote down!")

3


[**_satanas147 at gmail dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#90038) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#90038)

**16 years ago**

`Another add-on to previous php5 class for thumbnail (with a merge of Matt and Zorro's proposals).
This is dedicated to generate thumbnail on the fly for a webpage using the subclass thumbnail.
It saves the generated thumb as myimage_tn, in the same directory.
I'm quite new with php5, so I think this could be optimized, but it seems to work fine.
<?php
// Imaging
class imaging
{
    // Variables
    private $img_input;
    private $img_output;
    private $img_src;
    private $format;
    private $quality = 80;
    private $x_input;
    private $y_input;
    private $x_output;
    private $y_output;
    private $resize;
    // Set image
    public function set_img($img)
    {
        // Find format
        $ext = strtoupper(pathinfo($img, PATHINFO_EXTENSION));
        // JPEG image
        if(is_file($img) && ($ext == "JPG" OR $ext == "JPEG"))
        {
            $this->format = $ext;
            $this->img_input = ImageCreateFromJPEG($img);
            $this->img_src = $img;
        }
        // PNG image
        elseif(is_file($img) && $ext == "PNG")
        {
            $this->format = $ext;
            $this->img_input = ImageCreateFromPNG($img);
            $this->img_src = $img;
        }
        // GIF image
        elseif(is_file($img) && $ext == "GIF")
        {
            $this->format = $ext;
            $this->img_input = ImageCreateFromGIF($img);
            $this->img_src = $img;
        }
        // Get dimensions
        $this->x_input = imagesx($this->img_input);
        $this->y_input = imagesy($this->img_input);
    }
    // Set maximum image size (pixels)
    public function set_size($max_x = 100,$max_y = 100)
    {
        // Resize
        if($this->x_input > $max_x || $this->y_input > $max_y)
        {
            $a= $max_x / $max_y;
            $b= $this->x_input / $this->y_input;
            if ($a<$b)
            {
                $this->x_output = $max_x;
                $this->y_output = ($max_x / $this->x_input) * $this->y_input;
            }
            else
            {
                $this->y_output = $max_y;
                $this->x_output = ($max_y / $this->y_input) * $this->x_input;
            }
            // Ready
            $this->resize = TRUE;
        }
        // Don't resize
        else { $this->resize = FALSE; }
    }
    // Set image quality (JPEG only)
    public function set_quality($quality)
    {
        if(is_int($quality))
        {
            $this->quality = $quality;
        }
    }
    // Save image
    public function save_img($path)
    {
        // Resize
        if($this->resize)
        {
            $this->img_output = ImageCreateTrueColor($this->x_output, $this->y_output);
            ImageCopyResampled($this->img_output, $this->img_input, 0, 0, 0, 0, $this->x_output, $this->y_output, $this->x_input, $this->y_input);
        }
        // Save JPEG
        if($this->format == "JPG" OR $this->format == "JPEG")
        {
            if($this->resize) { imageJPEG($this->img_output, $path, $this->quality); }
            else { copy($this->img_src, $path); }
        }
        // Save PNG
        elseif($this->format == "PNG")
        {
            if($this->resize) { imagePNG($this->img_output, $path); }
            else { copy($this->img_src, $path); }
        }
        // Save GIF
        elseif($this->format == "GIF")
        {
            if($this->resize) { imageGIF($this->img_output, $path); }
            else { copy($this->img_src, $path); }
        }
    }
    // Get width
    public function get_width()
    {
        return $this->x_input;
    }
    // Get height
    public function get_height()
    {
        return $this->y_input;
    }
    // Clear image cache
    public function clear_cache()
    {
        @ImageDestroy($this->img_input);
        @ImageDestroy($this->img_output);
    }
}
class thumbnail extends imaging {
    private $image;
    private $width;
    private $height;

    function __construct($image,$width,$height) {
parent::set_img($image);
parent::set_quality(80);
parent::set_size($width,$height);
            $this->thumbnail= pathinfo($image, PATHINFO_DIRNAME).pathinfo($image, PATHINFO_FILENAME).'_tn.'.pathinfo($image, PATHINFO_EXTENSION);
parent::save_img($this->thumbnail);
parent::clear_cache();
        }
    function __toString() {
            return $this->thumbnail;
    }
}
********
* DEMO *
********
$thumb = new thumbnail('./image_dir/sub_dir/myimage.jpg',100,100);
echo '<img src=\''.$thumb.'\' alt=\'myimage\' title=\'myimage\'/>';
    ?>`

[up](https://www.php.net/manual/vote-note.php?id=114758&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114758&page=function.imagecopyresampled&vote=down "Vote down!")

1


[**_julien at go-on-web dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#114758) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#114758)

**11 years ago**

`Windows does not accept floating width and height...
So, in "Example #2 Resampling an image proportionally", prefer :
<?php
if ($width/$height > $ratio_orig) {
$width = round( $height*$ratio_orig );
} else {
$height = round( $width/$ratio_orig );
}
?>
(used "round")
otherwise your image wont be resized.`

[up](https://www.php.net/manual/vote-note.php?id=78239&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78239&page=function.imagecopyresampled&vote=down "Vote down!")

1


[**_tim dot daldini at gmail dot be_**](https://www.php.net/manual/en/function.imagecopyresampled.php#78239) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#78239)

**18 years ago**

`Tim's function is a whole lot faster, however, the quality setting doesnt seem right since resizing very big images doesnt affect quality of the resulting thumbnails that much on quality 1 for example.
Anyone has figured out how to use a more correct quality setting by comparing image surfaces (for example) basing on Tim's function?
images with a total of 10Megapixels that contain 5Megapixels when resized should use the same quality setting like images that contain 1Megapixels but only 0.5 when resized.
Not hard to understand, but the memoryload would be a lot lower if the function could decide to use a setting of quality 1 automatically when resizing big images to small thumbnails. This would be handy especially when using the function for images of various sizes in the same application.`

[up](https://www.php.net/manual/vote-note.php?id=94251&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94251&page=function.imagecopyresampled&vote=down "Vote down!")

2


[**_seifer at loveletslive dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#94251) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#94251)

**15 years ago**

`Okay so I saw that others have posted this already but I just messed around and made it so figured I would share it.
Mine works, not to say others don't, I haven't tested them.
This function creates a thumbnail of the specfied size.
If the thumbnail is a different ration it will automatically crop the center of the source image.
It works if the source image is bigger or smaller than the desired "cropped thumbnail."
Here is the code...
<?php
function CroppedThumbnail($imgSrc,$thumbnail_width,$thumbnail_height) { //$imgSrc is a FILE - Returns an image resource.
    //getting the image dimensions
    list($width_orig, $height_orig) = getimagesize($imgSrc);
    $myImage = imagecreatefromjpeg($imgSrc);
    $ratio_orig = $width_orig/$height_orig;

    if ($thumbnail_width/$thumbnail_height > $ratio_orig) {
       $new_height = $thumbnail_width/$ratio_orig;
       $new_width = $thumbnail_width;
    } else {
       $new_width = $thumbnail_height*$ratio_orig;
       $new_height = $thumbnail_height;
    }

    $x_mid = $new_width/2;  //horizontal middle
    $y_mid = $new_height/2; //vertical middle

    $process = imagecreatetruecolor(round($new_width), round($new_height));

    imagecopyresampled($process, $myImage, 0, 0, 0, 0, $new_width, $new_height, $width_orig, $height_orig);
    $thumb = imagecreatetruecolor($thumbnail_width, $thumbnail_height);
    imagecopyresampled($thumb, $process, 0, 0, ($x_mid-($thumbnail_width/2)), ($y_mid-($thumbnail_height/2)), $thumbnail_width, $thumbnail_height, $thumbnail_width, $thumbnail_height);
    imagedestroy($process);
    imagedestroy($myImage);
    return $thumb;
}
//Create the thumbnail
$newThumb = CroppedThumbnail("MyImageName.jpg",75,100);
// And display the image...
header('Content-type: image/jpeg');
imagejpeg($newThumb);
?>`

[up](https://www.php.net/manual/vote-note.php?id=110592&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110592&page=function.imagecopyresampled&vote=down "Vote down!")

1


[**_alex-thennstaett-remove at gmx dot net_**](https://www.php.net/manual/en/function.imagecopyresampled.php#110592) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#110592)

**12 years ago**

`Having updated GD-Library from 2.0.35-r1 to 2.0.35-r3 using negative numbers for $dstX or $dstY started to produce unpredictable results, such as inserting shrinked images and enlarging $dstH or $dstW all by itself. While it did work fine previously, one should avoid using or calculating negative numbers for imagecopyresampled from the beginning.`

[up](https://www.php.net/manual/vote-note.php?id=126845&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126845&page=function.imagecopyresampled&vote=down "Vote down!")

0


[**_mark at manngo dot net_**](https://www.php.net/manual/en/function.imagecopyresampled.php#126845) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#126845)

**3 years ago**

`Note that as of PHP 8.1, you will get deprecated errors if the arguments are floating point. You will save yourself a lot of angst if you cast the arguments:
<?php
    imagecopyresampled(
        $dst_image, $src_image,
        (int) $dst_x,        (int) $dst_y,
        (int) $src_x,        (int) $src_y,
        (int) $dst_width,    (int) $dst_height,
        (int) $src_width,    (int) $src_height
    );
?>
You could also have rounded them off, but I think casting them is truer to the original behaviour.`

[up](https://www.php.net/manual/vote-note.php?id=113009&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113009&page=function.imagecopyresampled&vote=down "Vote down!")

0


[**_sam at durosoft.com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#113009) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#113009)

**12 years ago**

`The ultimate smart image re-sizing routine. You provide the original image, and a desired width and/or height. The function will intelligently re-size the original image to fit, centered, within the specified dimensions. Either width or height can be omitted to have the re-size "lock" only on width or height. Fantastic for thumbnail generation. Designed to work with PNG's.
function resize_image_smart($orig, $dest_width=null, $dest_height=null)
{
$orig_width = imagesx($orig);
$orig_height = imagesy($orig);
$vertical_offset = 0;
$horizontal_offset = 0;
if($dest_width == null)
{
    if($dest_height == null)
    {
      die('$dest_width and $dest_height cant both be null!');
    }
    // height is locked
    $dest_width = $dest_height * $orig_width / $orig_height;
} else {
    if($dest_height == null)
    {
      // width is locked
      $dest_height = $dest_width * $orig_height / $orig_width;
    } else {
      // both dimensions are locked
      $vertical_offset = $dest_height - ($orig_height * $dest_width) / $orig_width;
      $horizontal_offset = $dest_width - ($dest_height * $orig_width) / $orig_height;
      if($vertical_offset < 0) $vertical_offset = 0;
      if($horizontal_offset < 0) $horizontal_offset = 0;
    }
}
$img = imagecreatetruecolor($dest_width, $dest_height);
imagesavealpha($img, true);
imagealphablending($img, false);
$transparent = imagecolorallocatealpha($img, 0, 0, 0, 127);
imagefill($img, 0, 0, $transparent);
imagecopyresampled($img, $orig, round($horizontal_offset / 2),
                                  round($vertical_offset / 2),
                                  0,
                                  0,
                                  round($dest_width - $horizontal_offset),
                                  round($dest_height - $vertical_offset),
                                  $orig_width,
                                  $orig_height);
return $img;
}`

[up](https://www.php.net/manual/vote-note.php?id=98560&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=98560&page=function.imagecopyresampled&vote=down "Vote down!")

2


[**_guru\_boy87 at hotmail dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#98560) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#98560)

**15 years ago**

`Function to resize an image.
<?php
function resizeImage($originalImage,$toWidth,$toHeight)
{
    list($width, $height) = getimagesize($originalImage);
    $xscale=$width/$toWidth;
    $yscale=$height/$toHeight;
    if ($yscale>$xscale){
        $new_width = round($width * (1/$yscale));
        $new_height = round($height * (1/$yscale));
    }
    else {
        $new_width = round($width * (1/$xscale));
        $new_height = round($height * (1/$xscale));
    }


    $imageResized = imagecreatetruecolor($new_width, $new_height);
    $imageTmp     = imagecreatefromjpeg ($originalImage);
    imagecopyresampled($imageResized, $imageTmp, 0, 0, 0, 0, $new_width, $new_height, $width, $height);
    return $imageResized;

}
?>`

[up](https://www.php.net/manual/vote-note.php?id=89987&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=89987&page=function.imagecopyresampled&vote=down "Vote down!")

2


[**_zuegs_**](https://www.php.net/manual/en/function.imagecopyresampled.php#89987) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#89987)

**16 years ago**

`Resampling GIFs and retain transparency dosen't work always, as dependent on the resample factor the resulting resampled image has some pattern-noise that prevents "imagegif" to find all the transparent-pixels.
One way to fix this, is to reset all pixels with high alpha to full-transparent:
<?php
// load/create images
$img_src=imagecreatefromgif($g_srcfile);
$img_dst=imagecreatetruecolor($g_iw,$g_ih);
imagealphablending($img_dst, false);
// get and reallocate transparency-color
$transindex = imagecolortransparent($img_src);
if($transindex >= 0) {
$transcol = imagecolorsforindex($img_src, $transindex);
$transindex = imagecolorallocatealpha($img_dst, $transcol['red'], $transcol['green'], $transcol['blue'], 127);
imagefill($img_dst, 0, 0, $transindex);
}
// resample
imagecopyresampled($img_dst, $img_src, 0, 0, 0, 0, $g_iw, $g_ih, $g_is[0], $g_is[1]);
// restore transparency
if($transindex >= 0) {
imagecolortransparent($img_dst, $transindex);
for($y=0; $y<$g_ih; ++$y)
    for($x=0; $x<$g_iw; ++$x)
      if(((imagecolorat($img_dst, $x, $y)>>24) & 0x7F) >= 100) imagesetpixel($img_dst, $x, $y, $transindex);
// save GIF
imagetruecolortopalette($img_dst, true, 255);
imagesavealpha($img_dst, false);
imagegif($img_dst, $g_dstfile);
imagedestroy($img_dst);
?>`

[up](https://www.php.net/manual/vote-note.php?id=88263&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88263&page=function.imagecopyresampled&vote=down "Vote down!")

1


[**_Warren_**](https://www.php.net/manual/en/function.imagecopyresampled.php#88263) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#88263)

**16 years ago**

`This is a function I wrote for making thumbnails -  it will accept a source *image resource* and destination *path*, plus the max dimension and whether the thumbnail should be square.
I chose to accept a resource as the source to make it a bit more efficient to create multiple sizes. For example:
<?php
$src_im=@imagecreatefromjpeg($pathtofile);
$large = resize($src_im,$destination_large,1024);
@imagedestroy($src_im);
$medium = resize($large,$destination_medium,500);
@imagedestroy($large);
$small = resize($medium,$destination_small,125);
@imagedestroy($medium);
$square = resize($small,$destination_square,75,TRUE);
@imagedestroy($small);
@imagedestroy($square);
function resize($src_im, $dpath, $maxd, $square=false) {
    $src_width = imagesx($src_im);
    $src_height = imagesy($src_im);
    $src_w=$src_width;
    $src_h=$src_height;
    $src_x=0;
    $src_y=0;
    if($square){
        $dst_w = $maxd;
        $dst_h = $maxd;
        if($src_width>$src_height){
            $src_x = ceil(($src_width-$src_height)/2);
            $src_w=$src_height;
            $src_h=$src_height;
        }else{
            $src_y = ceil(($src_height-$src_width)/2);
            $src_w=$src_width;
            $src_h=$src_width;
        }
    }else{
        if($src_width>$src_height){
            $dst_w=$maxd;
            $dst_h=floor($src_height*($dst_w/$src_width));
        }else{
            $dst_h=$maxd;
            $dst_w=floor($src_width*($dst_h/$src_height));
        }
    }
    $dst_im=@imagecreatetruecolor($dst_w,$dst_h);
    @imagecopyresampled($dst_im, $src_im, 0, 0, $src_x, $src_y, $dst_w, $dst_h, $src_w, $src_h);
    @imagejpeg($dst_im,$dpath);
    return $dst_im;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=93190&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93190&page=function.imagecopyresampled&vote=down "Vote down!")

0


[**_asgaroth dot belem at gmail dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#93190) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#93190)

**16 years ago**

`In case you are having trouble ( like I did ) and getting some kind of noise in the resampled image.
then changing imagecopyresampled() with imagecopyresized()  removes the noise, found that here: [http://bugs.php.net/bug.php?id=45030](http://bugs.php.net/bug.php?id=45030)
Do not ask me why. but it works.`

[up](https://www.php.net/manual/vote-note.php?id=93166&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93166&page=function.imagecopyresampled&vote=down "Vote down!")

0


[**_asgaroth dot belem at gmail dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#93166) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#93166)

**16 years ago**

`About preserving the  transparency when resizing PNGs this was the only thing that worked for me:
<?php imagealphablending($new_watermark, false);
        $color = imagecolortransparent($new_watermark, imagecolorallocatealpha($new_watermark, 0, 0, 0, 127));
        imagefill($new_watermark, 0, 0, $color);
        imagesavealpha($new_watermark, true);
        imagecopyresampled($new_watermark, $watermark, 0, 0, 0, 0, $new_watermark_width, $new_watermark_height, imagesx($watermark),imagesy($watermark));
?>
Tried without success:
<?php imagealphablending($new_watermark, false);
        $color = imagecolortransparent($new_watermark, imagecolorallocate($new_watermark, 0, 0, 0));
        imagefill($new_watermark, 0, 0, $color);
        imagesavealpha($new_watermark, true);
        imagecopyresampled($new_watermark, $watermark, 0, 0, 0, 0, $new_watermark_width, $new_watermark_height, imagesx($watermark),imagesy($watermark));
?>
hope it helps someone.`

[up](https://www.php.net/manual/vote-note.php?id=84516&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84516&page=function.imagecopyresampled&vote=down "Vote down!")

1


[**_swizec at swizec dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#84516) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#84516)

**17 years ago**

`Wrote a function for sanitising user uploaded images. It saves the native image in size roughly 800x600 so it still fits on most screens when opened, makes a desired size thumbnail and turns all images into high quality jpegs for smaller bandwidth use.
Thumbnails are made in a similar way a designer would make them in photoshop, first resize the most troublesome dimension to desired size, then crop the rest out so the image retains proportions and most of it ends up in the thumbnail.
<?php
// $image is $_FILES[ <image name> ]
// $imageId is the id used in a database or wherever for this image
// $thumbWidth and $thumbHeight are desired dimensions for the thumbnail
function processImage( $image, $imageId, $thumbWidth, $thumbHeight )
{
    $type = $image[ 'type' ];
    $galleryPath = 'images/collection/';

    if ( strpos( $type, 'image/' ) === FALSE )
    { // not an image
        return FALSE;
    }
    $type = str_replace( 'image/', '', $type );
    $createFunc = 'imagecreatefrom' . $type;

    $im = $createFunc( $image[ 'tmp_name' ] );

    $size = getimagesize( $image[ 'tmp_name' ] );

    $w = $size[ 0 ];
    $h = $size[ 1 ];
    if ( $w > 800 || $h > 600 )
    { // we make sure the image isn't too huge
        if ( $w > 800 )
        {
            $nw = 800;
            $nh = ceil( $nw*($h/$w) );
        }elseif( $h > 600 )
        {
            $nh = 600;
            $nw = ceil( $nh*($w/$h) );
        }

        $im2 = imagecreatetruecolor( $nw, $nh );
        imagecopyresampled( $im2, $im, 0, 0, 0, 0, $nw, $nh, $w, $h );
        imagedestroy( $im );

        $im = $im2;
        $w = $nw;
        $h = $nh;
    }

    // create thumbnail
    $tw = $thumbWidth;
    $th = $thumbHeight;
    $imT = imagecreatetruecolor( $tw, $th );

    if ( $tw/$th > $th/$tw )
    { // wider
        $tmph = $h*($tw/$w);
        $temp = imagecreatetruecolor( $tw, $tmph );
        imagecopyresampled( $temp, $im, 0, 0, 0, 0, $tw, $tmph, $w, $h ); // resize to width
        imagecopyresampled( $imT, $temp, 0, 0, 0, $tmph/2-$th/2, $tw, $th, $tw, $th ); // crop
        imagedestroy( $temp );
    }else
    { // taller
        $tmpw = $w*($th/$h );
        $imT = imagecreatetruecolor( $tmpw, $th );
        imagecopyresampled( $imT, $im, 0, 0, 0, 0, $tmpw, $h, $w, $h ); // resize to height
        imagecopyresampled( $imT, $temp, 0, 0, $tmpw/2-$tw/2, 0, $tw, $th, $tw, $th ); // crop
        imagedestroy( $temp );
    }

    // save the image
    imagejpeg( $im, $galleryPath . $imgid . '.jpg', 100 );
    imagejpeg( $imT, $galleryPath . $imgid . '_thumb.jpg', 100 );
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=81856&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81856&page=function.imagecopyresampled&vote=down "Vote down!")

1


[**_arnar at netvistun dot is_**](https://www.php.net/manual/en/function.imagecopyresampled.php#81856) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#81856)

**17 years ago**

`A small thumb script. Lets you specify max height and width. The thumb will always be of a rectangular shape while the image itself retains it's proportions. Very clean.
<?php
// The file
$filename = 'a.jpg';
// Set a maximum height and width
$width = 80;
$height = 80;
$thumbsize = 80;
// Content type
header('Content-type: image/jpeg');
// Get new dimensions
list($width_orig, $height_orig) = getimagesize($filename);
$ratio_orig = $width_orig/$height_orig;
if ($width/$height > $ratio_orig) {
$width = $height*$ratio_orig;
} else {
$height = $width/$ratio_orig;
}
// Resample
$image_p = imagecreatetruecolor($thumbsize, $thumbsize);
$image = imagecreatefromjpeg($filename);
imagecopyresampled($image_p, $image, -($width/2) + ($thumbsize/2), -($height/2) + ($thumbsize/2), 0, 0, $width, $height, $width_orig, $height_orig);
// Output
imagejpeg($image_p, null, 100);
?>`

[up](https://www.php.net/manual/vote-note.php?id=87881&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87881&page=function.imagecopyresampled&vote=down "Vote down!")

0


[**_MBorgPL at gmail dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#87881) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#87881)

**16 years ago**

`Another addition to zorroswordsman at gmail dot com's resize class.
The function takes $_FILES['sent_image'] as 1st parameter. The 2nd is complete destination path.
It only moves images.
It returns destination path if succeeded, and false if any error occurred.
<?php
public function move_image($tmp_img, $dest_img)
{
    //verifies if the uploaded file is an image
    if (strpos($tmp_img['type'], 'image') !== false)
        {
        //moves the uploaded file into the destination place
        if (move_uploaded_file($tmp_img['tmp_name'], $dest_img)) {
            return $dest_img;
        }
    }
    return false;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=87866&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87866&page=function.imagecopyresampled&vote=down "Vote down!")

0


[**_MBorg\_PL_**](https://www.php.net/manual/en/function.imagecopyresampled.php#87866) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#87866)

**16 years ago**

`Another tiny ammendment to zorroswordsman at gmail dot com's resize class AND matt at rees-jenkins dot co dot uk addition. The class may resize to different width and height not only same ones:
<?php
// Set maximum image size (pixels)
public function set_size($max_x = 100,$max_y = 100)
{

    // Resize
    if($this->x_input > $max_x || $this->y_input > $max_y)
    {
        $a= $max_x / $max_y;
        $b= $this->x_input / $this->y_input;

        if ($a<$b)
        {
            $this->x_output = $max_x;
            $this->y_output = ($max_x / $this->x_input) * $this->y_input;
        }
        else
        {
            $this->y_output = $max_y;
            $this->x_output = ($max_y / $this->y_input) * $this->x_input;
        }
        // Ready

        $this->resize = TRUE;

    }

    // Don't resize
    else { $this->resize = FALSE; }

}
?>
And the use of the class is now:
<?php
##### DEMO #####
// Image
$src = "myimage.jpg";
// Begin
$img = new imaging;
$img->set_img($src);
$img->set_quality(80);
// Small thumbnail
$img->set_size(250,150);
$img->save_img("small_250x150_" . $src);
// Baby thumbnail
$img->set_size(50,250);
$img->save_img("baby_50x250_" . $src);
// Finalize
$img->clear_cache();
?>`

[up](https://www.php.net/manual/vote-note.php?id=86344&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86344&page=function.imagecopyresampled&vote=down "Vote down!")

0


[**_matt at rees-jenkins dot co dot uk_**](https://www.php.net/manual/en/function.imagecopyresampled.php#86344) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#86344)

**17 years ago**

`A tiny ammendment to zorroswordsman at gmail dot com's resize class. It was only resizing if both the width AND height where greater than the desired size. This should fix it:
<?php
// Set maximum image size (pixels)
function set_size($size = 100)
{
    // Resize
    if($this->x_input > $size || $this->y_input > $size)
    {
        // Wide
        if($this->x_input >= $this->y_input)
        {
            $this->x_output = $size;
            $this->y_output = ($this->x_output / $this->x_input) * $this->y_input;
        }
        // Tall
        else
        {
            $this->y_output = $size;
            $this->x_output = ($this->y_output / $this->y_input) * $this->x_input;
        }
        // Ready
        $this->resize = TRUE;
    }
    // Don't resize
    else { $this->resize = FALSE; }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=77612&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77612&page=function.imagecopyresampled&vote=down "Vote down!")

1


[**_eblejr AT phrebh DOT com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#77612) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#77612)

**18 years ago**

`Tim's code is fast, but if you're trying to put resampled images anywhere but in the top-left corner, it doesn't work.`

[up](https://www.php.net/manual/vote-note.php?id=85038&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85038&page=function.imagecopyresampled&vote=down "Vote down!")

0


[**_crash_**](https://www.php.net/manual/en/function.imagecopyresampled.php#85038) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#85038)

**17 years ago**

`The suggestion of converting a gif to a png to retain transparency was useful. However the steps used to maintain the transparency work for a gif as well, so the conversion step is not necessary. Just do everything the same, and save as a gif anyway. i.e.
<?php
$g_iw is new image width
$g_ih is new image height
$img_src=imagecreatefromgif($g_srcfile);
$img_dst=imagecreatetruecolor($g_iw,$g_ih);
//preserve alpha
imagecolortransparent($img_dst, imagecolorallocate($img_dst, 0, 0, 0));
imagealphablending($img_dst, false);
imagesavealpha($img_dst, true);
imagecopyresampled($img_dst, $img_src, 0, 0, 0, 0, $g_iw, $g_ih, $g_is[0], $g_is[1]);
imagegif($img_dst, $g_dstfile);
imagedestroy($img_dst);
?>`

[up](https://www.php.net/manual/vote-note.php?id=75258&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75258&page=function.imagecopyresampled&vote=down "Vote down!")

1


[**_rich at corephp dot co dot uk_**](https://www.php.net/manual/en/function.imagecopyresampled.php#75258) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#75258)

**18 years ago**

`Be wary of this function when resizing images to make them *larger* than the original due to the memory consumption rate. For example a 200KB JPEG file (1024x768) will take up 4MB of memory when loaded, but when resampled to twice the the size the memory use jumps to 20.1MB. imagecopyresized does the same. Allow approx. 5 bytes per *pixel* for memory allowance when dealing with true colour images.`

[up](https://www.php.net/manual/vote-note.php?id=81633&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81633&page=function.imagecopyresampled&vote=down "Vote down!")

0


[**_rayg at daylongraphics dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#81633) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#81633)

**17 years ago**

`Here's a simple function to resample one JPEG imagefile to another while keeping aspect ratio of the source within the destination's dimensions. You can also tune the allowable distortion if you end up making too many thumbnails with thin blank areas around them. Should work when enlarging images too. Function returns true if it worked, false if not.
function resample_picfile($src, $dst, $w, $h)
{
    // If distortion stretching is within the range below,
    // then let image be distorted.
    $lowend = 0.8;
    $highend = 1.25;
    $src_img = imagecreatefromjpeg($src);
    if($src_img)
    {
        $dst_img = ImageCreateTrueColor($w, $h);
        /* if you don't want aspect-preserved images
to have a black bkgnd, fill $dst_img with the color of your choice here.
        */
        if($dst_img)
        {
            $src_w = imageSX($src_img);
            $src_h = imageSY($src_img);
            $scaleX = (float)$w / $src_w;
            $scaleY = (float)$h / $src_h;
            $scale = min($scaleX, $scaleY);
            $dstW = $w;
            $dstH = $h;
            $dstX = $dstY = 0;
            $scaleR = $scaleX / $scaleY;
            if($scaleR < $lowend || $scaleR > $highend)
            {
                $dstW = (int)($scale * $src_w + 0.5);
                $dstH = (int)($scale * $src_h + 0.5);
                // Keep pic centered in frame.
                $dstX = (int)(0.5 * ($w - $dstW));
                $dstY = (int)(0.5 * ($h - $dstH));
            }

            imagecopyresampled(
                $dst_img, $src_img, $dstX, $dstY, 0, 0,
                $dstW, $dstH, $src_w, $src_h);
            imagejpeg($dst_img, $dst);
            imagedestroy($dst_img);
        }
        imagedestroy($src_img);
        return file_exists($dst);
    }
    return false;
}`

[up](https://www.php.net/manual/vote-note.php?id=79297&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=79297&page=function.imagecopyresampled&vote=down "Vote down!")

0


[**_matt1walsh DESPAMMER gmail dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#79297) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#79297)

**17 years ago**

`None of the stuff I've seen for resizing transparent GIFs works consistently and yields a good image. The hack I thought of is silly, but it works okay -- convert GIF to PNG. This worked for me.
$g_iw is new image width
$g_ih is new image height
$img_src=imagecreatefromgif($g_srcfile);
$img_dst=imagecreatetruecolor($g_iw,$g_ih);
//preserve alpha
imagecolortransparent($img_dst, imagecolorallocate($img_dst, 0, 0, 0));
imagealphablending($img_dst, false);
imagesavealpha($img_dst, true);
imagecopyresampled($img_dst, $img_src, 0, 0, 0, 0, $g_iw, $g_ih, $g_is[0], $g_is[1]);
imagepng($img_dst, $g_dstfile);
imagedestroy($img_dst);`

[up](https://www.php.net/manual/vote-note.php?id=94221&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94221&page=function.imagecopyresampled&vote=down "Vote down!")

 -2


[**_michael at heymichael dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#94221) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#94221)

**15 years ago**

`imagecopyresampled() works amazingly well, but here is something NOT to try with it:
The resize routine I wrote looks for pixel widths, and resizes images based on the notion that if their widths and heights are too big, so are their byte sizes. It worked out well at first.
But when I saw huge byte-size images slipping through beneath my 1000px-wide benchmark, I figured I'd subject the smaller-width images to resizing if their filesize() exceeded 100K.
The idea was that I'd "resize" them keeping their original widths and heights (i.e. in (1) below, $newW = $oldW, $newH = $oldH), and letting the "75" at (2) below reduce the byte size.
DON'T try that. imagecopyresampled() will lock up the server trying to resize an 800px-wide image to a "new" width of 800px. (I caught that on my Windows server before ever putting it on the destination Linux server, so take that with a grain of salt.)
I got around it by making $newW = ($picW * 0.99), etc. You get the byte-size reduction you want without locking up.
(1) imagecopyresampled($image_p, $image, 0, 0, 0, 0, $newW, $newH, $picW, $picH);
(2) imagejpeg($image_p, $theFile, 75);`

[up](https://www.php.net/manual/vote-note.php?id=61169&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=61169&page=function.imagecopyresampled&vote=down "Vote down!")

0


[**_areddan at silverarm dot ie_**](https://www.php.net/manual/en/function.imagecopyresampled.php#61169) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#61169)

**19 years ago**

`<?php
// The file
$filein = ''; // File in
$fileout = 'ttt.gif'; // Fileout - optional
$imagethumbsize_w = 100; // thumbnail size (area cropped in middle of image)
$imagethumbsize_h = 75; // thumbnail size (area cropped in middle of image)
resize_then_crop( $filein,$fileout,$imagethumbsize_w,
$imagethumbsize_h,/*rgb*/"255","255","255");
//Author Alan Reddan Silverarm Solutions
//Date 27/01/2005
//Function that works well with images.
//It takes the image and reduces its size to best fit. i.e If you have an image
//that is 200 X 100 and you want a thumbnail of 75 X 50,
//it first resizes the image to 100 X 50
//and then takes out a portion 75 X 50 from then center of the input image.
//So loads of image information is retained.
//The corollary also holds if your input image is 100 X 200
//it first resizes image to 75 X 150 and then takes out a
//portion 75 X 75 from the centre
// The advantage here is that function decides on whether
//resize is by width or height itself.
//it also decides whether to use the height or the width as the base start point
//in the case that athumbnail is rectangular
function resize_then_crop( $filein,$fileout,
$imagethumbsize_w,$imagethumbsize_h,$red,$green,$blue)
{
// Get new dimensions
list($width, $height) = getimagesize($filein);
$new_width = $width * $percent;
$new_height = $height * $percent;
if(preg_match("/.jpg/i", "$filein"))
{
       $format = 'image/jpeg';
}
if (preg_match("/.gif/i", "$filein"))
{
       $format = 'image/gif';
}
if(preg_match("/.png/i", "$filein"))
{
       $format = 'image/png';
}

       switch($format)
       {
           case 'image/jpeg':
           $image = imagecreatefromjpeg($filein);
           break;
           case 'image/gif';
           $image = imagecreatefromgif($filein);
           break;
           case 'image/png':
           $image = imagecreatefrompng($filein);
           break;
       }
$width = $imagethumbsize_w ;
$height = $imagethumbsize_h ;
list($width_orig, $height_orig) = getimagesize($filein);
if ($width_orig < $height_orig) {
$height = ($imagethumbsize_w / $width_orig) * $height_orig;
} else {
    $width = ($imagethumbsize_h / $height_orig) * $width_orig;
}
if ($width < $imagethumbsize_w)
//if the width is smaller than supplied thumbnail size
{
$width = $imagethumbsize_w;
$height = ($imagethumbsize_w/ $width_orig) * $height_orig;;
}
if ($height < $imagethumbsize_h)
//if the height is smaller than supplied thumbnail size
{
$height = $imagethumbsize_h;
$width = ($imagethumbsize_h / $height_orig) * $width_orig;
}
$thumb = imagecreatetruecolor($width , $height);
$bgcolor = imagecolorallocate($thumb, $red, $green, $blue);
ImageFilledRectangle($thumb, 0, 0, $width, $height, $bgcolor);
imagealphablending($thumb, true);
imagecopyresampled($thumb, $image, 0, 0, 0, 0,
$width, $height, $width_orig, $height_orig);
$thumb2 = imagecreatetruecolor($imagethumbsize_w , $imagethumbsize_h);
// true color for best quality
$bgcolor = imagecolorallocate($thumb2, $red, $green, $blue);
ImageFilledRectangle($thumb2, 0, 0,
$imagethumbsize_w , $imagethumbsize_h , $white);
imagealphablending($thumb2, true);
$w1 =($width/2) - ($imagethumbsize_w/2);
$h1 = ($height/2) - ($imagethumbsize_h/2);
imagecopyresampled($thumb2, $thumb, 0,0, $w1, $h1,
$imagethumbsize_w , $imagethumbsize_h ,$imagethumbsize_w, $imagethumbsize_h);
// Output
//header('Content-type: image/gif');
//imagegif($thumb); //output to browser first image when testing
if ($fileout !="")imagegif($thumb2, $fileout); //write to file
header('Content-type: image/gif');
imagegif($thumb2); //output to browser
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=112275&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112275&page=function.imagecopyresampled&vote=down "Vote down!")

 -2


[**_hoangvu4000 at gmail dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#112275) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#112275)

**12 years ago**

`My complete function to resize an image  with exif data
<?php
function CreateThumbnail($pic,$thumb,$thumbwidth, $quality = 100)
{

        $im1=ImageCreateFromJPEG($pic);
        if(function_exists("exif_read_data")){
                $exif = exif_read_data($pic);
                if(!empty($exif['Orientation'])) {
                switch($exif['Orientation']) {
                case 8:
                    $im1 = imagerotate($im1,90,0);
                    break;
                case 3:
                    $im1 = imagerotate($im1,180,0);
                    break;
                case 6:
                    $im1 = imagerotate($im1,-90,0);
                    break;
                }
                }
        }
        $info = @getimagesize($pic);

        $width = $info[0];

        $w2=ImageSx($im1);
        $h2=ImageSy($im1);
        $w1 = ($thumbwidth <= $info[0]) ? $thumbwidth : $info[0]  ;

        $h1=floor($h2*($w1/$w2));
        $im2=imagecreatetruecolor($w1,$h1);

        imagecopyresampled ($im2,$im1,0,0,0,0,$w1,$h1,$w2,$h2);
        $path=addslashes($thumb);
        ImageJPEG($im2,$path,$quality);
        ImageDestroy($im1);
        ImageDestroy($im2);

}
?>`

[up](https://www.php.net/manual/vote-note.php?id=123343&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123343&page=function.imagecopyresampled&vote=down "Vote down!")

 -1


[**_aykuty at gmail dot com_**](https://www.php.net/manual/en/function.imagecopyresampled.php#123343) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#123343)

**6 years ago**

`scale image with ratio and then completes to the canvas size by centering
<?php
/*
verilen maksimum değerlere göre resmi boyutlandırır ve beyaz renk ile cerceveye ortalar. trendyol entegrasyonu için yazmıştım.
Aykut YILDIZGÖRÜR
aykuty add gmail dot com
*/
function set_image2canvas($file, $new_file, $canvas_width=1200, $canvas_height =1800, $quality=100) {

    if (!file_exists( $new_file )) {

        list($width, $height, $type, $attr) = getimagesize( $file );

        if($width> $height) {
                $width_tt=$canvas_width;
                $height_tt=round($height/$width*$canvas_width);
                $off_y = ceil(( $canvas_height - $height_tt)/2);
                $off_x=0;

        } else {
                $height_tt=$canvas_height;
                $width_tt=round($width/$height*$canvas_height);
                $off_x=ceil(($canvas_width - $width_tt)/2);
                $off_y=0;
        }
        $thumb=imagecreatefromjpeg( $file );
        $thumb_p = imagecreatetruecolor($canvas_width, $canvas_height);

        $bg = imagecolorallocate ( $thumb_p, 255, 255, 255 );
        imagefill ( $thumb_p, 0, 0, $bg );
        imagecopyresampled($thumb_p, $thumb, $off_x, $off_y, 0, 0, $width_tt, $height_tt, $width, $height);

        imagejpeg($thumb_p,$new_file,$quality);

    }else{ //hedef resim zaten var
            return -1;
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=80417&page=function.imagecopyresampled&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80417&page=function.imagecopyresampled&vote=down "Vote down!")

 -1


[**_Michael Shepanski_**](https://www.php.net/manual/en/function.imagecopyresampled.php#80417) [¶](https://www.php.net/manual/en/function.imagecopyresampled.php#80417)

**17 years ago**

`Here is a function I thought I would share that will resample and copy an image with rounded corners.
<?php
/** ------------------------------------------------------------
* Copy and resample an image with rounded corners.
* ----------------------------------------------------------- */
function imageRoundedCopyResampled(&$dstimg, &$srcimg, $dstx, $dsty, $srcx,
                                   $srcy, $dstw, $dsth, $srcw, $srch, $radius) {
    # Resize the Source Image
    $srcResized = imagecreatetruecolor($dstw, $dsth);
    imagecopyresampled($srcResized, $srcimg, 0, 0, $srcx, $srcy,
                       $dstw, $dsth, $srcw, $srch);
    # Copy the Body without corners
    imagecopy($dstimg, $srcResized, $dstx+$radius, $dsty,
              $radius, 0, $dstw-($radius*2), $dsth);
    imagecopy($dstimg, $srcResized, $dstx, $dsty+$radius,
              0, $radius, $dstw, $dsth-($radius*2));
    # Create a list of iterations; array(array(X1, X2, CenterX, CenterY), ...)
    # Iterations in order are: Top-Left, Top-Right, Bottom-Left, Bottom-Right
    $iterations = array(
        array(0, 0, $radius, $radius),
        array($dstw-$radius, 0, $dstw-$radius, $radius),
        array(0, $dsth-$radius, $radius, $dsth-$radius),
        array($dstw-$radius, $dsth-$radius, $dstw-$radius, $dsth-$radius)
    );
    # Loop through each corner 'iteration'
    foreach($iterations as $iteration) {
        list($x1,$y1,$cx,$cy) = $iteration;
        for ($y=$y1; $y<=$y1+$radius; $y++) {
            for ($x=$x1; $x<=$x1+$radius; $x++) {
                # If length (X,Y)->(CX,CY) is less then radius draw the point
                $length = sqrt(pow(($cx - $x), 2) + pow(($cy - $y), 2));
                if ($length < $radius) {
                    imagecopy($dstimg, $srcResized, $x+$dstx, $y+$dsty,
                              $x, $y, 1, 1);
                }
            }
        }
    }
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagecopyresampled&repo=en&redirect=https://www.php.net/manual/en/function.imagecopyresampled.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google