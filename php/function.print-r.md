---
url: https://www.php.net/manual/en/function.print-r.php
scraped_at: 2025-10-20T02:41:34.030Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# print\_r

(PHP 4, PHP 5, PHP 7, PHP 8)

print\_r —
Prints human-readable information about a variable


### Description [¶](https://www.php.net/manual/en/function.print-r.php\#refsect1-function.print-r-description)

**print\_r**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$value`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$return` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**): [string](https://www.php.net/manual/en/language.types.string.php)\|[true](https://www.php.net/manual/en/language.types.singleton.php)

**print\_r()** displays information about a variable
in a way that's readable by humans.


**print\_r()**, [var\_dump()](https://www.php.net/manual/en/function.var-dump.php) and
[var\_export()](https://www.php.net/manual/en/function.var-export.php) will
also show protected and private properties of objects.
Static class members will not be shown.


### Parameters [¶](https://www.php.net/manual/en/function.print-r.php\#refsect1-function.print-r-parameters)

`value`

The expression to be printed.


`return`

If you would like to capture the output of **print\_r()**,
use the `return` parameter. When this parameter is set
to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, **print\_r()** will return the information rather than print it.


### Return Values [¶](https://www.php.net/manual/en/function.print-r.php\#refsect1-function.print-r-returnvalues)

If given a [string](https://www.php.net/manual/en/language.types.string.php), [int](https://www.php.net/manual/en/language.types.integer.php) or [float](https://www.php.net/manual/en/language.types.float.php),
the value itself will be printed. If given an [array](https://www.php.net/manual/en/language.types.array.php), values
will be presented in a format that shows keys and elements. Similar
notation is used for [object](https://www.php.net/manual/en/language.types.object.php)s.


When the `return` parameter is **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, this function
will return a [string](https://www.php.net/manual/en/language.types.string.php). Otherwise, the return value is **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.


### Changelog [¶](https://www.php.net/manual/en/function.print-r.php\#refsect1-function.print-r-changelog)

| Version | Description |
| --- | --- |
| 8.4.0 | Return type changed from [string](https://www.php.net/manual/en/language.types.string.php)\|[bool](https://www.php.net/manual/en/language.types.boolean.php) to [string](https://www.php.net/manual/en/language.types.string.php)\|[true](https://www.php.net/manual/en/language.types.singleton.php). |

### Examples [¶](https://www.php.net/manual/en/function.print-r.php\#refsect1-function.print-r-examples)

**Example #1 **print\_r()** example**

`<pre>
<?php
$a = array ('a' => 'apple', 'b' => 'banana', 'c' => array ('x', 'y', 'z'));
print_r($a);
?>
</pre>`

Run code

The above example will output:

```
<pre>
Array
(
    [a] => apple
    [b] => banana
    [c] => Array
        (
            [0] => x
            [1] => y
            [2] => z
        )
)
</pre>
```

**Example #2 `return` parameter example**

`<?php
$b = array ('m' => 'monkey', 'foo' => 'bar', 'x' => array ('x', 'y', 'z'));
$results = print_r($b, true); // $results now contains output from print_r
print_r($results);
?>`

Run code

### Notes [¶](https://www.php.net/manual/en/function.print-r.php\#refsect1-function.print-r-notes)

> **Note**:
>
> When the `return` parameter
> is used, this function uses internal output buffering prior to PHP 7.1.0, so it cannot be used inside an
> [ob\_start()](https://www.php.net/manual/en/function.ob-start.php) callback function.

### See Also [¶](https://www.php.net/manual/en/function.print-r.php\#refsect1-function.print-r-seealso)

- [ob\_start()](https://www.php.net/manual/en/function.ob-start.php) \- Turn on output buffering
- [var\_dump()](https://www.php.net/manual/en/function.var-dump.php) \- Dumps information about a variable
- [var\_export()](https://www.php.net/manual/en/function.var-export.php) \- Outputs or returns a parsable string representation of a variable

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/functions/print-r.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.print-r%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.print-r&repo=en&redirect=https://www.php.net/manual/en/function.print-r.php)

### User Contributed Notes 16 notes

[up](https://www.php.net/manual/vote-note.php?id=96023&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96023&page=function.print-r&vote=down "Vote down!")

167


[**_liamtoh6 at hotmail dot com_**](https://www.php.net/manual/en/function.print-r.php#96023) [¶](https://www.php.net/manual/en/function.print-r.php#96023)

**15 years ago**

`I add this function to the global scope on just about every project I do, it makes reading the output of print_r() in a browser infinitely easier.
<?php
function print_r2($val){
        echo '<pre>';
        print_r($val);
        echo  '</pre>';
}
?>
It also makes sense in some cases to add an if statement to only display the output in certain scenarios, such as:
if(debug==true)
if($_SERVER['REMOTE_ADDR'] == '127.0.0.1')`

[up](https://www.php.net/manual/vote-note.php?id=121259&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121259&page=function.print-r&vote=down "Vote down!")

22


[**_simivar at gmail dot com_**](https://www.php.net/manual/en/function.print-r.php#121259) [¶](https://www.php.net/manual/en/function.print-r.php#121259)

**8 years ago**

`I've fixed function wrote by Matt to reverse print_r - it had problems with null values. Created a GIST for that too so please add any future fixes in there instead of this comment section:
[https://gist.github.com/simivar/037b13a9bbd53ae5a092d8f6d9828bc3](https://gist.github.com/simivar/037b13a9bbd53ae5a092d8f6d9828bc3)
<?php
/**
* Matt: core
* Trixor: object handling
* lech: Windows suppport
* simivar: null support
*
* @see [http://php.net/manual/en/function.print-r.php](http://php.net/manual/en/function.print-r.php)
**/
function print_r_reverse($input) {
        $lines = preg_split('#\r?\n#', trim($input));
        if (trim($lines[ 0 ]) != 'Array' && trim($lines[ 0 ] != 'stdClass Object')) {
            // bottomed out to something that isn't an array or object
            if ($input === '') {
                return null;
            }

            return $input;
        } else {
            // this is an array or object, lets parse it
            $match = array();
            if (preg_match("/(\s{5,})\(/", $lines[ 1 ], $match)) {
                // this is a tested array/recursive call to this function
                // take a set of spaces off the beginning
                $spaces = $match[ 1 ];
                $spaces_length = strlen($spaces);
                $lines_total = count($lines);
                for ($i = 0; $i < $lines_total; $i++) {
                    if (substr($lines[ $i ], 0, $spaces_length) == $spaces) {
                        $lines[ $i ] = substr($lines[ $i ], $spaces_length);
                    }
                }
            }
            $is_object = trim($lines[ 0 ]) == 'stdClass Object';
            array_shift($lines); // Array
            array_shift($lines); // (
            array_pop($lines); // )
            $input = implode("\n", $lines);
            $matches = array();
            // make sure we only match stuff with 4 preceding spaces (stuff for this array and not a nested one)
            preg_match_all("/^\s{4}\[(.+?)\] \=\> /m", $input, $matches, PREG_OFFSET_CAPTURE | PREG_SET_ORDER);
            $pos = array();
            $previous_key = '';
            $in_length = strlen($input);
            // store the following in $pos:
            // array with key = key of the parsed array's item
            // value = array(start position in $in, $end position in $in)
            foreach ($matches as $match) {
                $key = $match[ 1 ][ 0 ];
                $start = $match[ 0 ][ 1 ] + strlen($match[ 0 ][ 0 ]);
                $pos[ $key ] = array($start, $in_length);
                if ($previous_key != '') {
                    $pos[ $previous_key ][ 1 ] = $match[ 0 ][ 1 ] - 1;
                }
                $previous_key = $key;
            }
            $ret = array();
            foreach ($pos as $key => $where) {
                // recursively see if the parsed out value is an array too
                $ret[ $key ] = print_r_reverse(substr($input, $where[ 0 ], $where[ 1 ] - $where[ 0 ]));
            }

            return $is_object ? (object)$ret : $ret;
        }
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=121706&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121706&page=function.print-r&vote=down "Vote down!")

3


[**_Soaku_**](https://www.php.net/manual/en/function.print-r.php#121706) [¶](https://www.php.net/manual/en/function.print-r.php#121706)

**8 years ago**

`liamtoh6@hotmail.com posted a function that will echo print_r output with proper new lines in HTML files. He used <pre> for it to work, but that might not be always the best method to go. For example, it is not valid to place <pre> inside <p>.
Here is my way to do this:
<?php
function print_rbr ($var, $return = false) {
$r = nl2br(htmlspecialchars(print_r($var, true)));
if ($return) return $r;
else echo $r;
}
?>
This function will:
- Place <br> where newlines are,
- Escape unsecure characters with HTML entities.`

[up](https://www.php.net/manual/vote-note.php?id=75872&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75872&page=function.print-r&vote=down "Vote down!")

10


[**_motin at demomusic dot nu_**](https://www.php.net/manual/en/function.print-r.php#75872) [¶](https://www.php.net/manual/en/function.print-r.php#75872)

**18 years ago**

`This works around the hacky nature of print_r in return mode (using output buffering for the return mode to work is hacky...):
<?php
/**
* An alternative to print_r that unlike the original does not use output buffering with
* the return parameter set to true. Thus, Fatal errors that would be the result of print_r
* in return-mode within ob handlers can be avoided.
*
* Comes with an extra parameter to be able to generate html code. If you need a
* human readable DHTML-based print_r alternative, see [http://krumo.sourceforge.net/](http://krumo.sourceforge.net/)
*
* Support for printing of objects as well as the $return parameter functionality
* added by Fredrik Wollsén (fredrik dot motin at gmail), to make it work as a drop-in
* replacement for print_r (Except for that this function does not output
* paranthesises around element groups... ;) )
*
* Based on return_array() By Matthew Ruivo (mruivo at gmail)
* ( [http://se2.php.net/manual/en/function.print-r.php#73436](http://se2.php.net/manual/en/function.print-r.php#73436))
*/
function obsafe_print_r($var, $return = false, $html = false, $level = 0) {
    $spaces = "";
    $space = $html ? "&nbsp;" : " ";
    $newline = $html ? "<br />" : "\n";
    for ($i = 1; $i <= 6; $i++) {
        $spaces .= $space;
    }
    $tabs = $spaces;
    for ($i = 1; $i <= $level; $i++) {
        $tabs .= $spaces;
    }
    if (is_array($var)) {
        $title = "Array";
    } elseif (is_object($var)) {
        $title = get_class($var)." Object";
    }
    $output = $title . $newline . $newline;
    foreach($var as $key => $value) {
        if (is_array($value) || is_object($value)) {
            $level++;
            $value = obsafe_print_r($value, true, $html, $level);
            $level--;
        }
        $output .= $tabs . "[" . $key . "] => " . $value . $newline;
    }
    if ($return) return $output;
      else echo $output;
}
?>
Built on a function earlier posted in these comments as stated in the Doc comment. Cheers! /Fredrik (Motin)`

[up](https://www.php.net/manual/vote-note.php?id=121039&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121039&page=function.print-r&vote=down "Vote down!")

1


[**_lech_**](https://www.php.net/manual/en/function.print-r.php#121039) [¶](https://www.php.net/manual/en/function.print-r.php#121039)

**8 years ago**

`A slight amendment to Matt's awesome print_r_reverse function (Thank You, a life-saver - data recovery :-) . If the output is copied from a Windows system, the end of lines may include the return character "\r" and so the scalar (string) elements will include a trailing "\r" character that isn't suppose to be there. To resolve, replace the first line in the function with...
<?php $lines = preg_split('#\r?\n#', trim($in)); ?>
This will work for both cases (Linux and Windows).
I include the entire function below for completeness, but all credit to Matt, the original author, Thank You.
<?php
//Author: Matt ( [http://us3.php.net/print\_r](http://us3.php.net/print_r))
function print_r_reverse($in) {
    $lines = preg_split('#\r?\n#', trim($in));
    if (trim($lines[0]) != 'Array') {
        // bottomed out to something that isn't an array
        return $in;
    } else {
        // this is an array, lets parse it
        if (preg_match("/(\s{5,})\(/", $lines[1], $match)) {
            // this is a tested array/recursive call to this function
            // take a set of spaces off the beginning
            $spaces = $match[1];
            $spaces_length = strlen($spaces);
            $lines_total = count($lines);
            for ($i = 0; $i < $lines_total; $i++) {
                if (substr($lines[$i], 0, $spaces_length) == $spaces) {
                    $lines[$i] = substr($lines[$i], $spaces_length);
                }
            }
        }
        array_shift($lines); // Array
        array_shift($lines); // (
        array_pop($lines); // )
        $in = implode("\n", $lines);
        // make sure we only match stuff with 4 preceding spaces (stuff for this array and not a nested one)
        preg_match_all("/^\s{4}\[(.+?)\] \=\> /m", $in, $matches, PREG_OFFSET_CAPTURE | PREG_SET_ORDER);
        $pos = array();
        $previous_key = '';
        $in_length = strlen($in);
        // store the following in $pos:
        // array with key = key of the parsed array's item
        // value = array(start position in $in, $end position in $in)
        foreach ($matches as $match) {
            $key = $match[1][0];
            $start = $match[0][1] + strlen($match[0][0]);
            $pos[$key] = array($start, $in_length);
            if ($previous_key != '') $pos[$previous_key][1] = $match[0][1] - 1;
            $previous_key = $key;
        }
        $ret = array();
        foreach ($pos as $key => $where) {
            // recursively see if the parsed out value is an array too
            $ret[$key] = print_r_reverse(substr($in, $where[0], $where[1] - $where[0]));
        }
        return $ret;
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=93529&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93529&page=function.print-r&vote=down "Vote down!")

16


[**_Matt_**](https://www.php.net/manual/en/function.print-r.php#93529) [¶](https://www.php.net/manual/en/function.print-r.php#93529)

**16 years ago**

`Here is another version that parses the print_r() output. I tried the one posted, but I had difficulties with it. I believe it has a problem with nested arrays. This handles nested arrays without issue as far as I can tell.
<?php
function print_r_reverse($in) {
    $lines = explode("\n", trim($in));
    if (trim($lines[0]) != 'Array') {
        // bottomed out to something that isn't an array
        return $in;
    } else {
        // this is an array, lets parse it
        if (preg_match("/(\s{5,})\(/", $lines[1], $match)) {
            // this is a tested array/recursive call to this function
            // take a set of spaces off the beginning
            $spaces = $match[1];
            $spaces_length = strlen($spaces);
            $lines_total = count($lines);
            for ($i = 0; $i < $lines_total; $i++) {
                if (substr($lines[$i], 0, $spaces_length) == $spaces) {
                    $lines[$i] = substr($lines[$i], $spaces_length);
                }
            }
        }
        array_shift($lines); // Array
        array_shift($lines); // (
        array_pop($lines); // )
        $in = implode("\n", $lines);
        // make sure we only match stuff with 4 preceding spaces (stuff for this array and not a nested one)
        preg_match_all("/^\s{4}\[(.+?)\] \=\> /m", $in, $matches, PREG_OFFSET_CAPTURE | PREG_SET_ORDER);
        $pos = array();
        $previous_key = '';
        $in_length = strlen($in);
        // store the following in $pos:
        // array with key = key of the parsed array's item
        // value = array(start position in $in, $end position in $in)
        foreach ($matches as $match) {
            $key = $match[1][0];
            $start = $match[0][1] + strlen($match[0][0]);
            $pos[$key] = array($start, $in_length);
            if ($previous_key != '') $pos[$previous_key][1] = $match[0][1] - 1;
            $previous_key = $key;
        }
        $ret = array();
        foreach ($pos as $key => $where) {
            // recursively see if the parsed out value is an array too
            $ret[$key] = print_r_reverse(substr($in, $where[0], $where[1] - $where[0]));
        }
        return $ret;
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=61322&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=61322&page=function.print-r&vote=down "Vote down!")

10


[**_reinder at fake-address dot com_**](https://www.php.net/manual/en/function.print-r.php#61322) [¶](https://www.php.net/manual/en/function.print-r.php#61322)

**19 years ago**

`I always use this function in my code, because most of my functions return an Array or Boolean :
<?php
function printr ( $object , $name = '' ) {
    print ( '\'' . $name . '\' : ' ) ;
    if ( is_array ( $object ) ) {
        print ( '<pre>' )  ;
        print_r ( $object ) ;
        print ( '</pre>' ) ;
    } else {
        var_dump ( $object ) ;
    }
}
?>
( print_r gives no output on FALSE and that can be annoying! )`

[up](https://www.php.net/manual/vote-note.php?id=81480&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81480&page=function.print-r&vote=down "Vote down!")

3


[**_anon at anon dot com_**](https://www.php.net/manual/en/function.print-r.php#81480) [¶](https://www.php.net/manual/en/function.print-r.php#81480)

**17 years ago**

`A slight modification to the previous post to allow for arrays containing mutli line strings. haven't fully tested it with everything, but seems to work great for the stuff i've done so far.
<?php
function print_r_reverse(&$output)
{
    $expecting = 0; // 0=nothing in particular, 1=array open paren '(', 2=array element or close paren ')'
    $lines = explode("\n", $output);
    $result = null;
    $topArray = null;
    $arrayStack = array();
    $matches = null;
    while (!empty($lines) && $result === null)
    {
        $line = array_shift($lines);
        $trim = trim($line);
        if ($trim == 'Array')
        {
            if ($expecting == 0)
            {
                $topArray = array();
                $expecting = 1;
            }
            else
            {
                trigger_error("Unknown array.");
            }
        }
        else if ($expecting == 1 && $trim == '(')
        {
            $expecting = 2;
        }
        else if ($expecting == 2 && preg_match('/^\[(.+?)\] \=\> (.+)$/', $trim, $matches)) // array element
        {
            list ($fullMatch, $key, $element) = $matches;
            if (trim($element) == 'Array')
            {
                $topArray[$key] = array();
                $newTopArray =& $topArray[$key];
                $arrayStack[] =& $topArray;
                $topArray =& $newTopArray;
                $expecting = 1;
            }
            else
            {
                $topArray[$key] = $element;
            }
        }
        else if ($expecting == 2 && $trim == ')') // end current array
        {
            if (empty($arrayStack))
            {
                $result = $topArray;
            }
            else // pop into parent array
            {
                // safe array pop
                $keys = array_keys($arrayStack);
                $lastKey = array_pop($keys);
                $temp =& $arrayStack[$lastKey];
                unset($arrayStack[$lastKey]);
                $topArray =& $temp;
            }
        }
        // Added this to allow for multi line strings.
    else if (!empty($trim) && $expecting == 2)
    {
        // Expecting close parent or element, but got just a string
        $topArray[$key] .= "\n".$line;
    }
        else if (!empty($trim))
        {
            $result = $line;
        }
    }

    $output = implode(n, $lines);
    return $result;
}
/**
* @param string $output : The output of a multiple print_r calls, separated by newlines
* @return mixed[] : parseable elements of $output
*/
function print_r_reverse_multiple($output)
{
    $result = array();
    while (($reverse = print_r_reverse($output)) !== NULL)
    {
        $result[] = $reverse;
    }
    return $result;
}
$output = '
Array
(
    [a] => apple
    [b] => banana
    [c] => Array
        (
            [0] => x
            [1] => y
            [2] => z
            [3] => Array
            (
                [nest] => yes
                [nest2] => Array
                (
                    [nest] => some more
                    asffjaskkd
                )
                [nest3] => o rly?
            )
        )
)
some extra stuff
';
var_dump(print_r_reverse($output), $output);
?>
This should output
array(3) {
["a"]=>
string(5) "apple"
["b"]=>
string(6) "banana"
["c"]=>
array(4) {
    [0]=>
    string(1) "x"
    [1]=>
    string(1) "y"
    [2]=>
    string(1) "z"
    [3]=>
    array(3) {
      ["nest"]=>
      string(3) "yes"
      ["nest2"]=>
      array(1) {
        ["nest"]=>
        string(40) "some more
                    asffjaskkd"
      }
      ["nest3"]=>
      string(6) "o rly?"
    }
}
}
string(18) "nsome extra stuffn"
Added:
else if (!empty($trim) && $expecting == 2)
{
    // Expecting close parent or element, but got just a string
    $topArray[$key] .= "\n".$line;
}`

[up](https://www.php.net/manual/vote-note.php?id=111738&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111738&page=function.print-r&vote=down "Vote down!")

1


[**_preda dot vlad at yahoo dot com_**](https://www.php.net/manual/en/function.print-r.php#111738) [¶](https://www.php.net/manual/en/function.print-r.php#111738)

**12 years ago**

`print_r(), just like var_dump() does NOT cast an object, not even if it has a __toString() method - which is normal.
<?php
class A {
    public function __toString() {
        return 'In class A';
    }
}
$a = new A;
echo $a; // In class A
print_r($a); // A Object()
// you can simulate the echo by casting it manually
print_r((string)$a);  // In class A`

[up](https://www.php.net/manual/vote-note.php?id=58811&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=58811&page=function.print-r&vote=down "Vote down!")

3


[**_thbley at gmail dot com_**](https://www.php.net/manual/en/function.print-r.php#58811) [¶](https://www.php.net/manual/en/function.print-r.php#58811)

**19 years ago**

`Here is a print_r that produces xml:
(now you can expand/collapse the nodes in your browser)
<?php
header('Content-Type: text/xml; charset=UTF-8');
echo print_r_xml($some_var);
function print_r_xml($arr,$first=true) {
$output = "";
if ($first) $output .= "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<data>\n";
foreach($arr as $key => $val) {
    if (is_numeric($key)) $key = "arr_".$key; // <0 is not allowed
    switch (gettype($val)) {
      case "array":
        $output .= "<".htmlspecialchars($key)." type='array' size='".count($val)."'>".
          print_r_xml($val,false)."</".htmlspecialchars($key).">\n"; break;
      case "boolean":
        $output .= "<".htmlspecialchars($key)." type='bool'>".($val?"true":"false").
          "</".htmlspecialchars($key).">\n"; break;
      case "integer":
        $output .= "<".htmlspecialchars($key)." type='integer'>".
          htmlspecialchars($val)."</".htmlspecialchars($key).">\n"; break;
      case "double":
        $output .= "<".htmlspecialchars($key)." type='double'>".
          htmlspecialchars($val)."</".htmlspecialchars($key).">\n"; break;
      case "string":
        $output .= "<".htmlspecialchars($key)." type='string' size='".strlen($val)."'>".
          htmlspecialchars($val)."</".htmlspecialchars($key).">\n"; break;
      default:
        $output .= "<".htmlspecialchars($key)." type='unknown'>".gettype($val).
          "</".htmlspecialchars($key).">\n"; break;
    }
}
if ($first) $output .= "</data>\n";
return $output;
}

?>`

[up](https://www.php.net/manual/vote-note.php?id=55738&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=55738&page=function.print-r&vote=down "Vote down!")

2


[**_warhog at warhog dot net_**](https://www.php.net/manual/en/function.print-r.php#55738) [¶](https://www.php.net/manual/en/function.print-r.php#55738)

**20 years ago**

`For very long arrays I have written a little function which formats an array quite nice and uses javascript for browsing it like a tree. The function is very customizable with the $style parameter.
For me it's of great use for browsing large array's, for example when those are used in language-files in some script and so on. It may even be used in "real" scripts for the "real" front-end, cause the tree can very easily be styled (look at the function or the outputted source and you'll see what i mean).
Here's the function:
<?php
function print_r_html($arr, $style = "display: none; margin-left: 10px;")
{ static $i = 0; $i++;
echo "\n<div id=\"array_tree_$i\" class=\"array_tree\">\n";
foreach($arr as $key => $val)
{ switch (gettype($val))
    { case "array":
        echo "<a onclick=\"document.getElementById('";
        echo array_tree_element_$i."').style.display = ";
        echo "document.getElementById('array_tree_element_$i";
        echo "').style.display == 'block' ?";
        echo "'none' : 'block';\"\n";
        echo "name=\"array_tree_link_$i\" href=\"#array_tree_link_$i\">".htmlspecialchars($key)."</a><br />\n";
        echo "<div class=\"array_tree_element_\" id=\"array_tree_element_$i\" style=\"$style\">";
        echo print_r_html($val);
        echo "</div>";
      break;
      case "integer":
        echo "<b>".htmlspecialchars($key)."</b> => <i>".htmlspecialchars($val)."</i><br />";
      break;
      case "double":
        echo "<b>".htmlspecialchars($key)."</b> => <i>".htmlspecialchars($val)."</i><br />";
      break;
      case "boolean":
        echo "<b>".htmlspecialchars($key)."</b> => ";
        if ($val)
        { echo "true"; }
        else
        { echo "false"; }
        echo  "<br />\n";
      break;
      case "string":
        echo "<b>".htmlspecialchars($key)."</b> => <code>".htmlspecialchars($val)."</code><br />";
      break;
      default:
        echo "<b>".htmlspecialchars($key)."</b> => ".gettype($val)."<br />";
      break; }
    echo "\n"; }
echo "</div>\n"; }
?>
The function as it is now does not support the $return parameter as print_r does and will create an endless loop like print_r did in php-versions < 4.0.3 when there is an element which contains a reference to a variable inside of the array to print out :-/
I've tested it with PHP 5.0.6 and PHP 4.2.3 - no problems except those already mentioned.
please e-mail me if you've got a solution for the problems i've mentioned, i myself are not able to solve them 'cause i don't know how the hell i can find out whether a variable is a reference or not.`

[up](https://www.php.net/manual/vote-note.php?id=107298&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107298&page=function.print-r&vote=down "Vote down!")

1


[**_henzeberkheij at gmail dot com_**](https://www.php.net/manual/en/function.print-r.php#107298) [¶](https://www.php.net/manual/en/function.print-r.php#107298)

**13 years ago**

`print_r is used for debug purposes. Yet I had some classes where I just wanted the values coming out of the database, not all the other crap. thus i wrote the following function. If your class has an toArray function, that one will be called otherwise it will return the object as is. print_neat_classes_r is the function that should be called!
<?php
print_neat_classes_r($array, $return=false){
        return print_r(self::neat_class_print_r($array), $return);
    }

function do_print_r($array, $return=false){
        if(is_object($array) && method_exists($array, 'toArray')){
            return $array->toArray();
        }else if(is_array($array)){
            foreach($array as $key=>$obj){
                $array[$key] = self::do_print_r($obj, $return);
            }
            return $array;
        }else{
            return $array;
        }
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=90759&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90759&page=function.print-r&vote=down "Vote down!")

3


[**_Bob_**](https://www.php.net/manual/en/function.print-r.php#90759) [¶](https://www.php.net/manual/en/function.print-r.php#90759)

**16 years ago**

`Here is a function that formats the output of print_r as a expandable/collapsable tree list using HTML and JavaScript.
<?php
function print_r_tree($data)
{
    // capture the output of print_r
    $out = print_r($data, true);
    // replace something like '[element] => <newline> (' with <a href="javascript:toggleDisplay('...');">...</a><div id="..." style="display: none;">
    $out = preg_replace('/([ \t]*)(\[[^\]]+\][ \t]*\=\>[ \t]*[a-z0-9 \t_]+)\n[ \t]*\(/iUe',"'\\1<a href=\"javascript:toggleDisplay(\''.(\$id = substr(md5(rand().'\\0'), 0, 7)).'\');\">\\2</a><div id=\"'.\$id.'\" style=\"display: none;\">'", $out);
    // replace ')' on its own on a new line (surrounded by whitespace is ok) with '</div>
    $out = preg_replace('/^\s*\)\s*$/m', '</div>', $out);
    // print the javascript function toggleDisplay() and then the transformed output
    echo '<script language="Javascript">function toggleDisplay(id) { document.getElementById(id).style.display = (document.getElementById(id).style.display == "block") ? "none" : "block"; }</script>'."\n$out";
}
?>
Pass it a multidimensional array or object and each sub-array/object will be hidden and replaced by a html link that will toggle its display on and off.
Its quick and dirty, but great for debugging the contents of large arrays and objects.
Note: You'll want to surround the output with <pre></pre>`

[up](https://www.php.net/manual/vote-note.php?id=102233&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=102233&page=function.print-r&vote=down "Vote down!")

1


[**_machuidel_**](https://www.php.net/manual/en/function.print-r.php#102233) [¶](https://www.php.net/manual/en/function.print-r.php#102233)

**14 years ago**

`The following will output an array in a PHP parsable format:
<?php
function serialize_array(&$array, $root = '$root', $depth = 0)
{
        $items = array();
        foreach($array as $key => &$value)
        {
                if(is_array($value))
                {
                        serialize_array($value, $root . '[\'' . $key . '\']', $depth + 1);
                }
                else
                {
                        $items[$key] = $value;
                }
        }
        if(count($items) > 0)
        {
                echo $root . ' = array(';
                $prefix = '';
                foreach($items as $key => &$value)
                {
                        echo $prefix . '\'' . $key . '\' => \'' . addslashes($value) . '\'';
                        $prefix = ', ';
                }
                echo ');' . "\n";
        }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=84117&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84117&page=function.print-r&vote=down "Vote down!")

1


[**_Anonymous_**](https://www.php.net/manual/en/function.print-r.php#84117) [¶](https://www.php.net/manual/en/function.print-r.php#84117)

**17 years ago**

`I have written a nice debugging function.
This function handles arrays beautifully.
<?php
//Debug variables, $i and $k are for recursive use
function DebugDisplayVar($input, $name = "Debug", $i = "0", $k = array("Error")){
    if(is_array($input))
    {    foreach ($input as $i => $value){
            $temp = $k;
            $temp[] = $i;
            DebugDisplayVar($value, $name, $i, $temp);}
    }else{//if not array
        echo "$".$name;//[$k]
        foreach ($k as $i => $value){
            if($value !=="Error"){echo "[$value]";}
        }
        echo " = $input<br>";
}    }
//outputs
Debug[0] = value
Debug[1] = another value
ect...
?>`

[up](https://www.php.net/manual/vote-note.php?id=73436&page=function.print-r&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73436&page=function.print-r&vote=down "Vote down!")

1


[**_Matthew Ruivo (mruivo at gmail)_**](https://www.php.net/manual/en/function.print-r.php#73436) [¶](https://www.php.net/manual/en/function.print-r.php#73436)

**18 years ago**

`For those of you needing to print an array within a buffer callback function, I've created this quick function. It simply returns the array as a readable string rather than printing it. You can even choose whether to return it in normal text-mode or HTML. It's recursive, so multi-dimensial arrays are supported. I hope someone finds this useful!
<?php
    function return_array($array, $html = false, $level = 0) {
        $space = $html ? "&nbsp;" : " ";
        $newline = $html ? "<br />" : "\n";
        for ($i = 1; $i <= 6; $i++) {
            $spaces .= $space;
        }
        $tabs = $spaces;
        for ($i = 1; $i <= $level; $i++) {
            $tabs .= $spaces;
        }
        $output = "Array" . $newline . $newline;
        foreach($array as $key => $value) {
            if (is_array($value)) {
                $level++;
                $value = return_array($value, $html, $level);
                $level--;
            }
            $output .= $tabs . "[" . $key . "] => " . $value . $newline;
        }
        return $output;
    }
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.print-r&repo=en&redirect=https://www.php.net/manual/en/function.print-r.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google