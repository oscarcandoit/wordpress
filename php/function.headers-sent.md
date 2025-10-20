---
url: https://www.php.net/manual/en/function.headers-sent.php
scraped_at: 2025-10-20T02:53:03.754Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# headers\_sent

(PHP 4, PHP 5, PHP 7, PHP 8)

headers\_sent — Checks if or where headers have been sent

### Description [¶](https://www.php.net/manual/en/function.headers-sent.php\#refsect1-function.headers-sent-description)

**headers\_sent**([string](https://www.php.net/manual/en/language.types.string.php) `&$filename` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, [int](https://www.php.net/manual/en/language.types.integer.php) `&$line` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Checks if or where headers have been sent.


You can't add any more header lines using the [header()](https://www.php.net/manual/en/function.header.php)
function once the header block has already been sent. Using this function
you can at least prevent getting HTTP header related error messages.
Another option is to use [Output Buffering](https://www.php.net/manual/en/ref.outcontrol.php).


### Parameters [¶](https://www.php.net/manual/en/function.headers-sent.php\#refsect1-function.headers-sent-parameters)

`filename`

If the optional `filename` and
`line` parameters are set,
**headers\_sent()** will put the PHP source file name
and line number where output started in the `filename`
and `line` variables.


> **Note**:
>
>
> If the output has started before executing the PHP source file (for example due to a startup error),
> the `filename` parameter will be set to an empty string.

`line`

The line number where the output started.


### Return Values [¶](https://www.php.net/manual/en/function.headers-sent.php\#refsect1-function.headers-sent-returnvalues)

**headers\_sent()** will return **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if no HTTP headers
have already been sent or **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** otherwise.


### Examples [¶](https://www.php.net/manual/en/function.headers-sent.php\#refsect1-function.headers-sent-examples)

**Example #1 Examples using **headers\_sent()****

`<?php
// If no headers are sent, send one
if (!headers_sent()) {
    header('Location: http://www.example.com/');
    exit;
}
// An example using the optional file and line parameters
// Note that $filename and $linenum are passed in for later use.
// Do not assign them values beforehand.
if (!headers_sent($filename, $linenum)) {
    header('Location: http://www.example.com/');
    exit;
// You would most likely trigger an error here.
} else {
    echo "Headers already sent in $filename on line $linenum\n" .
          "Cannot redirect, for now please click this <a " .
          "href=\"http://www.example.com\">link</a> instead\n";
    exit;
}
?>`

### Notes [¶](https://www.php.net/manual/en/function.headers-sent.php\#refsect1-function.headers-sent-notes)

> **Note**:
>
>
> Headers will only be accessible and output when a SAPI that supports them
> is in use.

### See Also [¶](https://www.php.net/manual/en/function.headers-sent.php\#refsect1-function.headers-sent-seealso)

- [ob\_start()](https://www.php.net/manual/en/function.ob-start.php) \- Turn on output buffering
- [trigger\_error()](https://www.php.net/manual/en/function.trigger-error.php) \- Generates a user-level error/warning/notice message
- [headers\_list()](https://www.php.net/manual/en/function.headers-list.php) \- Returns a list of response headers sent (or ready to send)
- [header()](https://www.php.net/manual/en/function.header.php) \- Send a raw HTTP header for a more detailed discussion of the
matters involved.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/network/functions/headers-sent.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.headers-sent%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.headers-sent&repo=en&redirect=https://www.php.net/manual/en/function.headers-sent.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=86488&page=function.headers-sent&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86488&page=function.headers-sent&vote=down "Vote down!")

14


[**_yesmarklapointe at hotmail dot com_**](https://www.php.net/manual/en/function.headers-sent.php#86488) [¶](https://www.php.net/manual/en/function.headers-sent.php#86488)

**16 years ago**

`I was having trouble getting my mind around the concepts involved. Here is my dilemma and the conclusion I reached in case recounting them can help others:
I am using WAMPserver: PHP 5.2.6, and Apache 2.2.8 on Windows XP SP3. If it matters to your duplication,
I found two php.ini files in WAMPserver where output_buffering had been set to 4096. I changed them to OFF for this testing.
Here is how you can replicate what I am experiencing: With IE 7.0 go to Tools ... Display ieHTTPheaders ... and run the following script repeatedly and watch what happens:
<?php
header( 'Expires: Mon, 26 Jul 1998 05:00:00 GMT' );
//var_dump(headers_sent());
//print("whatever");
//flush();
//echo "whatever";
var_dump(headers_sent());
?>
Result: the final var_dump of the headers_sent() function will
always return FALSE unless any one or  more of the commented lines above it are uncommented. Uncommenting the statements allows an output to be sent to the user not just to their browser, after which the final var_dump will return TRUE. What I found confusing was that the ieHTTPheaders tool shows that the header is being sent to the user's browser even when all the output lines are commented out. So why does headers_sent() return FALSE in this case? Because you can keep sending other headers. The headers_sent function is meant to alert one to when no further headers can be sent. My testing shows it does not return true unless some other output is also sent after the header, thereby signaling that  "Headers have been sent and concluded with user output. NOW you can't send any more headers."
Someone else worked his way through this problem in a (false) bug report: [http://bugs.php.net/bug.php?id=30264](http://bugs.php.net/bug.php?id=30264)
Here is the relevant part of the reply from the pro:
"When you use compression the entire page is buffered in memory, until end of the request. Consequently you can send headers at any time because no data is being actually sent to user when you print it. Until PHP actually decides to send any page output to the user you can still send additional headers which is why the headers_sent() function is returning false. It will return true, indicating that headers have been sent  only at a time when output began going to the user and you no longer can send any additional headers."
So in summary, my point is that there is a difference between headers being sent only to the browser (which can be followed by other headers) vs. headers being sent and concluded by output for the user. The function should have been given a more clear name like headers_concluded().`

[up](https://www.php.net/manual/vote-note.php?id=60450&page=function.headers-sent&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60450&page=function.headers-sent&vote=down "Vote down!")

24


[**_Jakob B._**](https://www.php.net/manual/en/function.headers-sent.php#60450) [¶](https://www.php.net/manual/en/function.headers-sent.php#60450)

**19 years ago**

`<?php
function redirect($filename) {
    if (!headers_sent())
        header('Location: '.$filename);
    else {
        echo '<script type="text/javascript">';
        echo 'window.location.href="'.$filename.'";';
        echo '</script>';
        echo '<noscript>';
        echo '<meta http-equiv="refresh" content="0;url='.$filename.'" />';
        echo '</noscript>';
    }
}
redirect(' [http://www.google.com](http://www.google.com/)');
?>`

[up](https://www.php.net/manual/vote-note.php?id=40318&page=function.headers-sent&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=40318&page=function.headers-sent&vote=down "Vote down!")

2


[**_php at fufachew dot REMOVEME dot com_**](https://www.php.net/manual/en/function.headers-sent.php#40318) [¶](https://www.php.net/manual/en/function.headers-sent.php#40318)

**21 years ago**

`RE: antti at haapakangas dot net's post
I've changed the code so $_SERVER['SERVER_NAME'] is used if $_SERVER['HTTP_HOST'] is not set.  $_SERVER['SERVER_NAME'] doesn't meet my needs, but I suppose it's good to fall back on it.  I've also fixed a problem in the meta refresh line - it was missing the "url=" part of the content attribute.
<?php
function server_url()
{
    $proto = "http" .
        ((isset($_SERVER['HTTPS']) && $_SERVER['HTTPS'] == "on") ? "s" : "") . "://";
    $server = isset($_SERVER['HTTP_HOST']) ?
        $_SERVER['HTTP_HOST'] : $_SERVER['SERVER_NAME'];
    return $proto . $server;
}

function redirect_rel($relative_url)
{
    $url = server_url() . dirname($_SERVER['PHP_SELF']) . "/" . $relative_url;
    if (!headers_sent())
    {
        header("Location: $url");
    }
    else
    {
        echo "<meta http-equiv=\"refresh\" content=\"0;url=$url\">\r\n";
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=59242&page=function.headers-sent&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=59242&page=function.headers-sent&vote=down "Vote down!")

2


[**_trevize (shtrudel) gmail.com_**](https://www.php.net/manual/en/function.headers-sent.php#59242) [¶](https://www.php.net/manual/en/function.headers-sent.php#59242)

**19 years ago**

`Note that in IIS (or at least the version that comes with W2K server), the server seems to do some buffering, so even if you output someting or cause a warning, the value of headers_sent() may be false because the headers haven't been sent yet.
So it's not a safe way to know if warnings have been encountered in your script.`

[up](https://www.php.net/manual/vote-note.php?id=75835&page=function.headers-sent&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75835&page=function.headers-sent&vote=down "Vote down!")

1


[**_collectours at free dot fr_**](https://www.php.net/manual/en/function.headers-sent.php#75835) [¶](https://www.php.net/manual/en/function.headers-sent.php#75835)

**18 years ago**

`In response to K.Tomono and alexrussell101 at gmail dot com :
Yes,
headers_sent() will return false, even if you sent something to the ouptut using print() or header() , if output_buffering is different from Off in you php.ini, and the length of what you sent does not exceed the size of output_buffering.
To test it, try this code with  these values in php.ini
1) output_buffering=32
2) output buffering = 4096
[code]
<?php
    echo "Yo<br />";
    echo "Sent:",headers_sent(),"<br />";
    echo "enough text to feed the buffer until it overflows ;-)<br />";
    echo "Sent:",headers_sent(),"<br />";
?>
[/code]
then put
3) output buffering = Off
and try this code
[code]
<?php
    echo "Yo<br />";
    echo "Sent:",headers_sent(),"<br />";
?>
[/code]
which will this time unconditionnally say that headers were sent.
This is noticed in php.ini comment :
"Output buffering allows you to send header lines (including cookies) even after you send body content, in the price of slowing PHP's output layer a bit."
Note : This is completly independant of implicit_flush tuning.`

[up](https://www.php.net/manual/vote-note.php?id=122797&page=function.headers-sent&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122797&page=function.headers-sent&vote=down "Vote down!")

0


[**_rojasredes at gmail dot com_**](https://www.php.net/manual/en/function.headers-sent.php#122797) [¶](https://www.php.net/manual/en/function.headers-sent.php#122797)

**7 years ago**

`Remember to save source code file *.php with UTF-8 without BOM.
If saved with UTF-8 BOM the next code allways return "true":
<?php
if headers_sent($source,$numline)
{
    die("true");
}
else
{
    die("false");
}
?>
Even when $numline is 1, and there is any character before <?php
and after ?>
Save file without BOM and everything will be ok, then.`

[up](https://www.php.net/manual/vote-note.php?id=90160&page=function.headers-sent&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90160&page=function.headers-sent&vote=down "Vote down!")

0


[**_Jase_**](https://www.php.net/manual/en/function.headers-sent.php#90160) [¶](https://www.php.net/manual/en/function.headers-sent.php#90160)

**16 years ago**

`This is becoming annoying the amount of posts to try and describe the behaviour of headers
Headers appear first in the data sent to the user's browser
if headers have been called using the header() function but no data has been sent to the output buffer (using echo, readfile etc), then the headers are sent at the end of script execution otherwise they are sent when the buffer reaches it's limit and emptied
simple
this means that headers_sent() will return false if nothing is sent to the output buffer because the headers are being sent at the end of the script
This is not a bug either, this is expected behaviour. Keeping headers until forced to send them out is a good idea because certain measures can be taken like prevention of meta injection etc (option in header() to replace headers that have not yet been sent)
besides, headers_sent() is good for when you try and send headers but the output buffer has already been emptied (in cases of php error handling for example). Obviously if the buffer has emtpied, sending headers won't work.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.headers-sent&repo=en&redirect=https://www.php.net/manual/en/function.headers-sent.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google