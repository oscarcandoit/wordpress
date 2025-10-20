---
url: https://www.php.net/manual/en/function.inet-pton.php
scraped_at: 2025-10-20T03:01:47.884Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# inet\_pton

(PHP 5 >= 5.1.0, PHP 7, PHP 8)

inet\_pton — Converts a human readable IP address to its packed in\_addr representation

### Description [¶](https://www.php.net/manual/en/function.inet-pton.php\#refsect1-function.inet-pton-description)

**inet\_pton**([string](https://www.php.net/manual/en/language.types.string.php) `$ip`): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

This function converts a human readable IPv4 or IPv6 address (if PHP
was built with IPv6 support enabled) into an address family appropriate
32bit or 128bit binary structure.


### Parameters [¶](https://www.php.net/manual/en/function.inet-pton.php\#refsect1-function.inet-pton-parameters)

`ip`

A human readable IPv4 or IPv6 address.


### Return Values [¶](https://www.php.net/manual/en/function.inet-pton.php\#refsect1-function.inet-pton-returnvalues)

Returns the `in_addr` representation of the given
`ip`, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if a syntactically invalid
`ip` is given (for example, an IPv4 address
without dots or an IPv6 address without colons).


### Examples [¶](https://www.php.net/manual/en/function.inet-pton.php\#refsect1-function.inet-pton-examples)

**Example #1 **inet\_pton()** Example**

`<?php
$in_addr = inet_pton('127.0.0.1');

$in6_addr = inet_pton('::1');
?>`

### See Also [¶](https://www.php.net/manual/en/function.inet-pton.php\#refsect1-function.inet-pton-seealso)

- [ip2long()](https://www.php.net/manual/en/function.ip2long.php) \- Converts a string containing an (IPv4) Internet Protocol dotted address into a long integer
- [long2ip()](https://www.php.net/manual/en/function.long2ip.php) \- Converts a long integer address into a string in (IPv4) Internet standard dotted format
- [inet\_ntop()](https://www.php.net/manual/en/function.inet-ntop.php) \- Converts a packed internet address to a human readable representation

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/network/functions/inet-pton.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.inet-pton%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.inet-pton&repo=en&redirect=https://www.php.net/manual/en/function.inet-pton.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=115139&page=function.inet-pton&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115139&page=function.inet-pton&vote=down "Vote down!")

17


[**_TuRn3r_**](https://www.php.net/manual/en/function.inet-pton.php#115139) [¶](https://www.php.net/manual/en/function.inet-pton.php#115139)

**11 years ago**

`Be careful, address with leading 0 return false.
Example :
<?php
inet_pton('172.27.1.04'); // return false
inet_pton('172.27.1.4') ;// return the good result
?>`

[up](https://www.php.net/manual/vote-note.php?id=104917&page=function.inet-pton&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104917&page=function.inet-pton&vote=down "Vote down!")

12


[**_francis dot besset at gmail dot com_**](https://www.php.net/manual/en/function.inet-pton.php#104917) [¶](https://www.php.net/manual/en/function.inet-pton.php#104917)

**14 years ago**

`It is possible to verify if PHP was compiled with --disable-ipv6 option by AF_INET6 constant.
<?php
if (defined('AF_INET6')) {
echo "PHP was compiled without --disable-ipv6 option";
} else {
echo "PHP was compiled with --disable-ipv6 option";
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=66191&page=function.inet-pton&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=66191&page=function.inet-pton&vote=down "Vote down!")

10


[**_me at diogoresende dot net_**](https://www.php.net/manual/en/function.inet-pton.php#66191) [¶](https://www.php.net/manual/en/function.inet-pton.php#66191)

**19 years ago**

`If you want to use the above function you should test for ':' character before '.'. Meaning, you should check if it's an ipv6 address before checking for ipv4.
Why? IPv6 allows this type of notation:
::127.0.0.1
If you check for '.' character you will think this is an ipv4 address and it will fail.`

[up](https://www.php.net/manual/vote-note.php?id=125711&page=function.inet-pton&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125711&page=function.inet-pton&vote=down "Vote down!")

5


[**_admin at hanzlsoft dot eu_**](https://www.php.net/manual/en/function.inet-pton.php#125711) [¶](https://www.php.net/manual/en/function.inet-pton.php#125711)

**4 years ago**

`Regarding the ::127.0.0.1 notation
It is a very special case that needs not to be handled. This kind of notation is reserved for ipv4-compatible ipv6 address.
For example the notation ::ffff:192.0.2.128 can be easily read as "ipv6 address that maps to ipv4 address 192.0.2.128"
However as RFC says:
[https://tools.ietf.org/html/rfc5156#page-2](https://tools.ietf.org/html/rfc5156#page-2)
2.2.  IPv4-Mapped Addresses
::FFFF:0:0/96 are the IPv4-mapped addresses [RFC4291].  Addresses
within this block should not appear on the public Internet.
2.3.  IPv4-Compatible Addresses
::<ipv4-address>/96 are the IPv4-compatible addresses [RFC4291].
These addresses are deprecated and should not appear on the public
Internet.
This means that you only need to handle this kind of notation if you need to be compatible with private IP's`

[up](https://www.php.net/manual/vote-note.php?id=93501&page=function.inet-pton&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93501&page=function.inet-pton&vote=down "Vote down!")

10


[**_strata\_ranger at hotmail dot com_**](https://www.php.net/manual/en/function.inet-pton.php#93501) [¶](https://www.php.net/manual/en/function.inet-pton.php#93501)

**16 years ago**

`If the input string is not a readable IP address, inet_pton() generates an E_WARNING and returns FALSE.  The same is true for inet_ntop().
Also, inet_pton() does not recognize netmask notation (e.g: "1.2.3.4/24" or "1:2::3:4/64") in the input string.  This differs from how some database systems (like postgreSQL) support IP address types, so if you need that sort of functionality when processing IP addresses in PHP you'll have to write it in yourself.
A rough example:
<?php
// Sample IP addresses
$ipaddr = '1.2.3.4/24'; // IPv4 with /24 netmask
$ipaddr = '1:2::3:4/64'; // IPv6 with /64 netmask
// Strip out the netmask, if there is one.
$cx = strpos($ipaddr, '/');
if ($cx)
{
$subnet = (int)(substr($ipaddr, $cx+1));
$ipaddr = substr($ipaddr, 0, $cx);
}
else $subnet = null; // No netmask present
// Convert address to packed format
$addr = inet_pton($ipaddr);
// Let's display it as hexadecimal format
foreach(str_split($addr) as $char) echo str_pad(dechex(ord($char)), 2, '0', STR_PAD_LEFT);
echo "<br />\n";
// Convert the netmask
if (is_integer($subnet))
{
// Maximum netmask length = same as packed address
$len = 8*strlen($addr);
if ($subnet > $len) $subnet = $len;

// Create a hex expression of the subnet mask
$mask  = str_repeat('f', $subnet>>2);
switch($subnet & 3)
{
case 3: $mask .= 'e'; break;
case 2: $mask .= 'c'; break;
case 1: $mask .= '8'; break;
}
$mask = str_pad($mask, $len>>2, '0');
// Packed representation of netmask
$mask = pack('H*', $mask);
}
// Display the netmask as hexadecimal
foreach(str_split($mask) as $char) echo str_pad(dechex(ord($char)), 2, '0', STR_PAD_LEFT);
?>`

[up](https://www.php.net/manual/vote-note.php?id=116829&page=function.inet-pton&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116829&page=function.inet-pton&vote=down "Vote down!")

2


[**_dave at php dot net_**](https://www.php.net/manual/en/function.inet-pton.php#116829) [¶](https://www.php.net/manual/en/function.inet-pton.php#116829)

**10 years ago**

`If you are receiving an "Unrecognized address" error for an IPv6 address, it's possible your version of PHP has not been compiled with IPv6 support.
To check, load up phpinfo(); and look to see if "IPv6 Support" is set to "disabled".`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.inet-pton&repo=en&redirect=https://www.php.net/manual/en/function.inet-pton.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google