---
url: https://www.php.net/manual/en/function.is-writable.php
scraped_at: 2025-10-20T02:54:46.896Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# is\_writable

(PHP 4, PHP 5, PHP 7, PHP 8)

is\_writable — Tells whether the filename is writable

### Description [¶](https://www.php.net/manual/en/function.is-writable.php\#refsect1-function.is-writable-description)

**is\_writable**([string](https://www.php.net/manual/en/language.types.string.php) `$filename`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if the `filename` exists and is
writable. The filename argument may be a directory name allowing you
to check if a directory is writable.


Keep in mind that PHP may be accessing the file as the user id
that the web server runs as (often 'nobody').


### Parameters [¶](https://www.php.net/manual/en/function.is-writable.php\#refsect1-function.is-writable-parameters)

`filename`

The filename being checked.


### Return Values [¶](https://www.php.net/manual/en/function.is-writable.php\#refsect1-function.is-writable-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if the `filename` exists and is
writable.


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.is-writable.php\#refsect1-function.is-writable-errors)

Upon failure, an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is emitted.

### Examples [¶](https://www.php.net/manual/en/function.is-writable.php\#refsect1-function.is-writable-examples)

**Example #1 **is\_writable()** example**

`<?php
$filename = 'test.txt';
if (is_writable($filename)) {
    echo 'The file is writable';
} else {
    echo 'The file is not writable';
}
?>`

### Notes [¶](https://www.php.net/manual/en/function.is-writable.php\#refsect1-function.is-writable-notes)

> **Note**: The results of this
> function are cached. See [clearstatcache()](https://www.php.net/manual/en/function.clearstatcache.php) for
> more details.

**Tip**

As of PHP 5.0.0, this function
can also be used with _some_ URL wrappers. Refer to
[Supported Protocols and Wrappers](https://www.php.net/manual/en/wrappers.php) to determine which wrappers support
[stat()](https://www.php.net/manual/en/function.stat.php) family of functionality.

### See Also [¶](https://www.php.net/manual/en/function.is-writable.php\#refsect1-function.is-writable-seealso)

- [is\_readable()](https://www.php.net/manual/en/function.is-readable.php) \- Tells whether a file exists and is readable
- [file\_exists()](https://www.php.net/manual/en/function.file-exists.php) \- Checks whether a file or directory exists
- [fwrite()](https://www.php.net/manual/en/function.fwrite.php) \- Binary-safe file write

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/filesystem/functions/is-writable.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.is-writable%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.is-writable&repo=en&redirect=https://www.php.net/manual/en/function.is-writable.php)

### User Contributed Notes 9 notes

[up](https://www.php.net/manual/vote-note.php?id=120625&page=function.is-writable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120625&page=function.is-writable&vote=down "Vote down!")

21


[**_helvete at bahno dot net_**](https://www.php.net/manual/en/function.is-writable.php#120625) [¶](https://www.php.net/manual/en/function.is-writable.php#120625)

**8 years ago**

`Be warned, that is_writable returns false for non-existent files, although they can be written to the queried path.`

[up](https://www.php.net/manual/vote-note.php?id=129793&page=function.is-writable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129793&page=function.is-writable&vote=down "Vote down!")

8


[**_h3ssan at protonmail dot com_**](https://www.php.net/manual/en/function.is-writable.php#129793) [¶](https://www.php.net/manual/en/function.is-writable.php#129793)

**1 year ago**

`In Linux, you might encountering an issue which is a file is not writable even tho it has 644 permission! The problem is with SELinux, just disable it or add rules to allow it.`

[up](https://www.php.net/manual/vote-note.php?id=80990&page=function.is-writable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80990&page=function.is-writable&vote=down "Vote down!")

8


[**_starrychloe at yahoo dot com_**](https://www.php.net/manual/en/function.is-writable.php#80990) [¶](https://www.php.net/manual/en/function.is-writable.php#80990)

**17 years ago**

`To Darek and F Dot: About group permissions, there is this note in the php.ini file:
; By default, Safe Mode does a UID compare check when
; opening files. If you want to relax this to a GID compare,
; then turn on safe_mode_gid.
safe_mode_gid = Off`

[up](https://www.php.net/manual/vote-note.php?id=118667&page=function.is-writable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118667&page=function.is-writable&vote=down "Vote down!")

5


[**_arikan134 at gmail dot com_**](https://www.php.net/manual/en/function.is-writable.php#118667) [¶](https://www.php.net/manual/en/function.is-writable.php#118667)

**9 years ago**

`Check director is writable recursively. to return true, all of directory contents  must be writable
<?php
function is_writable_r($dir) {
    if (is_dir($dir)) {
        if(is_writable($dir)){
            $objects = scandir($dir);
            foreach ($objects as $object) {
                if ($object != "." && $object != "..") {
                    if (!is_writable_r($dir."/".$object)) return false;
                    else continue;
                }
            }
            return true;
        }else{
            return false;
        }

    }else if(file_exists($dir)){
        return (is_writable($dir));

    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=61331&page=function.is-writable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=61331&page=function.is-writable&vote=down "Vote down!")

8


[**_darek at fauxaddress dot com_**](https://www.php.net/manual/en/function.is-writable.php#61331) [¶](https://www.php.net/manual/en/function.is-writable.php#61331)

**19 years ago**

`It appears that is_writable() does not check full permissions of a file to determine whether the current user can write to it.  For example, with Apache running as user 'www', and a member of the group 'wheel', is_writable() returns false on a file like
-rwxrwxr-x           root         wheel          /etc/some.file`

[up](https://www.php.net/manual/vote-note.php?id=41194&page=function.is-writable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=41194&page=function.is-writable&vote=down "Vote down!")

4


[**_agrenier at assertex dot com_**](https://www.php.net/manual/en/function.is-writable.php#41194) [¶](https://www.php.net/manual/en/function.is-writable.php#41194)

**21 years ago**

`This file_write() function will give $filename the write permission before writing $content to it.
Note that many servers do not allow file permissions to be changed by the PHP user.
<?php
    function file_write($filename, &$content) {
        if (!is_writable($filename)) {
            if (!chmod($filename, 0666)) {
                 echo "Cannot change the mode of file ($filename)";
                 exit;
            };
        }
        if (!$fp = @fopen($filename, "w")) {
            echo "Cannot open file ($filename)";
            exit;
        }
        if (fwrite($fp, $content) === FALSE) {
            echo "Cannot write to file ($filename)";
            exit;
        }
        if (!fclose($fp)) {
            echo "Cannot close file ($filename)";
            exit;
        }
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=56673&page=function.is-writable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56673&page=function.is-writable&vote=down "Vote down!")

2


[**_JimmyNighthawk_**](https://www.php.net/manual/en/function.is-writable.php#56673) [¶](https://www.php.net/manual/en/function.is-writable.php#56673)

**20 years ago**

`Regarding you might recognize your files on your web contructed by your PHP-scripts are grouped as NOBODY you can avoid this problem by setting up an FTP-Connection ("ftp_connect", "ftp_raw", etc.) and use methods like "ftp_fput" to create these [instead of giving out rights so you can use the usual "unsecure" way]. This will give the files created not the GROUP NOBODY - it will give out the GROUP your FTP-Connection via your FTP-Program uses, too.
Furthermore you might want to hash the password for the FTP-Connection - then check out:
[http://dev.mysql.com/doc/mysql/en/Password\_hashing.html](http://dev.mysql.com/doc/mysql/en/Password_hashing.html)`

[up](https://www.php.net/manual/vote-note.php?id=100267&page=function.is-writable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100267&page=function.is-writable&vote=down "Vote down!")

2


[**_gr_**](https://www.php.net/manual/en/function.is-writable.php#100267) [¶](https://www.php.net/manual/en/function.is-writable.php#100267)

**15 years ago**

`The results of this function seems to be not cached :
Tested on linux and windows
<?php
chmod($s_pathFichier, 0400);
echo'<pre>';var_dump(is_writable($s_pathFichier));echo'</pre>';
chmod($s_pathFichier, 04600);
echo'<pre>';var_dump(is_writable($s_pathFichier));echo'</pre>';
exit;
?>`

[up](https://www.php.net/manual/vote-note.php?id=127479&page=function.is-writable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127479&page=function.is-writable&vote=down "Vote down!")

1


[**_develop at radon-software dot net_**](https://www.php.net/manual/en/function.is-writable.php#127479) [¶](https://www.php.net/manual/en/function.is-writable.php#127479)

**3 years ago**

`This function returns always false on windows, when you check an network drive.
See PHP Bug [https://bugs.php.net/bug.php?id=68926](https://bugs.php.net/bug.php?id=68926)
See [https://stackoverflow.com/q/54904676](https://stackoverflow.com/q/54904676)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.is-writable&repo=en&redirect=https://www.php.net/manual/en/function.is-writable.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google