---
url: https://www.php.net/manual/en/language.operators.string.php
scraped_at: 2025-10-20T02:37:54.294Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## String Operators [¶](https://www.php.net/manual/en/language.operators.string.php\#language.operators.string)

There are two [string](https://www.php.net/manual/en/language.types.string.php) operators. The first is the
concatenation operator ('.'), which returns the concatenation of its
right and left arguments. The second is the concatenating assignment
operator (' `.=`'), which appends the argument on the right side to
the argument on the left side. Please read [Assignment\\
Operators](https://www.php.net/manual/en/language.operators.assignment.php) for more information.


**Example #1 String Concatenating**

`<?php
$a = "Hello ";
$b = $a . "World!"; // now $b contains "Hello World!"
var_dump($b);
$a = "Hello ";
$a .= "World!";     // now $a contains "Hello World!"
var_dump($a);
?>`

Run code

### See Also

- [String type](https://www.php.net/manual/en/language.types.string.php)
- [String functions](https://www.php.net/manual/en/ref.strings.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/operators/string.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.operators.string%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.string&repo=en&redirect=https://www.php.net/manual/en/language.operators.string.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=110937&page=language.operators.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110937&page=language.operators.string&vote=down "Vote down!")

277


[**_K.Alex_**](https://www.php.net/manual/en/language.operators.string.php#110937) [¶](https://www.php.net/manual/en/language.operators.string.php#110937)

**12 years ago**

`As for me, curly braces serve good substitution for concatenation, and they are quicker to type and code looks cleaner. Remember to use double quotes (" ") as their content is parced by php, because in single quotes (' ') you'll get litaral name of variable provided:
<?php
$a = '12345';
// This works:
echo "qwe{$a}rty"; // qwe12345rty, using braces
echo "qwe" . $a . "rty"; // qwe12345rty, concatenation used
// Does not work:
echo 'qwe{$a}rty'; // qwe{$a}rty, single quotes are not parsed
echo "qwe$arty"; // qwe, because $a became $arty, which is undefined
?>`

[up](https://www.php.net/manual/vote-note.php?id=41950&page=language.operators.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=41950&page=language.operators.string&vote=down "Vote down!")

164


[**_anders dot benke at telia dot com_**](https://www.php.net/manual/en/language.operators.string.php#41950) [¶](https://www.php.net/manual/en/language.operators.string.php#41950)

**21 years ago**

`A word of caution - the dot operator has the same precedence as + and -, which can yield unexpected results.
Example:
<php
$var = 3;
echo "Result: " . $var + 3;
?>
The above will print out "3" instead of "Result: 6", since first the string "Result3" is created and this is then added to 3 yielding 3, non-empty non-numeric strings being converted to 0.
To print "Result: 6", use parantheses to alter precedence:
<php
$var = 3;
echo "Result: " . ($var + 3);
?>`

[up](https://www.php.net/manual/vote-note.php?id=60035&page=language.operators.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60035&page=language.operators.string&vote=down "Vote down!")

114


[**_Stephen Clay_**](https://www.php.net/manual/en/language.operators.string.php#60035) [¶](https://www.php.net/manual/en/language.operators.string.php#60035)

**19 years ago**

`<?php
"{$str1}{$str2}{$str3}"; // one concat = fast
$str1. $str2. $str3;   // two concats = slow
?>
Use double quotes to concat more than two strings instead of multiple '.' operators.  PHP is forced to re-concatenate with every '.' operator.`

[up](https://www.php.net/manual/vote-note.php?id=88827&page=language.operators.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88827&page=language.operators.string&vote=down "Vote down!")

92


[**_hexidecimalgadget at hotmail dot com_**](https://www.php.net/manual/en/language.operators.string.php#88827) [¶](https://www.php.net/manual/en/language.operators.string.php#88827)

**16 years ago**

`If you attempt to add numbers with a concatenation operator, your result will be the result of those numbers as strings.
<?php
echo "thr"."ee";           //prints the string "three"
echo "twe" . "lve";        //prints the string "twelve"
echo 1 . 2;                //prints the string "12"
echo 1.2;                  //prints the number 1.2
echo 1+2;                  //prints the number 3
?>`

[up](https://www.php.net/manual/vote-note.php?id=127624&page=language.operators.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127624&page=language.operators.string&vote=down "Vote down!")

11


[**_biziclop_**](https://www.php.net/manual/en/language.operators.string.php#127624) [¶](https://www.php.net/manual/en/language.operators.string.php#127624)

**3 years ago**

`Some bitwise operators (the and, or, xor and not operators: & | ^ ~ ) also work with strings too since PHP4, so you don't have to loop through strings and do chr(ord($s[i])) like things.
See the documentation of the bitwise operators: [https://www.php.net/operators.bitwise](https://www.php.net/operators.bitwise)
<?php var_dump(
('23456787654' ^ 'zVXYYhoXDYP'), // 'Hello_World'
('(!($)^!)@$@' | '@ddhfIvn2H$'), // 'hello_world'
('{}~|o!Wo{|}' & 'Lgmno|Wovmf'), // 'Hello World'
(~'<0-14)(98'  &   '}}}}}}}}}')  // 'AMPLITUDE'
); ?>
Live demo: [https://3v4l.org/MnFeb](https://3v4l.org/MnFeb)`

[up](https://www.php.net/manual/vote-note.php?id=85358&page=language.operators.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85358&page=language.operators.string&vote=down "Vote down!")

44


[**_mariusads::at::helpedia.com_**](https://www.php.net/manual/en/language.operators.string.php#85358) [¶](https://www.php.net/manual/en/language.operators.string.php#85358)

**17 years ago**

`Be careful so that you don't type "." instead of ";" at the end of a line.
It took me more than 30 minutes to debug a long script because of something like this:
<?
echo 'a'.
$c = 'x';
echo 'b';
echo 'c';
?>
The output is "axbc", because of the dot on the first line.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.string&repo=en&redirect=https://www.php.net/manual/en/language.operators.string.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google