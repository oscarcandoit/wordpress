---
url: https://www.php.net/manual/en/function.file.php
scraped_at: 2025-10-20T02:57:01.252Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# file

(PHP 4, PHP 5, PHP 7, PHP 8)

file — Reads entire file into an array

### Description [¶](https://www.php.net/manual/en/function.file.php\#refsect1-function.file-description)

**file**([string](https://www.php.net/manual/en/language.types.string.php) `$filename`, [int](https://www.php.net/manual/en/language.types.integer.php) `$flags` = 0, [?](https://www.php.net/manual/en/language.types.null.php)[resource](https://www.php.net/manual/en/language.types.resource.php) `$context` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [array](https://www.php.net/manual/en/language.types.array.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Reads an entire file into an array.


> **Note**:
>
>
> You can use [file\_get\_contents()](https://www.php.net/manual/en/function.file-get-contents.php) to return the contents
> of a file as a string.

### Parameters [¶](https://www.php.net/manual/en/function.file.php\#refsect1-function.file-parameters)

`filename`

Path to the file.


**Tip**

A URL can be used as a
filename with this function if the [fopen wrappers](https://www.php.net/manual/en/filesystem.configuration.php#ini.allow-url-fopen) have been enabled.
See [fopen()](https://www.php.net/manual/en/function.fopen.php) for more details on how to specify the
filename. See the [Supported Protocols and Wrappers](https://www.php.net/manual/en/wrappers.php) for links to information
about what abilities the various wrappers have, notes on their usage,
and information on any predefined variables they may
provide.

`flags`

The optional parameter `flags` can be one, or
more, of the following constants:


**`[FILE\_USE\_INCLUDE\_PATH](https://www.php.net/manual/en/filesystem.constants.php#constant.file-use-include-path)`**
Search for the file in the [include\_path](https://www.php.net/manual/en/ini.core.php#ini.include-path).
**`[FILE\_IGNORE\_NEW\_LINES](https://www.php.net/manual/en/filesystem.constants.php#constant.file-ignore-new-lines)`**
Omit newline at the end of each array element.
**`[FILE\_SKIP\_EMPTY\_LINES](https://www.php.net/manual/en/filesystem.constants.php#constant.file-skip-empty-lines)`**
Skip empty lines.
**`[FILE\_NO\_DEFAULT\_CONTEXT](https://www.php.net/manual/en/filesystem.constants.php#constant.file-no-default-context)`**
Don't use the default context.
`context`

A [context stream](https://www.php.net/manual/en/stream.contexts.php) [resource](https://www.php.net/manual/en/language.types.resource.php).

### Return Values [¶](https://www.php.net/manual/en/function.file.php\#refsect1-function.file-returnvalues)

Returns the file in an array. Each element of the array corresponds to a
line in the file, with the newline still attached. Upon failure,
**file()** returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


> **Note**:
>
>
> Each line in the resulting array will include the line ending, unless
> **`[FILE\_IGNORE\_NEW\_LINES](https://www.php.net/manual/en/filesystem.constants.php#constant.file-ignore-new-lines)`** is used.

> **Note**: If PHP is not properly recognizing
> the line endings when reading files either on or created by a Macintosh
> computer, enabling the
> [auto\_detect\_line\_endings](https://www.php.net/manual/en/filesystem.configuration.php#ini.auto-detect-line-endings)
> run-time configuration option may help resolve the problem.

### Errors/Exceptions [¶](https://www.php.net/manual/en/function.file.php\#refsect1-function.file-errors)

As of PHP 8.3.0, throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php)
if `flags` includes any invalid values, such
as **`[FILE\_APPEND](https://www.php.net/manual/en/filesystem.constants.php#constant.file-append)`**.


Emits an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** level error if the file
does not exist.


### Changelog [¶](https://www.php.net/manual/en/function.file.php\#refsect1-function.file-changelog)

| Version | Description |
| --- | --- |
| 8.3.0 | [ValueError](https://www.php.net/manual/en/class.valueerror.php) is thrown for any<br> invalid values of `flags`. |

### Examples [¶](https://www.php.net/manual/en/function.file.php\#refsect1-function.file-examples)

**Example #1 **file()** example**

`<?php
// Get a file into an array.  In this example we'll go through HTTP to get
// the HTML source of a URL.
$lines = file('http://www.example.com/');
// Loop through our array, show HTML source as HTML source; and line numbers too.
foreach ($lines as $line_num => $line) {
    echo "Line #<b>{$line_num}</b> : " . htmlspecialchars($line) . "<br />\n";
}
// Using the optional flags parameter
$trimmed = file('somefile.txt', FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);
?>`

### Notes [¶](https://www.php.net/manual/en/function.file.php\#refsect1-function.file-notes)

**Warning**

When using SSL, Microsoft IIS
will violate the protocol by closing the connection without sending a
`close_notify` indicator. PHP will report this as "SSL: Fatal
Protocol Error" when you reach the end of the data. To work around this, the
value of [error\_reporting](https://www.php.net/manual/en/errorfunc.configuration.php#ini.error-reporting) should be
lowered to a level that does not include warnings.
PHP can detect buggy IIS server software when you open
the stream using the `https://` wrapper and will suppress the
warning. When using [fsockopen()](https://www.php.net/manual/en/function.fsockopen.php) to create an
`ssl://` socket, the developer is responsible for detecting
and suppressing this warning.

### See Also [¶](https://www.php.net/manual/en/function.file.php\#refsect1-function.file-seealso)

- [file\_get\_contents()](https://www.php.net/manual/en/function.file-get-contents.php) \- Reads entire file into a string
- [readfile()](https://www.php.net/manual/en/function.readfile.php) \- Outputs a file
- [fopen()](https://www.php.net/manual/en/function.fopen.php) \- Opens file or URL
- [fsockopen()](https://www.php.net/manual/en/function.fsockopen.php) \- Open Internet or Unix domain socket connection
- [popen()](https://www.php.net/manual/en/function.popen.php) \- Opens process file pointer
- [include](https://www.php.net/manual/en/function.include.php) \- include
- [stream\_context\_create()](https://www.php.net/manual/en/function.stream-context-create.php) \- Creates a stream context

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/filesystem/functions/file.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.file%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.file&repo=en&redirect=https://www.php.net/manual/en/function.file.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=115500&page=function.file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115500&page=function.file&vote=down "Vote down!")

38


[**_Martin K._**](https://www.php.net/manual/en/function.file.php#115500) [¶](https://www.php.net/manual/en/function.file.php#115500)

**11 years ago**

`If the file you are reading is in CSV format do not use file(), use fgetcsv().  file() will split the file by each newline that it finds, even newlines that appear within a field (i.e. within quotations).`

[up](https://www.php.net/manual/vote-note.php?id=113461&page=function.file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113461&page=function.file&vote=down "Vote down!")

25


[**_bingo at dingo dot com_**](https://www.php.net/manual/en/function.file.php#113461) [¶](https://www.php.net/manual/en/function.file.php#113461)

**12 years ago**

`To write all the lines of the file in other words to read the file line by line you can write the code like this:
<?php
$names=file('name.txt');
// To check the number of lines
echo count($names).'<br>';
foreach($names as $name)
{
echo $name.'<br>';
}
?>
this example is so basic to understand how it's working. I hope it will help many beginners.
Regards,
Bingo`

[up](https://www.php.net/manual/vote-note.php?id=94067&page=function.file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94067&page=function.file&vote=down "Vote down!")

16


[**_d basin_**](https://www.php.net/manual/en/function.file.php#94067) [¶](https://www.php.net/manual/en/function.file.php#94067)

**16 years ago**

`this may be obvious, but it took me a while to figure out what I was doing wrong. So I wanted to share. I have a file on my "c:\" drive. How do I file() it?
Don't forget the backslash is special and you have to "escape" the backslash i.e. "\\":
<?php
$lines = file("C:\\Documents and Settings\\myfile.txt");
foreach($lines as $line)
{
    echo($line);
}
?>
hope this helps...`

[up](https://www.php.net/manual/vote-note.php?id=105772&page=function.file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105772&page=function.file&vote=down "Vote down!")

9


[**_twichi at web dot de_**](https://www.php.net/manual/en/function.file.php#105772) [¶](https://www.php.net/manual/en/function.file.php#105772)

**14 years ago**

`read from CSV data (file) into an array with named keys
... with or without 1st row = header (keys)
(see 4th parameter of function call as  true / false)
<?php
// --------------------------------------------------------------
function csv_in_array($url,$delm=";",$encl="\"",$head=false) {

    $csvxrow = file($url);   // ---- csv rows to array ----

    $csvxrow[0] = chop($csvxrow[0]);
    $csvxrow[0] = str_replace($encl,'',$csvxrow[0]);
    $keydata = explode($delm,$csvxrow[0]);
    $keynumb = count($keydata);

    if ($head === true) {
    $anzdata = count($csvxrow);
    $z=0;
    for($x=1; $x<$anzdata; $x++) {
        $csvxrow[$x] = chop($csvxrow[$x]);
        $csvxrow[$x] = str_replace($encl,'',$csvxrow[$x]);
        $csv_data[$x] = explode($delm,$csvxrow[$x]);
        $i=0;
        foreach($keydata as $key) {
            $out[$z][$key] = $csv_data[$x][$i];
            $i++;
            }
        $z++;
        }
    }
    else {
        $i=0;
        foreach($csvxrow as $item) {
            $item = chop($item);
            $item = str_replace($encl,'',$item);
            $csv_data = explode($delm,$item);
            for ($y=0; $y<$keynumb; $y++) {
               $out[$i][$y] = $csv_data[$y];
            }
        $i++;
        }
    }
return $out;
}
// --------------------------------------------------------------
?>
fuction call with 4 parameters:
(1) = the file with CSV data (url / string)
(2) = colum delimiter (e.g: ; or | or , ...)
(3) = values enclosed by (e.g: ' or " or ^ or ...)
(4) = with or without 1st row = head (true/false)
<?php
// ----- call ------
$csvdata = csv_in_array( $yourcsvfile, ";", "\"", true );
// -----------------
// ----- view ------
echo "<pre>\r\n";
print_r($csvdata);
echo "</pre>\r\n";
// -----------------
?>
PS: also see: [http://php.net/manual/de/function.fgetcsv.php](http://php.net/manual/de/function.fgetcsv.php) to read CSV data into an array
... and other file-handling methods
^`

[up](https://www.php.net/manual/vote-note.php?id=123195&page=function.file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123195&page=function.file&vote=down "Vote down!")

1


[**_radler63 at hotmail dot com_**](https://www.php.net/manual/en/function.file.php#123195) [¶](https://www.php.net/manual/en/function.file.php#123195)

**7 years ago**

`My experience is that the function file does uses the cached content if the file has changed....`

[up](https://www.php.net/manual/vote-note.php?id=126045&page=function.file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126045&page=function.file&vote=down "Vote down!")

0


[**_renanlazarotto at gmail dot com_**](https://www.php.net/manual/en/function.file.php#126045) [¶](https://www.php.net/manual/en/function.file.php#126045)

**4 years ago**

`Be aware that using file() to count lines can cause OOM on the server as it'll allocate all lines into an array.
If you're dealing with files that can have thousands of lines, SplFileObject might be a better idea and with little changes you can get the same result.`

[up](https://www.php.net/manual/vote-note.php?id=123893&page=function.file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123893&page=function.file&vote=down "Vote down!")

 -1


[**_sheldon at hyperlinked dot com_**](https://www.php.net/manual/en/function.file.php#123893) [¶](https://www.php.net/manual/en/function.file.php#123893)

**6 years ago**

`As of PHP 5.6 the file(), file_get_contents(), and fopen() functions will return false if you are referencing a source URL that doesn't have a valid SSL certificate. Presumably, you will run into this a lot in your development environments this will drive you crazy.
You will need to create a stream context and provide it as an argument to the various file operations to tell it to ignore invalid SSL credentials.
$args = array("ssl"=>array("verify_peer"=>false,"verify_peer_name"=>false),"http"=>array('timeout' => 60, 'user_agent' => 'Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.8.1.9) Gecko/20071025 Firefox/3.0.0.1'));
$context = stream_context_create($args);
$httpfile = file($url, false, $context);`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.file&repo=en&redirect=https://www.php.net/manual/en/function.file.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google