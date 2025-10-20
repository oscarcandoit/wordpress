---
url: https://www.php.net/manual/en/ref.bc.php
scraped_at: 2025-10-20T02:32:58.308Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# BC Math Functions [¶](https://www.php.net/manual/en/ref.bc.php\#ref.bc)

## Table of Contents [¶](https://www.php.net/manual/en/ref.bc.php\#ref.bc)

- [bcadd](https://www.php.net/manual/en/function.bcadd.php) — Add two arbitrary precision numbers
- [bcceil](https://www.php.net/manual/en/function.bcceil.php) — Round up arbitrary precision number
- [bccomp](https://www.php.net/manual/en/function.bccomp.php) — Compare two arbitrary precision numbers
- [bcdiv](https://www.php.net/manual/en/function.bcdiv.php) — Divide two arbitrary precision numbers
- [bcdivmod](https://www.php.net/manual/en/function.bcdivmod.php) — Get the quotient and modulus of an arbitrary precision number
- [bcfloor](https://www.php.net/manual/en/function.bcfloor.php) — Round down arbitrary precision number
- [bcmod](https://www.php.net/manual/en/function.bcmod.php) — Get modulus of an arbitrary precision number
- [bcmul](https://www.php.net/manual/en/function.bcmul.php) — Multiply two arbitrary precision numbers
- [bcpow](https://www.php.net/manual/en/function.bcpow.php) — Raise an arbitrary precision number to another
- [bcpowmod](https://www.php.net/manual/en/function.bcpowmod.php) — Raise an arbitrary precision number to another, reduced by a specified modulus
- [bcround](https://www.php.net/manual/en/function.bcround.php) — Round arbitrary precision number
- [bcscale](https://www.php.net/manual/en/function.bcscale.php) — Set or get default scale parameter for all bc math functions
- [bcsqrt](https://www.php.net/manual/en/function.bcsqrt.php) — Get the square root of an arbitrary precision number
- [bcsub](https://www.php.net/manual/en/function.bcsub.php) — Subtract one arbitrary precision number from another

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/bc/reference.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fref.bc%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.bc&repo=en&redirect=https://www.php.net/manual/en/ref.bc.php)

### User Contributed Notes 18 notes

[up](https://www.php.net/manual/vote-note.php?id=82155&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=82155&page=ref.bc&vote=down "Vote down!")

22


[**_Bouke Haarsma_**](https://www.php.net/manual/en/ref.bc.php#82155) [¶](https://www.php.net/manual/en/ref.bc.php#82155)

**17 years ago**

`Please be aware not to use/have spaces in your strings. It took me a while to find the error in some advanced calculations!
<?php
echo bcadd("1", "2"); // 3
echo bcadd("1", "2 "); // 1
echo bcadd("1", " 2"); // 1
?>`

[up](https://www.php.net/manual/vote-note.php?id=107014&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107014&page=ref.bc&vote=down "Vote down!")

15


[**_dawidgarus at gmail dot com_**](https://www.php.net/manual/en/ref.bc.php#107014) [¶](https://www.php.net/manual/en/ref.bc.php#107014)

**13 years ago**

`If you too are confused with illegible code like this:
<?php
$a = "3";
$b = "5";
bcadd(bcmod(bcadd(bcdiv(bcsqrt(bcadd(7, bcpow($a, 2))), 4), $b), "4"), "0.5"); // i might made a mistake somewhere
?>
You may consider use my function, which makes example above look:
<?php
bc("(sqrt(7 + $1^2) / 4 + $2) % 4 + 0.5", "3", "5");
?>
Code:
<?php
function bc() {
        $functions = 'sqrt';
        // list of | separated functions
        // sqrt refer to bcsqrt etc.
        // function must take exactly 1 argument
        $argv = func_get_args();
        $string = str_replace(' ', '', '('.$argv[0].')');
        $string = preg_replace('/\$([0-9\.]+)/e', '$argv[$1]', $string);
        while (preg_match('/(('.$functions.')?)\(([^\)\(]*)\)/', $string, $match)) {
                while (
                        preg_match('/([0-9\.]+)(\^)([0-9\.]+)/', $match[3], $m) ||
                        preg_match('/([0-9\.]+)([\*\/\%])([0-9\.]+)/', $match[3], $m) ||
                        preg_match('/([0-9\.]+)([\+\-])([0-9\.]+)/', $match[3], $m)
                ) {
                        switch($m[2]) {
                                case '+': $result = bcadd($m[1], $m[3]); break;
                                case '-': $result = bcsub($m[1], $m[3]); break;
                                case '*': $result = bcmul($m[1], $m[3]); break;
                                case '/': $result = bcdiv($m[1], $m[3]); break;
                                case '%': $result = bcmod($m[1], $m[3]); break;
                                case '^': $result = bcpow($m[1], $m[3]); break;
                        }
                        $match[3] = str_replace($m[0], $result, $match[3]);
                }
                if (!empty($match[1]) && function_exists($func = 'bc'.$match[1]))  {
                        $match[3] = $func($match[3]);
                }
                $string = str_replace($match[0], $match[3], $string);
        }
        return $string;
}
?>
Note you must define scale with bcscale().`

[up](https://www.php.net/manual/vote-note.php?id=99130&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99130&page=ref.bc&vote=down "Vote down!")

16


[**_artefact2 at gmail dot com_**](https://www.php.net/manual/en/ref.bc.php#99130) [¶](https://www.php.net/manual/en/ref.bc.php#99130)

**15 years ago**

`Here are some useful functions to convert large hex numbers from and to large decimal ones :
<?php
    public static function bchexdec($hex) {
        if(strlen($hex) == 1) {
            return hexdec($hex);
        } else {
            $remain = substr($hex, 0, -1);
            $last = substr($hex, -1);
            return bcadd(bcmul(16, bchexdec($remain)), hexdec($last));
        }
    }
    public static function bcdechex($dec) {
        $last = bcmod($dec, 16);
        $remain = bcdiv(bcsub($dec, $last), 16);
        if($remain == 0) {
            return dechex($last);
        } else {
            return bcdechex($remain).dechex($last);
        }
    }`

[up](https://www.php.net/manual/vote-note.php?id=25349&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=25349&page=ref.bc&vote=down "Vote down!")

2


[**_pulstar at mail dot com_**](https://www.php.net/manual/en/ref.bc.php#25349) [¶](https://www.php.net/manual/en/ref.bc.php#25349)

**23 years ago**

`A found a little fix to do in my base2dec() function:
The line "if($base<37) $value=strtolower($value);" should be removed if you want to specify another digits for your base conversions. Change it this way:
if(!$digits) {
$digits=digits($base);
if($base<37) {
$value=strtolower($value);
}
}
Another example using these functions is to generate a key for a session, to name temporary files or something else:
srand((double) microtime()*1000000);
$id=uniqid(rand(10,999));
$mykey=dec2base(base2dec($id,16),64);
$mykey is a base64 value, which is a good key for passing thru an URL and also is shorter than a MD5 string (it will be allways 11 chars long). If you need something more secure, just scramble the 64 digits in the digits() function.
Well, I hope you enjoy it.
Regards,
Edemilson Lima`

[up](https://www.php.net/manual/vote-note.php?id=47682&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=47682&page=ref.bc&vote=down "Vote down!")

0


[**_stonehew ut gm a il det com_**](https://www.php.net/manual/en/ref.bc.php#47682) [¶](https://www.php.net/manual/en/ref.bc.php#47682)

**20 years ago**

`Like any other bc function, you can't trust the last couple of digits, but everything else seems to check out.  If you want to use this for anything important, you may want to verify this against other sources of pi before use.  This function calculates 100 decimal places of pi in 329 iterations -- not exactly fast (each iteration calls the factorial function, from below, twice), so I try to avoid calling it more than once.
<?
//arbitrary precision pi approximator
//author tom boothby
//free for any use
function bcpi() {
    $r=2;
    $i=0;
    $or=0;
    while(bccomp($or,$r)) {
        $i++;
        $or=$r;
        $r = bcadd($r,bcdiv(bcmul(bcpow(bcfact($i),2),
                        bcpow(2,$i+1)),bcfact(2*$i+1)));
    }
    return $r;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=47654&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=47654&page=ref.bc&vote=down "Vote down!")

0


[**_stonehew et g m a i l dut com_**](https://www.php.net/manual/en/ref.bc.php#47654) [¶](https://www.php.net/manual/en/ref.bc.php#47654)

**20 years ago**

`I hacked these taylor expansions up to make diagrams for some physics homework.  I don't think you'll be wanting to do any real science with PHP... but what the hell, why not?  I plan to implement either a spigot algorithm or something similar to generate pi in the near future.
<?
// arbitrary precision sin and cosine functions
// author tom boothby
// free for any use
function bcfact($n) {
    $r = $n--;
    while($n>1) $r=bcmul($r,$n--);
    return $r;
}
function bcsin($a) {
    $or= $a;
    $r = bcsub($a,bcdiv(bcpow($a,3),6));
    $i = 2;
    while(bccomp($or,$r)) {
        $or=$r;
        switch($i%2) {
          case 0:  $r = bcadd($r,bcdiv(bcpow($a,$i*2+1),bcfact($i*2+1))); break;
          default: $r = bcsub($r,bcdiv(bcpow($a,$i*2+1),bcfact($i*2+1))); break;
        }
        $i++;
    }
    return $r;
}
function bccos($a) {
    $or= $a;
    $r = bcsub(1,bcdiv(bcpow($a,2),2));
    $i = 2;
    while(bccomp($or,$r)) {
        $or=$r;
        switch($i%2) {
          case 0:  $r = bcadd($r,bcdiv(bcpow($a,$i*2),bcfact($i*2))); break;
          default: $r = bcsub($r,bcdiv(bcpow($a,$i*2),bcfact($i*2))); break;
        }
        $i++;
    }
    return $r;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=42915&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=42915&page=ref.bc&vote=down "Vote down!")

0


[**_robert at scabserver dot com_**](https://www.php.net/manual/en/ref.bc.php#42915) [¶](https://www.php.net/manual/en/ref.bc.php#42915)

**21 years ago**

`I spent some time looking for how to generate a large random number, in the end I've settled for reading directly from /dev/urandom
I know this is a *nix only solution, but I figured that it might come in handy to someone else.
The value $size is the size in bits, it could be simplified greatly if you want the size in bytes, but bits was more helpful to what I needed.
<?php
function bcrand($size)
{
    $filename = "/dev/urandom";
    $handle = fopen($filename, "r");
    $bin_urand = fread($handle, ceil($size/8.0));
    fclose($handle);
    $mask = (($size % 8 < 5) ? '0' : '') . dechex(bindec(str_repeat('1', $size % 8))) . str_repeat('FF', floor($size/8));
    $binmask = pack("H*", $mask);
    $binrand = $binmask & $bin_urand;
    $hexnumber = unpack("H*", $binrand);
    $hexnumber = $hexnumber[''];
    $numlength = strlen($hexnumber);
    $decnumber = 0;
    for($x = 1; $x <= $numlength; $x++)
    {
        $place = $numlength - $x;
        $operand = hexdec(substr($hexnumber,$place,1));
        $exponent = bcpow(16,$x-1);
        $decValue = bcmul($operand, $exponent);
        $decnumber = bcadd($decValue, $decnumber);
    }
    return $decnumber;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=31268&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=31268&page=ref.bc&vote=down "Vote down!")

0


[**_pulstar at mail dot com_**](https://www.php.net/manual/en/ref.bc.php#31268) [¶](https://www.php.net/manual/en/ref.bc.php#31268)

**22 years ago**

`A little comment for the simplified example above: you can do base converting without BCMath functions using only math operators, but you will not able to manage very large values or work with strings to compress or scramble data. If you have BCMath installed in your system it worth use it for this.`

[up](https://www.php.net/manual/vote-note.php?id=29938&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=29938&page=ref.bc&vote=down "Vote down!")

0


[**_oliver at summertime dot net_**](https://www.php.net/manual/en/ref.bc.php#29938) [¶](https://www.php.net/manual/en/ref.bc.php#29938)

**22 years ago**

`A simplier Version of the Script above:
function dec2base($dec, $digits) {
$value = "";
$base  = strlen($digits);
while($dec>$base-1) {
$rest = $dec % $base;
$dec  = $dec / $base;
$value = $digits[$rest].$value;
}
$value = $digits[intval($dec)].$value;
return (string) $value;
}
function base2dec($value, $digits) {
$value = strtoupper($value);
$base  = strlen($digits);
$size  = strlen($value);
$dec   = '0';
for ($loop = 0; $loop<$size; $loop++) {
$element = strpos($digits,$value[$loop]);
$power   = pow($base,$size-$loop-1);
$dec    += $element * $power;
}
return (string) $dec;
}
$digits = "ABCDEFGHJKLMNPQRSTUVWXYZ23456789";
echo dec2base('1000', $digits);`

[up](https://www.php.net/manual/vote-note.php?id=119510&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119510&page=ref.bc&vote=down "Vote down!")

 -1


[**_kmeissen at gmx dot de_**](https://www.php.net/manual/en/ref.bc.php#119510) [¶](https://www.php.net/manual/en/ref.bc.php#119510)

**9 years ago**

`/*
* Computes ln(x) very fast even with high resolution
* uses standard log()-function to optimise convergence of
* ln(1+x) = x - x*x/2 + x*x*x/3 - ...
*
* example:
* bcscale(1000);
* $x = bcln("1000000");
*
* result:
* $x = 13.81551055796427410410794872810618524560660893...
* within 0.9 sec, that are 80 iterations
*
* @author Klaus Meissen, Germany
* @license Public domain
*/
function bcln($value) // value > 0
{
    $m = (string)log($value);
    $x = bcsub(bcdiv($value,bcexp($m)),"1");
    $res = "0";
    $xpow = "1";
    $i=0;
    do
    {
        $i++;
        $xpow = bcmul($xpow,$x);
        $sum = bcdiv($xpow, $i);
        if ($i%2==1)
        {
            $res = bcadd($res, $sum);
        }else{
            $res = bcsub($res, $sum);
        }
    }
    while (bccomp($sum, '0'));
    return bcadd($res,$m);
}`

[up](https://www.php.net/manual/vote-note.php?id=85084&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85084&page=ref.bc&vote=down "Vote down!")

 -2


[**_Charles_**](https://www.php.net/manual/en/ref.bc.php#85084) [¶](https://www.php.net/manual/en/ref.bc.php#85084)

**17 years ago**

`Function to round bc string:
<?php
function bcround($strval, $precision = 0) {
    if (false !== ($pos = strpos($strval, '.')) && (strlen($strval) - $pos - 1) > $precision) {
        $zeros = str_repeat("0", $precision);
        return bcadd($strval, "0.{$zeros}5", $precision);
    } else {
        return $strval;
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=92888&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92888&page=ref.bc&vote=down "Vote down!")

 -2


[**_francois dot barbier at gmail dot com_**](https://www.php.net/manual/en/ref.bc.php#92888) [¶](https://www.php.net/manual/en/ref.bc.php#92888)

**16 years ago**

`As "benjcarson at digitaljunkies dot ca" ( [http://www.php.net/ref.bc.php#23038](http://www.php.net/ref.bc.php#23038)) noted in the first two comments, bcmath doesn't accept exponential notation.
Moreover, you might have other problems if you feed the bcmath functions directly with floating point numbers.
Consider the following example:
<?php
bcscale(1);
$a = 0.8;
$b = 0.7;
var_dump((string) $a);   // string(3) "0.8"
var_dump((string) $b);   // string(3) "0.a"
var_dump(bcadd($a, $b)); // string(3) "1.5"
setLocale(LC_ALL, 'fr_BE.UTF-8');
var_dump((string) $a);   // string(3) "0,8" --> note the comma
var_dump((string) $b);   // string(3) "0,7" --> note the comma
var_dump(bcadd($a, $b)); // string(3) "0.0"
?>
The floating point numbers passed to the bcadd() function are automatically converted to string using the localized decimal separator. However, the bcmath functions always use a full stop, which results in the last result being incorrect.
Below is a function to convert floating point numbers to strings correctly. It takes care of the decimal separator and the exponential notation. It also preserve the precision without drifting away (e.g. 1.0 doesn't become 0.99999...)
<?php
/**
* Convert a number to locale independent string without E notation and without
* loosing precision
*
* @param      int/float/double $fNumber The number to convert.
* @return     string The locale independent converted number.
*/
function bcconv($fNumber)
{
    $sAppend = '';
    $iDecimals = ini_get('precision') - floor(log10(abs($fNumber)));
    if (0 > $iDecimals)
    {
        $fNumber *= pow(10, $iDecimals);
        $sAppend = str_repeat('0', -$iDecimals);
        $iDecimals = 0;
    }
    return number_format($fNumber, $iDecimals, '.', '').$sAppend;
}
?>
Example:
<?php
setLocale(LC_ALL, 'fr_BE.UTF-8'); // decimal separator is now a comma
$precision = ini_get('precision') + 2; // should give 16
bcscale($precision);
$big = pow(10, $precision);
$small = 1 / $big;
var_dump(bcconv($big + $small));               // string(17) "10000000000000000"
var_dump(bcadd($big, $small));                 // string(18) "0.0000000000000000"
var_dump(bcadd(bcconv($big), bcconv($small))); // string(34) "10000000000000000.0000000000000001"
?>
The first result's precision loss is due to PHP's internal floating point numbers' representation.
The second result is wrong because of the localized decimal separator.
Finally, the last result is correct.`

[up](https://www.php.net/manual/vote-note.php?id=25336&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=25336&page=ref.bc&vote=down "Vote down!")

 -2


[**_pulstar at mail dot com_**](https://www.php.net/manual/en/ref.bc.php#25336) [¶](https://www.php.net/manual/en/ref.bc.php#25336)

**23 years ago**

`A good use for BCMath functions:
The functions below can convert a number in any base (from 2 to 256) to its decimal value and vice-versa.
// convert a decimal value to any other base value
function dec2base($dec,$base,$digits=FALSE) {
    if($base<2 or $base>256) die("Invalid Base: ".$base);
    bcscale(0);
    $value="";
    if(!$digits) $digits=digits($base);
    while($dec>$base-1) {
        $rest=bcmod($dec,$base);
        $dec=bcdiv($dec,$base);
        $value=$digits[$rest].$value;
    }
    $value=$digits[intval($dec)].$value;
    return (string) $value;
}
// convert another base value to its decimal value
function base2dec($value,$base,$digits=FALSE) {
    if($base<2 or $base>256) die("Invalid Base: ".$base);
    bcscale(0);
    if($base<37) $value=strtolower($value);
    if(!$digits) $digits=digits($base);
    $size=strlen($value);
    $dec="0";
    for($loop=0;$loop<$size;$loop++) {
        $element=strpos($digits,$value[$loop]);
        $power=bcpow($base,$size-$loop-1);
        $dec=bcadd($dec,bcmul($element,$power));
    }
    return (string) $dec;
}
function digits($base) {
    if($base>64) {
        $digits="";
        for($loop=0;$loop<256;$loop++) {
            $digits.=chr($loop);
        }
    } else {
        $digits ="0123456789abcdefghijklmnopqrstuvwxyz";
        $digits.="ABCDEFGHIJKLMNOPQRSTUVWXYZ-_";
    }
    $digits=substr($digits,0,$base);
    return (string) $digits;
}
The purpose of digits() function above is to supply the characters that will be used as digits for the base you want. NOTE: You can use any characters for that when you convert to another base, but when you convert again to the decimal base, you need to use the same characters or you will get another unexpected result.`

[up](https://www.php.net/manual/vote-note.php?id=113463&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113463&page=ref.bc&vote=down "Vote down!")

 -3


[**_mail at djordjeungar dot com_**](https://www.php.net/manual/en/ref.bc.php#113463) [¶](https://www.php.net/manual/en/ref.bc.php#113463)

**12 years ago**

`Inspired by dawidgarus' implementation, here's my simple bc math helper, it does not support function calls, but supports boolean comparisons and is about ~40% faster.
<?php
function bc() {
    $argv = func_get_args();
    $string = str_replace(' ', '', "({$argv[0]})");
    $operations = array();
    if (strpos($string, '^') !== false) $operations[] = '\^';
    if (strpbrk($string, '*/%') !== false) $operations[] = '[\*\/\%]';
    if (strpbrk($string, '+-') !== false) $operations[] = '[\+\-]';
    if (strpbrk($string, '<>!=') !== false) $operations[] = '<|>|=|<=|==|>=|!=|<>';
    $string = preg_replace('/\$([0-9\.]+)/e', '$argv[$1]', $string);
    while (preg_match('/\(([^\)\(]*)\)/', $string, $match)) {
        foreach ($operations as $operation) {
            if (preg_match("/([+-]{0,1}[0-9\.]+)($operation)([+-]{0,1}[0-9\.]+)/", $match[1], $m)) {
                switch($m[2]) {
                    case '+':  $result = bcadd($m[1], $m[3]); break;
                    case '-':  $result = bcsub($m[1], $m[3]); break;
                    case '*':  $result = bcmul($m[1], $m[3]); break;
                    case '/':  $result = bcdiv($m[1], $m[3]); break;
                    case '%':  $result = bcmod($m[1], $m[3]); break;
                    case '^':  $result = bcpow($m[1], $m[3]); break;
                    case '==':
                    case '=':  $result = bccomp($m[1], $m[3]) == 0; break;
                    case '>':  $result = bccomp($m[1], $m[3]) == 1; break;
                    case '<':  $result = bccomp($m[1], $m[3]) ==-1; break;
                    case '>=': $result = bccomp($m[1], $m[3]) >= 0; break;
                    case '<=': $result = bccomp($m[1], $m[3]) <= 0; break;
                    case '<>':
                    case '!=': $result = bccomp($m[1], $m[3]) != 0; break;
                }
                $match[1] = str_replace($m[0], $result, $match[1]);
            }
        }
        $string = str_replace($match[0], $match[1], $string);
    }
    return $string;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=125284&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125284&page=ref.bc&vote=down "Vote down!")

 -2


[**_eyadbere at gmail dot com_**](https://www.php.net/manual/en/ref.bc.php#125284) [¶](https://www.php.net/manual/en/ref.bc.php#125284)

**5 years ago**

`If your calculations involves input from users don't forget to set a limit on the range and/or the length of the input because very huge numbers requires intensive processing and you might reach a point where your server can't do any further processing`

[up](https://www.php.net/manual/vote-note.php?id=72691&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72691&page=ref.bc&vote=down "Vote down!")

 -4


[**_mgcclx at gmail dot com_**](https://www.php.net/manual/en/ref.bc.php#72691) [¶](https://www.php.net/manual/en/ref.bc.php#72691)

**18 years ago**

`I wrote this function with many BCMath functions. It should be the fastest function in PHP to find the number pi into any precision, my test is it generate 2000 digits after the dot in 8 seconds. I don't think you need anything more than that.
<?php
//bcpi function with Gauss-Legendre algorithm
//by Chao Xu (Mgccl)
function bcpi($precision){
    $limit = ceil(log($precision)/log(2))-1;
    bcscale($precision+6);
    $a = 1;
    $b = bcdiv(1,bcsqrt(2));
    $t = 1/4;
    $p = 1;
    while($n < $limit){
        $x = bcdiv(bcadd($a,$b),2);
        $y = bcsqrt(bcmul($a, $b));
        $t = bcsub($t, bcmul($p,bcpow(bcsub($a,$x),2)));
        $a = $x;
        $b = $y;
        $p = bcmul(2,$p);
        ++$n;
    }
    return bcdiv(bcpow(bcadd($a, $b),2),bcmul(4,$t),$precision);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=73522&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73522&page=ref.bc&vote=down "Vote down!")

 -3


[**_udochen at gmail dot com_**](https://www.php.net/manual/en/ref.bc.php#73522) [¶](https://www.php.net/manual/en/ref.bc.php#73522)

**18 years ago**

`Code below implements standard rounding on 5 or higer round up, else don't round.  There wasn't a round function for the BC functions, so here is a simple one that works. Same args as round, except takes strings and returns a string for more BC operations.
----------------
function roundbc($x, $p) {
     $x = trim($x);
     $data = explode(".",$x);
     if(substr($data[1],$p,1) >= "5") {
           //generate the add string.
           $i=0;
           $addString = "5";
           while($i < $p) {
               $addString = "0" . $addString;
               $i++;
           }//end while.
           $addString = "." . $addString;
           //now add the addString to the original fraction.
           $sum = bcadd($data[0] . "." . $data   [1],$addString,$p+1);
           //explode the result.
           $sumData = explode(".",$sum);
           //now, return the correct precision on the rounded number.
           return $sumData[0] . "." . substr($sumData[1],0,$p);
      } else {
           //don't round the value and return the orignal to the desired
           //precision or less.
           return $data[0] . "." . substr($data[1],0,$p);
      }//end if/else.
}//end roundbc.`

[up](https://www.php.net/manual/vote-note.php?id=46965&page=ref.bc&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=46965&page=ref.bc&vote=down "Vote down!")

 -3


[**_Diabolos at GMail dot com_**](https://www.php.net/manual/en/ref.bc.php#46965) [¶](https://www.php.net/manual/en/ref.bc.php#46965)

**20 years ago**

`Here's a function to compute the natural exponential function in arbitrary precision using the basic bcMath arithmetic operations.
EXAMPLE:
To compute the exponential function of 1.7 to 36 decimals:
$y = bcExp("1.7", 36);
The result:
4.331733759839529271053448625299468628
would be returned in variable $y
NOTE:
In practice, the last couple of digits may be inaccurate due to small rounding errors.  If you require a specific degree of precision, always compute 3-4 decimals beyond the required precision.
The program code for the natural exponential function is:
******************************************
Function bcExp($xArg, $NumDecimals)
{
$x = Trim($xArg);
$PrevSum  = $x - 1;
$CurrTerm = 1;
$CurrSum  = bcAdd("1", $x, $NumDecimals);
$n        = 1;
While (bcComp($CurrSum, $PrevSum, $NumDecimals))
{
$PrevSum  = $CurrSum;
$CurrTerm = bcDiv(bcMul($CurrTerm, $x, $NumDecimals), $n + 1, $NumDecimals);
$CurrSum  = bcAdd($CurrSum, $CurrTerm, $NumDecimals);
$n++;
}
Return $CurrSum;
}`

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.bc&repo=en&redirect=https://www.php.net/manual/en/ref.bc.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google