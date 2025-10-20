---
url: https://www.php.net/manual/en/function.similar-text.php
scraped_at: 2025-10-20T02:53:38.462Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# similar\_text

(PHP 4, PHP 5, PHP 7, PHP 8)

similar\_text — Calculate the similarity between two strings

### Description [¶](https://www.php.net/manual/en/function.similar-text.php\#refsect1-function.similar-text-description)

**similar\_text**([string](https://www.php.net/manual/en/language.types.string.php) `$string1`, [string](https://www.php.net/manual/en/language.types.string.php) `$string2`, [float](https://www.php.net/manual/en/language.types.float.php) `&$percent` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [int](https://www.php.net/manual/en/language.types.integer.php)

This calculates the similarity between two strings as described in
Programming Classics: Implementing the World's Best Algorithms by Oliver (ISBN 0-131-00413-1). Note that this implementation does not use a
stack as in Oliver's pseudo code, but recursive calls which may or may not
speed up the whole process. Note also that the complexity of this algorithm
is O(N\*\*3) where N is the length of the longest string.


### Parameters [¶](https://www.php.net/manual/en/function.similar-text.php\#refsect1-function.similar-text-parameters)

`string1`

The first string.


`string2`

The second string.


> **Note**:
>
>
> Swapping the `string1` and
> `string2` may yield a different result; see the
> example below.

`percent`

By passing a reference as third argument,
**similar\_text()** will calculate the similarity in
percent, by dividing the result of **similar\_text()** by
the average of the lengths of the given strings times
`100`.


### Return Values [¶](https://www.php.net/manual/en/function.similar-text.php\#refsect1-function.similar-text-returnvalues)

Returns the number of matching chars in both strings.


The number of matching characters is calculated by finding the longest first
common substring, and then doing this for the prefixes and the suffixes,
recursively. The lengths of all found common substrings are added.


### Examples [¶](https://www.php.net/manual/en/function.similar-text.php\#refsect1-function.similar-text-examples)

**Example #1 **similar\_text()** argument swapping example**

This example shows that swapping the `string1` and
`string2` argument may yield different results.


`<?php
$sim = similar_text('bafoobar', 'barfoo', $perc);
echo "similarity: $sim ($perc %)\n";
$sim = similar_text('barfoo', 'bafoobar', $perc);
echo "similarity: $sim ($perc %)\n";`

Run code

The above example will output
something similar to:

```
similarity: 5 (71.428571428571 %)
similarity: 3 (42.857142857143 %)
```

### See Also [¶](https://www.php.net/manual/en/function.similar-text.php\#refsect1-function.similar-text-seealso)

- [levenshtein()](https://www.php.net/manual/en/function.levenshtein.php) \- Calculate Levenshtein distance between two strings
- [metaphone()](https://www.php.net/manual/en/function.metaphone.php) \- Calculate the metaphone key of a string
- [soundex()](https://www.php.net/manual/en/function.soundex.php) \- Calculate the soundex key of a string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/similar-text.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.similar-text%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.similar-text&repo=en&redirect=https://www.php.net/manual/en/function.similar-text.php)

### User Contributed Notes 11 notes

[up](https://www.php.net/manual/vote-note.php?id=109507&page=function.similar-text&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109507&page=function.similar-text&vote=down "Vote down!")

118


[**_SPAM HATER_**](https://www.php.net/manual/en/function.similar-text.php#109507) [¶](https://www.php.net/manual/en/function.similar-text.php#109507)

**13 years ago**

`Hey there,
Be aware when using this function, that the order of passing the strings is very important if you want to calculate the percentage of similarity, in fact, altering the variables will give a very different result, example :
<?php
$var_1 = 'PHP IS GREAT';
$var_2 = 'WITH MYSQL';
similar_text($var_1, $var_2, $percent);
echo $percent;
// 27.272727272727
similar_text($var_2, $var_1, $percent);
echo $percent;
// 18.181818181818
?>`

[up](https://www.php.net/manual/vote-note.php?id=101458&page=function.similar-text&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101458&page=function.similar-text&vote=down "Vote down!")

102


[**_daniel dot karbach at localhorst dot tv_**](https://www.php.net/manual/en/function.similar-text.php#101458) [¶](https://www.php.net/manual/en/function.similar-text.php#101458)

**14 years ago**

`Please note that this function calculates a similarity of 0 (zero) for two empty strings.
<?php
similar_text("", "", $sim);
echo $sim; // "0"
?>`

[up](https://www.php.net/manual/vote-note.php?id=115994&page=function.similar-text&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115994&page=function.similar-text&vote=down "Vote down!")

37


[**_I\_HATE\_SPAMMER- PAZ!_**](https://www.php.net/manual/en/function.similar-text.php#115994) [¶](https://www.php.net/manual/en/function.similar-text.php#115994)

**10 years ago**

`Actually similar_text() is not bad...
it works good. But before processing i think is a good way to make a little mod like this
$var_1 = strtoupper("doggy");
$var_2 = strtoupper("Dog");
similar_text($var_1, $var_2, $percent);
echo $percent; // output is 75 but without strtoupper output is 50`

[up](https://www.php.net/manual/vote-note.php?id=118799&page=function.similar-text&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118799&page=function.similar-text&vote=down "Vote down!")

20


[**_vasyl at vasyltech dot com_**](https://www.php.net/manual/en/function.similar-text.php#118799) [¶](https://www.php.net/manual/en/function.similar-text.php#118799)

**9 years ago**

`Recursive algorithm usually is very elegant one. I found a way to get better precision without the recursion. Imagine two different (or same) length ribbons with letters on each. You simply shifting one ribbon to left till it matches the letter the first.
<?php
function similarity($str1, $str2) {
    $len1 = strlen($str1);
    $len2 = strlen($str2);

    $max = max($len1, $len2);
    $similarity = $i = $j = 0;

    while (($i < $len1) && isset($str2[$j])) {
        if ($str1[$i] == $str2[$j]) {
            $similarity++;
            $i++;
            $j++;
        } elseif ($len1 < $len2) {
            $len1++;
            $j++;
        } elseif ($len1 > $len2) {
            $i++;
            $len1--;
        } else {
            $i++;
            $j++;
        }
    }
    return round($similarity / $max, 2);
}
$str1 = '12345678901234567890';
$str2 = '12345678991234567890';
echo 'Similarity: ' . (similarity($str1, $str2) * 100) . '%';
?>`

[up](https://www.php.net/manual/vote-note.php?id=114540&page=function.similar-text&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114540&page=function.similar-text&vote=down "Vote down!")

22


[**_ryan at derokorian dot com_**](https://www.php.net/manual/en/function.similar-text.php#114540) [¶](https://www.php.net/manual/en/function.similar-text.php#114540)

**11 years ago**

`Note that this function is case sensitive:
<?php
$var1 = 'Hello';
$var2 = 'Hello';
$var3 = 'hello';
echo similar_text($var1, $var2);  // 5
echo similar_text($var1, $var3);  // 4`

[up](https://www.php.net/manual/vote-note.php?id=15947&page=function.similar-text&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=15947&page=function.similar-text&vote=down "Vote down!")

13


[**_daniel at reflexionsdesign dot com_**](https://www.php.net/manual/en/function.similar-text.php#15947) [¶](https://www.php.net/manual/en/function.similar-text.php#15947)

**24 years ago**

`If performance is an issue, you may wish to use the levenshtein() function instead, which has a considerably better complexity of O(str1 * str2).`

[up](https://www.php.net/manual/vote-note.php?id=29221&page=function.similar-text&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=29221&page=function.similar-text&vote=down "Vote down!")

16


[**_julius at infoguiden dot no_**](https://www.php.net/manual/en/function.similar-text.php#29221) [¶](https://www.php.net/manual/en/function.similar-text.php#29221)

**22 years ago**

`If you have reserved names in a database that you don't want others to use, i find this to work pretty good.
I added strtoupper to the variables to validate typing only. Taking case into consideration will decrease similarity.
<?php
$query = mysql_query("select * from $table") or die("Query failed");
while ($row = mysql_fetch_array($query)) {
      similar_text(strtoupper($_POST['name']), strtoupper($row['reserved']), $similarity_pst);
      if (number_format($similarity_pst, 0) > 90){
        $too_similar = $row['reserved'];
        print "The name you entered is too similar the reserved name &quot;".$row['reserved']."&quot;";
        break;
       }
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=125033&page=function.similar-text&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125033&page=function.similar-text&vote=down "Vote down!")

4


[**_Anonymous_**](https://www.php.net/manual/en/function.similar-text.php#125033) [¶](https://www.php.net/manual/en/function.similar-text.php#125033)

**5 years ago**

`$result = similar_text ('ab', 'a', $percent);
> $percent: 66.666666666666671`

[up](https://www.php.net/manual/vote-note.php?id=72448&page=function.similar-text&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72448&page=function.similar-text&vote=down "Vote down!")

11


[**_Paul_**](https://www.php.net/manual/en/function.similar-text.php#72448) [¶](https://www.php.net/manual/en/function.similar-text.php#72448)

**18 years ago**

`The speed issues for similar_text seem to be only an issue for long sections of text (>20000 chars).
I found a huge performance improvement in my application by just testing if the string to be tested was less than 20000 chars before calling similar_text.
20000+ took 3-5 secs to process, anything else (10000 and below) took a fraction of a second.
Fortunately for me, there was only a handful of instances with >20000 chars which I couldn't get a comparison % for.`

[up](https://www.php.net/manual/vote-note.php?id=19734&page=function.similar-text&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=19734&page=function.similar-text&vote=down "Vote down!")

4


[**_georgesk at hotmail dot com_**](https://www.php.net/manual/en/function.similar-text.php#19734) [¶](https://www.php.net/manual/en/function.similar-text.php#19734)

**23 years ago**

`Well, as mentioned above the speed is O(N^3), i've done a longest common subsequence way that is O(m.n) where m and n are the length of str1 and str2, the result is a percentage and it seems to be exactly the same as similar_text percentage but with better performance... here's the 3 functions i'm using..
<?php
function LCS_Length($s1, $s2)
{
$m = strlen($s1);
$n = strlen($s2);
//this table will be used to compute the LCS-Length, only 128 chars per string are considered
$LCS_Length_Table = array(array(128),array(128));


//reset the 2 cols in the table
for($i=1; $i < $m; $i++) $LCS_Length_Table[$i][0]=0;
for($j=0; $j < $n; $j++) $LCS_Length_Table[0][$j]=0;
for ($i=1; $i <= $m; $i++) {
    for ($j=1; $j <= $n; $j++) {
      if ($s1[$i-1]==$s2[$j-1])
        $LCS_Length_Table[$i][$j] = $LCS_Length_Table[$i-1][$j-1] + 1;
      else if ($LCS_Length_Table[$i-1][$j] >= $LCS_Length_Table[$i][$j-1])
        $LCS_Length_Table[$i][$j] = $LCS_Length_Table[$i-1][$j];
      else
        $LCS_Length_Table[$i][$j] = $LCS_Length_Table[$i][$j-1];
    }
}
return $LCS_Length_Table[$m][$n];
}
function str_lcsfix($s)
{
$s = str_replace(" ","",$s);
$s = ereg_replace("[��������]","e", $s);
$s = ereg_replace("[������������]","a", $s);
$s = ereg_replace("[��������]","i", $s);
$s = ereg_replace("[���������]","o", $s);
$s = ereg_replace("[��������]","u", $s);
$s = ereg_replace("[�]","c", $s);
return $s;
}

function get_lcs($s1, $s2)
{
//ok, now replace all spaces with nothing
$s1 = strtolower(str_lcsfix($s1));
$s2 = strtolower(str_lcsfix($s2));

$lcs = LCS_Length($s1,$s2); //longest common sub sequence
$ms = (strlen($s1) + strlen($s2)) / 2;
return (($lcs*100)/$ms);
}
?>
you can skip calling str_lcsfix if you don't worry about accentuated characters and things like that or you can add up to it or modify it for faster performance, i think ereg is not the fastest way?
hope this helps.
Georges`

[up](https://www.php.net/manual/vote-note.php?id=125738&page=function.similar-text&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125738&page=function.similar-text&vote=down "Vote down!")

 -1


[**_pablo dot pazos at cabolabs dot com_**](https://www.php.net/manual/en/function.similar-text.php#125738) [¶](https://www.php.net/manual/en/function.similar-text.php#125738)

**4 years ago**

`To calculate the percentage of similarity between two strings without depending on the order of the parameters and be case insensitive, I use this function based on levenshtein's distance:
<?php
// string similarity calculated using levenshtein
static function similarity($a, $b)
{
    return 1 - (levenshtein(strtoupper($a), strtoupper($b)) / max(strlen($a), strlen($b)));
}
?>
This will always return a number between 0 and 1, representing the percentage, for instance 0.8 represents 80% similar strings.
If you want this to be case-sensitive, just remove the strtoupper() functions.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.similar-text&repo=en&redirect=https://www.php.net/manual/en/function.similar-text.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google