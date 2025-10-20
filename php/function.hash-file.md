---
url: https://www.php.net/manual/en/function.hash-file.php
scraped_at: 2025-10-20T02:36:54.904Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# hash\_file

(PHP 5 >= 5.1.2, PHP 7, PHP 8, PECL hash >= 1.1)

hash\_file — Generate a hash value using the contents of a given file

### Description [¶](https://www.php.net/manual/en/function.hash-file.php\#refsect1-function.hash-file-description)

**hash\_file**(

[string](https://www.php.net/manual/en/language.types.string.php) `$algo`,

[string](https://www.php.net/manual/en/language.types.string.php) `$filename`,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$binary` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**,

[array](https://www.php.net/manual/en/language.types.array.php) `$options` = \[\]

): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

### Parameters [¶](https://www.php.net/manual/en/function.hash-file.php\#refsect1-function.hash-file-parameters)

`algo`

Name of selected hashing algorithm (e.g. `"sha256"`).
For a list of supported algorithms see [hash\_algos()](https://www.php.net/manual/en/function.hash-algos.php).


`filename`

URL describing location of file to be hashed; Supports [fopen()](https://www.php.net/manual/en/function.fopen.php) wrappers.


`binary`

When set to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, outputs raw binary data.
**`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** outputs lowercase hexits.


`options`

An array of options for the various hashing algorithms.
Currently, only the `"seed"` parameter is
supported by the MurmurHash variants.


### Return Values [¶](https://www.php.net/manual/en/function.hash-file.php\#refsect1-function.hash-file-returnvalues)

Returns a string containing the calculated message digest as lowercase hexits
unless `binary` is set to true in which case the raw
binary representation of the message digest is returned, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Changelog [¶](https://www.php.net/manual/en/function.hash-file.php\#refsect1-function.hash-file-changelog)

| Version | Description |
| --- | --- |
| 8.1.0 | The `options` parameter has been added. |

### Examples [¶](https://www.php.net/manual/en/function.hash-file.php\#refsect1-function.hash-file-examples)

**Example #1 Using **hash\_file()****

`<?php
/* Create a file to calculate hash of */
file_put_contents('example.txt', 'The quick brown fox jumped over the lazy dog.');
echo hash_file('sha256', 'example.txt');
?>`

Run code

The above example will output:

```
68b1282b91de2c054c36629cb8dd447f12f096d3e3c587978dc2248444633483
```

### See Also [¶](https://www.php.net/manual/en/function.hash-file.php\#refsect1-function.hash-file-seealso)

- [hash\_init()](https://www.php.net/manual/en/function.hash-init.php) \- Initialize an incremental hashing context
- [hash\_hmac\_file()](https://www.php.net/manual/en/function.hash-hmac-file.php) \- Generate a keyed hash value using the HMAC method and the contents of a given file

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/hash/functions/hash-file.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.hash-file%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.hash-file&repo=en&redirect=https://www.php.net/manual/en/function.hash-file.php)

### User Contributed Notes 8 notes

[up](https://www.php.net/manual/vote-note.php?id=104836&page=function.hash-file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104836&page=function.hash-file&vote=down "Vote down!")

9


[**_apm at domain itsmee.co.uk_**](https://www.php.net/manual/en/function.hash-file.php#104836) [¶](https://www.php.net/manual/en/function.hash-file.php#104836)

**14 years ago**

`I have verified that the output of the "crc32" is the ITU I.363.5 algorithm (a.k.a. AAL5 CRC - popularised by BZIP2 but also used in ATM transmissions - the algorithm is the same as that in POSIX 1003.2-1992 in Cksum but that stuffs the size into the CRC at the end for extra measure).  However, the output is expressed in reverse order to many CRC programs.  Using the "standard" crctest.txt (numbers 1 to 9 in sequence - google it, it's not hard to find), php will output 181989fc - many other (Intel little endian) programs would output this as fc891918, hence the confusion (that I have had, at least).
The crc32b is the 32-bit Frame Check Sequence of ITU V.42 (used in Ethernet and popularised by PKZip).  The output from this CRC is popularised in Intel little endian format and would produce cbf43926 on the same file.`

[up](https://www.php.net/manual/vote-note.php?id=100061&page=function.hash-file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100061&page=function.hash-file&vote=down "Vote down!")

9


[**_chernyshevsky at hotmail dot com_**](https://www.php.net/manual/en/function.hash-file.php#100061) [¶](https://www.php.net/manual/en/function.hash-file.php#100061)

**15 years ago**

`If you want to use hash_file() to get the CRC32 value of a file, use the following to unpack the hex string returned by the function to an integer (similar to crc32()):
$hash = hash_file('crc32b', $filepath);
$array = unpack('N', pack('H*', $hash));
$crc32 = $array[1];`

[up](https://www.php.net/manual/vote-note.php?id=117484&page=function.hash-file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117484&page=function.hash-file&vote=down "Vote down!")

10


[**_synnus at gmail dot com_**](https://www.php.net/manual/en/function.hash-file.php#117484) [¶](https://www.php.net/manual/en/function.hash-file.php#117484)

**10 years ago**

`bench 476 Mo, win is 'haval160,4' : 0.037002
ALGO: md2, time: 74.702272891998
ALGO: md4, time: 9.2155270576477
ALGO: md5, time: 9.0815191268921
ALGO: sha1, time: 9.0945210456848
ALGO: sha224, time: 9.1465229988098
ALGO: sha256, time: 9.143522977829
ALGO: sha384, time: 14.065804004669
ALGO: sha512, time: 13.990800857544
ALGO: ripemd128, time: 9.3185329437256
ALGO: ripemd160, time: 9.3165328502655
ALGO: ripemd256, time: 9.2495288848877
ALGO: ripemd320, time: 9.2395279407501
ALGO: whirlpool, time: 27.779588937759
ALGO: tiger128,3, time: 9.3075330257416
ALGO: tiger160,3, time: 9.1875250339508
ALGO: tiger192,3, time: 9.3875370025635
ALGO: tiger128,4, time: 9.1755249500275
ALGO: tiger160,4, time: 9.355535030365
ALGO: tiger192,4, time: 9.2025260925293
ALGO: snefru, time: 42.781446218491
ALGO: snefru256, time: 42.613437175751
ALGO: gost, time: 18.606064081192
ALGO: gost-crypto, time: 18.664067983627
ALGO: adler32, time: 9.1535229682922
ALGO: crc32, time: 10.126579999924
ALGO: crc32b, time: 10.01757311821
ALGO: fnv132, time: 9.7505569458008
ALGO: fnv1a32, time: 9.7935597896576
ALGO: fnv164, time: 9.8945660591125
ALGO: fnv1a64, time: 9.3025319576263
ALGO: joaat, time: 9.7175559997559
ALGO: haval128,3, time: 9.6855540275574
ALGO: haval160,3, time: 10.10857796669
ALGO: haval192,3, time: 9.6765530109406
ALGO: haval224,3, time: 20.636180877686
ALGO: haval256,3, time: 10.641607999802
ALGO: haval128,4, time: 7.5594329833984
ALGO: haval160,4, time: 7.2884171009064
ALGO: haval192,4, time: 7.2934169769287
ALGO: haval224,4, time: 7.2964169979095
ALGO: haval256,4, time: 7.3034179210663
ALGO: haval128,5, time: 8.3244760036469
ALGO: haval160,5, time: 8.3174757957458
ALGO: haval192,5, time: 8.3204758167267
ALGO: haval224,5, time: 8.3234758377075
ALGO: haval256,5, time: 8.3254759311676
bench 13,0 Mo, win is 'adler32'  : 0.037002
ALGO: md2, time: 2.0341160297394
ALGO: md4, time: 0.062004089355469
ALGO: md5, time: 0.071003913879395
ALGO: sha1, time: 0.086004972457886
ALGO: sha224, time: 0.18301010131836
ALGO: sha256, time: 0.18301105499268
ALGO: sha384, time: 0.36102104187012
ALGO: sha512, time: 0.3610200881958
ALGO: ripemd128, time: 0.15900897979736
ALGO: ripemd160, time: 0.20701193809509
ALGO: ripemd256, time: 0.16500997543335
ALGO: ripemd320, time: 0.22501301765442
ALGO: whirlpool, time: 0.74204206466675
ALGO: tiger128,3, time: 0.12200689315796
ALGO: tiger160,3, time: 0.12100696563721
ALGO: tiger192,3, time: 0.12200713157654
ALGO: tiger128,4, time: 0.15700888633728
ALGO: tiger160,4, time: 0.15700888633728
ALGO: tiger192,4, time: 0.15600895881653
ALGO: snefru, time: 1.1520659923553
ALGO: snefru256, time: 1.151065826416
ALGO: gost, time: 0.48902797698975
ALGO: gost-crypto, time: 0.49202799797058
ALGO: adler32, time: 0.037002086639404
ALGO: crc32, time: 0.10300588607788
ALGO: crc32b, time: 0.093006134033203
ALGO: fnv132, time: 0.043002128601074
ALGO: fnv1a32, time: 0.045002937316895
ALGO: fnv164, time: 0.12800693511963
ALGO: fnv1a64, time: 0.12800693511963
ALGO: joaat, time: 0.070003986358643
ALGO: haval128,3, time: 0.12900686264038
ALGO: haval160,3, time: 0.12800693511963
ALGO: haval192,3, time: 0.12900805473328
ALGO: haval224,3, time: 0.12800693511963
ALGO: haval256,3, time: 0.12800693511963
ALGO: haval128,4, time: 0.19901204109192
ALGO: haval160,4, time: 0.1990110874176
ALGO: haval192,4, time: 0.20001196861267
ALGO: haval224,4, time: 0.20001101493835
ALGO: haval256,4, time: 0.20001220703125
ALGO: haval128,5, time: 0.22601294517517
ALGO: haval160,5, time: 0.2270131111145
ALGO: haval192,5, time: 0.2270131111145
ALGO: haval224,5, time: 0.2270131111145
ALGO: haval256,5, time: 0.22701287269592`

[up](https://www.php.net/manual/vote-note.php?id=122549&page=function.hash-file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122549&page=function.hash-file&vote=down "Vote down!")

3


[**_Lawrence Cherone_**](https://www.php.net/manual/en/function.hash-file.php#122549) [¶](https://www.php.net/manual/en/function.hash-file.php#122549)

**7 years ago**

`It's sometimes necessary to hash the same file with different algos,
<?php
function hash_file_multi($algos = [], $filename) {
    if (!is_array($algos)) {
        throw new \InvalidArgumentException('First argument must be an array');
    }
    if (!is_string($filename)) {
        throw new \InvalidArgumentException('Second argument must be a string');
    }
    if (!file_exists($filename)) {
        throw new \InvalidArgumentException('Second argument, file not found');
    }
    $result = [];
    $fp = fopen($filename, "r");
    if ($fp) {
        // ini hash contexts
        foreach ($algos as $algo) {
            $ctx[$algo] = hash_init($algo);
        }
        // calculate hash
        while (!feof($fp)) {
            $buffer = fgets($fp, 65536);
            foreach ($ctx as $key => $context) {
                hash_update($ctx[$key], $buffer);
            }
        }
        // finalise hash and store in return
        foreach ($algos as $algo) {
            $result[$algo] = hash_final($ctx[$algo]);
        }
        fclose($fp);
    } else {
        throw new \InvalidArgumentException('Could not open file for reading');
    }
    return $result;
}
?>
Which would be used like:
<?php
$result = hash_file_multi(['md5', 'sha1', 'sha256'], 'path/to/file.ext');
var_dump($result['md5'] === hash_file('md5', 'path/to/file.ext')); //true
var_dump($result['sha1'] === hash_file('sha1', 'path/to/file.ext')); //true
var_dump($result['sha256'] === hash_file('sha256', 'path/to/file.ext')); //true`

[up](https://www.php.net/manual/vote-note.php?id=85672&page=function.hash-file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85672&page=function.hash-file&vote=down "Vote down!")

3


[**_Keisial at gmail dot com_**](https://www.php.net/manual/en/function.hash-file.php#85672) [¶](https://www.php.net/manual/en/function.hash-file.php#85672)

**17 years ago**

`The 'octets reversed' you are seeing is the bug 45028 which has been fixed. [http://bugs.php.net/bug.php?id=45028](http://bugs.php.net/bug.php?id=45028)
The difference between crc32 and crc32b is explained on mhash man page. crc32 is the one used on ethernet, while crc32b is the one used on zip, png... They differ on the table used.`

[up](https://www.php.net/manual/vote-note.php?id=109259&page=function.hash-file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109259&page=function.hash-file&vote=down "Vote down!")

3


[**_holdoffhunger at gmail dot com_**](https://www.php.net/manual/en/function.hash-file.php#109259) [¶](https://www.php.net/manual/en/function.hash-file.php#109259)

**13 years ago**

`The Hash_File() function returns the same value as if the function Hash() had been performed on the same exact piece of data.  At first, I was uncertain if Hash_File() used the filename, or even the permission settings, when defining the data to be hashed for the given algorithm.  If it did work that way, then that means the same exact files would have different HASH values when you moved or renamed them on your system.  Anyway, fortunately, it does not work that way.  Hash() and Hash_File() produce identical results for the same pieces of data.  This is also true for the relationship between the Hash_HMAC() and Hash_HMAC_File() functions: the same pieces of data, the same keys, produce identical results.  It was a wise, design principle.
Some sample code to demonstrate this principle :
<?php
            // Author: holdoffhunger@gmail.com
        // Preset Data
        // ------------------------------------------------

    $test_data = "php-hashing";
    $test_file = "test.txt";
    $test_file_read = file_get_contents($test_file);

        // Hash Data
        // ------------------------------------------------

    $test_data_hash = hash("md2", $test_data, FALSE);
    $test_file_hash = hash_file("md2", $test_file, FALSE);

        // Print Hash Results
        // ------------------------------------------------

    print("Data Hash ($test_data): $test_data_hash<br><br>");
    print("File Hash ($test_file_read): $test_file_hash");

?>
    Expected Results
    ..................................

Data Hash (php-hashing): 457d84e1d69e519a7b73348db21477d3
File Hash (php-hashing): 457d84e1d69e519a7b73348db21477d3`

[up](https://www.php.net/manual/vote-note.php?id=121609&page=function.hash-file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121609&page=function.hash-file&vote=down "Vote down!")

 -2


[**_lnker dot ua at gmail dot com_**](https://www.php.net/manual/en/function.hash-file.php#121609) [¶](https://www.php.net/manual/en/function.hash-file.php#121609)

**8 years ago**

`Link id : 6r1j-d2gs
Code description : hash_file() performance check; Table head columns are sortable by clicking;
Open the code with PhpFiddle - [http://phpfiddle.org/main/code/6r1j-d2gs](http://phpfiddle.org/main/code/6r1j-d2gs)
Open the code with PhpFiddle Lite - [http://phpfiddle.org/lite/code/6r1j-d2gs](http://phpfiddle.org/lite/code/6r1j-d2gs)
So do not care a lot about performance! Just use what you need!`

[up](https://www.php.net/manual/vote-note.php?id=103656&page=function.hash-file&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103656&page=function.hash-file&vote=down "Vote down!")

 -5


[**_Anonymous_**](https://www.php.net/manual/en/function.hash-file.php#103656) [¶](https://www.php.net/manual/en/function.hash-file.php#103656)

**14 years ago**

`Please take note that hash-file will throw error on files >=2GB.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.hash-file&repo=en&redirect=https://www.php.net/manual/en/function.hash-file.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google