---
url: https://www.php.net/manual/en/function.md5-file.php
scraped_at: 2025-10-20T02:54:34.636Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# md5\_file

(PHP 4 >= 4.2.0, PHP 5, PHP 7, PHP 8)

md5\_file — Calculates the md5 hash of a given file

### Description [¶](https://www.php.net/manual/en/function.md5-file.php\#refsect1-function.md5-file-description)

**md5\_file**([string](https://www.php.net/manual/en/language.types.string.php) `$filename`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$binary` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Calculates the MD5 hash of the file specified by the
`filename` parameter using the
[» RSA Data Security, Inc. \\
MD5 Message-Digest Algorithm](https://datatracker.ietf.org/doc/html/rfc1321), and returns that hash.
The hash is a 32-character hexadecimal number.


### Parameters [¶](https://www.php.net/manual/en/function.md5-file.php\#refsect1-function.md5-file-parameters)

`filename`

The filename


`binary`

When **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, returns the digest in raw binary format with a length of
16.


### Return Values [¶](https://www.php.net/manual/en/function.md5-file.php\#refsect1-function.md5-file-returnvalues)

Returns a string on success, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.


### Examples [¶](https://www.php.net/manual/en/function.md5-file.php\#refsect1-function.md5-file-examples)

**Example #1 Usage example of **md5\_file()****

`<?php
$file = '/examples/book.xml';
echo 'MD5 file hash of ' . $file . ': ' . md5_file($file);
?>`

Run code

### See Also [¶](https://www.php.net/manual/en/function.md5-file.php\#refsect1-function.md5-file-seealso)

- [hash\_file()](https://www.php.net/manual/en/function.hash-file.php) \- Generate a hash value using the contents of a given file
- [hash\_init()](https://www.php.net/manual/en/function.hash-init.php) \- Initialize an incremental hashing context
- [md5()](https://www.php.net/manual/en/function.md5.php) \- Calculate the md5 hash of a string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/md5-file.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.md5-file%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.md5-file&repo=en&redirect=https://www.php.net/manual/en/function.md5-file.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=94494&page=function.md5-file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94494&page=function.md5-file&vote=down "Vote down!")

103


[**_Chris_**](https://www.php.net/manual/en/function.md5-file.php#94494) [¶](https://www.php.net/manual/en/function.md5-file.php#94494)

**15 years ago**

`If you just need to find out if two files are identical, comparing file hashes can be inefficient, especially on large files.  There's no reason to read two whole files and do all the math if the second byte of each file is different.  If you don't need to store the hash value for later use, there may not be a need to calculate the hash value just to compare files.  This can be much faster:
<?php
define('READ_LEN', 4096);
if(files_identical('file1.txt', 'file2.txt'))
    echo 'files identical';
else
    echo 'files not identical';
//   pass two file names
//   returns TRUE if files are the same, FALSE otherwise
function files_identical($fn1, $fn2) {
    if(filetype($fn1) !== filetype($fn2))
        return FALSE;
    if(filesize($fn1) !== filesize($fn2))
        return FALSE;
    if(!$fp1 = fopen($fn1, 'rb'))
        return FALSE;
    if(!$fp2 = fopen($fn2, 'rb')) {
        fclose($fp1);
        return FALSE;
    }
    $same = TRUE;
    while (!feof($fp1) and !feof($fp2))
        if(fread($fp1, READ_LEN) !== fread($fp2, READ_LEN)) {
            $same = FALSE;
            break;
        }
    if(feof($fp1) !== feof($fp2))
        $same = FALSE;
    fclose($fp1);
    fclose($fp2);
    return $same;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=107508&page=function.md5-file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107508&page=function.md5-file&vote=down "Vote down!")

11


[**_lukasamd at gmail dot com_**](https://www.php.net/manual/en/function.md5-file.php#107508) [¶](https://www.php.net/manual/en/function.md5-file.php#107508)

**13 years ago**

`It's faster to use md5sum than openssl md5:
<?php
$begin = microtime(true);
$file_path = '../backup_file1.tar.gz';
$result = explode("  ", exec("md5sum $file_path"));
echo "Hash = ".$result[0]."<br />";
# Here 7 other big files (20-300 MB)
$end = microtime(true) - $begin;
echo "Time = $end";
# Time = 4.4475841522217
#Method with openssl
# Time = 12.1463856900543
?>
About 3x faster`

[up](https://www.php.net/manual/vote-note.php?id=81751&page=function.md5-file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81751&page=function.md5-file&vote=down "Vote down!")

 -3


[**_smartin_**](https://www.php.net/manual/en/function.md5-file.php#81751) [¶](https://www.php.net/manual/en/function.md5-file.php#81751)

**17 years ago**

`In response to using exec instead for performance (Nov 13 2007 post), It looks like the performance depends on the size of the file.  See the results below using the same script from the original post.  The first hash is with md5_file and the second is with openssl md5.
With a 1MB file:
Hash = df1555ec0c2d7fcad3a03770f9aa238a; time = 0.005006
Hash = df1555ec0c2d7fcad3a03770f9aa238a; time = 0.01498
With a 2MB file:
Hash = 4387904830a4245a8ab767e5937d722c; time = 0.010393
Hash = 4387904830a4245a8ab767e5937d722c; time = 0.016691
With a 10MB file:
Hash = b89f948e98f3a113dc13fdbd3bdb17ef; time = 0.241907
Hash = b89f948e98f3a113dc13fdbd3bdb17ef; time = 0.037597
Performance seems to change proportionally with the file size.  Judging from the previous post's default file name (.mov) he/she was probably dealing with a large file.  These are just quick tests and far from a perfect benchmark, but you might want to test your own files before assuming that the openssl solution is faster (ie, if working with small text files vs. movies, etc)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.md5-file&repo=en&redirect=https://www.php.net/manual/en/function.md5-file.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google