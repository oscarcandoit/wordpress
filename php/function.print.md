---
url: https://www.php.net/manual/en/function.print.php
scraped_at: 2025-10-20T02:42:52.263Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# print

(PHP 4, PHP 5, PHP 7, PHP 8)

print — Output a string

### Description [¶](https://www.php.net/manual/en/function.print.php\#refsect1-function.print-description)

**print**([string](https://www.php.net/manual/en/language.types.string.php) `$expression`): [int](https://www.php.net/manual/en/language.types.integer.php)

Outputs `expression`.


`print` is not a function but a language construct.
Its argument is the expression following the `print` keyword,
and is not delimited by parentheses.


The major differences to [echo](https://www.php.net/manual/en/function.echo.php) are that
`print` only accepts a single argument and always returns
`1`.


### Parameters [¶](https://www.php.net/manual/en/function.print.php\#refsect1-function.print-parameters)

`expression`

The expression to be output. Non-string values will be coerced to strings,
even when [the\\
`strict_types` directive](https://www.php.net/manual/en/language.types.declarations.php#language.types.declarations.strict) is enabled.


### Return Values [¶](https://www.php.net/manual/en/function.print.php\#refsect1-function.print-returnvalues)

Returns `1`, always.


### Examples [¶](https://www.php.net/manual/en/function.print.php\#refsect1-function.print-examples)

**Example #1 `print` examples**

`<?php
print "print does not require parentheses.";
print PHP_EOL;
// No newline or space is added; the below outputs "helloworld" all on one line
print "hello";
print "world";
print PHP_EOL;
print "This string spans
multiple lines. The newlines will be
output as well";
print PHP_EOL;
print "This string spans\nmultiple lines. The newlines will be\noutput as well.";
print PHP_EOL;
// The argument can be any expression which produces a string
$foo = "example";
print "foo is $foo"; // foo is example
print PHP_EOL;
$fruits = ["lemon", "orange", "banana"];
print implode(" and ", $fruits); // lemon and orange and banana
print PHP_EOL;
// Non-string expressions are coerced to string, even if declare(strict_types=1) is used
print 6 * 7; // 42
print PHP_EOL;
// Because print has a return value, it can be used in expressions
// The following outputs "hello world"
if ( print "hello" ) {
    echo " world";
}
print PHP_EOL;
// The following outputs "true"
( 1 === 1 ) ? print 'true' : print 'false';
print PHP_EOL;
?>`

Run code

### Notes [¶](https://www.php.net/manual/en/function.print.php\#refsect1-function.print-notes)

> **Note**:
> **Using with parentheses**
>
> Surrounding the argument to `print` with parentheses will not
> raise a syntax error, and produces syntax which looks like a normal
> function call. However, this can be misleading, because the parentheses are actually
> part of the expression being output, not part of the `print`
> syntax itself.
>
>
>
> `<?php
> print "hello";
> // outputs "hello"
> print("hello");
> // also outputs "hello", because ("hello") is a valid expression
> print(1 + 2) * 3;
> // outputs "9"; the parentheses cause 1+2 to be evaluated first, then 3*3
> // the print statement sees the whole expression as one argument
> if ( print("hello") && false ) {
>     print " - inside if";
> }
> else {
>     print " - inside else";
> }
> // outputs " - inside if"
> // the expression ("hello") && false is first evaluated, giving false
> // this is coerced to the empty string "" and printed
> // the print construct then returns 1, so code in the if block is run
> ?>`
>
> Run code
>
> When using `print` in a larger expression, placing both the
> keyword and its argument in parentheses may be necessary to give the intended
> result:
>
>
>
> `<?php
> if ( (print "hello") && false ) {
>     print " - inside if";
> }
> else {
>     print " - inside else";
> }
> // outputs "hello - inside else"
> // unlike the previous example, the expression (print "hello") is evaluated first
> // after outputting "hello", print returns 1
> // since 1 && false is false, code in the else block is run
> print "hello " && print "world";
> // outputs "world1"; print "world" is evaluated first,
> // then the expression "hello " && 1 is passed to the left-hand print
> (print "hello ") && (print "world");
> // outputs "hello world"; the parentheses force the print expressions
> // to be evaluated before the &&
> ?>`
>
> Run code

> **Note**: Because this is a
> language construct and not a function, it cannot be called using
> [variable functions](https://www.php.net/manual/en/functions.variable-functions.php),
> or [named arguments](https://www.php.net/manual/en/functions.arguments.php#functions.named-arguments).

### See Also [¶](https://www.php.net/manual/en/function.print.php\#refsect1-function.print-seealso)

- [echo](https://www.php.net/manual/en/function.echo.php) \- Output one or more strings
- [printf()](https://www.php.net/manual/en/function.printf.php) \- Output a formatted string
- [flush()](https://www.php.net/manual/en/function.flush.php) \- Flush system output buffer
- [Ways to specify literal strings](https://www.php.net/manual/en/language.types.string.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/print.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.print%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.print&repo=en&redirect=https://www.php.net/manual/en/function.print.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=85310&page=function.print&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85310&page=function.print&vote=down "Vote down!")

30


[**_user at example dot net_**](https://www.php.net/manual/en/function.print.php#85310) [¶](https://www.php.net/manual/en/function.print.php#85310)

**17 years ago**

`Be careful when using print. Since print is a language construct and not a function, the parentheses around the argument is not required.
In fact, using parentheses can cause confusion with the syntax of a function and SHOULD be omited.
Most would expect the following behavior:
<?php
    if (print("foo") && print("bar")) {
        // "foo" and "bar" had been printed
    }
?>
But since the parenthesis around the argument are not required, they are interpretet as part of the argument.
This means that the argument of the first print is
    ("foo") && print("bar")
and the argument of the second print is just
    ("bar")
For the expected behavior of the first example, you need to write:
<?php
    if ((print "foo") && (print "bar")) {
        // "foo" and "bar" had been printed
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=128857&page=function.print&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128857&page=function.print&vote=down "Vote down!")

6


[**_mark at manngo dot net_**](https://www.php.net/manual/en/function.print.php#128857) [¶](https://www.php.net/manual/en/function.print.php#128857)

**2 years ago**

`The other major difference with echo is that print returns a value, even it’s always 1.
That might not look like much, but you can use print in another expression. Here are some examples:
<?php
    rand(0,1) ? print 'Hello' : print 'goodbye';
    print PHP_EOL;
    print 'Hello ' and print 'goodbye';
    print PHP_EOL;
    rand(0,1) or print 'whatever';
?>
Here’s a more serious example:
<?php
    function test() {
        return !!rand(0,1);
    }
    test() or print 'failed';
?>`

[up](https://www.php.net/manual/vote-note.php?id=83241&page=function.print&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=83241&page=function.print&vote=down "Vote down!")

16


[**_danielxmorris @ gmail dotcom_**](https://www.php.net/manual/en/function.print.php#83241) [¶](https://www.php.net/manual/en/function.print.php#83241)

**17 years ago**

`I wrote a println function that determines whether a \n or a <br /> should be appended to the line depending on whether it's being executed in a shell or a browser window.  People have probably thought of this before but I thought I'd post it anyway - it may help a couple of people.
<?php
function println ($string_message) {
    $_SERVER['SERVER_PROTOCOL'] ? print "$string_message<br />" : print "$string_message\n";
}
?>
Examples:
Running in a browser:
<?php println ("Hello, world!"); ?>
Output: Hello, world!<br />
Running in a shell:
<?php println ("Hello, world!"); ?>
Output: Hello, world!\n`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.print&repo=en&redirect=https://www.php.net/manual/en/function.print.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google