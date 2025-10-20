---
url: https://www.php.net/manual/en/function.range.php
scraped_at: 2025-10-20T02:58:33.797Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# range

(PHP 4, PHP 5, PHP 7, PHP 8)

range — Create an array containing a range of elements

### Description [¶](https://www.php.net/manual/en/function.range.php\#refsect1-function.range-description)

**range**([string](https://www.php.net/manual/en/language.types.string.php)\|[int](https://www.php.net/manual/en/language.types.integer.php)\|[float](https://www.php.net/manual/en/language.types.float.php) `$start`, [string](https://www.php.net/manual/en/language.types.string.php)\|[int](https://www.php.net/manual/en/language.types.integer.php)\|[float](https://www.php.net/manual/en/language.types.float.php) `$end`, [int](https://www.php.net/manual/en/language.types.integer.php)\|[float](https://www.php.net/manual/en/language.types.float.php) `$step` = 1): [array](https://www.php.net/manual/en/language.types.array.php)

Create an array containing a range of elements.


If both `start` and `end` are
[string](https://www.php.net/manual/en/language.types.string.php)s, and `step` is [int](https://www.php.net/manual/en/language.types.integer.php)
the produced array will be a sequence of bytes.
Otherwise, the produced array will be a sequence of numbers.


The sequence is increasing if `start` is less than
equal to `end`.
Otherwise, the sequence is decreasing.


### Parameters [¶](https://www.php.net/manual/en/function.range.php\#refsect1-function.range-parameters)

`start`

First value of the sequence.


`end`

Last possible value of the sequence.


`step`

`step` indicates by how much is the produced
sequence progressed between values of the sequence.


`step` may be negative for decreasing sequences.


If `step` is a [float](https://www.php.net/manual/en/language.types.float.php) without a
fractional part, it is interpreted as [int](https://www.php.net/manual/en/language.types.integer.php).


### Return Values [¶](https://www.php.net/manual/en/function.range.php\#refsect1-function.range-returnvalues)

Returns a sequence of elements as an [array](https://www.php.net/manual/en/language.types.array.php) with the first
element being `start` going up to
`end`, with each value of the sequence being
`step` values apart.


The last element of the returned array is either `end`
or the previous element of the sequence,
depending on the value of `step`.


If both `start` and `end` are
[string](https://www.php.net/manual/en/language.types.string.php)s, and `step` is [int](https://www.php.net/manual/en/language.types.integer.php)
the produced array will be a sequence of bytes,
generally latin ASCII characters.


If at least one of `start`, `end`,
or `step` is [float](https://www.php.net/manual/en/language.types.float.php)
the produced array will be a sequence of [float](https://www.php.net/manual/en/language.types.float.php).


Otherwise, the produced array will be a sequence of [int](https://www.php.net/manual/en/language.types.integer.php).


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.range.php\#refsect1-function.range-errors)

- If `step` is `0`,
a [ValueError](https://www.php.net/manual/en/class.valueerror.php) is thrown.

- If `start`, `end`,
or `step` is not [is\_finite()](https://www.php.net/manual/en/function.is-finite.php),
a [ValueError](https://www.php.net/manual/en/class.valueerror.php) is thrown.

- If `step` is negative,
but the produced range is increasing
(i.e. `$start <= $end`),
a [ValueError](https://www.php.net/manual/en/class.valueerror.php) is thrown.

- If `start` or `end`
is the empty string `''`,
an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is emitted and
the empty string will be interpreted as `0`.

- If `start` or `end` is a
non- [numeric string](https://www.php.net/manual/en/language.types.numeric-strings.php)
with more than one byte, an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is emitted.

- If `start` or `end` is a string
that is implicitly cast to an [int](https://www.php.net/manual/en/language.types.integer.php) because the other boundary
value is a number, an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is emitted.

- If `step` is a [float](https://www.php.net/manual/en/language.types.float.php),
and `start` and `end` are
non- [numeric string](https://www.php.net/manual/en/language.types.numeric-strings.php),
an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is emitted.


### Changelog [¶](https://www.php.net/manual/en/function.range.php\#refsect1-function.range-changelog)

| Version | Description |
| --- | --- |
| 8.3.0 | If both `start` and `end`<br> are strings then **range()** will now always produce<br> an [array](https://www.php.net/manual/en/language.types.array.php) of bytes.<br> Previously if one of the boundary values was a numeric string,<br> then the other boundary value was implicitly cast to [int](https://www.php.net/manual/en/language.types.integer.php). |
| 8.3.0 | An **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is now emitted if<br> `start` or `end`<br> is a string that is implicitly cast to [int](https://www.php.net/manual/en/language.types.integer.php)<br> because the other boundary value is a number. |
| 8.3.0 | An **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is now emitted if<br> `start` or `end`<br> is a non-numeric string with more than one byte. |
| 8.3.0 | An **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is now emitted if<br> `start` or `end`<br> is the empty string. |
| 8.3.0 | If `step` is a [float](https://www.php.net/manual/en/language.types.float.php) with no<br> fractional part, it will be interpreted as an [int](https://www.php.net/manual/en/language.types.integer.php). |
| 8.3.0 | A [ValueError](https://www.php.net/manual/en/class.valueerror.php) is now thrown if<br> `step` is negative when producing an increasing<br> range. |
| 8.3.0 | A [ValueError](https://www.php.net/manual/en/class.valueerror.php) is now thrown if<br> `step` is not finite. |
| 8.3.0 | A [TypeError](https://www.php.net/manual/en/class.typeerror.php) is now thrown if<br> `start` or `end`<br> is an [array](https://www.php.net/manual/en/language.types.array.php), [object](https://www.php.net/manual/en/language.types.object.php), or [resource](https://www.php.net/manual/en/language.types.resource.php).<br> Previously they were implicitly cast to [int](https://www.php.net/manual/en/language.types.integer.php). |

### Examples [¶](https://www.php.net/manual/en/function.range.php\#refsect1-function.range-examples)

**Example #1 **range()** examples**

`<?php
echo implode(', ', range(0, 12)), PHP_EOL;
echo implode(', ', range(0, 100, 10)), PHP_EOL;
echo implode(', ', range('a', 'i')), PHP_EOL;
echo implode(', ', range('c', 'a')), PHP_EOL;
echo implode(', ', range('A', 'z')), PHP_EOL;
?>`

Run code

The above example will output:

```
0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12
0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100
a, b, c, d, e, f, g, h, i
c, b, a
A, B, C, D, E, F, G, H, I, J, K, L, M, N, O, P, Q, R, S, T, U, V, W, X, Y, Z, [, \, ], ^, _, `, a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z
```

### See Also [¶](https://www.php.net/manual/en/function.range.php\#refsect1-function.range-seealso)

- [shuffle()](https://www.php.net/manual/en/function.shuffle.php) \- Shuffle an array
- [array\_fill()](https://www.php.net/manual/en/function.array-fill.php) \- Fill an array with values
- [`foreach`](https://www.php.net/manual/en/control-structures.foreach.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/range.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.range%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.range&repo=en&redirect=https://www.php.net/manual/en/function.range.php)

### User Contributed Notes 30 notes

[up](https://www.php.net/manual/vote-note.php?id=110504&page=function.range&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110504&page=function.range&vote=down "Vote down!")

135


[**_Palz_**](https://www.php.net/manual/en/function.range.php#110504) [¶](https://www.php.net/manual/en/function.range.php#110504)

**12 years ago**

`To create a range array like
Array
(
    [11] => 1
    [12] => 2
    [13] => 3
    [14] => 4
)
combine two range arrays using array_combine:
array_combine(range(11,14),range(1,4))`

[up](https://www.php.net/manual/vote-note.php?id=114493&page=function.range&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114493&page=function.range&vote=down "Vote down!")

14


[**_php at keith tyler dot com_**](https://www.php.net/manual/en/function.range.php#114493) [¶](https://www.php.net/manual/en/function.range.php#114493)

**11 years ago**

``So with the introduction of single-character ranges to the range() function, the internal function tries to be "smart", and (I am inferring from behavior here) apparently checks the type of the incoming values. If one is numeric, including numeric string, then the other is treated as numeric; if it is a non-numeric string, it is treated as zero.
But.
If you pass in a numeric string in such a way that is is forced to be recognized as type string and not type numeric, range() will function quite differently.
Compare:
<?php
echo implode("",range(9,"Q"));
// prints 9876543210
echo implode("",range("9 ","Q"));  //space after the 9
// prints 9:;<=>?@ABCDEFGHIJKLMNOPQ
echo implode("",range("q","9 "));
// prints qponmlkjihgfedcba`_^]\[ZYXWVUTSRQPONMLKJIHGFEDCBA@?>=<;:987654\
?>\
I wouldn't call this a bug, because IMO it is even more useful than the stock usage of the function.``\
\
[up](https://www.php.net/manual/vote-note.php?id=112036&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=112036&page=function.range&vote=down "Vote down!")\
\
15\
\
\
[**_gtisza at gmail dot com_**](https://www.php.net/manual/en/function.range.php#112036) [¶](https://www.php.net/manual/en/function.range.php#112036)\
\
**12 years ago**\
\
`You might expect range($n, $n-1) to be an empty array (as in e.g. Python) but actually PHP will assume a step of -1 if start is larger than end.`\
\
[up](https://www.php.net/manual/vote-note.php?id=118224&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=118224&page=function.range&vote=down "Vote down!")\
\
10\
\
\
[**_Alien426_**](https://www.php.net/manual/en/function.range.php#118224) [¶](https://www.php.net/manual/en/function.range.php#118224)\
\
**9 years ago**\
\
`The function will generate an array of integers even if your numerical parameters are enclosed in quotes.\
<?php\
var_dump( range('1', '2') ); // outputs  array(2) { [0]=> int(1) [1]=> int(2) }\
?>\
An easy way to get an array of strings is to map strval() to the range:\
<?php\
var_dump( array_map('strval', range('1', '2')) ); // outputs  array(2) { [0]=> string(1) "1" [1]=> string(1) "2" }\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=119519&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=119519&page=function.range&vote=down "Vote down!")\
\
8\
\
\
[**_luca.favorido ATgmailDOT com_**](https://www.php.net/manual/en/function.range.php#119519) [¶](https://www.php.net/manual/en/function.range.php#119519)\
\
**9 years ago**\
\
`The function "range" is very useful to get an array of characters as range('C','R') does.\
At work, I had to extend the function range($a,$b) to work in this special case: with two uppercase strings $a and $b, it should return all the possible strings between $a and $b.\
This could be used for example to get the excel column indexes.\
e.g. <?php range('A','AD') ==> array('A','B','C',...,'Z','AA','AB','AC','AD') ?>\
So I wrote the function getrange($min,$max) that exactly does this.\
<?php\
function getcolumnrange($min,$max){\
      $pointer=strtoupper($min);\
      $output=array();\
      while(positionalcomparison($pointer,strtoupper($max))<=0){\
         array_push($output,$pointer);\
         $pointer++;\
      }\
      return $output;\
}\
function positionalcomparison($a,$b){\
$a1=stringtointvalue($a); $b1=stringtointvalue($b);\
if($a1>$b1)return 1;\
else if($a1<$b1)return -1;\
else return 0;\
}\
/*\
* e.g. A=1 - B=2 - Z=26 - AA=27 - CZ=104 - DA=105 - ZZ=702 - AAA=703\
*/\
function stringtointvalue($str){\
$amount=0;\
$strarra=array_reverse(str_split($str));\
for($i=0;$i<strlen($str);$i++){\
      $amount+=(ord($strarra[$i])-64)*pow(26,$i);\
}\
return $amount;\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=114180&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=114180&page=function.range&vote=down "Vote down!")\
\
5\
\
\
[**_jazzduck AT gmail DOT com_**](https://www.php.net/manual/en/function.range.php#114180) [¶](https://www.php.net/manual/en/function.range.php#114180)\
\
**11 years ago**\
\
`Despite the line above that says that the $step value should be "given as a positive number," the range() function will in fact correctly handle reversed (decrementing) ranges. For example:\
<?php print_r( range( 24, 20 ) ); ?>\
Array\
(\
    [0] => 24\
    [1] => 23\
    [2] => 22\
    [3] => 21\
    [4] => 20\
)\
<?php print_r( range( 20, 11, -3 ) ); ?>\
Array\
(\
    [0] => 20\
    [1] => 17\
    [2] => 14\
    [3] => 11\
)\
It will actually ignore the sign of the $step argument, and determine whether to increment or decrement based purely on whether $start > $end or $end > $start. For example:\
<?php print_r( range( 20, 11, 3 ) ); ?>\
Array\
(\
    [0] => 20\
    [1] => 17\
    [2] => 14\
    [3] => 11\
)\
<?php print_r( range( 11, 20, -3 ) ); ?>\
Array\
(\
    [0] => 11\
    [1] => 14\
    [2] => 17\
    [3] => 20\
)`\
\
[up](https://www.php.net/manual/vote-note.php?id=85331&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=85331&page=function.range&vote=down "Vote down!")\
\
17\
\
\
[**_ThinkMedical at Gmail dot com_**](https://www.php.net/manual/en/function.range.php#85331) [¶](https://www.php.net/manual/en/function.range.php#85331)\
\
**17 years ago**\
\
`foreach(range()) whilst efficiant in other languages, such as python, it is not (compared to a for) in php*.\
php is a C-inspired language and thus for is entirely in-keeping with the lanuage aethetic to use it\
<?php\
//efficiant\
for($i = $start; $i < $end; $i+=$step)\
{\
        //do something with array\
}\
//inefficiant\
foreach(range($start, $end, $step) as $i)\
{\
        //do something with array\
}\
?>\
That the officiant documentation doesnt mention the for loop is strange.\
Note however, that in PHP5 foreach is faster than for when iterating without incrementing a variable.\
* My tests using microtime and 100 000 iterations consistently (~10 times) show that for is 4x faster than foreach(range()).`\
\
[up](https://www.php.net/manual/vote-note.php?id=75045&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=75045&page=function.range&vote=down "Vote down!")\
\
7\
\
\
[**_chris at laflash dot org_**](https://www.php.net/manual/en/function.range.php#75045) [¶](https://www.php.net/manual/en/function.range.php#75045)\
\
**18 years ago**\
\
`Quick HTML menus with minimum and maximum sets of years:\
<?php\
    /*\
    ** Quick HTML menus with minimum and maximum sets of years.\
    ** @author Chris Charlton <chris@laflash.org>\
    ** @license FREE!\
    */\
    // Years range setup\
    $year_built_min = 1900;\
    $year_built_max = date("Y");\
?>\
<select id="yearBuiltMin" size="1">\
    <?php // Generate minimum years\
        foreach (range($year_built_min, $year_built_max) as $year) { ?>\
        <option value="<?php echo($year); ?>"><?php echo($year); ?></option>\
        <?php } ?>\
</select>\
<select id="yearBuiltMax" size="1">\
      <?php // Generate max years\
        foreach (range($year_built_max, $year_built_min) as $year) { ?>\
        <option value="<?php echo($year); ?>"><?php echo($year); ?></option>\
        <?php } ?>\
</select>`\
\
[up](https://www.php.net/manual/vote-note.php?id=123925&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=123925&page=function.range&vote=down "Vote down!")\
\
4\
\
\
[**_ccb\_bc at hotmail dot com_**](https://www.php.net/manual/en/function.range.php#123925) [¶](https://www.php.net/manual/en/function.range.php#123925)\
\
**6 years ago**\
\
`<?php\
    function natural_prime_numbers(array $range, bool $print_info = false) : array {\
        $start_time = time();\
        $primes_numbers = array();\
        $print = '';\
        $count_range  = count($range);\
        foreach($range as $number){\
            $values_division_number = array();\
            if($number === 0 || $number === 1 || !is_int($number)){ // eliminate 0, 1 and other no integer\
                continue;\
            }\
            if($number != 2 && $number%2 === 0){ // eliminate 2 and pairs numbers\
                continue;\
            }\
            for($i = 1; $i <= $number; $i++){\
                $resultado_divisao = $number / $i;\
                $values_division_number[$i] = $resultado_divisao;\
                if($count_range <= 20){ // $count_range <= 20 (+ performance)\
                    $print .= PHP_EOL;\
                    $info = 'The number '.$number.' divided by the number '.$i.' is equal to: '.($number / $i);\
                    $print .= $info;\
                    if($i === $number){\
                        $print .= PHP_EOL;\
                    }\
                }\
                array_walk($values_division_number, function($value, $index) use (&$values_division_number, &$number){ // reference change values\
                    // eliminate floats and others numbers not are equal 1 and own number\
                    if(is_float($value) && $value != $number && $value > 1){\
                        unset($values_division_number[$index]);\
                    }\
                });\
                $values_division_number = array_values($values_division_number); // reindex array\
                // here we want only array with 2 indexes with the values 1 and own number (rule to a natural prime number)\
                if(count($values_division_number) === 2 && $values_division_number[0] === $number && $values_division_number[1] === 1){\
                    $primes_numbers[$number] = $number;\
                }\
            }\
        }\
        return array(\
            'length_prime_numbers' => count($primes_numbers),\
            'prime_numbers' => array_values($primes_numbers),\
            'print' => $print,\
            'total_time_processing' => (time() - $start_time).' seconds.',\
        );\
    }\
    var_dump(natural_prime_numbers(range(0, 11))); // here the range() function ;-)\
    // Result:\
    // array (size=3)\
    //   'length_prime_numbers' => int 5\
    //   'prime_numbers' =>\
    //     array (size=5)\
    //       0 => int 2\
    //       1 => int 3\
    //       2 => int 5\
    //       3 => int 7\
    //       4 => int 11\
    //   'print' => string '\
    // O número 2 dividido pelo número 1 é igual a: 2\
    // O número 2 dividido pelo número 2 é igual a: 1\
    // O número 3 dividido pelo número 1 é igual a: 3\
    // O número 3 dividido pelo número 2 é igual a: 1.5\
    // O número 3 dividido pelo número 3 é igual a: 1\
    // O número 5 dividido pelo número 1 é igual a: 5\
    // O número 5 dividido pelo número 2 é igual a: 2.5\
    // O número 5 dividido pelo número 3 é igual a: 1.6666666666667\
    // O número 5 dividido pelo número 4 é igual a: 1.25\
    // O número 5 dividido pelo '...\
    // **************************** //\
    //\
    // * Remember that the function is recursive, that is: a range of 5000 takes more than 1 minute on a processor Intel® Core™ i5-8250U (3.40 GHz).\
    //\
    // **************************** //\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=109642&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=109642&page=function.range&vote=down "Vote down!")\
\
8\
\
\
[**_ktamas77 at gmail dot com_**](https://www.php.net/manual/en/function.range.php#109642) [¶](https://www.php.net/manual/en/function.range.php#109642)\
\
**13 years ago**\
\
`if you need zero padding, string prefixes or any other masks, then a simple combination of array_map, inline functions and sprintf is your friend.\
<?php\
$a = array_map(function($n) { return sprintf('sample_%03d', $n); }, range(50, 59) );\
print_r($a);\
?>\
Will result:\
Array\
(\
    [0] => sample_050\
    [1] => sample_051\
    [2] => sample_052\
    [3] => sample_053\
    [4] => sample_054\
    [5] => sample_055\
    [6] => sample_056\
    [7] => sample_057\
    [8] => sample_058\
    [9] => sample_059\
)`\
\
[up](https://www.php.net/manual/vote-note.php?id=73579&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=73579&page=function.range&vote=down "Vote down!")\
\
6\
\
\
[**_m0sh3 at hotmail dot com_**](https://www.php.net/manual/en/function.range.php#73579) [¶](https://www.php.net/manual/en/function.range.php#73579)\
\
**18 years ago**\
\
`Here's how i use it to check if array is associative or not:\
<?php\
if (array_keys($arr)===range(0, sizeof($arr)-1)) {\
// not associative array\
} else {\
// associative array\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=112362&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=112362&page=function.range&vote=down "Vote down!")\
\
3\
\
\
[**_Ray.Paseur often uses Gmail_**](https://www.php.net/manual/en/function.range.php#112362) [¶](https://www.php.net/manual/en/function.range.php#112362)\
\
**12 years ago**\
\
`Interestingly, these two statements produce identical 26-character alphabet arrays.\
<?php\
$arr = range('A',  'Z');\
$arr = range('AA', 'ZZ');`\
\
[up](https://www.php.net/manual/vote-note.php?id=118659&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=118659&page=function.range&vote=down "Vote down!")\
\
2\
\
\
[**_moficer at host dot sk_**](https://www.php.net/manual/en/function.range.php#118659) [¶](https://www.php.net/manual/en/function.range.php#118659)\
\
**9 years ago**\
\
``php 5.6.16\
<?php\
var_export(range('Z', 'a'));\
/*\
array (\
0 => 'Z',\
1 => '[',\
2 => '\\',\
3 => ']',\
4 => '^',\
5 => '_',\
6 => '`',\
7 => 'a',\
)\
*/``\
\
[up](https://www.php.net/manual/vote-note.php?id=108767&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=108767&page=function.range&vote=down "Vote down!")\
\
9\
\
\
[**_me at phpscott dot com_**](https://www.php.net/manual/en/function.range.php#108767) [¶](https://www.php.net/manual/en/function.range.php#108767)\
\
**13 years ago**\
\
`So, I needed a quick and dirty way to create a dropdown select for hours, minutes and seconds using 2 digit formatting, and to create those arrays of data, I combined range with array merge..\
<?php\
$prepend = array('00','01','02','03','04','05','06','07','08','09');\
$hours     = array_merge($prepend,range(10, 23));\
$minutes     = array_merge($prepend,range(10, 59));\
$seconds     = $minutes;\
?>\
Super simple.`\
\
[up](https://www.php.net/manual/vote-note.php?id=90605&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=90605&page=function.range&vote=down "Vote down!")\
\
3\
\
\
[**_jay at NOspam dot myd3 dot com_**](https://www.php.net/manual/en/function.range.php#90605) [¶](https://www.php.net/manual/en/function.range.php#90605)\
\
**16 years ago**\
\
`This is a modified version of thomas' range_string() function. It's simpler, cleaner, and more robust, but it lacks the advanced features his function had, hopefully it will be of assitance to someone.\
Examples:\
    input: "1, 2, 3, 4, 5, 6" --> output: 1, 2, 3, 4, 5, 6\
    input: "1-6" --> output: 1, 2, 3, 4, 5, 6\
    input: "1-6" --> output: 1, 2, 3, 4, 5, 6\
    input: "1 - -6" --> output: 1, 2, 3, 4, 5, 6\
    input: "0 - 0" --> output: 0\
    input: "1, 4-6, 2" --> output: 1, 2, 4, 5, 6\
    input: "6,3-1" --> output: 1, 2, 3, 6\
<?php\
define('RANGE_ARRAY_SORT', 1);\
define('RANGE_ARRAY', 2);\
define('RANGE_STRING_SORT', 3);\
define('RANGE_STRING', 4);\
function range_string($range_str, $output_type = RANGE_ARRAY_SORT)\
{\
    // Remove spaces and nother non-essential characters\
    $find[]    = "/[^\d,\-]/";\
    $replace[] = "";\
\
    // Remove duplicate hyphens\
    $find[]    = "/\-+/";\
    $replace[] = "-";\
\
    // Remove duplicate commas\
    $find[]    = "/\,+/";\
    $replace[] = ",";\
\
    $range_str = preg_replace($find, $replace, $range_str);\
    // Remove any commas or hypens from the end of the string\
    $range_str = trim($range_str,",-");\
\
    $range_out = array();\
    $ranges    = explode(",", $range_str);\
\
    foreach($ranges as $range)\
    {\
\
        if(is_numeric($range) || strlen($range) == 1)\
        {\
            // Just a number; add it to the list.\
            $range_out[] = (int) $range;\
        }\
        else if(is_string($range))\
        {\
\
            // Is probably a range of values.\
           $range_exp = preg_split("/(\D)/",$range,-1,PREG_SPLIT_DELIM_CAPTURE);\
\
            $start = $range_exp[0];\
            $end   = $range_exp[2];\
\
            if($start > $end)\
            {\
                for($i = $start; $i >= $end; $i -= 1)\
                {\
                    $range_out[] = (int) $i;\
                }\
            }\
            else\
            {\
                for($i = $start; $i <= $end; $i += 1)\
                {\
                    $range_out[] = (int) $i;\
                }\
            }\
\
        }\
    }\
\
    switch ($output_type) {\
        case RANGE_ARRAY_SORT:\
            $range_out = array_unique($range_out);\
            sort($range_out);\
\
        case RANGE_ARRAY:\
            return $range_out;\
            break;\
\
        case RANGE_STRING_SORT:\
            $range_out = array_unique($range_out);\
            sort($range_out);\
\
        case RANGE_STRING:\
\
        default:\
            return implode(", ", $range_out);\
            break;\
    }\
}\
// Sample Usage:\
$range = range_string("6, 3-1");\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=82104&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=82104&page=function.range&vote=down "Vote down!")\
\
5\
\
\
[**_captvanhalen at gmail dot com_**](https://www.php.net/manual/en/function.range.php#82104) [¶](https://www.php.net/manual/en/function.range.php#82104)\
\
**17 years ago**\
\
`Here is a home rolled range() function that uses the step feature for those unfortunate souls who cannot use PHP5:\
<?php\
function my_range( $start, $end, $step = 1) {\
    $range = array();\
    foreach (range( $start, $end ) as $index) {\
        if (! (($index - $start) % $step) ) {\
            $range[] = $index;\
        }\
    }\
    return $range;\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=107440&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=107440&page=function.range&vote=down "Vote down!")\
\
5\
\
\
[**_dries at volta dot be_**](https://www.php.net/manual/en/function.range.php#107440) [¶](https://www.php.net/manual/en/function.range.php#107440)\
\
**13 years ago**\
\
`Ever wanted to generate an array with a range of column names for use in Excel file related parsing?\
I've wrote a function that starts at the A column and adds column names up until the column you specified.\
<?php\
/**\
* This function creates an array with column names up until the column\
* you specified.\
*/\
function createColumnsArray($end_column, $first_letters = '')\
{\
$columns = array();\
$length = strlen($end_column);\
$letters = range('A', 'Z');\
// Iterate over 26 letters.\
foreach ($letters as $letter) {\
      // Paste the $first_letters before the next.\
      $column = $first_letters . $letter;\
      // Add the column to the final array.\
      $columns[] = $column;\
      // If it was the end column that was added, return the columns.\
      if ($column == $end_column)\
          return $columns;\
}\
// Add the column children.\
foreach ($columns as $column) {\
      // Don't itterate if the $end_column was already set in a previous itteration.\
      // Stop iterating if you've reached the maximum character length.\
      if (!in_array($end_column, $columns) && strlen($column) < $length) {\
          $new_columns = createColumnsArray($end_column, $column);\
          // Merge the new columns which were created with the final columns array.\
          $columns = array_merge($columns, $new_columns);\
      }\
}\
return $columns;\
}\
?>\
Usage:\
<?php\
// Return an array with all column names from A until and with BI.\
createColumnsArray('BI');\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=113024&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=113024&page=function.range&vote=down "Vote down!")\
\
2\
\
\
[**_krdr dot mft at gmail dot com_**](https://www.php.net/manual/en/function.range.php#113024) [¶](https://www.php.net/manual/en/function.range.php#113024)\
\
**12 years ago**\
\
`I've been introduced with range() function not so long ago, and I found that examples about it is somewhat wrong, even inefficient:\
<?php\
$o = "";\
$time_start = microtime(true);\
foreach(range(1, 10000) as $val) {\
    $o .= $val;\
}\
$time_end = microtime(true);\
$time = $time_end - $time_start;\
echo 'rangein: '.$time.'<br />';\
$o = "";\
$time_start = microtime(true);\
$a = range(1, 10000);\
foreach($a as $val) {\
    $o .= $val;\
}\
$time_end = microtime(true);\
$time = $time_end - $time_start;\
echo 'rangeout: '.$time.'<br />';\
?>\
Which gives results:\
rangein: 0.0025348663330078\
rangeout: 0.0019199848175049\
In some cases difference is even bigger and proportional to the range generated. I suppose that results of range() are cached/hashed.\
Note: execution order does affects execution times, but difference still exists`\
\
[up](https://www.php.net/manual/vote-note.php?id=118692&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=118692&page=function.range&vote=down "Vote down!")\
\
1\
\
\
[**_qz_**](https://www.php.net/manual/en/function.range.php#118692) [¶](https://www.php.net/manual/en/function.range.php#118692)\
\
**9 years ago**\
\
`If you're looking to fill an array to get a hash with 0-9 numerical values, using\
range(0,9);\
is a faster solution compared to\
array_fill(0, 10, '');`\
\
[up](https://www.php.net/manual/vote-note.php?id=70989&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=70989&page=function.range&vote=down "Vote down!")\
\
1\
\
\
[**_manuel at levante dot de_**](https://www.php.net/manual/en/function.range.php#70989) [¶](https://www.php.net/manual/en/function.range.php#70989)\
\
**18 years ago**\
\
`<?php\
function srange ($s) {\
preg_match_all("/([0-9]{1,2})-?([0-9]{0,2}) ?,?;?/", $s, $a);\
$n = array ();\
foreach ($a[1] as $k => $v) {\
    $n  = array_merge ($n, range ($v, (empty($a[2][$k])?$v:$a[2][$k])));\
}\
return ($n);\
}\
$s = '1-4 6-7 9-10';\
print_r(srange($s));\
?>\
Return:\
Array\
(\
    [0] => 1\
    [1] => 2\
    [2] => 3\
    [3] => 4\
    [4] => 6\
    [5] => 7\
    [6] => 9\
    [7] => 10\
)`\
\
[up](https://www.php.net/manual/vote-note.php?id=128888&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=128888&page=function.range&vote=down "Vote down!")\
\
1\
\
\
[**_VivienG_**](https://www.php.net/manual/en/function.range.php#128888) [¶](https://www.php.net/manual/en/function.range.php#128888)\
\
**2 years ago**\
\
`They forgot to say something.\
If the ending value not encounter the last sequence, the function return false.\
In other words :\
Given a int $n, if ( $start + $n * $step ) < $end and  ( $start + ( $n + 1 ) * $step ) > $end, the function doen't give the maximum possible range, it returns a boolean.\
So the last range number HAVE TO BE the end number.`\
\
[up](https://www.php.net/manual/vote-note.php?id=126749&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=126749&page=function.range&vote=down "Vote down!")\
\
1\
\
\
[**_mohammed dot hussein dot mahmoud at gmail dot com_**](https://www.php.net/manual/en/function.range.php#126749) [¶](https://www.php.net/manual/en/function.range.php#126749)\
\
**3 years ago**\
\
``You could use negative numbers in place of the `step` parameter. You need to make sure that the `start` is bigger than `end`. Note that range() function in php generates the range inclusive, i.e. it also includes the `end` parameter and not just up to it but not including it like most other languages.\
The following snippet of code should explain what I mean about negative steps:\
<?php\
// 100, 90, 80, 70, 60, 50, 40, 30, 20, 10, 0\
print_r(range(100, 0, -10));\
?>\
What happens basically is that the range function does not really care about what is bigger or smaller, it just adds the step to the start and appends that to the a temp result variable as long as it did not reach the end param value. In this case, adding negative numbers is like minus (computers do that for 2's complement under the hood.) This will cause the number to go from 100 to 90 and then the function will check if 90 reached 0 yet. Since it wouldn't have done that, it will keep adding -step (-10 in that case) to the latest result (i.e. 90) and so on and so forth.\
Since range() is said to be better and faster than array_fill() I believe it was important for me to try it out and actually post this note on the official documentation just to make sure people can use this.``\
\
[up](https://www.php.net/manual/vote-note.php?id=114938&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=114938&page=function.range&vote=down "Vote down!")\
\
0\
\
\
[**_lsblsb at gmx dot de_**](https://www.php.net/manual/en/function.range.php#114938) [¶](https://www.php.net/manual/en/function.range.php#114938)\
\
**11 years ago**\
\
`I needed a function, that creates a letter range with arbitrary length.\
You specify via the $length parameter, how many entries you need.\
Logic is analog to the logic of the column-titles in a calc-sheet.\
<?php\
/**\
* create a letter range with arbitrary length\
* @param int $length\
* @return array\
*/\
function createLetterRange($length)\
{\
    $range = array();\
    $letters = range('A', 'Z');\
    for($i=0; $i<$length; $i++)\
    {\
        $position = $i*26;\
        foreach($letters as $ii => $letter)\
        {\
            $position++;\
            if($position <= $length)\
                $range[] = ($position > 26 ? $range[$i-1] : '').$letter;\
        }\
    }\
    return $range;\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=52644&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=52644&page=function.range&vote=down "Vote down!")\
\
0\
\
\
[**_derek at php dot net_**](https://www.php.net/manual/en/function.range.php#52644) [¶](https://www.php.net/manual/en/function.range.php#52644)\
\
**20 years ago**\
\
`This should emulate range() a little better.\
<?php\
function range_wroar($low, $high, $step = 1) {\
    $arr = array();\
    $step = (abs($step)>0)?abs($step):1;\
    $sign = ($low<=$high)?1:-1;\
    if(is_numeric($low) && is_numeric($high)) {\
        //numeric sequence\
        for ($i = (float)$low; $i*$sign <= $high*$sign; $i += $step*$sign)\
            $arr[] = $i;\
    }    else    {\
        //character sequence\
        if (is_numeric($low))\
            return $this->range($low, 0, $step);\
        if (is_numeric($high))\
            return $this->range(0, $high, $step);\
        $low = ord($low);\
        $high = ord($high);\
        for ($i = $low; $i*$sign <= $high*$sign; $i += $step*$sign) {\
\
            $arr[] = chr($i);\
        }\
    }\
    return $arr;\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=113327&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=113327&page=function.range&vote=down "Vote down!")\
\
 -1\
\
\
[**_pyetrosafe at gmail dot com_**](https://www.php.net/manual/en/function.range.php#113327) [¶](https://www.php.net/manual/en/function.range.php#113327)\
\
**12 years ago**\
\
`To create a simple array or a multidimensional array with defined size and null values​​, use this expression:\
<?php\
$SimpleArray = array_map(function($n) { return null; }, range(1, 3) );\
$MultiArray = array_map(function($n) { return array_map(function($n) { return null; }, range(1, 2) ); }, range(1, 3) );\
var_dump($SimpleArray);\
var_dump($MultiArray);\
// And will print:\
?>\
>>$SimpleArray\
array(3) {\
[0]=>  NULL\
[1]=>  NULL\
[2]=>  NULL\
}\
>>$MultiArray\
array(3) {\
[0]=>  array(2) {\
    [0]=>    NULL\
    [1]=>    NULL\
}\
[1]=>  array(2) {\
    [0]=>    NULL\
    [1]=>    NULL\
}\
[2]=>  array(2) {\
    [0]=>    NULL\
    [1]=>    NULL\
}\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=56023&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=56023&page=function.range&vote=down "Vote down!")\
\
 -2\
\
\
[**_emory underscore smith at hotmail_**](https://www.php.net/manual/en/function.range.php#56023) [¶](https://www.php.net/manual/en/function.range.php#56023)\
\
**20 years ago**\
\
`since its not stated explicitly above, thought id point out that you arent limited to using integers.\
however, be careful when doing so, as you might not get the range you expect!\
to illustrate:\
<?php\
$am = range(500,1600,10);\
$fm = range(88.1,107.9,.2);\
print_r($am);\
print_r($fm);\
?>\
print_r($am) yields the expected result:\
\
Array\
(\
    [0] => 500\
    [1] => 510\
    [2] => 520\
    ...\
    [109] => 1590\
    [110] => 1600\
)\
print_r($fm), however, falls a bit (1%) short:\
Array\
(\
    [0] => 88.1\
    [1] => 88.3\
    [2] => 88.5\
    ...\
    [97] => 107.5\
    [98] => 107.7\
)\
\
so, if you want to use a non-integral step size params for numeric ranges, be sure to account for fp representation accuracy and error accumulation; a step size of something like pi or 1/10 could spell disaster for a large range. if in doubt, use integral steps and divide ... something like <?php range(88.1,108,.2) ?> might work to recover 107.9, but would not be scalable like, say <?php array_map(create_function('$x','return $x/10;'),range(881,1079,2)) ?>.\
-emory`\
\
[up](https://www.php.net/manual/vote-note.php?id=60479&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=60479&page=function.range&vote=down "Vote down!")\
\
 -2\
\
\
[**_subscription101 at hotmail dot com_**](https://www.php.net/manual/en/function.range.php#60479) [¶](https://www.php.net/manual/en/function.range.php#60479)\
\
**19 years ago**\
\
`A much simpler way of creating a range of even numbers is by starting with an even number:\
<?php\
    range(2, 10, 2);\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=45913&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=45913&page=function.range&vote=down "Vote down!")\
\
 -2\
\
\
[**_j dot gizmo at aon dot at_**](https://www.php.net/manual/en/function.range.php#45913) [¶](https://www.php.net/manual/en/function.range.php#45913)\
\
**21 years ago**\
\
`i figured i'd add some more functionality to the myRange() functions below.\
now you can, besides giving a $step parameter,\
1. count backwards\
2. count with letters\
3. give whatever parameter you want, there's nothing (i know of) that will cause an endless loop (try a negative $step for the previous function....)\
<?php\
function myRange($num1, $num2, $step=1)\
{\
    if (is_numeric($num1) && is_numeric($num2))\
    {\
        //we have a numeric range\
        $step = ( abs($step)>0 ? abs($step) : 1 ); //make $step positive\
        $dir = ($num1<=$num2 ? 1 : -1); //get the direction\
        for($i = (float)$num1; $i*$dir <= $num2*$dir; $i += $step*$dir)\
        {\
            $temp[] = $i;\
        }\
    }\
    else\
    {\
        //we have a character range\
        $num1=ord((string)$num1); //convert to ascii value\
        $num2=ord((string)$num2);\
        $step = ( abs($step)>0 ? abs($step) : 1 ); //make $step positive\
        $dir = ($num1<=$num2 ? 1 : -1); //get direction\
        for($i = $num1; $i*$dir <= $num2*$dir; $i += $step*$dir)\
        {\
            $temp[] = chr($i);\
        }\
    }\
    return $temp;\
}\
print_r(myRange( 1, 3, 0.5 )); //you can use fractional steps\
print_r(myRange( "a", "k", 3 )); //or count letters\
print_r(myRange( "5", "9" )); //numbers are detected even if hidden in strtings\
print_r(myRange( "!", "%", 1/pi() )); //or mess around with senseless parameters\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=115933&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=115933&page=function.range&vote=down "Vote down!")\
\
 -4\
\
\
[**_unicod3 at hotmail dot com_**](https://www.php.net/manual/en/function.range.php#115933) [¶](https://www.php.net/manual/en/function.range.php#115933)\
\
**11 years ago**\
\
`a function to get column index by letter\
\
function getColumnNumber($char){\
    $alphabet = range('a','z');\
    $alphabet2 = range('a','z');\
    $newAlphabet = $alphabet;\
    foreach($alphabet as $k => $r)\
    {\
        foreach($alphabet2 as $row){\
            $newAlphabet[] = $r.$row;\
        }\
    }\
    $key = array_search($char, $newAlphabet);\
    return ($key !== false) ? $key : null;\
}`\
\
[up](https://www.php.net/manual/vote-note.php?id=102666&page=function.range&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=102666&page=function.range&vote=down "Vote down!")\
\
 -5\
\
\
[**_Aram Kocharyan_**](https://www.php.net/manual/en/function.range.php#102666) [¶](https://www.php.net/manual/en/function.range.php#102666)\
\
**14 years ago**\
\
`Here's a function to generate ranges from strings:\
<?php\
/*  Creates an array of integers based on a given range string of format "int - int"\
    Eg. range_str('2 - 5'); */\
function range_str($str) {\
    preg_match('#(\\d+)\\s*-\\s*(\\d+)#', $str, $matches);\
    if ( count($matches) == 3 ) {\
        return range($matches[1], $matches[2]);\
    }\
    return FALSE;\
}\
// Test\
$array = range_str(' 2 - 4 ');\
print_r($array);\
?>\
This outputs:\
Array\
(\
    [0] => 2\
    [1] => 3\
    [2] => 4\
)`\
\
[＋add a note](https://www.php.net/manual/add-note.php?sect=function.range&repo=en&redirect=https://www.php.net/manual/en/function.range.php)\
\
![To Top](https://www.php.net/images/to-top@2x.png)\
\
`↑` and `↓` to navigate •\
`Enter` to select •\
`Esc` to close\
\
\
Press `Enter` without\
selection to search using Google