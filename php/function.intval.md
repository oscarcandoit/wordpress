---
url: https://www.php.net/manual/en/function.intval.php
scraped_at: 2025-10-20T02:59:21.219Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# intval

(PHP 4, PHP 5, PHP 7, PHP 8)

intval — Get the integer value of a variable

### Description [¶](https://www.php.net/manual/en/function.intval.php\#refsect1-function.intval-description)

**intval**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$value`, [int](https://www.php.net/manual/en/language.types.integer.php) `$base` = 10): [int](https://www.php.net/manual/en/language.types.integer.php)

Returns the [int](https://www.php.net/manual/en/language.types.integer.php) value of `value`,
using the specified `base` for the conversion
(the default is base 10). **intval()** should not be used
on objects, as doing so will emit an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** level
error and return 1.


### Parameters [¶](https://www.php.net/manual/en/function.intval.php\#refsect1-function.intval-parameters)

`value`

The scalar value being converted to an integer


`base`

The base for the conversion


> **Note**:
>
>
> If `base` is 0, the base used is determined
> by the format of `value`:
>
>
> - if string includes a "0x" (or "0X") prefix, the base is taken
>    as 16 (hex); otherwise,
>
> - if string starts with a "0b" (or "0B"), the base is taken
>    as 2 (binary); otherwise,
>
> - if string starts with "0", the base is taken as 8 (octal);
>    otherwise,
>
> - the base is taken as 10 (decimal).

### Return Values [¶](https://www.php.net/manual/en/function.intval.php\#refsect1-function.intval-returnvalues)

The integer value of `value` on success, or 0 on
failure. Empty arrays return 0, non-empty arrays return 1.


The maximum value depends on the system. 32 bit systems have a
maximum signed integer range of -2147483648 to 2147483647. So for example
on such a system, `intval('1000000000000')` will return
2147483647\. The maximum signed integer value for 64 bit systems is
9223372036854775807.


Strings will most likely return 0 although this depends on the
leftmost characters of the string. The common rules of
[integer casting](https://www.php.net/manual/en/language.types.integer.php#language.types.integer.casting)
apply.


### Changelog [¶](https://www.php.net/manual/en/function.intval.php\#refsect1-function.intval-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | The error level when converting from object was changed from **`[E\_NOTICE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-notice)`** to **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**. |

### Examples [¶](https://www.php.net/manual/en/function.intval.php\#refsect1-function.intval-examples)

**Example #1 **intval()** examples**

The following examples are based on a 64 bit system.


`<?php
echo intval(42), PHP_EOL;                      // 42
echo intval(4.7), PHP_EOL;                     // 4
echo intval('42'), PHP_EOL;                    // 42
echo intval('+42'), PHP_EOL;                   // 42
echo intval('-42'), PHP_EOL;                   // -42
echo intval(042), PHP_EOL;                     // 34
echo intval('042'), PHP_EOL;                   // 42
echo intval(1e10), PHP_EOL;                    // 10000000000
echo intval('1e10'), PHP_EOL;                  // 10000000000
echo intval(0x1A), PHP_EOL;                    // 26
echo intval('0x1A'), PHP_EOL;                  // 0
echo intval('0x1A', 0), PHP_EOL;               // 26
echo intval(42000000), PHP_EOL;                // 42000000
echo intval(420000000000000000000), PHP_EOL;   // -4275113695319687168
echo intval('420000000000000000000'), PHP_EOL; // 9223372036854775807
echo intval(42, 8), PHP_EOL;                   // 42
echo intval('42', 8), PHP_EOL;                 // 34
echo intval(array()), PHP_EOL;                 // 0
echo intval(array('foo', 'bar')), PHP_EOL;     // 1
echo intval(false), PHP_EOL;                   // 0
echo intval(true), PHP_EOL;                    // 1
?>`

Run code

### Notes [¶](https://www.php.net/manual/en/function.intval.php\#refsect1-function.intval-notes)

> **Note**:
>
>
> The `base` parameter has no effect unless the
> `value` parameter is a string.

### See Also [¶](https://www.php.net/manual/en/function.intval.php\#refsect1-function.intval-seealso)

- [boolval()](https://www.php.net/manual/en/function.boolval.php) \- Get the boolean value of a variable
- [floatval()](https://www.php.net/manual/en/function.floatval.php) \- Get float value of a variable
- [strval()](https://www.php.net/manual/en/function.strval.php) \- Get string value of a variable
- [settype()](https://www.php.net/manual/en/function.settype.php) \- Set the type of a variable
- [is\_numeric()](https://www.php.net/manual/en/function.is-numeric.php) \- Finds whether a variable is a number or a numeric string
- [Type juggling](https://www.php.net/manual/en/language.types.type-juggling.php)
- [BCMath Arbitrary Precision Mathematics Functions](https://www.php.net/manual/en/ref.bc.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/functions/intval.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.intval%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.intval&repo=en&redirect=https://www.php.net/manual/en/function.intval.php)

### User Contributed Notes 16 notes

[up](https://www.php.net/manual/vote-note.php?id=106478&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106478&page=function.intval&vote=down "Vote down!")

367


[**_Ken_**](https://www.php.net/manual/en/function.intval.php#106478) [¶](https://www.php.net/manual/en/function.intval.php#106478)

**13 years ago**

`Not mentioned elsewhere: intval(NULL) also returns 0.`

[up](https://www.php.net/manual/vote-note.php?id=120543&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120543&page=function.intval&vote=down "Vote down!")

78


[**_leon at leonidasjp dot nl_**](https://www.php.net/manual/en/function.intval.php#120543) [¶](https://www.php.net/manual/en/function.intval.php#120543)

**8 years ago**

`It seems intval is interpreting valid numeric strings differently between PHP 5.6 and 7.0 on one hand, and PHP 7.1 on the other hand.
<?php
echo intval('1e5');
?>
will return 1 on PHP 5.6 and PHP 7.0,
but it will return 100000 on PHP 7.1.`

[up](https://www.php.net/manual/vote-note.php?id=101439&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101439&page=function.intval&vote=down "Vote down!")

155


[**_winbill at hotmail dot com_**](https://www.php.net/manual/en/function.intval.php#101439) [¶](https://www.php.net/manual/en/function.intval.php#101439)

**14 years ago**

`Be careful :
<?php
$n="19.99";
print intval($n*100); // prints 1998
print intval(strval($n*100)); // prints 1999
?>`

[up](https://www.php.net/manual/vote-note.php?id=7707&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=7707&page=function.intval&vote=down "Vote down!")

53


[**_zak at php dot net_**](https://www.php.net/manual/en/function.intval.php#7707) [¶](https://www.php.net/manual/en/function.intval.php#7707)

**25 years ago**

`intval converts doubles to integers by truncating the fractional component of the number.
When dealing with some values, this can give odd results.  Consider the following:
print intval ((0.1 + 0.7) * 10);
This will most likely print out 7, instead of the expected value of 8.
For more information, see the section on floating point numbers in the PHP manual ( [http://www.php.net/manual/language.types.double.php](http://www.php.net/manual/language.types.double.php))
Also note that if you try to convert a string to an integer, the result is often 0.
However, if the leftmost character of a string looks like a valid numeric value, then PHP will keep reading the string until a character that is not valid in a number is encountered.
For example:
"101 Dalmations" will convert to 101
"$1,000,000" will convert to 0 (the 1st character is not a valid start for a number
"80,000 leagues ..." will convert to 80
"1.4e98 microLenats were generated when..." will convert to 1.4e98
Also note that only decimal base numbers are recognized in strings.
"099" will convert to 99, while "0x99" will convert to 0.
One additional note on the behavior of intval.  If you specify the base argument, the var argument should be a string - otherwise the base will not be applied.
For Example:
print intval (77, 8);   // Prints 77
print intval ('77', 8); // Prints 63`

[up](https://www.php.net/manual/vote-note.php?id=60793&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60793&page=function.intval&vote=down "Vote down!")

38


[**_Ben Laurienti_**](https://www.php.net/manual/en/function.intval.php#60793) [¶](https://www.php.net/manual/en/function.intval.php#60793)

**19 years ago**

`You guys are going to love this.  I found something that I found quite disturbing.
$test1 = intVal(1999);
$amount = 19.99 * 100;
$test2 = intVal($amount);
$test3 = intVal("$amount");
echo $test1 . "<br />\n";
echo $test2 . "<br />\n";
echo $test3 . "<br />\n";
expected output:
1999
1999
1999
actual output
1999
1998
1999
Appears to be a floating point issue, but the number 1999 is the only number that I was able to get to do this.  19.99 is the price of many things, and for our purpose we must pass it as 1999 instead of 19.99.`

[up](https://www.php.net/manual/vote-note.php?id=91649&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91649&page=function.intval&vote=down "Vote down!")

36


[**_spoon\_reloaded at gmail dot com_**](https://www.php.net/manual/en/function.intval.php#91649) [¶](https://www.php.net/manual/en/function.intval.php#91649)

**16 years ago**

`Here is a really useful undocumented feature:
You can have it automatically deduce the base of the number from the prefix of the string using the same syntax as integer literals in PHP ("0x" for hexadecimal, "0" for octal, non-"0" for decimal) by passing a base of 0 to intval():
<?php
echo intval("0x1a", 0), "\n"; // hex; prints "26"
echo intval("057", 0), "\n"; // octal; prints "47"
echo intval("42", 0), "\n"; // decimal; prints "42"
?>`

[up](https://www.php.net/manual/vote-note.php?id=39681&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=39681&page=function.intval&vote=down "Vote down!")

11


[**_tuxedobob at mac dot com_**](https://www.php.net/manual/en/function.intval.php#39681) [¶](https://www.php.net/manual/en/function.intval.php#39681)

**21 years ago**

`Sometimes intval just won't cut it. For example if you want to use an unsigned 32-bit int and need all 32 bits. Recently, I wrote a little script that took and integer and converted it to an IP address. After realizing I couldn't just mod the whole thing, since the sign bit throws it off (and compensating for that), we ran into a problem where if it was entered into a form, the value somehow wasn't converted to an integer properly, at least not implicitly. The solution for this, and the way I recommend converting a string to an integer, is:
$num = $num + 0;
and PHP will leave your number alone; it'll just know it's a number. Such is the fun of a loosely-typed language. :)`

[up](https://www.php.net/manual/vote-note.php?id=111582&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111582&page=function.intval&vote=down "Vote down!")

15


[**_espertalhao04 at hotmail dot com_**](https://www.php.net/manual/en/function.intval.php#111582) [¶](https://www.php.net/manual/en/function.intval.php#111582)

**12 years ago**

`if you want to take a number from a string, no matter what it may contain, here is a good solution:
<?php
function int($s){return(int)preg_replace('/[^\-\d]*(\-?\d*).*/','$1',$s);}
echo int('j18ugj9hu0gj5hg');
//output: 18
?>
this example returns an int, so it will follow the int rules, and has support for negative values.
<?php
function int($s){return($a=preg_replace('/[^\-\d]*(\-?\d*).*/','$1',$s))?$a:'0';}
echo int('j-1809809808908099878758765ugj9hu0gj5hg');
//output: -1809809808908099878758765
?>
this one returns a string with just the numeric value.
it also supports negative values.
the latter is better when you have a 32 bit system and you want a huge int that is higher than PHP_MAX_INT.`

[up](https://www.php.net/manual/vote-note.php?id=122651&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122651&page=function.intval&vote=down "Vote down!")

6


[**_Anthony_**](https://www.php.net/manual/en/function.intval.php#122651) [¶](https://www.php.net/manual/en/function.intval.php#122651)

**7 years ago**

`The binary notation is NOT supported until php7.2
<?php
                         // PHP <7.2 | PHP >=7.2
echo intval(0b11);       //    3     |     3
echo intval(-0b11);      //   -3     |    -3
echo intval('0b11');     //    0     |     0
echo intval('-0b11');    //    0     |     0
echo intval('0b11', 0);  //    0     |     3
echo intval('-0b11', 0); //    0     |    -3
?>`

[up](https://www.php.net/manual/vote-note.php?id=125013&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125013&page=function.intval&vote=down "Vote down!")

5


[**_Anony Moose_**](https://www.php.net/manual/en/function.intval.php#125013) [¶](https://www.php.net/manual/en/function.intval.php#125013)

**5 years ago**

`As a warning, do not use this function alone for input validation.
Vulnerable example:
<?php
if(isset($_GET['id']) && intval($_GET['id']) > 0){
    echo $id;
}
?>
The following requests would pass this filter:
/page.php?id=10
/page.php?id=10oops
/page.php?id=10<script>alert(1)</script>
/page.php?id=1' OR '1'='1
/page.php?id[]=<script>alert(1)</script>
Instead use the is_numeric() function for integer validation:
<?php
echo intval("10oops"); // 10
echo is_numeric("10oops");  // false
?>
Secure example:
<?php
if(isset($_GET['id']) && is_numeric($_GET['id']) && intval($_GET['id']) > 0){
    echo $id;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=124710&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124710&page=function.intval&vote=down "Vote down!")

2


[**_Anonymous_**](https://www.php.net/manual/en/function.intval.php#124710) [¶](https://www.php.net/manual/en/function.intval.php#124710)

**5 years ago**

`PHP 7.2
$test = intval(150.20*100); //15019
$test2 = intval(15020); //15020
$test3 = intval(15020.0); //15020
$test4 = 150.20*100; //15020.0`

[up](https://www.php.net/manual/vote-note.php?id=101583&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101583&page=function.intval&vote=down "Vote down!")

4


[**_yves_**](https://www.php.net/manual/en/function.intval.php#101583) [¶](https://www.php.net/manual/en/function.intval.php#101583)

**14 years ago**

`The behaviour of intval() is interesting when supplying a base, and you better check your intval base-based expressions, as it is counter-intuitive.
As the example shows
<?php
intval('42', 8); // => 34
intval(42, 8);   // => 42 !
?>
PHP considers the 42 as being already an integer, and doesn't apply any conversion. And supplying
<?php
intval(49, 8);  // => 49 !
?>
produces no error and no warning.`

[up](https://www.php.net/manual/vote-note.php?id=112039&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112039&page=function.intval&vote=down "Vote down!")

4


[**_pfreet at gmail dot com_**](https://www.php.net/manual/en/function.intval.php#112039) [¶](https://www.php.net/manual/en/function.intval.php#112039)

**12 years ago**

`Do not use intval() when you really want round(). This is due to how PHP handles precision.
echo number_format(8.20*100, 20), "<br />";
echo intval(8.20*100), "<br />";
echo floor(8.20*100), "<br />";
echo round(8.20*100), "<br />";
819.99999999999988631316
819
819
820`

[up](https://www.php.net/manual/vote-note.php?id=117624&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117624&page=function.intval&vote=down "Vote down!")

1


[**_taylorsarrafian at gmail dot com_**](https://www.php.net/manual/en/function.intval.php#117624) [¶](https://www.php.net/manual/en/function.intval.php#117624)

**10 years ago**

`beware:
<?php
// observe the following
echo intval( strval( -0.0001 ) ); // 0
echo intval( strval( -0.00001 ) ); // -1
// this is because
echo strval( -0.0001 ); // -.0001
echo strval( -0.00001 ); // -1.0E-5
// thus beware when using
function trunc2_bad( $n ) {
      return intval( strval( $n * 100 ) / 100 );
}
// use this instead
function trunc2_good( $n ) {
      return intval( floatval( strval( $n * 100 )  ) / 100 );
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=62680&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62680&page=function.intval&vote=down "Vote down!")

2


[**_mkamerma at science dot uva dot nl_**](https://www.php.net/manual/en/function.intval.php#62680) [¶](https://www.php.net/manual/en/function.intval.php#62680)

**19 years ago**

`As addendum, the "if ($int > 0)" check in the encode function is redundant. It doesn't do anything bad to keep it in since it will always be true when reaching that point, but it's a meaningless conditional this way. It's a remnant from when I tried to write the function in terms of bitshifts, which could lead to negative ints when shifting if the 32nd bit was set (instead of always padding with 0's when using >> it pads with 1's leading to negative ints).`

[up](https://www.php.net/manual/vote-note.php?id=129193&page=function.intval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129193&page=function.intval&vote=down "Vote down!")

0


[**_Denes Kellner_**](https://www.php.net/manual/en/function.intval.php#129193) [¶](https://www.php.net/manual/en/function.intval.php#129193)

**1 year ago**

`Warning: intval() parses scientific notation, like "12.3e7".
This comes out of the blue when you use intval() to cut the first integer value from a string; at first glance there's nothing wrong with it, if you have "123.jeff" it will give you 123, but in the rare case of parsing something that has a second segment with a hex number, you can easily run into this. (Let's not start the "why would you parse a string like that" argument.)
So if you're not prepared, these results may surprise you:
    intval("123.ee-2") - gives you 123
    intval("123.e2-e") - gives you 12300
    intval("123.a2-e") - gives you 123
    intval("123.e-22") - gives you 0
    intval("123.e-a2") - gives you 123
    intval("123.e-2a") - gives you 1
    intval("123.2e2a") - gives you 12320
    intval("123.22e2") - gives you 12322
    intval("123.22ea") - gives you 123
Again, this is somewhat expected behaviour once you know that scientific notation is interpreted by it. But it looks like a less-than-widely known fact and I only faced this issue after 20+ years of php.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.intval&repo=en&redirect=https://www.php.net/manual/en/function.intval.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google