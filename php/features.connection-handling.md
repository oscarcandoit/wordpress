---
url: https://www.php.net/manual/en/features.connection-handling.php
scraped_at: 2025-10-20T02:41:46.162Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Connection handling [¶](https://www.php.net/manual/en/features.connection-handling.php\#features.connection-handling)

Internally in PHP a connection status is maintained. There are 4
possible states:


- 0 - NORMAL
- 1 - ABORTED
- 2 - TIMEOUT
- 3 - ABORTED and TIMEOUT

When a PHP script is running normally, the NORMAL state is active.
If the remote client disconnects, the ABORTED state flag is
turned on. A remote client disconnect is usually caused by
users hitting their STOP button. If the PHP-imposed time limit (see
[set\_time\_limit()](https://www.php.net/manual/en/function.set-time-limit.php)) is hit, the TIMEOUT state flag
is turned on.

You can decide whether or not you want a client disconnect to cause
your script to be aborted. Sometimes it is handy to always have your
scripts run to completion even if there is no remote browser receiving
the output. The default behaviour is however for your script to be
aborted when the remote client disconnects. This behaviour can be
set via the ignore\_user\_abort php.ini directive as well as through
the corresponding `php_value ignore_user_abort` Apache
httpd.conf directive or
with the [ignore\_user\_abort()](https://www.php.net/manual/en/function.ignore-user-abort.php) function. If you do
not tell PHP to ignore a user abort and the user aborts, your script
will terminate. The one exception is if you have registered a shutdown
function using [register\_shutdown\_function()](https://www.php.net/manual/en/function.register-shutdown-function.php). With a
shutdown function, when the remote user hits his STOP button, the
next time your script tries to output something PHP will detect that
the connection has been aborted and the shutdown function is called.
This shutdown function will also get called at the end of your script
terminating normally, so to do something different in case of a client
disconnect you can use the [connection\_aborted()](https://www.php.net/manual/en/function.connection-aborted.php)
function. This function will return **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if the connection was
aborted.

Your script can also be terminated by the built-in script timer.
The default timeout is 30 seconds. It can be changed using
the **max\_execution\_time** php.ini directive or the corresponding
`php_value max_execution_time` Apache httpd.conf
directive as well as with
the [set\_time\_limit()](https://www.php.net/manual/en/function.set-time-limit.php) function. When the timer
expires the script will be aborted and as with the above client
disconnect case, if a shutdown function has been registered it will
be called. Within this shutdown function you can check to see if
a timeout caused the shutdown function to be called by calling the
[connection\_status()](https://www.php.net/manual/en/function.connection-status.php) function. This function will
return 2 if a timeout caused the shutdown function to be called.


One thing to note is that both the ABORTED and the TIMEOUT states
can be active at the same time. This is possible if you tell
PHP to ignore user aborts. PHP will still note the fact that
a user may have broken the connection, but the script will keep
running. If it then hits the time limit it will be aborted and
your shutdown function, if any, will be called. At this point
you will find that [connection\_status()](https://www.php.net/manual/en/function.connection-status.php)
returns 3.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/features/connection-handling.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffeatures.connection-handling%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=features.connection-handling&repo=en&redirect=https://www.php.net/manual/en/features.connection-handling.php)

### User Contributed Notes 11 notes

[up](https://www.php.net/manual/vote-note.php?id=93441&page=features.connection-handling&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93441&page=features.connection-handling&vote=down "Vote down!")

65


[**_tom lgold2003 at gmail dot com_**](https://www.php.net/manual/en/features.connection-handling.php#93441) [¶](https://www.php.net/manual/en/features.connection-handling.php#93441)

**16 years ago**

`hey, thanks to arr1, and it is very useful for me, when I need to return to the user fast and then do something else.
When using the codes, it nearly drive me mad and I found another thing that may affect the codes:
Content-Encoding: gzip
This is because the zlib is on and the content will be compressed. But this will not output the buffer until all output is over.
So, it may need to send the header to prevent this problem.
now, the code becomes:
<?php
ob_end_clean();
header("Connection: close\r\n");
header("Content-Encoding: none\r\n");
ignore_user_abort(true); // optional
ob_start();
echo ('Text user will see');
$size = ob_get_length();
header("Content-Length: $size");
ob_end_flush();     // Strange behaviour, will not work
flush();            // Unless both are called !
ob_end_clean();
//do processing here
sleep(5);
echo('Text user will never see');
//do some processing
?>`

[up](https://www.php.net/manual/vote-note.php?id=71172&page=features.connection-handling&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=71172&page=features.connection-handling&vote=down "Vote down!")

55


[**_arr1 at hotmail dot co dot uk_**](https://www.php.net/manual/en/features.connection-handling.php#71172) [¶](https://www.php.net/manual/en/features.connection-handling.php#71172)

**18 years ago**

`Closing the users browser connection whilst keeping your php script running has been an issue since 4.1, when the behaviour of register_shutdown_function() was modified so that it would not automatically close the users connection.
sts at mail dot xubion dot hu
Posted the original solution:
<?php
header("Connection: close");
ob_start();
phpinfo();
$size=ob_get_length();
header("Content-Length: $size");
ob_end_flush();
flush();
sleep(13);
error_log("do something in the background");
?>
Which works fine until you substitute phpinfo() for
echo ('text I want user to see'); in which case the headers are never sent!
The solution is to explicitly turn off output buffering and clear the buffer prior to sending your header information.
example:
<?php
ob_end_clean();
header("Connection: close");
ignore_user_abort(); // optional
ob_start();
echo ('Text the user will see');
$size = ob_get_length();
header("Content-Length: $size");
ob_end_flush(); // Strange behaviour, will not work
flush();            // Unless both are called !
// Do processing here
sleep(30);
echo('Text user will never see');
?>

Just spent 3 hours trying to figure this one out, hope it helps someone :)
Tested in:
IE 7.5730.11
Mozilla Firefox 1.81`

[up](https://www.php.net/manual/vote-note.php?id=112843&page=features.connection-handling&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112843&page=features.connection-handling&vote=down "Vote down!")

38


[**_mheumann at comciencia dot cl_**](https://www.php.net/manual/en/features.connection-handling.php#112843) [¶](https://www.php.net/manual/en/features.connection-handling.php#112843)

**12 years ago**

`I had a lot of problems getting a redirect to work, after which my script was intended to keep working in the background. The redirect to another page of my site simply would only work once the original page had finished processing.
I finally found out what was wrong:
The session only gets closed by PHP at the very end of the script, and since access to the session data is locked to prevent more than one page writing to it simultaneously, the new page cannot load until the original processing has finished.
Solution:
Close the session manually when redirecting using session_write_close():
<?php
ignore_user_abort(true);
set_time_limit(0);
$strURL = "PUT YOUR REDIRCT HERE";
header("Location: $strURL", true);
header("Connection: close", true);
header("Content-Encoding: none\r\n");
header("Content-Length: 0", true);
flush();
ob_flush();
session_write_close();
// Continue processing...
sleep(100);
exit;
?>
But careful:
Make sure that your script doesn't write to the session after session_write_close(), i.e. in your background processing code.  That won't work.  Also avoid reading, remember, the next script may already have modified the data.
So try to read out the data you need prior to redirecting.`

[up](https://www.php.net/manual/vote-note.php?id=45779&page=features.connection-handling&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=45779&page=features.connection-handling&vote=down "Vote down!")

31


[**_Lee_**](https://www.php.net/manual/en/features.connection-handling.php#45779) [¶](https://www.php.net/manual/en/features.connection-handling.php#45779)

**21 years ago**

`The point mentioned in the last comment isn't always the case.
If a user's connection is lost half way through an order processing script is confirming a user's credit card/adding them to a DB, etc (due to their ISP going down, network trouble... whatever) and your script tries to send back output (such as, "pre-processing order" or any other type of confirmation), then your script will abort -- and this could cause problems for your process.
I have an order script that adds data to a InnoDB database (through MySQL) and only commits the transactions upon successful completion. Without ignore_user_abort(), I have had times when a user's connection dropped during the processing phase... and their card was charged, but they weren't added to my local DB.
So, it's always safe to ignore any aborts if you are processing sensitive transactions that should go ahead, whether your user is "watching" on the other end or not.`

[up](https://www.php.net/manual/vote-note.php?id=120770&page=features.connection-handling&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120770&page=features.connection-handling&vote=down "Vote down!")

23


[**_Marco_**](https://www.php.net/manual/en/features.connection-handling.php#120770) [¶](https://www.php.net/manual/en/features.connection-handling.php#120770)

**8 years ago**

`The CONNECTION_XXX constants that are not listed here for some reason are:
0 = CONNECTION_NORMAL
1 = CONNECTION_ABORTED
2 = CONNECTION_TIMEOUT
3 = CONNECTION_ABORTED & CONNECTION_TIMEOUT
Number 3 is effectively tested like this:
if (CONNECTION_ABORTED & CONNECTION_TIMEOUT)
    echo 'Connection both aborted and timed out';`

[up](https://www.php.net/manual/vote-note.php?id=95087&page=features.connection-handling&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95087&page=features.connection-handling&vote=down "Vote down!")

28


[**_a1n2ton at gmail dot com_**](https://www.php.net/manual/en/features.connection-handling.php#95087) [¶](https://www.php.net/manual/en/features.connection-handling.php#95087)

**15 years ago**

`PHP changes directory on connection abort so code like this will not do what you want:
<?php
function abort()
{
     if(connection_aborted())
           unlink('file.ini');
}
register_shutdown_function('abort');
?>
actually it will delete file in apaches's root dir so if you want to unlink file in your script's dir on abort or write to it you have to store directory
<?php
function abort()
{
     global $dsd;
     if(connection_aborted())
           unlink($dsd.'/file.ini');
}
register_shutdown_function('abort');
$dsd=getcwd();
?>`

[up](https://www.php.net/manual/vote-note.php?id=110184&page=features.connection-handling&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110184&page=features.connection-handling&vote=down "Vote down!")

27


[**_Ilya Penyaev_**](https://www.php.net/manual/en/features.connection-handling.php#110184) [¶](https://www.php.net/manual/en/features.connection-handling.php#110184)

**13 years ago**

`I was quite stuck when trying to make my script redirect the client to another URL and then continue processing. The reason was php-fpm. All possible buffer flushes did not work, unless I called fastcgi_finish_request();
For example:
<?php
    // redirecting...
    ignore_user_abort(true);
    header("Location: ".$redirectUrl, true);
    header("Connection: close", true);
    header("Content-Length: 0", true);
    ob_end_flush();
    flush();
    fastcgi_finish_request(); // important when using php-fpm!

    sleep (5); // User won't feel this sleep because he'll already be away

    // do some work after user has been redirected
?>`

[up](https://www.php.net/manual/vote-note.php?id=107027&page=features.connection-handling&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107027&page=features.connection-handling&vote=down "Vote down!")

22


[**_Anonymous_**](https://www.php.net/manual/en/features.connection-handling.php#107027) [¶](https://www.php.net/manual/en/features.connection-handling.php#107027)

**13 years ago**

`This simple function outputs a string and closes the connection. It considers compression using "ob_gzhandler"
It took me a little while to put this all together, mostly because setting the encoding to none, as some people noted here, didn't work.
<?php
function outputStringAndCloseConnection2($stringToOutput)
{
    set_time_limit(0);
    ignore_user_abort(true);
    // buffer all upcoming output - make sure we care about compression:
    if(!ob_start("ob_gzhandler"))
        ob_start();
    echo $stringToOutput;
    // get the size of the output
    $size = ob_get_length();
    // send headers to tell the browser to close the connection
    header("Content-Length: $size");
    header('Connection: close');
    // flush all output
    ob_end_flush();
    ob_flush();
    flush();
    // close current session
    if (session_id()) session_write_close();
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=79134&page=features.connection-handling&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=79134&page=features.connection-handling&vote=down "Vote down!")

22


[**_Anonymous_**](https://www.php.net/manual/en/features.connection-handling.php#79134) [¶](https://www.php.net/manual/en/features.connection-handling.php#79134)

**17 years ago**

`in regards of posting from:
arr1 at hotmail dot co dot uk
if you use/write sessions you need to do this before:
(otherwise it does not work)
session_write_close();
and if wanted:
ignore_user_abort(TRUE);
instead of ignore_user_abort();`

[up](https://www.php.net/manual/vote-note.php?id=34800&page=features.connection-handling&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=34800&page=features.connection-handling&vote=down "Vote down!")

19


[**_pulstar at mail dot com_**](https://www.php.net/manual/en/features.connection-handling.php#34800) [¶](https://www.php.net/manual/en/features.connection-handling.php#34800)

**22 years ago**

`These functions are very useful for example if you need to control when a visitor in your website place an order and you need to check if he/she didn't clicked the submit button twice or cancelled the submit just after have clicked the submit button.
If your visitor click the stop button just after have submitted it, your script may stop in the middle of the process of registering the products and do not finish the list, generating inconsistency in your database.
With the ignore_user_abort() function you can make your script finish everything fine and after you can check with register_shutdown_function() and connection_aborted() if the visitor cancelled the submission or lost his/her connection. If he/she did, you can set the order as not confirmed and when the visitor came back, you can present the old order again.
To prevent a double click of the submit button, you can disable it with javascript or in your script you can set a flag for that order, which will be recorded into the database. Before accept a new submission, the script will check if the same order was not placed before and reject it. This will work fine, as the script have finished the job before.
Note that if you use ob_start("callback_function") in the begin of your script, you can specify a callback function that will act like the shutdown function when our script ends and also will let you to work on the generated page before send it to the visitor.`

[up](https://www.php.net/manual/vote-note.php?id=82225&page=features.connection-handling&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82225&page=features.connection-handling&vote=down "Vote down!")

15


[**_Jean Charles MAMMANA_**](https://www.php.net/manual/en/features.connection-handling.php#82225) [¶](https://www.php.net/manual/en/features.connection-handling.php#82225)

**17 years ago**

`connection_status() return ABORTED state ONLY if the client disconnects gracefully (with STOP button). In this case the browser send the RST TCP packet that notify PHP the connection is closed.
But.... If the connection is stopped by networs troubles (wifi link down by exemple) the script doesn't know that the client is disconnected :(
I've tried to use fopen("php://output") with stream_select() on writting to detect write locks (due to full buffer) but php give me this error : "cannot represent a stream of type Output as a select()able descriptor"
So I don't know how to detect correctly network trouble connection...`

[＋add a note](https://www.php.net/manual/add-note.php?sect=features.connection-handling&repo=en&redirect=https://www.php.net/manual/en/features.connection-handling.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google