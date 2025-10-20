---
url: https://www.php.net/manual/en/function.scandir.php
scraped_at: 2025-10-20T02:49:17.562Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# scandir

(PHP 5, PHP 7, PHP 8)

scandir — List files and directories inside the specified path

### Description [¶](https://www.php.net/manual/en/function.scandir.php\#refsect1-function.scandir-description)

**scandir**([string](https://www.php.net/manual/en/language.types.string.php) `$directory`, [int](https://www.php.net/manual/en/language.types.integer.php) `$sorting_order` = **`[SCANDIR\_SORT\_ASCENDING](https://www.php.net/manual/en/dir.constants.php#constant.scandir-sort-ascending)`**, [?](https://www.php.net/manual/en/language.types.null.php)[resource](https://www.php.net/manual/en/language.types.resource.php) `$context` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [array](https://www.php.net/manual/en/language.types.array.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Returns an [array](https://www.php.net/manual/en/language.types.array.php) of files and directories from the
`directory`.


### Parameters [¶](https://www.php.net/manual/en/function.scandir.php\#refsect1-function.scandir-parameters)

`directory`

The directory that will be scanned.


`sorting_order`

By default, the sorted order is alphabetical in ascending order. If
the optional `sorting_order` is set to
**`[SCANDIR\_SORT\_DESCENDING](https://www.php.net/manual/en/dir.constants.php#constant.scandir-sort-descending)`**, then the sort order is
alphabetical in descending order. If it is set to
**`[SCANDIR\_SORT\_NONE](https://www.php.net/manual/en/dir.constants.php#constant.scandir-sort-none)`** then the result is unsorted.


`context`

For a description of the `context` parameter,
refer to [the streams section](https://www.php.net/manual/en/ref.stream.php) of
the manual.


### Return Values [¶](https://www.php.net/manual/en/function.scandir.php\#refsect1-function.scandir-returnvalues)

Returns an [array](https://www.php.net/manual/en/language.types.array.php) of filenames on success, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on
failure. If `directory` is not a directory, then
boolean **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** is returned, and an error of level
**`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is generated.


### Changelog [¶](https://www.php.net/manual/en/function.scandir.php\#refsect1-function.scandir-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `context` is now nullable. |

### Examples [¶](https://www.php.net/manual/en/function.scandir.php\#refsect1-function.scandir-examples)

**Example #1 A simple **scandir()** example**

`<?php
$dir    = '/tmp';
$files1 = scandir($dir);
$files2 = scandir($dir, SCANDIR_SORT_DESCENDING);
print_r($files1);
print_r($files2);
?>`

The above example will output
something similar to:

```
Array
(
    [0] => .
    [1] => ..
    [2] => bar.php
    [3] => foo.txt
    [4] => somedir
)
Array
(
    [0] => somedir
    [1] => foo.txt
    [2] => bar.php
    [3] => ..
    [4] => .
)
```

### Notes [¶](https://www.php.net/manual/en/function.scandir.php\#refsect1-function.scandir-notes)

**Tip**

A URL can be used as a
filename with this function if the [fopen wrappers](https://www.php.net/manual/en/filesystem.configuration.php#ini.allow-url-fopen) have been enabled.
See [fopen()](https://www.php.net/manual/en/function.fopen.php) for more details on how to specify the
filename. See the [Supported Protocols and Wrappers](https://www.php.net/manual/en/wrappers.php) for links to information
about what abilities the various wrappers have, notes on their usage,
and information on any predefined variables they may
provide.

### See Also [¶](https://www.php.net/manual/en/function.scandir.php\#refsect1-function.scandir-seealso)

- [opendir()](https://www.php.net/manual/en/function.opendir.php) \- Open directory handle
- [readdir()](https://www.php.net/manual/en/function.readdir.php) \- Read entry from directory handle
- [glob()](https://www.php.net/manual/en/function.glob.php) \- Find pathnames matching a pattern
- [is\_dir()](https://www.php.net/manual/en/function.is-dir.php) \- Tells whether the filename is a directory
- [sort()](https://www.php.net/manual/en/function.sort.php) \- Sort an array in ascending order

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/dir/functions/scandir.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.scandir%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.scandir&repo=en&redirect=https://www.php.net/manual/en/function.scandir.php)

### User Contributed Notes 16 notes

[up](https://www.php.net/manual/vote-note.php?id=107215&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107215&page=function.scandir&vote=down "Vote down!")

865


[**_dwieeb at gmail dot com_**](https://www.php.net/manual/en/function.scandir.php#107215) [¶](https://www.php.net/manual/en/function.scandir.php#107215)

**13 years ago**

`Easy way to get rid of the dots that scandir() picks up in Linux environments:
<?php
$directory = '/path/to/my/directory';
$scanned_directory = array_diff(scandir($directory), array('..', '.'));
?>`

[up](https://www.php.net/manual/vote-note.php?id=110570&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110570&page=function.scandir&vote=down "Vote down!")

178


[**_mmda dot nl at gmail dot com_**](https://www.php.net/manual/en/function.scandir.php#110570) [¶](https://www.php.net/manual/en/function.scandir.php#110570)

**12 years ago**

`Here is my 2 cents. I wanted to create an array of my directory structure recursively. I wanted to easely access data in a certain directory using foreach. I came up with the following:
<?php
function dirToArray($dir) {

$result = array();
$cdir = scandir($dir);
foreach ($cdir as $key => $value)
{
      if (!in_array($value,array(".","..")))
      {
         if (is_dir($dir . DIRECTORY_SEPARATOR . $value))
         {
            $result[$value] = dirToArray($dir . DIRECTORY_SEPARATOR . $value);
         }
         else
         {
            $result[] = $value;
         }
      }
}

return $result;
}
?>
Output
Array
(
[subdir1] => Array
(
      [0] => file1.txt
      [subsubdir] => Array
      (
         [0] => file2.txt
         [1] => file3.txt
      )
)
[subdir2] => Array
(
    [0] => file4.txt
}
)`

[up](https://www.php.net/manual/vote-note.php?id=122438&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122438&page=function.scandir&vote=down "Vote down!")

29


[**_info at remark dot no_**](https://www.php.net/manual/en/function.scandir.php#122438) [¶](https://www.php.net/manual/en/function.scandir.php#122438)

**7 years ago**

`Someone wrote that array_slice could be used to quickly remove directory entries "." and "..". However, "-" is a valid entry that would come before those, so array_slice would remove the wrong entries.`

[up](https://www.php.net/manual/vote-note.php?id=107117&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107117&page=function.scandir&vote=down "Vote down!")

23


[**_kodlee at kodleeshare dot net_**](https://www.php.net/manual/en/function.scandir.php#107117) [¶](https://www.php.net/manual/en/function.scandir.php#107117)

**13 years ago**

`I needed to find a way to get the full path of all files in the directory and all subdirectories of a directory.
Here's my solution: Recursive functions!
<?php
function find_all_files($dir)
{
    $root = scandir($dir);
    foreach($root as $value)
    {
        if($value === '.' || $value === '..') {continue;}
        if(is_file("$dir/$value")) {$result[]="$dir/$value";continue;}
        foreach(find_all_files("$dir/$value") as $value)
        {
            $result[]=$value;
        }
    }
    return $result;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=114184&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114184&page=function.scandir&vote=down "Vote down!")

18


[**_gambit\_642 AT hotmailDOTcom_**](https://www.php.net/manual/en/function.scandir.php#114184) [¶](https://www.php.net/manual/en/function.scandir.php#114184)

**11 years ago**

`Needed something that could return the contents of single or multiple directories, recursively or non-recursively,
for all files or specified file extensions that would be
accessible easily from any scope or script.
And I wanted to allow overloading cause sometimes I'm too lazy to pass all params.
<?php
class scanDir {
    static private $directories, $files, $ext_filter, $recursive;
// ----------------------------------------------------------------------------------------------
    // scan(dirpath::string|array, extensions::string|array, recursive::true|false)
    static public function scan(){
        // Initialize defaults
        self::$recursive = false;
        self::$directories = array();
        self::$files = array();
        self::$ext_filter = false;
        // Check we have minimum parameters
        if(!$args = func_get_args()){
            die("Must provide a path string or array of path strings");
        }
        if(gettype($args[0]) != "string" && gettype($args[0]) != "array"){
            die("Must provide a path string or array of path strings");
        }
        // Check if recursive scan | default action: no sub-directories
        if(isset($args[2]) && $args[2] == true){self::$recursive = true;}
        // Was a filter on file extensions included? | default action: return all file types
        if(isset($args[1])){
            if(gettype($args[1]) == "array"){self::$ext_filter = array_map('strtolower', $args[1]);}
            else
            if(gettype($args[1]) == "string"){self::$ext_filter[] = strtolower($args[1]);}
        }
        // Grab path(s)
        self::verifyPaths($args[0]);
        return self::$files;
    }
    static private function verifyPaths($paths){
        $path_errors = array();
        if(gettype($paths) == "string"){$paths = array($paths);}
        foreach($paths as $path){
            if(is_dir($path)){
                self::$directories[] = $path;
                $dirContents = self::find_contents($path);
            } else {
                $path_errors[] = $path;
            }
        }
        if($path_errors){echo "The following directories do not exists<br />";die(var_dump($path_errors));}
    }
    // This is how we scan directories
    static private function find_contents($dir){
        $result = array();
        $root = scandir($dir);
        foreach($root as $value){
            if($value === '.' || $value === '..') {continue;}
            if(is_file($dir.DIRECTORY_SEPARATOR.$value)){
                if(!self::$ext_filter || in_array(strtolower(pathinfo($dir.DIRECTORY_SEPARATOR.$value, PATHINFO_EXTENSION)), self::$ext_filter)){
                    self::$files[] = $result[] = $dir.DIRECTORY_SEPARATOR.$value;
                }
                continue;
            }
            if(self::$recursive){
                foreach(self::find_contents($dir.DIRECTORY_SEPARATOR.$value) as $value) {
                    self::$files[] = $result[] = $value;
                }
            }
        }
        // Return required for recursive search
        return $result;
    }
}
?>
Usage:
scanDir::scan(path(s):string|array, [file_extensions:string|array], [subfolders?:true|false]);
<?php
//Scan a single directory for all files, no sub-directories
$files = scanDir::scan('D:\Websites\temp');
//Scan multiple directories for all files, no sub-dirs
$dirs = array(
    'D:\folder';
    'D:\folder2';
    'C:\Other';
);
$files = scanDir::scan($dirs);
// Scan multiple directories for files with provided file extension,
// no sub-dirs
$files = scanDir::scan($dirs, "jpg");
//or with an array of extensions
$file_ext = array(
    "jpg",
    "bmp",
    "png"
);
$files = scanDir::scan($dirs, $file_ext);
// Scan multiple directories for files with any extension,
// include files in recursive sub-folders
$files = scanDir::scan($dirs, false, true);
// Multiple dirs, with specified extensions, include sub-dir files
$files = scanDir::scan($dirs, $file_ext, true);
?>`

[up](https://www.php.net/manual/vote-note.php?id=115871&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115871&page=function.scandir&vote=down "Vote down!")

48


[**_eep2004 at ukr dot net_**](https://www.php.net/manual/en/function.scandir.php#115871) [¶](https://www.php.net/manual/en/function.scandir.php#115871)

**11 years ago**

`Fastest way to get a list of files without dots.
<?php
$files = array_slice(scandir('/path/to/directory/'), 2);`

[up](https://www.php.net/manual/vote-note.php?id=123647&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123647&page=function.scandir&vote=down "Vote down!")

5


[**_artmanniako at gmail dot com_**](https://www.php.net/manual/en/function.scandir.php#123647) [¶](https://www.php.net/manual/en/function.scandir.php#123647)

**6 years ago**

`How i solved problem with '.' and '..'
$x = scandir__DIR__; //any directory
foreach ($x as $key => $value) {
        if ('.' !== $value && '..' !== $value){
               echo $value;
}
}
Simple and working`

[up](https://www.php.net/manual/vote-note.php?id=126663&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126663&page=function.scandir&vote=down "Vote down!")

5


[**_coolbikram0 at gmail dot com_**](https://www.php.net/manual/en/function.scandir.php#126663) [¶](https://www.php.net/manual/en/function.scandir.php#126663)

**3 years ago**

`A simple recursive function to list all files and subdirectories in a directory:
<?php
function listAllFiles($dir) {
$array = array_diff(scandir($dir), array('.', '..'));

foreach ($array as &$item) {
    $item = $dir . $item;
}
unset($item);
foreach ($array as $item) {
    if (is_dir($item)) {
     $array = array_merge($array, listAllFiles($item . DIRECTORY_SEPARATOR));
    }
}
return $array;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=52755&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=52755&page=function.scandir&vote=down "Vote down!")

3


[**_Pawel Dlugosz_**](https://www.php.net/manual/en/function.scandir.php#52755) [¶](https://www.php.net/manual/en/function.scandir.php#52755)

**20 years ago**

`For directory containing files like (for example) -.jpg the results of scandir are a little "weird" ;)
<?php

$dir = '/somedir';
$files = scandir($dir);
print_r($files);
?>
Array
(
    [0] => -.jpg
    [1] => .
    [2] => ..
    [3] => foo.txt
    [4] => somedir
)
Beware - sorting is in ASCII order :)`

[up](https://www.php.net/manual/vote-note.php?id=46872&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=46872&page=function.scandir&vote=down "Vote down!")

3


[**_Stan P. van de Burgt_**](https://www.php.net/manual/en/function.scandir.php#46872) [¶](https://www.php.net/manual/en/function.scandir.php#46872)

**20 years ago**

`scandir() with regexp matching on file name and sorting options based on stat().
<?php
function myscandir($dir, $exp, $how='name', $desc=0)
{
    $r = array();
    $dh = @opendir($dir);
    if ($dh) {
        while (($fname = readdir($dh)) !== false) {
            if (preg_match($exp, $fname)) {
                $stat = stat("$dir/$fname");
                $r[$fname] = ($how == 'name')? $fname: $stat[$how];
            }
        }
        closedir($dh);
        if ($desc) {
            arsort($r);
        }
        else {
            asort($r);
        }
    }
    return(array_keys($r));
}
$r = myscandir('./book/', '/^article[0-9]{4}\.txt$/i', 'ctime', 1);
print_r($r);
?>
files can be sorted on name and stat() attributes, ascending and descending:
name    file name
dev     device number
ino     inode number
mode    inode protection mode
nlink   number of links
uid     userid of owner
gid     groupid of owner
rdev    device type, if inode device *
size    size in bytes
atime   time of last access (Unix timestamp)
mtime   time of last modification (Unix timestamp)
ctime   time of last inode change (Unix timestamp)
blksize blocksize of filesystem IO *
blocks  number of blocks allocated`

[up](https://www.php.net/manual/vote-note.php?id=119422&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119422&page=function.scandir&vote=down "Vote down!")

1


[**_simon dot riget at gmail dot com_**](https://www.php.net/manual/en/function.scandir.php#119422) [¶](https://www.php.net/manual/en/function.scandir.php#119422)

**9 years ago**

`This is a simple and versatile function that returns an array tree of files, matching wildcards:
<?php
// List files in tree, matching wildcards * and ?
function tree($path){
static $match;
// Find the real directory part of the path, and set the match parameter
$last=strrpos($path,"/");
if(!is_dir($path)){
    $match=substr($path,$last);
    while(!is_dir($path=substr($path,0,$last)) && $last!==false)
      $last=strrpos($path,"/",-1);
}
if(empty($match)) $match="/*";
if(!$path=realpath($path)) return;
// List files
foreach(glob($path.$match) as $file){
    $list[]=substr($file,strrpos($file,"/")+1);
}
// Process sub directories
foreach(glob("$path/*", GLOB_ONLYDIR) as $dir){
    $list[substr($dir,strrpos($dir,"/",-1)+1)]=tree($dir);
}

return @$list;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=108229&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=108229&page=function.scandir&vote=down "Vote down!")

1


[**_fazle dot elahee at gmail dot com_**](https://www.php.net/manual/en/function.scandir.php#108229) [¶](https://www.php.net/manual/en/function.scandir.php#108229)

**13 years ago**

`/**
* This function will scan all files recursively in the sub-folder and folder.
*
* @author Fazle Elahee
*
*/
function scanFileNameRecursivly($path = '', &$name = array() )
{
$path = $path == ''? dirname(__FILE__) : $path;
$lists = @scandir($path);

if(!empty($lists))
{
      foreach($lists as $f)
      {

      if(is_dir($path.DIRECTORY_SEPARATOR.$f) && $f != ".." && $f != ".")
      {
          scanFileNameRecursivly($path.DIRECTORY_SEPARATOR.$f, &$name);
      }
      else
      {
          $name[] = $path.DIRECTORY_SEPARATOR.$f;
      }
      }
}
return $name;
}
$path = "/var/www/SimplejQueryDropdowns";
$file_names = scanFileNameRecursivly($path);
echo "<pre>";
var_dump($file_names);
echo "</pre>";`

[up](https://www.php.net/manual/vote-note.php?id=50623&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=50623&page=function.scandir&vote=down "Vote down!")

1


[**_csaba at alum dot mit dot edu_**](https://www.php.net/manual/en/function.scandir.php#50623) [¶](https://www.php.net/manual/en/function.scandir.php#50623)

**20 years ago**

`Scandir on steroids:
For when you want to filter your file list, or only want to list so many levels of subdirectories...
<?php
function dirList($path="", $types=2, $levels=1, $aFilter=array()) {
//  returns an array of the specified files/directories
//  start search in $path (defaults to current working directory)
//  return $types:  2 => files; 1 => directories; 3 => both;
//  $levels: 1 => look in the $path only; 2 => $path and all children;
//          3 => $path, children, grandchildren; 0 => $path and all subdirectories;
//          less than 0 => complement of -$levels, OR everything starting -$levels down
//                e.g. -1 => everthing except $path; -2 => all descendants except $path + children
//  Remaining argument(s) is(are) a filter array(list) of regular expressions which operate on the full path.
//    First character (before the '/' of the regExp) '-' => NOT.
//    First character (after a possible '-') 'd' => apply to directory name
//    The filters may be passed in as an array of strings or as a list of strings
//  Note that output directories are prefixed with a '*' (done in the line above the return)
$dS = DIRECTORY_SEPARATOR;
if (!($path = realpath($path?$path:getcwd()))) return array();    // bad path
// next line rids terminating \ on drives (works since c: == c:\ on PHP).  OK in *nix?
if (substr($path,-1)==$dS) $path = substr($path,0,-1);
if (is_null($types)) $types = 2;
if (is_null($levels)) $levels = 1;
if (is_null($aFilter)) $aFilter=array();
// last argument may be passed as a list or as an array
$aFilter = array_slice(func_get_args(),3);
if ($aFilter && gettype($aFilter[0])=="array") $aFilter=$aFilter[0];
$adFilter = array();
// now move directory filters to separate array:
foreach ($aFilter as $i=>$filter)                  // for each directory filter...
     if (($pos=stripos(" $filter","d")) && $pos<3) {  // next line eliminates the 'd'
         $adFilter[] = substr($filter,0,$pos-1) . substr($filter,$pos);
         unset($aFilter[$i]); }
$aFilter = array_merge($aFilter);    // reset indeces
$aRes = array();                    // results, $aAcc is an Accumulator
$aDir = array($path);    // dirs to check
for ($i=$levels>0?$levels++:-1;($aAcc=array())||$i--&&$aDir;$aDir=$aAcc)
     while ($dir = array_shift($aDir))
         foreach (scandir ($dir) as $fileOrDir)
           if ($fileOrDir!="." && $fileOrDir!="..") {
               if ($dirP = is_dir ($rp="$dir$dS$fileOrDir"))
                 if (pathFilter("$rp$dS", $adFilter))
                     $aAcc[] = $rp;
               if ($i<$levels-1 && ($types & (2-$dirP)))
                 if (pathFilter($rp, $aFilter))
                     $aRes[] = ($dirP?"*":"") . $rp; }
return $aRes;
}
?>
example usage:
<?php
define ("_", NULL);
// this will find all non .jpg, non .Thumbs.db files under c:\Photo
$aFiles = dirList('c:\Photo', _, 0, '-/\.jpg$/i', '-/\\\\Thumbs.db$/');
$aFiles = dirList();    // find the files in the current directory
// next lines will find .jpg files in non Photo(s) subdirectories, excluding Temporary Internet Files
set_time_limit(60);        // iterating from the top level can take a while
$aFiles = dirList("c:\\", _, 0, '/\.jpg$/i', '-d/\\\\Photos?$/i', '-d/Temporary Internet/i');
?>
Note that this function will consume a lot of time if scanning large
directory structures (which is the reason for the '[-]d/.../' filters).
Csaba Gabor from Vienna`

[up](https://www.php.net/manual/vote-note.php?id=80057&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80057&page=function.scandir&vote=down "Vote down!")

1


[**_fatpratmatt dot at dot gmail dot com_**](https://www.php.net/manual/en/function.scandir.php#80057) [¶](https://www.php.net/manual/en/function.scandir.php#80057)

**17 years ago**

`This function generates a list of all files in the chosen directory and all subdirectories, throws them into a NON-multidimentional array and returns them.
Most of the recursive functions on this page only return a multi-dimensional array.
This is actually a modification of some one else's function (thanks mail at bartrail dot de ;])
<?php
function scanDirectories($rootDir, $allData=array()) {
    // set filenames invisible if you want
    $invisibleFileNames = array(".", "..", ".htaccess", ".htpasswd");
    // run through content of root directory
    $dirContent = scandir($rootDir);
    foreach($dirContent as $key => $content) {
        // filter all files not accessible
        $path = $rootDir.'/'.$content;
        if(!in_array($content, $invisibleFileNames)) {
            // if content is file & readable, add to array
            if(is_file($path) && is_readable($path)) {
                // save file name with path
                $allData[] = $path;
            // if content is a directory and readable, add path and name
            }elseif(is_dir($path) && is_readable($path)) {
                // recursive callback to open new directory
                $allData = scanDirectories($path, $allData);
            }
        }
    }
    return $allData;
}
?>
Example output:
print_r(scanDirectories("www"));
---
Array
(
    [0] => www/index.php
    [1] => www/admin.php
    [3] => www/css/css.css
    [4] => www/articles/2007/article1.txt
    [4] => www/articles/2006/article1.txt
    [8] => www/img/img1.png
)`

[up](https://www.php.net/manual/vote-note.php?id=121183&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121183&page=function.scandir&vote=down "Vote down!")

0


[**_SPekary_**](https://www.php.net/manual/en/function.scandir.php#121183) [¶](https://www.php.net/manual/en/function.scandir.php#121183)

**8 years ago**

`Unless you specify no sorting, file names are sorted in ASCII alphabetic order, meaning numbers first, then uppercase, then lowercase letters, even on operating systems whose file system ignores the case of file names when it does its own sorting.
For example, on Mac OS, the following files will appear in this order in the Finder, when your disk is formated using the standard file system:
1file.php
a.inc
B.txt
c.txt
However, scandir will produce an array in the following order:
1file.php
B.txt
a.inc
c.txt`

[up](https://www.php.net/manual/vote-note.php?id=109140&page=function.scandir&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109140&page=function.scandir&vote=down "Vote down!")

1


[**_carneiro at isharelife dot com dot br_**](https://www.php.net/manual/en/function.scandir.php#109140) [¶](https://www.php.net/manual/en/function.scandir.php#109140)

**13 years ago**

`<?php
/**
     * Get an array that represents directory tree
     * @param string $directory     Directory path
     * @param bool $recursive         Include sub directories
     * @param bool $listDirs         Include directories on listing
     * @param bool $listFiles         Include files on listing
     * @param regex $exclude         Exclude paths that matches this regex
     */
    function directoryToArray($directory, $recursive = true, $listDirs = false, $listFiles = true, $exclude = '') {
        $arrayItems = array();
        $skipByExclude = false;
        $handle = opendir($directory);
        if ($handle) {
            while (false !== ($file = readdir($handle))) {
            preg_match("/(^(([\.]){1,2})$|(\.(svn|git|md))|(Thumbs\.db|\.DS_STORE))$/iu", $file, $skip);
            if($exclude){
                preg_match($exclude, $file, $skipByExclude);
            }
            if (!$skip && !$skipByExclude) {
                if (is_dir($directory. DIRECTORY_SEPARATOR . $file)) {
                    if($recursive) {
                        $arrayItems = array_merge($arrayItems, directoryToArray($directory. DIRECTORY_SEPARATOR . $file, $recursive, $listDirs, $listFiles, $exclude));
                    }
                    if($listDirs){
                        $file = $directory . DIRECTORY_SEPARATOR . $file;
                        $arrayItems[] = $file;
                    }
                } else {
                    if($listFiles){
                        $file = $directory . DIRECTORY_SEPARATOR . $file;
                        $arrayItems[] = $file;
                    }
                }
            }
        }
        closedir($handle);
        }
        return $arrayItems;
    }
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.scandir&repo=en&redirect=https://www.php.net/manual/en/function.scandir.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google