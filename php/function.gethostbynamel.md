---
url: https://www.php.net/manual/en/function.gethostbynamel.php
scraped_at: 2025-10-20T02:58:20.843Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# gethostbynamel

(PHP 4, PHP 5, PHP 7, PHP 8)

gethostbynamel —
Get a list of IPv4 addresses corresponding to a given Internet host
name


### Description [¶](https://www.php.net/manual/en/function.gethostbynamel.php\#refsect1-function.gethostbynamel-description)

**gethostbynamel**([string](https://www.php.net/manual/en/language.types.string.php) `$hostname`): [array](https://www.php.net/manual/en/language.types.array.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Returns a list of IPv4 addresses to which the Internet host
specified by `hostname` resolves.


### Parameters [¶](https://www.php.net/manual/en/function.gethostbynamel.php\#refsect1-function.gethostbynamel-parameters)

`hostname`

The host name.


### Return Values [¶](https://www.php.net/manual/en/function.gethostbynamel.php\#refsect1-function.gethostbynamel-returnvalues)

Returns an array of IPv4 addresses or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if
`hostname` could not be resolved.


### Examples [¶](https://www.php.net/manual/en/function.gethostbynamel.php\#refsect1-function.gethostbynamel-examples)

**Example #1 **gethostbynamel()** example**

`<?php
$hosts = gethostbynamel('www.example.com');
print_r($hosts);
?>`

The above example will output:

```
Array
(
    [0] => 192.0.34.166
)
```

### See Also [¶](https://www.php.net/manual/en/function.gethostbynamel.php\#refsect1-function.gethostbynamel-seealso)

- [gethostbyname()](https://www.php.net/manual/en/function.gethostbyname.php) \- Get the IPv4 address corresponding to a given Internet host name
- [gethostbyaddr()](https://www.php.net/manual/en/function.gethostbyaddr.php) \- Get the Internet host name corresponding to a given IP address
- [checkdnsrr()](https://www.php.net/manual/en/function.checkdnsrr.php) \- Check DNS records corresponding to a given Internet host name or IP address
- [getmxrr()](https://www.php.net/manual/en/function.getmxrr.php) \- Get MX records corresponding to a given Internet host name
- the `named(8)` manual page

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/network/functions/gethostbynamel.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.gethostbynamel%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.gethostbynamel&repo=en&redirect=https://www.php.net/manual/en/function.gethostbynamel.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=119535&page=function.gethostbynamel&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119535&page=function.gethostbynamel&vote=down "Vote down!")

10


[**_ab at null dot ixo dot ca_**](https://www.php.net/manual/en/function.gethostbynamel.php#119535) [¶](https://www.php.net/manual/en/function.gethostbynamel.php#119535)

**9 years ago**

`If using gethostbyname against the name of the localhost is always giving you 127.0.0.1 but you want the DNS address instead, just put a dot at the end of the name.  E.g.,
$foo = gethostbynamel("myhost.example.com");
print_r($foo);
...is giving you this:
Array
(
    [0] => 127.0.0.1
)
Then put a dot at the end of the name:
$foo = gethostbynamel("myhost.example.com.");
print_r($foo);
...and now you get something like:
Array
(
    [0] => 172.217.1.99
)`

[up](https://www.php.net/manual/vote-note.php?id=70018&page=function.gethostbynamel&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70018&page=function.gethostbynamel&vote=down "Vote down!")

 -3


[**_info at methfessel-computers.de_**](https://www.php.net/manual/en/function.gethostbynamel.php#70018) [¶](https://www.php.net/manual/en/function.gethostbynamel.php#70018)

**19 years ago**

`The solution is simpel. Just add a . (point) to the end of the URL for correct name resolving.
Without this point PHP thinks it's a subdomain of your local domain and so returns the "local-IP".`

[up](https://www.php.net/manual/vote-note.php?id=45974&page=function.gethostbynamel&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=45974&page=function.gethostbynamel&vote=down "Vote down!")

 -4


[**_Skyld at o2 dot co dot uk_**](https://www.php.net/manual/en/function.gethostbynamel.php#45974) [¶](https://www.php.net/manual/en/function.gethostbynamel.php#45974)

**21 years ago**

`Obviously, in some cases, not all IPs are likely to be useful while checking a hostname. Sometimes also, not all IPs will work. This code will check for the first WORKING IP from the list. Or at least it should - I haven't had time to test it yet.
Needs domain parameter, and port and max IPs to check are optional.
If port is not set, it will check HTTP port 80, and if max IPs to check is not set, it will only check the first 10 IPs from the list.
Hope it helps someone.
<?php
function checkhostlist($domain, $port = 80, $maxipstocheck = 10) {
? $hosts = gethostbynamel($domain);
    for ($chk=0;$chk<$maxipstocheck;$chk++) {
      if (isset($hosts[$chk])) {
        $th = fsockopen($domain, $port);
        if ($th) {
          fclose($th);
          return $hosts[$chk];
          break;
        }
      }
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=56924&page=function.gethostbynamel&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56924&page=function.gethostbynamel&vote=down "Vote down!")

 -4


[**_webdev at concraption dot com_**](https://www.php.net/manual/en/function.gethostbynamel.php#56924) [¶](https://www.php.net/manual/en/function.gethostbynamel.php#56924)

**20 years ago**

`In PHP 5.0.4, gethostbynamel returns an empty string instead of false if the lookup fails. A simple workaround for this error is to use is_array() in an IF block:
<?
$hosts = gethostbynamel($hostname);
if (is_array($hosts)) {
     echo "Host ".$hostname." resolves to:<br><br>";
     foreach ($hosts as $ip) {
          echo "IP: ".$ip."<br>";
     }
} else {
     echo "Host ".$hostname." is not tied to any IP.";
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.gethostbynamel&repo=en&redirect=https://www.php.net/manual/en/function.gethostbynamel.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google