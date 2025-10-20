---
url: https://www.php.net/manual/en/function.hash.php
scraped_at: 2025-10-20T02:39:35.848Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# hash

(PHP 5 >= 5.1.2, PHP 7, PHP 8, PECL hash >= 1.1)

hash — Generate a hash value (message digest)

### Description [¶](https://www.php.net/manual/en/function.hash.php\#refsect1-function.hash-description)

**hash**(

[string](https://www.php.net/manual/en/language.types.string.php) `$algo`,

[string](https://www.php.net/manual/en/language.types.string.php) `$data`,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$binary` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**,

[array](https://www.php.net/manual/en/language.types.array.php) `$options` = \[\]

): [string](https://www.php.net/manual/en/language.types.string.php)

### Parameters [¶](https://www.php.net/manual/en/function.hash.php\#refsect1-function.hash-parameters)

`algo`

Name of selected hashing algorithm (e.g. `"sha256"`).
For a list of supported algorithms see [hash\_algos()](https://www.php.net/manual/en/function.hash-algos.php).


`data`

Message to be hashed.


`binary`

When set to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, outputs raw binary data.
**`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** outputs lowercase hexits.


`options`

An array of options for the various hashing algorithms.
Currently, only the `"seed"` parameter is
supported by the MurmurHash variants.


### Return Values [¶](https://www.php.net/manual/en/function.hash.php\#refsect1-function.hash-returnvalues)

Returns a string containing the calculated message digest as lowercase hexits
unless `binary` is set to true in which case the raw
binary representation of the message digest is returned.


### Changelog [¶](https://www.php.net/manual/en/function.hash.php\#refsect1-function.hash-changelog)

| Version | Description |
| --- | --- |
| 8.1.0 | The `options` parameter has been added. |
| 8.0.0 | **hash()** now throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php) exception<br> if `algo` is unknown; previously, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** was returned instead. |

### Examples [¶](https://www.php.net/manual/en/function.hash.php\#refsect1-function.hash-examples)

**Example #1 A **hash()** example**

`<?php
echo hash('sha256', 'The quick brown fox jumped over the lazy dog.');
?>`

Run code

The above example will output:

```
68b1282b91de2c054c36629cb8dd447f12f096d3e3c587978dc2248444633483
```

### See Also [¶](https://www.php.net/manual/en/function.hash.php\#refsect1-function.hash-seealso)

- [hash\_init()](https://www.php.net/manual/en/function.hash-init.php) \- Initialize an incremental hashing context
- [hash\_file()](https://www.php.net/manual/en/function.hash-file.php) \- Generate a hash value using the contents of a given file
- [hash\_hmac()](https://www.php.net/manual/en/function.hash-hmac.php) \- Generate a keyed hash value using the HMAC method

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/hash/functions/hash.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.hash%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.hash&repo=en&redirect=https://www.php.net/manual/en/function.hash.php)

### User Contributed Notes 14 notes

[up](https://www.php.net/manual/vote-note.php?id=104987&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104987&page=function.hash&vote=down "Vote down!")

693


[**_nmmm at nmmm dot nu_**](https://www.php.net/manual/en/function.hash.php#104987) [¶](https://www.php.net/manual/en/function.hash.php#104987)

**14 years ago**

`I was interested how "long" each hash is, so I did:
<?php
$data = "hello";
foreach (hash_algos() as $v) {
        $r = hash($v, $data, false);
        printf("%-12s %3d %s\n", $v, strlen($r), $r);
}
?>
which produce (long hashes are cropped)
md2           32 a9046c73e00331af68917d3804f70655
md4           32 866437cb7a794bce2b727acc0362ee27
md5           32 5d41402abc4b2a76b9719d911017c592
sha1          40 aaf4c61ddcc5e8a2dabede0f3b482cd9aea9434d
sha256        64 2cf24dba5fb0a30e26e83b2ac5b9e29e1b161e5c1fa7425e730
sha384        96 59e1748777448c69de6b800d7a33bbfb9ff1b463e44354c3553
sha512       128 9b71d224bd62f3785d96d46ad3ea3d73319bfbc2890caadae2d
ripemd128     32 789d569f08ed7055e94b4289a4195012
ripemd160     40 108f07b8382412612c048d07d13f814118445acd
ripemd256     64 cc1d2594aece0a064b7aed75a57283d9490fd5705ed3d66bf9a
ripemd320     80 eb0cf45114c56a8421fbcb33430fa22e0cd607560a88bbe14ce
whirlpool    128 0a25f55d7308eca6b9567a7ed3bd1b46327f0f1ffdc804dd8bb
tiger128,3    32 a78862336f7ffd2c8a3874f89b1b74f2
tiger160,3    40 a78862336f7ffd2c8a3874f89b1b74f2f27bdbca
tiger192,3    48 a78862336f7ffd2c8a3874f89b1b74f2f27bdbca39660254
tiger128,4    32 1c2a939f230ee5e828f5d0eae5947135
tiger160,4    40 1c2a939f230ee5e828f5d0eae5947135741cd0ae
tiger192,4    48 1c2a939f230ee5e828f5d0eae5947135741cd0aefeeb2adc
snefru        64 7c5f22b1a92d9470efea37ec6ed00b2357a4ce3c41aa6e28e3b
gost          64 a7eb5d08ddf2363f1ea0317a803fcef81d33863c8b2f9f6d7d1
adler32        8 062c0215
crc32          8 3d653119
crc32b         8 3610a686
haval128,3    32 85c3e4fac0ba4d85519978fdc3d1d9be
haval160,3    40 0e53b29ad41cea507a343cdd8b62106864f6b3fe
haval192,3    48 bfaf81218bbb8ee51b600f5088c4b8601558ff56e2de1c4f
haval224,3    56 92d0e3354be5d525616f217660e0f860b5d472a9cb99d6766be
haval256,3    64 26718e4fb05595cb8703a672a8ae91eea071cac5e7426173d4c
haval128,4    32 fe10754e0b31d69d4ece9c7a46e044e5
haval160,4    40 b9afd44b015f8afce44e4e02d8b908ed857afbd1
haval192,4    48 ae73833a09e84691d0214f360ee5027396f12599e3618118
haval224,4    56 e1ad67dc7a5901496b15dab92c2715de4b120af2baf661ecd92
haval256,4    64 2d39577df3a6a63168826b2a10f07a65a676f5776a0772e0a87
haval128,5    32 d20e920d5be9d9d34855accb501d1987
haval160,5    40 dac5e2024bfea142e53d1422b90c9ee2c8187cc6
haval192,5    48 bbb99b1e989ec3174019b20792fd92dd67175c2ff6ce5965
haval224,5    56 aa6551d75e33a9c5cd4141e9a068b1fc7b6d847f85c3ab16295
haval256,5    64 348298791817d5088a6de6c1b6364756d404a50bd64e645035f`

[up](https://www.php.net/manual/vote-note.php?id=94104&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94104&page=function.hash&vote=down "Vote down!")

161


[**_Kai Petzke_**](https://www.php.net/manual/en/function.hash.php#94104) [¶](https://www.php.net/manual/en/function.hash.php#94104)

**16 years ago**

`The well known hash functions MD5 and SHA1 should be avoided in new applications. Collission attacks against MD5 are well documented in the cryptographics literature and have already been demonstrated in practice. Therefore, MD5 is no longer secure for certain applications.
Collission attacks against SHA1 have also been published, though they still require computing power, which is somewhat out of scope. As computing power increases with time and the attacks are likely to get better, too, attacks against systems relying on SHA1 for security are likely to become feasible within the next few years.
There is no lack of potential alternative hash algorithms, as the many choices for the "algo" argument of PHPs hash() function already suggests. Unfortunately, there is lack of analysis, as to how secure these alternative algorithms are. It is rather safe to assume, though, that the SHA2 family with its most prominent members SHA-256 und SHA-512, is better than SHA1.
When storing password hashes, it is a good idea to prefix a salt to the password before hashing, to avoid the same passwords to hash to the same values and to avoid the use of rainbow tables for password recovery. Unlike suggested in other articles, there is no security advantage in putting the salt in the middle, or even at both the beginning and the end, of the combined salt-password-string.
Rather, there are two other factors, that determine the strength of the salt: Its length and its variability. For example, using the same salt for all passwords is easy to implement, but gives only very little additional security. In particular, if users type the same passwords, they will still hash to the same value!
Therefore, the salt should be random string with at least as many variable bits, as there are bits in the hash result. In the user database, store username, the randomly generated salt for that user, and the result of hashing the salt-password-string. Access authentication is then done by looking up the entry for the user, calculating the hash of the salt found in the database and the password provided by the user, and comparing the result with the one stored in the database.`

[up](https://www.php.net/manual/vote-note.php?id=122785&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122785&page=function.hash&vote=down "Vote down!")

63


[**_jrz \[dot\] agarcia \[at\] gmail \[dot\] com_**](https://www.php.net/manual/en/function.hash.php#122785) [¶](https://www.php.net/manual/en/function.hash.php#122785)

**7 years ago**

`I was curious about hashes behavior (time and length), so i ran this code (yeah, I'm cheating because i took two examples from this page)
<?php
echo "Building data...";
$data = "";
for($i = 0; $i < 1500; $i++)
    $data .= sha1("H:k - $i - k:H");
echo "OK! (".strlen($data)." bytes)".PHP_EOL;
$res = [];
echo "Testing hashes.....".PHP_EOL;
foreach (hash_algos() as $algo) {
    $time = microtime(1);
    $hash = hash($algo, $data);
    $time = (microtime(1) - $time) * 1000;
    $length = strlen($hash);
    $res["$time"][] = [\
      "algo"   => "HEX-$algo",\
      "length" => "$length",\
      "time"   => sprintf("%.8f", $time)\
    ];
    $time = microtime(1);
    hash($algo, $data, 1);
    $time = (microtime(1) - $time) * 1000;
    $res["$time"][] = [\
      "algo"   => "RAW-$algo",\
      "length" => "$length",\
      "time"   => sprintf("%.8f", $time)\
    ];
}
ksort($res);
$i = 0;
echo "Results:".PHP_EOL;
echo "Posit.      Time in ms   Type-Hash algo        Hash length".PHP_EOL;
foreach($res as $sres){
    foreach($sres as $result){
      echo sprintf("%5d. %12s ms    %-20s %-2d bytes", $i++, $result['time'], $result['algo'], $result['length']).PHP_EOL;
    }
}
?>
I found interesting that today (may 31, 2018), I found 103 algos, 65 more than 9 years ago (based on this comment: [https://secure.php.net/manual/en/function.hash.php#89574](https://secure.php.net/manual/en/function.hash.php#89574) )
Also, here is my results: [https://ideone.com/embed/0iwuGn](https://ideone.com/embed/0iwuGn)
I'm not posting here due to message length limitations.`

[up](https://www.php.net/manual/vote-note.php?id=89574&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=89574&page=function.hash&vote=down "Vote down!")

78


[**_luka8088 at gmail dot com_**](https://www.php.net/manual/en/function.hash.php#89574) [¶](https://www.php.net/manual/en/function.hash.php#89574)

**16 years ago**

`Performance test results on my laptop:
Results are here shorten to fit php web notes ...
This was tested with 1024000 bytes (1000 KB) of random data, md4 always gets the first place, and md2 always get the last place :)
Results: (in microseconds)
1.  md4                           5307.912
2.  md5                           6890.058
3.  crc32b                        7298.946
4.  crc32                         7561.922
5.  sha1                          8886.098
6.  tiger128,3                    11054.992
7.  haval192,3                    11132.955
8.  haval224,3                    11160.135
9.  tiger160,3                    11162.996
10.  haval160,3                    11242.151
11.  haval256,3                    11327.981
12.  tiger192,3                    11630.058
13.  haval128,3                    11880.874
14.  tiger192,4                    14776.945
15.  tiger128,4                    14871.12
16.  tiger160,4                    14946.937
17.  haval160,4                    15661.954
18.  haval192,4                    15717.029
19.  haval256,4                    15759.944
20.  adler32                       15796.184
21.  haval128,4                    15887.022
22.  haval224,4                    16047.954
23.  ripemd256                     16245.126
24.  haval160,5                    17818.927
25.  haval128,5                    17887.115
26.  haval224,5                    18085.002
27.  haval192,5                    18135.07
28.  haval256,5                    18678.903
29.  sha256                        19020.08
30.  ripemd128                     20671.844
31.  ripemd160                     21853.923
32.  ripemd320                     22425.889
33.  sha384                        45102.119
34.  sha512                        45655.965
35.  gost                          57237.148
36.  whirlpool                     64682.96
37.  snefru                        80352.783
38.  md2                           705397.844
Code for generating this:
(compatible both with browser and cli mode)
<pre>
<?php
echo 'Building random data ...' . PHP_EOL;
@ob_flush();flush();
$data = '';
for ($i = 0; $i < 64000; $i++)
    $data .= hash('md5', rand(), true);
echo strlen($data) . ' bytes of random data built !' . PHP_EOL . PHP_EOL . 'Testing hash algorithms ...' . PHP_EOL;
@ob_flush();flush();
$results = array();
foreach (hash_algos() as $v) {
    echo $v . PHP_EOL;
    @ob_flush();flush();
    $time = microtime(true);
    hash($v, $data, false);
    $time = microtime(true) - $time;
    $results[$time * 1000000000][] = "$v (hex)";
    $time = microtime(true);
    hash($v, $data, true);
    $time = microtime(true) - $time;
    $results[$time * 1000000000][] = "$v (raw)";
}
ksort($results);
echo PHP_EOL . PHP_EOL . 'Results: ' . PHP_EOL;
$i = 1;
foreach ($results as $k => $v)
    foreach ($v as $k1 => $v1)
        echo ' ' . str_pad($i++ . '.', 4, ' ', STR_PAD_LEFT) . '  ' . str_pad($v1, 30, ' ') . ($k / 1000) . ' microseconds' . PHP_EOL;
?>
</pre>`

[up](https://www.php.net/manual/vote-note.php?id=121361&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121361&page=function.hash&vote=down "Vote down!")

11


[**_Hayley Watson_**](https://www.php.net/manual/en/function.hash.php#121361) [¶](https://www.php.net/manual/en/function.hash.php#121361)

**8 years ago**

`Of the hash algorithms currently available, SHA3 was chosen by NIST from fifty-one submitted candidates and subsequently mandated by the U.S. Department of Commerce for Federal Government use.
[http://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.202.pdf](http://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.202.pdf)
So if you're wanting to select a hash algorithm, you can consider SHA3 to be "good enough for government work".`

[up](https://www.php.net/manual/vote-note.php?id=124509&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124509&page=function.hash&vote=down "Vote down!")

10


[**_synnus at gmail dot com_**](https://www.php.net/manual/en/function.hash.php#124509) [¶](https://www.php.net/manual/en/function.hash.php#124509)

**5 years ago**

`<?php
/* PHP 7.4
n°   hash  results
1.   adler32 (hex)       555.992 ms
2.   adler32 (raw)       556.945 ms
3.   fnv132 (raw)        1107.931 ms
4.   fnv1a64 (raw)       1107.931 ms
5.   fnv164 (raw)        1108.169 ms
6.   fnv1a32 (raw)       1108.884 ms
7.   fnv164 (hex)        1108.884 ms
8.   fnv1a64 (hex)       1109.123 ms
9.   fnv132 (hex)        1116.991 ms
10.  fnv1a32 (hex)       1147.985 ms
11.  tiger192,3 (raw)    1523.017 ms
12.  tiger192,3 (hex)    1532.077 ms
13.  tiger128,3 (hex)    1538.038 ms
14.  tiger128,3 (raw)    1546.144 ms
15.  md4 (raw)           1554.965 ms
16.  md4 (hex)           1565.933 ms
17.  tiger160,3 (raw)    1574.039 ms
18.  tiger160,3 (hex)    1588.106 ms
19.  joaat (hex)         1661.777 ms
20.  joaat (raw)         1662.969 ms
21.  md5 (raw)           1822.948 ms
22.  md5 (hex)           1842.975 ms
23.  tiger160,4 (hex)    1996.994 ms
24.  tiger160,4 (raw)    2007.961 ms
25.  tiger128,4 (raw)    2035.14 ms
26.  tiger192,4 (raw)    2043.962 ms
27.  tiger128,4 (hex)    2065.896 ms
28.  tiger192,4 (hex)    2070.903 ms
29.  sha1 (hex)          2254.009 ms
30.  sha1 (raw)          2326.011 ms
31.  sha3-224 (hex)      2768.039 ms
32.  sha3-224 (raw)      2783.06 ms
33.  sha512 (hex)        2936.124 ms
34.  sha512 (raw)        2943.992 ms
35.  sha3-256 (hex)      2945.899 ms
36.  sha3-256 (raw)      2970.933 ms
37.  sha512/224 (raw)    2990.007 ms
38.  sha384 (raw)        3006.935 ms
39.  sha512/224 (hex)    3010.988 ms
40.  sha512/256 (raw)    3024.101 ms
41.  sha384 (hex)        3036.975 ms
42.  ripemd256 (raw)     3068.923 ms
43.  ripemd256 (hex)     3072.023 ms
44.  ripemd128 (raw)     3077.03 ms
45.  ripemd128 (hex)     3123.998 ms
46.  sha512/256 (hex)    3184.08 ms
47.  haval256,3 (hex)    3671.884 ms
48.  haval224,3 (hex)    3776.073 ms
49.  sha3-384 (hex)      3777.98 ms
50.  haval128,3 (raw)    3823.041 ms
51.  haval128,3 (hex)    3829.002 ms
52.  sha3-384 (raw)      3835.916 ms
53.  haval256,3 (raw)    3852.128 ms
54.  haval224,3 (raw)    3855.943 ms
55.  haval160,3 (raw)    3859.996 ms
56.  haval160,3 (hex)    3862.857 ms
57.  haval192,3 (raw)    3892.898 ms
58.  haval192,3 (hex)    3922.939 ms
59.  crc32c (hex)        4080.057 ms
60.  ripemd160 (hex)     4091.024 ms
61.  ripemd160 (raw)     4094.123 ms
62.  ripemd320 (raw)     4114.866 ms
63.  crc32b (hex)        4116.058 ms
64.  crc32 (raw)         4118.919 ms
65.  ripemd320 (hex)     4175.186 ms
66.  crc32c (raw)        4180.908 ms
67.  crc32 (hex)         4194.974 ms
68.  crc32b (raw)        4208.803 ms
69.  sha224 (hex)        4735.946 ms
70.  sha256 (raw)        4753.112 ms
71.  sha256 (hex)        4761.934 ms
72.  sha224 (raw)        4762.887 ms
73.  haval192,4 (raw)    5304.098 ms
74.  haval160,4 (raw)    5308.151 ms
75.  haval128,4 (raw)    5323.886 ms
76.  haval192,4 (hex)    5346.059 ms
77.  haval128,4 (hex)    5351.066 ms
78.  haval256,4 (hex)    5367.04 ms
79.  haval256,4 (raw)    5378.007 ms
80.  haval224,4 (raw)    5398.988 ms
81.  haval224,4 (hex)    5413.055 ms
82.  sha3-512 (raw)      5460.023 ms
83.  sha3-512 (hex)      5527.973 ms
84.  haval160,4 (hex)    5529.88 ms
85.  haval192,5 (hex)    6403.923 ms
86.  haval160,5 (raw)    6499.052 ms
87.  haval128,5 (raw)    6513.833 ms
88.  haval160,5 (hex)    6540.06 ms
89.  haval128,5 (hex)    6541.013 ms
90.  haval192,5 (raw)    6566.047 ms
91.  haval224,5 (raw)    6567.001 ms
92.  haval256,5 (hex)    6577.014 ms
93.  haval224,5 (hex)    6598.949 ms
94.  haval256,5 (raw)    6598.949 ms
95.  whirlpool (raw)     9627.103 ms
96.  whirlpool (hex)     9634.017 ms
97.  gost (raw)          18457.889 ms
98.  gost-crypto (raw)   18479.824 ms
99.  gost (hex)          18527.03 ms
100.  gost-crypto (hex)  18530.13 ms
101.  snefru256 (hex)    36260.843 ms
102.  snefru256 (raw)    36325.931 ms
103.  snefru (hex)       36480.903 ms
104.  snefru (raw)       36496.877 ms
105.  md2 (raw)          184617.996 ms
106.  md2 (hex)          185398.101 ms
*/
?>`

[up](https://www.php.net/manual/vote-note.php?id=84939&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84939&page=function.hash&vote=down "Vote down!")

32


[**_Leigh_**](https://www.php.net/manual/en/function.hash.php#84939) [¶](https://www.php.net/manual/en/function.hash.php#84939)

**17 years ago**

`Just a quick note about these benchmarks and how you should apply them.
If you are hashing passwords etc for security, speed is not your friend. You should use the slowest method.
Slow to hash means slow to crack and will hopefully make generating things like rainbow tables more trouble than it's worth.`

[up](https://www.php.net/manual/vote-note.php?id=113346&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113346&page=function.hash&vote=down "Vote down!")

8


[**_buar42 at gmail dot com_**](https://www.php.net/manual/en/function.hash.php#113346) [¶](https://www.php.net/manual/en/function.hash.php#113346)

**12 years ago**

`I made a PHP script that will let you sort all the available hashes on your system by generation time or by the length of the hash. It shows a general correlation on my system (longer hashes take longer to calculate) but some are faster than others, for example, sha512 makes the (joint) longest hash, but is actually only ninth slowest (from 43 hashes available on my machine)
As I understand it, the strength of a hash is dependant on the number of collisions that it has (where two input values produce the same hash) so with an infinite number of input values but a finite number of hashes, there are a (theoretically) infinite number of collisions. But, if you have a longer hash, then you're dividing infinity by a larger number, so you'll have fewer collisions.
In reality the number of collisions will be limited by the minimum and maximum password lengths that you choose to allow, so that if you enforce a policy where passwords must be exactly a certain length (20 characters for example) you'll have a large number of unique passwords, but a smaller number of potential inputs than you have hashes coming out, so that should prevent collisions entirely. In theory.
Tl;dr: I think that longer hashes are better.
Anyway, here's the code:
<?php
$data = "hello";
foreach (hash_algos() as $v)
{
$time=microtime(1);
for ($i = 0; $i < 10000; $i++)
{
    $r[$v] = strlen(hash($v, $data.$i, false));
}
$t[$v] = microtime(1)-$time;
}
switch ($_GET['sort'])
{
default:
ksort ($r);
$array = 'r';
break;
case 'length':
asort ($r);
$array = 'r';
break;
case 'time':
asort ($t);
$array = 't';
break;
}
echo '<pre>        <a href="?sort=alph">Name</a>        | <a href="?sort=length">Hash Length</a> | <a href="?sort=time">Time taken for 10000 hashes.</a>'."\n";
foreach ($$array as $key => $value)
{
echo $key;
for ($i = strlen ($key); $i <= 19; $i++)
{
    echo ' ';
}
echo '| '.$r[$key];
for ($i = strlen ($r[$key]); $i <= 11; $i++)
{
    echo ' ';
}
echo '| '.$t[$key]."\n";
}
echo '</pre>';
?>`

[up](https://www.php.net/manual/vote-note.php?id=107920&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107920&page=function.hash&vote=down "Vote down!")

5


[**_sneskid at hotmail dot com_**](https://www.php.net/manual/en/function.hash.php#107920) [¶](https://www.php.net/manual/en/function.hash.php#107920)

**13 years ago**

`On two different servers I found that crc32() relates to hash('crc32b',)
This may be good to know if you are writing a crc32_file function based on hash_file.
(The example does not compensate for negative crc32 results)
<?php
$val = 'hello';
var_dump(crc32($val) == ( '0x' . hash('crc32b', $val) ) ); // bool(true)
var_dump(crc32($val) == ( '0x' . hash('crc32', $val) ) ); // bool(false)
?>
Also if you are looking for a way to reduce collisions and still keep the hash result small (smaller than say md5) you could get a nice database friendly 64 bit value by using hash/crc32 and hash/crc32b, which is slower than a single md5 but the result may be more suitable for certain tasks.
<?php
$val = 'hello';
$crc64 = ( '0x' . hash('crc32', $val) . hash('crc32b', $val) ) );
var_dump($crc64); // string(18) "0x3d6531193610a686"
var_dump($crc64 + 0); // int(4423996193312384646)
?>
(examples tested on php 5.2.17)
note: ('0x' . $hex . + 0) is faster than base_convert($hex,16,10)`

[up](https://www.php.net/manual/vote-note.php?id=124917&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124917&page=function.hash&vote=down "Vote down!")

0


[**_Anonymous_**](https://www.php.net/manual/en/function.hash.php#124917) [¶](https://www.php.net/manual/en/function.hash.php#124917)

**5 years ago**

`<?PHP
function allhash($d){
    foreach(hash_algos() as $v){
        $r[] = "$v\t Length: ".strlen(hash($v, $d));
    }
    return $r;
}
print_r(allhash(1));
?>
output:
Array
(
    [0] => md2   Length: 32
    [1] => md4   Length: 32
    [2] => md5   Length: 32
    [3] => sha1  Length: 40
    [4] => sha224        Length: 56
    [5] => sha256        Length: 64
    [6] => sha384        Length: 96
    [7] => sha512/224    Length: 56
    [8] => sha512/256    Length: 64
    [9] => sha512        Length: 128
    [10] => sha3-224     Length: 56
    [11] => sha3-256     Length: 64
    [12] => sha3-384     Length: 96
    [13] => sha3-512     Length: 128
    [14] => ripemd128    Length: 32
    [15] => ripemd160    Length: 40
    [16] => ripemd256    Length: 64
    [17] => ripemd320    Length: 80
    [18] => whirlpool    Length: 128
    [19] => tiger128,3   Length: 32
    [20] => tiger160,3   Length: 40
    [21] => tiger192,3   Length: 48
    [22] => tiger128,4   Length: 32
    [23] => tiger160,4   Length: 40
    [24] => tiger192,4   Length: 48
    [25] => snefru       Length: 64
    [26] => snefru256    Length: 64
    [27] => gost         Length: 64
    [28] => gost-crypto  Length: 64
    [29] => adler32      Length: 8
    [30] => crc32        Length: 8
    [31] => crc32b       Length: 8
    [32] => crc32c       Length: 8
    [33] => fnv132       Length: 8
    [34] => fnv1a32      Length: 8
    [35] => fnv164       Length: 16
    [36] => fnv1a64      Length: 16
    [37] => joaat        Length: 8
    [38] => haval128,3   Length: 32
    [39] => haval160,3   Length: 40
    [40] => haval192,3   Length: 48
    [41] => haval224,3   Length: 56
    [42] => haval256,3   Length: 64
    [43] => haval128,4   Length: 32
    [44] => haval160,4   Length: 40
    [45] => haval192,4   Length: 48
    [46] => haval224,4   Length: 56
    [47] => haval256,4   Length: 64
    [48] => haval128,5   Length: 32
    [49] => haval160,5   Length: 40
    [50] => haval192,5   Length: 48
    [51] => haval224,5   Length: 56
    [52] => haval256,5   Length: 64
)`

[up](https://www.php.net/manual/vote-note.php?id=95715&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95715&page=function.hash&vote=down "Vote down!")

0


[**_robert+nospam at robert-gonzalez dot com_**](https://www.php.net/manual/en/function.hash.php#95715) [¶](https://www.php.net/manual/en/function.hash.php#95715)

**15 years ago**

`I've recently had the need to look at various hash algorithms and their values of the same string. To make my life a little easier I wrote this little script. It takes a string and runs it through all of the available hash algorithms on your server, outputting them in a clean little HTML table.
-----
<?php
/* Get the posted value of the form if there is one */
$p = empty($_POST['p']) ? null : $_POST['p'];
?>
<html>
<head><title>Hash testing</title></head>
<style type="text/css">
    table {border-collapse: collapse;}
    table, td, th {border: solid 1px #ccc;}
    th {background: #e1e1e1;border-color: #999;}
    td, th {padding: 0.25em;}
    td.algo {font-weight: bold;}
    tr.on td {background: #f0f0f0;}
</style>
<body>
    <h1>String hashing</h1>
    <form method="post" action="<?php echo basename(__FILE__) ?>">
        <p><label for="p">Enter a string to hash:</label><br /><input id="p" type="text" name="p" value="<?php echo $p ?>" /></p>
        <p><input type="submit" name="submit" value="Hash It" /></p>
    </form>

    <?php /* If there is a posted value use it */ ?>
    <?php if ($p): ?>
    <hr />
    <h2>Table of hash values for <em><?php echo $p ?></em> based on algorithm</h2>
    <table>
        <tr>
            <th>Algorithm</th>
            <th>Hashed value of <em><?php echo $p ?></em></th>
        </tr>
        <?php /* Loop through each hash algorithm, colorizing every other row */ ?>
        <?php $on = false; foreach (hash_algos() as $algo): ?>
        <tr<?php if ($on): ?> class="on"<?php endif; ?>>
            <td class="algo"><?php echo $algo ?></td>
            <td class="hash"><?php echo hash($algo, $p) ?></td>
        </tr>
    <?php $on = !$on; endforeach; ?>
    </table>
    <?php endif; ?>
</body>
</html>`

[up](https://www.php.net/manual/vote-note.php?id=121362&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121362&page=function.hash&vote=down "Vote down!")

 -2


[**_Hayley Watson_**](https://www.php.net/manual/en/function.hash.php#121362) [¶](https://www.php.net/manual/en/function.hash.php#121362)

**8 years ago**

`These are hash functions. Some have been designed to act as signatures for documents, while others are simply act as checks that transmitted data hasn't been damaged or otherwise modified during transmission and don't provide any cryptographic features.
Learn their differences, and use what's appropriate, because using the wrong hash function can be worse than not using one at all.`

[up](https://www.php.net/manual/vote-note.php?id=123152&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123152&page=function.hash&vote=down "Vote down!")

 -4


[**_Ricardo Striquer (ricardophp yohoocombr)_**](https://www.php.net/manual/en/function.hash.php#123152) [¶](https://www.php.net/manual/en/function.hash.php#123152)

**7 years ago**

`I haven't done any test or actual study (I'm using crc32 and storing it in mysql signed int types), but if your algorithm of choice is bigger them the supported integer of your database I suppose it is possible that the raw_format option is the best option to store directly in the database without type casting demands for it results in a binary string value.
To check if your algorithm of choice have the supported integer size in your database just strlen the raw_format output and see how many bytes it have (for example: crc32 have 4 bytes output, sha256 have 32 e md5 possue 16).
<?php
var_dump(strlen(hash('md5', 'string to check', true))); // int(16)
?>
PS: You can always use floating points to store a very big number but for "common humans" binary types by and large are easier to check, understand and maintain, so i recommend to use binary, but if you are about speed them floating point could be your friend.
PS: remembering ... without the raw_format the returned value are hexadecimal values without the 'Hx' complement, so to transform the result into a decimal just hexdec as shown ...
<?php
var_dump(hexdec(hash('crc32b', 'string to check'))); // int(1206832624)
?>
PS: Just registering ... I have noticed here some tests where 'crc32' is slower than md5, AFAIK by definition a CRC32 algorithm (there are several algorithms to calculate CRC32) is faster than MD5 and Adler-32 is faster than CRC32 (CRC32 is more consistent than Adler-32, less consistent than MD5, but if you want to safely validate the recommended would be SHA256 or better yet SHA512 because they are less likely to collide, so less vulnerable to collision attacks)`

[up](https://www.php.net/manual/vote-note.php?id=82972&page=function.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82972&page=function.hash&vote=down "Vote down!")

 -5


[**_inspiration3 at gmail dot com_**](https://www.php.net/manual/en/function.hash.php#82972) [¶](https://www.php.net/manual/en/function.hash.php#82972)

**17 years ago**

`Another comprehensive benchmark script that orders results from best to worst and includes the crc32(), md5() and sha1() standalone functions:
<?php
define('HASH_TIMES', 1000);
define('HASH_DATA', 'The quick brown fox jumped over!'); // 32 bytes
header('Content-Type: text/plain');
echo 'Testing ' . strlen(HASH_DATA) . ' bytes of data over ' . HASH_TIMES . " iterations:\n";
foreach (hash_algos() as $algo) {
    $time = microtime(1);
    for ($i = 0; $i < HASH_TIMES; $i++) hash($algo, HASH_DATA);
    $results[$algo] = microtime(1) - $time;
}
$time = microtime(1); for ($i = 0; $i < HASH_TIMES; $i++) crc32(HASH_DATA); $results['crc32()'] = microtime(1) - $time;
$time = microtime(1); for ($i = 0; $i < HASH_TIMES; $i++) md5(HASH_DATA); $results['md5()'] = microtime(1) - $time;
$time = microtime(1); for ($i = 0; $i < HASH_TIMES; $i++) sha1(HASH_DATA); $results['sha1()'] = microtime(1) - $time;
asort($results, SORT_NUMERIC);
foreach ($results as $algo => $time) echo "\n$time\t$algo";
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.hash&repo=en&redirect=https://www.php.net/manual/en/function.hash.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google