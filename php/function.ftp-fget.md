---
url: https://www.php.net/manual/en/function.ftp-fget.php
scraped_at: 2025-10-20T02:54:16.015Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ftp\_fget

(PHP 4, PHP 5, PHP 7, PHP 8)

ftp\_fget — Downloads a file from the FTP server and saves to an open file

### Description [¶](https://www.php.net/manual/en/function.ftp-fget.php\#refsect1-function.ftp-fget-description)

**ftp\_fget**(

[FTP\\Connection](https://www.php.net/manual/en/class.ftp-connection.php) `$ftp`,

[resource](https://www.php.net/manual/en/language.types.resource.php) `$stream`,

[string](https://www.php.net/manual/en/language.types.string.php) `$remote_filename`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$mode` = **`[FTP\_BINARY](https://www.php.net/manual/en/ftp.constants.php#constant.ftp-binary)`**,

[int](https://www.php.net/manual/en/language.types.integer.php) `$offset` = 0

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**ftp\_fget()** retrieves `remote_filename`
from the FTP server, and writes it to the given file pointer.


### Parameters [¶](https://www.php.net/manual/en/function.ftp-fget.php\#refsect1-function.ftp-fget-parameters)

`ftp`

An [FTP\\Connection](https://www.php.net/manual/en/class.ftp-connection.php) instance.

`stream`

An open file pointer in which we store the data.


`remote_filename`

The remote file path.


`mode`

The transfer mode. Must be either **`[FTP\_ASCII](https://www.php.net/manual/en/ftp.constants.php#constant.ftp-ascii)`** or
**`[FTP\_BINARY](https://www.php.net/manual/en/ftp.constants.php#constant.ftp-binary)`**.


`offset`

The position in the remote file to start downloading from.


### Return Values [¶](https://www.php.net/manual/en/function.ftp-fget.php\#refsect1-function.ftp-fget-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Changelog [¶](https://www.php.net/manual/en/function.ftp-fget.php\#refsect1-function.ftp-fget-changelog)

| Version | Description |
| --- | --- |
| 8.1.0 | The `ftp` parameter expects an [FTP\\Connection](https://www.php.net/manual/en/class.ftp-connection.php)<br> instance now; previously, a [resource](https://www.php.net/manual/en/language.types.resource.php) was expected. |
| 7.3.0 | The `mode` parameter is now optional. Formerly it<br> has been mandatory. |

### Examples [¶](https://www.php.net/manual/en/function.ftp-fget.php\#refsect1-function.ftp-fget-examples)

**Example #1 **ftp\_fget()** example**

`<?php
// path to remote file
$remote_file = 'somefile.txt';
$local_file = 'localfile.txt';
// open some file to write to
$handle = fopen($local_file, 'w');
// set up basic connection
$ftp = ftp_connect($ftp_server);
// login with username and password
$login_result = ftp_login($ftp, $ftp_user_name, $ftp_user_pass);
// try to download $remote_file and save it to $handle
if (ftp_fget($ftp, $handle, $remote_file, FTP_ASCII, 0)) {
echo "successfully written to $local_file\n";
} else {
echo "There was a problem while downloading $remote_file to $local_file\n";
}
// close the connection and the file handler
ftp_close($ftp);
fclose($handle);
?>`

### See Also [¶](https://www.php.net/manual/en/function.ftp-fget.php\#refsect1-function.ftp-fget-seealso)

- [ftp\_get()](https://www.php.net/manual/en/function.ftp-get.php) \- Downloads a file from the FTP server
- [ftp\_nb\_get()](https://www.php.net/manual/en/function.ftp-nb-get.php) \- Retrieves a file from the FTP server and writes it to a local file (non-blocking)
- [ftp\_nb\_fget()](https://www.php.net/manual/en/function.ftp-nb-fget.php) \- Retrieves a file from the FTP server and writes it to an open file (non-blocking)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/ftp/functions/ftp-fget.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.ftp-fget%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ftp-fget&repo=en&redirect=https://www.php.net/manual/en/function.ftp-fget.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=86106&page=function.ftp-fget&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86106&page=function.ftp-fget&vote=down "Vote down!")

8


[**_broom at alturnanetworks dot com_**](https://www.php.net/manual/en/function.ftp-fget.php#86106) [¶](https://www.php.net/manual/en/function.ftp-fget.php#86106)

**17 years ago**

`Another ftp_get_contents approach, using a temperary stream handler. Returns file contents as string.
<?php
function ftp_get_contents ($conn_id, $filename,
//Create temp handler:
    $tempHandle = fopen('php://temp', 'r+');
//Get file from FTP assuming that it exists:
    ftp_fget($conn_id, $tempHandle, $filename, FTP_ASCII, 0));
    //Getting detailed stats to check filesize:
    $fstats = fstat($tempHandle);
    return fread($tempHandle, $fstats['size']);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=86107&page=function.ftp-fget&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86107&page=function.ftp-fget&vote=down "Vote down!")

5


[**_broom at alturnanetworks dot com_**](https://www.php.net/manual/en/function.ftp-fget.php#86107) [¶](https://www.php.net/manual/en/function.ftp-fget.php#86107)

**17 years ago**

`<?php
/**
* Function returns contents via FTP connection and returns it as string (right version...)
*/
function ftp_get_contents ($conn_id, $filename) {
    //Create temp handler:
    $tempHandle = fopen('php://temp', 'r+');

    //Get file from FTP:
    if (@ftp_fget($conn_id, $tempHandle, $filename, FTP_ASCII, 0)) {
        rewind($tempHandle);
        return stream_get_contents($tempHandle);
    } else {
        return false;
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=120599&page=function.ftp-fget&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120599&page=function.ftp-fget&vote=down "Vote down!")

1


[**_lionskape at gmail dot com_**](https://www.php.net/manual/en/function.ftp-fget.php#120599) [¶](https://www.php.net/manual/en/function.ftp-fget.php#120599)

**8 years ago**

`if you are using windows ftp-server with cp1251 encoding there are some troubles with russian "я" in filename\path.
php use telnet to connect ftp-server and there are special symbol with code 255 in telnet protocol. You can try use ftp_raw($connection, 'OPTS UTF8 ON'); and work in utf-8 (if server provides it).
P.S. sorry for my bad english`

[up](https://www.php.net/manual/vote-note.php?id=111548&page=function.ftp-fget&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111548&page=function.ftp-fget&vote=down "Vote down!")

1


[**_mike at eastghost dot com_**](https://www.php.net/manual/en/function.ftp-fget.php#111548) [¶](https://www.php.net/manual/en/function.ftp-fget.php#111548)

**12 years ago**

`You might need to use ftp_pasv() if you're behind a firewall and receiving odd timeouts, file creation but now local data saving, etc.`

[up](https://www.php.net/manual/vote-note.php?id=80912&page=function.ftp-fget&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80912&page=function.ftp-fget&vote=down "Vote down!")

 -2


[**_justrafi at gmail dot com_**](https://www.php.net/manual/en/function.ftp-fget.php#80912) [¶](https://www.php.net/manual/en/function.ftp-fget.php#80912)

**17 years ago**

`I was in need to synchronize two folders on two separate servers, one is a Windows server, and the other is a Linux server. I created this short and sweet function to help me do this. PLEASE NOTICE: This will not copy folders, and probably will fail if remote folder contains anything else than files.
function sync_folders($host, $port, $username, $password, $remote_dir, $local_dir, $passive_mode = true) {
    $conn_id = ftp_connect($host, $port);
    if (!$conn_id) return false; # fail to connect
    if (!ftp_login($conn_id, $username, $password)) { ftp_close($conn_id); return false; }  # fail to login
    ftp_pasv($conn_id, $passive_mode);
    if (!ftp_chdir($conn_id, $remote_dir)) { ftp_close($conn_id); return false; } # fail to change dir
    if (substr($local_dir, -1) != '/') $local_dir .= '/';
    $list = ftp_nlist($conn_id, '.');
    sort($list);
    foreach ($list as $file) {
        if (!file_exists($local_dir . $file)) {
            $is_copied = ftp_get($conn_id, $local_dir . $file, $file, FTP_BINARY);
        }
    }
    ftp_close($conn_id);
    return true;
}`

[up](https://www.php.net/manual/vote-note.php?id=24974&page=function.ftp-fget&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=24974&page=function.ftp-fget&vote=down "Vote down!")

 -5


[**_rodrigo-rocha at oi dot net dot br_**](https://www.php.net/manual/en/function.ftp-fget.php#24974) [¶](https://www.php.net/manual/en/function.ftp-fget.php#24974)

**23 years ago**

`If you suply only a filename to the second parameter of function the ftp_get will open a pointer to the local file creating it and write to it.It's ok if your server dont execute for to mutch time and you dont get too many files but if you do it too many times the pointers created by ftp_get will not be closed and will end your opened files capacity at your server making it to do not open any more files until you restart it.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ftp-fget&repo=en&redirect=https://www.php.net/manual/en/function.ftp-fget.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google