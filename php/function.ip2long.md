---
url: https://www.php.net/manual/en/function.ip2long.php
scraped_at: 2025-10-20T03:01:13.868Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ip2long

(PHP 4, PHP 5, PHP 7, PHP 8)

ip2long — Converts a string containing an (IPv4) Internet Protocol dotted address into a long integer

### Description [¶](https://www.php.net/manual/en/function.ip2long.php\#refsect1-function.ip2long-description)

**ip2long**([string](https://www.php.net/manual/en/language.types.string.php) `$ip`): [int](https://www.php.net/manual/en/language.types.integer.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

The function **ip2long()** generates a long integer
representation of IPv4 Internet network address from its Internet
standard format (dotted string) representation.


**ip2long()** will also work with non-complete IP
addresses. Read [» http://ps-2.kev009.com/wisclibrary/aix52/usr/share/man/info/en\_US/a\_doc\_lib/libs/commtrf2/inet\_addr.htm](http://ps-2.kev009.com/wisclibrary/aix52/usr/share/man/info/en_US/a_doc_lib/libs/commtrf2/inet_addr.htm)
for more info.


### Parameters [¶](https://www.php.net/manual/en/function.ip2long.php\#refsect1-function.ip2long-parameters)

`ip`

A standard format address.


### Return Values [¶](https://www.php.net/manual/en/function.ip2long.php\#refsect1-function.ip2long-returnvalues)

Returns the long integer or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if `ip`
is invalid.


### Examples [¶](https://www.php.net/manual/en/function.ip2long.php\#refsect1-function.ip2long-examples)

**Example #1 **ip2long()** Example**

`<?php
$ip = gethostbyname('www.example.com');
$out = "The following URLs are equivalent:<br />\n";
$out .= 'http://www.example.com/, http://' . $ip . '/, and http://' . sprintf("%u", ip2long($ip)) . "/<br />\n";
echo $out;
?>`

**Example #2 Displaying an IP address**

This second example shows how to print a converted address with the
[printf()](https://www.php.net/manual/en/function.printf.php) function:


`<?php
$ip   = gethostbyname('www.example.com');
$long = ip2long($ip);
if ($long == -1 || $long === FALSE) {
    echo 'Invalid IP, please try again';
} else {
    echo $ip   . "\n";            // 192.0.34.166
    echo $long . "\n";            // 3221234342 (-1073732954 on 32-bit systems, due to integer overflow)
    printf("%u\n", ip2long($ip)); // 3221234342
}
?>`

### Notes [¶](https://www.php.net/manual/en/function.ip2long.php\#refsect1-function.ip2long-notes)

> **Note**:
>
>
> Because PHP's [int](https://www.php.net/manual/en/language.types.integer.php) type is signed, and many IP addresses
> will result in negative integers on 32-bit architectures, you need to use
> the "%u" formatter of [sprintf()](https://www.php.net/manual/en/function.sprintf.php) or
> [printf()](https://www.php.net/manual/en/function.printf.php) to get the string representation of the
> unsigned IP address.

> **Note**:
>
>
> **ip2long()** will return `-1` for the IP
> `255.255.255.255` on 32-bit systems due to the integer value overflowing.

### See Also [¶](https://www.php.net/manual/en/function.ip2long.php\#refsect1-function.ip2long-seealso)

- [long2ip()](https://www.php.net/manual/en/function.long2ip.php) \- Converts a long integer address into a string in (IPv4) Internet standard dotted format
- [sprintf()](https://www.php.net/manual/en/function.sprintf.php) \- Return a formatted string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/network/functions/ip2long.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.ip2long%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ip2long&repo=en&redirect=https://www.php.net/manual/en/function.ip2long.php)

### User Contributed Notes 25 notes

[up](https://www.php.net/manual/vote-note.php?id=94787&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94787&page=function.ip2long&vote=down "Vote down!")

34


[**_joe at joeceresini dot com_**](https://www.php.net/manual/en/function.ip2long.php#94787) [¶](https://www.php.net/manual/en/function.ip2long.php#94787)

**15 years ago**

`A quick method to convert a netmask (ex: 255.255.255.240) to a cidr mask (ex: /28):
<?php
function mask2cidr($mask){
$long = ip2long($mask);
$base = ip2long('255.255.255.255');
return 32-log(($long ^ $base)+1,2);
/* xor-ing will give you the inverse mask,
      log base 2 of that +1 will return the number
      of bits that are off in the mask and subtracting
      from 32 gets you the cidr notation */

}
?>`

[up](https://www.php.net/manual/vote-note.php?id=121755&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121755&page=function.ip2long&vote=down "Vote down!")

18


[**_Mike B_**](https://www.php.net/manual/en/function.ip2long.php#121755) [¶](https://www.php.net/manual/en/function.ip2long.php#121755)

**8 years ago**

`<?php
/*
     Given an IP address and Subnet Mask,
     determine the subnet address, broadcast address, and wildcard mask
     by using bitwise operators
     ref:  [http://php.net/manual/en/language.operators.bitwise.php](http://php.net/manual/en/language.operators.bitwise.php)
*/
$ip='10.10.10.7';
$mask='255.255.255.0';
$wcmask=long2ip( ~ip2long($mask) );
$subnet=long2ip( ip2long($ip) & ip2long($mask) );
$bcast=long2ip( ip2long($ip) | ip2long($wcmask) );
echo "Given address $ip and mask $mask, \n" .
"the subnet is $subnet and broadcast is $bcast \n" .
"with a wildcard mask of $wcmask";
/*
Given address 10.10.10.7 and mask 255.255.255.0,
the subnet is 10.10.10.0 and broadcast is 10.10.10.255
with a wildcard mask of 0.0.0.255
*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=90344&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90344&page=function.ip2long&vote=down "Vote down!")

4


[**_spinyn at gmail dot com_**](https://www.php.net/manual/en/function.ip2long.php#90344) [¶](https://www.php.net/manual/en/function.ip2long.php#90344)

**16 years ago**

`Just want to add a comment to kaputt's valuable contribution to the task of matching hosts to ip ranges, efficiently.  The script works fine if the binary representation of the ip involves no leading zeros.  Unfortunately, the way decbin() seems to work, leading zeros in the binary representation of the first ip quad get dropped.  That is a serious matter if you're trying to match all possible candidates in the checklist.  In those cases the leading zeros need to be added back to get accurate matches for values in the first quad between 0-127 (or the binary equivalent, 0-01111111).
The solution I came up with to address this issue was the following function:
<?php
function addLeadingZero($ip) {
if (($result = (32 - strlen($ip))) > 0)
      return str_repeat("0", $result).$ip;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=74264&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74264&page=function.ip2long&vote=down "Vote down!")

4


[**_one tiger one at gee mail dot comm_**](https://www.php.net/manual/en/function.ip2long.php#74264) [¶](https://www.php.net/manual/en/function.ip2long.php#74264)

**18 years ago**

`I wrote a small function to validate a netmask (We have a form where the netmask of a given server is entered in, and I wanted to make sure it was valid). Hope this is useful.
<?php
// Netmask Validator //
function checkNetmask($ip) {
if (!ip2long($ip)) {
return false;
} elseif(strlen(decbin(ip2long($ip))) != 32 && ip2long($ip) != 0) {
return false;
} elseif(ereg('01',decbin(ip2long($ip))) || !ereg('0',decbin(ip2long($ip)))) {
return false;
} else {
return true;
}
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=78643&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78643&page=function.ip2long&vote=down "Vote down!")

6


[**_ir on ir id is at gm ai ld ot co m_**](https://www.php.net/manual/en/function.ip2long.php#78643) [¶](https://www.php.net/manual/en/function.ip2long.php#78643)

**17 years ago**

`Keep in mind that storing IP addresses inside of your database as integers (rather than 15 character strings in decimal format, or 8 character strings in hex format) is hundreds of times faster.
Take the typical case of a MySQL database doing a search for an IP address on thousands (or millions!) of rows; you're either doing a string compare for each entry, or an integer equation. If you do your indexes correctly, your lookups should be literally 100x faster using an INT rather than a VARCHAR.
Also note that an integer doesn't need to be escaped when passed to a database. :)`

[up](https://www.php.net/manual/vote-note.php?id=82219&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82219&page=function.ip2long&vote=down "Vote down!")

12


[**_php dot net at kenman dot net_**](https://www.php.net/manual/en/function.ip2long.php#82219) [¶](https://www.php.net/manual/en/function.ip2long.php#82219)

**17 years ago**

``To nate, who advises that there is no reason to use an unsigned version of the IP in a MySQL DB:
I think it would depend on your application, but personally, I find it useful to store IP's as unsigneds since MySQL has 2 native functions, INET_ATON() and INET_NTOA(), which work the same as ip2long()/long2ip() _except_ that they generate the unsigned counterpart. So if you want, you could do:
-- IANA Class-B reserved/private
SELECT * FROM `servers`
WHERE `ip` >= INET_ATON('192.168.0.0')
AND `ip` <= INET_ATON('192.168.255.255');
In my current application, I find it easier to use the MySQL built-ins than the PHP counter-parts.
In case you're curious as to the names ATON and NTOA:
ATON = address to number aka. ip2long
NTOA = number to address aka. long2ip``

[up](https://www.php.net/manual/vote-note.php?id=83320&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=83320&page=function.ip2long&vote=down "Vote down!")

3


[**_jpmarcotte at gmail dot com_**](https://www.php.net/manual/en/function.ip2long.php#83320) [¶](https://www.php.net/manual/en/function.ip2long.php#83320)

**17 years ago**

`In using a combination of jbothe's code below and some of the "$mask = 0xFFFFFFFF << (32 - $bits)" type code, I ran into an error with some later calculations on a 64 bit machine.
Keep in mind that when you're analyzing numbers meant to be treated as 32 bits wide (such as IP addresses), you may want to truncate them. Without relying on other libraries, it was simple enough to follow any calculations that may end with different results on a 64 bit machine with " & 0xFFFFFFFF"
Though in many cases, it seems like it might be simpler to just use "~0 << ..." for initial shifting to create the network mask instead of "0xFFFFFFFF << ...". I don't know that it guarantees further operations to work as expected though.`

[up](https://www.php.net/manual/vote-note.php?id=94290&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94290&page=function.ip2long&vote=down "Vote down!")

10


[**_david dot schueler at tel-billig dot de_**](https://www.php.net/manual/en/function.ip2long.php#94290) [¶](https://www.php.net/manual/en/function.ip2long.php#94290)

**15 years ago**

`To get the network adress out of the broadcast adress and netmask just to an AND on it:
<?php
// simple example
$bcast = ip2long("192.168.178.255");
$smask = ip2long("255.255.255.0");
$nmask = $bcast & $smask;
echo long2ip($nmask); // Will give 192.168.178.0
?>
With this example you are able to check if a given host is in your own local net or not (on linux):
<?php
/**
* Check if a client IP is in our Server subnet
*
* @param string $client_ip
* @param string $server_ip
* @return boolean
*/
function clientInSameSubnet($client_ip=false,$server_ip=false) {
    if (!$client_ip)
        $client_ip = $_SERVER['REMOTE_ADDR'];
    if (!$server_ip)
        $server_ip = $_SERVER['SERVER_ADDR'];
    // Extract broadcast and netmask from ifconfig
    if (!($p = popen("ifconfig","r"))) return false;
    $out = "";
    while(!feof($p))
        $out .= fread($p,1024);
    fclose($p);
    // This is because the php.net comment function does not
    // allow long lines.
    $match  = "/^.*".$server_ip;
    $match .= ".*Bcast:(\d{1,3}\.\d{1,3}i\.\d{1,3}\.\d{1,3}).*";
    $match .= "Mask:(\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3})$/im";
    if (!preg_match($match,$out,$regs))
        return false;
    $bcast = ip2long($regs[1]);
    $smask = ip2long($regs[2]);
    $ipadr = ip2long($client_ip);
    $nmask = $bcast & $smask;
    return (($ipadr & $smask) == ($nmask & $smask));
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=115761&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115761&page=function.ip2long&vote=down "Vote down!")

5


[**_Karl Rixon_**](https://www.php.net/manual/en/function.ip2long.php#115761) [¶](https://www.php.net/manual/en/function.ip2long.php#115761)

**11 years ago**

`The manual states that "ip2long() will also work with non-complete IP addresses", however this is system-dependant so cannot be relied upon. For example, on my system ip2long() will return FALSE for incomplete addresses:
<?php
var_dump(ip2long("255.255")); // bool(false)
?>
This is because ip2long will use inet_pton if available, which does not support non-complete addresses. If inet_pton is not available on your system, inet_addr will be used and incomplete addresses will work as stated.`

[up](https://www.php.net/manual/vote-note.php?id=123840&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123840&page=function.ip2long&vote=down "Vote down!")

2


[**_schat_**](https://www.php.net/manual/en/function.ip2long.php#123840) [¶](https://www.php.net/manual/en/function.ip2long.php#123840)

**6 years ago**

`sorry i just wrote wrong, sorry. this is the right one. thanks.
<?php
/**
* convert cidr to ip range
* From: < [https://github.com/www-schat-top>](https://github.com/www-schat-top%3E)
* @param  string $cidr "192.168.0.0/23"
* @return array  ["192.168.0.0", "192.168.1.255"]
*/
function cidr2range($cidr){
list( $subnet, $mask ) = explode( '/', $cidr );
return [$subnet, long2ip(ip2long( $subnet ) | (pow(2,( 32 - $mask ))-1))];
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=108567&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=108567&page=function.ip2long&vote=down "Vote down!")

3


[**_Aleksey Kuznetsov_**](https://www.php.net/manual/en/function.ip2long.php#108567) [¶](https://www.php.net/manual/en/function.ip2long.php#108567)

**13 years ago**

`Unfortunately sprintf('%u', ...) is low and returns string representation of integer value instead of integer.
Here is a function I use to convert IP to mySQL-compatible signed integer:
function ip2int($ip) {
if (!$r = ip2long($ip)) return 0; // we want 0 instead of false, even in case of bad IP
if ($r > 2147483647)
      $r-= 4294967296;
return $r; // ok
}`

[up](https://www.php.net/manual/vote-note.php?id=108812&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=108812&page=function.ip2long&vote=down "Vote down!")

4


[**_replay111 at tlen dot pl_**](https://www.php.net/manual/en/function.ip2long.php#108812) [¶](https://www.php.net/manual/en/function.ip2long.php#108812)

**13 years ago**

`Hi,
based on examples above I have mixed class IPFilter with netMatch function wich gives me complete class for IP4 check including CIDR IP format:
<?php
class IP4Filter {
    private static $_IP_TYPE_SINGLE = 'single';
    private static $_IP_TYPE_WILDCARD = 'wildcard';
    private static $_IP_TYPE_MASK = 'mask';
    private static $_IP_TYPE_CIDR = 'CIDR';
    private static $_IP_TYPE_SECTION = 'section';
    private $_allowed_ips = array();
    public function __construct($allowed_ips) {
        $this->_allowed_ips = $allowed_ips;
    }
    public function check($ip, $allowed_ips = null) {
        $allowed_ips = $allowed_ips ? $allowed_ips : $this->_allowed_ips;
        foreach ($allowed_ips as $allowed_ip) {
            $type = $this->_judge_ip_type($allowed_ip);
            $sub_rst = call_user_func(array($this, '_sub_checker_' . $type), $allowed_ip, $ip);
            if ($sub_rst) {
                return true;
            }
        }
        return false;
    }
    private function _judge_ip_type($ip) {
        if (strpos($ip, '*')) {
            return self :: $_IP_TYPE_WILDCARD;
        }
        if (strpos($ip, '/')) {
            $tmp = explode('/', $ip);
            if (strpos($tmp[1], '.')) {
                return self :: $_IP_TYPE_MASK;
            } else {
                return self :: $_IP_TYPE_CIDR;
            }
        }
        if (strpos($ip, '-')) {
            return self :: $_IP_TYPE_SECTION;
        }
        if (ip2long($ip)) {
            return self :: $_IP_TYPE_SINGLE;
        }
        return false;
    }
    private function _sub_checker_single($allowed_ip, $ip) {
        return (ip2long($allowed_ip) == ip2long($ip));
    }
    private function _sub_checker_wildcard($allowed_ip, $ip) {
        $allowed_ip_arr = explode('.', $allowed_ip);
        $ip_arr = explode('.', $ip);
        for ($i = 0; $i < count($allowed_ip_arr); $i++) {
            if ($allowed_ip_arr[$i] == '*') {
                return true;
            } else {
                if (false == ($allowed_ip_arr[$i] == $ip_arr[$i])) {
                    return false;
                }
            }
        }
    }
    private function _sub_checker_mask($allowed_ip, $ip) {
        list($allowed_ip_ip, $allowed_ip_mask) = explode('/', $allowed_ip);
        $begin = (ip2long($allowed_ip_ip) & ip2long($allowed_ip_mask)) + 1;
        $end = (ip2long($allowed_ip_ip) | (~ ip2long($allowed_ip_mask))) + 1;
        $ip = ip2long($ip);
        return ($ip >= $begin && $ip <= $end);
    }
    private function _sub_checker_section($allowed_ip, $ip) {
        list($begin, $end) = explode('-', $allowed_ip);
        $begin = ip2long($begin);
        $end = ip2long($end);
        $ip = ip2long($ip);
        return ($ip >= $begin && $ip <= $end);
    }
    private function _sub_checker_CIDR($CIDR, $IP) {
        list ($net, $mask) = explode('/', $CIDR);
        return ( ip2long($IP) & ~((1 << (32 - $mask)) - 1) ) == ip2long($net);
    }
}
?>
For me this code works great, so I wanna thank to all You guys!!!`

[up](https://www.php.net/manual/vote-note.php?id=113080&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113080&page=function.ip2long&vote=down "Vote down!")

3


[**_rasmus at mindplay dot dk_**](https://www.php.net/manual/en/function.ip2long.php#113080) [¶](https://www.php.net/manual/en/function.ip2long.php#113080)

**12 years ago**

`As pointed out by others, this function's return value is not consistent on 32 and 64-bit platforms.
Your best bet for consistent behavior across 32/64-bit platforms (and Windows) is the lowest common denominator: force the return value of ip2long() into a signed 32-bit integer, e.g.:
    var_dump(unpack('l', pack('l', ip2long('255.255.255.0'))));
This looks idiotic, but it gives you a consistent signed integer value on all platforms.
(the arguments to both pack() and unpack() are the lower-case letter "L", not the number "1", in case it looks that way on your screen...)`

[up](https://www.php.net/manual/vote-note.php?id=106749&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106749&page=function.ip2long&vote=down "Vote down!")

2


[**_PandoraBox2007 at gmail dot com_**](https://www.php.net/manual/en/function.ip2long.php#106749) [¶](https://www.php.net/manual/en/function.ip2long.php#106749)

**13 years ago**

``Universal ip4/ip6
<?php
// encoded --
function encode_ip ($ip)
{
    $d = explode('.', $ip);
    if (count($d) == 4) return sprintf('%02x%02x%02x%02x', $d[0], $d[1], $d[2], $d[3]);

    $d = explode(':', preg_replace('/(^:)|(:$)/', '', $ip));
    $res = '';
    foreach ($d as $x)
        $res .= sprintf('%0'. ($x == '' ? (9 - count($d)) * 4 : 4) .'s', $x);
    return $res;
}
// decoded
function decode_ip($int_ip)
{
    function hexhex($value) { return dechex(hexdec($value)); };

    if (strlen($int_ip) == 32) {
        $int_ip = substr(chunk_split($int_ip, 4, ':'), 0, 39);
        $int_ip = ':'. implode(':', array_map("hexhex", explode(':',$int_ip))) .':';
        preg_match_all("/(:0)+/", $int_ip, $zeros);
        if (count($zeros[0]) > 0) {
            $match = '';
            foreach($zeros[0] as $zero)
                if (strlen($zero) > strlen($match))
                    $match = $zero;
            $int_ip = preg_replace('/'. $match .'/', ':', $int_ip, 1);
        }
        return preg_replace('/(^:([^:]))|(([^:]):$)/', '$2$4', $int_ip);
    }
    $hexipbang = explode('.', chunk_split($int_ip, 2, '.'));
    return hexdec($hexipbang[0]). '.' . hexdec($hexipbang[1]) . '.' . hexdec($hexipbang[2]) . '.' . hexdec($hexipbang[3]);
}
?>
DB:
`user_ip` varchar(32) DEFAULT NULL``

[up](https://www.php.net/manual/vote-note.php?id=119883&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119883&page=function.ip2long&vote=down "Vote down!")

1


[**_alex at alex-at dot ru_**](https://www.php.net/manual/en/function.ip2long.php#119883) [¶](https://www.php.net/manual/en/function.ip2long.php#119883)

**9 years ago**

`Here are my versions of prefix to mask and mask to prefix conversions. You can remove first lines with if/preg of each function if you don't want sanity precheck.
    function prefix2Mask($prefix)
    {
        if (!preg_match('#^(?:0*[0-2]?[0-9]|3[0-2])$#', $prefix)) return false; # wrong prefix
        return long2ip(0xffffffff << (32 - $prefix));
    }

    function mask2Prefix($mask)
    {
        if (!preg_match('#^(?:(?:[0-1][0-9][0-9]|2[0-4][0-9]|25[0-5]|[0-9][0-9]|[0-9])\.){3}'.
            '(?:[0-1][0-9][0-9]|2[0-4][0-9]|25[0-5]|[0-9][0-9]|[0-9])$#', $mask))
            return false; # wrong mask
        $m2p = str_pad(substr(decbin(ip2long($mask)), -32, 32), 32, '0', STR_PAD_LEFT);
        if (!preg_match('#^(1*)0*$#', $m2p, $m)) return false; # wrong mask
        return strlen($m[1]);
    }`

[up](https://www.php.net/manual/vote-note.php?id=92544&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92544&page=function.ip2long&vote=down "Vote down!")

3


[**_jwadhams1 at yahoo dot com_**](https://www.php.net/manual/en/function.ip2long.php#92544) [¶](https://www.php.net/manual/en/function.ip2long.php#92544)

**16 years ago**

`I wanted to build on what kaputt and spinyn contributed in a way that I think is a little more intuitive (e.g., let sprintf do all the binary conversion and padding, and let substr_compare do the trimming and comparing):
<?php
function ip_in_network($ip, $net_addr, $net_mask){
    if($net_mask <= 0){ return false; }
        $ip_binary_string = sprintf("%032b",ip2long($ip));
        $net_binary_string = sprintf("%032b",ip2long($net_addr));
        return (substr_compare($ip_binary_string,$net_binary_string,0,$net_mask) === 0);
}
ip_in_network("192.168.2.1","192.168.2.0",24); //true
ip_in_network("192.168.6.93","192.168.0.0",16); //true
ip_in_network("1.6.6.6","128.168.2.0",1); //false
?>`

[up](https://www.php.net/manual/vote-note.php?id=94477&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94477&page=function.ip2long&vote=down "Vote down!")

3


[**_f dot wiessner at smart-weblications dot net_**](https://www.php.net/manual/en/function.ip2long.php#94477) [¶](https://www.php.net/manual/en/function.ip2long.php#94477)

**15 years ago**

`Here some working ip2long6 and long2ip6 functions - keep in mind that this needs php gmp-lib:
<?php
$ipv6 = "2001:4860:a005::68";
function ip2long6($ipv6) {
$ip_n = inet_pton($ipv6);
$bits = 15; // 16 x 8 bit = 128bit
while ($bits >= 0) {
    $bin = sprintf("%08b",(ord($ip_n[$bits])));
    $ipv6long = $bin.$ipv6long;
    $bits--;
}
return gmp_strval(gmp_init($ipv6long,2),10);
}
function long2ip6($ipv6long) {
$bin = gmp_strval(gmp_init($ipv6long,10),2);
if (strlen($bin) < 128) {
    $pad = 128 - strlen($bin);
    for ($i = 1; $i <= $pad; $i++) {
    $bin = "0".$bin;
    }
}
$bits = 0;
while ($bits <= 7) {
    $bin_part = substr($bin,($bits*16),16);
    $ipv6 .= dechex(bindec($bin_part)).":";
    $bits++;
}
// compress
return inet_ntop(inet_pton(substr($ipv6,0,-1)));
}
print $ipv6long =  ip2long6($ipv6)."\n";
print $ipv6 = long2ip6($ipv6long)."\n";
?>
outputs:
42541956150894553250710573749450571880
2001:4860:a005::68`

[up](https://www.php.net/manual/vote-note.php?id=71939&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=71939&page=function.ip2long&vote=down "Vote down!")

1


[**_Ian B_**](https://www.php.net/manual/en/function.ip2long.php#71939) [¶](https://www.php.net/manual/en/function.ip2long.php#71939)

**18 years ago**

`NOTE: ip2long() should NOT be used for CIDR calculation.
Instead, you should use something like the following:
<?php
        /* get the base and the bits from the ban in the database */
        list($base, $bits) = explode('/', $CIDR);
        /* now split it up into it's classes */
        list($a, $b, $c, $d) = explode('.', $base);
        /* now do some bit shfiting/switching to convert to ints */
        $i = ($a << 24) + ($b << 16) + ($c << 8) + $d;
        $mask = $bits == 0 ? 0 : (~0 << (32 - $bits));
        /* here's our lowest int */
        $low = $i & $mask;
        /* here's our highest int */
        $high = $i | (~$mask & 0xFFFFFFFF);
        /* now split the ip were checking against up into classes */
        list($a, $b, $c, $d) = explode('.', $iptocheck);
        /* now convert the ip we're checking against to an int */
        $check = ($a << 24) + ($b << 16) + ($c << 8) + $d;
        /* if the ip is within the range, including
      highest/lowest values, then it's witin the CIDR range */
        if ($check >= $low && $check <= $high)
            return 1;
       else
            return 0;
?>
This means that you should check to see if the IP
address is of the correct format each time.`

[up](https://www.php.net/manual/vote-note.php?id=108436&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=108436&page=function.ip2long&vote=down "Vote down!")

2


[**_pink at pink dot art dot pl_**](https://www.php.net/manual/en/function.ip2long.php#108436) [¶](https://www.php.net/manual/en/function.ip2long.php#108436)

**13 years ago**

`Be aware when you're running 64bit system, ip2long will result 64 bit integer which doesn't fit in MySQL INT, you can use BIGINT or INT UNSIGNED because on 64bit systems ip2long will never return negative integer. See also [https://bugs.php.net/bug.php?id=54338](https://bugs.php.net/bug.php?id=54338)`

[up](https://www.php.net/manual/vote-note.php?id=47814&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=47814&page=function.ip2long&vote=down "Vote down!")

1


[**_Anonymous_**](https://www.php.net/manual/en/function.ip2long.php#47814) [¶](https://www.php.net/manual/en/function.ip2long.php#47814)

**20 years ago**

`I re-wrote the functions from jbothe at hotmail dot com as a little exercise in OO and added a couple of extra functions.
<?php
//--------------
// IPv4 class
class ipv4
{
var $address;
var $netbits;
//--------------
// Create new class
function ipv4($address,$netbits)
{
    $this->address = $address;
    $this->netbits = $netbits;
}
//--------------
// Return the IP address
function address() { return ($this->address); }
//--------------
// Return the netbits
function netbits() { return ($this->netbits); }
//--------------
// Return the netmask
function netmask()
{
    return (long2ip(ip2long("255.255.255.255")
           << (32-$this->netbits)));
}
//--------------
// Return the network that the address sits in
function network()
{
    return (long2ip((ip2long($this->address))
           & (ip2long($this->netmask()))));
}
//--------------
// Return the broadcast that the address sits in
function broadcast()
{
    return (long2ip(ip2long($this->network())
           | (~(ip2long($this->netmask())))));
}
//--------------
// Return the inverse mask of the netmask
function inverse()
{
    return (long2ip(~(ip2long("255.255.255.255")
           << (32-$this->netbits))));
}
}
$ip = new ipv4("192.168.2.1",24);
print "Address: $ip->address()\n";
print "Netbits: $ip->netbits()\n";
print "Netmask: $ip->netmask()\n";
print "Inverse: $ip->inverse()\n";
print "Network: $ip->network()\n";
print "Broadcast: $ip->broadcast()\n";
?>`

[up](https://www.php.net/manual/vote-note.php?id=109298&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109298&page=function.ip2long&vote=down "Vote down!")

2


[**_admin at wudimei dot com_**](https://www.php.net/manual/en/function.ip2long.php#109298) [¶](https://www.php.net/manual/en/function.ip2long.php#109298)

**13 years ago**

`<?php
/**
*
*get the first ip and last ip from cidr(network id and mask length)
* i will integrate this function into "Rong Framework" :)
* @author admin@wudimei.com
* @param string $cidr 56.15.0.6/16 , [network id]/[mask length]
* @return array $ipArray = array( 0 =>"first ip of the network", 1=>"last ip of the network" );
*                         Each element of $ipArray's type is long int,use long2ip( $ipArray[0] ) to convert it into ip string.
* example:
* list( $long_startIp , $long_endIp) = getIpRange( "56.15.0.6/16" );
* echo "start ip:" . long2ip( $long_startIp );
* echo "<br />";
* echo "end ip:" . long2ip( $long_endIp );
*/
function getIpRang(  $cidr) {
list($ip, $mask) = explode('/', $cidr);

$maskBinStr =str_repeat("1", $mask ) . str_repeat("0", 32-$mask );      //net mask binary string
$inverseMaskBinStr = str_repeat("0", $mask ) . str_repeat("1",  32-$mask ); //inverse mask

$ipLong = ip2long( $ip );
$ipMaskLong = bindec( $maskBinStr );
$inverseIpMaskLong = bindec( $inverseMaskBinStr );
$netWork = $ipLong & $ipMaskLong;
$start = $netWork+1;//去掉网络号 ,ignore network ID(eg: 192.168.1.0)

$end = ($netWork | $inverseIpMaskLong) -1 ; //去掉广播地址 ignore brocast IP(eg: 192.168.1.255)
return array( $start, $end );
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=83548&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=83548&page=function.ip2long&vote=down "Vote down!")

1


[**_chrisp-phpnet at inventivedingo dot com_**](https://www.php.net/manual/en/function.ip2long.php#83548) [¶](https://www.php.net/manual/en/function.ip2long.php#83548)

**17 years ago**

`I had a problem with calling this function with REMOTE_ADDR on my lighttpd web server. Turned out that IPv6 was installed on this server, so even though REMOTE_ADDR was an IPv4 address, it was being formatted using IPv6's IPv4 compatibility mode. For example, 10.0.0.1 was becoming ::ffff:10.0.0.1, which caused iplong to report the address as invalid instead of parsing it correctly.
The correct fix would of course be to update my infrastructure so that it's properly IPv6-compatible; but in the context of my particular situation, this would involve a lot of re-engineering. So in the meantime, I worked around the issue using this quick and dirty hack:
<?php
    $ip = htmlspecialchars($_SERVER['REMOTE_ADDR']);
    if (strpos($ip, '::') === 0) {
        $ip = substr($ip, strrpos($ip, ':')+1);
    }
    $host = ip2long($ip);
?>
Ugly but functional.`

[up](https://www.php.net/manual/vote-note.php?id=73288&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73288&page=function.ip2long&vote=down "Vote down!")

2


[**_laacz at php dot net_**](https://www.php.net/manual/en/function.ip2long.php#73288) [¶](https://www.php.net/manual/en/function.ip2long.php#73288)

**18 years ago**

`Just to save you some time.
Beware that octets in IP address are being treated as numbers. So, '10.0.0.11' is not equal to '10.0.0.011'. '011' is octal number (base 8), so it converts to '9'. You can even go further and see that '10.0.0.0xa' also works (equals to '10.0.0.16').
This is not PHP issue, though.`

[up](https://www.php.net/manual/vote-note.php?id=114064&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114064&page=function.ip2long&vote=down "Vote down!")

0


[**_oo dot para at gmail dot com_**](https://www.php.net/manual/en/function.ip2long.php#114064) [¶](https://www.php.net/manual/en/function.ip2long.php#114064)

**11 years ago**

`If you want to validate IPs using this function, please be careful:
The function filter_var should be used instead for validating IPs.
<?php
$ip = '192.168.0355.24';
var_dump(ip2long($ip) !== false); // true (expected false)
var_dump(filter_var($ip, FILTER_VALIDATE_IP) !== false); // false
$ip = '192.168.355.24';
var_dump(ip2long($ip) !== false); // false
var_dump(filter_var($ip, FILTER_VALIDATE_IP) !== false); // false
?>`

[up](https://www.php.net/manual/vote-note.php?id=56373&page=function.ip2long&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56373&page=function.ip2long&vote=down "Vote down!")

0


[**_ken at expitrans dot com_**](https://www.php.net/manual/en/function.ip2long.php#56373) [¶](https://www.php.net/manual/en/function.ip2long.php#56373)

**20 years ago**

`Below is a merged form of all various notes, and a better (and correct) network matching function.
<?php
function net_match($network, $ip) {
      // determines if a network in the form of 192.168.17.1/16 or
      // 127.0.0.1/255.255.255.255 or 10.0.0.1 matches a given ip
      $ip_arr = explode('/', $network);
      $network_long = ip2long($ip_arr[0]);
      $x = ip2long($ip_arr[1]);
      $mask =  long2ip($x) == $ip_arr[1] ? $x : 0xffffffff << (32 - $ip_arr[1]);
      $ip_long = ip2long($ip);
      // echo ">".$ip_arr[1]."> ".decbin($mask)."\n";
      return ($ip_long & $mask) == ($network_long & $mask);
}
echo net_match('192.168.17.1/16', '192.168.15.1')."\n"; // returns true
echo net_match('127.0.0.1/255.255.255.255', '127.0.0.2')."\n"; // returns false
echo net_match('10.0.0.1', '10.0.0.1')."\n"; // returns true
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.ip2long&repo=en&redirect=https://www.php.net/manual/en/function.ip2long.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google