---
url: https://www.php.net/manual/en/ziparchive.getstream.php
scraped_at: 2025-10-20T02:51:31.121Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ZipArchive::getStream

(PHP 5 >= 5.2.0, PHP 7, PHP 8, PECL zip >= 1.1.0)

ZipArchive::getStream — Get a file handler to the entry defined by its name (read only)

### Description [¶](https://www.php.net/manual/en/ziparchive.getstream.php\#refsect1-ziparchive.getstream-description)

public**ZipArchive::getStream**([string](https://www.php.net/manual/en/language.types.string.php) `$name`): [resource](https://www.php.net/manual/en/language.types.resource.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Get a file handler to the entry defined by its name. For now, it only
supports read operations.


### Parameters [¶](https://www.php.net/manual/en/ziparchive.getstream.php\#refsect1-ziparchive.getstream-parameters)

`name`

The name of the entry to use.


### Return Values [¶](https://www.php.net/manual/en/ziparchive.getstream.php\#refsect1-ziparchive.getstream-returnvalues)

Returns a file pointer (resource) on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/ziparchive.getstream.php\#refsect1-ziparchive.getstream-examples)

**Example #1 Get the entry contents with [fread()](https://www.php.net/manual/en/function.fread.php) and store it**

`<?php
$contents = '';
$z = new ZipArchive();
if ($z->open('test.zip')) {
    $fp = $z->getStream('test');
    if(!$fp) exit("failed\n");
    while (!feof($fp)) {
        $contents .= fread($fp, 2);
    }
    fclose($fp);
    file_put_contents('t',$contents);
    echo "done.\n";
}
?>`

**Example #2 Same as the previous example but with [fopen()](https://www.php.net/manual/en/function.fopen.php) and the zip**
**stream wrapper**

`<?php
$contents = '';
$fp = fopen('zip://' . dirname(__FILE__) . '/test.zip#test', 'r');
if (!$fp) {
    exit("cannot open\n");
}
while (!feof($fp)) {
    $contents .= fread($fp, 2);
}
echo "$contents\n";
fclose($fp);
echo "done.\n";
?>`

**Example #3 Stream wrapper and image, can be used with the xml function**
**as well**

`<?php
$im = imagecreatefromgif('zip://' . dirname(__FILE__) . '/test_im.zip#pear_item.gif');
imagepng($im, 'a.png');
?>`

### See Also [¶](https://www.php.net/manual/en/ziparchive.getstream.php\#refsect1-ziparchive.getstream-seealso)

- [ZipArchive::getStreamIndex()](https://www.php.net/manual/en/ziparchive.getstreamindex.php) \- Get a file handler to the entry defined by its index (read only)
- [ZipArchive::getStreamName()](https://www.php.net/manual/en/ziparchive.getstreamname.php) \- Get a file handler to the entry defined by its name (read only)
- [Compression Streams](https://www.php.net/manual/en/wrappers.compression.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/zip/ziparchive/getstream.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fziparchive.getstream%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ziparchive.getstream&repo=en&redirect=https://www.php.net/manual/en/ziparchive.getstream.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=127211&page=ziparchive.getstream&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127211&page=ziparchive.getstream&vote=down "Vote down!")

2


[**_Sbastien_**](https://www.php.net/manual/en/ziparchive.getstream.php#127211) [¶](https://www.php.net/manual/en/ziparchive.getstream.php#127211)

**3 years ago**

`Here a way to handle specific files from a zip archive without full extract :
<?php
$zip_file = '/path/to/file.zip'; // I wan to get stream a CSV files
$zip = new ZipArchive();
$zip->open($zip_file);
for ($i = 0; $i < $zip->numFiles; $i++) { // Check file by file
    $name = $zip->getNameIndex($i); // Retrieve entry name
    $extension = pathinfo($name, PATHINFO_EXTENSION);
    if ($extension === 'csv') { // I want to handle csv files
        $stream = $zip->getStream($name); // No stream index access before PHP 8.2
        // Starting PHP 8.2 $zip->getStreamIndex() or $zip->getStreamName()
        // Do stuff with $stream
        // ...
    }
}`

[up](https://www.php.net/manual/vote-note.php?id=126872&page=ziparchive.getstream&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126872&page=ziparchive.getstream&vote=down "Vote down!")

0


[**_oleg at andreyev dot lv_**](https://www.php.net/manual/en/ziparchive.getstream.php#126872) [¶](https://www.php.net/manual/en/ziparchive.getstream.php#126872)

**3 years ago**

`Keep in mind that this stream is not rewindable/seekable.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=ziparchive.getstream&repo=en&redirect=https://www.php.net/manual/en/ziparchive.getstream.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google