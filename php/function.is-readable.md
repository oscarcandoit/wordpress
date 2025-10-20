---
url: https://www.php.net/manual/en/function.is-readable.php
scraped_at: 2025-10-20T02:53:06.990Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# is\_readable

(PHP 4, PHP 5, PHP 7, PHP 8)

is\_readable — Tells whether a file exists and is readable

### Description [¶](https://www.php.net/manual/en/function.is-readable.php\#refsect1-function.is-readable-description)

**is\_readable**([string](https://www.php.net/manual/en/language.types.string.php) `$filename`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Tells whether a file exists and is readable.


### Parameters [¶](https://www.php.net/manual/en/function.is-readable.php\#refsect1-function.is-readable-parameters)

`filename`

Path to the file.


### Return Values [¶](https://www.php.net/manual/en/function.is-readable.php\#refsect1-function.is-readable-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if the file or directory specified by
`filename` exists and is readable, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.is-readable.php\#refsect1-function.is-readable-errors)

Upon failure, an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is emitted.

### Examples [¶](https://www.php.net/manual/en/function.is-readable.php\#refsect1-function.is-readable-examples)

**Example #1 **is\_readable()** example**

`<?php
$filename = 'test.txt';
if (is_readable($filename)) {
    echo 'The file is readable';
} else {
    echo 'The file is not readable';
}
?>`

### Notes [¶](https://www.php.net/manual/en/function.is-readable.php\#refsect1-function.is-readable-notes)

Keep in mind that PHP may be accessing the file as the user
id that the web server runs as (often 'nobody').


> **Note**: The results of this
> function are cached. See [clearstatcache()](https://www.php.net/manual/en/function.clearstatcache.php) for
> more details.

**Tip**

As of PHP 5.0.0, this function
can also be used with _some_ URL wrappers. Refer to
[Supported Protocols and Wrappers](https://www.php.net/manual/en/wrappers.php) to determine which wrappers support
[stat()](https://www.php.net/manual/en/function.stat.php) family of functionality.

> **Note**:
>
>
> The check is done using the real UID/GID instead of the effective one.

This function may return **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** for directories. Use
[is\_dir()](https://www.php.net/manual/en/function.is-dir.php) to distinguish file and directory.


### See Also [¶](https://www.php.net/manual/en/function.is-readable.php\#refsect1-function.is-readable-seealso)

- [is\_writable()](https://www.php.net/manual/en/function.is-writable.php) \- Tells whether the filename is writable
- [file\_exists()](https://www.php.net/manual/en/function.file-exists.php) \- Checks whether a file or directory exists
- [fgets()](https://www.php.net/manual/en/function.fgets.php) \- Gets line from file pointer

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/filesystem/functions/is-readable.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.is-readable%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.is-readable&repo=en&redirect=https://www.php.net/manual/en/function.is-readable.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=61293&page=function.is-readable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=61293&page=function.is-readable&vote=down "Vote down!")

8


[**_jo at durchholz dot org_**](https://www.php.net/manual/en/function.is-readable.php#61293) [¶](https://www.php.net/manual/en/function.is-readable.php#61293)

**19 years ago**

`DrTebi at yahoo dot com is wrong. is_readable() checks whether you can do file_get_contents() or similar calls, no more, no less. If the location given returns a 500 or 403 error, you can still read() that (you'll simply get the error page), but it's still read()able. Using is_readable to check the validity of a URL is simply the wrong function.`

[up](https://www.php.net/manual/vote-note.php?id=92618&page=function.is-readable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92618&page=function.is-readable&vote=down "Vote down!")

1


[**_pgl at yoyo dot org_**](https://www.php.net/manual/en/function.is-readable.php#92618) [¶](https://www.php.net/manual/en/function.is-readable.php#92618)

**16 years ago**

`Note that is_readable() will return false for streams, eg, php://stdin.`

[up](https://www.php.net/manual/vote-note.php?id=130325&page=function.is-readable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130325&page=function.is-readable&vote=down "Vote down!")

0


[**_johninen at gmail dot com_**](https://www.php.net/manual/en/function.is-readable.php#130325) [¶](https://www.php.net/manual/en/function.is-readable.php#130325)

**4 months ago**

`This will return false on urls, even if file_get_contents() reads them. So, only for files.`

[up](https://www.php.net/manual/vote-note.php?id=118668&page=function.is-readable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118668&page=function.is-readable&vote=down "Vote down!")

0


[**_arikan134 at gmail dot com_**](https://www.php.net/manual/en/function.is-readable.php#118668) [¶](https://www.php.net/manual/en/function.is-readable.php#118668)

**9 years ago**

`is readable recursively. Check all sub directories and files readable
<?php
function is_readable_r($dir) {
    if (is_dir($dir)) {
        if(is_readable($dir)){
            $objects = scandir($dir);
            foreach ($objects as $object) {
                if ($object != "." && $object != "..") {
                    if (!is_readable_r($dir."/".$object)) return false;
                    else continue;
                }
            }
            return true;
        }else{
            return false;
        }

    }else if(file_exists($dir)){
        return (is_readable($dir));

    }
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.is-readable&repo=en&redirect=https://www.php.net/manual/en/function.is-readable.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google