---
url: https://www.php.net/manual/en/stream.examples.php
scraped_at: 2025-10-20T02:46:31.724Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Examples [¶](https://www.php.net/manual/en/stream.examples.php\#stream.examples)

## Table of Contents [¶](https://www.php.net/manual/en/stream.examples.php\#stream.examples)

- [Example class registered as stream wrapper](https://www.php.net/manual/en/stream.streamwrapper.example-1.php)

**Example #1 Using [file\_get\_contents()](https://www.php.net/manual/en/function.file-get-contents.php)**
**to retrieve data from multiple sources**

`<?php
/* Read local file from /home/bar */
$localfile = file_get_contents("/home/bar/foo.txt");
/* Identical to above, explicitly naming FILE scheme */
$localfile = file_get_contents("file:///home/bar/foo.txt");
/* Read remote file from www.example.com using HTTP */
$httpfile  = file_get_contents("http://www.example.com/foo.txt");
/* Read remote file from www.example.com using HTTPS */
$httpsfile = file_get_contents("https://www.example.com/foo.txt");
/* Read remote file from ftp.example.com using FTP */
$ftpfile   = file_get_contents("ftp://user:pass@ftp.example.com/foo.txt");
/* Read remote file from ftp.example.com using FTPS */
$ftpsfile  = file_get_contents("ftps://user:pass@ftp.example.com/foo.txt");
?>`

**Example #2 Making a POST request to an https server**

`<?php
/* Send POST request to https://secure.example.com/form_action.php
* Include form elements named "foo" and "bar" with dummy values
*/
$sock = fsockopen("ssl://secure.example.com", 443, $errno, $errstr, 30);
if (!$sock) die("$errstr ($errno)\n");
$data = "foo=" . urlencode("Value for Foo") . "&bar=" . urlencode("Value for Bar");
fwrite($sock, "POST /form_action.php HTTP/1.0\r\n");
fwrite($sock, "Host: secure.example.com\r\n");
fwrite($sock, "Content-type: application/x-www-form-urlencoded\r\n");
fwrite($sock, "Content-length: " . strlen($data) . "\r\n");
fwrite($sock, "Accept: */*\r\n");
fwrite($sock, "\r\n");
fwrite($sock, $data);
$headers = "";
while ($str = trim(fgets($sock, 4096)))
$headers .= "$str\n";
echo "\n";
$body = "";
while (!feof($sock))
$body .= fgets($sock, 4096);
fclose($sock);
?>`

**Example #3 Writing data to a compressed file**

`<?php
/* Create a compressed file containing an arbitrary string
* File can be read back using compress.zlib stream or just
* decompressed from the command line using 'gzip -d foo-bar.txt.gz'
*/
$fp = fopen("compress.zlib://foo-bar.txt.gz", "wb");
if (!$fp) die("Unable to create file.");
fwrite($fp, "This is a test.\n");
fclose($fp);
?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/stream/examples.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fstream.examples%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=stream.examples&repo=en&redirect=https://www.php.net/manual/en/stream.examples.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google