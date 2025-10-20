---
url: https://www.php.net/manual/en/function.strval.php
scraped_at: 2025-10-20T02:42:12.366Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# strval

(PHP 4, PHP 5, PHP 7, PHP 8)

strval — Get string value of a variable

### Description [¶](https://www.php.net/manual/en/function.strval.php\#refsect1-function.strval-description)

**strval**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$value`): [string](https://www.php.net/manual/en/language.types.string.php)

Get the string value of a variable.
See the documentation on [string](https://www.php.net/manual/en/language.types.string.php) for more information
on converting to string.


This function performs no formatting on the returned value. If you
are looking for a way to format a numeric value as a string, please
see [sprintf()](https://www.php.net/manual/en/function.sprintf.php) or [number\_format()](https://www.php.net/manual/en/function.number-format.php).


### Parameters [¶](https://www.php.net/manual/en/function.strval.php\#refsect1-function.strval-parameters)

`value`

The variable that is being converted to a [string](https://www.php.net/manual/en/language.types.string.php).


`value` may be any scalar type, [null](https://www.php.net/manual/en/language.types.null.php),
or an [object](https://www.php.net/manual/en/language.types.object.php) that implements the [\_\_toString()](https://www.php.net/manual/en/language.oop5.magic.php#object.tostring)
method. You cannot use **strval()** on arrays or on
objects that do not implement the
[\_\_toString()](https://www.php.net/manual/en/language.oop5.magic.php#object.tostring) method.


### Return Values [¶](https://www.php.net/manual/en/function.strval.php\#refsect1-function.strval-returnvalues)

The [string](https://www.php.net/manual/en/language.types.string.php) value of `value`.


### Examples [¶](https://www.php.net/manual/en/function.strval.php\#refsect1-function.strval-examples)

**Example #1**
****strval()** example using PHP magic**
**[\_\_toString()](https://www.php.net/manual/en/language.oop5.magic.php#object.tostring) method.**

`<?php
class StrValTest
{
    public function __toString()
    {
        return __CLASS__;
    }
}
// Prints 'StrValTest'
echo strval(new StrValTest);
?>`

Run code

### See Also [¶](https://www.php.net/manual/en/function.strval.php\#refsect1-function.strval-seealso)

- [boolval()](https://www.php.net/manual/en/function.boolval.php) \- Get the boolean value of a variable
- [floatval()](https://www.php.net/manual/en/function.floatval.php) \- Get float value of a variable
- [intval()](https://www.php.net/manual/en/function.intval.php) \- Get the integer value of a variable
- [settype()](https://www.php.net/manual/en/function.settype.php) \- Set the type of a variable
- [sprintf()](https://www.php.net/manual/en/function.sprintf.php) \- Return a formatted string
- [number\_format()](https://www.php.net/manual/en/function.number-format.php) \- Format a number with grouped thousands
- [Type juggling](https://www.php.net/manual/en/language.types.type-juggling.php)
- [\_\_toString()](https://www.php.net/manual/en/language.oop5.magic.php#object.tostring)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/functions/strval.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.strval%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.strval&repo=en&redirect=https://www.php.net/manual/en/function.strval.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=119421&page=function.strval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119421&page=function.strval&vote=down "Vote down!")

19


[**_Mark Clements_**](https://www.php.net/manual/en/function.strval.php#119421) [¶](https://www.php.net/manual/en/function.strval.php#119421)

**9 years ago**

`Some notes about how this function has changed over time, with regards the following statement:
> You cannot use strval() on arrays or on objects that
> do not implement the __toString() method.
== Arrays ==
In PHP 5.3 and below, strval(array(1, 2, 3)) would return the string "Array" without any sort of error occurring.
From 5.4 and above, the return value is unchanged but you will now get a notice-level error: "Array to string conversion".
== Objects ==
For objects that do not implement __toString(), the behaviour has varied:
PHP 4: "Object"
PHP 5 < 5.2: "Object id #1" (number obviously varies)
PHP >= 5.2: Catchable fatal error:  Object of class X could not be converted to string`

[up](https://www.php.net/manual/vote-note.php?id=77266&page=function.strval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77266&page=function.strval&vote=down "Vote down!")

17


[**_Hayley Watson_**](https://www.php.net/manual/en/function.strval.php#77266) [¶](https://www.php.net/manual/en/function.strval.php#77266)

**18 years ago**

`As of PHP 5.2, strval() will return the string value of an object, calling its __toString() method to determine what that value is.`

[up](https://www.php.net/manual/vote-note.php?id=41988&page=function.strval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=41988&page=function.strval&vote=down "Vote down!")

19


[**_Tom Nicholson_**](https://www.php.net/manual/en/function.strval.php#41988) [¶](https://www.php.net/manual/en/function.strval.php#41988)

**21 years ago**

`If you want to convert an integer into an English word string, eg. 29 -> twenty-nine, then here's a function to do it.
Note on use of fmod()
I used the floating point fmod() in preference to the % operator, because % converts the operands to int, corrupting values outside of the range [-2147483648, 2147483647]
I haven't bothered with "billion" because the word means 10e9 or 10e12 depending who you ask.
The function returns '#' if the argument does not represent a whole number.
<?php
$nwords = array( "zero", "one", "two", "three", "four", "five", "six", "seven",
                   "eight", "nine", "ten", "eleven", "twelve", "thirteen",
                   "fourteen", "fifteen", "sixteen", "seventeen", "eighteen",
                   "nineteen", "twenty", 30 => "thirty", 40 => "forty",
                   50 => "fifty", 60 => "sixty", 70 => "seventy", 80 => "eighty",
                   90 => "ninety" );
function int_to_words($x) {
global $nwords;
if(!is_numeric($x))
      $w = '#';
else if(fmod($x, 1) != 0)
      $w = '#';
else {
      if($x < 0) {
         $w = 'minus ';
         $x = -$x;
      } else
         $w = '';
      // ... now $x is a non-negative integer.
      if($x < 21)   // 0 to 20
         $w .= $nwords[$x];
      else if($x < 100) {   // 21 to 99
         $w .= $nwords[10 * floor($x/10)];
         $r = fmod($x, 10);
         if($r > 0)
            $w .= '-'. $nwords[$r];
      } else if($x < 1000) {   // 100 to 999
         $w .= $nwords[floor($x/100)] .' hundred';
         $r = fmod($x, 100);
         if($r > 0)
            $w .= ' and '. int_to_words($r);
      } else if($x < 1000000) {   // 1000 to 999999
         $w .= int_to_words(floor($x/1000)) .' thousand';
         $r = fmod($x, 1000);
         if($r > 0) {
            $w .= ' ';
            if($r < 100)
               $w .= 'and ';
            $w .= int_to_words($r);
         }
      } else {    //  millions
         $w .= int_to_words(floor($x/1000000)) .' million';
         $r = fmod($x, 1000000);
         if($r > 0) {
            $w .= ' ';
            if($r < 100)
               $word .= 'and ';
            $w .= int_to_words($r);
         }
      }
}
return $w;
}
?>
Usage:
<?php
echo 'There are currently '. int_to_words($count) . ' members logged on.';
?>`

[up](https://www.php.net/manual/vote-note.php?id=57559&page=function.strval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=57559&page=function.strval&vote=down "Vote down!")

14


[**_php at ianco dot co dot uk_**](https://www.php.net/manual/en/function.strval.php#57559) [¶](https://www.php.net/manual/en/function.strval.php#57559)

**20 years ago**

`I can't help being surprised that
(string)"0" == (string)"0.00"
evaluates to true. It's the same with strval and single quotes.
=== avoids it.
Why does it matter? One of my suppliers, unbelievably, uses 0 to mean standard discount and 0.00 to mean no discount in their stock files.`

[up](https://www.php.net/manual/vote-note.php?id=75496&page=function.strval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75496&page=function.strval&vote=down "Vote down!")

11


[**_kendsnyder+phpnet at gmail dot com_**](https://www.php.net/manual/en/function.strval.php#75496) [¶](https://www.php.net/manual/en/function.strval.php#75496)

**18 years ago**

`The only way to convert a large float to a string is to use printf('%0.0f',$float); instead of strval($float); (php 5.1.4).
// strval() will lose digits around pow(2,45);
echo pow(2,50); // 1.1258999068426E+015
echo (string)pow(2,50); // 1.1258999068426E+015
echo strval(pow(2,50)); // 1.1258999068426E+015
// full conversion
printf('%0.0f',pow(2,50)); // 112589906846624
echo sprintf('%0.0f',pow(2,50)); // 112589906846624`

[up](https://www.php.net/manual/vote-note.php?id=75682&page=function.strval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75682&page=function.strval&vote=down "Vote down!")

 -2


[**_NyctoFixer at gmail dot com_**](https://www.php.net/manual/en/function.strval.php#75682) [¶](https://www.php.net/manual/en/function.strval.php#75682)

**18 years ago**

`As of PHP 5.1.4 (I have not tested it in later versions), the strval function does not attempt to invoke the __toString method when it encounters an object. This simple wrapper function will handle this circumstance for you:
<?
/**
* Returns the string value of a variable
*
* This differs from strval in that it invokes __toString if an object is given
* and the object has that method
*/
function stringVal ($value)
{
    // We use get_class_methods instead of method_exists to ensure that __toString is a public method
    if (is_object($value) && in_array("__toString", get_class_methods($value)))
        return strval($value->__toString());
    else
        return strval($value);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=56605&page=function.strval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56605&page=function.strval&vote=down "Vote down!")

 -3


[**_Steve Ball_**](https://www.php.net/manual/en/function.strval.php#56605) [¶](https://www.php.net/manual/en/function.strval.php#56605)

**20 years ago**

`It seems that one is being treated as an unsigned large int (32 bit), and the other as a signed large int (which has rolled over/under).
2326201276 - (-1968766020) =  4294967296.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.strval&repo=en&redirect=https://www.php.net/manual/en/function.strval.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google