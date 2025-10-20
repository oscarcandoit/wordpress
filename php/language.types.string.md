---
url: https://www.php.net/manual/en/language.types.string.php
scraped_at: 2025-10-20T02:42:39.771Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Strings [¶](https://www.php.net/manual/en/language.types.string.php\#language.types.string)

A [string](https://www.php.net/manual/en/language.types.string.php) is a series of characters, where a character is
the same as a byte. This means that PHP only supports a 256-character set,
and hence does not offer native Unicode support. See
[details of the string\\
type](https://www.php.net/manual/en/language.types.string.php#language.types.string.details).


> **Note**:
>
> On 32-bit builds, a [string](https://www.php.net/manual/en/language.types.string.php) can be as large as up to 2GB
> (2147483647 bytes maximum)

### Syntax [¶](https://www.php.net/manual/en/language.types.string.php\#language.types.string.syntax)

A [string](https://www.php.net/manual/en/language.types.string.php) literal can be specified in four different ways:


- [single quoted](https://www.php.net/manual/en/language.types.string.php#language.types.string.syntax.single)
- [double quoted](https://www.php.net/manual/en/language.types.string.php#language.types.string.syntax.double)
- [heredoc syntax](https://www.php.net/manual/en/language.types.string.php#language.types.string.syntax.heredoc)
- [nowdoc syntax](https://www.php.net/manual/en/language.types.string.php#language.types.string.syntax.nowdoc)

#### Single quoted [¶](https://www.php.net/manual/en/language.types.string.php\#language.types.string.syntax.single)

The simplest way to specify a [string](https://www.php.net/manual/en/language.types.string.php) is to enclose it in single
quotes (the character `'`).


To specify a literal single quote, escape it with a backslash
( `\`). To specify a literal backslash, double it
( `\\`). All other instances of backslash will be treated
as a literal backslash: this means that the other escape sequences you
might be used to, such as `\r` or `\n`,
will be output literally as specified rather than having any special
meaning.


> **Note**:
>
> Unlike the [double-quoted](https://www.php.net/manual/en/language.types.string.php#language.types.string.syntax.double)
> and [heredoc](https://www.php.net/manual/en/language.types.string.php#language.types.string.syntax.heredoc) syntaxes,
> [variables](https://www.php.net/manual/en/language.variables.php) and escape sequences
> for special characters will _not_ be expanded when they
> occur in single quoted [string](https://www.php.net/manual/en/language.types.string.php)s.

**Example #1 Syntax Variants**

`<?php
echo 'this is a simple string', PHP_EOL;
echo 'You can also have embedded newlines in
strings this way as it is
okay to do', PHP_EOL;
// Outputs: Arnold once said: "I'll be back"
echo 'Arnold once said: "I\'ll be back"', PHP_EOL;
// Outputs: You deleted C:\*.*?
echo 'You deleted C:\\*.*?', PHP_EOL;
// Outputs: You deleted C:\*.*?
echo 'You deleted C:\*.*?', PHP_EOL;
// Outputs: This will not expand: \n a newline
echo 'This will not expand: \n a newline', PHP_EOL;
// Outputs: Variables do not $expand $either
echo 'Variables do not $expand $either', PHP_EOL;
?>`

Run code

#### Double quoted [¶](https://www.php.net/manual/en/language.types.string.php\#language.types.string.syntax.double)

If the [string](https://www.php.net/manual/en/language.types.string.php) is enclosed in double-quotes ( `"`), PHP will
interpret the following escape sequences for special characters:


| Sequence | Meaning |
| --- | --- |
| `\n` | linefeed (LF or 0x0A (10) in ASCII) |
| `\r` | carriage return (CR or 0x0D (13) in ASCII) |
| `\t` | horizontal tab (HT or 0x09 (9) in ASCII) |
| `\v` | vertical tab (VT or 0x0B (11) in ASCII) |
| `\e` | escape (ESC or 0x1B (27) in ASCII) |
| `\f` | form feed (FF or 0x0C (12) in ASCII) |
| `\\` | backslash |
| `\$` | dollar sign |
| `\"` | double-quote |
| `\[0-7]{1,3}` | Octal: the sequence of characters matching the regular expression `[0-7]{1,3}`<br> is a character in octal notation (e.g. `"\101" === "A"`),<br> which silently overflows to fit in a byte (e.g. `"\400" === "\000"`) |
| `\x[0-9A-Fa-f]{1,2}` | Hexadecimal: the sequence of characters matching the regular expression<br> `[0-9A-Fa-f]{1,2}` is a character in hexadecimal notation<br> (e.g. `"\x41" === "A"`) |
| `\u{[0-9A-Fa-f]+}` | Unicode: the sequence of characters matching the regular expression `[0-9A-Fa-f]+`<br> is a Unicode codepoint, which will be output to the string as that codepoint's UTF-8 representation.<br> The braces are required in the sequence. E.g. `"\u{41}" === "A"` |

**Escaped characters**

As in single quoted [string](https://www.php.net/manual/en/language.types.string.php)s, escaping any other character will
result in the backslash being printed too.


The most important feature of double-quoted [string](https://www.php.net/manual/en/language.types.string.php)s is the fact
that variable names will be expanded. See
[string interpolation](https://www.php.net/manual/en/language.types.string.php#language.types.string.parsing) for
details.


#### Heredoc [¶](https://www.php.net/manual/en/language.types.string.php\#language.types.string.syntax.heredoc)

A third way to delimit [string](https://www.php.net/manual/en/language.types.string.php)s is the heredoc syntax:
`<<<`. After this operator, an identifier is
provided, then a newline. The [string](https://www.php.net/manual/en/language.types.string.php) itself follows, and then
the same identifier again to close the quotation.


The closing identifier may be indented by space or tab, in which case
the indentation will be stripped from all lines in the doc string.
Prior to PHP 7.3.0, the closing identifier _must_
begin in the first column of the line.


Also, the closing identifier must follow the same naming rules as any
other label in PHP: it must contain only alphanumeric characters and
underscores, and must start with a non-digit character or underscore.


**Example #2 Basic Heredoc example as of PHP 7.3.0**

`<?php
// no indentation
echo <<<END
      a
     b
    c
\n
END;
// 4 spaces of indentation
echo <<<END
      a
     b
    c
    END;`

Run code

Output of the above example in PHP 7.3:

```
      a
     b
    c

  a
 b
c

```

If the closing identifier is indented further than any lines of the body, then a [ParseError](https://www.php.net/manual/en/class.parseerror.php) will be thrown:


**Example #3 Closing identifier must not be indented further than any lines of the body**

`<?php
echo <<<END
a
b
c
END;`

Run code

Output of the above example in PHP 7.3:

```
Parse error: Invalid body indentation level (expecting an indentation level of at least 3) in example.php on line 4

```

If the closing identifier is indented, tabs can be used as well, however,
tabs and spaces _must not_ be intermixed regarding
the indentation of the closing identifier and the indentation of the body
(up to the closing identifier). In any of these cases, a [ParseError](https://www.php.net/manual/en/class.parseerror.php) will be thrown.

These whitespace constraints have been included because mixing tabs and
spaces for indentation is harmful to legibility.


**Example #4 Different indentation for body (spaces) closing identifier**

`<?php
// All the following code do not work.
// different indentation for body (spaces) ending marker (tabs)
{
    echo <<<END
     a
        END;
}
// mixing spaces and tabs in body
{
    echo <<<END
        a
     END;
}
// mixing spaces and tabs in ending marker
{
    echo <<<END
          a
         END;
}`

Output of the above example in PHP 7.3:

```
Parse error: Invalid indentation - tabs and spaces cannot be mixed in example.php line 8

```

The closing identifier for the body string is not required to be
followed by a semicolon or newline. For example, the following code
is allowed as of PHP 7.3.0:


**Example #5 Continuing an expression after a closing identifier**

`<?php
$values = [<<<END\
a\
b\
    c\
END, 'd e f'];
var_dump($values);`

Run code

Output of the above example in PHP 7.3:

```
array(2) {
  [0] =>
  string(11) "a
  b
    c"
  [1] =>
  string(5) "d e f"
}

```

**Warning**

If the closing identifier was found at the start of a line, then
regardless of whether it was a part of another word, it may be considered
as the closing identifier and causes a [ParseError](https://www.php.net/manual/en/class.parseerror.php).


**Example #6 Closing identifier in body of the string tends to cause ParseError**

`<?php
$values = [<<<END\
a\
b\
END ING\
END, 'd e f'];`

Run code

Output of the above example in PHP 7.3:

```
Parse error: syntax error, unexpected identifier "ING", expecting "]" in example.php on line 5

```

To avoid this problem, it is safe to follow the simple rule:
_do not choose a word that appears in the body of the text_
_as a closing identifier_.


**Warning**

Prior to PHP 7.3.0, it is very important to note that the line with the
closing identifier must contain no other characters, except a semicolon
( `;`).
That means especially that the identifier
_may not be indented_, and there may not be any spaces
or tabs before or after the semicolon. It's also important to realize that
the first character before the closing identifier must be a newline as
defined by the local operating system. This is `\n` on
UNIX systems, including macOS. The closing delimiter must also be
followed by a newline.


If this rule is broken and the closing identifier is not "clean", it will
not be considered a closing identifier, and PHP will continue looking for
one. If a proper closing identifier is not found before the end of the
current file, a parse error will result at the last line.


**Example #7 Invalid example, prior to PHP 7.3.0**

`<?php
class foo {
    public $bar = <<<EOT
bar
    EOT;
}
// Identifier must not be indented
?>`

Run code

**Example #8 Valid example, even prior to PHP 7.3.0**

`<?php
class foo {
    public $bar = <<<EOT
bar
EOT;
}
?>`

Run code

Heredocs containing variables can not be used for initializing class properties.


Heredoc text behaves just like a double-quoted [string](https://www.php.net/manual/en/language.types.string.php), without
the double quotes. This means that quotes in a heredoc do not need to be
escaped, but the escape codes listed above can still be used. Variables are
expanded, but the same care must be taken when expressing complex variables
inside a heredoc as with [string](https://www.php.net/manual/en/language.types.string.php)s.


**Example #9 Heredoc string quoting example**

`<?php
$str = <<<EOD
Example of string
spanning multiple lines
using heredoc syntax.
EOD;
/* More complex example, with variables. */
class foo
{
    var $foo;
    var $bar;
    function __construct()
    {
        $this->foo = 'Foo';
        $this->bar = array('Bar1', 'Bar2', 'Bar3');
    }
}
$foo = new foo();
$name = 'MyName';
echo <<<EOT
My name is "$name". I am printing some $foo->foo.
Now, I am printing some {$foo->bar[1]}.
This should print a capital 'A': \x41
EOT;
?>`

Run code

The above example will output:

```
My name is "MyName". I am printing some Foo.
Now, I am printing some Bar2.
This should print a capital 'A': A
```

It is also possible to use the Heredoc syntax to pass data to function
arguments:


**Example #10 Heredoc in arguments example**

`<?php
var_dump(array(<<<EOD
foobar!
EOD
));
?>`

Run code

It's possible to initialize static variables and class
properties/constants using the Heredoc syntax:


**Example #11 Using Heredoc to initialize static values**

`<?php
// Static variables
function foo()
{
    static $bar = <<<LABEL
Nothing in here...
LABEL;
}
// Class properties/constants
class foo
{
    const BAR = <<<FOOBAR
Constant example
FOOBAR;
    public $baz = <<<FOOBAR
Property example
FOOBAR;
}
?>`

The opening Heredoc identifier may optionally be
enclosed in double quotes:


**Example #12 Using double quotes in Heredoc**

`<?php
echo <<<"FOOBAR"
Hello World!
FOOBAR;
?>`

Run code

#### Nowdoc [¶](https://www.php.net/manual/en/language.types.string.php\#language.types.string.syntax.nowdoc)

Nowdocs are to single-quoted strings what heredocs are to double-quoted
strings. A nowdoc is specified similarly to a heredoc, but _no_
_String interpolation is done_ inside a nowdoc. The construct is ideal for
embedding PHP code or other large blocks of text without the need for
escaping. It shares some features in common with the SGML
`<![CDATA[ ]]>` construct, in that it declares a
block of text which is not for parsing.


A nowdoc is identified with the same `<<<`
sequence used for heredocs, but the identifier which follows is enclosed in
single quotes, e.g. `<<<'EOT'`. All the rules for
heredoc identifiers also apply to nowdoc identifiers, especially those
regarding the appearance of the closing identifier.


**Example #13 Nowdoc string quoting example**

`<?php
echo <<<'EOD'
Example of string spanning multiple lines
using nowdoc syntax. Backslashes are always treated literally,
e.g. \\ and \'.
EOD;`

Run code

The above example will output:

```
Example of string spanning multiple lines
using nowdoc syntax. Backslashes are always treated literally,
e.g. \\ and \'.

```

**Example #14 Nowdoc string quoting example with variables**

`<?php
class foo
{
    public $foo;
    public $bar;
    function __construct()
    {
        $this->foo = 'Foo';
        $this->bar = array('Bar1', 'Bar2', 'Bar3');
    }
}
$foo = new foo();
$name = 'MyName';
echo <<<'EOT'
My name is "$name". I am printing some $foo->foo.
Now, I am printing some {$foo->bar[1]}.
This should not print a capital 'A': \x41
EOT;
?>`

Run code

The above example will output:

```
My name is "$name". I am printing some $foo->foo.
Now, I am printing some {$foo->bar[1]}.
This should not print a capital 'A': \x41
```

**Example #15 Static data example**

`<?php
class foo {
    public $bar = <<<'EOT'
bar
EOT;
}
?>`

#### String interpolation [¶](https://www.php.net/manual/en/language.types.string.php\#language.types.string.parsing)

When a [string](https://www.php.net/manual/en/language.types.string.php) is specified in double quotes or with heredoc,
[variables](https://www.php.net/manual/en/language.variables.php) can be substituted within it.


There are two types of syntax: a
[basic](https://www.php.net/manual/en/language.types.string.php#language.types.string.parsing.basic) one and an
[advanced](https://www.php.net/manual/en/language.types.string.php#language.types.string.parsing.advanced) one.
The basic syntax is the most common and convenient. It provides a way to
embed a variable, an [array](https://www.php.net/manual/en/language.types.array.php) value, or an [object](https://www.php.net/manual/en/language.types.object.php)
property in a [string](https://www.php.net/manual/en/language.types.string.php) with a minimum of effort.


##### Basic syntax

If a dollar sign ( `$`) is encountered, the characters
that follow it which can be used in a variable name will be interpreted
as such and substituted.


**Example #16 String Interpolation**

`<?php
$juice = "apple";
echo "He drank some $juice juice." . PHP_EOL;
?>`

Run code

The above example will output:

```
He drank some apple juice.

```

Formally, the structure for the basic variable substitution syntax is
as follows:


```
string-variable::
     variable-name   (offset-or-property)?
   | ${   expression   }

offset-or-property::
     offset-in-string
   | property-in-string

offset-in-string::
     [   name   ]
   | [   variable-name   ]
   | [   integer-literal   ]

property-in-string::
     ->  name

variable-name::
     $   name

name::
     [a-zA-Z_\x80-\xff][a-zA-Z0-9_\x80-\xff]*

```

**Warning**

The `${ expression }` syntax is deprecated as of
PHP 8.2.0, as it can be interpreted as
[variable variables](https://www.php.net/manual/en/language.variables.variable.php):


`<?php
const foo = 'bar';
$foo = 'foo';
$bar = 'bar';
var_dump("${foo}");
var_dump("${(foo)}");
?>`

Run code

Output of the above example in PHP 8.2:

```
Deprecated: Using ${var} in strings is deprecated, use {$var} instead in file on line 6

Deprecated: Using ${expr} (variable variables) in strings is deprecated, use {${expr}} instead in file on line 9
string(3) "foo"
string(3) "bar"

```

The above example will output:

```
string(3) "foo"
string(3) "bar"

```

The [advanced](https://www.php.net/manual/en/language.types.string.php#language.types.string.parsing.advanced)
string interpolation syntax should be used instead.


> **Note**:
>
> If it is not possible to form a valid name the dollar sign remains
> as verbatim in the string:
>
>
> `<?php
> echo "No interpolation $  has happened\n";
> echo "No interpolation $\n has happened\n";
> echo "No interpolation $2 has happened\n";
> ?>`
>
> Run code
>
> The above example will output:
>
> ```
> No interpolation $  has happened
> No interpolation $
>  has happened
> No interpolation $2 has happened
>
> ```

**Example #17 Interpolating the value of the first dimension of an array or property**

`<?php
$juices = array("apple", "orange", "string_key" => "purple");
echo "He drank some $juices[0] juice.";
echo PHP_EOL;
echo "He drank some $juices[1] juice.";
echo PHP_EOL;
echo "He drank some $juices[string_key] juice.";
echo PHP_EOL;
class A {
    public $s = "string";
}
$o = new A();
echo "Object value: $o->s.";
?>`

Run code

The above example will output:

```
He drank some apple juice.
He drank some orange juice.
He drank some purple juice.
Object value: string.

```

> **Note**:
>
> The array key must be unquoted, and it is therefore not possible to
> refer to a constant as a key with the basic syntax. Use the
> [advanced](https://www.php.net/manual/en/language.types.string.php#language.types.string.parsing.advanced)
> syntax instead.

As of PHP 7.1.0 also _negative_ numeric indices are
supported.


**Example #18 Negative numeric indices**

`<?php
$string = 'string';
echo "The character at index -2 is $string[-2].", PHP_EOL;
$string[-3] = 'o';
echo "Changing the character at index -3 to o gives $string.", PHP_EOL;
?>`

Run code

The above example will output:

```
The character at index -2 is n.
Changing the character at index -3 to o gives strong.

```

For anything more complex, the
[advanced](https://www.php.net/manual/en/language.types.string.php#language.types.string.parsing.advanced)
syntax must be used.


##### Advanced (curly) syntax

The advanced syntax permits the interpolation of
_variables_ with arbitrary accessors.


Any scalar variable, array element or object property
(static or not) with a
[string](https://www.php.net/manual/en/language.types.string.php) representation can be included via this syntax.
The expression is written the same way as it would appear outside the
[string](https://www.php.net/manual/en/language.types.string.php), and then wrapped in `{` and
`}`. Since `{` can not be escaped, this
syntax will only be recognised when the `$` immediately
follows the `{`. Use `{\$` to get a
literal `{$`. Some examples to make it clear:


**Example #19 Curly Syntax**

`<?php
const DATA_KEY = 'const-key';
$great = 'fantastic';
$arr = [\
    '1',\
    '2',\
    '3',\
    [41, 42, 43],\
    'key' => 'Indexed value',\
    'const-key' => 'Key with minus sign',\
    'foo' => ['foo1', 'foo2', 'foo3']\
];
// Won't work, outputs: This is { fantastic}
echo "This is { $great}";
// Works, outputs: This is fantastic
echo "This is {$great}";
class Square {
    public $width;
    public function __construct(int $width) { $this->width = $width; }
}
$square = new Square(5);
// Works
echo "This square is {$square->width}00 centimeters wide.";
// Works, quoted keys only work using the curly brace syntax
echo "This works: {$arr['key']}";
// Works
echo "This works: {$arr[3][2]}";
echo "This works: {$arr[DATA_KEY]}";
// When using multidimensional arrays, always use braces around arrays
// when inside of strings
echo "This works: {$arr['foo'][2]}";
echo "This works: {$obj->values[3]->name}";
echo "This works: {$obj->$staticProp}";
// Won't work, outputs: C:\directory\{fantastic}.txt
echo "C:\directory\{$great}.txt";
// Works, outputs: C:\directory\fantastic.txt
echo "C:\\directory\\{$great}.txt";
?>`

Run code

> **Note**:
>
> As this syntax allows arbitrary expressions it is possible to use
> [variable variables](https://www.php.net/manual/en/language.variables.variable.php)
> within the advanced syntax.

#### String access and modification by character [¶](https://www.php.net/manual/en/language.types.string.php\#language.types.string.substr)

Characters within [string](https://www.php.net/manual/en/language.types.string.php)s may be accessed and modified by
specifying the zero-based offset of the desired character after the
[string](https://www.php.net/manual/en/language.types.string.php) using square [array](https://www.php.net/manual/en/language.types.array.php) brackets, as in
$str\[42\]. Think of a [string](https://www.php.net/manual/en/language.types.string.php) as an
[array](https://www.php.net/manual/en/language.types.array.php) of characters for this purpose. The functions
[substr()](https://www.php.net/manual/en/function.substr.php) and [substr\_replace()](https://www.php.net/manual/en/function.substr-replace.php)
can be used when you want to extract or replace more than 1 character.


> **Note**:
>
> As of PHP 7.1.0, negative string offsets are also supported. These specify
> the offset from the end of the string.
> Formerly, negative offsets emitted **`[E\_NOTICE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-notice)`** for reading
> (yielding an empty string) and **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** for writing
> (leaving the string untouched).

> **Note**:
>
> Prior to PHP 8.0.0, [string](https://www.php.net/manual/en/language.types.string.php)s could also be accessed using braces, as in
> $str{42}, for the same purpose.
> This curly brace syntax was deprecated as of PHP 7.4.0 and no longer supported as of PHP 8.0.0.

**Warning**

Writing to an out of range offset pads the string with spaces.
Non-integer types are converted to integer.
Illegal offset type emits **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**.
Only the first character of an assigned string is used.
As of PHP 7.1.0, assigning an empty string throws a fatal error. Formerly,
it assigned a NULL byte.


**Warning**

Internally, PHP strings are byte arrays. As a result, accessing or
modifying a string using array brackets is not multi-byte safe, and
should only be done with strings that are in a single-byte encoding such
as ISO-8859-1.


> **Note**:
>
> As of PHP 7.1.0, applying the empty index operator on an empty string throws a fatal
> error. Formerly, the empty string was silently converted to an array.

**Example #20 Some string examples**

`<?php
// Get the first character of a string
$str = 'This is a test.';
$first = $str[0];
var_dump($first);
// Get the third character of a string
$third = $str[2];
var_dump($third);
// Get the last character of a string.
$str = 'This is still a test.';
$last = $str[strlen($str)-1];
var_dump($last);
// Modify the last character of a string
$str = 'Look at the sea';
$str[strlen($str)-1] = 'e';
var_dump($str);
?>`

Run code

String offsets have to either be integers or integer-like strings,
otherwise a warning will be thrown.


**Example #21 Example of Illegal String Offsets**

`<?php
$str = 'abc';
$keys = [ '1', '1.0', 'x', '1x' ];
foreach ($keys as $keyToTry) {
    var_dump(isset($str[$keyToTry]));
    try {
        var_dump($str[$keyToTry]);
    } catch (TypeError $e) {
        echo $e->getMessage(), PHP_EOL;
    }
    echo PHP_EOL;
}
?>`

Run code

The above example will output:

```
bool(true)
string(1) "b"

bool(false)
Cannot access offset of type string on string

bool(false)
Cannot access offset of type string on string

bool(false)

Warning: Illegal string offset "1x" in Standard input code on line 10
string(1) "b"

```

> **Note**:
>
>
> Accessing variables of other types (not including arrays or objects
> implementing the appropriate interfaces) using `[]` or
> `{}` silently returns **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**.

> **Note**:
>
>
> Characters within string literals can be accessed
> using `[]` or `{}`.

> **Note**:
>
>
> Accessing characters within string literals using the
> `{}` syntax has been deprecated in PHP 7.4.
> This has been removed in PHP 8.0.

### Useful functions and operators [¶](https://www.php.net/manual/en/language.types.string.php\#language.types.string.useful-funcs)

[String](https://www.php.net/manual/en/language.types.string.php)s may be concatenated using the '.' (dot) operator. Note
that the '+' (addition) operator will _not_ work for this.
See [String operators](https://www.php.net/manual/en/language.operators.string.php) for
more information.


There are a number of useful functions for [string](https://www.php.net/manual/en/language.types.string.php) manipulation.


See the [string functions section](https://www.php.net/manual/en/ref.strings.php) for
general functions, and the [Perl-compatible regular\\
expression functions](https://www.php.net/manual/en/ref.pcre.php) for advanced find & replace functionality.


There are also [functions for URL strings](https://www.php.net/manual/en/ref.url.php), and
functions to encrypt/decrypt strings
( [Sodium](https://www.php.net/manual/en/ref.sodium.php) and
[Hash](https://www.php.net/manual/en/ref.hash.php)).


Finally, see also the [character type\\
functions](https://www.php.net/manual/en/ref.ctype.php).


### Converting to string [¶](https://www.php.net/manual/en/language.types.string.php\#language.types.string.casting)

A value can be converted to a [string](https://www.php.net/manual/en/language.types.string.php) using the
`(string)` cast or the [strval()](https://www.php.net/manual/en/function.strval.php) function.
[String](https://www.php.net/manual/en/language.types.string.php) conversion is automatically done in the scope of an
expression where a [string](https://www.php.net/manual/en/language.types.string.php) is needed. This happens when using the
[echo](https://www.php.net/manual/en/function.echo.php) or [print](https://www.php.net/manual/en/function.print.php) functions, or when a
variable is compared to a [string](https://www.php.net/manual/en/language.types.string.php). The sections on
[Types](https://www.php.net/manual/en/language.types.php) and
[Type Juggling](https://www.php.net/manual/en/language.types.type-juggling.php) will make
the following clearer. See also the [settype()](https://www.php.net/manual/en/function.settype.php) function.


A [bool](https://www.php.net/manual/en/language.types.boolean.php) **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** value is converted to the [string](https://www.php.net/manual/en/language.types.string.php) `"1"`. [bool](https://www.php.net/manual/en/language.types.boolean.php) **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** is converted to
`""` (the empty string). This allows conversion back and
forth between [bool](https://www.php.net/manual/en/language.types.boolean.php) and [string](https://www.php.net/manual/en/language.types.string.php) values.


An [int](https://www.php.net/manual/en/language.types.integer.php) or [float](https://www.php.net/manual/en/language.types.float.php) is converted to a
[string](https://www.php.net/manual/en/language.types.string.php) representing the number textually (including the
exponent part for [float](https://www.php.net/manual/en/language.types.float.php)s). Floating point numbers can be
converted using exponential notation ( `4.1E+6`).


> **Note**:
>
>
> As of PHP 8.0.0, the decimal point character is always
> a period (" `.`"). Prior to PHP 8.0.0,
> the decimal point character is defined in the script's locale (category
> LC\_NUMERIC). See the [setlocale()](https://www.php.net/manual/en/function.setlocale.php) function.

[Array](https://www.php.net/manual/en/language.types.array.php)s are always converted to the [string](https://www.php.net/manual/en/language.types.string.php) `"Array"`; because of this, [echo](https://www.php.net/manual/en/function.echo.php) and
[print](https://www.php.net/manual/en/function.print.php) can not by themselves show the contents of an
[array](https://www.php.net/manual/en/language.types.array.php). To view a single element, use a construction such as
`echo $arr['foo']`. See below for tips on viewing the entire
contents.


In order to convert [object](https://www.php.net/manual/en/language.types.object.php)s to [string](https://www.php.net/manual/en/language.types.string.php), the magic
method [\_\_toString](https://www.php.net/manual/en/language.oop5.magic.php) must be used.


[Resource](https://www.php.net/manual/en/language.types.resource.php)s are always converted to [string](https://www.php.net/manual/en/language.types.string.php)s with the
structure `"Resource id #1"`, where `1`
is the resource number assigned to the [resource](https://www.php.net/manual/en/language.types.resource.php) by PHP at
runtime. While the exact structure of this string should not be relied on
and is subject to change, it will always be unique for a given resource
within the lifetime of a script being executed (ie a Web request or CLI
process) and won't be reused. To get a [resource](https://www.php.net/manual/en/language.types.resource.php)'s type, use
the [get\_resource\_type()](https://www.php.net/manual/en/function.get-resource-type.php) function.


**`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** is always converted to an empty string.


As stated above, directly converting an [array](https://www.php.net/manual/en/language.types.array.php),
[object](https://www.php.net/manual/en/language.types.object.php), or [resource](https://www.php.net/manual/en/language.types.resource.php) to a [string](https://www.php.net/manual/en/language.types.string.php) does
not provide any useful information about the value beyond its type. See the
functions [print\_r()](https://www.php.net/manual/en/function.print-r.php) and [var\_dump()](https://www.php.net/manual/en/function.var-dump.php) for
more effective means of inspecting the contents of these types.


Most PHP values can also be converted to [string](https://www.php.net/manual/en/language.types.string.php)s for permanent
storage. This method is called serialization, and is performed by the
[serialize()](https://www.php.net/manual/en/function.serialize.php) function.


### Details of the String Type [¶](https://www.php.net/manual/en/language.types.string.php\#language.types.string.details)

The [string](https://www.php.net/manual/en/language.types.string.php) in PHP is implemented as an array of bytes and an
integer indicating the length of the buffer. It has no information about how
those bytes translate to characters, leaving that task to the programmer.
There are no limitations on the values the string can be composed of; in
particular, bytes with value `0` (“NUL bytes”) are allowed
anywhere in the string (however, a few functions, said in this manual not to
be “binary safe”, may hand off the strings to libraries that ignore data
after a NUL byte.)


This nature of the string type explains why there is no separate “byte” type
in PHP – strings take this role. Functions that return no textual data – for
instance, arbitrary data read from a network socket – will still return
strings.


Given that PHP does not dictate a specific encoding for strings, one might
wonder how string literals are encoded. For instance, is the string
`"á"` equivalent to `"\xE1"` (ISO-8859-1),
`"\xC3\xA1"` (UTF-8, C form),
`"\x61\xCC\x81"` (UTF-8, D form) or any other possible
representation? The answer is that string will be encoded in whatever fashion
it is encoded in the script file. Thus, if the script is written in
ISO-8859-1, the string will be encoded in ISO-8859-1 and so on. However,
this does not apply if Zend Multibyte is enabled; in that case, the script
may be written in an arbitrary encoding (which is explicitly declared or is
detected) and then converted to a certain internal encoding, which is then
the encoding that will be used for the string literals.
Note that there are some constraints on the encoding of the script (or on the
internal encoding, should Zend Multibyte be enabled) – this almost always
means that this encoding should be a compatible superset of ASCII, such as
UTF-8 or ISO-8859-1. Note, however, that state-dependent encodings where
the same byte values can be used in initial and non-initial shift states
may be problematic.


Of course, in order to be useful, functions that operate on text may have to
make some assumptions about how the string is encoded. Unfortunately, there
is much variation on this matter throughout PHP’s functions:


- Some functions assume that the string is encoded in some (any) single-byte
encoding, but they do not need to interpret those bytes as specific
characters. This is case of, for instance, [substr()](https://www.php.net/manual/en/function.substr.php),
[strpos()](https://www.php.net/manual/en/function.strpos.php), [strlen()](https://www.php.net/manual/en/function.strlen.php) or
[strcmp()](https://www.php.net/manual/en/function.strcmp.php). Another way to think of these functions is
that operate on memory buffers, i.e., they work with bytes and byte
offsets.

- Other functions are passed the encoding of the string, possibly they also
assume a default if no such information is given. This is the case of
[htmlentities()](https://www.php.net/manual/en/function.htmlentities.php) and the majority of the
functions in the [mbstring](https://www.php.net/manual/en/book.mbstring.php) extension.

- Others use the current locale (see [setlocale()](https://www.php.net/manual/en/function.setlocale.php)), but
operate byte-by-byte.

- Finally, they may just assume the string is using a specific encoding,
usually UTF-8. This is the case of most functions in the
[intl](https://www.php.net/manual/en/book.intl.php) extension and in the
[PCRE](https://www.php.net/manual/en/book.pcre.php) extension
(in the last case, only when the `u` modifier is used).


Ultimately, this means writing correct programs using Unicode depends on
carefully avoiding functions that will not work and that most likely will
corrupt the data and using instead the functions that do behave correctly,
generally from the [intl](https://www.php.net/manual/en/book.intl.php) and
[mbstring](https://www.php.net/manual/en/book.mbstring.php) extensions.
However, using functions that can handle Unicode encodings is just the
beginning. No matter the functions the language provides, it is essential to
know the Unicode specification. For instance, a program that assumes there is
only uppercase and lowercase is making a wrong assumption.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/string.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.string%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.string&repo=en&redirect=https://www.php.net/manual/en/language.types.string.php)

### User Contributed Notes 11 notes

[up](https://www.php.net/manual/vote-note.php?id=107138&page=language.types.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107138&page=language.types.string&vote=down "Vote down!")

108


[**_gtisza at gmail dot com_**](https://www.php.net/manual/en/language.types.string.php#107138) [¶](https://www.php.net/manual/en/language.types.string.php#107138)

**13 years ago**

`The documentation does not mention, but a closing semicolon at the end of the heredoc is actually interpreted as a real semicolon, and as such, sometimes leads to syntax errors.
This works:
<?php
$foo = <<<END
abcd
END;
?>
This does not:
<?php
foo(<<<END
abcd
END;
);
// syntax error, unexpected ';'
?>
Without semicolon, it works fine:
<?php
foo(<<<END
abcd
END
);
?>`

[up](https://www.php.net/manual/vote-note.php?id=128097&page=language.types.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128097&page=language.types.string&vote=down "Vote down!")

24


[**_BahmanMD_**](https://www.php.net/manual/en/language.types.string.php#128097) [¶](https://www.php.net/manual/en/language.types.string.php#128097)

**2 years ago**

`In PHP 8.2 using ${var} in strings is deprecated, use {$var} instead:
<?php
$juice = "apple";
// Valid. Explicitly specify the end of the variable name by enclosing it in braces:
echo "He drank some juice made of {$juice}s.";
?>`

[up](https://www.php.net/manual/vote-note.php?id=46914&page=language.types.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=46914&page=language.types.string&vote=down "Vote down!")

22


[**_lelon at lelon dot net_**](https://www.php.net/manual/en/language.types.string.php#46914) [¶](https://www.php.net/manual/en/language.types.string.php#46914)

**20 years ago**

`You can use the complex syntax to put the value of both object properties AND object methods inside a string.  For example...
<?php
class Test {
    public $one = 1;
    public function two() {
        return 2;
    }
}
$test = new Test();
echo "foo {$test->one} bar {$test->two()}";
?>
Will output "foo 1 bar 2".
However, you cannot do this for all values in your namespace.  Class constants and static properties/methods will not work because the complex syntax looks for the '$'.
<?php
class Test {
    const ONE = 1;
}
echo "foo {Test::ONE} bar";
?>
This will output "foo {Test::one} bar".  Constants and static properties require you to break up the string.`

[up](https://www.php.net/manual/vote-note.php?id=123393&page=language.types.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123393&page=language.types.string&vote=down "Vote down!")

11


[**_Ray.Paseur sometimes uses Gmail_**](https://www.php.net/manual/en/language.types.string.php#123393) [¶](https://www.php.net/manual/en/language.types.string.php#123393)

**6 years ago**

`md5('240610708') == md5('QNKCDZO')
This comparison is true because both md5() hashes start '0e' so PHP type juggling understands these strings to be scientific notation.  By definition, zero raised to any power is zero.`

[up](https://www.php.net/manual/vote-note.php?id=74744&page=language.types.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74744&page=language.types.string&vote=down "Vote down!")

12


[**_og at gams dot at_**](https://www.php.net/manual/en/language.types.string.php#74744) [¶](https://www.php.net/manual/en/language.types.string.php#74744)

**18 years ago**

`easy transparent solution for using constants in the heredoc format:
DEFINE('TEST','TEST STRING');
$const = get_defined_constants();
echo <<<END
{$const['TEST']}
END;
Result:
TEST STRING`

[up](https://www.php.net/manual/vote-note.php?id=86044&page=language.types.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86044&page=language.types.string&vote=down "Vote down!")

3


[**_steve at mrclay dot org_**](https://www.php.net/manual/en/language.types.string.php#86044) [¶](https://www.php.net/manual/en/language.types.string.php#86044)

**17 years ago**

`Simple function to create human-readably escaped double-quoted strings for use in source code or when debugging strings with newlines/tabs/etc.
<?php
function doubleQuote($str) {
    $ret = '"';
    for ($i = 0, $l = strlen($str); $i < $l; ++$i) {
        $o = ord($str[$i]);
        if ($o < 31 || $o > 126) {
            switch ($o) {
                case 9: $ret .= '\t'; break;
                case 10: $ret .= '\n'; break;
                case 11: $ret .= '\v'; break;
                case 12: $ret .= '\f'; break;
                case 13: $ret .= '\r'; break;
                default: $ret .= '\x' . str_pad(dechex($o), 2, '0', STR_PAD_LEFT);
            }
        } else {
            switch ($o) {
                case 36: $ret .= '\$'; break;
                case 34: $ret .= '\"'; break;
                case 92: $ret .= '\\\\'; break;
                default: $ret .= $str[$i];
            }
        }
    }
    return $ret . '"';
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=41470&page=language.types.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=41470&page=language.types.string&vote=down "Vote down!")

4


[**_atnak at chejz dot com_**](https://www.php.net/manual/en/language.types.string.php#41470) [¶](https://www.php.net/manual/en/language.types.string.php#41470)

**21 years ago**

`Here is a possible gotcha related to oddness involved with accessing strings by character past the end of the string:
$string = 'a';
var_dump($string[2]);  // string(0) ""
var_dump($string[7]);  // string(0) ""
$string[7] === '';  // TRUE
It appears that anything past the end of the string gives an empty string..  However, when E_NOTICE is on, the above examples will throw the message:
Notice:  Uninitialized string offset:  N in FILE on line LINE
This message cannot be specifically masked with @$string[7], as is possible when $string itself is unset.
isset($string[7]);  // FALSE
$string[7] === NULL;  // FALSE
Even though it seems like a not-NULL value of type string, it is still considered unset.`

[up](https://www.php.net/manual/vote-note.php?id=125281&page=language.types.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125281&page=language.types.string&vote=down "Vote down!")

 -1


[**_greenbluemoonlight at gmail dot com_**](https://www.php.net/manual/en/language.types.string.php#125281) [¶](https://www.php.net/manual/en/language.types.string.php#125281)

**5 years ago**

`<?php
\\Example # 10 Simple Syntax - Solution for the last "echo" line.
class people {
    public $john = "John Smith";
    public $jane = "Jane Smith";
    public $robert = "Robert Paulsen";
    public $smith = "Smith";
}
$people = new people();
echo "$people->john then said hello to $people->jane.".PHP_EOL;
echo "$people->john's wife greeted $people->robert.".PHP_EOL;
echo "$people->robert greeted the two $people->smiths";
\\Won't work
\\Outputs: Robert Paulsen greeted the two
/**Solution:**\
echo "$people->robert greeted the two $people->smith\x08s";
\\Will work
\\Outputs: Robert Paulsen greeted the two Smiths
?>`

[up](https://www.php.net/manual/vote-note.php?id=111522&page=language.types.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111522&page=language.types.string&vote=down "Vote down!")

0


[**_php at richardneill dot org_**](https://www.php.net/manual/en/language.types.string.php#111522) [¶](https://www.php.net/manual/en/language.types.string.php#111522)

**12 years ago**

`Leading zeroes in strings are (least-surprise) not treated as octal.
Consider:
$x = "0123"  + 0;
$y = 0123 + 0;
echo "x is $x, y is $y";    //prints  "x is 123, y is 83"
in other words:
* leading zeros in numeric literals in the source-code are interpreted as "octal", c.f. strtol().
* leading zeros in strings (eg user-submitted data), when cast (implicitly or explicitly) to integer are ignored, and considered as decimal, c.f. strtod().`

[up](https://www.php.net/manual/vote-note.php?id=85668&page=language.types.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=85668&page=language.types.string&vote=down "Vote down!")

0


[**_chAlx at findme dot if dot u dot need_**](https://www.php.net/manual/en/language.types.string.php#85668) [¶](https://www.php.net/manual/en/language.types.string.php#85668)

**17 years ago**

`To save Your mind don't read previous comments about dates  ;)
When both strings can be converted to the numerics (in ("$a" > "$b") test) then resulted numerics are used, else FULL strings are compared char-by-char:
<?php
var_dump('1.22' > '01.23'); // bool(false)
var_dump('1.22.00' > '01.23.00'); // bool(true)
var_dump('1-22-00' > '01-23-00'); // bool(true)
var_dump((float)'1.22.00' > (float)'01.23.00'); // bool(false)
?>`

[up](https://www.php.net/manual/vote-note.php?id=91628&page=language.types.string&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91628&page=language.types.string&vote=down "Vote down!")

 -2


[**_headden at karelia dot ru_**](https://www.php.net/manual/en/language.types.string.php#91628) [¶](https://www.php.net/manual/en/language.types.string.php#91628)

**16 years ago**

`Here is an easy hack to allow double-quoted strings and heredocs to contain arbitrary expressions in curly braces syntax, including constants and other function calls:
<?php
// Hack declaration
function _expr($v) { return $v; }
$_expr = '_expr';
// Our playground
define('qwe', 'asd');
define('zxc', 5);
$a=3;
$b=4;
function c($a, $b) { return $a+$b; }
// Usage
echo "pre {$_expr(1+2)} post\n"; // outputs 'pre 3 post'
echo "pre {$_expr(qwe)} post\n"; // outputs 'pre asd post'
echo "pre {$_expr(c($a, $b)+zxc*2)} post\n"; // outputs 'pre 17 post'
// General syntax is {$_expr(...)}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.string&repo=en&redirect=https://www.php.net/manual/en/language.types.string.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google