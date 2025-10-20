---
url: https://www.php.net/manual/en/ref.gmp.php
scraped_at: 2025-10-20T02:39:11.794Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# GMP Functions [¶](https://www.php.net/manual/en/ref.gmp.php\#ref.gmp)

## See Also [¶](https://www.php.net/manual/en/ref.gmp.php\#gmp.seealso)

More mathematical functions can be found in the
[Mathematical Extensions](https://www.php.net/manual/en/refs.math.php) section


## Table of Contents [¶](https://www.php.net/manual/en/ref.gmp.php\#ref.gmp)

- [gmp\_abs](https://www.php.net/manual/en/function.gmp-abs.php) — Absolute value
- [gmp\_add](https://www.php.net/manual/en/function.gmp-add.php) — Add numbers
- [gmp\_and](https://www.php.net/manual/en/function.gmp-and.php) — Bitwise AND
- [gmp\_binomial](https://www.php.net/manual/en/function.gmp-binomial.php) — Calculates binomial coefficient
- [gmp\_clrbit](https://www.php.net/manual/en/function.gmp-clrbit.php) — Clear bit
- [gmp\_cmp](https://www.php.net/manual/en/function.gmp-cmp.php) — Compare numbers
- [gmp\_com](https://www.php.net/manual/en/function.gmp-com.php) — Calculates one's complement
- [gmp\_div](https://www.php.net/manual/en/function.gmp-div.php) — Alias of gmp\_div\_q
- [gmp\_div\_q](https://www.php.net/manual/en/function.gmp-div-q.php) — Divide numbers
- [gmp\_div\_qr](https://www.php.net/manual/en/function.gmp-div-qr.php) — Divide numbers and get quotient and remainder
- [gmp\_div\_r](https://www.php.net/manual/en/function.gmp-div-r.php) — Remainder of the division of numbers
- [gmp\_divexact](https://www.php.net/manual/en/function.gmp-divexact.php) — Exact division of numbers
- [gmp\_export](https://www.php.net/manual/en/function.gmp-export.php) — Export to a binary string
- [gmp\_fact](https://www.php.net/manual/en/function.gmp-fact.php) — Factorial
- [gmp\_gcd](https://www.php.net/manual/en/function.gmp-gcd.php) — Calculate GCD
- [gmp\_gcdext](https://www.php.net/manual/en/function.gmp-gcdext.php) — Calculate GCD and multipliers
- [gmp\_hamdist](https://www.php.net/manual/en/function.gmp-hamdist.php) — Hamming distance
- [gmp\_import](https://www.php.net/manual/en/function.gmp-import.php) — Import from a binary string
- [gmp\_init](https://www.php.net/manual/en/function.gmp-init.php) — Create GMP number
- [gmp\_intval](https://www.php.net/manual/en/function.gmp-intval.php) — Convert GMP number to integer
- [gmp\_invert](https://www.php.net/manual/en/function.gmp-invert.php) — Inverse by modulo
- [gmp\_jacobi](https://www.php.net/manual/en/function.gmp-jacobi.php) — Jacobi symbol
- [gmp\_kronecker](https://www.php.net/manual/en/function.gmp-kronecker.php) — Kronecker symbol
- [gmp\_lcm](https://www.php.net/manual/en/function.gmp-lcm.php) — Calculate LCM
- [gmp\_legendre](https://www.php.net/manual/en/function.gmp-legendre.php) — Legendre symbol
- [gmp\_mod](https://www.php.net/manual/en/function.gmp-mod.php) — Modulo operation
- [gmp\_mul](https://www.php.net/manual/en/function.gmp-mul.php) — Multiply numbers
- [gmp\_neg](https://www.php.net/manual/en/function.gmp-neg.php) — Negate number
- [gmp\_nextprime](https://www.php.net/manual/en/function.gmp-nextprime.php) — Find next prime number
- [gmp\_or](https://www.php.net/manual/en/function.gmp-or.php) — Bitwise OR
- [gmp\_perfect\_power](https://www.php.net/manual/en/function.gmp-perfect-power.php) — Perfect power check
- [gmp\_perfect\_square](https://www.php.net/manual/en/function.gmp-perfect-square.php) — Perfect square check
- [gmp\_popcount](https://www.php.net/manual/en/function.gmp-popcount.php) — Population count
- [gmp\_pow](https://www.php.net/manual/en/function.gmp-pow.php) — Raise number into power
- [gmp\_powm](https://www.php.net/manual/en/function.gmp-powm.php) — Raise number into power with modulo
- [gmp\_prob\_prime](https://www.php.net/manual/en/function.gmp-prob-prime.php) — Check if number is "probably prime"
- [gmp\_random](https://www.php.net/manual/en/function.gmp-random.php) — Random number
- [gmp\_random\_bits](https://www.php.net/manual/en/function.gmp-random-bits.php) — Random number
- [gmp\_random\_range](https://www.php.net/manual/en/function.gmp-random-range.php) — Get a uniformly selected integer
- [gmp\_random\_seed](https://www.php.net/manual/en/function.gmp-random-seed.php) — Sets the RNG seed
- [gmp\_root](https://www.php.net/manual/en/function.gmp-root.php) — Take the integer part of nth root
- [gmp\_rootrem](https://www.php.net/manual/en/function.gmp-rootrem.php) — Take the integer part and remainder of nth root
- [gmp\_scan0](https://www.php.net/manual/en/function.gmp-scan0.php) — Scan for 0
- [gmp\_scan1](https://www.php.net/manual/en/function.gmp-scan1.php) — Scan for 1
- [gmp\_setbit](https://www.php.net/manual/en/function.gmp-setbit.php) — Set bit
- [gmp\_sign](https://www.php.net/manual/en/function.gmp-sign.php) — Sign of number
- [gmp\_sqrt](https://www.php.net/manual/en/function.gmp-sqrt.php) — Calculate square root
- [gmp\_sqrtrem](https://www.php.net/manual/en/function.gmp-sqrtrem.php) — Square root with remainder
- [gmp\_strval](https://www.php.net/manual/en/function.gmp-strval.php) — Convert GMP number to string
- [gmp\_sub](https://www.php.net/manual/en/function.gmp-sub.php) — Subtract numbers
- [gmp\_testbit](https://www.php.net/manual/en/function.gmp-testbit.php) — Tests if a bit is set
- [gmp\_xor](https://www.php.net/manual/en/function.gmp-xor.php) — Bitwise XOR

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/gmp/reference.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fref.gmp%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.gmp&repo=en&redirect=https://www.php.net/manual/en/ref.gmp.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=99788&page=ref.gmp&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99788&page=ref.gmp&vote=down "Vote down!")

5


[**_Nitrogen_**](https://www.php.net/manual/en/ref.gmp.php#99788) [¶](https://www.php.net/manual/en/ref.gmp.php#99788)

**15 years ago**

`I made a function that can be used for converting numbers to any base you wish.. instead of returning a string of pre-defined index of characters (i.e. 0-9a-z) you could simply make your own of any length using the array of indexes it returns.
I looked around and didn't see anybody made one, I needed one for a simple compression algorithm with only numbers, I've not actually made it yet but this was an initial idea.
<?php
// ConvertBase function explained:
// we add an array item $Input%$Base floored and divide $Input by $Base floored.
// repeat until $Input is no longer above 0.
function ConvertBase($Input,$Base=10) {
$Input=gmp_init($Input);
$Result=array();
for($i=0;$i<1||gmp_sign($Input)==1;$i++) {
    $Result[]=gmp_intval(gmp_mod($Input,$Base));
    $Input=gmp_div_q($Input,$Base);
}
$Result=array_reverse($Result);
return($Result);
}
// an example how gmp_strval($.., 36); could be achieved:
// the funny emergency number from The IT Crowd
// (leading zeroes aren't liked in gmp_init though)
$Input = '1189998819991197253';
// our example 36 characters used in gmp_strval($.., 36);
$Chars = '0123456789abcdefghijklmnopqrstuvwxyz';
// count the $Chars so they're all used
// or use your own number less than the length of $Chars
$Base = strlen($Chars);
// perform
$Result = ConvertBase($Input,$Base);
// replace the resulting index with the corrosponding characters of the index in $Chars
for($i=0;$i<count($Result);$i++)
$Result[$i]=$Chars{$Result[$i]};
// compare
printf("gmp_strval:  %s\r\n",gmp_strval($Input,36));
printf("BaseConvert: %s\r\n",implode($Result));
/* OUTPUT:
gmp_strval:  91h7dixfq6h1
BaseConvert: 91h7dixfq6h1
*/
?>
The example shows a familiar result of course, but the idea of this function was so that you can use whatever base you wish, and display entirely your own output to represent any number of choice.
Also, for those who wish to do bitwise shifting, it's quite simple.. to shift left, just multiply the number by pow(2,x), and to shift right, divide by pow(2,x).
<?php
function gmp_shiftl($x,$n) { // shift left
return(gmp_mul($x,gmp_pow(2,$n)));
}
function gmp_shiftr($x,$n) { // shift right
return(gmp_div($x,gmp_pow(2,$n)));
}
?>
Have fun,
Nitrogen.`

[up](https://www.php.net/manual/vote-note.php?id=40106&page=ref.gmp&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=40106&page=ref.gmp&vote=down "Vote down!")

1


[**_richard-slater.co.uk_**](https://www.php.net/manual/en/ref.gmp.php#40106) [¶](https://www.php.net/manual/en/ref.gmp.php#40106)

**21 years ago**

`For those (like me) who are trying to do bit masking with very large numbers, here is a useful function to do the work for you.
<?php
function isBitSet($bitMask, $bitMap)
{
    return (bool) gmp_intval(gmp_div(gmp_and($bitMask, $bitMap),$bitMask));
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.gmp&repo=en&redirect=https://www.php.net/manual/en/ref.gmp.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google