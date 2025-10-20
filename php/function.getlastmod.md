---
url: https://www.php.net/manual/en/function.getlastmod.php
scraped_at: 2025-10-20T03:01:02.515Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# getlastmod

(PHP 4, PHP 5, PHP 7, PHP 8)

getlastmod — Gets time of last page modification

### Description [¶](https://www.php.net/manual/en/function.getlastmod.php\#refsect1-function.getlastmod-description)

**getlastmod**(): [int](https://www.php.net/manual/en/language.types.integer.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Gets the time of the last modification of the main script of execution.


If you're interested in getting the last modification time
of a different file, consider using [filemtime()](https://www.php.net/manual/en/function.filemtime.php).


### Parameters [¶](https://www.php.net/manual/en/function.getlastmod.php\#refsect1-function.getlastmod-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/function.getlastmod.php\#refsect1-function.getlastmod-returnvalues)

Returns the time of the last modification of the current
page. The value returned is a Unix timestamp, suitable for
feeding to [date()](https://www.php.net/manual/en/function.date.php). Returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on error.


### Examples [¶](https://www.php.net/manual/en/function.getlastmod.php\#refsect1-function.getlastmod-examples)

**Example #1 **getlastmod()** example**

`<?php
// outputs e.g. 'Last modified: March 04 1998 20:43:59.'
echo "Last modified: " . date ("F d Y H:i:s.", getlastmod());
?>`

### See Also [¶](https://www.php.net/manual/en/function.getlastmod.php\#refsect1-function.getlastmod-seealso)

- [date()](https://www.php.net/manual/en/function.date.php) \- Format a Unix timestamp
- [getmyuid()](https://www.php.net/manual/en/function.getmyuid.php) \- Gets PHP script owner's UID
- [getmygid()](https://www.php.net/manual/en/function.getmygid.php) \- Get PHP script owner's GID
- [get\_current\_user()](https://www.php.net/manual/en/function.get-current-user.php) \- Gets the name of the owner of the current PHP script
- [getmyinode()](https://www.php.net/manual/en/function.getmyinode.php) \- Gets the inode of the current script
- [getmypid()](https://www.php.net/manual/en/function.getmypid.php) \- Gets PHP's process ID
- [filemtime()](https://www.php.net/manual/en/function.filemtime.php) \- Gets file modification time

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/info/functions/getlastmod.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.getlastmod%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.getlastmod&repo=en&redirect=https://www.php.net/manual/en/function.getlastmod.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=107867&page=function.getlastmod&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107867&page=function.getlastmod&vote=down "Vote down!")

11


[**_luca dot delpivo at gmail dot com_**](https://www.php.net/manual/en/function.getlastmod.php#107867) [¶](https://www.php.net/manual/en/function.getlastmod.php#107867)

**13 years ago**

`With better words getlastmod() returning the last time the script in which it is being called was modified, it does not require or use a parameter.`

[up](https://www.php.net/manual/vote-note.php?id=109250&page=function.getlastmod&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109250&page=function.getlastmod&vote=down "Vote down!")

4


[**_Moro_**](https://www.php.net/manual/en/function.getlastmod.php#109250) [¶](https://www.php.net/manual/en/function.getlastmod.php#109250)

**13 years ago**

`Return latest mod time of all included files:
<?php
function get_page_mod_time() {
    $incls = get_included_files();
    $incls = array_filter($incls, "is_file");
    $mod_times = array_map('filemtime', $incls);
    $mod_time = max($mod_times);
    return $mod_time;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=96393&page=function.getlastmod&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96393&page=function.getlastmod&vote=down "Vote down!")

1


[**_Ant P._**](https://www.php.net/manual/en/function.getlastmod.php#96393) [¶](https://www.php.net/manual/en/function.getlastmod.php#96393)

**15 years ago**

`If you use register_shutdown_function() on certain SAPIs, various filesystem-related things inside the shutdown function might do unexpected things, one of which being this function can return false.
On the other hand getlastmod() apparently caches the return value, so if you use it at least once in normal code it should work for the remainder of the request.`

[up](https://www.php.net/manual/vote-note.php?id=46613&page=function.getlastmod&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=46613&page=function.getlastmod&vote=down "Vote down!")

 -1


[**_rwruck_**](https://www.php.net/manual/en/function.getlastmod.php#46613) [¶](https://www.php.net/manual/en/function.getlastmod.php#46613)

**21 years ago**

`DO NOT use this function unless you are absolutely sure both your Apache and PHP have been compiled with the same value for -DFILE_OFFSET_BITS.
If not, this function will return the access time (or maybe even garbage) instead of the modification time due do Apache and PHP using different versions of the stat structure.
This is true regardless of Apache and PHP version.
To be on the safe side, always use the workaround already posted below:
filemtime($_SERVER['SCRIPT_FILENAME'])`

[up](https://www.php.net/manual/vote-note.php?id=42506&page=function.getlastmod&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=42506&page=function.getlastmod&vote=down "Vote down!")

 -2


[**_Anonymous_**](https://www.php.net/manual/en/function.getlastmod.php#42506) [¶](https://www.php.net/manual/en/function.getlastmod.php#42506)

**21 years ago**

`Setting the 'Last-Modified' header:
<?php
setlocale(LC_TIME, "C");
$ft = filemtime ('referencefile');
$localt = mktime ();
$gmtt = gmmktime ();
$ft = $ft - $gmtt + $localt;
$modified = strftime ("%a, %d %b %Y %T GMT", $ft);
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.getlastmod&repo=en&redirect=https://www.php.net/manual/en/function.getlastmod.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google