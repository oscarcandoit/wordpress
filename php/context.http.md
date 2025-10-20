---
url: https://www.php.net/manual/en/context.http.php
scraped_at: 2025-10-20T02:34:53.496Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# HTTP context options

HTTP context options — HTTP context option listing

### Description [¶](https://www.php.net/manual/en/context.http.php\#refsect1-context.http-description)

Context options for `http://` and `https://`
transports.


### Options [¶](https://www.php.net/manual/en/context.http.php\#refsect1-context.http-options)

`method` [string](https://www.php.net/manual/en/language.types.string.php)

**`GET`**, **`POST`**, or
any other HTTP method supported by the remote server.


Defaults to **`GET`**.


`header` [array](https://www.php.net/manual/en/language.types.array.php) or [string](https://www.php.net/manual/en/language.types.string.php)

Additional headers to be sent during request. Values
in this option will override other values (such as
`User-agent:`, `Host:`,
and `Authentication:`),
even when following `Location:` redirects.
Thus it is not recommended to set a `Host:` header,
if `follow_location` is enabled.


String value should be `Key: value` pairs delimited by
`\r\n`, e.g.
`"Content-Type: application/json\r\nConnection: close"`.
Array value should be a list of `Key: value` pairs, e.g.
`["Content-Type: application/json", "Connection: close"]`.


`user_agent` [string](https://www.php.net/manual/en/language.types.string.php)

Value to send with `User-Agent:` header. This value will
only be used if user-agent is _not_ specified
in the `header` context option above.


By default the
[user\_agent](https://www.php.net/manual/en/filesystem.configuration.php#ini.user-agent) php.ini setting is used.


`content` [string](https://www.php.net/manual/en/language.types.string.php)

Additional data to be sent after the headers. Typically used
with POST or PUT requests.


`proxy` [string](https://www.php.net/manual/en/language.types.string.php)

URI specifying address of proxy server (e.g.
`tcp://proxy.example.com:5100`).


`request_fulluri` [bool](https://www.php.net/manual/en/language.types.boolean.php)

When set to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, the entire URI will be used when
constructing the request (e.g.
`GET http://www.example.com/path/to/file.html HTTP/1.0`).
While this is a non-standard request format, some
proxy servers require it.


Defaults to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


`follow_location` [int](https://www.php.net/manual/en/language.types.integer.php)

Follow `Location` header redirects. Set to
`0` to disable.


Defaults to `1`.


`max_redirects` [int](https://www.php.net/manual/en/language.types.integer.php)

The max number of redirects to follow. Value `1` or
less means that no redirects are followed.


Defaults to `20`.


`protocol_version` [float](https://www.php.net/manual/en/language.types.float.php)

HTTP protocol version.


Defaults to `1.1` as of PHP 8.0.0;
prior to that version the default was `1.0`.


`timeout` [float](https://www.php.net/manual/en/language.types.float.php)

Read timeout in seconds, specified by a [float](https://www.php.net/manual/en/language.types.float.php)
(e.g. `10.5`).


By default the
[default\_socket\_timeout](https://www.php.net/manual/en/filesystem.configuration.php#ini.default-socket-timeout) php.ini setting is used.


`ignore_errors` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Fetch the content even on failure status codes.


Defaults to **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


### Examples [¶](https://www.php.net/manual/en/context.http.php\#refsect1-context.http-examples)

**Example #1 Fetch a page and send POST data**

`<?php
$postdata = http_build_query(
    [\
        'var1' => 'some content',\
        'var2' => 'doh',\
    ]
);
$opts = [\
    'http' => [\
        'method'  => 'POST',\
        'header'  => 'Content-type: application/x-www-form-urlencoded',\
        'content' => $postdata,\
    ]\
];
$context = stream_context_create($opts);
$result = file_get_contents('http://example.com/submit.php', false, $context);
?>`

**Example #2 Ignore redirects but fetch headers and content**

`<?php
$url = "http://www.example.org/header.php";
$opts = [\
    'http' => [\
        'method'        => 'GET',\
        'max_redirects' => '0',\
        'ignore_errors' => '1',\
    ]\
];
$context = stream_context_create($opts);
$stream = fopen($url, 'r', false, $context);
// header information as well as meta data
// about the stream
var_dump(stream_get_meta_data($stream));
// actual data at $url
var_dump(stream_get_contents($stream));
fclose($stream);
?>`

### Notes [¶](https://www.php.net/manual/en/context.http.php\#refsect1-context.http-notes)

> **Note**:
> **Underlying socket stream context options**
>
> Additional context options may be supported by the
> [underlying transport](https://www.php.net/manual/en/transports.inet.php)
> For `http://` streams, refer to context
> options for the `tcp://` transport. For
> `https://` streams, refer to context options
> for the `ssl://` transport.

> **Note**:
> **HTTP status line**
>
> When this stream wrapper follows a redirect, the
> `wrapper_data` returned by
> [stream\_get\_meta\_data()](https://www.php.net/manual/en/function.stream-get-meta-data.php) might not necessarily contain
> the HTTP status line that actually applies to the content data at index
> `0`.
>
>
> ```
> array (
>   'wrapper_data' =>
>   array (
>     0 => 'HTTP/1.0 301 Moved Permanently',
>     1 => 'Cache-Control: no-cache',
>     2 => 'Connection: close',
>     3 => 'Location: http://example.com/foo.jpg',
>     4 => 'HTTP/1.1 200 OK',
>     ...
> ```
>
>  The first request returned a `301` (permanent redirect),
>  so the stream wrapper automatically followed the redirect to get a
>  `200` response (index = `4`).

### See Also [¶](https://www.php.net/manual/en/context.http.php\#refsect1-context.http-seealso)

- [http://](https://www.php.net/manual/en/wrappers.http.php)
- [Socket context options](https://www.php.net/manual/en/context.socket.php)
- [SSL context options](https://www.php.net/manual/en/context.ssl.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/context/http.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fcontext.http%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=context.http&repo=en&redirect=https://www.php.net/manual/en/context.http.php)

### User Contributed Notes 12 notes

[up](https://www.php.net/manual/vote-note.php?id=114867&page=context.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114867&page=context.http&vote=down "Vote down!")

33


[**_nate_**](https://www.php.net/manual/en/context.http.php#114867) [¶](https://www.php.net/manual/en/context.http.php#114867)

**11 years ago**

`Note that if you set the protocol_version option to 1.1 and the server you are requesting from is configured to use keep-alive connections, the function (fopen, file_get_contents, etc.) will "be slow" and take a long time to complete. This is a feature of the HTTP 1.1 protocol you are unlikely to use with stream contexts in PHP.
Simply add a "Connection: close" header to the request to eliminate the keep-alive timeout:
<?php
// php 5.4 : array syntax and header option with array value
$data = file_get_contents(' [http://www.example.com/](http://www.example.com/)', null, stream_context_create([\
    'http' => [\
        'protocol_version' => 1.1,\
        'header'           => [\
            'Connection: close',\
        ],\
    ],\
]));
?>`

[up](https://www.php.net/manual/vote-note.php?id=121762&page=context.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121762&page=context.http&vote=down "Vote down!")

18


[**_daniel dot peder at gmail dot com_**](https://www.php.net/manual/en/context.http.php#121762) [¶](https://www.php.net/manual/en/context.http.php#121762)

**8 years ago**

`note that for both http and https protocols require the same 'http' context keyword:
<?php
// CORRECT example:
// this will work as expected
// note the url with https but context with http
$correct_data = file_get_contents(' [https://example.com](https://example.com/)', false, stream_context_create(array('http' => array(...))));
// INVALID example:
// this will not work, the context will be ignored
// note the url with https also context with https
$correct_data = file_get_contents(' [https://example.com](https://example.com/)', false, stream_context_create(array('https' => array(...))));`

[up](https://www.php.net/manual/vote-note.php?id=125832&page=context.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125832&page=context.http&vote=down "Vote down!")

6


[**_ASchmidt at Anamera dot net_**](https://www.php.net/manual/en/context.http.php#125832) [¶](https://www.php.net/manual/en/context.http.php#125832)

**4 years ago**

`With the default of
    'follow_location'   =>  1
be certain NEVER include a "Host:" header in the 'header' array.
If the host is set to "mydomain.com", and that web site has a (quite common) redirect to "www.mydomain.com", then the initial request to " [http://mydomain.com](http://mydomain.com/)" will get the expected response of:
HTTP/1.1 301 Moved Permanently
Location: [http://www.mydomain.com/](http://www.mydomain.com/)
However, the follow-up request does NOT replace the original "host" header with the new "location" value, as one would expect. Consequently each "follow-location" request will again be served by the original host of " [http://mydomain.com](http://mydomain.com/)", and continue the redirect loop until 'max_redirects' has been exhausted.
(For details: [https://bugs.php.net/bug.php?id=77889](https://bugs.php.net/bug.php?id=77889))`

[up](https://www.php.net/manual/vote-note.php?id=121763&page=context.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121763&page=context.http&vote=down "Vote down!")

17


[**_daniel.peder (a) gmail.com_**](https://www.php.net/manual/en/context.http.php#121763) [¶](https://www.php.net/manual/en/context.http.php#121763)

**8 years ago**

`note that both http and https transports require the same context name http
// OK example:
// this will work as expected
// note the url with https but context with http
$correct_data = file_get_contents(' [https://example.com](https://example.com/)', false, stream_context_create(array('http' => array(...))));
// INVALID example:
// this will not work, the context will be ignored
// note the url with https also context with https
$correct_data = file_get_contents(' [https://example.com](https://example.com/)', false, stream_context_create(array('https' => array(...))));`

[up](https://www.php.net/manual/vote-note.php?id=121470&page=context.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121470&page=context.http&vote=down "Vote down!")

5


[**_ywarnier at beeznest dot org_**](https://www.php.net/manual/en/context.http.php#121470) [¶](https://www.php.net/manual/en/context.http.php#121470)

**8 years ago**

`Note that setting request_fulluri to true will *change* the value of $_SERVER['REQUEST_URI] on the receiving end (from /abc.php to [http://domain.com/abc.php](http://domain.com/abc.php)).`

[up](https://www.php.net/manual/vote-note.php?id=101933&page=context.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101933&page=context.http&vote=down "Vote down!")

15


[**_gourav sarkar_**](https://www.php.net/manual/en/context.http.php#101933) [¶](https://www.php.net/manual/en/context.http.php#101933)

**14 years ago**

`watch your case when using methods (POST and GET)...it must be always uppercase. in case of you write it in lower case it wont work.`

[up](https://www.php.net/manual/vote-note.php?id=121671&page=context.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121671&page=context.http&vote=down "Vote down!")

7


[**_aruntechguy at outlook dot com_**](https://www.php.net/manual/en/context.http.php#121671) [¶](https://www.php.net/manual/en/context.http.php#121671)

**8 years ago**

`If you want to use Basic Auth while using get_headers(), use stream_context options below.
I am using HEAD method here, but please feel free to use GET also.
<?php
$targetUrl = 'http or https target url here';
$basicAuth = base64_encode('username:password');
stream_context_set_default(
    [\
        'http' => [\
            'method' => 'HEAD',\
            'header' => 'Authorization: Basic ' . $basicAuth\
        ]\
    ]
);
$result = get_headers($targetUrl);
print_r($result);`

[up](https://www.php.net/manual/vote-note.php?id=129638&page=context.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129638&page=context.http&vote=down "Vote down!")

2


[**_njt1982 at yahoo dot com_**](https://www.php.net/manual/en/context.http.php#129638) [¶](https://www.php.net/manual/en/context.http.php#129638)

**1 year ago**

``It's worth noting that the `header` array seems to only want an array of strings, not an associative array.
I just spent a chunk of time debugging something not working as expected (no errors though) which was fixed by converting an associative array of headers into a simple array of strings.``

[up](https://www.php.net/manual/vote-note.php?id=110449&page=context.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110449&page=context.http&vote=down "Vote down!")

10


[**_vchampion at gmail dot com_**](https://www.php.net/manual/en/context.http.php#110449) [¶](https://www.php.net/manual/en/context.http.php#110449)

**12 years ago**

`If you use the proxy server and encounter an error "fopen( [http://example.com](http://example.com/)): failed to open stream: HTTP request failed! HTTP/1.0 400 Bad Request" note that in many situations you need also set the parameter "request_fulluri" to "true" in your stream options. Without this option the php script sends the empty request to the server as "GET / HTTP/0.0" and the proxy server replies to it with the "HTTP 400" error.
For example (working sample):
<?php
$stream = stream_context_create(Array("http" => Array("method"  => "GET",
                                                      "timeout" => 20,
                                                      "header"  => "User-agent: Myagent",
                                                      "proxy"   => "tcp://my-proxy.localnet:3128",
                                                      'request_fulluri' => True /* without this option we get an HTTP error! */
                                )));
if ( $fp = fopen(" [http://example.com](http://example.com/)", 'r', false, $stream) ) {
    print "well done";
}
?>
P>S> PHP 5.3.17`

[up](https://www.php.net/manual/vote-note.php?id=117092&page=context.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117092&page=context.http&vote=down "Vote down!")

7


[**_jay_**](https://www.php.net/manual/en/context.http.php#117092) [¶](https://www.php.net/manual/en/context.http.php#117092)

**10 years ago**

`Remember to match content with Content-type:
<?php
$data = array(
    'var1' => 'some content',
    'var2' => 'doh'
);
$opts = array('http' =>
    array(
        'method'  => 'POST',
        'header'  => 'Content-type: application/json',  // here...
        'content' => json_encode($data)  // and here.
    )
);
. . .
?>`

[up](https://www.php.net/manual/vote-note.php?id=114314&page=context.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114314&page=context.http&vote=down "Vote down!")

4


[**_chris_**](https://www.php.net/manual/en/context.http.php#114314) [¶](https://www.php.net/manual/en/context.http.php#114314)

**11 years ago**

`I had quite a bit of trouble trying to make a request with fopen through a proxy to a secure url.  I kept getting a 400 Bad Request back from the remote host.  It was receiving the proxy url as the SNI host.  In order to get around this I had to explicity set the SNI host to the domain I was trying to reach.  It's apparently the issue outlined in this bug:
[https://bugs.php.net/bug.php?id=63519](https://bugs.php.net/bug.php?id=63519)
<?php
$domain = parse_url($file, PHP_URL_HOST);
$proxy_string = "tcp://" . WP_PROXY_HOST  . ":" . WP_PROXY_PORT;
$opts = array(
    'http' => array( 'proxy' => $proxy_string ),
    'ssl' => array( 'SNI_enabled' => true, 'SNI_server_name' => $domain));
$context = stream_context_create($opts);
$handle = fopen( $file, 'r', false, $context );
?>`

[up](https://www.php.net/manual/vote-note.php?id=130179&page=context.http&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130179&page=context.http&vote=down "Vote down!")

0


[**_bigtree at 29a dot nl_**](https://www.php.net/manual/en/context.http.php#130179) [¶](https://www.php.net/manual/en/context.http.php#130179)

**6 months ago**

`If you pass the 'header' option as a string and you have multiple headers, they must be separated by "\r\n".`

[＋add a note](https://www.php.net/manual/add-note.php?sect=context.http&repo=en&redirect=https://www.php.net/manual/en/context.http.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google