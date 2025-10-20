---
url: https://www.php.net/manual/en/language.generators.overview.php
scraped_at: 2025-10-20T02:40:29.629Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Generators overview [¶](https://www.php.net/manual/en/language.generators.overview.php\#language.generators.overview)

(PHP 5 >= 5.5.0, PHP 7, PHP 8)

Generators provide an easy way to implement simple
[iterators](https://www.php.net/manual/en/language.oop5.iterations.php) without the
overhead or complexity of implementing a class that implements the
[Iterator](https://www.php.net/manual/en/class.iterator.php) interface.


A generator offers a convenient way to provide data to [`foreach`](https://www.php.net/manual/en/control-structures.foreach.php) loops without
having to build an array in memory ahead of time, which may cause the program
to exceed a memory limit or require a considerable amount of
processing time to generate. Instead, a generator function can be used,
which is the same as a normal
[function](https://www.php.net/manual/en/functions.user-defined.php), except that instead
of
[return](https://www.php.net/manual/en/functions.returning-values.php) ing once, a
generator can [`yield`](https://www.php.net/manual/en/language.generators.syntax.php#control-structures.yield) as many times as it needs to in order to provide the
values to be iterated over.
Like with iterators, random data access is not possible.


A simple example of this is to reimplement the [range()](https://www.php.net/manual/en/function.range.php)
function as a generator. The standard [range()](https://www.php.net/manual/en/function.range.php) function
has to generate an array with every value in it and return it, which can
result in large arrays: for example, calling
**range(0, 1000000)** will result in well over 100 MB of
memory being used.


As an alternative, we can implement an `xrange()`
generator, which will only ever need enough memory to create an
[Iterator](https://www.php.net/manual/en/class.iterator.php) object and track the current state of the
generator internally, which turns out to be less than 1 kilobyte.


**Example #1 Implementing [range()](https://www.php.net/manual/en/function.range.php) as a generator**

`<?php
function xrange($start, $limit, $step = 1) {
    if ($start <= $limit) {
        if ($step <= 0) {
            throw new LogicException('Step must be positive');
        }
        for ($i = $start; $i <= $limit; $i += $step) {
            yield $i;
        }
    } else {
        if ($step >= 0) {
            throw new LogicException('Step must be negative');
        }
        for ($i = $start; $i >= $limit; $i += $step) {
            yield $i;
        }
    }
}
/*
* Note that both range() and xrange() result in the same
* output below.
*/
echo 'Single digit odd numbers from range():  ';
foreach (range(1, 9, 2) as $number) {
    echo "$number ";
}
echo "\n";
echo 'Single digit odd numbers from xrange(): ';
foreach (xrange(1, 9, 2) as $number) {
    echo "$number ";
}
?>`

The above example will output:

```
Single digit odd numbers from range():  1 3 5 7 9
Single digit odd numbers from xrange(): 1 3 5 7 9

```

### [Generator](https://www.php.net/manual/en/class.generator.php) objects [¶](https://www.php.net/manual/en/language.generators.overview.php\#language.generators.object)

When a generator function is called, a new object of the
internal [Generator](https://www.php.net/manual/en/class.generator.php) class is returned. This object
implements the [Iterator](https://www.php.net/manual/en/class.iterator.php) interface in much the same
way as a forward-only iterator object would, and provides methods that can
be called to manipulate the state of the generator, including sending
values to and returning values from it.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/generators.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.generators.overview%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.generators.overview&repo=en&redirect=https://www.php.net/manual/en/language.generators.overview.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=112985&page=language.generators.overview&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112985&page=language.generators.overview&vote=down "Vote down!")

181


[**_bloodjazman at gmail dot com_**](https://www.php.net/manual/en/language.generators.overview.php#112985) [¶](https://www.php.net/manual/en/language.generators.overview.php#112985)

**12 years ago**

`for the protection from the leaking of resources
see RFC [https://wiki.php.net/rfc/generators#closing\_a\_generator](https://wiki.php.net/rfc/generators#closing_a_generator)
and use finnaly
sample code
function getLines($file) {
    $f = fopen($file, 'r');
    try {
        while ($line = fgets($f)) {
            yield $line;
        }
    } finally {
        fclose($f);
    }
}
foreach (getLines("file.txt") as $n => $line) {
    if ($n > 5) break;
    echo $line;
}`

[up](https://www.php.net/manual/vote-note.php?id=119275&page=language.generators.overview&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119275&page=language.generators.overview&vote=down "Vote down!")

44


[**_montoriusz at gmail dot com_**](https://www.php.net/manual/en/language.generators.overview.php#119275) [¶](https://www.php.net/manual/en/language.generators.overview.php#119275)

**9 years ago**

`Bear in mind that execution of a generator function is postponed until iteration over its result (the Generator object) begins. This might confuse one if the result of a generator is assigned to a variable instead of immediate iteration.
<?php
$some_state = 'initial';
function gen() {
    global $some_state;
    echo "gen() execution start\n";
    $some_state = "changed";
    yield 1;
    yield 2;
}
function peek_state() {
    global $some_state;
    echo "\$some_state = $some_state\n";
}
echo "calling gen()...\n";
$result = gen();
echo "gen() was called\n";
peek_state();
echo "iterating...\n";
foreach ($result as $val) {
    echo "iteration: $val\n";
    peek_state();
}
?>
If you need to perform some action when the function is called and before the result is used, you'll have to wrap your generator in another function.
<?php
/**
* @return Generator
*/
function some_generator() {
    global $some_state;
    $some_state = "changed";
    return gen();
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=124259&page=language.generators.overview&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124259&page=language.generators.overview&vote=down "Vote down!")

18


[**_chung1905 at gmail dot com_**](https://www.php.net/manual/en/language.generators.overview.php#124259) [¶](https://www.php.net/manual/en/language.generators.overview.php#124259)

**6 years ago**

`In addition to the note of "montoriusz at gmail dot com": [https://www.php.net/manual/en/language.generators.overview.php#119275](https://www.php.net/manual/en/language.generators.overview.php#119275)
"If you need to perform some action when the function is called and before the result is used, you'll have to wrap your generator in another function."
You can use Generator::rewind instead ( [https://www.php.net/manual/en/generator.rewind.php](https://www.php.net/manual/en/generator.rewind.php))
Sample code:
<?php
/** function/generator definition **/
echo "calling gen()...\n";
$result = gen();
$result->rewind();
echo "gen() was called\n";
/** iteration **/
?>`

[up](https://www.php.net/manual/vote-note.php?id=118529&page=language.generators.overview&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118529&page=language.generators.overview&vote=down "Vote down!")

30


[**_info at boukeversteegh dot nl_**](https://www.php.net/manual/en/language.generators.overview.php#118529) [¶](https://www.php.net/manual/en/language.generators.overview.php#118529)

**9 years ago**

`Here's how to detect loop breaks, and how to handle or cleanup after an interruption.
<?php
    function generator()
    {
        $complete = false;
        try {
            while (($result = some_function())) {
                yield $result;
            }
            $complete = true;
        } finally {
            if (!$complete) {
                // cleanup when loop breaks
            } else {
                // cleanup when loop completes
            }
        }
        // Do something only after loop completes
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=114136&page=language.generators.overview&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114136&page=language.generators.overview&vote=down "Vote down!")

18


[**_lubaev_**](https://www.php.net/manual/en/language.generators.overview.php#114136) [¶](https://www.php.net/manual/en/language.generators.overview.php#114136)

**11 years ago**

`Abstract test.
<?php
$start_time=microtime(true);
$array = array();
$result = '';
for($count=1000000; $count--;)
{
$array[]=$count/2;
}
foreach($array as $val)
{
$val += 145.56;
$result .= $val;
}
$end_time=microtime(true);
echo "time: ", bcsub($end_time, $start_time, 4), "\n";
echo "memory (byte): ", memory_get_peak_usage(true), "\n";
?>
<?php
$start_time=microtime(true);
$result = '';
function it()
{
for($count=1000000; $count--;)
{
    yield $count/2;
}
}
foreach(it() as $val)
{
$val += 145.56;
$result .= $val;
}
$end_time=microtime(true);
echo "time: ", bcsub($end_time, $start_time, 4), "\n";
echo "memory (byte): ", memory_get_peak_usage(true), "\n";
?>
Result:
----------------------------------
           |  time  | memory, mb |
----------------------------------
| not gen  | 2.1216 | 89.25      |
|---------------------------------
| with gen | 6.1963 | 8.75       |
|---------------------------------
| diff     | < 192% | > 90%      |
----------------------------------`

[up](https://www.php.net/manual/vote-note.php?id=114409&page=language.generators.overview&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114409&page=language.generators.overview&vote=down "Vote down!")

15


[**_dc at libertyskull dot com_**](https://www.php.net/manual/en/language.generators.overview.php#114409) [¶](https://www.php.net/manual/en/language.generators.overview.php#114409)

**11 years ago**

`Same example, different results:
----------------------------------
           |  time  | memory, mb |
----------------------------------
| not gen  | 0.7589 | 146.75     |
|---------------------------------
| with gen | 0.7469 | 8.75       |
|---------------------------------
Time in results varying from 6.5 to 7.8 on both examples.
So no real drawbacks concerning processing speed.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.generators.overview&repo=en&redirect=https://www.php.net/manual/en/language.generators.overview.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google