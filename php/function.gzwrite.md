---
url: https://www.php.net/manual/en/function.gzwrite.php
scraped_at: 2025-10-20T02:52:53.106Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# gzwrite

(PHP 4, PHP 5, PHP 7, PHP 8)

gzwrite — Binary-safe gz-file write

### Description [¶](https://www.php.net/manual/en/function.gzwrite.php\#refsect1-function.gzwrite-description)

**gzwrite**([resource](https://www.php.net/manual/en/language.types.resource.php) `$stream`, [string](https://www.php.net/manual/en/language.types.string.php) `$data`, [?](https://www.php.net/manual/en/language.types.null.php)[int](https://www.php.net/manual/en/language.types.integer.php) `$length` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [int](https://www.php.net/manual/en/language.types.integer.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

**gzwrite()** writes the contents of
`data` to the given gz-file.


### Parameters [¶](https://www.php.net/manual/en/function.gzwrite.php\#refsect1-function.gzwrite-parameters)

`stream`

The gz-file pointer. It must be valid, and must point to a file
successfully opened by [gzopen()](https://www.php.net/manual/en/function.gzopen.php).


`data`

The string to write.


`length`

The number of uncompressed bytes to write. If supplied, writing will
stop after `length` (uncompressed) bytes have been
written or the end of `data` is reached,
whichever comes first.


### Return Values [¶](https://www.php.net/manual/en/function.gzwrite.php\#refsect1-function.gzwrite-returnvalues)


Returns the number of (uncompressed) bytes written to the given gz-file
stream, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Changelog [¶](https://www.php.net/manual/en/function.gzwrite.php\#refsect1-function.gzwrite-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `length` is nullable now; previously, the default was<br> `0`. |
| 7.4.0 | This functions returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure now; previously `0` was returned. |

### Examples [¶](https://www.php.net/manual/en/function.gzwrite.php\#refsect1-function.gzwrite-examples)

**Example #1 **gzwrite()** example**

`<?php
$string = 'Some information to compress';
$gz = gzopen('somefile.gz','w9');
gzwrite($gz, $string);
gzclose($gz);
?>`

### See Also [¶](https://www.php.net/manual/en/function.gzwrite.php\#refsect1-function.gzwrite-seealso)

- [gzread()](https://www.php.net/manual/en/function.gzread.php) \- Binary-safe gz-file read
- [gzopen()](https://www.php.net/manual/en/function.gzopen.php) \- Open gz-file

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/zlib/functions/gzwrite.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.gzwrite%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.gzwrite&repo=en&redirect=https://www.php.net/manual/en/function.gzwrite.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=88746&page=function.gzwrite&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88746&page=function.gzwrite&vote=down "Vote down!")

3


[**_calmarius at nospam dot atw dot hu_**](https://www.php.net/manual/en/function.gzwrite.php#88746) [¶](https://www.php.net/manual/en/function.gzwrite.php#88746)

**16 years ago**

`gz compression is often used with tar archives. Building tar archives is quite easy. Here is a code snipplet which can be used for building tar archives before compressing them to tar.gz.
<?php
//\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\
// Adds file header to the tar file, it is used before adding file content.
// f: file resource (provided by eg. fopen)
// phisfn: path to file
// archfn: path to file in archive, directory names must be followed by '/'
//\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\
function TarAddHeader($f,$phisfn,$archfn)
{
    $info=stat($phisfn);
    $ouid=sprintf("%6s ", decoct($info[4]));
    $ogid=sprintf("%6s ", decoct($info[5]));
    $omode=sprintf("%6s ", decoct(fileperms($phisfn)));
    $omtime=sprintf("%11s", decoct(filemtime($phisfn)));
    if (@is_dir($phisfn))
    {
         $type="5";
         $osize=sprintf("%11s ", decoct(0));
    }
    else
    {
         $type='';
         $osize=sprintf("%11s ", decoct(filesize($phisfn)));
         clearstatcache();
    }
    $dmajor = '';
    $dminor = '';
    $gname = '';
    $linkname = '';
    $magic = '';
    $prefix = '';
    $uname = '';
    $version = '';
    $chunkbeforeCS=pack("a100a8a8a8a12A12",$archfn, $omode, $ouid, $ogid, $osize, $omtime);
    $chunkafterCS=pack("a1a100a6a2a32a32a8a8a155a12", $type, $linkname, $magic, $version, $uname, $gname, $dmajor, $dminor ,$prefix,'');
    $checksum = 0;
    for ($i=0; $i<148; $i++) $checksum+=ord(substr($chunkbeforeCS,$i,1));
    for ($i=148; $i<156; $i++) $checksum+=ord(' ');
    for ($i=156, $j=0; $i<512; $i++, $j++)    $checksum+=ord(substr($chunkafterCS,$j,1));
    fwrite($f,$chunkbeforeCS,148);
    $checksum=sprintf("%6s ",decoct($checksum));
    $bdchecksum=pack("a8", $checksum);
    fwrite($f,$bdchecksum,8);
    fwrite($f,$chunkafterCS,356);
    return true;
}
//\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/
// Writes file content to the tar file must be called after a TarAddHeader
// f:file resource provided by fopen
// phisfn: path to file
//\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/
function TarWriteContents($f,$phisfn)
{
    if (@is_dir($phisfn))
    {
        return;
    }
    else
    {
        $size=filesize($phisfn);
        $padding=$size % 512 ? 512-$size%512 : 0;
        $f2=fopen($phisfn,"rb");
        while (!feof($f2)) fwrite($f,fread($f2,1024*1024));
        $pstr=sprintf("a%d",$padding);
        fwrite($f,pack($pstr,''));
    }
}
//\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/
// Adds 1024 byte footer at the end of the tar file
// f: file resource
//\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/
function TarAddFooter($f)
{
    fwrite($f,pack('a1024',''));
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=34955&page=function.gzwrite&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=34955&page=function.gzwrite&vote=down "Vote down!")

2


[**_Kioob_**](https://www.php.net/manual/en/function.gzwrite.php#34955) [¶](https://www.php.net/manual/en/function.gzwrite.php#34955)

**22 years ago**

`This is a short example of use gzwrite function.
<?php
function gzcompressfile($source,$level=false){
    $dest=$source.'.gz';
    $mode='wb'.$level;
    $error=false;
    if($fp_out=gzopen($dest,$mode)){
        if($fp_in=fopen($source,'rb')){
            while(!feof($fp_in))
                gzwrite($fp_out,fread($fp_in,1024*512));
            fclose($fp_in);
            }
          else $error=true;
        gzclose($fp_out);
        }
      else $error=true;
    if($error) return false;
      else return $dest;
    }
?>
the function gzcompressfile() compress a file 'data.csv' to 'data.csv.gz'. the function return false if error, and the new file name if it's ok.`

[up](https://www.php.net/manual/vote-note.php?id=100799&page=function.gzwrite&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100799&page=function.gzwrite&vote=down "Vote down!")

0


[**_Take Heed_**](https://www.php.net/manual/en/function.gzwrite.php#100799) [¶](https://www.php.net/manual/en/function.gzwrite.php#100799)

**14 years ago**

`Read the description of gzwrite() very carefully.  If the 'length' option is not specified, then the input data will have slashes stripped on systems where magic quotes are enabled.  This is important information to know when compressing files.
<?php
$data = fread($fp, 5000);
gzwrite($fp2, $data, strlen($data));
?>
Is the correct way to avoid issues with magic quotes.`

[up](https://www.php.net/manual/vote-note.php?id=82108&page=function.gzwrite&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82108&page=function.gzwrite&vote=down "Vote down!")

0


[**_Anonymous_**](https://www.php.net/manual/en/function.gzwrite.php#82108) [¶](https://www.php.net/manual/en/function.gzwrite.php#82108)

**17 years ago**

`katzlbtjunk's method is certainly shorter, but it is unusable for anything except small files.  It would try to load the whole file into memory, then create an entire compressed copy, and only then write it to disk.  The other method given below will not exhaust memory like that.`

[up](https://www.php.net/manual/vote-note.php?id=88682&page=function.gzwrite&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88682&page=function.gzwrite&vote=down "Vote down!")

 -4


[**_repository at lamaresh dot net_**](https://www.php.net/manual/en/function.gzwrite.php#88682) [¶](https://www.php.net/manual/en/function.gzwrite.php#88682)

**16 years ago**

`This function add a line to a .gz compressed file
<?php
function AppendLineGz($file,$string) {
    if (file_exists($file)) {
        $lines = gzfile($file);
        $lines[count($lines)] = "$string\r\n";
        $input=implode($lines);
    } else {$input="$string\r\n";}
    $gz = gzopen($file,'w9');
    gzwrite($gz, $input);
    gzclose($gz);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=81314&page=function.gzwrite&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81314&page=function.gzwrite&vote=down "Vote down!")

 -5


[**_katzlbtjunk at hotmail dot com_**](https://www.php.net/manual/en/function.gzwrite.php#81314) [¶](https://www.php.net/manual/en/function.gzwrite.php#81314)

**17 years ago**

`How about this instead:
$s = file_get_contents('file.tar');
file_put_contents('file.tar.gz',gzencode($s,9));`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.gzwrite&repo=en&redirect=https://www.php.net/manual/en/function.gzwrite.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google