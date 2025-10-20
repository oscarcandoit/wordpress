---
url: https://www.php.net/manual/en/ref.url.php
scraped_at: 2025-10-20T02:37:41.292Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# URL Functions [¶](https://www.php.net/manual/en/ref.url.php\#ref.url)

## Table of Contents [¶](https://www.php.net/manual/en/ref.url.php\#ref.url)

- [base64\_decode](https://www.php.net/manual/en/function.base64-decode.php) — Decodes data encoded with MIME base64
- [base64\_encode](https://www.php.net/manual/en/function.base64-encode.php) — Encodes data with MIME base64
- [get\_headers](https://www.php.net/manual/en/function.get-headers.php) — Fetches all the headers sent by the server in response to an HTTP request
- [get\_meta\_tags](https://www.php.net/manual/en/function.get-meta-tags.php) — Extracts all meta tag content attributes from a file and returns an array
- [http\_build\_query](https://www.php.net/manual/en/function.http-build-query.php) — Generate URL-encoded query string
- [parse\_url](https://www.php.net/manual/en/function.parse-url.php) — Parse a URL and return its components
- [rawurldecode](https://www.php.net/manual/en/function.rawurldecode.php) — Decode URL-encoded strings
- [rawurlencode](https://www.php.net/manual/en/function.rawurlencode.php) — URL-encode according to RFC 3986
- [urldecode](https://www.php.net/manual/en/function.urldecode.php) — Decodes URL-encoded string
- [urlencode](https://www.php.net/manual/en/function.urlencode.php) — URL-encodes string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/url/reference.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fref.url%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.url&repo=en&redirect=https://www.php.net/manual/en/ref.url.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=32792&page=ref.url&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=32792&page=ref.url&vote=down "Vote down!")

3


[**_chemanfit at hotmail_**](https://www.php.net/manual/en/ref.url.php#32792) [¶](https://www.php.net/manual/en/ref.url.php#32792)

**22 years ago**

`just a side note to the above you will need to add the ?
example
$page=$PHP_SELF."?".$_SERVER['QUERY_STRING'];`

[up](https://www.php.net/manual/vote-note.php?id=38334&page=ref.url&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=38334&page=ref.url&vote=down "Vote down!")

 -1


[**_php at malaker dot com_**](https://www.php.net/manual/en/ref.url.php#38334) [¶](https://www.php.net/manual/en/ref.url.php#38334)

**21 years ago**

`Following method do not show the URL in user browser (as the author claimed) if the code resides in the source page of  FRAME or IFRAME (say SRC="sourcepage.php") . In that case the URL of the SOURCE page is displayed.
$url = sprintf("%s%s%s"," [http://](http:)",$HTTP_HOST,$REQUEST_URI);
echo "$url";
Expected result: [http://localhost/urltest/framedpage.php](http://localhost/urltest/framedpage.php)
Actual result: [http://localhost/urltest/sourcepage.php](http://localhost/urltest/sourcepage.php)`

[up](https://www.php.net/manual/vote-note.php?id=23148&page=ref.url&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=23148&page=ref.url&vote=down "Vote down!")

 -2


[**_jrg45 at pantheon dot yale dot edu_**](https://www.php.net/manual/en/ref.url.php#23148) [¶](https://www.php.net/manual/en/ref.url.php#23148)

**23 years ago**

`Note that $_SERVER["HTTP_REFERER"] may not include GET data that was included in the referring address, depending on the browser.  So if you rely on GET variables to generate a page, it's not a good idea to use HTTP_REFERER to smoothly "bounce" someone back to the page he/she came from.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.url&repo=en&redirect=https://www.php.net/manual/en/ref.url.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google