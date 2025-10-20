---
url: https://www.php.net/manual/en/function.snmpwalkoid.php
scraped_at: 2025-10-20T02:48:49.448Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# snmpwalkoid

(PHP 4, PHP 5, PHP 7, PHP 8)

snmpwalkoid — Query for a tree of information about a network entity


### Description [¶](https://www.php.net/manual/en/function.snmpwalkoid.php\#refsect1-function.snmpwalkoid-description)

**snmpwalkoid**(

[string](https://www.php.net/manual/en/language.types.string.php) `$hostname`,

[string](https://www.php.net/manual/en/language.types.string.php) `$community`,

[array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php) `$object_id`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$timeout` = -1,

[int](https://www.php.net/manual/en/language.types.integer.php) `$retries` = -1

): [array](https://www.php.net/manual/en/language.types.array.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

**snmpwalkoid()** function is used to read all object ids
and their respective values from an SNMP agent specified by
`hostname`.


The existence of **snmpwalkoid()** and
[snmpwalk()](https://www.php.net/manual/en/function.snmpwalk.php) has historical reasons. Both
functions are provided for backward compatibility.
Use [snmprealwalk()](https://www.php.net/manual/en/function.snmprealwalk.php) instead.


### Parameters [¶](https://www.php.net/manual/en/function.snmpwalkoid.php\#refsect1-function.snmpwalkoid-parameters)

`hostname`

The SNMP agent.


`community`

The read community.


`object_id`

If **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, `object_id` is taken as the root of
the SNMP objects tree and all objects under that tree are returned as
an array.


If `object_id` is specified, all the SNMP objects
below that `object_id` are returned.


`timeout`

The number of microseconds until the first timeout.


`retries`

The number of times to retry if timeouts occur.


### Return Values [¶](https://www.php.net/manual/en/function.snmpwalkoid.php\#refsect1-function.snmpwalkoid-returnvalues)

Returns an associative array with object ids and their respective
object value starting from the `object_id`
as root or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on error.


### Examples [¶](https://www.php.net/manual/en/function.snmpwalkoid.php\#refsect1-function.snmpwalkoid-examples)

**Example #1 **snmpwalkoid()** Example**

`<?php
$a = snmpwalkoid("127.0.0.1", "public", "");
for (reset($a); $i = key($a); next($a)) {
    echo "$i: $a[$i]<br />\n";
}
?>`

Above function call would return all the SNMP objects from the
SNMP agent running on localhost. One can step through the values
with a loop


### See Also [¶](https://www.php.net/manual/en/function.snmpwalkoid.php\#refsect1-function.snmpwalkoid-seealso)

- [snmpwalk()](https://www.php.net/manual/en/function.snmpwalk.php) \- Fetch all the SNMP objects from an agent

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/snmp/functions/snmpwalkoid.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.snmpwalkoid%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.snmpwalkoid&repo=en&redirect=https://www.php.net/manual/en/function.snmpwalkoid.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=116209&page=function.snmpwalkoid&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116209&page=function.snmpwalkoid&vote=down "Vote down!")

0


[**_Anonymous_**](https://www.php.net/manual/en/function.snmpwalkoid.php#116209) [¶](https://www.php.net/manual/en/function.snmpwalkoid.php#116209)

**10 years ago**

`make sure you install "snmp-mibs-downloader" in debian.
apt-get install snmp-mibs-downloader
you my also need to edit your /etc/apt/sources.list
deb [http://ftp.us.debian.org/debian/](http://ftp.us.debian.org/debian/) wheezy main contrib non-free
deb-src [http://ftp.us.debian.org/debian/](http://ftp.us.debian.org/debian/) wheezy main contrib non-free`

[up](https://www.php.net/manual/vote-note.php?id=53832&page=function.snmpwalkoid&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=53832&page=function.snmpwalkoid&vote=down "Vote down!")

0


[**_thammer at rtccom dot com_**](https://www.php.net/manual/en/function.snmpwalkoid.php#53832) [¶](https://www.php.net/manual/en/function.snmpwalkoid.php#53832)

**20 years ago**

`The above note mentions that the MAC addresses come back converted to integers or something funky like that. Not sure why that is happening but I fixed that with a wrapper function.
function PadMAC($mac) {
    $mac_arr = explode(':',$mac);
    foreach($mac_arr as $atom) {
        $atom = trim($atom);
        $newarr[] = sprintf("%02s",$atom);
    }
    $newmac = implode(':',$newarr);
    return $newmac;
}
Maybe that will help somebody with that issue. I know I personally use the heck out of these user contributed notes`

[up](https://www.php.net/manual/vote-note.php?id=46538&page=function.snmpwalkoid&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=46538&page=function.snmpwalkoid&vote=down "Vote down!")

0


[**_gene\_wood at example dot com_**](https://www.php.net/manual/en/function.snmpwalkoid.php#46538) [¶](https://www.php.net/manual/en/function.snmpwalkoid.php#46538)

**21 years ago**

`Looks like timeout is in MICRO seconds.
1,000,000 &micros = 1 s`

[up](https://www.php.net/manual/vote-note.php?id=10489&page=function.snmpwalkoid&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=10489&page=function.snmpwalkoid&vote=down "Vote down!")

0


[**_jasper at pointless dot net_**](https://www.php.net/manual/en/function.snmpwalkoid.php#10489) [¶](https://www.php.net/manual/en/function.snmpwalkoid.php#10489)

**24 years ago**

`N.B. it's possible for snmpwalkoid to lose data - the "rmon.matrix.matrixSDTable" table for example uses binary mac addresses as part of the index, these get converted to ascii, and by the time they get to php they can be non-unique - so some entrys in the table get lost...`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.snmpwalkoid&repo=en&redirect=https://www.php.net/manual/en/function.snmpwalkoid.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google