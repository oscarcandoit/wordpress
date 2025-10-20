---
url: https://www.php.net/manual/en/function.strlen.php
scraped_at: 2025-10-20T02:36:44.303Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# strlen

(PHP 4, PHP 5, PHP 7, PHP 8)

strlen — Get string length

### Description [¶](https://www.php.net/manual/en/function.strlen.php\#refsect1-function.strlen-description)

**strlen**([string](https://www.php.net/manual/en/language.types.string.php) `$string`): [int](https://www.php.net/manual/en/language.types.integer.php)

Returns the length of the given `string`.


### Parameters [¶](https://www.php.net/manual/en/function.strlen.php\#refsect1-function.strlen-parameters)

`string`

The [string](https://www.php.net/manual/en/language.types.string.php) being measured for length.


### Return Values [¶](https://www.php.net/manual/en/function.strlen.php\#refsect1-function.strlen-returnvalues)

The length of the `string` in bytes.


### Examples [¶](https://www.php.net/manual/en/function.strlen.php\#refsect1-function.strlen-examples)

**Example #1 A **strlen()** example**

`<?php
$str = 'abcdef';
echo strlen($str), PHP_EOL; // 6
$str = ' ab cd ';
echo strlen($str), PHP_EOL; // 7
?>`

Run code

### Notes [¶](https://www.php.net/manual/en/function.strlen.php\#refsect1-function.strlen-notes)

> **Note**:
>
>
> **strlen()** returns the number of bytes rather than the number
> of characters in a string.

### See Also [¶](https://www.php.net/manual/en/function.strlen.php\#refsect1-function.strlen-seealso)

- [count()](https://www.php.net/manual/en/function.count.php) \- Counts all elements in an array or in a Countable object
- [grapheme\_strlen()](https://www.php.net/manual/en/function.grapheme-strlen.php) \- Get string length in grapheme units
- [iconv\_strlen()](https://www.php.net/manual/en/function.iconv-strlen.php) \- Returns the character count of string
- [mb\_strlen()](https://www.php.net/manual/en/function.mb-strlen.php) \- Get string length

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/strlen.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.strlen%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.strlen&repo=en&redirect=https://www.php.net/manual/en/function.strlen.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=118484&page=function.strlen&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118484&page=function.strlen&vote=down "Vote down!")

232


[**_rm dot nasir at hotmail dot com_**](https://www.php.net/manual/en/function.strlen.php#118484) [¶](https://www.php.net/manual/en/function.strlen.php#118484)

**9 years ago**

`I want to share something seriously important for newbies or beginners of PHP who plays with strings of UTF8 encoded characters or the languages like: Arabic, Persian, Pashto, Dari, Chinese (simplified), Chinese (traditional), Japanese, Vietnamese, Urdu, Macedonian, Lithuanian, and etc.
As the manual says: "strlen() returns the number of bytes rather than the number of characters in a string.", so if you want to get the number of characters in a string of UTF8 so use mb_strlen() instead of strlen().
Example:
<?php
// the Arabic (Hello) string below is: 59 bytes and 32 characters
$utf8 = "السلام علیکم ورحمة الله وبرکاته!";
var_export( strlen($utf8) ); // 59
echo "<br>";
var_export( mb_strlen($utf8, 'utf8') ); // 32
?>`

[up](https://www.php.net/manual/vote-note.php?id=112411&page=function.strlen&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112411&page=function.strlen&vote=down "Vote down!")

33


[**_jasonrohrer at fastmail dot fm_**](https://www.php.net/manual/en/function.strlen.php#112411) [¶](https://www.php.net/manual/en/function.strlen.php#112411)

**12 years ago**

`PHP's strlen function behaves differently than the C strlen function in terms of its handling of null bytes ('\0').
In PHP, a null byte in a string does NOT count as the end of the string, and any null bytes are included in the length of the string.
For example, in PHP:
strlen( "te\0st" ) = 5
In C, the same call would return 2.
Thus, PHP's strlen function can be used to find the number of bytes in a binary string (for example, binary data returned by base64_decode).`

[up](https://www.php.net/manual/vote-note.php?id=119650&page=function.strlen&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119650&page=function.strlen&vote=down "Vote down!")

18


[**_joeri at sebrechts dot net_**](https://www.php.net/manual/en/function.strlen.php#119650) [¶](https://www.php.net/manual/en/function.strlen.php#119650)

**9 years ago**

`When checking for length to make sure a value will fit in a database field, be mindful of using the right function.
There are three possible situations:
1. Most likely case: the database column is UTF-8 with a length defined in unicode code points (e.g. mysql varchar(200) for a utf-8 database).
<?php
// ok if php.ini default_charset set to UTF-8 (= default value)
mb_strlen($value);
iconv_strlen($value);
// always ok
mb_strlen($value, "UTF-8");
iconv_strlen($value, "UTF-8");
// BAD, do not use:
strlen(utf8_decode($value)); // breaks for some multi-byte characters
grapheme_strlen($value); // counts graphemes, not code points
?>
2. The database column has a length defined in bytes (e.g. oracle's VARCHAR2(200 BYTE))
<?php
// ok, but assumes mbstring.func_overload is 0 in php.ini (= default value)
strlen($value);
// ok, forces count in bytes
mb_strlen($value, "8bit")
?>
3. The database column is in another character set (UTF-16, ISO-8859-1, etc...) with a length defined in characters / code points.
Find the character set used, and pass it explicitly to the length function.
<?php
// ok, supported charsets: [http://php.net/manual/en/mbstring.supported-encodings.php](http://php.net/manual/en/mbstring.supported-encodings.php)
mb_strlen($value, $charset);
// ok, supported charsets: [https://www.gnu.org/software/libiconv/](https://www.gnu.org/software/libiconv/)
iconv_strlen($value, $charset);
?>`

[up](https://www.php.net/manual/vote-note.php?id=127814&page=function.strlen&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127814&page=function.strlen&vote=down "Vote down!")

5


[**_Daniel Klein_**](https://www.php.net/manual/en/function.strlen.php#127814) [¶](https://www.php.net/manual/en/function.strlen.php#127814)

**2 years ago**

`Since PHP 8.0, passing null to strlen() is deprecated. To check for a blank string (not including '0'):
<?php
// PHP < 8.0
if (!strlen($text)) {
echo 'Blank';
}
// PHP >= 8.0
if ($text === null || $text === '')) {
echo 'empty';
}`

[up](https://www.php.net/manual/vote-note.php?id=98315&page=function.strlen&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=98315&page=function.strlen&vote=down "Vote down!")

20


[**_basil at gohar dot us_**](https://www.php.net/manual/en/function.strlen.php#98315) [¶](https://www.php.net/manual/en/function.strlen.php#98315)

**15 years ago**

`We just ran into what we thought was a bug but turned out to be a documented difference in behavior between PHP 5.2 & 5.3.  Take the following code example:
<?php
$attributes = array('one', 'two', 'three');
if (strlen($attributes) == 0 && !is_bool($attributes)) {
    echo "We are in the 'if'\n";  //  PHP 5.3
} else {
    echo "We are in the 'else'\n";  //  PHP 5.2
}
?>
This is because in 5.2 strlen will automatically cast anything passed to it as a string, and casting an array to a string yields the string "Array".  In 5.3, this changed, as noted in the following point in the backward incompatible changes in 5.3 ( [http://www.php.net/manual/en/migration53.incompatible.php](http://www.php.net/manual/en/migration53.incompatible.php)):
"The newer internal parameter parsing API has been applied across all the extensions bundled with PHP 5.3.x. This parameter parsing API causes functions to return NULL when passed incompatible parameters. There are some exceptions to this rule, such as the get_class() function, which will continue to return FALSE on error."
So, in PHP 5.3, strlen($attributes) returns NULL, while in PHP 5.2, strlen($attributes) returns the integer 5.  This likely affects other functions, so if you are getting different behaviors or new bugs suddenly, check if you have upgraded to 5.3 (which we did recently), and then check for some warnings in your logs like this:
strlen() expects parameter 1 to be string, array given in /var/www/sis/lib/functions/advanced_search_lib.php on line 1028
If so, then you are likely experiencing this changed behavior.`

[up](https://www.php.net/manual/vote-note.php?id=120632&page=function.strlen&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120632&page=function.strlen&vote=down "Vote down!")

10


[**_John_**](https://www.php.net/manual/en/function.strlen.php#120632) [¶](https://www.php.net/manual/en/function.strlen.php#120632)

**8 years ago**

`There's a LOT of misinformation here, which I want to correct! Many people have warned against using strlen(), because it is "super slow". Well, that was probably true in old versions of PHP. But as of PHP7 that's definitely no longer true. It's now SUPER fast!
I created a 20,00,000 byte string (~20 megabytes), and iterated ONE HUNDRED MILLION TIMES in a loop. Every loop iteration did a new strlen() on that very, very long string.
The result: 100 million strlen() calls on a 20 megabyte string only took a total of 488 milliseconds. And the strlen() calls didn't get slower/faster even if I made the string smaller or bigger. The strlen() was pretty much a constant-time, super-fast operation
So either PHP7 stores the length of every string as a field that it can simply always look up without having to count characters. Or it caches the result of strlen() until the string contents actually change. Either way, you should now never, EVER worry about strlen() performance again. As of PHP7, it is super fast!
Here is the complete benchmark code if you want to reproduce it on your machine:
<?php
$iterations = 100000000; // 100 million
$str = str_repeat( '0', 20000000 );
// benchmark loop and variable assignment to calculate loop overhead
$start = microtime(true);
for( $i = 0; $i < $iterations; ++$i ) {
    $len = 0;
}
$end = microtime(true);
$loop_elapsed = 1000 * ($end - $start);
// benchmark strlen in a loop
$len = 0;
$start = microtime(true);
for( $i = 0; $i < $iterations; ++$i ) {
    $len = strlen( $str );
}
$end = microtime(true);
$strlen_elapsed = 1000 * ($end - $start);
// subtract loop overhead from strlen() speed calculation
$strlen_elapsed -= $loop_elapsed;
echo "\nstring length: {$len}\ntest took: {$strlen_elapsed} milliseconds\n";
?>`

[up](https://www.php.net/manual/vote-note.php?id=109715&page=function.strlen&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109715&page=function.strlen&vote=down "Vote down!")

19


[**_vcardillo at gmail dot com_**](https://www.php.net/manual/en/function.strlen.php#109715) [¶](https://www.php.net/manual/en/function.strlen.php#109715)

**13 years ago**

`I would like to demonstrate that you need more than just this function in order to truly test for an empty string. The reason being that <?php strlen(null); ?> will return 0. So how do you know if the value was null, or truly an empty string?
<?php
$foo = null;
$len = strlen(null);
$bar = '';
echo "Length: " . strlen($foo) . "<br>";
echo "Length: $len <br>";
echo "Length: " . strlen(null) . "<br>";
if (strlen($foo) === 0) echo 'Null length is Zero <br>';
if ($len === 0) echo 'Null length is still Zero <br>';
if (strlen($foo) == 0 && !is_null($foo)) echo '!is_null(): $foo is truly an empty string <br>';
else echo '!is_null(): $foo is probably null <br>';
if (strlen($foo) == 0 && isset($foo)) echo 'isset(): $foo is truly an empty string <br>';
else echo 'isset(): $foo is probably null <br>';
if (strlen($bar) == 0 && !is_null($bar)) echo '!is_null(): $bar is truly an empty string <br>';
else echo '!is_null(): $foo is probably null <br>';
if (strlen($bar) == 0 && isset($bar)) echo 'isset(): $bar is truly an empty string <br>';
else echo 'isset(): $foo is probably null <br>';
?>
// Begin Output:
Length: 0
Length: 0
Length: 0
Null length is Zero
Null length is still Zero
!is_null(): $foo is probably null
isset(): $foo is probably null
!is_null(): $bar is truly an empty string
isset(): $bar is truly an empty string
// End Output
So it would seem you need either is_null() or isset() in addition to strlen() if you care whether or not the original value was null.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.strlen&repo=en&redirect=https://www.php.net/manual/en/function.strlen.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google