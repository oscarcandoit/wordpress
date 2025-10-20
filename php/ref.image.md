---
url: https://www.php.net/manual/en/ref.image.php
scraped_at: 2025-10-20T02:46:54.674Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# GD and Image Functions [¶](https://www.php.net/manual/en/ref.image.php\#ref.image)

## Table of Contents [¶](https://www.php.net/manual/en/ref.image.php\#ref.image)

- [gd\_info](https://www.php.net/manual/en/function.gd-info.php) — Retrieve information about the currently installed GD library
- [getimagesize](https://www.php.net/manual/en/function.getimagesize.php) — Get the size of an image
- [getimagesizefromstring](https://www.php.net/manual/en/function.getimagesizefromstring.php) — Get the size of an image from a string
- [image\_type\_to\_extension](https://www.php.net/manual/en/function.image-type-to-extension.php) — Get file extension for image type
- [image\_type\_to\_mime\_type](https://www.php.net/manual/en/function.image-type-to-mime-type.php) — Get Mime-Type for image-type returned by getimagesize,
exif\_read\_data, exif\_thumbnail, exif\_imagetype
- [image2wbmp](https://www.php.net/manual/en/function.image2wbmp.php) — Output image to browser or file
- [imageaffine](https://www.php.net/manual/en/function.imageaffine.php) — Return an image containing the affine transformed src image, using an optional clipping area
- [imageaffinematrixconcat](https://www.php.net/manual/en/function.imageaffinematrixconcat.php) — Concatenate two affine transformation matrices
- [imageaffinematrixget](https://www.php.net/manual/en/function.imageaffinematrixget.php) — Get an affine transformation matrix
- [imagealphablending](https://www.php.net/manual/en/function.imagealphablending.php) — Set the blending mode for an image
- [imageantialias](https://www.php.net/manual/en/function.imageantialias.php) — Should antialias functions be used or not
- [imagearc](https://www.php.net/manual/en/function.imagearc.php) — Draws an arc
- [imageavif](https://www.php.net/manual/en/function.imageavif.php) — Output image to browser or file
- [imagebmp](https://www.php.net/manual/en/function.imagebmp.php) — Output a BMP image to browser or file
- [imagechar](https://www.php.net/manual/en/function.imagechar.php) — Draw a character horizontally
- [imagecharup](https://www.php.net/manual/en/function.imagecharup.php) — Draw a character vertically
- [imagecolorallocate](https://www.php.net/manual/en/function.imagecolorallocate.php) — Allocate a color for an image
- [imagecolorallocatealpha](https://www.php.net/manual/en/function.imagecolorallocatealpha.php) — Allocate a color for an image
- [imagecolorat](https://www.php.net/manual/en/function.imagecolorat.php) — Get the index of the color of a pixel
- [imagecolorclosest](https://www.php.net/manual/en/function.imagecolorclosest.php) — Get the index of the closest color to the specified color
- [imagecolorclosestalpha](https://www.php.net/manual/en/function.imagecolorclosestalpha.php) — Get the index of the closest color to the specified color + alpha
- [imagecolorclosesthwb](https://www.php.net/manual/en/function.imagecolorclosesthwb.php) — Get the index of the color which has the hue, white and blackness
- [imagecolordeallocate](https://www.php.net/manual/en/function.imagecolordeallocate.php) — De-allocate a color for an image
- [imagecolorexact](https://www.php.net/manual/en/function.imagecolorexact.php) — Get the index of the specified color
- [imagecolorexactalpha](https://www.php.net/manual/en/function.imagecolorexactalpha.php) — Get the index of the specified color + alpha
- [imagecolormatch](https://www.php.net/manual/en/function.imagecolormatch.php) — Makes the colors of the palette version of an image more closely match the true color version
- [imagecolorresolve](https://www.php.net/manual/en/function.imagecolorresolve.php) — Get the index of the specified color or its closest possible alternative
- [imagecolorresolvealpha](https://www.php.net/manual/en/function.imagecolorresolvealpha.php) — Get the index of the specified color + alpha or its closest possible alternative
- [imagecolorset](https://www.php.net/manual/en/function.imagecolorset.php) — Set the color for the specified palette index
- [imagecolorsforindex](https://www.php.net/manual/en/function.imagecolorsforindex.php) — Get the colors for an index
- [imagecolorstotal](https://www.php.net/manual/en/function.imagecolorstotal.php) — Find out the number of colors in an image's palette
- [imagecolortransparent](https://www.php.net/manual/en/function.imagecolortransparent.php) — Define a color as transparent
- [imageconvolution](https://www.php.net/manual/en/function.imageconvolution.php) — Apply a 3x3 convolution matrix, using coefficient and offset
- [imagecopy](https://www.php.net/manual/en/function.imagecopy.php) — Copy part of an image
- [imagecopymerge](https://www.php.net/manual/en/function.imagecopymerge.php) — Copy and merge part of an image
- [imagecopymergegray](https://www.php.net/manual/en/function.imagecopymergegray.php) — Copy and merge part of an image with gray scale
- [imagecopyresampled](https://www.php.net/manual/en/function.imagecopyresampled.php) — Copy and resize part of an image with resampling
- [imagecopyresized](https://www.php.net/manual/en/function.imagecopyresized.php) — Copy and resize part of an image
- [imagecreate](https://www.php.net/manual/en/function.imagecreate.php) — Create a new palette based image
- [imagecreatefromavif](https://www.php.net/manual/en/function.imagecreatefromavif.php) — Create a new image from file or URL
- [imagecreatefrombmp](https://www.php.net/manual/en/function.imagecreatefrombmp.php) — Create a new image from file or URL
- [imagecreatefromgd](https://www.php.net/manual/en/function.imagecreatefromgd.php) — Create a new image from GD file or URL
- [imagecreatefromgd2](https://www.php.net/manual/en/function.imagecreatefromgd2.php) — Create a new image from GD2 file or URL
- [imagecreatefromgd2part](https://www.php.net/manual/en/function.imagecreatefromgd2part.php) — Create a new image from a given part of GD2 file or URL
- [imagecreatefromgif](https://www.php.net/manual/en/function.imagecreatefromgif.php) — Create a new image from file or URL
- [imagecreatefromjpeg](https://www.php.net/manual/en/function.imagecreatefromjpeg.php) — Create a new image from file or URL
- [imagecreatefrompng](https://www.php.net/manual/en/function.imagecreatefrompng.php) — Create a new image from file or URL
- [imagecreatefromstring](https://www.php.net/manual/en/function.imagecreatefromstring.php) — Create a new image from the image stream in the string
- [imagecreatefromtga](https://www.php.net/manual/en/function.imagecreatefromtga.php) — Create a new image from file or URL
- [imagecreatefromwbmp](https://www.php.net/manual/en/function.imagecreatefromwbmp.php) — Create a new image from file or URL
- [imagecreatefromwebp](https://www.php.net/manual/en/function.imagecreatefromwebp.php) — Create a new image from file or URL
- [imagecreatefromxbm](https://www.php.net/manual/en/function.imagecreatefromxbm.php) — Create a new image from file or URL
- [imagecreatefromxpm](https://www.php.net/manual/en/function.imagecreatefromxpm.php) — Create a new image from file or URL
- [imagecreatetruecolor](https://www.php.net/manual/en/function.imagecreatetruecolor.php) — Create a new true color image
- [imagecrop](https://www.php.net/manual/en/function.imagecrop.php) — Crop an image to the given rectangle
- [imagecropauto](https://www.php.net/manual/en/function.imagecropauto.php) — Crop an image automatically using one of the available modes
- [imagedashedline](https://www.php.net/manual/en/function.imagedashedline.php) — Draw a dashed line
- [imagedestroy](https://www.php.net/manual/en/function.imagedestroy.php) — Destroy an image
- [imageellipse](https://www.php.net/manual/en/function.imageellipse.php) — Draw an ellipse
- [imagefill](https://www.php.net/manual/en/function.imagefill.php) — Flood fill
- [imagefilledarc](https://www.php.net/manual/en/function.imagefilledarc.php) — Draw a partial arc and fill it
- [imagefilledellipse](https://www.php.net/manual/en/function.imagefilledellipse.php) — Draw a filled ellipse
- [imagefilledpolygon](https://www.php.net/manual/en/function.imagefilledpolygon.php) — Draw a filled polygon
- [imagefilledrectangle](https://www.php.net/manual/en/function.imagefilledrectangle.php) — Draw a filled rectangle
- [imagefilltoborder](https://www.php.net/manual/en/function.imagefilltoborder.php) — Flood fill to specific color
- [imagefilter](https://www.php.net/manual/en/function.imagefilter.php) — Applies a filter to an image
- [imageflip](https://www.php.net/manual/en/function.imageflip.php) — Flips an image using a given mode
- [imagefontheight](https://www.php.net/manual/en/function.imagefontheight.php) — Get font height
- [imagefontwidth](https://www.php.net/manual/en/function.imagefontwidth.php) — Get font width
- [imageftbbox](https://www.php.net/manual/en/function.imageftbbox.php) — Give the bounding box of a text using fonts via freetype2
- [imagefttext](https://www.php.net/manual/en/function.imagefttext.php) — Write text to the image using fonts using FreeType 2
- [imagegammacorrect](https://www.php.net/manual/en/function.imagegammacorrect.php) — Apply a gamma correction to a GD image
- [imagegd](https://www.php.net/manual/en/function.imagegd.php) — Output GD image to browser or file
- [imagegd2](https://www.php.net/manual/en/function.imagegd2.php) — Output GD2 image to browser or file
- [imagegetclip](https://www.php.net/manual/en/function.imagegetclip.php) — Get the clipping rectangle
- [imagegetinterpolation](https://www.php.net/manual/en/function.imagegetinterpolation.php) — Get the interpolation method
- [imagegif](https://www.php.net/manual/en/function.imagegif.php) — Output image to browser or file
- [imagegrabscreen](https://www.php.net/manual/en/function.imagegrabscreen.php) — Captures the whole screen
- [imagegrabwindow](https://www.php.net/manual/en/function.imagegrabwindow.php) — Captures a window
- [imageinterlace](https://www.php.net/manual/en/function.imageinterlace.php) — Enable or disable interlace
- [imageistruecolor](https://www.php.net/manual/en/function.imageistruecolor.php) — Finds whether an image is a truecolor image
- [imagejpeg](https://www.php.net/manual/en/function.imagejpeg.php) — Output image to browser or file
- [imagelayereffect](https://www.php.net/manual/en/function.imagelayereffect.php) — Set the alpha blending flag to use layering effects
- [imageline](https://www.php.net/manual/en/function.imageline.php) — Draw a line
- [imageloadfont](https://www.php.net/manual/en/function.imageloadfont.php) — Load a new font
- [imageopenpolygon](https://www.php.net/manual/en/function.imageopenpolygon.php) — Draws an open polygon
- [imagepalettecopy](https://www.php.net/manual/en/function.imagepalettecopy.php) — Copy the palette from one image to another
- [imagepalettetotruecolor](https://www.php.net/manual/en/function.imagepalettetotruecolor.php) — Converts a palette based image to true color
- [imagepng](https://www.php.net/manual/en/function.imagepng.php) — Output a PNG image to either the browser or a file
- [imagepolygon](https://www.php.net/manual/en/function.imagepolygon.php) — Draws a polygon
- [imagerectangle](https://www.php.net/manual/en/function.imagerectangle.php) — Draw a rectangle
- [imageresolution](https://www.php.net/manual/en/function.imageresolution.php) — Get or set the resolution of the image
- [imagerotate](https://www.php.net/manual/en/function.imagerotate.php) — Rotate an image with a given angle
- [imagesavealpha](https://www.php.net/manual/en/function.imagesavealpha.php) — Whether to retain full alpha channel information when saving images
- [imagescale](https://www.php.net/manual/en/function.imagescale.php) — Scale an image using the given new width and height
- [imagesetbrush](https://www.php.net/manual/en/function.imagesetbrush.php) — Set the brush image for line drawing
- [imagesetclip](https://www.php.net/manual/en/function.imagesetclip.php) — Set the clipping rectangle
- [imagesetinterpolation](https://www.php.net/manual/en/function.imagesetinterpolation.php) — Set the interpolation method
- [imagesetpixel](https://www.php.net/manual/en/function.imagesetpixel.php) — Set a single pixel
- [imagesetstyle](https://www.php.net/manual/en/function.imagesetstyle.php) — Set the style for line drawing
- [imagesetthickness](https://www.php.net/manual/en/function.imagesetthickness.php) — Set the thickness for line drawing
- [imagesettile](https://www.php.net/manual/en/function.imagesettile.php) — Set the tile image for filling
- [imagestring](https://www.php.net/manual/en/function.imagestring.php) — Draw a string horizontally
- [imagestringup](https://www.php.net/manual/en/function.imagestringup.php) — Draw a string vertically
- [imagesx](https://www.php.net/manual/en/function.imagesx.php) — Get image width
- [imagesy](https://www.php.net/manual/en/function.imagesy.php) — Get image height
- [imagetruecolortopalette](https://www.php.net/manual/en/function.imagetruecolortopalette.php) — Convert a true color image to a palette image
- [imagettfbbox](https://www.php.net/manual/en/function.imagettfbbox.php) — Give the bounding box of a text using TrueType fonts
- [imagettftext](https://www.php.net/manual/en/function.imagettftext.php) — Write text to the image using TrueType fonts
- [imagetypes](https://www.php.net/manual/en/function.imagetypes.php) — Return the image types supported by this PHP build
- [imagewbmp](https://www.php.net/manual/en/function.imagewbmp.php) — Output image to browser or file
- [imagewebp](https://www.php.net/manual/en/function.imagewebp.php) — Output a WebP image to browser or file
- [imagexbm](https://www.php.net/manual/en/function.imagexbm.php) — Output an XBM image to browser or file
- [iptcembed](https://www.php.net/manual/en/function.iptcembed.php) — Embeds binary IPTC data into a JPEG image
- [iptcparse](https://www.php.net/manual/en/function.iptcparse.php) — Parse a binary IPTC block into single tags
- [jpeg2wbmp](https://www.php.net/manual/en/function.jpeg2wbmp.php) — Convert JPEG image file to WBMP image file
- [png2wbmp](https://www.php.net/manual/en/function.png2wbmp.php) — Convert PNG image file to WBMP image file

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/reference.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fref.image%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.image&repo=en&redirect=https://www.php.net/manual/en/ref.image.php)

### User Contributed Notes 8 notes

[up](https://www.php.net/manual/vote-note.php?id=87238&page=ref.image&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87238&page=ref.image&vote=down "Vote down!")

8


[**_chuckstudios at gmail dot com_**](https://www.php.net/manual/en/ref.image.php#87238) [¶](https://www.php.net/manual/en/ref.image.php#87238)

**16 years ago**

`I wrote a simple function to convert an image resource to PGM (portable graymap) in order to feed it to an OCR program. It works just like the rest of the image output functions, and will convert to grayscale for you:
<?php
    function imagepgm($image, $filename = null)
    {
        $pgm = "P5 ".imagesx($image)." ".imagesy($image)." 255\n";
        for($y = 0; $y < imagesy($image); $y++)
        {
            for($x = 0; $x < imagesx($image); $x++)
            {
                $colors = imagecolorsforindex($image, imagecolorat($image, $x, $y));
                $pgm .= chr(0.3 * $colors["red"] + 0.59 * $colors["green"] + 0.11 * $colors["blue"]);
            }
        }
        if($filename != null)
        {
            $fp = fopen($filename, "w");
            fwrite($fp, $pgm);
            fclose($fp);
        }
        else
        {
            return $pgm;
        }
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=57909&page=ref.image&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=57909&page=ref.image&vote=down "Vote down!")

5


[**_michal-ok at o2 dot pl_**](https://www.php.net/manual/en/ref.image.php#57909) [¶](https://www.php.net/manual/en/ref.image.php#57909)

**20 years ago**

`The image sharpen function (by Alex R. Austin) provided below seems to be very resource hungry and I couldn't make it work on two different servers - trying to sharpen a 413 x 413 image I ended up with "Fatal error: Allowed memory size of 8388608 bytes exhausted" or "Internal Server Error" or the script terminated without notice. Because I had no priviliges to change the default memory limit on these servers I started looking for other sharpen functions. I have come across a php Unsharp Mask function which works like a charm on both of the servers I dealt with. It can be found at [http://vikjavev.no/hovudsida/umtestside.php.](http://vikjavev.no/hovudsida/umtestside.php.)`

[up](https://www.php.net/manual/vote-note.php?id=63064&page=ref.image&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=63064&page=ref.image&vote=down "Vote down!")

4


[**_felipensp at gmail dot com_**](https://www.php.net/manual/en/ref.image.php#63064) [¶](https://www.php.net/manual/en/ref.image.php#63064)

**19 years ago**

`Representation decimal of a color in hexadecimal for use on functions of library GD.
<?php
    // Representation hexadecimal
    $var = '#FFFFFF';
    function getRgbFromGd($color_hex) {
        return array_map('hexdec', explode('|', wordwrap(substr($color_hex, 1), 2, '|', 1)));
    }

    print_r(getRgbFromGd($var));
    // Output: Array ( [0] => 255 [1] => 255 [2] => 255 )
?>`

[up](https://www.php.net/manual/vote-note.php?id=63689&page=ref.image&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=63689&page=ref.image&vote=down "Vote down!")

 -1


[**_shd at earthling dot net_**](https://www.php.net/manual/en/ref.image.php#63689) [¶](https://www.php.net/manual/en/ref.image.php#63689)

**19 years ago**

`If you happen to need a way to output a Windows BMP file (e.g. when using the PEAR ExcelWriter), feel free to use the following code:
<?php
function imagebmp ($im, $fn = false)
{
    if (!$im) return false;

    if ($fn === false) $fn = 'php://output';
    $f = fopen ($fn, "w");
    if (!$f) return false;

    //Image dimensions
    $biWidth = imagesx ($im);
    $biHeight = imagesy ($im);
    $biBPLine = $biWidth * 3;
    $biStride = ($biBPLine + 3) & ~3;
    $biSizeImage = $biStride * $biHeight;
    $bfOffBits = 54;
    $bfSize = $bfOffBits + $biSizeImage;

    //BITMAPFILEHEADER
    fwrite ($f, 'BM', 2);
    fwrite ($f, pack ('VvvV', $bfSize, 0, 0, $bfOffBits));

    //BITMAPINFO (BITMAPINFOHEADER)
    fwrite ($f, pack ('VVVvvVVVVVV', 40, $biWidth, $biHeight, 1, 24, 0, $biSizeImage, 0, 0, 0, 0));

    $numpad = $biStride - $biBPLine;
    for ($y = $biHeight - 1; $y >= 0; --$y)
    {
        for ($x = 0; $x < $biWidth; ++$x)
        {
            $col = imagecolorat ($im, $x, $y);
            fwrite ($f, pack ('V', $col), 3);
        }
        for ($i = 0; $i < $numpad; ++$i)
            fwrite ($f, pack ('C', 0));
    }
    fclose ($f);
    return true;
}
?>
It works the same way as regular imagejpeg/imagepng do and only supports GD2.0 true colour bitmaps (which is what's required by ExcelWriter).`

[up](https://www.php.net/manual/vote-note.php?id=120217&page=ref.image&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120217&page=ref.image&vote=down "Vote down!")

 -2


[**_delabahan at gmail dot com_**](https://www.php.net/manual/en/ref.image.php#120217) [¶](https://www.php.net/manual/en/ref.image.php#120217)

**8 years ago**

`This is an example of get high resolution images.
<?php
/**
* Class name      : resizeImage
* Created by   : wang
* Description   : This class is to resize the image from original size to new size
*/
class resizeImage
{
     /**
     * Function name : resize_img
     * Description   : This function is to resize image
     * @param          : $origimg variable is the original image
     * @param          : $newimg variable is the new image
     * @param          : $w variable is the width of image
     * @param          : $f variable is the height of image
     */
    public  function resize_img($origimg,$newimg,$w,$h){
        $info = getimagesize($origimg);
        $mime   = $info['mime'];
        // Make sure that the requested file is actually an image
        if(substr($mime, 0, 6) != 'image/')
        {
            header('HTTP/1.1 400 Bad Request');
            return 'Error: requested file is not an accepted type: ' .$origimg;
            exit();
        }
        // Check they extention of image
        $extension = image_type_to_extension($info[2]);
        if(strtolower($extension) == '.png'){
            $img = $this->resize_imagepng($origimg,$w, $h);
            imagepng($img,$newimg);
            imagedestroy($img);
        }elseif(strtolower($extension) == '.jpeg'){
            $img = $this->resize_imagejpeg($origimg, $w, $h);
            imagejpeg($img, $newimg);
            imagedestroy($img);
        }elseif(strtolower($extension == '.gif')){
            $img = $this->resize_imagegif($origimg, $w, $h);
            imagegif($img,$newimg);
            imagedestroy($img);
        }
    }
     /**
     * End function name : resize_img
     */
     /**
     * Function name : resize_imagepng
     * Description   : This function is to resize png image
     * @param          : $file variable is the original image
     * @param          : $w variable is the width of image
     * @param          : $f variable is the height of image
     */
    private function resize_imagepng($file, $w, $h) {
       list($width, $height) = getimagesize($file);
       $src = imagecreatefrompng($file);
       $dst = imagecreatetruecolor($w, $h);
       imagecopyresampled($dst, $src, 0, 0, 0, 0, $w, $h, $width, $height);
       return $dst;
    }
     /**
     * End function name : resize_imagepng
     */
     /**
     * Function name : resize_imagejpeg
     * Description   : This function is to resize jpeg image
     * @param          : $file variable is the original image
     * @param          : $w variable is the width of image
     * @param          : $f variable is the height of image
     */
    private function resize_imagejpeg($file, $w, $h) {
       list($width, $height) = getimagesize($file);
       $src = imagecreatefromjpeg($file);
       $dst = imagecreatetruecolor($w, $h);
       imagecopyresampled($dst, $src, 0, 0, 0, 0, $w, $h, $width, $height);
       return $dst;
    }
     /**
     * End function name : resize_imagejpeg
     */
     /**
     * Function name : resize_imagegif
     * Description   : This function is to resize gif image
     * @param          : $file variable is the original image
     * @param          : $w variable is the width of image
     * @param          : $f variable is the height of image
     */
    private function resize_imagegif($file, $w, $h) {
       list($width, $height) = getimagesize($file);
       $src = imagecreatefromgif($file);
       $dst = imagecreatetruecolor($w, $h);
       imagecopyresampled($dst, $src, 0, 0, 0, 0, $w, $h, $width, $height);
       return $dst;
    }
     /**
     * End function name : resize_imagegif
     */
}
/**
* End class name : resizeImage
*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=106150&page=ref.image&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106150&page=ref.image&vote=down "Vote down!")

 -3


[**_ingo at jache dot de_**](https://www.php.net/manual/en/ref.image.php#106150) [¶](https://www.php.net/manual/en/ref.image.php#106150)

**14 years ago**

`I know this might look somewhat superfluous to others, but i once came across a situation where i needed a *strong* blur on an image without having ImageMagick installed. Executing the convolution-filter several times on the same image is awfully slow and still doesn't give a good blur.
The function below accepts a truecolor-image and a blur-factor between 0.0 and 1.0. Beware: It's still quite slow.
<?php
    function blurImage($srcimg,$blur)
    {
        $blur = $blur*$blur;
        $blur = max(0,min(1,$blur));

        $srcw = imagesx($srcimg);
        $srch = imagesy($srcimg);

        $dstimg = imagecreatetruecolor($srcw,$srch);

        $f1a = $blur;
        $f1b = 1.0 - $blur;

        $cr = 0; $cg = 0; $cb = 0;
        $nr = 0; $ng = 0; $nb = 0;
        $rgb = imagecolorat($srcimg,0,0);
        $or = ($rgb >> 16) & 0xFF;
        $og = ($rgb >> 8) & 0xFF;
        $ob = ($rgb) & 0xFF;
        //-------------------------------------------------
        // first line is a special case
        //-------------------------------------------------
        $x = $srcw;
        $y = $srch-1;
        while ($x--)
        {
            //horizontal blurren
            $rgb = imagecolorat($srcimg,$x,$y);
            $cr = ($rgb >> 16) & 0xFF;
            $cg = ($rgb >> 8) & 0xFF;
            $cb = ($rgb) & 0xFF;

            $nr = ($cr * $f1a) + ($or * $f1b);
            $ng = ($cg * $f1a) + ($og * $f1b);
            $nb = ($cb * $f1a) + ($ob * $f1b);
            $or = $nr;
            $og = $ng;
            $ob = $nb;

            imagesetpixel($dstimg,$x,$y,($nr << 16) | ($ng << 8) | ($nb));
        }
        //-------------------------------------------------
        //-------------------------------------------------
        // now process the entire picture
        //-------------------------------------------------
        $y = $srch-1;
        while ($y--)
        {
            $rgb = imagecolorat($srcimg,0,$y);
            $or = ($rgb >> 16) & 0xFF;
            $og = ($rgb >> 8) & 0xFF;
            $ob = ($rgb) & 0xFF;
            $x = $srcw;
            while ($x--)
            {
                //horizontal
                $rgb = imagecolorat($srcimg,$x,$y);
                $cr = ($rgb >> 16) & 0xFF;
                $cg = ($rgb >> 8) & 0xFF;
                $cb = ($rgb) & 0xFF;

                $nr = ($cr * $f1a) + ($or * $f1b);
                $ng = ($cg * $f1a) + ($og * $f1b);
                $nb = ($cb * $f1a) + ($ob * $f1b);

                $or = $nr;
                $og = $ng;
                $ob = $nb;


                //vertical
                $rgb = imagecolorat($dstimg,$x,$y+1);
                $vr = ($rgb >> 16) & 0xFF;
                $vg = ($rgb >> 8) & 0xFF;
                $vb = ($rgb) & 0xFF;

                $nr = ($nr * $f1a) + ($vr * $f1b);
                $ng = ($ng * $f1a) + ($vg * $f1b);
                $nb = ($nb * $f1a) + ($vb * $f1b);

                $vr = $nr;
                $vg = $ng;
                $vb = $nb;

                imagesetpixel($dstimg,$x,$y,($nr << 16) | ($ng << 8) | ($nb));
            }

        }
        //-------------------------------------------------
        return $dstimg;
    }

    $srcimg = imagecreatefromjpeg("test.jpg");
    $dstimg = blurImage($srcimg,0.2);
    header('Content-type: image/jpeg');
    echo( imagejpeg($dstimg) );
    exit();


?>`

[up](https://www.php.net/manual/vote-note.php?id=37131&page=ref.image&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=37131&page=ref.image&vote=down "Vote down!")

 -2


[**_jeff at lushmedia dot com_**](https://www.php.net/manual/en/ref.image.php#37131) [¶](https://www.php.net/manual/en/ref.image.php#37131)

**21 years ago**

`I wrote an online overview of the image functions that people might find useful. In addition to a general overview of the various function categories and code samples, I have included many interactive examples of the functions, allowing viewers to experiment with the parameters, and seeing the results in real time. The presentation is located at New York PHP
[http://www.nyphp.org/content/presentations/GDintro/](http://www.nyphp.org/content/presentations/GDintro/)`

[up](https://www.php.net/manual/vote-note.php?id=120139&page=ref.image&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120139&page=ref.image&vote=down "Vote down!")

 -4


[**_mpyw_**](https://www.php.net/manual/en/ref.image.php#120139) [¶](https://www.php.net/manual/en/ref.image.php#120139)

**8 years ago**

`This is an example of black-and-white imagebmp() implementation.
<?php
/**
* Output a black-and-white BMP image to either the browser or a file.
*
* @param resource $image
*            An image resource, returned by one of the image creation functions,
*            such as imagecreatetruecolor().
*
* @param string|null $to
*            The path or an open stream resource
*            (which is automatically being closed after this function returns)
*            to save the file to.
*            If not set or NULL, the raw image stream will be outputted directly.
*
* @param float $threshold
*            The number in the range of 0.0 to 1.0.
*            Brighter for larger, or darker for smaller.
*
* @return bool Returns TRUE on success or FALSE on failure.
*
*/
function imagebwbmp($image, $to = null, $threshold = 0.5)
{
    if (func_num_args() < 1) {
        $fmt = "imagebwbmp() expects a least 1 parameters, %d given";
        trigger_error(sprintf($fmt, func_num_args()), E_USER_WARNING);
        return;
    }
    if (!is_resource($image)) {
        $fmt = "imagebwbmp() expects parameter 1 to be resource, %s given";
        trigger_error(sprintf($fmt, gettype($image)), E_USER_WARNING);
        return;
    }
    if (!is_numeric($threshold)) {
        $fmt = "imagebwbmp() expects parameter 3 to be float, %s given";
        trigger_error(sprintf($fmt, gettype($threshold)), E_USER_WARNING);
        return;
    }
    if (get_resource_type($image) !== 'gd') {
        $msg = "imagebwbmp(): supplied resource is not a valid gd resource";
        trigger_error($msg, E_USER_WARNING);
        return false;
    }
    switch (true) {
        case $to === null:
            break;
        case is_resource($to) && get_resource_type($to) === 'stream':
        case is_string($to) && $to = fopen($to, 'wb'):
            if (preg_match('/[waxc+]/', stream_get_meta_data($to)['mode'])) {
                break;
            }
        default:
            $msg = "imagebwbmp(): Invalid 2nd parameter, it must a writable filename or a writable stream";
            trigger_error($msg, E_USER_WARNING);
            return false;
    }
    if ($to === null) {
        $to = fopen('php://output', 'wb');
    }
    $biWidth = imagesx($image);
    $biHeight = imagesy($image);
    $biSizeImage = ((int)ceil($biWidth / 32) * 32 / 8 * $biHeight);
    $bfOffBits = 54 + 4 * 2; // Use two colors (black and white)
    $bfSize = $bfOffBits + $biSizeImage;

    fwrite($to, 'BM');
    fwrite($to, pack('VvvV', $bfSize, 0, 0, $bfOffBits));
    fwrite($to, pack('VVVvvVVVVVV', 40, $biWidth, $biHeight, 1, 1, 0, $biSizeImage, 0, 0, 0, 0));
    fwrite($to, "\xff\xff\xff\x00"); // white
    fwrite($to, "\x00\x00\x00\x00"); // black

    for ($y = $biHeight - 1; $y >= 0; --$y) {
        $byte = 0;
        for ($x = 0; $x < $biWidth; ++$x) {
            $rgb = imagecolorsforindex($image, imagecolorat($image, $x, $y));
            $value = (0.299 * $rgb['red'] + 0.587 * $rgb['green'] + 0.114 * $rgb['blue']) / 0xff;
            $color = (int)($value > $threshold);
            $byte = ($byte << 1) | $color;
            if ($x % 8 === 7) {
                fwrite($to, pack('C', $byte));
                $byte = 0;
            }
        }
        if ($x % 8) {
            fwrite($to, pack('C', $byte << (8 - $x % 8)));
        }
        if ($x % 32) {
            fwrite($to, str_repeat("\x00", (int)((32 - $x % 32) / 8)));
        }
    }
    return true;
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.image&repo=en&redirect=https://www.php.net/manual/en/ref.image.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google