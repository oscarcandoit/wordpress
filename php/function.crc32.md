---
url: https://www.php.net/manual/en/function.crc32.php
scraped_at: 2025-10-20T02:56:32.050Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# crc32

(PHP 4 >= 4.0.1, PHP 5, PHP 7, PHP 8)

crc32 — Calculates the crc32 polynomial of a string

### Description [¶](https://www.php.net/manual/en/function.crc32.php\#refsect1-function.crc32-description)

**crc32**([string](https://www.php.net/manual/en/language.types.string.php) `$string`): [int](https://www.php.net/manual/en/language.types.integer.php)

Generates the cyclic redundancy checksum polynomial of 32-bit
lengths of the `string`. This is usually used
to validate the integrity of data being transmitted.


**Warning**

Because PHP's integer type is signed many crc32 checksums will
result in negative integers on 32bit platforms. On 64bit installations
all **crc32()** results will be positive integers though.


So you need to use the "%u" formatter of [sprintf()](https://www.php.net/manual/en/function.sprintf.php) or
[printf()](https://www.php.net/manual/en/function.printf.php) to get the string representation of the
unsigned **crc32()** checksum in decimal format.


For a hexadecimal representation of the checksum you can either use the
"%x" formatter of [sprintf()](https://www.php.net/manual/en/function.sprintf.php) or [printf()](https://www.php.net/manual/en/function.printf.php)
or the [dechex()](https://www.php.net/manual/en/function.dechex.php) conversion functions, both of these
also take care of converting the **crc32()** result to
an unsigned integer.


Having 64bit installations also return negative integers for higher
result values was considered but would break the hexadecimal conversion
as negatives would get an extra 0xFFFFFFFF######## offset then. As
hexadecimal representation seems to be the most common use case we
decided to not break this even if it breaks direct decimal comparisons
in about 50% of the cases when moving from 32 to 64bits.


In retrospect having the function return an integer maybe wasn't the
best idea and returning a hex string representation right away (as
e.g. [md5()](https://www.php.net/manual/en/function.md5.php) does) might have been a better plan to
begin with.


For a more portable solution you may also consider the generic
[hash()](https://www.php.net/manual/en/function.hash.php). `hash("crc32b", $str)` will
return the same string as `str_pad(dechex(crc32($str)), 8, '0', STR_PAD_LEFT)`.


### Parameters [¶](https://www.php.net/manual/en/function.crc32.php\#refsect1-function.crc32-parameters)

`string`

The data.


### Return Values [¶](https://www.php.net/manual/en/function.crc32.php\#refsect1-function.crc32-returnvalues)

Returns the crc32 checksum of `string` as an integer.


### Examples [¶](https://www.php.net/manual/en/function.crc32.php\#refsect1-function.crc32-examples)

**Example #1 Displaying a crc32 checksum**

This example shows how to print a converted checksum with the
[printf()](https://www.php.net/manual/en/function.printf.php) function:


`<?php
$checksum = crc32("The quick brown fox jumped over the lazy dog.");
printf("%u\n", $checksum);
?>`

Run code

### See Also [¶](https://www.php.net/manual/en/function.crc32.php\#refsect1-function.crc32-seealso)

- [hash()](https://www.php.net/manual/en/function.hash.php) \- Generate a hash value (message digest)
- [md5()](https://www.php.net/manual/en/function.md5.php) \- Calculate the md5 hash of a string
- [sha1()](https://www.php.net/manual/en/function.sha1.php) \- Calculate the sha1 hash of a string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/crc32.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.crc32%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.crc32&repo=en&redirect=https://www.php.net/manual/en/function.crc32.php)

### User Contributed Notes 22 notes

[up](https://www.php.net/manual/vote-note.php?id=96262&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96262&page=function.crc32&vote=down "Vote down!")

24


[**_jian at theorchard dot com_**](https://www.php.net/manual/en/function.crc32.php#96262) [¶](https://www.php.net/manual/en/function.crc32.php#96262)

**15 years ago**

`This function returns an unsigned integer from a 64-bit Linux platform.  It does return the signed integer from other 32-bit platforms even a 64-bit Windows one.
The reason is because the two constants PHP_INT_SIZE and PHP_INT_MAX have different values on the 64-bit Linux platform.
I've created a work-around function to handle this situation.
<?php
function get_signed_int($in) {
    $int_max = pow(2, 31)-1;
    if ($in > $int_max){
        $out = $in - $int_max * 2 - 2;
    }
    else {
        $out = $in;
    }
    return $out;
}
?>
Hope this helps.`

[up](https://www.php.net/manual/vote-note.php?id=111699&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111699&page=function.crc32&vote=down "Vote down!")

12


[**_i at morfi dot ru_**](https://www.php.net/manual/en/function.crc32.php#111699) [¶](https://www.php.net/manual/en/function.crc32.php#111699)

**12 years ago**

`Implementation crc64() in php 64bit
<?php
/**
* @return array
*/
function crc64Table()
{
    $crc64tab = [];
    // ECMA polynomial
    $poly64rev = (0xC96C5795 << 32) | 0xD7870F42;
    // ISO polynomial
    // $poly64rev = (0xD8 << 56);
    for ($i = 0; $i < 256; $i++)
    {
        for ($part = $i, $bit = 0; $bit < 8; $bit++) {
            if ($part & 1) {
                $part = (($part >> 1) & ~(0x8 << 60)) ^ $poly64rev;
            } else {
                $part = ($part >> 1) & ~(0x8 << 60);
            }
        }
       $crc64tab[$i] = $part;
    }
    return $crc64tab;
}
/**
* @param string $string
* @param string $format
* @return mixed
*
* Formats:
*  crc64('php'); // afe4e823e7cef190
*  crc64('php', '0x%x'); // 0xafe4e823e7cef190
*  crc64('php', '0x%X'); // 0xAFE4E823E7CEF190
*  crc64('php', '%d'); // -5772233581471534704 signed int
*  crc64('php', '%u'); // 12674510492238016912 unsigned int
*/
function crc64($string, $format = '%x')
{
    static $crc64tab;
    if ($crc64tab === null) {
        $crc64tab = crc64Table();
    }
    $crc = 0;
    for ($i = 0; $i < strlen($string); $i++) {
        $crc = $crc64tab[($crc ^ ord($string[$i])) & 0xff] ^ (($crc >> 8) & ~(0xff << 56));
    }
    return sprintf($format, $crc);
}`

[up](https://www.php.net/manual/vote-note.php?id=111931&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111931&page=function.crc32&vote=down "Vote down!")

10


[**_JS at JavsSys dot Org_**](https://www.php.net/manual/en/function.crc32.php#111931) [¶](https://www.php.net/manual/en/function.crc32.php#111931)

**12 years ago**

`The khash() function by sukitsupaluk has two problems, it does not use all 62 characters from the $map set and when corrected it then produces different results on 64-bit compared to 32-bit PHP systems.
Here is my modified version :
<?php
/**
* Small sample convert crc32 to character map
* Based upon [http://www.php.net/manual/en/function.crc32.php#105703](http://www.php.net/manual/en/function.crc32.php#105703)
* (Modified to now use all characters from $map)
* (Modified to be 32-bit PHP safe)
*/
function khash($data)
{
    static $map = "0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
    $hash = bcadd(sprintf('%u',crc32($data)) , 0x100000000);
    $str = "";
    do
    {
        $str = $map[bcmod($hash, 62) ] . $str;
        $hash = bcdiv($hash, 62);
    }
    while ($hash >= 1);
    return $str;
}
//-----------------------------------------------------------------------------------
$test = array(null, true, false, 0, "0", 1, "1", "2", "3", "ab", "abc", "abcd",
    "abcde", "abcdefoo", "248840027", "1365848013", // time()
    "9223372035488927794", // PHP_INT_MAX-time()
    "901131979", // mt_rand()
    "Sat, 13 Apr 2013 10:13:33 +0000" // gmdate('r')
);
$out = array();
foreach ($test as $s)
{
    $out[] = khash($s) . ": " . $s;
}
print "<h3>khash() -- maps a crc32 result into a (62-character) result</h3>";
print '<pre>';
var_dump($out);
print "\n\n\$GLOBALS['raw_crc32']:\n";
var_dump($GLOBALS['raw_crc32']);
print '</pre><hr>';
flush();
$pefile = __FILE__;
print "<h3>$pefile</h3>";
ob_end_flush();
flush();
highlight_file($pefile);
print "<hr>";
//-----------------------------------------------------------------------------------
/* CURRENT output
array(19) {
[0]=>
string(8) "4GFfc4: "
[1]=>
string(9) "76nO4L: 1"
[2]=>
string(8) "4GFfc4: "
[3]=>
string(9) "9aGcIp: 0"
[4]=>
string(9) "9aGcIp: 0"
[5]=>
string(9) "76nO4L: 1"
[6]=>
string(9) "76nO4L: 1"
[7]=>
string(9) "5b8iNn: 2"
[8]=>
string(9) "6HmfFN: 3"
[9]=>
string(10) "7ADPD7: ab"
[10]=>
string(11) "5F0aUq: abc"
[11]=>
string(12) "92kWw9: abcd"
[12]=>
string(13) "78hcpf: abcde"
[13]=>
string(16) "9eBVPB: abcdefoo"
[14]=>
string(17) "5TjOuZ: 248840027"
[15]=>
string(18) "5eNliI: 1365848013"
[16]=>
string(27) "4Q00e5: 9223372035488927794"
[17]=>
string(17) "6DUX8V: 901131979"
[18]=>
string(39) "5i2aOW: Sat, 13 Apr 2013 10:13:33 +0000"
}
*/
//-----------------------------------------------------------------------------------
?>`

[up](https://www.php.net/manual/vote-note.php?id=56215&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56215&page=function.crc32&vote=down "Vote down!")

10


[**_Bulk at bulksplace dot com_**](https://www.php.net/manual/en/function.crc32.php#56215) [¶](https://www.php.net/manual/en/function.crc32.php#56215)

**20 years ago**

`A faster way I've found to return CRC values of larger files, is instead of using the file()/implode() method used below, is to us file_get_contents() (PHP 4 >= 4.3.0) which uses memory mapping techniques if supported by your OS to enhance performance. Here's my example function:
<?php
// $file is the path to the file you want to check.
function file_crc($file)
{
    $file_string = file_get_contents($file);
    $crc = crc32($file_string);

    return sprintf("%u", $crc);
}
$file_to_crc = /home/path/to/file.jpg;
echo file_crc($file_to_crc); // Outputs CRC value for given file.
?>
I've found in testing this method is MUCH faster for larger binary files.`

[up](https://www.php.net/manual/vote-note.php?id=75884&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75884&page=function.crc32&vote=down "Vote down!")

8


[**_slimshady451_**](https://www.php.net/manual/en/function.crc32.php#75884) [¶](https://www.php.net/manual/en/function.crc32.php#75884)

**18 years ago**

`I see a lot of function for crc32_file, but for php version >= 5.1.2 don't forget you can use this :
<?php
function crc32_file($filename)
{
    return hash_file ('CRC32', $filename , FALSE );
}
?>
Using crc32(file_get_contents($filename)) will use too many memory on big file so don't use it.`

[up](https://www.php.net/manual/vote-note.php?id=39545&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=39545&page=function.crc32&vote=down "Vote down!")

6


[**_same_**](https://www.php.net/manual/en/function.crc32.php#39545) [¶](https://www.php.net/manual/en/function.crc32.php#39545)

**21 years ago**

`bit by bit crc32 computation
<?php
function bitbybit_crc32($str,$first_call=false){
    //reflection in 32 bits of crc32 polynomial 0x04C11DB7
    $poly_reflected=0xEDB88320;
    //=0xFFFFFFFF; //keep track of register value after each call
    static $reg=0xFFFFFFFF;
    //initialize register on first call
    if($first_call) $reg=0xFFFFFFFF;

    $n=strlen($str);
    $zeros=$n<4 ? $n : 4;
    //xor first $zeros=min(4,strlen($str)) bytes into the register
    for($i=0;$i<$zeros;$i++)
        $reg^=ord($str{$i})<<$i*8;
    //now for the rest of the string
    for($i=4;$i<$n;$i++){
        $next_char=ord($str{$i});
        for($j=0;$j<8;$j++)
            $reg=(($reg>>1&0x7FFFFFFF)|($next_char>>$j&1)<<0x1F)
                ^($reg&1)*$poly_reflected;
    }
    //put in enough zeros at the end
    for($i=0;$i<$zeros*8;$i++)
        $reg=($reg>>1&0x7FFFFFFF)^($reg&1)*$poly_reflected;
    //xor the register with 0xFFFFFFFF
    return ~$reg;
}
$str="123456789"; //whatever
$blocksize=4; //whatever
for($i=0;$i<strlen($str);$i+=$blocksize) $crc=bitbybit_crc32(substr($str,$i,$blocksize),!$i);
?>`

[up](https://www.php.net/manual/vote-note.php?id=79567&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=79567&page=function.crc32&vote=down "Vote down!")

5


[**_dave at jufer dot info_**](https://www.php.net/manual/en/function.crc32.php#79567) [¶](https://www.php.net/manual/en/function.crc32.php#79567)

**17 years ago**

`This function returns the same int value on a 64 bit mc. like the crc32() function on a 32 bit mc.
<?php
function crcKw($num){
    $crc = crc32($num);
    if($crc & 0x80000000){
        $crc ^= 0xffffffff;
        $crc += 1;
        $crc = -$crc;
    }
    return $crc;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=109662&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109662&page=function.crc32&vote=down "Vote down!")

3


[**_Clifford dot ct at gmail dot com_**](https://www.php.net/manual/en/function.crc32.php#109662) [¶](https://www.php.net/manual/en/function.crc32.php#109662)

**13 years ago**

`The crc32() function can return a signed integer in certain environments.  Assuming that it will always return an unsigned integer is not portable.
Depending on your desired behavior, you should probably use sprintf() on the result or the generic hash() instead.  Also note that integer arithmetic operators do not have the precision to work correctly with the integer output.`

[up](https://www.php.net/manual/vote-note.php?id=106672&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106672&page=function.crc32&vote=down "Vote down!")

3


[**_alban dot lopez+php \[ at \] gmail dot com_**](https://www.php.net/manual/en/function.crc32.php#106672) [¶](https://www.php.net/manual/en/function.crc32.php#106672)

**13 years ago**

`I made this code to verify Transmition with Vantage Pro2 ( weather station ) based on CRC16-CCITT standard.
<?php
// CRC16-CCITT validator
$crc_table = array(
    0x0,  0x1021,  0x2042,  0x3063,  0x4084,  0x50a5,  0x60c6,  0x70e7,
        0x8108,  0x9129,  0xa14a,  0xb16b,  0xc18c,  0xd1ad,  0xe1ce,  0xf1ef,
        0x1231,  0x210,  0x3273,  0x2252,  0x52b5,  0x4294,  0x72f7,  0x62d6,
        0x9339,  0x8318,  0xb37b,  0xa35a,  0xd3bd,  0xc39c,  0xf3ff,  0xe3de,
        0x2462,  0x3443,  0x420,  0x1401,  0x64e6,  0x74c7,  0x44a4,  0x5485,
        0xa56a,  0xb54b,  0x8528,  0x9509,  0xe5ee,  0xf5cf,  0xc5ac,  0xd58d,
        0x3653,  0x2672,  0x1611,  0x630,  0x76d7,  0x66f6,  0x5695,  0x46b4,
        0xb75b,  0xa77a,  0x9719,  0x8738,  0xf7df,  0xe7fe,  0xd79d,  0xc7bc,
        0x48c4,  0x58e5,  0x6886,  0x78a7,  0x840,  0x1861,  0x2802,  0x3823,
        0xc9cc,  0xd9ed,  0xe98e,  0xf9af,  0x8948,  0x9969,  0xa90a,  0xb92b,
        0x5af5,  0x4ad4,  0x7ab7,  0x6a96,  0x1a71,  0xa50,  0x3a33,  0x2a12,
        0xdbfd,  0xcbdc,  0xfbbf,  0xeb9e,  0x9b79,  0x8b58,  0xbb3b,  0xab1a,
        0x6ca6,  0x7c87,  0x4ce4,  0x5cc5,  0x2c22,  0x3c03,  0xc60,  0x1c41,
        0xedae,  0xfd8f,  0xcdec,  0xddcd,  0xad2a,  0xbd0b,  0x8d68,  0x9d49,
        0x7e97,  0x6eb6,  0x5ed5,  0x4ef4,  0x3e13,  0x2e32,  0x1e51,  0xe70,
        0xff9f,  0xefbe,  0xdfdd,  0xcffc,  0xbf1b,  0xaf3a,  0x9f59,  0x8f78,
        0x9188,  0x81a9,  0xb1ca,  0xa1eb,  0xd10c,  0xc12d,  0xf14e,  0xe16f,
        0x1080,  0xa1,  0x30c2,  0x20e3,  0x5004,  0x4025,  0x7046,  0x6067,
        0x83b9,  0x9398,  0xa3fb,  0xb3da,  0xc33d,  0xd31c,  0xe37f,  0xf35e,
        0x2b1,  0x1290,  0x22f3,  0x32d2,  0x4235,  0x5214,  0x6277,  0x7256,
        0xb5ea,  0xa5cb,  0x95a8,  0x8589,  0xf56e,  0xe54f,  0xd52c,  0xc50d,
        0x34e2,  0x24c3,  0x14a0,  0x481,  0x7466,  0x6447,  0x5424,  0x4405,
        0xa7db,  0xb7fa,  0x8799,  0x97b8,  0xe75f,  0xf77e,  0xc71d,  0xd73c,
        0x26d3,  0x36f2,  0x691,  0x16b0,  0x6657,  0x7676,  0x4615,  0x5634,
        0xd94c,  0xc96d,  0xf90e,  0xe92f,  0x99c8,  0x89e9,  0xb98a,  0xa9ab,
        0x5844,  0x4865,  0x7806,  0x6827,  0x18c0,  0x8e1,  0x3882,  0x28a3,
        0xcb7d,  0xdb5c,  0xeb3f,  0xfb1e,  0x8bf9,  0x9bd8,  0xabbb,  0xbb9a,
        0x4a75,  0x5a54,  0x6a37,  0x7a16,  0xaf1,  0x1ad0,  0x2ab3,  0x3a92,
        0xfd2e,  0xed0f,  0xdd6c,  0xcd4d,  0xbdaa,  0xad8b,  0x9de8,  0x8dc9,
        0x7c26,  0x6c07,  0x5c64,  0x4c45,  0x3ca2,  0x2c83,  0x1ce0,  0xcc1,
        0xef1f,  0xff3e,  0xcf5d,  0xdf7c,  0xaf9b,  0xbfba,  0x8fd9,  0x9ff8,
        0x6e17,  0x7e36,  0x4e55,  0x5e74,  0x2e93,  0x3eb2,  0xed1,  0x1ef0);
    $test = chr(0xC6).chr(0xCE).chr(0xA2).chr(0x03); // CRC16-CCITT = 0xE2B4
    genCRC ($test);

function genCRC (&$ptr)
{
    $crc = 0x0000;
    $crc_table = $GLOBALS['crc_table'];
    for ($i = 0; $i < strlen($ptr); $i++)
        $crc =  $crc_table[(($crc>>8) ^ ord($ptr[$i]))] ^ (($crc<<8) & 0x00FFFF);
    return $crc;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=64127&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=64127&page=function.crc32&vote=down "Vote down!")

4


[**_roberto at spadim dot com dot br_**](https://www.php.net/manual/en/function.crc32.php#64127) [¶](https://www.php.net/manual/en/function.crc32.php#64127)

**19 years ago**

`MODBUS RTU, CRC16,
input-> modbus rtu string
output -> 2bytes string, in correct modbus order
<?php
function crc16($string,$length=0){
    $auchCRCHi=array(    0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81,
                0x40, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0,
                0x80, 0x41, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x00, 0xC1, 0x81, 0x40, 0x01,
                0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41, 0x01, 0xC0, 0x80, 0x41,
                0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x00, 0xC1, 0x81,
                0x40, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41, 0x01, 0xC0,
                0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41, 0x01,
                0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81, 0x40,
                0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81,
                0x40, 0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0,
                0x80, 0x41, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x00, 0xC1, 0x81, 0x40, 0x01,
                0xC0, 0x80, 0x41, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41,
                0x00, 0xC1, 0x81, 0x40, 0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81,
                0x40, 0x01, 0xC0, 0x80, 0x41, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0,
                0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41, 0x01,
                0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81, 0x40, 0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41,
                0x00, 0xC1, 0x81, 0x40, 0x01, 0xC0, 0x80, 0x41, 0x01, 0xC0, 0x80, 0x41, 0x00, 0xC1, 0x81,
                0x40);
    $auchCRCLo=array(    0x00, 0xC0, 0xC1, 0x01, 0xC3, 0x03, 0x02, 0xC2, 0xC6, 0x06, 0x07, 0xC7, 0x05, 0xC5, 0xC4,
                0x04, 0xCC, 0x0C, 0x0D, 0xCD, 0x0F, 0xCF, 0xCE, 0x0E, 0x0A, 0xCA, 0xCB, 0x0B, 0xC9, 0x09,
                0x08, 0xC8, 0xD8, 0x18, 0x19, 0xD9, 0x1B, 0xDB, 0xDA, 0x1A, 0x1E, 0xDE, 0xDF, 0x1F, 0xDD,
                0x1D, 0x1C, 0xDC, 0x14, 0xD4, 0xD5, 0x15, 0xD7, 0x17, 0x16, 0xD6, 0xD2, 0x12, 0x13, 0xD3,
                0x11, 0xD1, 0xD0, 0x10, 0xF0, 0x30, 0x31, 0xF1, 0x33, 0xF3, 0xF2, 0x32, 0x36, 0xF6, 0xF7,
                0x37, 0xF5, 0x35, 0x34, 0xF4, 0x3C, 0xFC, 0xFD, 0x3D, 0xFF, 0x3F, 0x3E, 0xFE, 0xFA, 0x3A,
                0x3B, 0xFB, 0x39, 0xF9, 0xF8, 0x38, 0x28, 0xE8, 0xE9, 0x29, 0xEB, 0x2B, 0x2A, 0xEA, 0xEE,
                0x2E, 0x2F, 0xEF, 0x2D, 0xED, 0xEC, 0x2C, 0xE4, 0x24, 0x25, 0xE5, 0x27, 0xE7, 0xE6, 0x26,
                0x22, 0xE2, 0xE3, 0x23, 0xE1, 0x21, 0x20, 0xE0, 0xA0, 0x60, 0x61, 0xA1, 0x63, 0xA3, 0xA2,
                0x62, 0x66, 0xA6, 0xA7, 0x67, 0xA5, 0x65, 0x64, 0xA4, 0x6C, 0xAC, 0xAD, 0x6D, 0xAF, 0x6F,
                0x6E, 0xAE, 0xAA, 0x6A, 0x6B, 0xAB, 0x69, 0xA9, 0xA8, 0x68, 0x78, 0xB8, 0xB9, 0x79, 0xBB,
                0x7B, 0x7A, 0xBA, 0xBE, 0x7E, 0x7F, 0xBF, 0x7D, 0xBD, 0xBC, 0x7C, 0xB4, 0x74, 0x75, 0xB5,
                0x77, 0xB7, 0xB6, 0x76, 0x72, 0xB2, 0xB3, 0x73, 0xB1, 0x71, 0x70, 0xB0, 0x50, 0x90, 0x91,
                0x51, 0x93, 0x53, 0x52, 0x92, 0x96, 0x56, 0x57, 0x97, 0x55, 0x95, 0x94, 0x54, 0x9C, 0x5C,
                0x5D, 0x9D, 0x5F, 0x9F, 0x9E, 0x5E, 0x5A, 0x9A, 0x9B, 0x5B, 0x99, 0x59, 0x58, 0x98, 0x88,
                0x48, 0x49, 0x89, 0x4B, 0x8B, 0x8A, 0x4A, 0x4E, 0x8E, 0x8F, 0x4F, 0x8D, 0x4D, 0x4C, 0x8C,
                0x44, 0x84, 0x85, 0x45, 0x87, 0x47, 0x46, 0x86, 0x82, 0x42, 0x43, 0x83, 0x41, 0x81, 0x80,
                0x40);
    $length        =($length<=0?strlen($string):$length);
    $uchCRCHi    =0xFF;
    $uchCRCLo    =0xFF;
    $uIndex        =0;
    for ($i=0;$i<$length;$i++){
        $uIndex        =$uchCRCLo ^ ord(substr($string,$i,1));
        $uchCRCLo    =$uchCRCHi ^ $auchCRCHi[$uIndex];
        $uchCRCHi    =$auchCRCLo[$uIndex] ;
    }
    return(chr($uchCRCLo).chr($uchCRCHi));
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=41541&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=41541&page=function.crc32&vote=down "Vote down!")

2


[**_arachnid at notdot dot net_**](https://www.php.net/manual/en/function.crc32.php#41541) [¶](https://www.php.net/manual/en/function.crc32.php#41541)

**21 years ago**

`Note that the CRC32 algorithm should NOT be used for cryptographic purposes, or in situations where a hostile/untrusted user is involved, as it is far too easy to generate a hash collision for CRC32 (two different binary strings that have the same CRC32 hash). Instead consider SHA-1 or MD5.`

[up](https://www.php.net/manual/vote-note.php?id=105703&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105703&page=function.crc32&vote=down "Vote down!")

2


[**_sukitsupaluk at hotmail dot com_**](https://www.php.net/manual/en/function.crc32.php#105703) [¶](https://www.php.net/manual/en/function.crc32.php#105703)

**14 years ago**

`small sample convert crc32 to character map
<?php
function khash($data) {
    static $map="0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
    $hash=crc32($data)+0x100000000;
    $str = "";
    do {
        $str = $map[31+ ($hash % 31)] . $str;
        $hash /= 31;
    } while($hash >= 1);
    return $str;
}
$test= array(null,TRUE,FALSE,0,"0",1,"1","2","3","ab","abc","abcd","abcde","abcdefoo");
$out = array();
foreach($test as $s)
{
    $out[]=khash($s).": ". $s;
}
var_dump($out);
/*
output:
array
0 => string 'zVvOYTv: ' (length=9)
1 => string 'xKDKKL8: 1' (length=10)
2 => string 'zVvOYTv: ' (length=9)
3 => string 'zOKCQxh: 0' (length=10)
4 => string 'zOKCQxh: 0' (length=10)
5 => string 'xKDKKL8: 1' (length=10)
6 => string 'xKDKKL8: 1' (length=10)
7 => string 'AFSzIAO: 2' (length=10)
8 => string 'BXGSvQJ: 3' (length=10)
9 => string 'xZWOQSu: ab' (length=11)
10 => string 'AVAwHOR: abc' (length=12)
11 => string 'zKASNE1: abcd' (length=13)
12 => string 'xLCTOV7: abcde' (length=14)
13 => string 'zQLzKMt: abcdefoo' (length=17)
*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=100060&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100060&page=function.crc32&vote=down "Vote down!")

1


[**_chernyshevsky at hotmail dot com_**](https://www.php.net/manual/en/function.crc32.php#100060) [¶](https://www.php.net/manual/en/function.crc32.php#100060)

**15 years ago**

`The crc32_combine() function provided by petteri at qred dot fi has a bug that causes an infinite loop, a shift operation on a 32-bit signed int might never reach zero. Replacing the function gf2_matrix_times() with the following seems to fix it:
<?php
function gf2_matrix_times($mat, $vec)
{
    $sum=0;
    $i=0;
    while ($vec) {
        if ($vec & 1) {
            $sum ^= $mat[$i];
        }
        $vec = ($vec >> 1) & 0x7FFFFFFF;
        $i++;
    }
    return $sum;
}
?>
Otherwise, it's probably the best solution if you can't use hash_file(). Using a 1meg read buffer, the function only takes twice as long to process a 300meg files than hash_file() in my test.`

[up](https://www.php.net/manual/vote-note.php?id=93797&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93797&page=function.crc32&vote=down "Vote down!")

1


[**_berna (at) gensis (dot) com (dot) br_**](https://www.php.net/manual/en/function.crc32.php#93797) [¶](https://www.php.net/manual/en/function.crc32.php#93797)

**16 years ago**

`For those who want a more familiar return value for the function:
<?php
function strcrc32($text) {
$crc = crc32($text);
if ($crc & 0x80000000) {
    $crc ^= 0xffffffff;
    $crc += 1;
    $crc = -$crc;
}
return $crc;
}
?>
And to show the result in Hex string:
<?php
function int32_to_hex($value) {
$value &= 0xffffffff;
return str_pad(strtoupper(dechex($value)), 8, "0", STR_PAD_LEFT);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=106216&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106216&page=function.crc32&vote=down "Vote down!")

1


[**_arris at zsolttech dot com_**](https://www.php.net/manual/en/function.crc32.php#106216) [¶](https://www.php.net/manual/en/function.crc32.php#106216)

**14 years ago**

`not found anywhere crc64 based on [http://bioinfadmin.cs.ucl.ac.uk/downloads/crc64/crc64.c](http://bioinfadmin.cs.ucl.ac.uk/downloads/crc64/crc64.c) .
(use gmp module)
<?php
/* OLDCRC */
define('POLY64REV', "d800000000000000");
define('INITIALCRC', "0000000000000000");
define('TABLELEN', 256);
/* NEWCRC */
// define('POLY64REV', "95AC9329AC4BC9B5");
// define('INITIALCRC', "FFFFFFFFFFFFFFFF");
if(function_exists('gmp_init')){
        class CRC64{
                private static $CRCTable = array();
                public static function encode($seq){
                        $crc = gmp_init(INITIALCRC, 16);
                        $init = FALSE;
                        $poly64rev = gmp_init(POLY64REV, 16);
                        if (!$init)
                        {
                                $init = TRUE;
                                for ($i = 0; $i < TABLELEN; $i++)
                                {
                                        $part = gmp_init($i, 10);
                                        for ($j = 0; $j < 8; $j++)
                                        {
                                                if (gmp_strval(gmp_and($part, "0x1")) != "0"){
                                                        // if (gmp_testbit($part, 1)){ /* PHP 5 >= 5.3.0, untested */
                                                        $part = gmp_xor(gmp_div_q($part, "2"), $poly64rev);
                                                } else {
                                                        $part = gmp_div_q($part, "2");
                                                }
                                        }
                                        self::$CRCTable[$i] = $part;
                                }
                        }
                        for($k = 0; $k < strlen($seq); $k++){
                                $tmp_gmp_val = gmp_init(ord($seq[$k]), 10);
                                $tableindex = gmp_xor(gmp_and($crc, "0xff"), $tmp_gmp_val);
                                $crc = gmp_div_q($crc, "256");
                                $crc = gmp_xor($crc, self::$CRCTable[gmp_strval($tableindex, 10)]);
                        }
                        $res = gmp_strval($crc, 16);
                        return $res;
                }
        }
} else {
        die("Please install php-gmp package!!!");
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=31832&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=31832&page=function.crc32&vote=down "Vote down!")

1


[**_quix at free dot fr_**](https://www.php.net/manual/en/function.crc32.php#31832) [¶](https://www.php.net/manual/en/function.crc32.php#31832)

**22 years ago**

`I needed the crc32 of a file that was pretty large, so I didn't want to read it into memory.
So I made this:
<?php
    $GLOBALS['__crc32_table']=array();        // Lookup table array
    __crc32_init_table();
    function __crc32_init_table() {            // Builds lookup table array
        // This is the official polynomial used by
        // CRC-32 in PKZip, WinZip and Ethernet.
        $polynomial = 0x04c11db7;
        // 256 values representing ASCII character codes.
        for($i=0;$i <= 0xFF;++$i) {
            $GLOBALS['__crc32_table'][$i]=(__crc32_reflect($i,8) << 24);
            for($j=0;$j < 8;++$j) {
                $GLOBALS['__crc32_table'][$i]=(($GLOBALS['__crc32_table'][$i] << 1) ^
                    (($GLOBALS['__crc32_table'][$i] & (1 << 31))?$polynomial:0));
            }
            $GLOBALS['__crc32_table'][$i] = __crc32_reflect($GLOBALS['__crc32_table'][$i], 32);
        }
    }
    function __crc32_reflect($ref, $ch) {        // Reflects CRC bits in the lookup table
        $value=0;

        // Swap bit 0 for bit 7, bit 1 for bit 6, etc.
        for($i=1;$i<($ch+1);++$i) {
            if($ref & 1) $value |= (1 << ($ch-$i));
            $ref = (($ref >> 1) & 0x7fffffff);
        }
        return $value;
    }
    function __crc32_string($text) {        // Creates a CRC from a text string
        // Once the lookup table has been filled in by the two functions above,
        // this function creates all CRCs using only the lookup table.
        // You need unsigned variables because negative values
        // introduce high bits where zero bits are required.
        // PHP doesn't have unsigned integers:
        // I've solved this problem by doing a '&' after a '>>'.
        // Start out with all bits set high.
        $crc=0xffffffff;
        $len=strlen($text);
        // Perform the algorithm on each character in the string,
        // using the lookup table values.
        for($i=0;$i < $len;++$i) {
            $crc=(($crc >> 8) & 0x00ffffff) ^ $GLOBALS['__crc32_table'][($crc & 0xFF) ^ ord($text{$i})];
        }

        // Exclusive OR the result with the beginning value.
        return $crc ^ 0xffffffff;
    }

    function __crc32_file($name) {            // Creates a CRC from a file
        // Info: look at __crc32_string
        // Start out with all bits set high.
        $crc=0xffffffff;
        if(($fp=fopen($name,'rb'))===false) return false;
        // Perform the algorithm on each character in file
        for(;;) {
            $i=@fread($fp,1);
            if(strlen($i)==0) break;
            $crc=(($crc >> 8) & 0x00ffffff) ^ $GLOBALS['__crc32_table'][($crc & 0xFF) ^ ord($i)];
        }

        @fclose($fp);

        // Exclusive OR the result with the beginning value.
        return $crc ^ 0xffffffff;
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=28012&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=28012&page=function.crc32&vote=down "Vote down!")

1


[**_spectrumizer at cycos dot net_**](https://www.php.net/manual/en/function.crc32.php#28012) [¶](https://www.php.net/manual/en/function.crc32.php#28012)

**22 years ago**

`Here is a tested and working CRC16-Algorithm:
<?php
function crc16($string) {
$crc = 0xFFFF;
for ($x = 0; $x < strlen ($string); $x++) {
    $crc = $crc ^ ord($string[$x]);
    for ($y = 0; $y < 8; $y++) {
      if (($crc & 0x0001) == 0x0001) {
        $crc = (($crc >> 1) ^ 0xA001);
      } else { $crc = $crc >> 1; }
    }
}
return $crc;
}
?>
Regards,
Mario`

[up](https://www.php.net/manual/vote-note.php?id=78232&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78232&page=function.crc32&vote=down "Vote down!")

1


[**_Ren_**](https://www.php.net/manual/en/function.crc32.php#78232) [¶](https://www.php.net/manual/en/function.crc32.php#78232)

**18 years ago**

`Dealing with 32 bit unsigned values overflowing 32 bit php signed values can be done by adding 0x10000000 to any unexpected negative result, rather than using sprintf.
$i = crc32('1');
printf("%u\n", $i);
if (0 > $i)
{
    // Implicitly casts i as float, and corrects this sign.
    $i += 0x100000000;
}
var_dump($i);
Outputs:
2212294583
float(2212294583)`

[up](https://www.php.net/manual/vote-note.php?id=120387&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120387&page=function.crc32&vote=down "Vote down!")

0


[**_dotg at mail dot ru_**](https://www.php.net/manual/en/function.crc32.php#120387) [¶](https://www.php.net/manual/en/function.crc32.php#120387)

**8 years ago**

`crc32() on php 32bit and 64 bit not equal in some values
i use abs for result in positive for 32 bit
not equal
<?=abs(crc32(1));?>
64 bit
2212294583
32 bit
2082672713
equal
<?=abs(crc32(3));?>
64 bit
1842515611
32 bit
1842515611`

[up](https://www.php.net/manual/vote-note.php?id=118752&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118752&page=function.crc32&vote=down "Vote down!")

0


[**_toggio at writeme dot com_**](https://www.php.net/manual/en/function.crc32.php#118752) [¶](https://www.php.net/manual/en/function.crc32.php#118752)

**9 years ago**

`A faster implementation of modbus CRC16
function crc16($data)
{
$crc = 0xFFFF;
for ($i = 0; $i < strlen($data); $i++)
{
     $crc ^=ord($data[$i]);

        for ($j = 8; $j !=0; $j--)
        {
            if (($crc & 0x0001) !=0)
            {
                $crc >>= 1;
                $crc ^= 0xA001;
            }
            else
                $crc >>= 1;
        }
    }
return $crc;
}`

[up](https://www.php.net/manual/vote-note.php?id=75440&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75440&page=function.crc32&vote=down "Vote down!")

 -1


[**_mail at tristansmis dot nl_**](https://www.php.net/manual/en/function.crc32.php#75440) [¶](https://www.php.net/manual/en/function.crc32.php#75440)

**18 years ago**

`I used the abs value of this function on a 32-bit system. When porting the code to a 64-bit system I’ve found that the value is different. The following code has the same outcome on both systems.
<?php
$crc = abs(crc32($string));
if( $crc & 0x80000000){
      $crc ^= 0xffffffff;
      $crc += 1;
}
/* Old solution
    * $crc = abs(crc32($string))
    */
?>`

[up](https://www.php.net/manual/vote-note.php?id=99939&page=function.crc32&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99939&page=function.crc32&vote=down "Vote down!")

 -2


[**_gabri dot ns at gmail dot com_**](https://www.php.net/manual/en/function.crc32.php#99939) [¶](https://www.php.net/manual/en/function.crc32.php#99939)

**15 years ago**

`if you are looking for a fast function to hash a file, take a look at
[http://www.php.net/manual/en/function.hash-file.php](http://www.php.net/manual/en/function.hash-file.php)
this is crc32 file checker based on a CRC32 guide
it have performance at ~ 625 KB/s on my 2.2GHz Turion
far slower than hash_file('crc32b','filename.ext')
<?php
function crc32_file ($filename)
{
$f = @fopen($filename,'rb');
if (!$f) return false;

static $CRC32Table, $Reflect8Table;
if (!isset($CRC32Table))
{
      $Polynomial = 0x04c11db7;
      $topBit = 1 << 31;

      for($i = 0; $i < 256; $i++)
      {
         $remainder = $i << 24;
         for ($j = 0; $j < 8; $j++)
         {
            if ($remainder & $topBit)
               $remainder = ($remainder << 1) ^ $Polynomial;
            else $remainder = $remainder << 1;
         }

         $CRC32Table[$i] = $remainder;

         if (isset($Reflect8Table[$i])) continue;
         $str = str_pad(decbin($i), 8, '0', STR_PAD_LEFT);
         $num = bindec(strrev($str));
         $Reflect8Table[$i] = $num;
         $Reflect8Table[$num] = $i;
      }
}

$remainder = 0xffffffff;
while ($data = fread($f,1024))
{
      $len = strlen($data);
      for ($i = 0; $i < $len; $i++)
      {
         $byte = $Reflect8Table[ord($data[$i])];
         $index = (($remainder >> 24) & 0xff) ^ $byte;
         $crc = $CRC32Table[$index];
         $remainder = ($remainder << 8) ^ $crc;
      }
}

$str = decbin($remainder);
$str = str_pad($str, 32, '0', STR_PAD_LEFT);
$remainder = bindec(strrev($str));
return $remainder ^ 0xffffffff;
}
?>
<?php
$a = microtime();
echo dechex(crc32_file('filename.ext'))."\n";
$b = microtime();
echo array_sum(explode(' ',$b)) - array_sum(explode(' ',$a))."\n";
?>
Output:
ec7369fe
2.384134054184 (or similiar)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.crc32&repo=en&redirect=https://www.php.net/manual/en/function.crc32.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google