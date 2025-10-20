---
url: https://www.php.net/manual/en/function.fputcsv.php
scraped_at: 2025-10-20T02:34:46.269Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# fputcsv

(PHP 5 >= 5.1.0, PHP 7, PHP 8)

fputcsv — Format line as CSV and write to file pointer

### Description [¶](https://www.php.net/manual/en/function.fputcsv.php\#refsect1-function.fputcsv-description)

**fputcsv**(

[resource](https://www.php.net/manual/en/language.types.resource.php) `$stream`,

[array](https://www.php.net/manual/en/language.types.array.php) `$fields`,

[string](https://www.php.net/manual/en/language.types.string.php) `$separator` = ",",

[string](https://www.php.net/manual/en/language.types.string.php) `$enclosure` = "\\"",

[string](https://www.php.net/manual/en/language.types.string.php) `$escape` = "\\\",

[string](https://www.php.net/manual/en/language.types.string.php) `$eol` = "\\n"

): [int](https://www.php.net/manual/en/language.types.integer.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

**fputcsv()** formats a line (passed as a
`fields` array) as CSV and writes it
(terminated by a `eol`) to the specified
`stream`.


### Parameters [¶](https://www.php.net/manual/en/function.fputcsv.php\#refsect1-function.fputcsv-parameters)

`stream`

The file pointer must be valid, and must point to
a file successfully opened by [fopen()](https://www.php.net/manual/en/function.fopen.php) or
[fsockopen()](https://www.php.net/manual/en/function.fsockopen.php) (and not yet closed by
[fclose()](https://www.php.net/manual/en/function.fclose.php)).

`fields`

An array of [string](https://www.php.net/manual/en/language.types.string.php)s.


`separator`

The `separator` parameter sets the field separator.
It must be a single byte character.


`enclosure`

The `enclosure` parameter sets the field enclosure character.
It must be a single byte character.


`escape`

The `escape` parameter sets the escape character.
It must be a single byte character or the empty string.
The empty string ( `""`) disables the proprietary escape mechanism.


> **Note**:
>
> Usually an `enclosure` character is escaped inside
> a field by doubling it; however, the `escape`
> character can be used as an alternative. So for the default parameter
> values `""` and `\"` have the same
> meaning. Other than allowing to escape the
> `enclosure` character the
> `escape` character has no special meaning; it isn't
> even meant to escape itself.

**Warning**

As of PHP 8.4.0, depending on the default value of
`escape` is deprecated.
It needs to be provided explicitly either positionally or by the use
of [named arguments](https://www.php.net/manual/en/functions.arguments.php#functions.named-arguments).


`eol`

The optional `eol` parameter sets
a custom End of Line sequence.


**Warning**

When `escape` is set to anything other than an empty string
( `""`) it can result in CSV that is not compliant with
[» RFC 4180](https://datatracker.ietf.org/doc/html/rfc4180) or unable to survive a roundtrip
through the PHP CSV functions. The default for `escape` is
`"\\"` so it is recommended to set it to the empty string explicitly.
The default value will change in a future version of PHP, no earlier than PHP 9.0.

> **Note**:
>
>
> If an `enclosure` character is contained in a field,
> it will be escaped by doubling it, unless it is immediately preceded by an
> `escape`.

### Return Values [¶](https://www.php.net/manual/en/function.fputcsv.php\#refsect1-function.fputcsv-returnvalues)

Returns the length of the written string or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.fputcsv.php\#refsect1-function.fputcsv-errors)

Throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if
`separator` or `enclosure`
is not one byte long.


Throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) if
`escape` is not one byte long or the empty string.


### Changelog [¶](https://www.php.net/manual/en/function.fputcsv.php\#refsect1-function.fputcsv-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Relying on the default value of `escape` is now<br> deprecated. |
| 8.1.0 | The optional `eol` parameter has been added. |
| 7.4.0 | The `escape` parameter now also accepts an empty<br> string to disable the proprietary escape mechanism. |

### Examples [¶](https://www.php.net/manual/en/function.fputcsv.php\#refsect1-function.fputcsv-examples)

**Example #1 **fputcsv()** example**

`<?php
$list = [\
    ['aaa', 'bbb', 'ccc', 'dddd'],\
    ['123', '456', '789'],\
    ['"aaa"', '"bbb"']\
];
$fp = fopen('file.csv', 'w');
foreach ($list as $fields) {
    fputcsv($fp, $fields, ',', '"', '');
}
fclose($fp);
?>`

The above example will write the following to `file.csv`:

```
aaa,bbb,ccc,dddd
123,456,789
"""aaa""","""bbb"""
```

### See Also [¶](https://www.php.net/manual/en/function.fputcsv.php\#refsect1-function.fputcsv-seealso)

- [fgetcsv()](https://www.php.net/manual/en/function.fgetcsv.php) \- Gets line from file pointer and parse for CSV fields
- [str\_getcsv()](https://www.php.net/manual/en/function.str-getcsv.php) \- Parse a CSV string into an array
- [SplFileObject::fgetcsv()](https://www.php.net/manual/en/splfileobject.fgetcsv.php) \- Gets line from file and parse as CSV fields
- [SplFileObject::fputcsv()](https://www.php.net/manual/en/splfileobject.fputcsv.php) \- Write a field array as a CSV line
- [SplFileObject::setCsvControl()](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php) \- Set the delimiter, enclosure and escape character for CSV
- [SplFileObject::getCsvControl()](https://www.php.net/manual/en/splfileobject.getcsvcontrol.php) \- Get the delimiter, enclosure and escape character for CSV

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/filesystem/functions/fputcsv.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.fputcsv%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.fputcsv&repo=en&redirect=https://www.php.net/manual/en/function.fputcsv.php)

### User Contributed Notes 26 notes

[up](https://www.php.net/manual/vote-note.php?id=72428&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72428&page=function.fputcsv&vote=down "Vote down!")

343


[**_MagicalTux at ooKoo dot org_**](https://www.php.net/manual/en/function.fputcsv.php#72428) [¶](https://www.php.net/manual/en/function.fputcsv.php#72428)

**18 years ago**

`If you need to send a CSV file directly to the browser, without writing in an external file, you can open the output and use fputcsv on it..
<?php
$out = fopen('php://output', 'w');
fputcsv($out, array('this','is some', 'csv "stuff", you know.'));
fclose($out);
?>`

[up](https://www.php.net/manual/vote-note.php?id=74118&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74118&page=function.fputcsv&vote=down "Vote down!")

64


[**_bl at mindbench dot nl_**](https://www.php.net/manual/en/function.fputcsv.php#74118) [¶](https://www.php.net/manual/en/function.fputcsv.php#74118)

**18 years ago**

`If you need to save the output to a variable (e.g. for use within a framework) you can write to a temporary memory-wrapper and retrieve it's contents:
<?php
// output up to 5MB is kept in memory, if it becomes bigger it will automatically be written to a temporary file
$csv = fopen('php://temp/maxmemory:'. (5*1024*1024), 'r+');
fputcsv($csv, array('blah','blah'));
rewind($csv);
// put it all in a variable
$output = stream_get_contents($csv);
?>`

[up](https://www.php.net/manual/vote-note.php?id=121950&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121950&page=function.fputcsv&vote=down "Vote down!")

45


[**_mikhail dot galanin at yahoo dot com_**](https://www.php.net/manual/en/function.fputcsv.php#121950) [¶](https://www.php.net/manual/en/function.fputcsv.php#121950)

**7 years ago**

`Sometimes it's useful to get CSV line as string. I.e. to store it somewhere, not in on a filesystem.
<?php
function csvstr(array $fields) : string
{
    $f = fopen('php://memory', 'r+');
    if (fputcsv($f, $fields) === false) {
        return false;
    }
    rewind($f);
    $csv_line = stream_get_contents($f);
    return rtrim($csv_line);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=118252&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118252&page=function.fputcsv&vote=down "Vote down!")

82


[**_Anonymous_**](https://www.php.net/manual/en/function.fputcsv.php#118252) [¶](https://www.php.net/manual/en/function.fputcsv.php#118252)

**9 years ago**

`if you want make UTF-8 file for excel, use this:
$fp = fopen($filename, 'w');
//add BOM to fix UTF-8 in Excel
fputs($fp, $bom =( chr(0xEF) . chr(0xBB) . chr(0xBF) ));`

[up](https://www.php.net/manual/vote-note.php?id=125399&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125399&page=function.fputcsv&vote=down "Vote down!")

38


[**_reinhold dot egenter at gmail dot com_**](https://www.php.net/manual/en/function.fputcsv.php#125399) [¶](https://www.php.net/manual/en/function.fputcsv.php#125399)

**5 years ago**

`Please note, that fputcsv ist not always enclosing strings with the enclosure character.
<?php
$fh = fopen('file.csv', 'w');
$a = [ 'One 1', 'Two', 'Three 3' ];
fputcsv($fh, $a, "\t");
fclose($fh);
?>
results in a file containing the line:
"One 1"    Two    "Three 3"
It seems that only strings containing at least one of the following characters are enclosed:
- the delimiter character
- the enclosure character
- the escape character
- \n (new line)
- \r (line feed)
- \t (tab)
- blank
I hope this saves you the hour it took me to get to the bottom of this behaviour.`

[up](https://www.php.net/manual/vote-note.php?id=126647&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126647&page=function.fputcsv&vote=down "Vote down!")

2


[**_encode_**](https://www.php.net/manual/en/function.fputcsv.php#126647) [¶](https://www.php.net/manual/en/function.fputcsv.php#126647)

**3 years ago**

`Regarding Excel and UTF-16LE encoding
For complete Excel compatibility (umlauts, cyrillic, chinese alphabet etc.) one needs to encode their .csv to UTF-16LE, use tabulators (\t) as the separator and include a UTF-16LE BOM at the start of the file.
This however can not be done by simply encoding the input for putcsv, since separators and enclosure characters will still be written in the default encoding, and fputcsv will not accept utf-16 encoded separator/enclosure characters.
The simple solution is to roll your own implementation of fputcsv with escaping etc., or possibly to encode the generated .csv file after the fact.`

[up](https://www.php.net/manual/vote-note.php?id=91473&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91473&page=function.fputcsv&vote=down "Vote down!")

39


[**_alex /-\\-l- windeagle DOT org_**](https://www.php.net/manual/en/function.fputcsv.php#91473) [¶](https://www.php.net/manual/en/function.fputcsv.php#91473)

**16 years ago**

`TAB delimiting.
Using fputcsv to output a CSV with a tab delimiter is a little tricky since the delimiter field only takes one character.
The answer is to use the chr() function.  The ascii code for tab is 9, so chr(9) returns a tab character.
<?php
    fputcsv($fp, $foo, '\t');      //won't work
    fputcsv($fp, $foo, '    ');    //won't work
    fputcsv($fp, $foo, chr(9));    //works
?>
==================
it should be:
<?php
    fputcsv($fp, $foo, "\t");
?>
you just forgot that single quotes are literal...meaning whatever you put there that's what will come out so '\t' would be same as 't' because \ in that case would be only used for escaping but if you use double quotes then that would work.`

[up](https://www.php.net/manual/vote-note.php?id=129152&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129152&page=function.fputcsv&vote=down "Vote down!")

1


[**_php at richardneill dot org_**](https://www.php.net/manual/en/function.fputcsv.php#129152) [¶](https://www.php.net/manual/en/function.fputcsv.php#129152)

**1 year ago**

`For maximum compatibility with standard (RFC-4180) CSV files, remember that the proprietary-escape mechanism should be disabled. i.e. set the optional 5th parameter to ""  (the empty string).`

[up](https://www.php.net/manual/vote-note.php?id=118697&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118697&page=function.fputcsv&vote=down "Vote down!")

11


[**_Biniam Nigusse_**](https://www.php.net/manual/en/function.fputcsv.php#118697) [¶](https://www.php.net/manual/en/function.fputcsv.php#118697)

**9 years ago**

`the solution for how to solve the encoding problem while converting an array to csv file is below.
$fp = fopen('php://memory', 'w');
    //add BOM to fix UTF-8 in Excel
    fputs($fp, $bom =( chr(0xEF) . chr(0xBB) . chr(0xBF) ));
    // output the column headings
    //fputcsv($fp, array('Topic', 'Title', 'URL', 'Keywords', 'Score', 'FB_count', 'TW_count', '|'));
    if(isset($trend)){
        foreach ( $trend as $myField ){
        fputcsv($fp, $myField, '|');
        }
    }`

[up](https://www.php.net/manual/vote-note.php?id=90883&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90883&page=function.fputcsv&vote=down "Vote down!")

10


[**_soapergem at gmail dot com_**](https://www.php.net/manual/en/function.fputcsv.php#90883) [¶](https://www.php.net/manual/en/function.fputcsv.php#90883)

**16 years ago**

`I've created a function for quickly generating CSV files that work with Microsoft applications. In the field I learned a few things about generating CSVs that are not always obvious. First, since PHP is generally *nix-based, it makes sense that the line endings are always \n instead of \r\n. However, certain Microsoft programs (I'm looking at you, Access 97), will fail to recognize the CSV properly unless each line ends with \r\n. So this function changes the line endings accordingly. Secondly, if the first column heading / value of the CSV file begins with uppercase ID, certain Microsoft programs (ahem, Excel 2007) will interpret the file as being in the SYLK format rather than CSV, as described here: [http://support.microsoft.com/kb/323626](http://support.microsoft.com/kb/323626)
This function accommodates for that as well, by forcibly enclosing that first value in quotes (when this doesn't occur automatically). It would be fairly simple to modify this function to use another delimiter if need be and I leave that as an exercise to the reader. So quite simply, this function is used for outputting CSV data to a CSV file in a way that is safe for use with Windows applications. It takes two parameters + one optional parameter: the location of where the file should be saved, an array of data rows, and an optional array of column headings. (Technically you could omit the headings array and just include it as the first row of the data, but it is often useful to keep this data stored in different arrays in practice.)
<?php
function mssafe_csv($filepath, $data, $header = array())
{
    if ( $fp = fopen($filepath, 'w') ) {
        $show_header = true;
        if ( empty($header) ) {
            $show_header = false;
            reset($data);
            $line = current($data);
            if ( !empty($line) ) {
                reset($line);
                $first = current($line);
                if ( substr($first, 0, 2) == 'ID' && !preg_match('/["\\s,]/', $first) ) {
                    array_shift($data);
                    array_shift($line);
                    if ( empty($line) ) {
                        fwrite($fp, "\"{$first}\"\r\n");
                    } else {
                        fwrite($fp, "\"{$first}\",");
                        fputcsv($fp, $line);
                        fseek($fp, -1, SEEK_CUR);
                        fwrite($fp, "\r\n");
                    }
                }
            }
        } else {
            reset($header);
            $first = current($header);
            if ( substr($first, 0, 2) == 'ID' && !preg_match('/["\\s,]/', $first) ) {
                array_shift($header);
                if ( empty($header) ) {
                    $show_header = false;
                    fwrite($fp, "\"{$first}\"\r\n");
                } else {
                    fwrite($fp, "\"{$first}\",");
                }
            }
        }
        if ( $show_header ) {
            fputcsv($fp, $header);
            fseek($fp, -1, SEEK_CUR);
            fwrite($fp, "\r\n");
        }
        foreach ( $data as $line ) {
            fputcsv($fp, $line);
            fseek($fp, -1, SEEK_CUR);
            fwrite($fp, "\r\n");
        }
        fclose($fp);
    } else {
        return false;
    }
    return true;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=104980&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104980&page=function.fputcsv&vote=down "Vote down!")

22


[**_jamie at agentdesign dot co dot uk_**](https://www.php.net/manual/en/function.fputcsv.php#104980) [¶](https://www.php.net/manual/en/function.fputcsv.php#104980)

**14 years ago**

`Utility function to output a mysql query to csv with the option to write to file or send back to the browser as a csv attachment.
<?php
    function query_to_csv($db_conn, $query, $filename, $attachment = false, $headers = true) {

        if($attachment) {
            // send response headers to the browser
            header( 'Content-Type: text/csv' );
            header( 'Content-Disposition: attachment;filename='.$filename);
            $fp = fopen('php://output', 'w');
        } else {
            $fp = fopen($filename, 'w');
        }

        $result = mysql_query($query, $db_conn) or die( mysql_error( $db_conn ) );

        if($headers) {
            // output header row (if at least one row exists)
            $row = mysql_fetch_assoc($result);
            if($row) {
                fputcsv($fp, array_keys($row));
                // reset pointer back to beginning
                mysql_data_seek($result, 0);
            }
        }

        while($row = mysql_fetch_assoc($result)) {
            fputcsv($fp, $row);
        }

        fclose($fp);
    }
    // Using the function
    $sql = "SELECT * FROM table";
    // $db_conn should be a valid db handle
    // output as an attachment
    query_to_csv($db_conn, $sql, "test.csv", true);
    // output to file system
    query_to_csv($db_conn, $sql, "test.csv", false);
?>`

[up](https://www.php.net/manual/vote-note.php?id=87120&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87120&page=function.fputcsv&vote=down "Vote down!")

13


[**_nate at example dot com_**](https://www.php.net/manual/en/function.fputcsv.php#87120) [¶](https://www.php.net/manual/en/function.fputcsv.php#87120)

**16 years ago**

`Alright, after playing a while, I'm confident the following replacement function works in all cases, including the ones for which the native fputcsv function fails. If fputcsv fails to work for you (particularly with mysql csv imports), try this function as a drop-in replacement instead.
Arguments to pass in are exactly the same as for fputcsv, though I have added an additional $mysql_null boolean which allows one to turn php null's into mysql-insertable nulls (by default, this add-on is disabled, thus working identically to fputcsv [except this one works!]).
<?php
function fputcsv2 ($fh, array $fields, $delimiter = ',', $enclosure = '"', $mysql_null = false) {
    $delimiter_esc = preg_quote($delimiter, '/');
    $enclosure_esc = preg_quote($enclosure, '/');
    $output = array();
    foreach ($fields as $field) {
        if ($field === null && $mysql_null) {
            $output[] = 'NULL';
            continue;
        }
        $output[] = preg_match("/(?:${delimiter_esc}|${enclosure_esc}|\s)/", $field) ? (
            $enclosure . str_replace($enclosure, $enclosure . $enclosure, $field) . $enclosure
        ) : $field;
    }
    fwrite($fh, join($delimiter, $output) . "\n");
}
// the _EXACT_ LOAD DATA INFILE command to use
// (if you pass in something different for $delimiter
// and/or $enclosure above, change them here too;
// but _LEAVE ESCAPED BY EMPTY!_).
/*
LOAD DATA INFILE
    '/path/to/file.csv'
INTO TABLE
    my_table
FIELDS TERMINATED BY
    ','
OPTIONALLY ENCLOSED BY
    '"'
ESCAPED BY
    ''
LINES TERMINATED BY
    '\n'
*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=77866&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77866&page=function.fputcsv&vote=down "Vote down!")

10


[**_ifunk_**](https://www.php.net/manual/en/function.fputcsv.php#77866) [¶](https://www.php.net/manual/en/function.fputcsv.php#77866)

**18 years ago**

`I converted this from the PHP source code. This replicates PHP5 functionality exactly, whereas the other examples here do not.
<?php
if (!function_exists('fputcsv')) {

function fputcsv(&$handle, $fields = array(), $delimiter = ',', $enclosure = '"') {
    $str = '';
    $escape_char = '\\';
    foreach ($fields as $value) {
      if (strpos($value, $delimiter) !== false ||
          strpos($value, $enclosure) !== false ||
          strpos($value, "\n") !== false ||
          strpos($value, "\r") !== false ||
          strpos($value, "\t") !== false ||
          strpos($value, ' ') !== false) {
        $str2 = $enclosure;
        $escaped = 0;
        $len = strlen($value);
        for ($i=0;$i<$len;$i++) {
          if ($value[$i] == $escape_char) {
            $escaped = 1;
          } else if (!$escaped && $value[$i] == $enclosure) {
            $str2 .= $enclosure;
          } else {
            $escaped = 0;
          }
          $str2 .= $value[$i];
        }
        $str2 .= $enclosure;
        $str .= $str2.$delimiter;
      } else {
        $str .= $value.$delimiter;
      }
    }
    $str = substr($str,0,-1);
    $str .= "\n";
    return fwrite($handle, $str);
}

}
?>`

[up](https://www.php.net/manual/vote-note.php?id=123807&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123807&page=function.fputcsv&vote=down "Vote down!")

1


[**_mnz_**](https://www.php.net/manual/en/function.fputcsv.php#123807) [¶](https://www.php.net/manual/en/function.fputcsv.php#123807)

**6 years ago**

`Hope this could help..
In some server configuration an associative array doesn't work. In my case the script stops without any error or message, just fputcsv return "false".
Diggin'n'Debuggin I found that in my local setup associative arrays works, but on live server not. Just removing keys solved the problem.
So, it's better to strip keys before calling fputcsv()
<?php
// Remove keys from an array
$csv_fields = array();
foreach($associative_array as $value) {
     $csv_fields[] = $value;
}
fputcsv( $handler, $csv_fields);
?>`

[up](https://www.php.net/manual/vote-note.php?id=121657&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121657&page=function.fputcsv&vote=down "Vote down!")

1


[**_perske at muenster dot de_**](https://www.php.net/manual/en/function.fputcsv.php#121657) [¶](https://www.php.net/manual/en/function.fputcsv.php#121657)

**8 years ago**

`To produce RFC 4180 conforming output, do not use fputcsv but encode manually, like this:
function rfccsv($arr){
    foreach($arr as &$a){
        $a=strval($a);
        if(strcspn($a,",\"\r\n")<strlen($a))$a='"'.strtr($a,array('"'=>'""')).'"';
    }
    return implode(',',$arr);
}
echo rfccsv(array(.....))."\n";`

[up](https://www.php.net/manual/vote-note.php?id=125186&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125186&page=function.fputcsv&vote=down "Vote down!")

1


[**_julian at polygon dot red_**](https://www.php.net/manual/en/function.fputcsv.php#125186) [¶](https://www.php.net/manual/en/function.fputcsv.php#125186)

**5 years ago**

`If you do not want to enclose strings (because you're managing that yourself or your content is already enclosed?), note that you cannot pass an empty enclosure to fputcsv. The function requires one character for that parameter. chr(0) works well:
fputcsv($handle, $fields, ",", chr(0));`

[up](https://www.php.net/manual/vote-note.php?id=47606&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=47606&page=function.fputcsv&vote=down "Vote down!")

2


[**_drew at zitnay dot com_**](https://www.php.net/manual/en/function.fputcsv.php#47606) [¶](https://www.php.net/manual/en/function.fputcsv.php#47606)

**20 years ago**

`[EDIT BY danbrown AT php DOT net: This is a revised function with a few bugfixes and improvements done by this author.  The original function example was written by arthur AT mclean DOT ws, and rewritten between by arthur AT korn DOT ch.]
- when calling str_replace(), you must assign $cell the return value or nothing gets saved
- when using strchr(), you should explicitly check !== FALSE, or it'll treat a return value of 0 (found the character at string position 0) as FALSE
- Excel seems to quote not only fields containing commas, but fields containing quotes as well, so I've added another strchr() for quotes; I'm not saying Microsoft knows the correct way for sure, but it seems reasonable to me
- the original function put a space after each comma; that might be legal, I don't know, but I've never seen it (and I don't think it is, because then how would you indicate you wanted a field to start with a space other than by quoting it?)
- the original function didn't correctly return the length of the data outputted
Here's the function, fixed up a bit:
<?php
function fputcsv($handle, $row, $fd=',', $quot='"')
{
$str='';
foreach ($row as $cell) {
       $cell=str_replace(Array($quot,        "\n"),
                         Array($quot.$quot,  ''),
                         $cell);
       if (strchr($cell, $fd)!==FALSE || strchr($cell, $quot)!==FALSE) {
           $str.=$quot.$cell.$quot.$fd;
       } else {
           $str.=$cell.$fd;
       }
}
fputs($handle, substr($str, 0, -1)."\n");
return strlen($str);
}
?>
Drew`

[up](https://www.php.net/manual/vote-note.php?id=115432&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115432&page=function.fputcsv&vote=down "Vote down!")

1


[**_mike at fatica dot net_**](https://www.php.net/manual/en/function.fputcsv.php#115432) [¶](https://www.php.net/manual/en/function.fputcsv.php#115432)

**11 years ago**

`We had a function that wrote a single line CSV.  I noticed that with enabling auto_detect_line_endings, fputcsv would not write a newline at the end of the file.
Enabling auto_detect_line_endings changed the fputcsv behavior to include a newline.`

[up](https://www.php.net/manual/vote-note.php?id=130328&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130328&page=function.fputcsv&vote=down "Vote down!")

0


[**_maldiran at maldiran dot com_**](https://www.php.net/manual/en/function.fputcsv.php#130328) [¶](https://www.php.net/manual/en/function.fputcsv.php#130328)

**4 months ago**

`As stated above, if you want to parse the csv later with fgetcsv, you should disable the escape mechanism by setting the escape parameter to empty string. Here is what can happen if you don't:
<?php
$a = array('xyz\\', 'qwerty');
var_dump($a);
$f = fopen('test.csv', 'w');
fputcsv($f, $a);
fclose($f);
$f = fopen('test.csv', 'r');
$b = fgetcsv($f);
fclose($f);
var_dump($b);
?>
Result :
array(2) {
[0]=>
string(4) "xyz\"
[1]=>
string(6) "qwerty"
}
array(1) {
[0]=>
string(13) "xyz\",qwerty
"
}
As you can see, the output of fputcsv cannot be safely parsed by fgetcsv.`

[up](https://www.php.net/manual/vote-note.php?id=96937&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96937&page=function.fputcsv&vote=down "Vote down!")

1


[**_simeonl at dbc dot co dot nz_**](https://www.php.net/manual/en/function.fputcsv.php#96937) [¶](https://www.php.net/manual/en/function.fputcsv.php#96937)

**15 years ago**

`In general I found myself wanting to get the result as a string rather than writing it to a file, and in particular I wanted to produce a CSV using an EOL that might not be the same as that on the server where I generated it.  This is how I solved the problem without rewriting  fputcsv.
<?php
function sputcsv($row, $delimiter = ',', $enclosure = '"', $eol = "\n")
{
    static $fp = false;
    if ($fp === false)
    {
        $fp = fopen('php://temp', 'r+'); // see [http://php.net/manual/en/wrappers.php.php](http://php.net/manual/en/wrappers.php.php) - yes there are 2 '.php's on the end.
        // NB: anything you read/write to/from 'php://temp' is specific to this filehandle
    }
    else
    {
        rewind($fp);
    }

    if (fputcsv($fp, $row, $delimiter, $enclosure) === false)
    {
        return false;
    }

    rewind($fp);
    $csv = fgets($fp);

    if ($eol != PHP_EOL)
    {
        $csv = substr($csv, 0, (0 - strlen(PHP_EOL))) . $eol;
    }

    return $csv;
}
// test
$rows = array
(
    array('blue, sky', 'green, lime', 'red', 'black'),
    array('white', 'gold', 'purple, imperial', 'grey, slate'),
    array('orange, burnt', 'pink, hot', 'violet', 'indigo'),
);
if (PHP_EOL == "\r\n")
{
    $eol = "\n";
}
else
{
    $eol = "\r\n";
}
foreach($rows as $row)
{
    echo nl2br(sputcsv($row, ',', '"', $eol));
}
?>
The test should produce something like the following:
"blue, sky","green, lime",red,black
white,gold,"purple, imperial","grey, slate"
"orange, burnt","pink, hot",violet,indigo`

[up](https://www.php.net/manual/vote-note.php?id=84783&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84783&page=function.fputcsv&vote=down "Vote down!")

1


[**_jon+dontspamme at phpsitesolutions dot com_**](https://www.php.net/manual/en/function.fputcsv.php#84783) [¶](https://www.php.net/manual/en/function.fputcsv.php#84783)

**17 years ago**

`I found that the fputcsv examples for PHP 4 missed one thing, that was proper handling of the $enclosure value when it is a quote (if a quote is passed in a field, and it is delimited by a slash, it will be improperly handled by the functions submitted here).
My modified function was built using the actual PHP5 source for fputcsv, with the addition of properly reacting to the existence of a delimited quote in the field being processed.
<?php
if (!function_exists('fputcsv')) {
    function fputcsv(&$handle, $fields = array(), $delimiter = ',', $enclosure = '"') {
        // Sanity Check
        if (!is_resource($handle)) {
            trigger_error('fputcsv() expects parameter 1 to be resource, ' .
                gettype($handle) . ' given', E_USER_WARNING);
            return false;
        }
        if ($delimiter!=NULL) {
            if( strlen($delimiter) < 1 ) {
                trigger_error('delimiter must be a character', E_USER_WARNING);
                return false;
            }elseif( strlen($delimiter) > 1 ) {
                trigger_error('delimiter must be a single character', E_USER_NOTICE);
            }
            /* use first character from string */
            $delimiter = $delimiter[0];
        }
        if( $enclosure!=NULL ) {
             if( strlen($enclosure) < 1 ) {
                trigger_error('enclosure must be a character', E_USER_WARNING);
                return false;
            }elseif( strlen($enclosure) > 1 ) {
                trigger_error('enclosure must be a single character', E_USER_NOTICE);
            }
            /* use first character from string */
            $enclosure = $enclosure[0];
       }
        $i = 0;
        $csvline = '';
        $escape_char = '\\';
        $field_cnt = count($fields);
        $enc_is_quote = in_array($enclosure, array('"',"'"));
        reset($fields);
        foreach( $fields AS $field ) {
            /* enclose a field that contains a delimiter, an enclosure character, or a newline */
            if( is_string($field) && (
                strpos($field, $delimiter)!==false ||
                strpos($field, $enclosure)!==false ||
                strpos($field, $escape_char)!==false ||
                strpos($field, "\n")!==false ||
                strpos($field, "\r")!==false ||
                strpos($field, "\t")!==false ||
                strpos($field, ' ')!==false ) ) {
                $field_len = strlen($field);
                $escaped = 0;
                $csvline .= $enclosure;
                for( $ch = 0; $ch < $field_len; $ch++ )    {
                    if( $field[$ch] == $escape_char && $field[$ch+1] == $enclosure && $enc_is_quote ) {
                        continue;
                    }elseif( $field[$ch] == $escape_char ) {
                        $escaped = 1;
                    }elseif( !$escaped && $field[$ch] == $enclosure ) {
                        $csvline .= $enclosure;
                    }else{
                        $escaped = 0;
                    }
                    $csvline .= $field[$ch];
                }
                $csvline .= $enclosure;
            } else {
                $csvline .= $field;
            }
            if( $i++ != $field_cnt ) {
                $csvline .= $delimiter;
            }
        }
        $csvline .= "\n";
        return fwrite($handle, $csvline);
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=113751&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113751&page=function.fputcsv&vote=down "Vote down!")

0


[**_alanzhang717 at gmail dot com_**](https://www.php.net/manual/en/function.fputcsv.php#113751) [¶](https://www.php.net/manual/en/function.fputcsv.php#113751)

**11 years ago**

`When you output csv by fputcsv, if there are any Chinese character, you may get messy code. Then you need to set the encoding properly:
fprintf($fp, chr(0xEF).chr(0xBB).chr(0xBF));  // just add this line
fputcsv($fp, ...);`

[up](https://www.php.net/manual/vote-note.php?id=113326&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113326&page=function.fputcsv&vote=down "Vote down!")

 -1


[**_R dot Mansveld at Spider-IT dot de_**](https://www.php.net/manual/en/function.fputcsv.php#113326) [¶](https://www.php.net/manual/en/function.fputcsv.php#113326)

**12 years ago**

`Inspired by boonerunner's function, I wrote a smaller, faster, and more flexible one, which also uses less memory.
I also renamed it to avoid collision or overwriting the PHP function, and gave the 3rd and 4th parameter default values like fputcsv() uses.
This function puts all text values in $enclosure's while doubling the $enclosure in the value, and leaves numeric values as they are.
But if the $delimiter exists in the numeric value, this value will also be put in $enclosure's (may happen if you use a dot as the $delimiter).
function fwritecsv($handle, $fields, $delimiter = ',', $enclosure = '"') {
    # Check if $fields is an array
    if (!is_array($fields)) {
        return false;
    }
    # Walk through the data array
    for ($i = 0, $n = count($fields); $i < $n; $i ++) {
        # Only 'correct' non-numeric values
        if (!is_numeric($fields[$i])) {
            # Duplicate in-value $enclusure's and put the value in $enclosure's
            $fields[$i] = $enclosure . str_replace($enclosure, $enclosure . $enclosure, $fields[$i]) . $enclosure;
        }
        # If $delimiter is a dot (.), also correct numeric values
        if (($delimiter == '.') && (is_numeric($fields[$i]))) {
            # Put the value in $enclosure's
            $fields[$i] = $enclosure . $fields[$i] . $enclosure;
        }
    }
    # Combine the data array with $delimiter and write it to the file
    $line = implode($delimiter, $fields) . "\n";
    fwrite($handle, $line);
    # Return the length of the written data
    return strlen($line);
}`

[up](https://www.php.net/manual/vote-note.php?id=106583&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106583&page=function.fputcsv&vote=down "Vote down!")

 -2


[**_David Thomas_**](https://www.php.net/manual/en/function.fputcsv.php#106583) [¶](https://www.php.net/manual/en/function.fputcsv.php#106583)

**13 years ago**

`Output XML string as CSV with first row as column headers:
<?php
    // In this case XML is
    // <records>
    //  <record>...</record>
    //  <record>...</record>
    // </records>
if($xml = simplexml_load_string($string)){
    // Keep up to 12MB in memory, if becomes bigger write to temp file
    $file = fopen('php://temp/maxmemory:'. (12*1024*1024), 'r+');
    if($row = get_object_vars($xml->record[0])){ // First record
      // First row contains column header values
      foreach($row as $key => $value){
        $header[] = $key;
      }
      fputcsv($file, $header,',','"');
      foreach ($xml->record as $record) {
        fputcsv($file, get_object_vars($record),',','"');
      }
      rewind($file);
      $output = stream_get_contents($file);
      fclose($file);
      return $output;
    }else{
      return '';
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=56827&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56827&page=function.fputcsv&vote=down "Vote down!")

 -5


[**_boonerunner at hotmail dot com_**](https://www.php.net/manual/en/function.fputcsv.php#56827) [¶](https://www.php.net/manual/en/function.fputcsv.php#56827)

**20 years ago**

`Here is an adaption of the above code that adds support for double quotes inside a field. (One double quote is replaced with a pair of double quotes per the CSV format).
<?php
function fputcsv($filePointer,$dataArray,$delimiter,$enclosure)
{
// Write a line to a file
// $filePointer = the file resource to write to
// $dataArray = the data to write out
// $delimeter = the field separator

// Build the string
$string = "";

// No leading delimiter
$writeDelimiter = FALSE;
foreach($dataArray as $dataElement)
{
    // Replaces a double quote with two double quotes
    $dataElement=str_replace("\"", "\"\"", $dataElement);

    // Adds a delimiter before each field (except the first)
    if($writeDelimiter) $string .= $delimiter;

    // Encloses each field with $enclosure and adds it to the string
    $string .= $enclosure . $dataElement . $enclosure;

    // Delimiters are used every time except the first.
    $writeDelimiter = TRUE;
} // end foreach($dataArray as $dataElement)

// Append new line
$string .= "\n";

// Write the string to the file
fwrite($filePointer,$string);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=126454&page=function.fputcsv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126454&page=function.fputcsv&vote=down "Vote down!")

 -3


[**_johannes dot kingma at gmail dot com_**](https://www.php.net/manual/en/function.fputcsv.php#126454) [¶](https://www.php.net/manual/en/function.fputcsv.php#126454)

**4 years ago**

`In all those cases you need a bug free csv writer with custom record seperating capability:
<?php
/**
* Custom fputcsv
* @param int $handle filehandle
* @param mixed[] $fields array of values to write
* @param string $delimiter field delimiter
* @param string $enclosure field enclosures
* @param string $escape_char escape enclosure chars in fields
* @param string $record_seperator
* @return int characters written
*/
function _fputcsv($handle, $fields, $delimiter = ",", $enclosure = '"', $escape_char = "\\", $record_seperator = "\r\n")
{
    $result = [];
    foreach ($fields as $field) {
        $result[] = $enclosure . str_replace($enclosure, $escape_char . $enclosure, $field) . $enclosure;
    }
    return fwrite($handle, implode($delimiter, $result) . $record_seperator);
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.fputcsv&repo=en&redirect=https://www.php.net/manual/en/function.fputcsv.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google