---
url: https://www.php.net/manual/en/function.imagettftext.php
scraped_at: 2025-10-20T02:59:27.925Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imagettftext

(PHP 4, PHP 5, PHP 7, PHP 8)

imagettftext — Write text to the image using TrueType fonts

### Description [¶](https://www.php.net/manual/en/function.imagettftext.php\#refsect1-function.imagettftext-description)

**imagettftext**(

[GdImage](https://www.php.net/manual/en/class.gdimage.php) `$image`,

[float](https://www.php.net/manual/en/language.types.float.php) `$size`,

[float](https://www.php.net/manual/en/language.types.float.php) `$angle`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$x`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$y`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$color`,

[string](https://www.php.net/manual/en/language.types.string.php) `$font_filename`,

[string](https://www.php.net/manual/en/language.types.string.php) `$text`,

[array](https://www.php.net/manual/en/language.types.array.php) `$options` = \[\]

): [array](https://www.php.net/manual/en/language.types.array.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Writes the given `text` into the image using TrueType
fonts.


> **Note**:
>
>
> Prior to PHP 8.0.0, [imagefttext()](https://www.php.net/manual/en/function.imagefttext.php) was an extended variant of
> **imagettftext()** which additionally supported the
> `extrainfo`.
> As of PHP 8.0.0, **imagettftext()** is an alias of [imagefttext()](https://www.php.net/manual/en/function.imagefttext.php).

### Parameters [¶](https://www.php.net/manual/en/function.imagettftext.php\#refsect1-function.imagettftext-parameters)

`image`

A [GdImage](https://www.php.net/manual/en/class.gdimage.php) object, returned by one of the image creation functions,
such as [imagecreatetruecolor()](https://www.php.net/manual/en/function.imagecreatetruecolor.php).

`size`

The font size in points.

`angle`

The angle in degrees, with 0 degrees being left-to-right reading text.
Higher values represent a counter-clockwise rotation. For example, a
value of 90 would result in bottom-to-top reading text.


`x`

The coordinates given by `x` and
`y` will define the basepoint of the first
character (roughly the lower-left corner of the character). This
is different from the [imagestring()](https://www.php.net/manual/en/function.imagestring.php), where
`x` and `y` define the
upper-left corner of the first character. For example, "top left"
is 0, 0.


`y`

The y-ordinate. This sets the position of the fonts baseline, not the
very bottom of the character.


`color`

The color index. Using the negative of a color index has the effect of
turning off antialiasing. See [imagecolorallocate()](https://www.php.net/manual/en/function.imagecolorallocate.php).


`fontfile`

The path to the TrueType font you wish to use.


Depending on which version of the GD library PHP is using, _when_
_`fontfile` does not begin with a leading_
_`/` then `.ttf` will be appended_
to the filename and the library will attempt to search for that
filename along a library-defined font path.


When using versions of the GD library lower than 2.0.18, a `space` character,
rather than a semicolon, was used as the 'path separator' for different font files.
Unintentional use of this feature will result in the warning message:
`Warning: Could not find/open font`. For these affected versions, the
only solution is moving the font to a path which does not contain spaces.


In many cases where a font resides in the same directory as the script using it
the following trick will alleviate any include problems.


`<?php
// Set the environment variable for GD
putenv('GDFONTPATH=' . realpath('.'));
// Name the font to be used (note the lack of the .ttf extension)
$font = 'SomeFont';
?>`

> **Note**:
>
>
> Note that [open\_basedir](https://www.php.net/manual/en/ini.core.php#ini.open-basedir) does
> _not_ apply to `fontfile`.

`text`

The text string in UTF-8 encoding.


May include decimal numeric character references (of the form:
`&#8364;`) to access characters in a font beyond position 127.
The hexadecimal format (like `&#xA9;`) is supported.
Strings in UTF-8 encoding can be passed directly.


Named entities, such as `&copy;`, are not supported. Consider using
[html\_entity\_decode()](https://www.php.net/manual/en/function.html-entity-decode.php)
to decode these named entities into UTF-8 strings.


If a character is used in the string which is not supported by the
font, a hollow rectangle will replace the character.


`options`

An array with `linespacing` key holding a [float](https://www.php.net/manual/en/language.types.float.php) value.


### Return Values [¶](https://www.php.net/manual/en/function.imagettftext.php\#refsect1-function.imagettftext-returnvalues)

Returns an array with 8 elements representing four points making the
bounding box of the text. The order of the points is lower left, lower
right, upper right, upper left. The points are relative to the text
regardless of the angle, so "upper left" means in the top left-hand
corner when you see the text horizontally.
Returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on error.


### Changelog [¶](https://www.php.net/manual/en/function.imagettftext.php\#refsect1-function.imagettftext-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | The `options` has been added. |

### Examples [¶](https://www.php.net/manual/en/function.imagettftext.php\#refsect1-function.imagettftext-examples)

**Example #1 **imagettftext()** example**

This example script will produce a white PNG 400x30 pixels, with
the words "Testing..." in black (with grey shadow), in the font Arial.


`<?php
// Set the content-type
header('Content-Type: image/png');
// Create the image
$im = imagecreatetruecolor(400, 30);
// Create some colors
$white = imagecolorallocate($im, 255, 255, 255);
$grey = imagecolorallocate($im, 128, 128, 128);
$black = imagecolorallocate($im, 0, 0, 0);
imagefilledrectangle($im, 0, 0, 399, 29, $white);
// The text to draw
$text = 'Testing...';
// Replace path by your own font path
$font = 'arial.ttf';
// Add some shadow to the text
imagettftext($im, 20, 0, 11, 21, $grey, $font, $text);
// Add the text
imagettftext($im, 20, 0, 10, 20, $black, $font, $text);
// Using imagepng() results in clearer text compared with imagejpeg()
imagepng($im);
?>`

The above example will output
something similar to:

![Output of example : imagettftext()](https://www.php.net/manual/en/images/21009b70229598c6a80eef8b45bf282b-imagettftext.png)

### Notes [¶](https://www.php.net/manual/en/function.imagettftext.php\#refsect1-function.imagettftext-notes)

> **Note**: This function is only available if
> PHP is compiled with freetype support ( **--with-freetype-dir=DIR**)

### See Also [¶](https://www.php.net/manual/en/function.imagettftext.php\#refsect1-function.imagettftext-seealso)

- [imagettfbbox()](https://www.php.net/manual/en/function.imagettfbbox.php) \- Give the bounding box of a text using TrueType fonts
- [imagefttext()](https://www.php.net/manual/en/function.imagefttext.php) \- Write text to the image using fonts using FreeType 2
- [imagestring()](https://www.php.net/manual/en/function.imagestring.php) \- Draw a string horizontally

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/functions/imagettftext.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imagettftext%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagettftext&repo=en&redirect=https://www.php.net/manual/en/function.imagettftext.php)

### User Contributed Notes 40 notes

[up](https://www.php.net/manual/vote-note.php?id=83248&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=83248&page=function.imagettftext&vote=down "Vote down!")

52


[**_Valentijn de Pagter_**](https://www.php.net/manual/en/function.imagettftext.php#83248) [¶](https://www.php.net/manual/en/function.imagettftext.php#83248)

**17 years ago**

`If you're looking for easy text alignment, you need to use the imagettfbbox() command. When given the correct parameters, it will return the boundaries of your to-be-made text field in an array, which will allow you to calculate the x and y coordinate that you need to use for centering or aligning your text.
A horizontal centering example:
<?php
$tb = imagettfbbox(17, 0, 'airlock.ttf', 'Hello world!');
?>
$tb would contain:
Array
(
    [0] => 0 // lower left X coordinate
    [1] => -1 // lower left Y coordinate
    [2] => 198 // lower right X coordinate
    [3] => -1 // lower right Y coordinate
    [4] => 198 // upper right X coordinate
    [5] => -20 // upper right Y coordinate
    [6] => 0 // upper left X coordinate
    [7] => -20 // upper left Y coordinate
)
For horizontal alignment, we need to substract the "text box's" width { $tb[2] or $tb[4] } from the image's width and then substract by two.
Saying you have a 200px wide image, you could do something like this:
<?php
$x = ceil((200 - $tb[2]) / 2); // lower left X coordinate for text
imagettftext($im, 17, 0, $x, $y, $tc, 'airlock.ttf', 'Hello world!'); // write text to image
?>
This'll give you perfect horizontal center alignment for your text, give or take 1 pixel. Have fun!`

[up](https://www.php.net/manual/vote-note.php?id=55687&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=55687&page=function.imagettftext&vote=down "Vote down!")

6


[**_gav-alex at bk dot ru_**](https://www.php.net/manual/en/function.imagettftext.php#55687) [¶](https://www.php.net/manual/en/function.imagettftext.php#55687)

**20 years ago**

`Hi all!
When my hoster updated his php's libs at first minutes i've got the same problem as some of you.
Php couldn't find the path to true type fonts.
The solution in my case was to make the path look like this
<?php
imagettftext($im, 20, 0, 620, 260, $secondary_color, "./tahoma.ttf" , "NEWS");
?>
so as you can see i simply added "./"
another tip that i wanted to add here is how to write in RUssian on image using imagettftext
you simply have to change the function argument like this
<?php
imagettftext($im, 15, 0, 575, 300, $secondary_color, "./tahoma.ttf" , win2uni("some word in russian"));
?>
where win2uni is the function that converts win1251 to unicode. here is the code of it
<?php
//  Windows 1251 -> Unicode
function win2uni($s)
{
    $s = convert_cyr_string($s,'w','i'); //  win1251 -> iso8859-5
    //  iso8859-5 -> unicode:
    for ($result='', $i=0; $i<strlen($s); $i++) {
      $charcode = ord($s[$i]);
      $result .= ($charcode>175)?"&#".(1040+($charcode-176)).";":$s[$i];
    }
    return $result;
}
?>
That's all today! Thanks for your attention!
Alex`

[up](https://www.php.net/manual/vote-note.php?id=113563&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113563&page=function.imagettftext&vote=down "Vote down!")

12


[**_suyog at suyogdixit dot com_**](https://www.php.net/manual/en/function.imagettftext.php#113563) [¶](https://www.php.net/manual/en/function.imagettftext.php#113563)

**11 years ago**

`For your general edification: The following drop-in function will place a block of fully justified text onto a GD image. It is a little CPU heavy, so I suggest caching the output rather than doing it on-the-fly.
Arguments:
$image - the GD handle of the target canvas
$size - text size
$angle - slope of text (does not work very well), leave at 0 for horizontal text
$left - no. of pixels from left to start block
$top - no. of pixels from top to start block
$color - handle for colour (imagecolorallocate result)
$font - path to .ttf font
$text - the text to wrap and justify
$max_width - the width of the text block within which the text should be wrapped and fully justified
$minspacing - the minimum number of pixels between words
$linespacing - a multiplier of line height (1 for normal spacing; 1.5 for line-and-a-half etc.)
eg.
$image = ImageCreateFromJPEG( "sample.jpg" );
$cor = imagecolorallocate($image, 0, 0, 0);
$font = 'arial.ttf';
$a = imagettftextjustified($image, 20, 0, 50, 50, $color, $font, "Shree", 500, $minspacing=3,$linespacing=1);
header('Content-type: image/jpeg');
imagejpeg($image,NULL,100);
function imagettftextjustified(&$image, $size, $angle, $left, $top, $color, $font, $text, $max_width, $minspacing=3,$linespacing=1)
{
$wordwidth = array();
$linewidth = array();
$linewordcount = array();
$largest_line_height = 0;
$lineno=0;
$words=explode(" ",$text);
$wln=0;
$linewidth[$lineno]=0;
$linewordcount[$lineno]=0;
foreach ($words as $word)
{
$dimensions = imagettfbbox($size, $angle, $font, $word);
$line_width = $dimensions[2] - $dimensions[0];
$line_height = $dimensions[1] - $dimensions[7];
if ($line_height>$largest_line_height) $largest_line_height=$line_height;
if (($linewidth[$lineno]+$line_width+$minspacing)>$max_width)
{
$lineno++;
$linewidth[$lineno]=0;
$linewordcount[$lineno]=0;
$wln=0;
}
$linewidth[$lineno]+=$line_width+$minspacing;
$wordwidth[$lineno][$wln]=$line_width;
$wordtext[$lineno][$wln]=$word;
$linewordcount[$lineno]++;
$wln++;
}
for ($ln=0;$ln<=$lineno;$ln++)
{
$slack=$max_width-$linewidth[$ln];
if (($linewordcount[$ln]>1)&&($ln!=$lineno)) $spacing=($slack/($linewordcount[$ln]-1));
else $spacing=$minspacing;
$x=0;
for ($w=0;$w<$linewordcount[$ln];$w++)
{
imagettftext($image, $size, $angle, $left + intval($x), $top + $largest_line_height + ($largest_line_height * $ln * $linespacing), $color, $font, $wordtext[$ln][$w]);
$x+=$wordwidth[$ln][$w]+$spacing+$minspacing;
}
}
return true;
}`

[up](https://www.php.net/manual/vote-note.php?id=77935&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77935&page=function.imagettftext&vote=down "Vote down!")

2


[**_mitch at electricpulp dot com_**](https://www.php.net/manual/en/function.imagettftext.php#77935) [¶](https://www.php.net/manual/en/function.imagettftext.php#77935)

**18 years ago**

`If you're having issues with fonts not working... (Could not find/open font) check your permissions on the folder/font files and make sure they're 775, especially if you've just pulled them from a windows box. Hope this helps!`

[up](https://www.php.net/manual/vote-note.php?id=84961&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84961&page=function.imagettftext&vote=down "Vote down!")

2


[**_s.pynenburg \_at\_ gm ail dotcom_**](https://www.php.net/manual/en/function.imagettftext.php#84961) [¶](https://www.php.net/manual/en/function.imagettftext.php#84961)

**17 years ago**

`I had an image generator where the user could position where they wanted the text to begin - however it kept going off the side of an image. So I made this basic function: it measures if the inputted text and x-position will cause the string to go off the edge, and if so, it will fit as much as it can on the first line, then go down to the next one.
Limitations:
-It only performs this once (i.e. it won't split into three lines)
-I'm pretty sure it won't work with angled text.
<?PHP
function imagettftextwrap($im, $size, $angle, $x_pos, $y_pos, $color, $font, $instr)
{
    $box = @imagettfbbox($size, 0, $font, $instr);
    $width = abs($box[4] - $box[0]);
    $height = abs($box[3] - $box[5]);
    $overlap = (($x_pos + $width) - imagesx($im));
    if($overlap > 0) //if the text doesn't fit on the image
    {
        $chars = str_split($instr);
        $str = "";
        $pstr = "";
        for($m=0; $m < sizeof($chars); $m++)
        {
            $bo = imagettfbbox($fsize1, 0, $font1, $str);
            $wid = abs($bo[4] - $bo[0]);
            if(($x_pos + $wid) < imagesx($im)) //add one char from the string as long as it's not overflowing
            {
                $pstr .= $chars[$m];
                $bo2 = imagettfbbox($fsize1, 0, $font1, $pstr);
                $wid2 = abs($bo2[4] - $bo2[0]);
                if(($x_pos + $wid2) < imagesx($im))
                {
                    $str .= $chars[$m];
                }
                else
                {
                    break;
                }
            }
            else
            {
                break;
            }
        }
        $restof = "";
        for($l=$m; $l < sizeof($chars); $l++)
        {
            $restof .= $chars[$l]; //add the rest of the string to a new line
        }
        imagettftext($im, $size, $angle, $x_pos, $y_pos, $color, $font, $str); // print out the smaller line
        imagettftext($im, $size, $angle, 0, $y_pos + $height, $color, $font, $restof); //and the rest of it
    }
    else
    {
        imagettftext($im, $size, $angle, $x_pos, $y_pos, $color, $font, $instr); //otherwise just do normally
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=48938&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=48938&page=function.imagettftext&vote=down "Vote down!")

3


[**_pillepop2003 at nospam dot yahoo dot de_**](https://www.php.net/manual/en/function.imagettftext.php#48938) [¶](https://www.php.net/manual/en/function.imagettftext.php#48938)

**20 years ago**

`Hey guys,
check this function if you want to rotate the text around its center and not its "lower left" pivot-point:
<?php
        // Put center-rotated ttf-text into image
        // Same signature as imagettftext();
        function imagettftext_cr(&$im, $size, $angle, $x, $y, $color, $fontfile, $text)
        {
            // retrieve boundingbox
            $bbox = imagettfbbox($size, $angle, $fontfile, $text);

            // calculate deviation
            $dx = ($bbox[2]-$bbox[0])/2.0 - ($bbox[2]-$bbox[4])/2.0;         // deviation left-right
            $dy = ($bbox[3]-$bbox[1])/2.0 + ($bbox[7]-$bbox[1])/2.0;        // deviation top-bottom

            // new pivotpoint
            $px = $x-$dx;
            $py = $y-$dy;

            return imagettftext($im, $size, $angle, $px, $py, $color, $fontfile, $text);
        }
?>
Big up
Phil`

[up](https://www.php.net/manual/vote-note.php?id=96472&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96472&page=function.imagettftext&vote=down "Vote down!")

2


[**_JohnB_**](https://www.php.net/manual/en/function.imagettftext.php#96472) [¶](https://www.php.net/manual/en/function.imagettftext.php#96472)

**15 years ago**

`Just in case you were--like me--unaware of this, in Windows, ttf fonts don't necessarily antialias at all font sizes. Arial appears to work at all sizes but Calibri, for example, only antialiases at a point size of 8 and then at all sizes 16 and up. Not only that but at fonts sizes like 10 and 12 characters don't print at the expected angle: the characters are all printed upright on an angled baseline.`

[up](https://www.php.net/manual/vote-note.php?id=90580&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90580&page=function.imagettftext&vote=down "Vote down!")

3


[**_philip at webdesco dot com_**](https://www.php.net/manual/en/function.imagettftext.php#90580) [¶](https://www.php.net/manual/en/function.imagettftext.php#90580)

**16 years ago**

`Hi,
for the dummies (like myself) if you are having problems including your font file, prefix the file name with ./
On my development server the following worked fine
$myfont = "coolfont.ttf";
on my hosting server the only way i could get the font to work was as follows
$myfont = "./coolfont.ttf";
hope this helps someone out!`

[up](https://www.php.net/manual/vote-note.php?id=91061&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91061&page=function.imagettftext&vote=down "Vote down!")

2


[**_web at evanreeves dot com_**](https://www.php.net/manual/en/function.imagettftext.php#91061) [¶](https://www.php.net/manual/en/function.imagettftext.php#91061)

**16 years ago**

`I was having trouble trying to render non antialiased text using a pixel font. The tips about setting a negative value for the color are valid, but I was still having trouble with the text I was trying to render because it was black. I discovered that if I changed the imagecolorallocate() function from:
$color = imagecolorallocate($base, 0, 0, 0);
to
$color = imagecolorallocate($base, 1, 1, 1); (near black)
and then used the negative value for the color in imagettftext(), it would work properly. The difference is that my first implementation set $color = 0. Obviously, you can't have $color = -0, it made no difference. When I switched to (1,1,1) it became $color = 1 which I could take a negative value for.`

[up](https://www.php.net/manual/vote-note.php?id=100713&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100713&page=function.imagettftext&vote=down "Vote down!")

2


[**_John Conde_**](https://www.php.net/manual/en/function.imagettftext.php#100713) [¶](https://www.php.net/manual/en/function.imagettftext.php#100713)

**14 years ago**

`If you want to create a paragraph you will need to break your text up into lines and then place each line individually one below the next.
Here's a basic example of how to do that:
<?php
// Basic font settings
$font ='./times.ttf';
$font_size = 15;
$font_color =  0x000000
// Text to be placed as a paragraph
$text = 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer non nunc lectus. Curabitur hendrerit bibendum enim dignissim tempus. Suspendisse non ipsum auctor metus consectetur eleifend. Fusce cursus ullamcorper sem nec ultricies. Aliquam erat volutpat. Vivamus massa justo, pharetra et sodales quis, rhoncus in ligula. Integer dolor velit, ultrices in iaculis nec, viverra ut nunc.';
// Break it up into pieces 125 characters long
$lines = explode('|', wordwrap($text, 115, '|'));
// Starting Y position
$y = 513;
// Loop through the lines and place them on the image
foreach ($lines as $line)
{
    imagettftext($image, $font_size, 0, 50, $y, $font_color, $font, $line);
    // Increment Y so the next line is below the previous line
    $y += 23;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=126038&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126038&page=function.imagettftext&vote=down "Vote down!")

1


[**_badrou14 at yahoo dot fr_**](https://www.php.net/manual/en/function.imagettftext.php#126038) [¶](https://www.php.net/manual/en/function.imagettftext.php#126038)

**4 years ago**

`for windows you can use this code thanks to Ohmycode
the link of his solution : [https://ohmycode.wordpress.com/2008/09/20/imagettftext-gdfontpath-et-ttf-sous-windows/](https://ohmycode.wordpress.com/2008/09/20/imagettftext-gdfontpath-et-ttf-sous-windows/)
<?php
$font = realpath(".")."\\arial.ttf";

$black = imagecolorallocate($im, 0, 0, 0);

$im = imagecreatetruecolor(400, 30);

imagettftext($im, 20, 0, 10, 20, $black, $font, "coucou");
?>`

[up](https://www.php.net/manual/vote-note.php?id=89505&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=89505&page=function.imagettftext&vote=down "Vote down!")

0


[**_ben at spooty dot net_**](https://www.php.net/manual/en/function.imagettftext.php#89505) [¶](https://www.php.net/manual/en/function.imagettftext.php#89505)

**16 years ago**

`Here's a simple function to wrap text going into an image. It'll wrap onto as many lines as it needs to, but $angle has to be zero. The $width parameter is the width of the image.
<?php
function wrap($fontSize, $angle, $fontFace, $string, $width){

    $ret = "";

    $arr = explode(' ', $string);

    foreach ( $arr as $word ){

        $teststring = $ret.' '.$word;
        $testbox = imagettfbbox($fontSize, $angle, $fontFace, $teststring);
        if ( $testbox[2] > $width ){
            $ret.=($ret==""?"":"\n").$word;
        } else {
            $ret.=($ret==""?"":' ').$word;
        }
    }

    return $ret;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=80473&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80473&page=function.imagettftext&vote=down "Vote down!")

0


[**_matt at mmkennedy dot net_**](https://www.php.net/manual/en/function.imagettftext.php#80473) [¶](https://www.php.net/manual/en/function.imagettftext.php#80473)

**17 years ago**

`For anyone attempting to print black barcodes, and trying to turn of anti-aliasing, remember that -1 * [0,0,0] is 0, not -0.`

[up](https://www.php.net/manual/vote-note.php?id=79705&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=79705&page=function.imagettftext&vote=down "Vote down!")

0


[**_dotpointer_**](https://www.php.net/manual/en/function.imagettftext.php#79705) [¶](https://www.php.net/manual/en/function.imagettftext.php#79705)

**17 years ago**

`For those trying to disable the font smoothing or font cleartype:ing, take a look at the color parameter for this function. The correct word for what you're looking for is antialiasing.`

[up](https://www.php.net/manual/vote-note.php?id=75062&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75062&page=function.imagettftext&vote=down "Vote down!")

0


[**_lassial at gmail dot com_**](https://www.php.net/manual/en/function.imagettftext.php#75062) [¶](https://www.php.net/manual/en/function.imagettftext.php#75062)

**18 years ago**

`Roy van Arem suggested a neat code for listing TTFs on a machine. However, it has some problems (such as lower and upper case distinction of file extension and defective fonts) that I have corrected in the following script, which can be implemented as a single PHP script (name as you like):
<?php //make sure there are no blank lines above

$ffolder="/usr/local/bin/fonts"; //The directory where your fonts reside
if (empty($_GET['f']))
{
$folder=dir($ffolder); //open directory
echo "<HTML><BODY>\n";

while($font=$folder->read())
if(stristr($font,'.ttf')) //only ttf fonts
        $fonts[]=$font;

$folder->close();
if (!empty($fonts))
        {
        echo "<table><tr><th colspan='2'>Fonts available in $ffolder</th></tr>"
        ."\n<tr><th>Name</th><th>Appereance</th>";
        sort($fonts);
        foreach ($fonts as $font)
                echo "<tr><td>$font</td><td> <IMG src='".$_SERVER['SCRIPT_NAME']
                        ."?f=$font'></td></tr>\n";
        }
else echo "No fonts found from $ffolder";
echo "\n</HTML></BODY>";
}
else
{
$im=@imagecreatetruecolor(200,30)
        or die("Cannot Initialize new GD image stream");
$black=imagecolorallocate($im,0,0,0);
$white=imagecolorallocate($im,255,255,255);
imagefill($im,0,0,$white);
imagettftext($im,14,0,5,25,$black, "$ffolder/".$_GET['f'] , $_GET['f']);
header("Content-type: image/png");
header('Content-Length: ' . strlen($im));
imagepng($im);
imagedestroy($im);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=74949&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74949&page=function.imagettftext&vote=down "Vote down!")

0


[**_ultraniblet at gmail dot com_**](https://www.php.net/manual/en/function.imagettftext.php#74949) [¶](https://www.php.net/manual/en/function.imagettftext.php#74949)

**18 years ago**

`I have found the kerning (spacing between letters) pretty poor with GD - it's not up to your average designer's standards. Here are some ways to improve it:
- Place the letters one by one using their bounding box instead of using one string
- adjust with a $kerning value
- For small text, sample it down from a larger size to adjust in increments less than 1px
Eg:
<?PHP
$STRING = "NOTRE PHILOSOPHIE";
// ---- PRESETS
$FONT = "CantoriaMTStd-SemiBold.otf";
$FONT_SIZE = 10.5;
$WIDTH = 200;
$HEIGHT = 16;
$KERNING = 0;
$BASELINE = 12;
$BG_COLOR = array(
    "R"=>5,
    "G"=>45,
    "B"=>53
);
$TXT_COLOR = array(
    "R"=>188,
    "G"=>189,
    "B"=>0
);
// ---- CREATE CANVAS + PALETTE
$canvas = imageCreateTrueColor($WIDTH*4,$HEIGHT*4);
$bg_color = imageColorAllocate($canvas, $BG_COLOR["R"], $BG_COLOR["G"], $BG_COLOR["B"]);
$txt_color = imageColorAllocate($canvas, $TXT_COLOR["R"], $TXT_COLOR["G"], $TXT_COLOR["B"]);
imagefill ( $canvas, 0, 0, $bg_color );
// ---- DRAW
$array = str_split($STRING);
$hpos = 0;
for($i=0; $i<count($array); $i++)
{
    $bbox = imagettftext( $canvas, $FONT_SIZE*4, 0, $hpos, $BASELINE*4, $txt_color, $FONT, $array[$i] );

    $hpos = $bbox[2]+$KERNING;
}
// ---- SAMPLE DOWN & OUTPUT
$final = imageCreateTrueColor($WIDTH,$HEIGHT);
imageCopyResampled( $final, $canvas, 0,0,0,0, $WIDTH, $HEIGHT, $WIDTH*4, $HEIGHT*4 );
header('Content-type: image/png');
imagePNG($final);
imageDestroy($canvas);
imageDestroy($final);
?>`

[up](https://www.php.net/manual/vote-note.php?id=70130&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70130&page=function.imagettftext&vote=down "Vote down!")

0


[**_Tom Pike_**](https://www.php.net/manual/en/function.imagettftext.php#70130) [¶](https://www.php.net/manual/en/function.imagettftext.php#70130)

**19 years ago**

`Ref: Craig at frostycoolslug dot com
"Using the negative of a color index has the effect of turning off antialiasing."
This is true, but only if the image has been created with imagecreate() (as opposed to imagecreatetruecolor())`

[up](https://www.php.net/manual/vote-note.php?id=69972&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=69972&page=function.imagettftext&vote=down "Vote down!")

0


[**_Craig at frostycoolslug dot com_**](https://www.php.net/manual/en/function.imagettftext.php#69972) [¶](https://www.php.net/manual/en/function.imagettftext.php#69972)

**19 years ago**

`This one caught me out a little bit as confusing, so in an attempt to help others..
"Using the negative of a color index has the effect of turning off antialiasing."
Simply put:
<?php
$textColour = ImageColorAllocate($image, 255, 255, 255);
ImageTTFText($image, 8, 0, 0, 0, -$textColour, $font, $text);
?>
Note the - (minus) before the $textColor in ImageTTFText, this creates the negative colour index, and switches off AA on text.`

[up](https://www.php.net/manual/vote-note.php?id=60547&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60547&page=function.imagettftext&vote=down "Vote down!")

0


[**_Mer\`Zikain_**](https://www.php.net/manual/en/function.imagettftext.php#60547) [¶](https://www.php.net/manual/en/function.imagettftext.php#60547)

**19 years ago**

`I was looking for a way to add kerning to my text and finally just made this function to do it. Of course, if you're generating the size of the image based on the text you're putting in it, you'll have to figure out the new size to fit the new text width but I'm sure you can figure that out.
for($i=0;$i<strlen($text);$i++){
        // Get single character
    $value=substr($text,$i,1);
    if($pval){ // check for existing previous character
        list($lx,$ly,$rx,$ry) = imagettfbbox($fontsize,0,$font,$pval);
        $nxpos+=$rx+3;
    }else{
        $nxpos=0;
    }
        // Add the letter to the image
    imagettftext($im, $fontsize, 0, $nxpos, $ypos, $fontcolor, $font, $value);
    $pval=$value; // save current character for next loop
}`

[up](https://www.php.net/manual/vote-note.php?id=63684&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=63684&page=function.imagettftext&vote=down "Vote down!")

 -1


[**_mats dot engstrom at gmail dot com_**](https://www.php.net/manual/en/function.imagettftext.php#63684) [¶](https://www.php.net/manual/en/function.imagettftext.php#63684)

**19 years ago**

`I'll second the note from --colobri--.
Just adding --with-ttf and --with-freetype-dir=/usr/lib/ on the ./configure and then doing a "make; make install" is not enough.
I had to do a "make clean" and then a "make install" in order to get the FreeType-support enabled.
Here are my relevant ./configure lines:
--with-gd \
--enable-gd-native-ttf \
--with-ttf \
--with-freetype-dir=/usr/lib/ \
--with-jpeg-dir=/usr/lib/libjpeg.so.62 \
--enable-exif \`

[up](https://www.php.net/manual/vote-note.php?id=56340&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56340&page=function.imagettftext&vote=down "Vote down!")

 -1


[**_alexey at NOSPAMPLS dot ozerov dot de_**](https://www.php.net/manual/en/function.imagettftext.php#56340) [¶](https://www.php.net/manual/en/function.imagettftext.php#56340)

**20 years ago**

`Notice that the path to the TrueType font has to be included in open_basedir list if open_basedir restriction is activated in php.ini.`

[up](https://www.php.net/manual/vote-note.php?id=80013&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80013&page=function.imagettftext&vote=down "Vote down!")

 -2


[**_denis at reddodo dot com_**](https://www.php.net/manual/en/function.imagettftext.php#80013) [¶](https://www.php.net/manual/en/function.imagettftext.php#80013)

**17 years ago**

`Small but very dangerous bug in function ttfWordWrappedText, written by waage, just try ttfWordWrappedText("aaaaa\naa",4) and your script will run into endless loop.
You can fix it with code below:
<?php
    function ttfWordWrappedText_fixed($text, $strlen = 8) {
    $text = urldecode($text);
    $text = explode("\n", $text);
    $i = 0;
    foreach($text as $text)
    {
        while(strlen($text) > $strlen  && strstr($text, ' ') !== FALSE) {
           $startPoint = strpos($text, ' ');
           $line[$i][] =substr($text,0,$startPoint);
           $text = trim(strstr($text, ' '));
        }
        $line[$i][] = trim($text);
        }
        $line[$i][] = trim($text);
        $i++;
    }

    return $line;
}
?>
better solutions is to check input text for lines longer than needed wrap point.`

[up](https://www.php.net/manual/vote-note.php?id=80012&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80012&page=function.imagettftext&vote=down "Vote down!")

 -2


[**_denis at reddodo dot com_**](https://www.php.net/manual/en/function.imagettftext.php#80012) [¶](https://www.php.net/manual/en/function.imagettftext.php#80012)

**17 years ago**

`Small but very dangerous bug in function ttfWordWrappedText, written by waage, just try ttfWordWrappedText("aaaaa\naa",4) and your script will run into endless loop.
You can fix it with code below:
<?php
    function ttfWordWrappedText_fixed($text, $strlen = 8) {
    $text = urldecode($text);
    $text = explode("\n", $text);

    $i = 0;
    foreach($text as $text)
    {
        while(strlen($text) > $strlen && stristr($text, ' ') !== FALSE) {
           $startPoint = $strlen - 1;
           while(substr($text, $startPoint, 1) != " ") {
                $startPoint--;
           }
           $line[$i][] = trim(substr($text, 0, $startPoint));
           $text = substr($text, $startPoint);
        }
        $line[$i][] = trim($text);
        $i++;
    }

    return $line;
}
?>
better solutions is to check input text for lines longer than needed wrap point.`

[up](https://www.php.net/manual/vote-note.php?id=79024&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=79024&page=function.imagettftext&vote=down "Vote down!")

 -2


[**_waage_**](https://www.php.net/manual/en/function.imagettftext.php#79024) [¶](https://www.php.net/manual/en/function.imagettftext.php#79024)

**17 years ago**

`I had some issues trying to get both word wrapping and new line detection but with some of the help from the comments below i got this. (thanks to jwe for the main part of the code here)
<?php
function ttfWordWrappedText($text, $strlen = 38) {
    $text = urldecode($text);
    $text = explode("\n", $text);

    $i = 0;
    foreach($text as $text)
    {
        while(strlen($text) > $strlen) {
           $startPoint = $strlen - 1;
           while(substr($text, $startPoint, 1) != " ") {
                $startPoint--;
           }
           $line[$i][] = trim(substr($text, 0, $startPoint));
           $text = substr($text, $startPoint);
        }
        $line[$i][] = trim($text);
        $i++;
    }

    return $line;
}
?>
This returns an array for each newline entered and subarray for each wordwrapped line to print.
ie.
Array
(
    [0] => Array
        (
            [0] => This is the first long line
            [1] => that i entered.
        )
    [1] => Array
        (
            [0] => And this is the new line after that.
        )
)`

[up](https://www.php.net/manual/vote-note.php?id=65460&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=65460&page=function.imagettftext&vote=down "Vote down!")

 -2


[**_admin at sgssweb dot com_**](https://www.php.net/manual/en/function.imagettftext.php#65460) [¶](https://www.php.net/manual/en/function.imagettftext.php#65460)

**19 years ago**

`Another way of the bellow. After creating a child class of GMIPluggableSet class, which should override two method: getExpression() and getVariables(), throw it to a instance of FontImageGenerator class.
For example, the code follows:
<?php
require_once 'package.fig.php';
class SampleFontImagePluggableSet
    extends GMIPluggableSet
{
    var $defaultVariables = array(
        "text" => null,
        "size" => null,
        "font" => null,
        "color" => "0x000000",
        "alpha" => "100",
        "padding" => 0,
        "width" => null,
        "height" => null,
        "align" => "left",
        "valign" => "middle",
        "bgcolor" => "0xffffff",
        "antialias" => 4
    );

    function SampleFontImagePluggableSet() {
        parent::GMIPluggableSet();
    }

    function getExpression() {
        return "size {width}, {height};".
               "autoresize none;".
               "type gif, 256, {color: {bgcolor}};".
               "padding {padding};".
               "color {color: {bgcolor}};".
               "fill;".
               "color {color: {color}, {alpha}};".
               "antialias {antialias};".
               "font {font}, {size};".
               "string {text}, 0, 0, {width}, {height}, {align}, {valign};";
    }

    function getVariables() {
        return array_merge($this->defaultVariables, $_GET);
    }
}
$pluggableSet = new SampleFontImagePluggableSet();
$fig = new FontImageGenerator();
$fig->setPluggableSet($pluggableSet);
$fig->execute();
?>
This output a image with the text defined in $_GET['text'], the font in $_GET['font'], the text color in $_GET['color'], the background in $_GET['bgcolor'], and so on.
The script file is available at: [http://sgssweb.com/experiments/?file=PHPFontImageGenerator](http://sgssweb.com/experiments/?file=PHPFontImageGenerator) .`

[up](https://www.php.net/manual/vote-note.php?id=62437&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62437&page=function.imagettftext&vote=down "Vote down!")

 -2


[**_admin at phpru dot com_**](https://www.php.net/manual/en/function.imagettftext.php#62437) [¶](https://www.php.net/manual/en/function.imagettftext.php#62437)

**19 years ago**

`On my conf: php5.1.2+apache 1.33
iconv() function works very well with all cyrillic encodings, so you needn't to write your function like win2uni`

[up](https://www.php.net/manual/vote-note.php?id=68232&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=68232&page=function.imagettftext&vote=down "Vote down!")

 -1


[**_jwe_**](https://www.php.net/manual/en/function.imagettftext.php#68232) [¶](https://www.php.net/manual/en/function.imagettftext.php#68232)

**19 years ago**

`Quick tip for anyone who is receiving text like in the example in this page (ie: through $_GET['text'] or something similar) and needs to format the text into multiple lines.  The trick is finding the spaces...
<?php
$text = $_GET['text'];
// for a maximum of 38 characters on a line...
while(strlen($text) > 38) {
$startPoint = 37;
// find a space to break the line on
while(substr($text, $startPoint, 1) != " ") {
        $startPoint--;
}
$line[] = trim(substr($text, 0, $startPoint));
$text = substr($text, $startPoint);
}
$line[] = trim($text);
?>
The result is an array called $line that contains all the lines of text you need to output in order.
The only tasks left are to determine the correct height of the image based on the font size you want to use.  Don't forget to leave some padding space for punctuation and descenders between lines (commas, g, q, p, y, etc).
imagettftext is unbelievably useful when you need to create header images using non-standard fonts.  Amazing.  Huge thanks to the devs.
--Julian`

[up](https://www.php.net/manual/vote-note.php?id=44127&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=44127&page=function.imagettftext&vote=down "Vote down!")

 -1


[**_plusplus7 at hotmail dot com_**](https://www.php.net/manual/en/function.imagettftext.php#44127) [¶](https://www.php.net/manual/en/function.imagettftext.php#44127)

**21 years ago**

`If you are getting all rectangles instead of text, it may well mean that your ttf font is not opentype, particularly if it is an older freeware one. This requirement didn't exist in older versions so you may find that your font stops working after you upgrade. To fix this problem, try downloading the free MS Volt utility. From there, open your font file, and then click on Compile, and resave.`

[up](https://www.php.net/manual/vote-note.php?id=79233&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=79233&page=function.imagettftext&vote=down "Vote down!")

 -2


[**_Anonymous_**](https://www.php.net/manual/en/function.imagettftext.php#79233) [¶](https://www.php.net/manual/en/function.imagettftext.php#79233)

**17 years ago**

`Just to comment on Sohel Taslims great function...
if anyone needs to add BACKGROUND TRANSPARENCY to this kind of function (which almost does everyone one would want already) then add
$bg_color = imagecolorat($im,1,1);
imagecolortransparent($im, $bg_color);
ABOVE the "if($L_R_C == 0){ //Justify Left"  line`

[up](https://www.php.net/manual/vote-note.php?id=82706&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82706&page=function.imagettftext&vote=down "Vote down!")

 -1


[**_damititi at gmail dot com_**](https://www.php.net/manual/en/function.imagettftext.php#82706) [¶](https://www.php.net/manual/en/function.imagettftext.php#82706)

**17 years ago**

`First of all, thanks sk89q for the func! it was exactly I was looking for.
I made a change. Depending on the letter, the text were incorrect vertical aligned.
I replace the line:
                $line_height = $dimensions[1] - $dimensions[7];
for the following:
                $line_height = $size+4;
No matter if mama or jeje is written, the vertical position will be the same.`

[up](https://www.php.net/manual/vote-note.php?id=81746&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81746&page=function.imagettftext&vote=down "Vote down!")

 -1


[**_llewellyntd at gmail dot com_**](https://www.php.net/manual/en/function.imagettftext.php#81746) [¶](https://www.php.net/manual/en/function.imagettftext.php#81746)

**17 years ago**

`Hi All,
I struggled for moths to do a decent text warp with GD lib. Here is the code that I made use of:
<?php
//word wrap
$warpText = wordwrap($text, 30, "\n");
//display text
imagettftext($image, $fontSize, 0, $x, $y, $fontColor, $font, $warpText);
?>
Hope this helps somebody.
Cheers`

[up](https://www.php.net/manual/vote-note.php?id=81088&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81088&page=function.imagettftext&vote=down "Vote down!")

 -1


[**_m0r1arty at mail dot ru_**](https://www.php.net/manual/en/function.imagettftext.php#81088) [¶](https://www.php.net/manual/en/function.imagettftext.php#81088)

**17 years ago**

`Sorry my English.
I have trouble with using imagettftext under Windows.
I can't used short name of fonts(example "arial","arialbd.ttf" etc). PHP say what not find this font.
Manipulation with environment GDFONTPATH lost.
This is my solution
<?php
$dir=opendir('./font/');//directory with fonts
if($dir)
    while($f=readdir($dir)){
        if(preg_match('/\.ttf$/',$f)){
            $font=explode('.',$f);
            define($font[0],realpath('./font/'.$f));
        }
    }
if($dir)
    closedir($dir);
?>
Directory "font" have two file: arial.ttf and arialbd.ttf
Now one can using constant font name by calling imagettftext:
imagettftext($img,12,0,25,28,$color,arialbd,'some text');`

[up](https://www.php.net/manual/vote-note.php?id=71399&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=71399&page=function.imagettftext&vote=down "Vote down!")

 -1


[**_Roy van Arem_**](https://www.php.net/manual/en/function.imagettftext.php#71399) [¶](https://www.php.net/manual/en/function.imagettftext.php#71399)

**18 years ago**

`If you want to display a list of fonts in a directory and see what they look like, you could do something like this:
<HTML><BODY>
<?php
$folder=dir("fonts/"); //The directory where your fonts reside
while($font=$folder->read())
{
if(stristr($font,'.ttf'))echo '<IMG SRC="img.php?'.substr($font,0,strpos($font,'.')).'">'; //only ttf fonts
}
$folder->close();
?>
</BODY></HTML>
The file for 'img.php' should be something like this:
<?php
$font=$_SERVER["QUERY_STRING"];
header("Content-type: image/png");
$im=@imagecreatetruecolor(200,30)or die("Cannot Initialize new GD image stream");
$black=imagecolorallocate($im,0,0,0);
$white=imagecolorallocate($im,255,255,255);
imagefill($im,0,0,$white);
imagettftext($im,18,0,5,25,$black,"fonts/".$font,$font);
imagepng($im);
imagedestroy($im);
?>
Something similar I implemented at [http://font.beginstart.com](http://font.beginstart.com/)`

[up](https://www.php.net/manual/vote-note.php?id=70946&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70946&page=function.imagettftext&vote=down "Vote down!")

 -2


[**_ben at evolutioncomputing co uk_**](https://www.php.net/manual/en/function.imagettftext.php#70946) [¶](https://www.php.net/manual/en/function.imagettftext.php#70946)

**18 years ago**

`A centralised text watermark - of  any length, that automatically sizes to about 70% of the width, and can be rotated to any angle.
<?php
/* Get image info */
$Image = @ImageCreateFromJPEG ("YourImage.jpg") ;
$sx = imagesx($Image) ;
$sy = imagesy($Image) ;
if ($WatermarkNeeded)
    {
    /* Set text info */
    $Text="Copyright Ben Clay" ;
    $Font="arial.ttf" ;
    $FontColor = ImageColorAllocate ($Image,255,255,255) ;
    $FontShadow = ImageColorAllocate ($Image,0,0,0) ;
    $Rotation = 30 ;
    /* Make a copy image */
    $OriginalImage = ImageCreateTrueColor($sx,$sy) ;
    ImageCopy ($OriginalImage,$Image,0,0,0,0,$sx,$sy) ;
    /* Iterate to get the size up */
    $FontSize=1 ;
    do
        {
        $FontSize *= 1.1 ;
        $Box = @ImageTTFBBox($FontSize,0,$Font,$Text);
        $TextWidth = abs($Box[4] - $Box[0]) ;
        $TextHeight = abs($Box[5] - $Box[1]) ;
        }
    while ($TextWidth < $sx*0.7) ;
    /*  Awkward maths to get the origin of the text in the right place */
    $x = $sx/2 - cos(deg2rad($Rotation))*$TextWidth/2 ;
    $y = $sy/2 + sin(deg2rad($Rotation))*$TextWidth/2 + cos(deg2rad($Rotation))*$TextHeight/2 ;
    /* Make shadow text first followed by solid text */
    ImageTTFText ($Image,$FontSize,$Rotation,$x+4,$y+4,$FontShadow,$Font,$Text);
    ImageTTFText ($Image,$FontSize,$Rotation,$x,$y,$FontColor,$Font,$Text);
    /* merge original image into version with text to show image through text */
    ImageCopyMerge ($Image,$OriginalImage,0,0,0,0,$sx,$sy,50) ;
    }
ImageJPEG ($Image) ;
?>`

[up](https://www.php.net/manual/vote-note.php?id=77739&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77739&page=function.imagettftext&vote=down "Vote down!")

 -2


[**_Ole Clausen_**](https://www.php.net/manual/en/function.imagettftext.php#77739) [¶](https://www.php.net/manual/en/function.imagettftext.php#77739)

**18 years ago**

`Comment to: Sohel Taslim (03-Aug-2007 06:19)
Thanks for the function which I have modified a bit. In the new version the lines have equal space between them (the g's in your example create bigger space between the lines) - set by the parameter '$Leading'.
I have used the for-loop for better performance and slimmed the rest a little  :)
    /**
     * @name                    : makeImageF
     *
     * Function for create image from text with selected font. Justify text in image (0-Left, 1-Right, 2-Center).
     *
     * @param String $text     : String to convert into the Image.
     * @param String $font     : Font name of the text. Kip font file in same folder.
     * @param int    $Justify  : Justify text in image (0-Left, 1-Right, 2-Center).
     * @param int    $Leading  : Space between lines.
     * @param int    $W        : Width of the Image.
     * @param int    $H        : Hight of the Image.
     * @param int    $X        : x-coordinate of the text into the image.
     * @param int    $Y        : y-coordinate of the text into the image.
     * @param int    $fsize    : Font size of text.
     * @param array  $color    : RGB color array for text color.
     * @param array  $bgcolor  : RGB color array for background.
     *
     */
    function imagettfJustifytext($text, $font="CENTURY.TTF", $Justify=2, $Leading=0, $W=0, $H=0, $X=0, $Y=0, $fsize=12, $color=array(0x0,0x0,0x0), $bgcolor=array(0xFF,0xFF,0xFF)){

        $angle = 0;
        $_bx = imageTTFBbox($fsize,0,$font,$text);
        $s = split("[\n]+", $text);  // Array of lines
        $nL = count($s);  // Number of lines
        $W = ($W==0)?abs($_bx[2]-$_bx[0]):$W;    // If Width not initialized by programmer then it will detect and assign perfect width.
        $H = ($H==0)?abs($_bx[5]-$_bx[3])+($nL>1?($nL*$Leading):0):$H;    // If Height not initialized by programmer then it will detect and assign perfect height.

        $im = @imagecreate($W, $H)
            or die("Cannot Initialize new GD image stream");

        $background_color = imagecolorallocate($im, $bgcolor[0], $bgcolor[1], $bgcolor[2]);  // RGB color background.
        $text_color = imagecolorallocate($im, $color[0], $color[1], $color[2]); // RGB color text.

        if ($Justify == 0){ //Justify Left
            imagettftext($im, $fsize, $angle, $X, $fsize, $text_color, $font, $text);
        } else {
            // Create alpha-nummeric string with all international characters - both upper- and lowercase
            $alpha = range("a", "z");
            $alpha = $alpha.strtoupper($alpha).range(0, 9);
            // Use the string to determine the height of a line
            $_b = imageTTFBbox($fsize,0,$font,$alpha);
            $_H = abs($_b[5]-$_b[3]);
            $__H=0;
            for ($i=0; $i<$nL; $i++) {
                $_b = imageTTFBbox($fsize,0,$font,$s[$i]);
                $_W = abs($_b[2]-$_b[0]);
                //Defining the X coordinate.
                if ($Justify == 1) $_X = $W-$_W;  // Justify Right
                else $_X = abs($W/2)-abs($_W/2);  // Justify Center

                //Defining the Y coordinate.
                $__H += $_H;
                imagettftext($im, $fsize, $angle, $_X, $__H, $text_color, $font, $s[$i]);
                $__H += $Leading;
            }
        }

        return $im;
    }`

[up](https://www.php.net/manual/vote-note.php?id=117209&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117209&page=function.imagettftext&vote=down "Vote down!")

 -3


[**_simbiat at bk dot ru_**](https://www.php.net/manual/en/function.imagettftext.php#117209) [¶](https://www.php.net/manual/en/function.imagettftext.php#117209)

**10 years ago**

`Another way to wrap and center using wordwrap and learning the number of lines in the result of that wordwrap
<?php
$text="privet privet privet privet privet privet2 privet2 privet2 privet2 privet2 privet3";
$text=wordwrap($text, 35, "\n", TRUE);
//setting the image header in order to proper display the image
header("Content-Type: image/png");
//try to create an image
$im = @imagecreate(460, 215)
    or die("Cannot Initialize new GD image stream");
//set the background color of the image
$background_color = imagecolorallocate($im, 0x00, 0x00, 0x00);
//set the color for the text
$text_color = imagecolorallocate($im, 0xFF, 0xFF, 0xFF);
//adf the string to the image
$font = "verdana.ttf";
$font_size = 20;
$angle = 0;
$splittext = explode ( "\n" , $text );
$lines = count($splittext);
foreach ($splittext as $text) {
    $text_box = imagettfbbox($font_size,$angle,$font,$text);
    $text_width = abs(max($text_box[2], $text_box[4]));
    $text_height = abs(max($text_box[5], $text_box[7]));
    $x = (imagesx($im) - $text_width)/2;
    $y = ((imagesy($im) + $text_height)/2)-($lines-2)*$text_height;
    $lines=$lines-1;
    imagettftext($im, $font_size, $angle, $x, $y, $text_color, $font, $text);
}
imagepng($im);
imagedestroy($im);
?>`

[up](https://www.php.net/manual/vote-note.php?id=76728&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76728&page=function.imagettftext&vote=down "Vote down!")

 -3


[**_Borgso_**](https://www.php.net/manual/en/function.imagettftext.php#76728) [¶](https://www.php.net/manual/en/function.imagettftext.php#76728)

**18 years ago**

`Right align out of "webmaster at higher-designs dot com" code
<?php
$color = imagecolorallocate($im, 0, 0, 0);
$font = 'visitor.ttf';
$fontsize = "12";
$fontangle = "0";
$imagewidth = imagesx($im);
$imageheight = imagesy($im);
$text = "My right align text";
$box = @imageTTFBbox($fontsize,$fontangle,$font,$text);
$textwidth = abs($box[4] - $box[0]);
$textheight = abs($box[5] - $box[1]);
$xcord = $imagewidth - ($textwidth)-2; // 2 = some space from right side.
$ycord = ($imageheight/2)+($textheight/2);
ImageTTFText ($im, $fontsize, $fontangle, $xcord, $ycord, $black, $font, $text);
?>`

[up](https://www.php.net/manual/vote-note.php?id=61227&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=61227&page=function.imagettftext&vote=down "Vote down!")

 -3


[**_--Colibri--_**](https://www.php.net/manual/en/function.imagettftext.php#61227) [¶](https://www.php.net/manual/en/function.imagettftext.php#61227)

**19 years ago**

`If you have configured and compiled PHP with all the necessary command-line options and still get the error:
Fatal error: Call to undefined function imagettftext()
Try doing a "make clean"  before building the php apache module:
./configure [...]
make clean
make
make install
This may solve your problem (and hopefully keep you from wasting hours trying different compile options!)`

[up](https://www.php.net/manual/vote-note.php?id=50599&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=50599&page=function.imagettftext&vote=down "Vote down!")

 -3


[**_erik\[at\]phpcastle.com_**](https://www.php.net/manual/en/function.imagettftext.php#50599) [¶](https://www.php.net/manual/en/function.imagettftext.php#50599)

**20 years ago**

`Remember!!!
When uploading a font to your website you have to set the transfer mode to binary. It took me some time to find out :P. Tried to download the font from my website and it was spoiled.
In your script, the path to your font, use realpath("arial.ttf") so there is no confusion about that.`

[up](https://www.php.net/manual/vote-note.php?id=68366&page=function.imagettftext&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=68366&page=function.imagettftext&vote=down "Vote down!")

 -4


[**_jwe_**](https://www.php.net/manual/en/function.imagettftext.php#68366) [¶](https://www.php.net/manual/en/function.imagettftext.php#68366)

**19 years ago**

`I found this line a little confusing:
"May include decimal numeric character references (of the form: &#8364;) to access characters in a font beyond position 127."
I was using a font that had apostrophes and quotes stored in a non-standard position, and so they were being rendered as spaces by imagettftext.  This line seemed to suggest a solution, but it took a while to figure it out.
Turns out, a "decimal numeric character reference" is a decimal conversion of the hex value of the *unicode* position of the character you want.  For a while I was trying ASCII positions (I knew the ALT+ code for typing the character I needed in Windows).
In the Windows XP character map, the unicode positions are shown as U+2018 or U+201C, etc.  Ignore the U+ and convert that hex number to decimal, and then stick that in your text string with the &# on the front and ; on the end, and pass it to imagettftext.
--Julian`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagettftext&repo=en&redirect=https://www.php.net/manual/en/function.imagettftext.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google