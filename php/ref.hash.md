---
url: https://www.php.net/manual/en/ref.hash.php
scraped_at: 2025-10-20T02:33:44.931Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Hash Functions [¶](https://www.php.net/manual/en/ref.hash.php\#ref.hash)

## Table of Contents [¶](https://www.php.net/manual/en/ref.hash.php\#ref.hash)

- [hash](https://www.php.net/manual/en/function.hash.php) — Generate a hash value (message digest)
- [hash\_algos](https://www.php.net/manual/en/function.hash-algos.php) — Return a list of registered hashing algorithms
- [hash\_copy](https://www.php.net/manual/en/function.hash-copy.php) — Copy hashing context
- [hash\_equals](https://www.php.net/manual/en/function.hash-equals.php) — Timing attack safe string comparison
- [hash\_file](https://www.php.net/manual/en/function.hash-file.php) — Generate a hash value using the contents of a given file
- [hash\_final](https://www.php.net/manual/en/function.hash-final.php) — Finalize an incremental hash and return resulting digest
- [hash\_hkdf](https://www.php.net/manual/en/function.hash-hkdf.php) — Generate a HKDF key derivation of a supplied key input
- [hash\_hmac](https://www.php.net/manual/en/function.hash-hmac.php) — Generate a keyed hash value using the HMAC method
- [hash\_hmac\_algos](https://www.php.net/manual/en/function.hash-hmac-algos.php) — Return a list of registered hashing algorithms suitable for hash\_hmac
- [hash\_hmac\_file](https://www.php.net/manual/en/function.hash-hmac-file.php) — Generate a keyed hash value using the HMAC method and the contents of a given file
- [hash\_init](https://www.php.net/manual/en/function.hash-init.php) — Initialize an incremental hashing context
- [hash\_pbkdf2](https://www.php.net/manual/en/function.hash-pbkdf2.php) — Generate a PBKDF2 key derivation of a supplied password
- [hash\_update](https://www.php.net/manual/en/function.hash-update.php) — Pump data into an active hashing context
- [hash\_update\_file](https://www.php.net/manual/en/function.hash-update-file.php) — Pump data into an active hashing context from a file
- [hash\_update\_stream](https://www.php.net/manual/en/function.hash-update-stream.php) — Pump data into an active hashing context from an open stream

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/hash/reference.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fref.hash%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.hash&repo=en&redirect=https://www.php.net/manual/en/ref.hash.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=82018&page=ref.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82018&page=ref.hash&vote=down "Vote down!")

4


[**_CraquePipe_**](https://www.php.net/manual/en/ref.hash.php#82018) [¶](https://www.php.net/manual/en/ref.hash.php#82018)

**17 years ago**

`For thoes of you who're looking to generate an NTLM hash (not an LM hash), I found out it's quite simple..
It uses the basic MD4 function, but the password needs to be in Unicode Little Endian encode first (this canbe achieved by the iconv function).
This can be done easily by using the following code:
<?php
function NTLMHash($Input) {
// Convert the password from UTF8 to UTF16 (little endian)
$Input=iconv('UTF-8','UTF-16LE',$Input);
// Encrypt it with the MD4 hash
$MD4Hash=bin2hex(mhash(MHASH_MD4,$Input));
// You could use this instead, but mhash works on PHP 4 and 5 or above
// The hash function only works on 5 or above
//$MD4Hash=hash('md4',$Input);
// Make it uppercase, not necessary, but it's common to do so with NTLM hashes
$NTLMHash=strtoupper($MD4Hash);
// Return the result
return($NTLMHash);
}
?>
To produce an LM hash requires a fully-written script containing the algorithm used to make it.
Enjoy,
CraquePipe.`

[up](https://www.php.net/manual/vote-note.php?id=84587&page=ref.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84587&page=ref.hash&vote=down "Vote down!")

3


[**_artem at it-nt dot ru_**](https://www.php.net/manual/en/ref.hash.php#84587) [¶](https://www.php.net/manual/en/ref.hash.php#84587)

**17 years ago**

`And some code for LM hash:
<?php
function LMhash($string)
{
    $string = strtoupper(substr($string,0,14));
    $p1 = LMhash_DESencrypt(substr($string, 0, 7));
    $p2 = LMhash_DESencrypt(substr($string, 7, 7));
    return strtoupper($p1.$p2);
}
function LMhash_DESencrypt($string)
{
    $key = array();
    $tmp = array();
    $len = strlen($string);
    for ($i=0; $i<7; ++$i)
        $tmp[] = $i < $len ? ord($string[$i]) : 0;
    $key[] = $tmp[0] & 254;
    $key[] = ($tmp[0] << 7) | ($tmp[1] >> 1);
    $key[] = ($tmp[1] << 6) | ($tmp[2] >> 2);
    $key[] = ($tmp[2] << 5) | ($tmp[3] >> 3);
    $key[] = ($tmp[3] << 4) | ($tmp[4] >> 4);
    $key[] = ($tmp[4] << 3) | ($tmp[5] >> 5);
    $key[] = ($tmp[5] << 2) | ($tmp[6] >> 6);
    $key[] = $tmp[6] << 1;

    $is = mcrypt_get_iv_size(MCRYPT_DES, MCRYPT_MODE_ECB);
    $iv = mcrypt_create_iv($is, MCRYPT_RAND);
    $key0 = "";

    foreach ($key as $k)
        $key0 .= chr($k);
    $crypt = mcrypt_encrypt(MCRYPT_DES, $key0, "KGS!@#$%", MCRYPT_MODE_ECB, $iv);
    return bin2hex($crypt);
}
?>
Some optimization?`

[up](https://www.php.net/manual/vote-note.php?id=94990&page=ref.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94990&page=ref.hash&vote=down "Vote down!")

 -3


[**_kungla at gmail dot com_**](https://www.php.net/manual/en/ref.hash.php#94990) [¶](https://www.php.net/manual/en/ref.hash.php#94990)

**15 years ago**

`For Samba ueserPassword you can use:
(I am not very sure aboute the salt part, but it works for me like that)
<?php
function CRYPThash($string, $salt = null)
{
    if (!$salt)
        $salt = rand(10,99);

    return "{CRYPT}".crypt($string, $salt);
}
?>
In posted NTLMHash function you can also use:
<?php
// Encrypt it with the MD4 hash
$MD4Hash=hash('md4',$Input);
?>
So you don't need to install mhash libraries`

[up](https://www.php.net/manual/vote-note.php?id=95595&page=ref.hash&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95595&page=ref.hash&vote=down "Vote down!")

 -4


[**_ocarter at mirabeau dot nl_**](https://www.php.net/manual/en/ref.hash.php#95595) [¶](https://www.php.net/manual/en/ref.hash.php#95595)

**15 years ago**

`Note for FreeBSD with PHP-5.
This is disabled by default; use the security/php5-hash port:
cd /usr/ports/security/php5-hash ; make install clean
(do not use the security/pecl-hash port as in the past, see the /usr/ports/UPDATING post from 20081211)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.hash&repo=en&redirect=https://www.php.net/manual/en/ref.hash.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google