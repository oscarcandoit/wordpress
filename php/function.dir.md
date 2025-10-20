---
url: https://www.php.net/manual/en/function.dir.php
scraped_at: 2025-10-20T02:57:06.040Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# dir

(PHP 4, PHP 5, PHP 7, PHP 8)

dir — Return an instance of the Directory class

### Description [¶](https://www.php.net/manual/en/function.dir.php\#refsect1-function.dir-description)

**dir**([string](https://www.php.net/manual/en/language.types.string.php) `$directory`, [?](https://www.php.net/manual/en/language.types.null.php)[resource](https://www.php.net/manual/en/language.types.resource.php) `$context` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [Directory](https://www.php.net/manual/en/class.directory.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

A pseudo-object-oriented mechanism for reading a directory. The
given `directory` is opened.


### Parameters [¶](https://www.php.net/manual/en/function.dir.php\#refsect1-function.dir-parameters)

`directory`

Directory to open


`context`

A [context stream](https://www.php.net/manual/en/stream.contexts.php) [resource](https://www.php.net/manual/en/language.types.resource.php).

### Return Values [¶](https://www.php.net/manual/en/function.dir.php\#refsect1-function.dir-returnvalues)

Returns an instance of [Directory](https://www.php.net/manual/en/class.directory.php), or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** in case of error.


### Changelog [¶](https://www.php.net/manual/en/function.dir.php\#refsect1-function.dir-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `context` is now nullable. |

### Examples [¶](https://www.php.net/manual/en/function.dir.php\#refsect1-function.dir-examples)

**Example #1 **dir()** example**

Please note the fashion in which [Directory::read()](https://www.php.net/manual/en/directory.read.php)'s
return value is checked in the example below. We are explicitly
testing whether the return value is identical to (equal to and of
the same type as - see [Comparison Operators](https://www.php.net/manual/en/language.operators.comparison.php) for more information) **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** since
otherwise, any directory entry whose name evaluates to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** will
stop the loop.


`<?php
$d = dir("/etc/php5");
echo "Handle: " . $d->handle . "\n";
echo "Path: " . $d->path . "\n";
while (false !== ($entry = $d->read())) {
echo $entry."\n";
}
$d->close();
?>`

The above example will output
something similar to:

```
Handle: Resource id #2
Path: /etc/php5
.
..
apache
cgi
cli
```

### Notes [¶](https://www.php.net/manual/en/function.dir.php\#refsect1-function.dir-notes)

> **Note**:
>
>
> The order in which directory entries are returned by the read method is
> system-dependent.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/dir/functions/dir.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.dir%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.dir&repo=en&redirect=https://www.php.net/manual/en/function.dir.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=126112&page=function.dir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126112&page=function.dir&vote=down "Vote down!")

9


[**_synnus at gmail dot com_**](https://www.php.net/manual/en/function.dir.php#126112) [¶](https://www.php.net/manual/en/function.dir.php#126112)

**4 years ago**

`<?php
// simple juste use FilesystemIterator
// and you can skip dot and duble dot
// and use it in array
// new FilesystemIterator( PATH , OPTIONS ) : array
$array_file_list = new FilesystemIterator( PATH_ROOT . 'folder/', FilesystemIterator::SKIP_DOTS );
?>`

[up](https://www.php.net/manual/vote-note.php?id=60562&page=function.dir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60562&page=function.dir&vote=down "Vote down!")

8


[**_fordiman at gmail dot com_**](https://www.php.net/manual/en/function.dir.php#60562) [¶](https://www.php.net/manual/en/function.dir.php#60562)

**19 years ago**

`This one's pretty nice.  After getting frustrated for hunting down .jpg files in my massive music collection (PHP would run out of memory), I thought there should be a preg_ls function.
function preg_ls ($path=".", $rec=false, $pat="/.*/") {
    // it's going to be used repeatedly, ensure we compile it for speed.
    $pat=preg_replace("|(/.*/[^S]*)|s", "\\1S", $pat);
    //Remove trailing slashes from path
    while (substr($path,-1,1)=="/") $path=substr($path,0,-1);
    //also, make sure that $path is a directory and repair any screwups
    if (!is_dir($path)) $path=dirname($path);
    //assert either truth or falsehoold of $rec, allow no scalars to mean truth
    if ($rec!==true) $rec=false;
    //get a directory handle
    $d=dir($path);
    //initialise the output array
    $ret=Array();
    //loop, reading until there's no more to read
    while (false!==($e=$d->read())) {
        //Ignore parent- and self-links
        if (($e==".")||($e=="..")) continue;
        //If we're working recursively and it's a directory, grab and merge
        if ($rec && is_dir($path."/".$e)) {
            $ret=array_merge($ret,preg_ls($path."/".$e,$rec,$pat));
            continue;
        }
        //If it don't match, exclude it
        if (!preg_match($pat,$e)) continue;
        //In all other cases, add it to the output array
        $ret[]=$path."/".$e;
    }
    //finally, return the array
    return $ret;
}
Not bad for a mere 18 lines, don't you think?
Example use:
foreach (preg_ls("/etc/X11", true, "/.*\.conf/i") as $file) echo $file."\n";
Output:
/etc/X11/xkb/README.config
/etc/X11/xorg.conf-vesa
/etc/X11/xorg.conf~
/etc/X11/gui.conf
/etc/X11/xorg.conf
/etc/X11/xorg.conf-fbdev`

[up](https://www.php.net/manual/vote-note.php?id=126890&page=function.dir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126890&page=function.dir&vote=down "Vote down!")

2


[**_synnus at gmail dot com_**](https://www.php.net/manual/en/function.dir.php#126890) [¶](https://www.php.net/manual/en/function.dir.php#126890)

**3 years ago**

`<?php
/*
New recursive PHP8
gen array path with  FilesystemIterator
*/
$recurcive_path = [];
rdir(path, $recurcive_path);
var_dump($recurcive_path);
function rdir(string $path, array &$recurcive_path): string
{
    if ($path != '') {
        $recurcive_path[] = $path;
        $array_list = iterator_to_array(new FilesystemIterator($path, FilesystemIterator::SKIP_DOTS));
        foreach ($array_list as $name) {
            $pathname = $name->getpathname();
            if(is_dir($pathname) && $name->getfilename()[0] != '.'){
                $path = rdir($pathname,$recurcive_path);
            }
        }
        return $path;
    }
    return '';
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=62224&page=function.dir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62224&page=function.dir&vote=down "Vote down!")

3


[**_Anonymous_**](https://www.php.net/manual/en/function.dir.php#62224) [¶](https://www.php.net/manual/en/function.dir.php#62224)

**19 years ago**

`Regarding samuel's comment about the dir() function not supporting Unicode properly, it's all in the encoding. The function does NOT internally change Unicode characters into question marks (?), as I was first led to believe. If you simply try to output them in UTF-8, they'll show up just right.`

[up](https://www.php.net/manual/vote-note.php?id=61064&page=function.dir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=61064&page=function.dir&vote=down "Vote down!")

2


[**_samuel dot l at mushicrew dot com_**](https://www.php.net/manual/en/function.dir.php#61064) [¶](https://www.php.net/manual/en/function.dir.php#61064)

**19 years ago**

`Note that the dir object will use the default encoding for non-unicode programs on Windows with PHP 5.x.
So, if you have a file named with characters unsupported by the current default encoding, the dir->read() method will return a wrong entry.
<?php
/*
** This script is on the same directory than a file named with
** unsupported characters for the current default encoding.
*/
$d = dir("./");
while(false !== ($e = $d->read()))
    echo $e . '<br/>';
?>
This will print a "?" for every unsupported characters, and not the right file name. So take care if you check with is_file/is_dir right after enumerating.`

[up](https://www.php.net/manual/vote-note.php?id=101924&page=function.dir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101924&page=function.dir&vote=down "Vote down!")

0


[**_GUILLE@GARGANO_**](https://www.php.net/manual/en/function.dir.php#101924) [¶](https://www.php.net/manual/en/function.dir.php#101924)

**14 years ago**

`to get a dir of [http://www.example.com/directory](http://www.example.com/directory)
<?php
function remotedir($dir)
{
$dir = str_replace(" ", "%20", html_entity_decode($dir));
if (($rh = fopen($dir, 'rb')) === FALSE) { return false; }
$i = 0;
while (!feof($rh)) {
     $archivos = fgetss($rh);
     $directorio[$i++] = trim( substr($archivos,1,strpos($archivos," ",1)) );
}
fclose($rh);
return $directorio;
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.dir&repo=en&redirect=https://www.php.net/manual/en/function.dir.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google