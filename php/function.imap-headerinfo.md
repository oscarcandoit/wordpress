---
url: https://www.php.net/manual/en/function.imap-headerinfo.php
scraped_at: 2025-10-20T02:59:10.802Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# imap\_headerinfo

(PHP 4, PHP 5, PHP 7, PHP 8)

imap\_headerinfo — Read the header of the message

### Description [¶](https://www.php.net/manual/en/function.imap-headerinfo.php\#refsect1-function.imap-headerinfo-description)

**imap\_headerinfo**(

[IMAP\\Connection](https://www.php.net/manual/en/class.imap-connection.php) `$imap`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$message_num`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$from_length` = 0,

[int](https://www.php.net/manual/en/language.types.integer.php) `$subject_length` = 0

): [stdClass](https://www.php.net/manual/en/class.stdclass.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Gets information about the given message number by reading its headers.


### Parameters [¶](https://www.php.net/manual/en/function.imap-headerinfo.php\#refsect1-function.imap-headerinfo-parameters)

`imap`

An [IMAP\\Connection](https://www.php.net/manual/en/class.imap-connection.php) instance.

`message_num`

The message number


`from_length`

Number of characters for the `fetchfrom` property.
Must be greater than or equal to zero.


`subject_length`

Number of characters for the `fetchsubject` property
Must be greater than or equal to zero.


`defaulthost`

### Return Values [¶](https://www.php.net/manual/en/function.imap-headerinfo.php\#refsect1-function.imap-headerinfo-returnvalues)

Returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on error or, if successful, the information in an object with following properties:


- toaddress - full to: line, up to 1024 characters

- to - an array of objects from the To: line, with the following
properties: `personal`, `adl`,
`mailbox`, and `host`
- fromaddress - full from: line, up to 1024 characters

- from - an array of objects from the From: line, with the following
properties: `personal`, `adl`,
`mailbox`, and `host`
- ccaddress - full cc: line, up to 1024 characters

- cc - an array of objects from the Cc: line, with the following
properties: `personal`, `adl`,
`mailbox`, and `host`
- bccaddress - full bcc: line, up to 1024 characters

- bcc - an array of objects from the Bcc: line, with the following
properties: `personal`, `adl`,
`mailbox`, and `host`
- reply\_toaddress - full Reply-To: line, up to 1024 characters

- reply\_to - an array of objects from the Reply-To: line, with the following
properties: `personal`, `adl`,
`mailbox`, and `host`
- senderaddress - full sender: line, up to 1024 characters

- sender - an array of objects from the Sender: line, with the following
properties: `personal`, `adl`,
`mailbox`, and `host`
- return\_pathaddress - full Return-Path: line, up to 1024 characters

- return\_path - an array of objects from the Return-Path: line, with the
following properties: `personal`,
`adl`, `mailbox`, and
`host`
- remail -

- date - The message date as found in its headers

- Date - Same as date

- subject - The message subject

- Subject - Same as subject

- in\_reply\_to -

- message\_id -

- newsgroups -

- followup\_to -

- references -

- Recent - `R` if recent and seen, `N`
if recent and not seen, ' ' if not recent.

- Unseen - `U` if not seen AND not recent, ' ' if seen
OR not seen and recent

- Flagged - `F` if flagged, ' ' if not flagged

- Answered - `A` if answered, ' ' if unanswered

- Deleted - `D` if deleted, ' ' if not deleted

- Draft - `X` if draft, ' ' if not draft

- Msgno - The message number

- MailDate -

- Size - The message size

- udate - mail message date in Unix time

- fetchfrom - from line formatted to fit `from_length`
characters

- fetchsubject - subject line formatted to fit
`subject_length` characters


### Changelog [¶](https://www.php.net/manual/en/function.imap-headerinfo.php\#refsect1-function.imap-headerinfo-changelog)

| Version | Description |
| --- | --- |
| 8.1.0 | The `imap` parameter expects an [IMAP\\Connection](https://www.php.net/manual/en/class.imap-connection.php)<br> instance now; previously, a valid `imap` [resource](https://www.php.net/manual/en/language.types.resource.php) was expected. |
| 8.0.0 | The unused `defaulthost` parameter has been removed. |

### See Also [¶](https://www.php.net/manual/en/function.imap-headerinfo.php\#refsect1-function.imap-headerinfo-seealso)

- [imap\_fetch\_overview()](https://www.php.net/manual/en/function.imap-fetch-overview.php) \- Read an overview of the information in the headers of the given message

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/imap/functions/imap-headerinfo.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.imap-headerinfo%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imap-headerinfo&repo=en&redirect=https://www.php.net/manual/en/function.imap-headerinfo.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=98809&page=function.imap-headerinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=98809&page=function.imap-headerinfo&vote=down "Vote down!")

25


[**_andyltm_**](https://www.php.net/manual/en/function.imap-headerinfo.php#98809) [¶](https://www.php.net/manual/en/function.imap-headerinfo.php#98809)

**15 years ago**

`When I was testing imap_headerinfo() with an e-mail that had multiple recipients (multiple e-mails in to to: and/or cc: field), I noticed that imap_headerinfo() was failing hard for me on PHP 5.2.10-2ubuntu6.4 with Suhosin-Patch 0.9.7 (cli).
Rather than providing me an array with each and every e-mail address listed in the to and/or cc fields, it was only providing me the first listed.  This was disappointing.
[to] => Array
        (
            [0] => stdClass Object
                (
                    [mailbox] => game
                    [host] => blunts.com
                )
        )
Luckily, there was a cool workaround to this problem:
imap_rfc822_parse_headers(imap_fetchheader( string ); which subsequentally worked like a nice little pet would:
[to] => Array
        (
            [0] => stdClass Object
                (
                    [mailbox] => game
                    [host] => blunts.com
                )
            [1] => stdClass Object
                (
                    [mailbox] => dutch
                    [host] => masters.com
                )
        )
TL;DR:
So in other words, instead of imap_headerinfo() use imap_rfc822_parse_headers(imap_fetchheader()).
Hope this helps anyone else that runs into this issue from now into the future.  This post was suggested by people in #PHP on FreeNode IRC.`

[up](https://www.php.net/manual/vote-note.php?id=95012&page=function.imap-headerinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95012&page=function.imap-headerinfo&vote=down "Vote down!")

9


[**_jahservant 13 at gmail dot com_**](https://www.php.net/manual/en/function.imap-headerinfo.php#95012) [¶](https://www.php.net/manual/en/function.imap-headerinfo.php#95012)

**15 years ago**

`I'm not entirely sure why this is, but if you loop through all of the messages in a mailbox, calling imap_header() each time, you can significantly increase performance by calling imap_headers() first.
Compare this:
<?php
     $imap = imap_open("{my.server.com:143}INBOX", "user", "pass");
     $n_msgs = imap_num_msg($imap);
     $s = microtime(true);
     for ($i=0; $i<$n_msgs; $i++) {
          $header = imap_header($imap, $i);
     }
     $e = microtime(true);
     echo ($e - $s);
     imap_close($imap);
?>
With this:
<?php
     $imap = imap_open("{my.server.com:143}INBOX", "user", "pass");
     $n_msgs = imap_num_msg($imap);
/****** adding this line: ******/
     imap_headers($imap)
/***************************/
     $s = microtime(true);
     for ($i=0; $i<$n_msgs; $i++) {
          $header = imap_header($imap, $i);
     }
     $e = microtime(true);
     echo ($e - $s);
     imap_close($imap);
?>
The performance difference, as I have tested on several boxes, connecting to several different servers, is that the second code snippet ALWAYS takes 1/2 the time, if not less.
Perhaps it is because imap_headers() retrieves all of the messages on one connection, whereas imap_header() has to make a new fetch request for each message??  I'm not sure WHY it is faster if imap_headers() is called first, but I do know that it is, so I thought I'd pass on the knowledge.  If anyone knows why this is, please let me know....`

[up](https://www.php.net/manual/vote-note.php?id=120797&page=function.imap-headerinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120797&page=function.imap-headerinfo&vote=down "Vote down!")

3


[**_php at our-software dot com_**](https://www.php.net/manual/en/function.imap-headerinfo.php#120797) [¶](https://www.php.net/manual/en/function.imap-headerinfo.php#120797)

**8 years ago**

`Please Note : imap_headerinfo only returns a subset of the headers, rather than the entire thing.
Among other things, this means it only shows the first recipient from the "to" section of the email, rather than all recipients.
If you're not seeing something you expected to, you'll be better off using
$hdr_raw = imap_fetchheader($mbox, $mailid);
$hdr = imap_rfc822_parse_headers($hdr_raw);
then you'll see the full set of headers, and be able to do more with it.`

[up](https://www.php.net/manual/vote-note.php?id=26741&page=function.imap-headerinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=26741&page=function.imap-headerinfo&vote=down "Vote down!")

5


[**_scott at fuzzygroup dot com_**](https://www.php.net/manual/en/function.imap-headerinfo.php#26741) [¶](https://www.php.net/manual/en/function.imap-headerinfo.php#26741)

**22 years ago**

`If you want to extract values from to, from, or other header elements, they are an object and you need to loop over them i.e.
$header = imap_header($mbox, $message_id);
$from = $header->from;
foreach ($from as $id => $object) {
    $fromname = $object->personal;
    $fromaddress = $object->mailbox . "@" . $object->host;
}
Would give you two variables for the friendly from and the smtp from address
Thanks to www.natrak.net for help with this`

[up](https://www.php.net/manual/vote-note.php?id=117985&page=function.imap-headerinfo&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117985&page=function.imap-headerinfo&vote=down "Vote down!")

1


[**_Murray_**](https://www.php.net/manual/en/function.imap-headerinfo.php#117985) [¶](https://www.php.net/manual/en/function.imap-headerinfo.php#117985)

**10 years ago**

`An email without a subject line will not generate the 'subject' property.
Before using the 'subject' property you should test for it.
if (property_exists($header, 'subject')) echo $header->subject;`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.imap-headerinfo&repo=en&redirect=https://www.php.net/manual/en/function.imap-headerinfo.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google