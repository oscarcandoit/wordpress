---
url: https://www.php.net/manual/en/function.zlib-decode.php
scraped_at: 2025-10-20T02:57:57.859Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# zlib\_decode

(PHP 5 >= 5.4.0, PHP 7, PHP 8)

zlib\_decode — Uncompress any raw/gzip/zlib encoded data

### Description [¶](https://www.php.net/manual/en/function.zlib-decode.php\#refsect1-function.zlib-decode-description)

**zlib\_decode**([string](https://www.php.net/manual/en/language.types.string.php) `$data`, [int](https://www.php.net/manual/en/language.types.integer.php) `$max_length` = 0): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Uncompress any raw/gzip/zlib encoded data.


**Warning**

This function is
currently not documented; only its argument list is available.

### Parameters [¶](https://www.php.net/manual/en/function.zlib-decode.php\#refsect1-function.zlib-decode-parameters)

`data``max_length`

### Return Values [¶](https://www.php.net/manual/en/function.zlib-decode.php\#refsect1-function.zlib-decode-returnvalues)

Returns the uncompressed data, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### See Also [¶](https://www.php.net/manual/en/function.zlib-decode.php\#refsect1-function.zlib-decode-seealso)

- [zlib\_encode()](https://www.php.net/manual/en/function.zlib-encode.php) \- Compress data with the specified encoding

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/zlib/functions/zlib-decode.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.zlib-decode%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.zlib-decode&repo=en&redirect=https://www.php.net/manual/en/function.zlib-decode.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=112214&page=function.zlib-decode&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112214&page=function.zlib-decode&vote=down "Vote down!")

15


[**_anonymous at dekho-ji dot com_**](https://www.php.net/manual/en/function.zlib-decode.php#112214) [¶](https://www.php.net/manual/en/function.zlib-decode.php#112214)

**12 years ago**

`To decode / uncompress the received HTTP POST data in PHP code, request data coming from Java / Android application via HTTP POST GZIP / DEFLATE compressed format
1) Data sent from Java Android app to PHP using DeflaterOutputStream java class and received in PHP as shown below
echo gzinflate( substr($HTTP_RAW_POST_DATA,2,-4) ) . PHP_EOL  . PHP_EOL;
2) Data sent from Java Android app to PHP using GZIPOutputStream java class and received in PHP code as shown below
echo gzinflate( substr($HTTP_RAW_POST_DATA,10,-8) ) . PHP_EOL  . PHP_EOL;
From Java Android side (API level 10+), data being sent in DEFLATE compressed format
        String body = "Lorem ipsum shizzle ma nizle";
        URL url = new URL(" [http://www.url.com/postthisdata.php](http://www.url.com/postthisdata.php)");
        URLConnection conn = url.openConnection();
        conn.setDoOutput(true);
        conn.setRequestProperty("Content-encoding", "deflate");
        conn.setRequestProperty("Content-type", "application/octet-stream");
        DeflaterOutputStream dos = new DeflaterOutputStream(
                conn.getOutputStream());
        dos.write(body.getBytes());
        dos.flush();
        dos.close();
        BufferedReader in = new BufferedReader(new InputStreamReader(
                conn.getInputStream()));
        String decodedString = "";
        while ((decodedString = in.readLine()) != null) {
            Log.e("dump",decodedString);
        }
        in.close();
On PHP side (v 5.3.1), code for decompressing this DEFLATE data will be
    echo substr($HTTP_RAW_POST_DATA,2,-4);
From Java Android side (API level 10+), data being sent in GZIP compressed format
        String body1 = "Lorem ipsum shizzle ma nizle";
        URL url1 = new URL(" [http://www.url.com/postthisdata.php](http://www.url.com/postthisdata.php)");
        URLConnection conn1 = url1.openConnection();
        conn1.setDoOutput(true);
        conn1.setRequestProperty("Content-encoding", "gzip");
        conn1.setRequestProperty("Content-type", "application/octet-stream");
        GZIPOutputStream dos1 = new GZIPOutputStream(conn1.getOutputStream());
        dos1.write(body1.getBytes());
        dos1.flush();
        dos1.close();
        BufferedReader in1 = new BufferedReader(new InputStreamReader(
                conn1.getInputStream()));
        String decodedString1 = "";
        while ((decodedString1 = in1.readLine()) != null) {
            Log.e("dump",decodedString1);
        }
        in1.close();
On PHP side (v 5.3.1), code for decompressing this GZIP data will be
    echo substr($HTTP_RAW_POST_DATA,10,-8);
Useful PHP code for printing out compressed data using all available formats.
$data = "Lorem ipsum shizzle ma nizle";
echo "\n\n\n";
for($i=-1;$i<=9;$i++)
    echo chunk_split(strtoupper(bin2hex(gzcompress($data,$i))),2," ") . PHP_EOL  . PHP_EOL;
echo "\n\n\n";
for($i=-1;$i<=9;$i++)
    echo chunk_split(strtoupper(bin2hex(gzdeflate($data,$i))),2," ") . PHP_EOL  . PHP_EOL;
echo "\n\n\n";
for($i=-1;$i<=9;$i++)
    echo chunk_split(strtoupper(bin2hex(gzencode($data,$i,FORCE_GZIP))),2," ") . PHP_EOL  . PHP_EOL;
echo "\n\n\n";
for($i=-1;$i<=9;$i++)
    echo chunk_split(strtoupper(bin2hex(gzencode($data,$i,FORCE_DEFLATE))),2," ") . PHP_EOL  . PHP_EOL;
echo "\n\n\n";
Hope this helps. Please ThumbsUp if this saved you a lot of effort and time.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.zlib-decode&repo=en&redirect=https://www.php.net/manual/en/function.zlib-decode.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google