---
url: https://www.php.net/manual/en/function.imagecreatefromstring.php
scraped_at: 2025-10-20T02:50:11.792Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imagecreatefromstring

(PHP 4 >= 4.0.4, PHP 5, PHP 7, PHP 8)

imagecreatefromstring — Create a new image from the image stream in the string

### Description [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php\#refsect1-function.imagecreatefromstring-description)

**imagecreatefromstring**([string](https://www.php.net/manual/en/language.types.string.php) `$data`): [GdImage](https://www.php.net/manual/en/class.gdimage.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

**imagecreatefromstring()** returns an image identifier
representing the image obtained from the given `data`.
These types will be automatically detected if your build of PHP supports
them: JPEG, PNG, GIF, BMP, WBMP, GD2, WEBP and AVIF.


### Parameters [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php\#refsect1-function.imagecreatefromstring-parameters)

`data`

A string containing the image data.


### Return Values [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php\#refsect1-function.imagecreatefromstring-returnvalues)

An image object will be returned on success. **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** is returned if
the image type is unsupported, the data is not in a recognised format,
or the image is corrupt and cannot be loaded.


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php\#refsect1-function.imagecreatefromstring-errors)

**imagecreatefromstring()** raises an E\_WARNING level error,
if the data is not in a recognized format.


### Changelog [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php\#refsect1-function.imagecreatefromstring-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | On success, this function returns a [GDImage](https://www.php.net/manual/en/class.gdimage.php) instance now;<br> previously, a [resource](https://www.php.net/manual/en/language.types.resource.php) was returned. |
| 7.3.0 | WEBP is supported now (if supported by the libgd in use). |

### Examples [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php\#refsect1-function.imagecreatefromstring-examples)

**Example #1 **imagecreatefromstring()** example**

`<?php
$data = 'iVBORw0KGgoAAAANSUhEUgAAABwAAAASCAMAAAB/2U7WAAAABl'
       . 'BMVEUAAAD///+l2Z/dAAAASUlEQVR4XqWQUQoAIAxC2/0vXZDr'
       . 'EX4IJTRkb7lobNUStXsB0jIXIAMSsQnWlsV+wULF4Avk9fLq2r'
       . '8a5HSE35Q3eO2XP1A1wQkZSgETvDtKdQAAAABJRU5ErkJggg==';
$data = base64_decode($data);
$im = imagecreatefromstring($data);
if ($im !== false) {
    header('Content-Type: image/png');
    imagepng($im);
}
else {
    echo 'An error occurred.';
}
?>`

The above example will output
something similar to:

![Output of example : imagecreatefromstring()](https://www.php.net/manual/en/images/21009b70229598c6a80eef8b45bf282b-imagecreatefromstring.png)

### See Also [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php\#refsect1-function.imagecreatefromstring-seealso)

- [imagecreatefromjpeg()](https://www.php.net/manual/en/function.imagecreatefromjpeg.php) \- Create a new image from file or URL
- [imagecreatefrompng()](https://www.php.net/manual/en/function.imagecreatefrompng.php) \- Create a new image from file or URL
- [imagecreatefromgif()](https://www.php.net/manual/en/function.imagecreatefromgif.php) \- Create a new image from file or URL
- [imagecreatetruecolor()](https://www.php.net/manual/en/function.imagecreatetruecolor.php) \- Create a new true color image

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/image/functions/imagecreatefromstring.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imagecreatefromstring%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagecreatefromstring&repo=en&redirect=https://www.php.net/manual/en/function.imagecreatefromstring.php)

### User Contributed Notes 16 notes

[up](https://www.php.net/manual/vote-note.php?id=85909&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85909&page=function.imagecreatefromstring&vote=down "Vote down!")

30


[**_ville dot jungman at gmail dot com_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#85909) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#85909)

**17 years ago**

`While downloading images from internet, it's easiest to let php decide what is the file type. So, forget using imagecreatefromjpg, imagecreatefromgif and imagecreatefrompng. Instead, this is the way to go:
<?php
$src = " [http://www.varuste.net/tiedostot/l\_ylabanneri.jpg](http://www.varuste.net/tiedostot/l_ylabanneri.jpg)";
$image = imagecreatefromstring(file_get_contents($src));
?>`

[up](https://www.php.net/manual/vote-note.php?id=94254&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94254&page=function.imagecreatefromstring&vote=down "Vote down!")

9


[**_php dot net at phor dot net_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#94254) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#94254)

**15 years ago**

`My site allows anonymous uploads to a web-accessible location (that will execute a script if it finds one).
Naturally, I need to verify that only harmless content is accepted. I am expecting only images, so I use:
<?php
$im = $imagecreatefromstring($USERFILE);
$valid = ($im != FALSE);
imagedestroy($im);
return $valid;
?>`

[up](https://www.php.net/manual/vote-note.php?id=118792&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118792&page=function.imagecreatefromstring&vote=down "Vote down!")

5


[**_anon at dude dot com_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#118792) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#118792)

**9 years ago**

`[Editor's note: BMP will be supported as of PHP 7.2.0.]
In case it's not obvious from the lack of "imagecreatefrombmp()" in GD, this function cannot handle plain old BMP files either.`

[up](https://www.php.net/manual/vote-note.php?id=124150&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124150&page=function.imagecreatefromstring&vote=down "Vote down!")

4


[**_chris at haydenwheeler dot com_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#124150) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#124150)

**6 years ago**

`imagecreatefromstring does not appear to support WebP images (tested on PHP 7.2.10, with GD 2.1.0 and GD WebP support enabled)`

[up](https://www.php.net/manual/vote-note.php?id=92823&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92823&page=function.imagecreatefromstring&vote=down "Vote down!")

5


[**_logan at logansbailey dot com_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#92823) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#92823)

**16 years ago**

`So you guys don't spend an hour trying to figure out why your script keeps running out of memory when you're using this or the other imagecreatefrom functions.  GD uncompresses the image when you use these functions, and this can lead to your script running out of memory.
If you download a rawimage save it on your computer to jpeg so the file size comes down, GD will automatically convert it to the raw and you can possibly run out of memory.`

[up](https://www.php.net/manual/vote-note.php?id=77792&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77792&page=function.imagecreatefromstring&vote=down "Vote down!")

1


[**_Blizzke at gmail dot com_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#77792) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#77792)

**18 years ago**

`I use dynamically generated images that require a little touch-up before being displayed. So essentially I do some base work, then store the images in a memory cache (APC), reload the images again from the cache later on "into" GD, do final processing and then display the image.
Since I wanted to avoid a lot of disc access I used the output buffering functions:
<?php
// Do your image processing stuff

// Start buffering
ob_start ( );
ImageGD ( $hImage );
$sImage = ob_get_contents ( );
ob_end_clean ( );
// Put stuff into cache

// Reload from cache and recreate image
$hImage = imagecreatefromstring ( $sImage );
// Do final editing stuff and output image
?>
Of course this is a condensed example but I just wanted to share the idea.`

[up](https://www.php.net/manual/vote-note.php?id=104147&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104147&page=function.imagecreatefromstring&vote=down "Vote down!")

2


[**_hope at it-helps dot com_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#104147) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#104147)

**14 years ago**

`Create an image resource from file, without knowing image type:
<?php
function imagecreatefromfile($imagepath=false) {
    if(!$imagepath || !$is_readable($imagepath) return false;
    return @imagecreatefromstring(file_get_contents($imagepath));
}
$img_resource=imagecreatefromfile($imagepath);
?>`

[up](https://www.php.net/manual/vote-note.php?id=62351&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62351&page=function.imagecreatefromstring&vote=down "Vote down!")

0


[**_junkmail at pmobl dot com_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#62351) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#62351)

**19 years ago**

`I know a lot of people have been having trouble using images from the Sprint PPC6700 with GD.  The jpeg library always thows an error about 16 bytes of extraneous data.  I decided to poke around in a hex editor and found those extraneous bytes occur right at the end of the exif data.
By removing this extraneous data, images can easily be manipulated by GD and the EXIF extension as a normal images.  This also removes any problems using the images with GIMP which must rely on the same jpeg libraries.
Here is a function that will check to see if an image is from the PPC6700 and then remove the extraneous data for you.  The result can successully be used with imagecreatefromstring
Author: Paul Visco
IM: paulsidekick
Created: 2-12-06
function checkFixPPC6700($orig){
    //get the file contents
    $data = file_get_contents($orig);
    //if its a PPC 6700 image cut out the extraneous 16 bits
    if(strstr($data, "\x41\x70\x61\x63\x68\x65\x00\x48")){
//this next line can all be one string I split it up so the form on php.net would accept it
        $bad_data ="\x00\x10\x4A\x46" . "\x49\x46\x00\x01\x01" . "\x00\x00\x01\x00\x01\x00\x00";
        return substr_replace($data, "", strpos($data, $bad_data),
        strlen($bad_data));
    } else {
        //if not from a PPC 6700 return data unaltered
         return $data;
    }
}`

[up](https://www.php.net/manual/vote-note.php?id=124517&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124517&page=function.imagecreatefromstring&vote=down "Vote down!")

 -2


[**_adeline dot duterre at boxify dot be_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#124517) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#124517)

**5 years ago**

`Many websites add, during the conversion from .jpg / .png to base64 some words before the base64 string : "data:image/png;base64,"
If you let them, the PHP function will return an error "Data is not in a recognized format in".
If you have this situation :
$image_string=str_replace("data:image/png;base64,","",$image_string);
$image_string = base64_decode($image_string);
$img = imagecreatefromstring($image_string);`

[up](https://www.php.net/manual/vote-note.php?id=56260&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56260&page=function.imagecreatefromstring&vote=down "Vote down!")

 -1


[**_alexandrebr at ignorethis dot gmail dot com_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#56260) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#56260)

**20 years ago**

`An easy example to help understanding this function...
<?
$loadFile = " [http://static.php.net/images/php.gif](http://static.php.net/images/php.gif)";
$im = imagecreatefromstring(file_get_contents($loadFile));
// identical to imagecreatefromgif($loadFile);
imagegif($im);
?>
The function will try to auto-determine file format (jpg, gif, png....), and will return false if fails.`

[up](https://www.php.net/manual/vote-note.php?id=55114&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=55114&page=function.imagecreatefromstring&vote=down "Vote down!")

 -3


[**_paul at epeeps dot net_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#55114) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#55114)

**20 years ago**

`I run a blogging site that allowed users to publish images from their cell phones.  For some reason, the nokia 3220 produces jpegs with extrandeous data before the EOF 0xFFF9
I wrote this class to allow you to fix the images so that they can be used with GD to resize and manipulate.  Without applying the fix both GD and gimp report errors for the file.  If basically keeps eating bytes from the junk part till the file is a valid jpeg.  Here is an example bunk pic written by a nokia 3220 that you cna test it with [http://www.shawnrider.com/moblog/cache/0854747001121624103.jpg](http://www.shawnrider.com/moblog/cache/0854747001121624103.jpg)
/*
Author: Paul Visco
Hompage: [http://www.elmwoodstrip.com?u=paul](http://www.elmwoodstrip.com/?u=paul)
AIM: paulsidekick
Notes:  The file allows you fix the jpegs created by the Nokia 3220 picture phone so that they can be manipulated using the GD library with PHP.
Usage:  Simply instanitiate the class and then call the fix method for each image.
e.g.
$nokia = new nokia;
$nokia->debug ="y";
$nokia->fix("yourpic.jpg");
*/
class nokia
{
    public $file;
    public $debug = "n";
    public $dir_name = "";
    private $img; //the image created from the string
    private $str;

    function fix($file)
    {

        //set the file to fix
        $this->file = $file;

        //load the file into a string
        $this->str = file_get_contents($this->file);

        //test to see if it is a nokia image or if it has been corrupted previously
        if (substr_count($this->str, chr(0x28).chr(0x36).chr(0x28).chr(0x2B)) == 0 || @imagecreatefromstring($this->str))
        {
            if ($this->debug =="y")
            {
                echo "\n<br />".$this->file." is not a corrupted Nokia pic";
            }

            return true;
        }

        //make a directory for fixed images if it doesn't exist and is specified
        if(!empty($this->dir_name) && !is_dir($this->dir_name))
        {
            @mkdir($this->dir_name, 0777);
        }

        //strip out the funk e crap from the file
        $this->eat($this->str);

        //write the file back to itself
        file_put_contents($this->dir_name.$this->file, $this->str);
        //return true for fixed
        return true;
    }

    function eat()
    {

        //check the image
        $this->img = @imagecreatefromstring($this->str);

        //if the image doesn't work then keep striping out crap
        while(!$this->img)
        {
            //cut off the bad bytes one by one
            $this->str= substr_replace($this->str, "", -3, -2);

            //check the image again
            $this->img = @imagecreatefromstring($this->str);
        }

        if ($this->debug =="y")
        {
            //notify the user it's fixed
            echo "\n<br />Nasty bits eaten!! ".$this->file." is fixed now thanks to p:labs!";
        }
        return true;
    }
}`

[up](https://www.php.net/manual/vote-note.php?id=34677&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=34677&page=function.imagecreatefromstring&vote=down "Vote down!")

 -3


[**_not given_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#34677) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#34677)

**22 years ago**

`A note to the previous question (if you still don't know it :))...
GIF's are 256 colors (or 8 bit), and the resample function needs true color I guess... that's why it works with JPG's and not with GIF's.
Next thing... you take a string, write it to file, open the file (imagecreatefromgif), and delete the file again.
if you do imagecreatefromstring($string) you can skip the temporary file part.`

[up](https://www.php.net/manual/vote-note.php?id=85614&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85614&page=function.imagecreatefromstring&vote=down "Vote down!")

 -4


[**_nfo\[NOSPAM\] at safernetworks dot net_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#85614) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#85614)

**17 years ago**

`The only way I managed to resolve the loading of image files from file data either on local site or from off-site protocols is as follows. I hope this saves someone else the two hours of debugging and looking for good examples.
[PHP]
<?php
$sFile = " [http://www.justgreatwine.co.uk/img/vineyard.jpg](http://www.justgreatwine.co.uk/img/vineyard.jpg)";
$imagedata = GetFileData($sFile); //load the file in 4k chunks
/*=======THE OUTPUT=========*/
ob_start();
// assuming you have image data in $imagedata
$length = strlen($imagedata);
header('Last-Modified: '.date('r'));
header('Accept-Ranges: bytes');
header('Content-Length: '.$length);
header('Content-Type: image/jpeg');
print($imagedata);
ob_end_flush();
/*======FUNCTIONS USED======*/
function GetFileData($sFilePath){
    $fp = fopen($sFilePath, 'rb') or die('404! Unable to open file!');
    $buf = '';
    while(!feof($fp)){
        $buf .= fgets($fp, 4096);
    }
    fclose($fp);
return $buf; //returns False if failed, else the contents up to FileSize bytes.
}
?>
[/PHP]`

[up](https://www.php.net/manual/vote-note.php?id=31178&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=31178&page=function.imagecreatefromstring&vote=down "Vote down!")

 -5


[**_shiehj at yahoo dot com_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#31178) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#31178)

**22 years ago**

`Here is the code I did to create a thumbnail image from the database blob field. The trick is to use "imagecreatefromstring()" to create an image file.
Jack Shieh
<?php
require("dbconfig.inc");
$id = $_GET['id'];
if($id) {
    $link = @mysql_connect($host, $user, $password) or die("Could not connect: " . mysql_error());
    @mysql_select_db($dbname, $link);
    $query = "select filetype, image from pictures where id = $id";
    $result = @mysql_query($query);
    $data = @mysql_result($result,0,"image");
    $type = @mysql_result($result,0,"filetype");

    Header( "Content-type: $type");

    $size = 150;  // new image width
    $src = imagecreatefromstring($data);
    $width = imagesx($src);
    $height = imagesy($src);
    $aspect_ratio = $height/$width;
    if ($width <= $size) {
      $new_w = $width;
      $new_h = $height;
    } else {
      $new_w = $size;
      $new_h = abs($new_w * $aspect_ratio);
    }
    $img = imagecreatetruecolor($new_w,$new_h);
    imagecopyresized($img,$src,0,0,0,0,$new_w,$new_h,$width,$height);

    // determine image type and send it to the client
    if ($type == "image/pjpeg") {
      imagejpeg($img);
    } else if ($type == "image/x-png") {
      imagepng($img);
    } else if ($type == "image/gif") {
      imagegif($img);
    }
    imagedestroy($img);
    mysql_close($link);
};
?>`

[up](https://www.php.net/manual/vote-note.php?id=68048&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=68048&page=function.imagecreatefromstring&vote=down "Vote down!")

 -4


[**_kanzure at gmail dot com_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#68048) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#68048)

**19 years ago**

`Generating graphs in an external program (in this case, gnuplot) may cause problems. This is a solution hacked together in the late hours of night.
<?php
// get the values from, say, a database
$vals = "1 2\\\\n4 8\\\\n"; # etc
// construct the gnuplot_call variable, something like:
$gnuplot_call = "echo \"set term png; plot '<echo -e \\\"$vals\\\" ' ti 'Updated with' with line ; \" | gnuplot";
ob_start();
passthru($gnuplot_call, $gnuplot_call_output);
$image = imagecreatefromstring(ob_get_contents());
ob_end_clean();
imagepng($image); # display
?>`

[up](https://www.php.net/manual/vote-note.php?id=30080&page=function.imagecreatefromstring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=30080&page=function.imagecreatefromstring&vote=down "Vote down!")

 -5


[**_adrian\_schmidt at yahoo dot com_**](https://www.php.net/manual/en/function.imagecreatefromstring.php#30080) [¶](https://www.php.net/manual/en/function.imagecreatefromstring.php#30080)

**22 years ago**

`I'm trying to get the imagecreatefromstring to work with GIFs. Of course, it won't.
I've read the tips but can't get them to work either.
The following is what I tried, based on above tips:
---
    header('Content-Type: image/gif');
    header('Content-Disposition: inline; filename=file.gif');
    $temp = tmpfile();
    fwrite($temp, $line['image']);
    $src_img = imagecreatefromgif($temp);
    fclose($temp); // this removes the file
    $dst_img = imagecreatetruecolor(100, 100);
    imagecopyresampled($dst_img, $src_img, 0,0,0,0, 100,100, imagesx($src_img), imagesy($src_img));

    imagegif($dst_img);
---
where $line['image'] is the gif as taken from my MySQL database...
If anyone that has been able to make something like this work could give me a working piece of code I'd be really greatful!
I would be great if the tempfile could be excluded too...
Below is a working piece of code for jpeg:
---
    header('Content-Type: image/jpeg');
    header('Content-Disposition: inline; filename=file.jpg');

    $src_img = imagecreatefromstring($line['image']);
    $dst_img = imagecreatetruecolor(100, 100);
    imagecopyresampled($dst_img, $src_img, 0,0,0,0, 100,100, imagesx($src_img), imagesy($src_img));

    imagejpeg($dst_img);`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imagecreatefromstring&repo=en&redirect=https://www.php.net/manual/en/function.imagecreatefromstring.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google