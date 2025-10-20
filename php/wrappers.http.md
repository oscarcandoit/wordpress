---
url: https://www.php.net/manual/en/wrappers.http.php
scraped_at: 2025-10-20T02:31:40.513Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# http://

# https://

http:// \-\- https:// — Accessing HTTP(s) URLs

### Description [¶](https://www.php.net/manual/en/wrappers.http.php\#refsect1-wrappers.http-description)

Allows read-only access to files/resources via HTTP.
By default, a HTTP 1.0 GET is used. A `Host:` header is sent with the request
to handle name-based virtual hosts. If you have configured
a [user\_agent](https://www.php.net/manual/en/filesystem.configuration.php#ini.user-agent) string using
your php.ini file or the stream context, it will also be included
in the request.


The stream allows access to the _body_ of
the resource; the headers are stored in the
[$http\_response\_header](https://www.php.net/manual/en/reserved.variables.httpresponseheader.php) variable.


If it's important to know the URL of the resource where
your document came from (after all redirects have been processed),
you'll need to process the series of response headers returned by the
stream.


The [from](https://www.php.net/manual/en/filesystem.configuration.php#ini.from) directive will be used for the
`From:` header if set and not overwritten by the
[Context options and parameters](https://www.php.net/manual/en/context.php).


### Usage [¶](https://www.php.net/manual/en/wrappers.http.php\#refsect1-wrappers.http-usage)

- http://example.com
- http://example.com/file.php?var1=val1&var2=val2
- http://user:password@example.com
- https://example.com
- https://example.com/file.php?var1=val1&var2=val2
- https://user:password@example.com

### Options [¶](https://www.php.net/manual/en/wrappers.http.php\#refsect1-wrappers.http-options)

| Attribute | Supported |
| --- | --- |
| Restricted by [allow\_url\_fopen](https://www.php.net/manual/en/filesystem.configuration.php#ini.allow-url-fopen) | Yes |
| Allows Reading | Yes |
| Allows Writing | No |
| Allows Appending | No |
| Allows Simultaneous Reading and Writing | N/A |
| Supports [stat()](https://www.php.net/manual/en/function.stat.php) | No |
| Supports [unlink()](https://www.php.net/manual/en/function.unlink.php) | No |
| Supports [rename()](https://www.php.net/manual/en/function.rename.php) | No |
| Supports [mkdir()](https://www.php.net/manual/en/function.mkdir.php) | No |
| Supports [rmdir()](https://www.php.net/manual/en/function.rmdir.php) | No |

**Wrapper Summary**

### Examples [¶](https://www.php.net/manual/en/wrappers.http.php\#refsect1-wrappers.http-examples)

**Example #1 Detecting which URL we ended up on after redirects**

`<?php
$url = 'http://www.example.com/redirecting_page.php';
$fp = fopen($url, 'r');
$meta_data = stream_get_meta_data($fp);
foreach ($meta_data['wrapper_data'] as $response) {
    /* Were we redirected? */
    if (strtolower(substr($response, 0, 10)) == 'location: ') {
        /* update $url with where we were redirected to */
        $url = substr($response, 10);
    }
}
?>`

### Notes [¶](https://www.php.net/manual/en/wrappers.http.php\#refsect1-wrappers.http-notes)

> **Note**:
>
> HTTPS is only supported when the [openssl](https://www.php.net/manual/en/book.openssl.php)
> extension is enabled.

HTTP connections are read-only; writing data or copying
files to an HTTP resource is not supported.


Sending _POST_ and _PUT_ requests, for example,
can be done with the help of [HTTP Contexts](https://www.php.net/manual/en/context.http.php).


### See Also [¶](https://www.php.net/manual/en/wrappers.http.php\#refsect1-wrappers.http-seealso)

- [HTTP context options](https://www.php.net/manual/en/context.http.php)
- [$http\_response\_header](https://www.php.net/manual/en/reserved.variables.httpresponseheader.php)
- [stream\_get\_meta\_data()](https://www.php.net/manual/en/function.stream-get-meta-data.php) \- Retrieves header/meta data from streams/file pointers

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/wrappers/http.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fwrappers.http%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=wrappers.http&repo=en&redirect=https://www.php.net/manual/en/wrappers.http.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=71226&page=wrappers.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=71226&page=wrappers.http&vote=down "Vote down!")

7


[**_dwalton at acm dot org_**](https://www.php.net/manual/en/wrappers.http.php#71226) [¶](https://www.php.net/manual/en/wrappers.http.php#71226)

**18 years ago**

`As it says on this page:
"The stream allows access to the body of the resource; the headers are stored in the $http_response_header variable. Since PHP 4.3.0, the headers are available using stream_get_meta_data()."
This one sentence is the only documentation I have found on the mysterious $http_response_header variable, and I'm afraid it's misleading.  It implies that from 4.3.0 onward, stream_get_meta_data() ought to be used in favor of $http_response_header.
Don't be fooled!  stream_get_meta_data() requires a stream reference, which makes it ONLY useful with fopen() and related functions.  However, $http_response_header can be used to get the headers from the much simpler file_get_contents() and related functions, which makes it still very useful in 5.x.
Also note that even when file_get_contents() and friends fail due to a 4xx or 5xx error and return false, the headers are still available in $http_response_header.`

[up](https://www.php.net/manual/vote-note.php?id=118291&page=wrappers.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118291&page=wrappers.http&vote=down "Vote down!")

5


[**_Rainer Perske_**](https://www.php.net/manual/en/wrappers.http.php#118291) [¶](https://www.php.net/manual/en/wrappers.http.php#118291)

**9 years ago**

`Passing authentication information in the URL as in " [https://user:password@example.com](https://user:password@example.com/)" works for HTTP "Basic" access authentication but not for HTTP "Digest" access authentication. You can use the cURL functions for servers requesting HTTP "Digest" access authentication.`

[up](https://www.php.net/manual/vote-note.php?id=76760&page=wrappers.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76760&page=wrappers.http&vote=down "Vote down!")

1


[**_NEA at AraTaraBul dot com_**](https://www.php.net/manual/en/wrappers.http.php#76760) [¶](https://www.php.net/manual/en/wrappers.http.php#76760)

**18 years ago**

`HTTP post function;
<?php
function post_it($datastream, $url) {
$url = preg_replace("@^ [http://@i](http://i/)", "", $url);
$host = substr($url, 0, strpos($url, "/"));
$uri = strstr($url, "/");
      $reqbody = "";
      foreach($datastream as $key=>$val) {
          if (!empty($reqbody)) $reqbody.= "&";
      $reqbody.= $key."=".urlencode($val);
      }
$contentlength = strlen($reqbody);
     $reqheader =  "POST $uri HTTP/1.1\r\n".
                   "Host: $host\n". "User-Agent: PostIt\r\n".
     "Content-Type: application/x-www-form-urlencoded\r\n".
     "Content-Length: $contentlength\r\n\r\n".
     "$reqbody\r\n";
$socket = fsockopen($host, 80, $errno, $errstr);
if (!$socket) {
$result["errno"] = $errno;
$result["errstr"] = $errstr;
return $result;
}
fputs($socket, $reqheader);
while (!feof($socket)) {
$result[] = fgets($socket, 4096);
}
fclose($socket);
return $result;
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=wrappers.http&repo=en&redirect=https://www.php.net/manual/en/wrappers.http.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google