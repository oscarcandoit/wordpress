---
url: https://www.php.net/manual/en/function.sha1.php
scraped_at: 2025-10-20T02:49:35.550Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# sha1

(PHP 4 >= 4.3.0, PHP 5, PHP 7, PHP 8)

sha1 — Calculate the sha1 hash of a string

**Warning**

It is not recommended to use this function to secure passwords,
due to the fast nature of this hashing algorithm. See the
[Password Hashing FAQ](https://www.php.net/manual/en/faq.passwords.php#faq.passwords.fasthash)
for details and best practices.


### Description [¶](https://www.php.net/manual/en/function.sha1.php\#refsect1-function.sha1-description)

**sha1**([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$binary` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**): [string](https://www.php.net/manual/en/language.types.string.php)

Calculates the sha1 hash of `string` using the
[» US Secure Hash Algorithm 1](https://datatracker.ietf.org/doc/html/rfc3174).


### Parameters [¶](https://www.php.net/manual/en/function.sha1.php\#refsect1-function.sha1-parameters)

`string`

The input string.


`binary`

If the optional `binary` is set to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**,
then the sha1 digest is instead returned in raw binary format with a
length of 20, otherwise the returned value is a 40-character
hexadecimal number.


### Return Values [¶](https://www.php.net/manual/en/function.sha1.php\#refsect1-function.sha1-returnvalues)

Returns the sha1 hash as a string.


### Examples [¶](https://www.php.net/manual/en/function.sha1.php\#refsect1-function.sha1-examples)

**Example #1 A **sha1()** example**

`<?php
$str = 'apple';
if (sha1($str) === 'd0be2dc421be4fcd0172e5afceea3970e2f3d940') {
    echo "Would you like a green or red apple?";
}
?>`

Run code

### See Also [¶](https://www.php.net/manual/en/function.sha1.php\#refsect1-function.sha1-seealso)

- [hash()](https://www.php.net/manual/en/function.hash.php) \- Generate a hash value (message digest)
- [password\_hash()](https://www.php.net/manual/en/function.password-hash.php) \- Creates a password hash

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/sha1.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.sha1%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.sha1&repo=en&redirect=https://www.php.net/manual/en/function.sha1.php)

### User Contributed Notes 31 notes

[up](https://www.php.net/manual/vote-note.php?id=81388&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81388&page=function.sha1&vote=down "Vote down!")

129


[**_nathan_**](https://www.php.net/manual/en/function.sha1.php#81388) [¶](https://www.php.net/manual/en/function.sha1.php#81388)

**17 years ago**

`The suggestion below to double-hash your password is not a good idea.  You are much much better off adding a variable salt to passwords before hashing (such as the username or other field that is dissimilar for every account).
Double hashing is *worse* security than a regular hash.  What you're actually doing is taking some input $passwd, converting it to a string of exactly 32 characters containing only the characters [0-9][A-F], and then hashing *that*. You have just *greatly* increased the odds of a hash collision (ie. the odds that I can guess a phrase that will hash to the same value as your password).
sha1(md5($pass)) makes even less sense, since you're feeding in 128-bits of information to generate a 256-bit hash, so 50% of the resulting data is redundant.  You have not increased security at all.`

[up](https://www.php.net/manual/vote-note.php?id=54509&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=54509&page=function.sha1&vote=down "Vote down!")

9


[**_Helpful Harry_**](https://www.php.net/manual/en/function.sha1.php#54509) [¶](https://www.php.net/manual/en/function.sha1.php#54509)

**20 years ago**

`check out these randomized sha1 password storage functions, they output a string of 50 characters, the first 40 characters being a sha1 output based on the last 10 characters - those being a random seed
to encode a password run pw_encode with the password, it'll return a different pseudo-random string every time - store this value.
to check a password run pw_check with the password attempt and the stored value, it'll return true on a match and false otherwise
these functions eliminate the pesky problem of dictionary matches being run on your password lists
<?php
function pw_encode($password)
{
for ($i = 1; $i <= 10; $i++)
       $seed .= substr('0123456789abcdef', rand(0,15), 1);
return sha1($seed.$password.$seed).$seed;
}
function pw_check($password, $stored_value)
{
if (strlen($stored_value) != 50)
      return FALSE;
$stored_seed = substr($stored_value,40,10);
if (sha1($stored_seed.$password.$stored_seed).$stored_seed == $stored_value)
     return TRUE;
else
     return FALSE;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=71449&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=71449&page=function.sha1&vote=down "Vote down!")

3


[**_novum123 at ribbonbazaar dot com_**](https://www.php.net/manual/en/function.sha1.php#71449) [¶](https://www.php.net/manual/en/function.sha1.php#71449)

**18 years ago**

`So far as the dictionary attacks are concerned, I thought up the following function:
<?php
function twistSTR($array){
$twisted="";
$array_strlen=array();
foreach ($array as $element){
    $array_strlen[]=strlen($element);
}
for ($i=0; $i<max($array_strlen); $i++){
    foreach ($array as $element){
      if ($i<strlen($element)){
        $twisted=$twisted.$element{$i};
      }
    }
}
return $twisted;
}
?>
The twistSTR function basically takes an array input of strings and alternates each character of each string among all the other strings.  For example:
<?php
echo twistSTR(array("this","and","that"));//output: tathnhidast
?>
It can be applied in the following manner:
<?php
if ($un===$_POST["username"] && $pwd===sha1(twistSTR(array($salt,$_POST["password"])))){
?>
It's not amazingly difficult to reverse engineer the actual output, but then again, that's not the point.  The point is that when a password is entered into one of those databases, they are going to enter for example "thisandthat", not "tathnhidast".`

[up](https://www.php.net/manual/vote-note.php?id=112844&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112844&page=function.sha1&vote=down "Vote down!")

5


[**_marcin at marcinwolny dot net_**](https://www.php.net/manual/en/function.sha1.php#112844) [¶](https://www.php.net/manual/en/function.sha1.php#112844)

**12 years ago**

`Keep in mind that MD5 is less secure than SHA1.
Older CPUs can calculate MD5 over twice as fast as SHA1. GPUs in parallel calculations can handle MD5 over 3 times as fast as SHA1!
Two Radeon 79xx-series GPUs can calculate a rainbow table for 6-character lowercase MD5 password in... roughly 6 seconds!
Source: [http://www.codinghorror.com/blog/2012/04/speed-hashing.html](http://www.codinghorror.com/blog/2012/04/speed-hashing.html)`

[up](https://www.php.net/manual/vote-note.php?id=86239&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86239&page=function.sha1&vote=down "Vote down!")

5


[**_Andre D_**](https://www.php.net/manual/en/function.sha1.php#86239) [¶](https://www.php.net/manual/en/function.sha1.php#86239)

**17 years ago**

`Here's a better version of the getDigestNotation() function I posted earlier. (The first version had a bug in the argument checking.)
<?php
function getDigestNotation($rawDigest, $bitsPerCharacter, $chars = NULL)
{
    if ($chars === NULL || strlen($chars) < 2) {
        $chars = '0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ-,';
    }
    if ($bitsPerCharacter < 1) {
        // $bitsPerCharacter must be at least 1
        $bitsPerCharacter = 1;
    } elseif (strlen($chars) < pow(2, $bitsPerCharacter)) {
        // Character length of $chars is too small for $bitsPerCharacter
        // Set $bitsPerCharacter to greatest value allowed by length of $chars
        $bitsPerCharacter = 1;
        $minCharLength = 2;
        while (strlen($chars) >= ($minCharLength *= 2)) {
            $bitsPerCharacter++;
        }
        unset($minCharLength);
    }
    $bytes = unpack('C*', $rawDigest);
    $byteCount = count($bytes);
    $out = '';
    $byte = array_shift($bytes);
    $bitsRead = 0;
    for ($i = 0; $i < $byteCount * 8 / $bitsPerCharacter; $i++) {
        if ($bitsRead + $bitsPerCharacter > 8) {
            // Not enough bits remain in this byte for the current character
            // Get remaining bits and get next byte
            $oldBits = $byte - ($byte >> 8 - $bitsRead << 8 - $bitsRead);
            if (count($bytes) == 0) {
                // Last bits; match final character and exit loop
                $out .= $chars[$oldBits];
                break;
            }
            $oldBitCount = 8 - $bitsRead;
            $byte = array_shift($bytes);
            $bitsRead = 0;
        } else {
            $oldBitCount = 0;
        }
        // Read only the needed bits from this byte
        $bits = $byte >> 8 - ($bitsRead + ($bitsPerCharacter - $oldBitCount));
        $bits = $bits - ($bits >> $bitsPerCharacter - $oldBitCount << $bitsPerCharacter - $oldBitCount);
        $bitsRead += $bitsPerCharacter - $oldBitCount;
        if ($oldBitCount > 0) {
            // Bits come from seperate bytes, add $oldBits to $bits
            $bits = ($oldBits << $bitsPerCharacter - $oldBitCount) | $bits;
        }
        $out .= $chars[$bits];
    }
    return $out;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=39492&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=39492&page=function.sha1&vote=down "Vote down!")

3


[**_mark at dot BANSPAM dot pronexus dot nl_**](https://www.php.net/manual/en/function.sha1.php#39492) [¶](https://www.php.net/manual/en/function.sha1.php#39492)

**21 years ago**

`Looking for a simple function to implement HMAC-SHA1 but don't want to use the entire PEAR Message lib?
//Calculate HMAC-SHA1 according to RFC2104
// [http://www.ietf.org/rfc/rfc2104.txt](http://www.ietf.org/rfc/rfc2104.txt)
function hmacsha1($key,$data) {
    $blocksize=64;
    $hashfunc='sha1';
    if (strlen($key)>$blocksize)
        $key=pack('H*', $hashfunc($key));
    $key=str_pad($key,$blocksize,chr(0x00));
    $ipad=str_repeat(chr(0x36),$blocksize);
    $opad=str_repeat(chr(0x5c),$blocksize);
    $hmac = pack(
                'H*',$hashfunc(
                    ($key^$opad).pack(
                        'H*',$hashfunc(
                            ($key^$ipad).$data
                        )
                    )
                )
            );
    return bin2hex($hmac);
}
It is very useful for client-authentication. see also [http://cookies.lcs.mit.edu/pubs/webauth:tr.pdf](http://cookies.lcs.mit.edu/pubs/webauth:tr.pdf)
Optionally you can change $hashfunc to 'md5' to make this an HMAC-MD5 function ;-)
If you want raw or base64 output instead of hexadecimal, just change the last return line.
Cheers,
Mark
p.s. the "$hmac =" line used to be 1 line but I had to cut it up in order to fit it here ;)`

[up](https://www.php.net/manual/vote-note.php?id=87692&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87692&page=function.sha1&vote=down "Vote down!")

4


[**_ranko84 at gmail dot com_**](https://www.php.net/manual/en/function.sha1.php#87692) [¶](https://www.php.net/manual/en/function.sha1.php#87692)

**16 years ago**

`Small update..., well more like fix to the obscure function, replace
<?php
if ($keepLength != NULL)
{
    if ($hSLength != 0)
    {
        $hPassHash = substr($hPassHash, $hLPosition, -$hRPosition);
    }
}
?>
with
<?php
if ($keepLength != NULL)
{
    if ($hSLength != 0)
    {
        if ($hRPosition == 0)
        {
            $hPassHash = substr($hPassHash, $hLPosition);
        }
        else
        {
            $hPassHash = substr($hPassHash, $hLPosition, -$hRPosition);
        }
    }
}
?>
I've been getting few requests to explain how it's used so, this might be little long.
Problems:
1. In most solutions with hash and salt, you were bound to have one extra row in your database that would state, preferably random, salt for that hashed data. If attacker would manage to get drop of your database he would get hashed data and salt that is used with plain data to make it obscure, and then cracking that hashed data would be same as if you didn't add any salt to it.
2. I stumbled upon some functions that would hash data, then input salt into random places in hash and store it in database, but they would still have to write down random parameter used to scramble salt so they could reuse it when validating data. Getting simple database drop wouldn't help much here, but if they would manage to get their hands on obscuring function too, they could easily see what is salt and what hash.
Solutions:
1. Why use extra row to store salt when you can input it in hash. I'm not sure how attackers determine what type of hash are they facing, but I guess it has connection to hash length. In that case, why make attackers job easier and store in database data_hash+salt where they could assume just by it's length it has salt in there.
Reason behind $keepLength. If it's set to 1, strlen of hashed data plus salt would be equal to strlen of hashed data leading attacker to believe there is no salt.
If you leave $keepLength on NULL, strlen of final result would be strlen(used_hash_algorithm)+$hSLength.
$minhPass is there to reserve enough place for string that has to be hashed, so someone using this function wouldn't accidentally delete it by setting too high salt length ($hSLength), for example... if you set it 30000 it will keep working normal.
2. If you think about it, constant, but variable value when making input would be same data that is being input.
In case we're trying to hash password, and have user A with password "notme", password strlen equals to 5, and if we use default parameters of the function, with $keepLength set to 1, process would be:
random salt, hash it, add first 5 characters of hashed_salt at beginning of plain password, add last 5 characters of hashed_salt at end of plain password, hash it. Replace first 5 characters of hashed_password with first 5 character of hashed_salt, do same with last 5 characters of hashed_password, return hashed_password.
In case that string is longer than 10 characters function would use simple mathematics to reduce it to numbers lower than 10, well... lower than number that is stated in $hSLength.
And good thing is that every time user enters correct password it has same length so it's not necessary to write it anywhere.
So what is achieved in the end?
1. Attacker might not know that hash is salted, and you don't have that extra row in your database stating THIS IS SALT FOR THIS HASH.
2. If he does find out that it is, he wouldn't know what is hashed password and what is salt.
3. If he manages to get access to obscure function, only thing that might help him is value of $hSLength, where if $hSLength is set to 10 he would have to crack 10 variations of hashed string since he doesn't know how long password of user he's trying to crack is.
For example first variation would be hashed_password without last 10 characters, second variation would be hashed_password without first character and last 9 characters...
4. Even in case he has enough power to crack all 10 variations, resulting string that he might get doesn't necessarily has to be exactly long as password of original user in which case, attacker fails again.`

[up](https://www.php.net/manual/vote-note.php?id=31479&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=31479&page=function.sha1&vote=down "Vote down!")

4


[**_bobm at hp dot com_**](https://www.php.net/manual/en/function.sha1.php#31479) [¶](https://www.php.net/manual/en/function.sha1.php#31479)

**22 years ago**

`To achieve raw binary format prior to PHP5, you can do this...
$raw = pack("H*", sha1($str));
Regards,
Bob Mader`

[up](https://www.php.net/manual/vote-note.php?id=56503&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56503&page=function.sha1&vote=down "Vote down!")

3


[**_Dan_**](https://www.php.net/manual/en/function.sha1.php#56503) [¶](https://www.php.net/manual/en/function.sha1.php#56503)

**20 years ago**

`I've noticed websites are now starting to require passwords of a certain length that MUST contain at least 1 non-alphanumeric character. This in itself makes dictionary attacks kind of useless. My web site requires that as well. It uses md5, and appends a site code into the md5 as well. And the include file that contains that site key is outside the public folders. I sure hope I've done enough to keep the bad boys out.`

[up](https://www.php.net/manual/vote-note.php?id=47609&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=47609&page=function.sha1&vote=down "Vote down!")

3


[**_sinatosk at gmail dot com_**](https://www.php.net/manual/en/function.sha1.php#47609) [¶](https://www.php.net/manual/en/function.sha1.php#47609)

**20 years ago**

`Heres an SHA1 function that will work on it's own completely. This is for users who are using below PHP 4.3.0. it works same as PHP5 ( being able to return raw output ).
<?php
/*
** Date modified: 1st October 2004 20:09 GMT
*
** PHP implementation of the Secure Hash Algorithm ( SHA-1 )
*
** This code is available under the GNU Lesser General Public License:
** [http://www.gnu.org/licenses/lgpl.txt](http://www.gnu.org/licenses/lgpl.txt)
*
** Based on the PHP implementation by Marcus Campbell
** [http://www.tecknik.net/sha-1/](http://www.tecknik.net/sha-1/)
*
** This is a slightly modified version by me Jerome Clarke ( sinatosk@gmail.com )
** because I feel more comfortable with this
*/
function sha1_str2blks_SHA1($str)
{
    $strlen_str = strlen($str);

    $nblk = (($strlen_str + 8) >> 6) + 1;

    for ($i=0; $i < $nblk * 16; $i++) $blks[$i] = 0;

    for ($i=0; $i < $strlen_str; $i++)
    {
        $blks[$i >> 2] |= ord(substr($str, $i, 1)) << (24 - ($i % 4) * 8);
    }

    $blks[$i >> 2] |= 0x80 << (24 - ($i % 4) * 8);
    $blks[$nblk * 16 - 1] = $strlen_str * 8;

    return $blks;
}
function sha1_safe_add($x, $y)
{
    $lsw = ($x & 0xFFFF) + ($y & 0xFFFF);
    $msw = ($x >> 16) + ($y >> 16) + ($lsw >> 16);

    return ($msw << 16) | ($lsw & 0xFFFF);
}
function sha1_rol($num, $cnt)
{
    return ($num << $cnt) | sha1_zeroFill($num, 32 - $cnt);
}
function sha1_zeroFill($a, $b)
{
    $bin = decbin($a);

    $strlen_bin = strlen($bin);

    $bin = $strlen_bin < $b ? 0 : substr($bin, 0, $strlen_bin - $b);

    for ($i=0; $i < $b; $i++) $bin = '0'.$bin;

    return bindec($bin);
}
function sha1_ft($t, $b, $c, $d)
{
    if ($t < 20) return ($b & $c) | ((~$b) & $d);
    if ($t < 40) return $b ^ $c ^ $d;
    if ($t < 60) return ($b & $c) | ($b & $d) | ($c & $d);

    return $b ^ $c ^ $d;
}
function sha1_kt($t)
{
    if ($t < 20) return 1518500249;
    if ($t < 40) return 1859775393;
    if ($t < 60) return -1894007588;

    return -899497514;
}
function sha1($str, $raw_output=FALSE)
{
    if ( $raw_output === TRUE ) return pack('H*', sha1($str, FALSE));

    $x = sha1_str2blks_SHA1($str);
    $a =  1732584193;
    $b = -271733879;
    $c = -1732584194;
    $d =  271733878;
    $e = -1009589776;

    $x_count = count($x);

    for ($i = 0; $i < $x_count; $i += 16)
    {
        $olda = $a;
        $oldb = $b;
        $oldc = $c;
        $oldd = $d;
        $olde = $e;

        for ($j = 0; $j < 80; $j++)
        {
            $w[$j] = ($j < 16) ? $x[$i + $j] : sha1_rol($w[$j - 3] ^ $w[$j - 8] ^ $w[$j - 14] ^ $w[$j - 16], 1);

            $t = sha1_safe_add(sha1_safe_add(sha1_rol($a, 5), sha1_ft($j, $b, $c, $d)), sha1_safe_add(sha1_safe_add($e, $w[$j]), sha1_kt($j)));
            $e = $d;
            $d = $c;
            $c = sha1_rol($b, 30);
            $b = $a;
            $a = $t;
        }

        $a = sha1_safe_add($a, $olda);
        $b = sha1_safe_add($b, $oldb);
        $c = sha1_safe_add($c, $oldc);
        $d = sha1_safe_add($d, $oldd);
        $e = sha1_safe_add($e, $olde);
    }

    return sprintf('%08x%08x%08x%08x%08x', $a, $b, $c, $d, $e);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=70474&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70474&page=function.sha1&vote=down "Vote down!")

5


[**_Gregory Boshoff_**](https://www.php.net/manual/en/function.sha1.php#70474) [¶](https://www.php.net/manual/en/function.sha1.php#70474)

**19 years ago**

`Note that the sha1 algorithm has been compromised and is no longer being used by government agencies.
As of PHP 5.1.2 a new set of hashing functions are available.
[http://www.php.net/manual/en/function.hash.php](http://www.php.net/manual/en/function.hash.php)
The new function hash() supports a new range of hashing methods.
echo hash('sha256', 'The quick brown fox jumped over the lazy dog.');
It is recommended that developers start to future proof their applications by using the stronger sha-2, hashing methods such as sha256, sha384, sha512 or better.
As of PHP 5.1.2 hash_algos() returns an array of system specific or registered hashing algorithms methods that are available to PHP.
print_r(hash_algos());`

[up](https://www.php.net/manual/vote-note.php?id=55435&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=55435&page=function.sha1&vote=down "Vote down!")

1


[**_WTM_**](https://www.php.net/manual/en/function.sha1.php#55435) [¶](https://www.php.net/manual/en/function.sha1.php#55435)

**20 years ago**

`Actually, the post by Helpful Harry won't improve your security except for the most simple break in attempts.  Since the random seed is attached to the end of the password hash, if you steal the hashed password, you steal the seed.
That means you can write a simple php program to call the pw_check function Harry included from a loop, feeding it dictionary words or random characters.
Of course, if you modified the program to use the seed in a more complicated way, "they" would have to know the new function's operation.  But then again, if someone can steal your password database, they can probably steal your website code (or guess it).`

[up](https://www.php.net/manual/vote-note.php?id=47097&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=47097&page=function.sha1&vote=down "Vote down!")

2


[**_rsemirag at yahoo dot com_**](https://www.php.net/manual/en/function.sha1.php#47097) [¶](https://www.php.net/manual/en/function.sha1.php#47097)

**20 years ago**

`If you're struggling to generate an SHA encoded password for LDAP (PHP < 5.0), what you end up needing is this:
$userpassword = base64_encode(pack("H*", sha1($pass)));
I found this in the OpenLDAP FAQ (many thanks to Google and Ace), though I'm using the iPlanet LDAP server.
Ray Semiraglio`

[up](https://www.php.net/manual/vote-note.php?id=94326&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94326&page=function.sha1&vote=down "Vote down!")

2


[**_Anonymous_**](https://www.php.net/manual/en/function.sha1.php#94326) [¶](https://www.php.net/manual/en/function.sha1.php#94326)

**15 years ago**

`Another solution to the salted hash with salt included directly in the hash, while keeping the same length of the result. If you want to generate a hash, call the function without the second argument. If you want to check a password against a hash, use the hash as the second argument. In this case, the function returns the hash itself on success, or boolean false on failure. You can also specify a hash algorithm as the third argument (otherwise SHA-1 will be used).
<?php
function __hash($password, $obscured = NULL, $algorithm = "sha1")
{
// whether to use user specified algorithm
$mode = in_array($algorithm, hash_algos());
// generate random salt
$salt = uniqid(mt_rand(), true);
// hash it
$salt = $mode ? hash($algorithm, $salt) : sha1($salt);
// get the length
$slen = strlen($salt);
// compute the actual length of salt we will use
// 1/8 to 1/4 of the hash, with shorter passwords producing longer salts
$slen = max($slen >> 3, ($slen >> 2) - strlen($password));
// if we are checking password against a hash, harvest the actual salt from it, otherwise just cut the salt we already have to the proper size
$salt = $obscured ? __harvest($obscured, $slen, $password) : substr($salt, 0, $slen);
// hash the password - this is maybe unnecessary
$hash = $mode ? hash($algorithm, $password) : sha1($password);
// place the salt in it
$hash = __scramble($hash, $salt, $password);
// and hash it again
$hash = $mode ? hash($algorithm, $hash) : sha1($hash);
// cut the result so we can add salt and maintain the same length
$hash = substr($hash, $slen);
// ... do that
$hash = __scramble($hash, $salt, $password);
// and return the result
return $obscured && $obscured !== $hash ? false : $hash;
}
?>
It uses a random, variable length salt, depending on the length of the password. The functions __scramble() and __harvest() are used to place salt into the hash or pull it out respectively. You can write your own, and of course the strength of the result greatly depends on them. They can be relatively simple yet still quite secure:
<?php
function __scramble($hash, $salt, $password)
{
return substr($hash, 0, strlen($password)) . $salt . substr($hash, strlen($password));
}
function __harvest($obscured, $slen, $password)
{
return substr($obscured, min(strlen($password), strlen($obscured) - $slen), $slen);
}
?>
Or they can be ridiculously complicated (my favourite kind):
<?php
function __scramble($hash, $salt, $password)
{
$k = strlen($password); $j = $k = $k > 0 ? $k : 1; $p = 0; $index = array(); $out = ""; $m = 0;
for ($i = 0; $i < strlen($salt); $i++)
{
    $c = substr($password, $p, 1);
    $j = pow($j + ($c !== false ? ord($c) : 0), 2) % (strlen($hash) + strlen($salt));
    while (array_key_exists($j, $index))
      $j = ++$j % (strlen($hash) + strlen($salt));
    $index[$j] = $i;
    $p = ++$p % $k;
}
for ($i = 0; $i < strlen($hash) + strlen($salt); $i++)
    $out .= array_key_exists($i, $index) ? $salt[$index[$i]] : $hash[$m++];
return $out;
}
function __harvest($obscured, $slen, $password)
{
$k = strlen($password); $j = $k = $k > 0 ? $k : 1; $p = 0; $index = array(); $out = "";
for ($i = 0; $i < $slen; $i++)
{
    $c = substr($password, $p, 1);
    $j = pow($j + ($c !== false ? ord($c) : 0), 2) % strlen($obscured);
    while (in_array($j, $index))
      $j = ++$j % strlen($obscured);
    $index[$i] = $j;
    $p = ++$p % $k;
}
for ($i = 0; $i < $slen; $i++)
    $out .= $obscured[$index[$i]];
return $out;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=56941&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56941&page=function.sha1&vote=down "Vote down!")

1


[**_php at REMOVEMEkennel17 dot co dot uk_**](https://www.php.net/manual/en/function.sha1.php#56941) [¶](https://www.php.net/manual/en/function.sha1.php#56941)

**20 years ago**

`It should be noted that sha1("") does not return an empty string.  This means that if you are running a system that does not require users to have a password, the following code will not work as expected:
<?php
if ($StoredPassword == sha1($NewPassword))
    // Password good
?>
If $StoredPassword and $NewPassword are both blank, then the password should be treated as good, but because sha1("") != "" it will be treated as bad. To get the correct behaviour you need to use:
<?php
if (($StoredPassword == "" && $NewPassword == "") || ($StoredPassword == sha1($NewPassword)))
    // Password good
?>
(Note: I use a custom IsBlank() function instead of comparison against the empty string, so NULL values are also matched.)
For reference, here are a couple of special values put through sha1().  Note that sha1("") == sha1(NULL) == sha1(false), and also that sha1(0) != sha1(false)
"" -> da39a3ee5e6b4b0d3255bfef95601890afd80709
NULL -> da39a3ee5e6b4b0d3255bfef95601890afd80709
0 -> b6589fc6ab0dc82cf12099d1c2d40ab994e8410c
1 -> 356a192b7913b04c54574d18c28d46e6395428ab
false -> da39a3ee5e6b4b0d3255bfef95601890afd80709
true -> 356a192b7913b04c54574d18c28d46e6395428ab`

[up](https://www.php.net/manual/vote-note.php?id=121919&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121919&page=function.sha1&vote=down "Vote down!")

0


[**_hkmaly_**](https://www.php.net/manual/en/function.sha1.php#121919) [¶](https://www.php.net/manual/en/function.sha1.php#121919)

**7 years ago**

`Note: Before you get some idea like using sha1 with password as way to prevent others tampering with message, read pages "Length extension attack" and "Hash-based message authentication code" on wikipedia. In short, naive constructions can be dangerously insecure. Use hash_hmac if available or reimplement HMAC properly without shortcuts, like already shown in comment from  mark at dot BANSPAM dot pronexus dot nl.`

[up](https://www.php.net/manual/vote-note.php?id=103024&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103024&page=function.sha1&vote=down "Vote down!")

0


[**_mgcummings at yahoo dot com_**](https://www.php.net/manual/en/function.sha1.php#103024) [¶](https://www.php.net/manual/en/function.sha1.php#103024)

**14 years ago**

`Thought I might save someone else some time trying to figure out how to generate a hash like MySQL5 PASSWORD() makes using just PHP.
$hash = '*' . sha1(sha1($pass), TRUE));`

[up](https://www.php.net/manual/vote-note.php?id=66239&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=66239&page=function.sha1&vote=down "Vote down!")

 -1


[**_erling dot westenvik at gmail dot com_**](https://www.php.net/manual/en/function.sha1.php#66239) [¶](https://www.php.net/manual/en/function.sha1.php#66239)

**19 years ago**

`Regarding php at REMOVEMEkennel17 dot co dot uk's note below:
The phrase: "To get the correct behaviour", would perhaps be better off if it read: "To get the wanted (but not recommended) behaviour".
Always honor the expected data types for functions: sha1 expects a string as input, and returns a string on exit. NULL, TRUE and FALSE are not string data types. The string "" is a string as good as "any". By following the "logic" that sha1("") should return "", then what should sha1("a") return? "b"? "c"?
An authentication system that allows for blank passwords is not really an authentication system in the first place. What you are describing is merely a way to tell the application that you want to see data in some specific context, like sorted by user name, etc. Create other tools for this purpose and leave the authentication system to deal with what it is supposed to do: Granting users access to restricted data and blocking other users from seeing the same data.
Don't store passwords in clear text, but salt and encrypt them. That way it makes perfect sense having <?php $sStoredPwd === sha1($sStoredSalt . $_POST["sTypedPwd"]); ?>, even with a blank "password". No other person than the user itself, not even the programmer, should know the password or be able to guess it. If the user forgets the password, a new one must be generated.
Regards,
Erling`

[up](https://www.php.net/manual/vote-note.php?id=86172&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86172&page=function.sha1&vote=down "Vote down!")

 -1


[**_Andr D_**](https://www.php.net/manual/en/function.sha1.php#86172) [¶](https://www.php.net/manual/en/function.sha1.php#86172)

**17 years ago**

`Sometimes you want the digest in both readable notation (such as hexadecimal) and raw binary. At other times you want the digest in a notation other than hexadecimal.
The following getDigestNotation() function takes a binary string and returns it in base 2, 4, 8, 16, 32, or 64 notation. It works with sha1(), md5(), hash(), or anything else that can output a raw binary string.
It works similar to the session.hash_bits_per_character php.ini configuration option.
You can specify which characters to use for each position, or use the default, which matches session.hash_bits_per_character (0-9, a-z, A-Z, "-", ","). The practical range of bits to use per character ($bitsPerCharacter) is 1 to 6; you may use more, but you will have to provide your own base character string ($chars) that is at least pow(2, $bitsPerCharacter) characters long. So even with 7 bits per character you need to specify a value for $chars that is 128 characters long, which exceeds the number of printable ASCII characters.
The output's radix relates to the value of $bitsPerCharacter as follows:
1: base-2 (binary)
2: base-4
3: base-8 (octal)
4: base-16 (hexadecimal)
5: base-32
6: base-64
<?php
$raw = sha1(uniqid(mt_rand(), TRUE), TRUE);
echo getDigestNotation($raw, 6);
function getDigestNotation($rawDigest, $bitsPerCharacter, $chars = NULL)
{
    if ($chars === NULL || strlen($chars) < 2) {
        $chars '0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ-,';
    }
    if ($bitsPerCharacter < 1) {
        // $bitsPerCharacter must be at least 1
        $bitsPerCharacter = 1;
    } elseif (strlen($chars) < pow(2, $bitsPerCharacter)) {
        // Character length of $chars is too small for $bitsPerCharacter
        // Set $bitsPerCharacter to greatest value allowed by length of $chars
        $bitsPerCharacter = 1;
        do {
            $bitsPerCharacter++;
        } while (strlen($chars) > pow(2, $bitsPerCharacter));
    }
    $bytes = unpack('C*', $rawDigest);
    $byteCount = count($bytes);
    $out = '';
    $byte = array_shift($bytes);
    $bitsRead = 0;
    for ($i = 0; $i < $byteCount * 8 / $bitsPerCharacter; $i++) {
        if ($bitsRead + $bitsPerCharacter > 8) {
            // Not enough bits remain in this byte for the current character
            // Get remaining bits and get next byte
            $oldBits = $byte - ($byte >> 8 - $bitsRead << 8 - $bitsRead);
            if (count($bytes) == 0) {
                // Last bits; match final character and exit loop
                $out .= $chars[$oldBits];
                break;
            }
            $oldBitCount = 8 - $bitsRead;
            $byte = array_shift($bytes);
            $bitsRead = 0;
        } else {
            $oldBitCount = 0;
        }
        // Read only the needed bits from this byte
        $bits = $byte >> 8 - ($bitsRead + ($bitsPerCharacter - $oldBitCount));
        $bits = $bits - ($bits >> $bitsPerCharacter - $oldBitCount << $bitsPerCharacter - $oldBitCount);
        $bitsRead += $bitsPerCharacter - $oldBitCount;
        if ($oldBitCount > 0) {
            // Bits come from seperate bytes, add $oldBits to $bits
            $bits = ($oldBits << $bitsPerCharacter - $oldBitCount) | $bits;
        }
        $out .= $chars[$bits];
    }
    return $out;
}
?>
Lastly, depending on the digest length, there may be fewer bits remaining for the last character than $bitsPerCharacter, so the last character will be smaller. The same thing happens with PHP's session ID generator, when 5 or 6 is used for session.hash_bits_per_character.`

[up](https://www.php.net/manual/vote-note.php?id=83079&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=83079&page=function.sha1&vote=down "Vote down!")

 -1


[**_ranko84 at gmail dot com_**](https://www.php.net/manual/en/function.sha1.php#83079) [¶](https://www.php.net/manual/en/function.sha1.php#83079)

**17 years ago**

`Thanks for the feedback. This should do the trick, I hope.
I think that I haven't understood this sentence completely "In this case you will need the salt to reside in the database along with the username and password." As in, were you refering to previous method, this method or this function.
Salt already resides in database along with username, password, or any string you decide to hash. This function just scrambles it depending on length of string (password) user enters so that attacker has trouble finding out what is salt and what is hash, if attacker even suspects that there is salt (reasons behind $keepLength, or defining $hSLength where you could set it to 24 leading attacker to believe he's facing sha256, not sha1).
<?php
function obscure ($hString, $hDecode = NULL, $hSLength = 10, $keepLength = NULL, $minhPass = 10, $hMethod = sha1)
{
    if ($hDecode == NULL)
    {
        for ($i = 0; $i<16; $i++)
        {

            $hSalt = rand(33, 255);
            $hRandomSalt .= chr($hSalt);
        }
        $hRandomSalt = hash($hMethod, $hRandomSalt);
    }
    else
    {
        $hRandomSalt = $hDecode;
    }
    if ($keepLength != NULL)
    {

        if ($hSLength > (strlen($hRandomSalt) - $minhPass))
        {
            $hSLength = (strlen($hRandomSalt) - $minhPass);
        }
    }
    else if ($hSLength < 0)
    {
        $hSLength = 0;
    }
    $hLPosition = strlen($hString);
    while ($hLPosition > $hSLength)
    {
        $hNumber = substr($hLPosition, -1);

        $hLPosition = $hLPosition * ($hNumber/10);
    }
    $hLPosition = (integer)$hLPosition;
    $hRPosition = $hSLength - $hLPosition;
    $hFSalt = substr($hRandomSalt, 0, $hLPosition);
    $hLSalt = substr($hRandomSalt, -$hRPosition, $hRPosition);
    $hPassHash = hash($hMethod, ($hLSalt . $hString . $hFSalt));
    if ($keepLength != NULL)
    {
        if ($hSLength != 0)
        {
            $hPassHash = substr($hPassHash, $hLPosition, -$hRPosition);
        }
    }
    return $hFSalt . $hPassHash . $hLSalt;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=101087&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101087&page=function.sha1&vote=down "Vote down!")

 -1


[**_rich dot sage at gmail dot com_**](https://www.php.net/manual/en/function.sha1.php#101087) [¶](https://www.php.net/manual/en/function.sha1.php#101087)

**14 years ago**

`If you're using Dovecot for mail retrieval and you want to generate SHA1 passwords yourself, you'll need to set the raw_output value to true, then base64_encode the output:
<?php
function makeDovecotPassword($input)
{
return '{SHA}' . base64_encode(sha1($input, true));
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=37442&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=37442&page=function.sha1&vote=down "Vote down!")

 -1


[**_labarks_**](https://www.php.net/manual/en/function.sha1.php#37442) [¶](https://www.php.net/manual/en/function.sha1.php#37442)

**21 years ago**

`Append this to the your sha1lib file to make it more portable.  If your version of php does support sha1() then it will try to use Mhash or else it will use the sha1lib.  Use $sha1 if you want to display which is being used.
if ( function_exists('sha1') )
    $sha1 = "sha1";
if ( !function_exists('sha1') && function_exists('mhash'))
{
    function sha1($hash_source)
    {
           $hash = mhash(MHASH_SHA1, $hash_source);
          $hex_hash = bin2hex($hash);
           return $hex_hash;
    }
    $sha1 = "Mhash";
}
if ( !function_exists('sha1') && !function_exists('mhash'))
{
    function sha1( $string, $raw_output = false )
    {
        $library = new Sha1Lib();

        return $raw_output ? $library->str_sha1($string) : $library->hex_sha1($string);
    }
    $sha1 = "sha1lib";
}`

[up](https://www.php.net/manual/vote-note.php?id=109602&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109602&page=function.sha1&vote=down "Vote down!")

 -5


[**_php at wbhostmax dot de_**](https://www.php.net/manual/en/function.sha1.php#109602) [¶](https://www.php.net/manual/en/function.sha1.php#109602)

**13 years ago**

`<?php
function DoubleSaltedHash($pw, $salt) {
    return sha1($salt.sha1($salt.sha1($pw)));
}
function generate_salt() {
        $dummy = array_merge(range('0', '9'));
        mt_srand((double)microtime()*1000000);
        for ($i = 1; $i <= (count($dummy)*2); $i++)
        {
                $swap = mt_rand(0,count($dummy)-1);
                $tmp = $dummy[$swap];
                $dummy[$swap] = $dummy[0];
                $dummy[0] = $tmp;
        }
        return sha1(substr(implode('',$dummy),0,9));
}
$pw="geheim"
$salt=generate_salt();
echo "hash:".DoubleSaltedHash($pw, $salt);
?>
this is my way to crypt passwords`

[up](https://www.php.net/manual/vote-note.php?id=77817&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77817&page=function.sha1&vote=down "Vote down!")

 -1


[**_NoName_**](https://www.php.net/manual/en/function.sha1.php#77817) [¶](https://www.php.net/manual/en/function.sha1.php#77817)

**18 years ago**

`Regarding the twistSTR - the problem is that currently it is relatively easy to generate a collision for any alphanumeric plaintext of a given, short length via e.g. a rainbow table. You're bettter off using a sufficiently lengthy and random salt.`

[up](https://www.php.net/manual/vote-note.php?id=88057&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88057&page=function.sha1&vote=down "Vote down!")

 -2


[**_mVamer_**](https://www.php.net/manual/en/function.sha1.php#88057) [¶](https://www.php.net/manual/en/function.sha1.php#88057)

**16 years ago**

`If I correctly understand what ranko84 is on about, this would be a simpler function with roughly the same result.
<?php
function obscure($password, $algorythm = "sha1")
{
        // Get some random salt, or verify a salt.
        // Added by (grosbedo AT gmail DOT com)
        if ($salt == NULL)
        {
            $salt = hash($algorythm, uniqid(rand(), true));
        }
    // Determine the length of the hash.
    $hash_length = strlen($salt);
    // Determine the length of the password.
    $password_length = strlen($password);
    // Determine the maximum length of password. This is only needed if
    // the user enters a very long password. In any case, the salt will
    // be a maximum of half the end result. The longer the hash, the
    // longer the password/salt can be.
    $password_max_length = $hash_length / 2;
    // Shorten the salt based on the length of the password.
    if ($password_length >= $password_max_length)
    {
        $salt = substr($salt, 0, $password_max_length);
    }
    else
    {
        $salt = substr($salt, 0, $password_length);
    }
    // Determine the length of the salt.
    $salt_length = strlen($salt);
    // Determine the salted hashed password.
    $salted_password = hash($algorythm, $salt . $password);
    // If we add the salt to the hashed password, we would get a hash that
    // is longer than a normally hashed password. We don't want that; it
    // would give away hints to an attacker. Because the password and the
    // length of the password are known, we can just throw away the first
    // couple of characters of the salted password. That way the salt and
    // the salted password together are the same length as a normally
    // hashed password without salt.
    $used_chars = ($hash_length - $salt_length) * -1;
    $final_result = $salt . substr($salted_password, $used_chars);
    return $final_result;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=50169&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=50169&page=function.sha1&vote=down "Vote down!")

 -2


[**_svn at datapirate dot de_**](https://www.php.net/manual/en/function.sha1.php#50169) [¶](https://www.php.net/manual/en/function.sha1.php#50169)

**20 years ago**

`Wanna use SHA-2 algorithm? Try this:
Download Tar-Ball from [http://www.adg.us/computers/sha.html](http://www.adg.us/computers/sha.html)
Compile (may occur some warnings) and test it:
cc -O2 -DSHA2_UNROLL_TRANSFORM -Wall -o sha2 sha2prog.c sha2.c
./sha2test.pl
Copy it to /usr/local/bin/ (don't forget to check permissions)
Here are two functions that could be used with:
function sha2($bits, $string){
    $sha2bin="/usr/local/bin/sha2";
    $echocmd="echo";
    if(!in_array($bits, array(256, 384, 512)))return(false);
    $r=exec($echocmd." ".escapeshellarg($string)."|".$sha2bin." -q -".$bits, $sha2);
    return($sha2[0]);
}
function sha2_file($bits, $filename){
    $sha2bin="/usr/local/bin/sha2";
    if(!in_array($bits, array(256, 384, 512)))return(false);
    if(!file_exists($filename)||!is_readable($filename))return(false);
    $r=exec($sha2bin." -q -".$bits." ".escapeshellarg($filename), $sha2);
    return($sha2[0]);
}
and use it like below:
<?php
$str = 'apple';
if (sha2(256, $str) === '303980bcb9e9e6cdec515230791af8b0ab1aaa244b58a8d99152673aa22197d0') {
echo "Would you like a green or red apple?";
exit;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=90301&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90301&page=function.sha1&vote=down "Vote down!")

 -4


[**_paul_**](https://www.php.net/manual/en/function.sha1.php#90301) [¶](https://www.php.net/manual/en/function.sha1.php#90301)

**16 years ago**

`I believe this offers best amount of protection using a random salt, that has to be stored so it can be used later for verification.
If no salt is given (which can be retrieved by halving the output and taking the first half), then it will generate a random salt, hash it, place it in a position relative to the length of password (between 0 and length of hash type(sha1? md5?)) within the hashed password, and then hash the complete string.
This results in a password hash using a salt that is dynamically placed dependant on password length. The salt used is then appended to the front of the finished hash so it can be retrieved later on for verifying.
Seeing as users will choose a typical password of between 5 and say 15 characters long, this gives them an extra 10 times the amount of dictionary attacks to try out with the hash as it could be placed in any position, because this is a random generated salt too, it means at least 10 dictionary attacks (with possiblity of upto 40) for each instance a password is created, to try and work out your sha1 encrypted password.
If you change your password say every month, even if someone gets a look in at your file through a local exploit, the amount of time to work out your password would far outweigh the frequency at which you change it.
Nothing is secure, but this should take them longer to work out then the time you change it. That is at least by todays technologies.
Paul
<?php
    function createHash($inText, $saltHash=NULL, $mode='sha1'){
        // hash the text //
        $textHash = hash($mode, $inText);
        // set where salt will appear in hash //
        $saltStart = strlen($inText);
        // if no salt given create random one //
        if($saltHash == NULL) {
            $saltHash = hash($mode, uniqid(rand(), true));
        }
        // add salt into text hash at pass length position and hash it //
        if($saltStart > 0 && $saltStart < strlen($saltHash)) {
            $textHashStart = substr($textHash,0,$saltStart);
            $textHashEnd = substr($textHash,$saltStart,strlen($saltHash));
            $outHash = hash($mode, $textHashEnd.$saltHash.$textHashStart);
        } elseif($saltStart > (strlen($saltHash)-1)) {
            $outHash = hash($mode, $textHash.$saltHash);
        } else {
            $outHash = hash($mode, $saltHash.$textHash);
        }
        // put salt at front of hash //
        $output = $saltHash.$outHash;
        return $output;
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=40226&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=40226&page=function.sha1&vote=down "Vote down!")

 -3


[**_brian\_bisaillon at rogers dot com_**](https://www.php.net/manual/en/function.sha1.php#40226) [¶](https://www.php.net/manual/en/function.sha1.php#40226)

**21 years ago**

`Source code to create SSHA passwords...
public function HashPassword($password)
{
mt_srand((double)microtime()*1000000);
$salt = mhash_keygen_s2k(MHASH_SHA1, $password, substr(pack('h*', md5(mt_rand())), 0, 8), 4);
$hash = "{SSHA}".base64_encode(mhash(MHASH_SHA1, $password.$salt).$salt);
return $hash;
}
Source code to validate SSHA passwords...
public function ValidatePassword($password, $hash)
{
$hash = base64_decode(substr($hash, 6));
$original_hash = substr($hash, 0, 20);
$salt = substr($hash, 20);
$new_hash = mhash(MHASH_SHA1, $password . $salt);
if (strcmp($original_hash, $new_hash) == 0)
     ... do something because your password is valid ...
else
    echo 'Unauthorized: Authorization has been refused for the credentials you provided. Please login with a valid username and password.';
    ... be sure to clear your session data ...
}
Note: The format is compatible with OpenLDAP's SSHA scheme if I'm not mistaken.`

[up](https://www.php.net/manual/vote-note.php?id=52372&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=52372&page=function.sha1&vote=down "Vote down!")

 -1


[**_alex at milivojevic dot org_**](https://www.php.net/manual/en/function.sha1.php#52372) [¶](https://www.php.net/manual/en/function.sha1.php#52372)

**20 years ago**

`Regarding my previous comment, if you want to be on the safe side and use only ASCII printable seeds (shouldn't matter for SSHA seeds), something like this could be used:
<?php
$salt = substr(base64_encode(pack("H*", sha1(mt_rand()))), 0, 4);
?>`

[up](https://www.php.net/manual/vote-note.php?id=121967&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121967&page=function.sha1&vote=down "Vote down!")

 -4


[**_cneeds athome dot co dot bw_**](https://www.php.net/manual/en/function.sha1.php#121967) [¶](https://www.php.net/manual/en/function.sha1.php#121967)

**7 years ago**

`The most secure way of sending passwords I have found so far
is to first ask for and receive a one-time code from the server
and mask (hash) the password being sent back to the server with the one-time code.`

[up](https://www.php.net/manual/vote-note.php?id=118770&page=function.sha1&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118770&page=function.sha1&vote=down "Vote down!")

 -3


[**_jcastromail at yahoo dot es_**](https://www.php.net/manual/en/function.sha1.php#118770) [¶](https://www.php.net/manual/en/function.sha1.php#118770)

**9 years ago**

`Hi there:
About the complexity of sha1, sha1 generates a code a different code each 1,4615016373309029182036848327163e+48 (2 ^ 160 bits).  So the chances of the use of the same hash is really small.
The "problem" of sha1 (and md5) is the speed of the generation. However, the speed is proportional with the length of the text to encrypt.
However, using a SALT, it increases tenfold times the security, even for a weak password.
In gross terms, a password of 6 characters can be hacked in a minute (if its store in md5 or sha).   However, a password of 7 characters takes an hour, a password of 8 a year and a password of more than 8 character is virtually inviable of hack.
However, if we used an SALT (a secret salt btw), then even a password of 3 characters will be really safe.
sha1('SALT SECRET TEXT!!@@@aaa0000'.'123');
And a double sha1 will ensure more safety
sha1(sha1('SALT SECRET TEXT'.'123',false),false)
It will require a rainbow table of 20 characters, enough big to be absurdly safe even for a thousand of servers running during a year.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.sha1&repo=en&redirect=https://www.php.net/manual/en/function.sha1.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google