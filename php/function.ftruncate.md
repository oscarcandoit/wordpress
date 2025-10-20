---
url: https://www.php.net/manual/en/function.ftruncate.php
scraped_at: 2025-10-20T02:48:56.189Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ftruncate

(PHP 4, PHP 5, PHP 7, PHP 8)

ftruncate — Truncates a file to a given length

### Description [¶](https://www.php.net/manual/en/function.ftruncate.php\#refsect1-function.ftruncate-description)

**ftruncate**([resource](https://www.php.net/manual/en/language.types.resource.php) `$stream`, [int](https://www.php.net/manual/en/language.types.integer.php) `$size`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Takes the filepointer, `stream`, and truncates the file to
length, `size`.


### Parameters [¶](https://www.php.net/manual/en/function.ftruncate.php\#refsect1-function.ftruncate-parameters)

`stream`

The file pointer.


> **Note**:
>
>
> The `stream` must be open for writing.

`size`

The size to truncate to.


> **Note**:
>
>
> If `size` is larger than the file then the file
> is extended with null bytes.
>
>
> If `size` is smaller than the file then the file
> is truncated to that size.

### Return Values [¶](https://www.php.net/manual/en/function.ftruncate.php\#refsect1-function.ftruncate-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/function.ftruncate.php\#refsect1-function.ftruncate-examples)

**Example #1 File truncation example**

`<?php
$filename = 'lorem_ipsum.txt';
$handle = fopen($filename, 'r+');
ftruncate($handle, rand(1, filesize($filename)));
rewind($handle);
echo fread($handle, filesize($filename));
fclose($handle);
?>`

### Notes [¶](https://www.php.net/manual/en/function.ftruncate.php\#refsect1-function.ftruncate-notes)

> **Note**:
>
>
> The file pointer is _not_ changed.

### See Also [¶](https://www.php.net/manual/en/function.ftruncate.php\#refsect1-function.ftruncate-seealso)

- [fopen()](https://www.php.net/manual/en/function.fopen.php) \- Opens file or URL
- [fseek()](https://www.php.net/manual/en/function.fseek.php) \- Seeks on a file pointer

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/filesystem/functions/ftruncate.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.ftruncate%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ftruncate&repo=en&redirect=https://www.php.net/manual/en/function.ftruncate.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=104455&page=function.ftruncate&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104455&page=function.ftruncate&vote=down "Vote down!")

45


[**_emailfire at gmail dot com_**](https://www.php.net/manual/en/function.ftruncate.php#104455) [¶](https://www.php.net/manual/en/function.ftruncate.php#104455)

**14 years ago**

`If you want to empty a file of it's contents bare in mind that opening a file in w mode truncates the file automatically, so instead of doing...
<?php
$fp = fopen("/tmp/file.txt", "r+");
ftruncate($fp, 0);
fclose($fp);
?>
You can just do...
<?php
$fp = fopen("/tmp/file.txt", "w");
fclose($fp);
?>`

[up](https://www.php.net/manual/vote-note.php?id=117205&page=function.ftruncate&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117205&page=function.ftruncate&vote=down "Vote down!")

19


[**_Julien B._**](https://www.php.net/manual/en/function.ftruncate.php#117205) [¶](https://www.php.net/manual/en/function.ftruncate.php#117205)

**10 years ago**

`You MUST use rewind() after ftruncate() to replace file content`

[up](https://www.php.net/manual/vote-note.php?id=80250&page=function.ftruncate&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80250&page=function.ftruncate&vote=down "Vote down!")

9


[**_rc at opelgt dot org_**](https://www.php.net/manual/en/function.ftruncate.php#80250) [¶](https://www.php.net/manual/en/function.ftruncate.php#80250)

**17 years ago**

`Writing after ftruncate
I didnt expect that I can write in the middle of nowhere. I thought that I would write at the beginning of the file but the first 4 bytes were filled automatically with NULLs followed by "56":
<?php
$str1  = 1234;
$str2  =   56;
$datei = "test.txt";
$dh = fopen($datei,"w");
fwrite($dh, $str1);
fclose($dh);
$dh = fopen ($datei,"r+");
echo "content: ".fread($dh, filesize($datei))."<br>";
echo "pointer after fread at: ".ftell($dh)."<br>";
ftruncate($dh, 0);
echo "pointer after truncate at: ".ftell($dh)."<br>";
fwrite($dh, $str2);
echo "pointer after fwrite at: ".ftell($dh)."<br>";
rewind($dh);
echo "pointer after rewind at: ".ftell($dh)."<br>";
$str = fread($dh, 6);
echo "content: $str<br>in ASCII: ";
for($i = 0; $i < 6; $i++)
echo ord($str{$i})."-";
fclose($dh);
/*
OUTPUT:
content: 1234
pointer after fread at: 4
pointer after truncate at: 4
pointer after fwrite at: 6
pointer after rewind at: 0
content: 56
in ASCII: 0-0-0-0-53-54
*/
?>
So not only ftruncate is filling an empty file up with NULLs as in the note before. Fread is filling leading space with NULLs too.`

[up](https://www.php.net/manual/vote-note.php?id=125539&page=function.ftruncate&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125539&page=function.ftruncate&vote=down "Vote down!")

2


[**_Masoud_**](https://www.php.net/manual/en/function.ftruncate.php#125539) [¶](https://www.php.net/manual/en/function.ftruncate.php#125539)

**4 years ago**

`The problem that rc at opelgt dot org mentioned seems completely logical.
When pointer is at offset 4 and you truncate file, the pointer is still at offset 4.
So when you write(), the first 4 bytes are filled with null byte by Operating System - There is nothing wrong by PHP. And it's filled with null byte, because there is data on disk and that needs to be cleared with zero bits.
Even though this is a Operating System's gotcha, to avoid data corruption, PHP Docs should mention it clearly. Also it would be nice if PHP automatically sets the pointer's offset to SEEK_END  after truncating to an smaller size to fool-proof it.`

[up](https://www.php.net/manual/vote-note.php?id=103591&page=function.ftruncate&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103591&page=function.ftruncate&vote=down "Vote down!")

1


[**_eurosat7 at yahoo dot de_**](https://www.php.net/manual/en/function.ftruncate.php#103591) [¶](https://www.php.net/manual/en/function.ftruncate.php#103591)

**14 years ago**

`If you want to ftruncate but keep the end:
<?php
    function ftruncatestart($filename,$maxfilesize){
        $size=filesize($filename);
        if ($size<$maxfilesize*1.0) return;
        $maxfilesize=$maxfilesize*0.5; //we don't want to do it too often...
        $fh=fopen($filename,"r+");
        $start=ftell($fh);
        fseek($fh,-$maxfilesize,SEEK_END);
        $drop=fgets($fh);
        $offset=ftell($fh);
        for ($x=0;$x<$maxfilesize;$x++){
            fseek($fh,$x+$offset);
            $c=fgetc($fh);
            fseek($fh,$x);
            fwrite($fh,$c);
        }
        ftruncate($fh,$maxfilesize-strlen($drop));
        fclose($fh);
    }
?>
It will not just cut it but search for a newline so you avoid corrupting your csv or logfiles. But I don't know if you will stress the reading head of your drive. ;)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ftruncate&repo=en&redirect=https://www.php.net/manual/en/function.ftruncate.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google