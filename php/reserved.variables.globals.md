---
url: https://www.php.net/manual/en/reserved.variables.globals.php
scraped_at: 2025-10-20T03:02:08.657Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# $GLOBALS

(PHP 4, PHP 5, PHP 7, PHP 8)

$GLOBALS — References all variables available in global scope

### Description [¶](https://www.php.net/manual/en/reserved.variables.globals.php\#refsect1-reserved.variables.globals-description)

An associative [array](https://www.php.net/manual/en/language.types.array.php) containing references to all variables which
are currently defined in the global scope of the script. The
variable names are the keys of the array.


### Examples [¶](https://www.php.net/manual/en/reserved.variables.globals.php\#refsect1-reserved.variables.globals-examples)

**Example #1 $GLOBALS example**

`<?php
function test()
{
    $foo = "local variable";
    echo '$foo in global scope: ' . $GLOBALS["foo"] . "\n";
    echo '$foo in current scope: ' . $foo . "\n";
}
$foo = "Example content";
test();
?>`

The above example will output
something similar to:

```
$foo in global scope: Example content
$foo in current scope: local variable
```

**Warning**

As of PHP 8.1.0, write access to the entire $GLOBALS array is no longer supported:


**Example #2 writing entire $GLOBALS will result in error.**

`<?php
// Generates compile-time error:
$GLOBALS = [];
$GLOBALS += [];
$GLOBALS =& $x;
$x =& $GLOBALS;
unset($GLOBALS);
array_pop($GLOBALS);
// ...and any other write/read-write operation on $GLOBALS
?>`

### Notes [¶](https://www.php.net/manual/en/reserved.variables.globals.php\#refsect1-reserved.variables.globals-notes)

> **Note**:
>
> This is a 'superglobal', or
> automatic global, variable. This simply means that it is available in
> all scopes throughout a script. There is no need to do
> **global $variable;** to access it within functions or methods.

> **Note**:
> **Variable availability**
>
> Unlike all of the other [superglobals](https://www.php.net/manual/en/language.variables.superglobals.php),
> $GLOBALS has essentially always been available in PHP.

> **Note**:
>
>
> As of PHP 8.1.0, $GLOBALS is now a read-only copy of
> the global [symbol table](https://www.php.net/manual/en/features.gc.refcounting-basics.php).
> That is, global variables cannot be modified via its copy.
> Previously, $GLOBALS array is excluded from the usual
> by-value behavior of PHP arrays and global variables can be modified via its copy.
>
>
> `<?php
> // Before PHP 8.1.0
> $a = 1;
> $globals = $GLOBALS; // Ostensibly by-value copy
> $globals['a'] = 2;
> var_dump($a); // int(2)
> // As of PHP 8.1.0
> // this no longer modifies $a. The previous behavior violated by-value semantics.
> $globals = $GLOBALS;
> $globals['a'] = 1;
> // To restore the previous behavior, iterate its copy and assign each property back to $GLOBALS.
> foreach ($globals as $key => $value) {
>     $GLOBALS[$key] = $value;
> }
> ?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/predefined/variables/globals.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Freserved.variables.globals%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=reserved.variables.globals&repo=en&redirect=https://www.php.net/manual/en/reserved.variables.globals.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=127971&page=reserved.variables.globals&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127971&page=reserved.variables.globals&vote=down "Vote down!")

30


[**_inafeeur at gmail dot com_**](https://www.php.net/manual/en/reserved.variables.globals.php#127971) [¶](https://www.php.net/manual/en/reserved.variables.globals.php#127971)

**2 years ago**

`We can be more clear with the extension of the given example.
Before PHP Version 8.1
<?php
$a = 1;
$globals = $GLOBALS;
$globals['a'] = 2;
echo $a; // 2
echo $globals['a']; // 2
echo $GLOBALS['a'];  // 2
?>
After PHP Version 8.1
<?php
$a = 1;
$globals = $GLOBALS;
$globals['a'] = 2;
echo $a; // 1
echo $globals['a']; // 2
echo $GLOBALS['a'];  // 1
?>`

[up](https://www.php.net/manual/vote-note.php?id=104666&page=reserved.variables.globals&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104666&page=reserved.variables.globals&vote=down "Vote down!")

17


[**_therandshow at gmail dot com_**](https://www.php.net/manual/en/reserved.variables.globals.php#104666) [¶](https://www.php.net/manual/en/reserved.variables.globals.php#104666)

**14 years ago**

`As of PHP 5.4 $GLOBALS is now initialized just-in-time. This means there now is an advantage to not use the $GLOBALS variable as you can avoid the overhead of initializing it. How much of an advantage that is I'm not sure, but I've never liked $GLOBALS much anyways.`

[up](https://www.php.net/manual/vote-note.php?id=112395&page=reserved.variables.globals&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112395&page=reserved.variables.globals&vote=down "Vote down!")

16


[**_mstraczkowski at gmail dot com_**](https://www.php.net/manual/en/reserved.variables.globals.php#112395) [¶](https://www.php.net/manual/en/reserved.variables.globals.php#112395)

**12 years ago**

`Watch out when you are trying to set $GLOBALS to the local variable.
Even without reference operator "&" your variable seems to be referenced to the $GLOBALS
You can test this behaviour using below code
<?php
/**
* Result:
* POST: B, Variable: C
* GLOBALS: C, Variable: C
*/

// Testing $_POST
$_POST['A'] = 'B';

$nonReferencedPostVar = $_POST;
$nonReferencedPostVar['A'] = 'C';

echo 'POST: '.$_POST['A'].', Variable: '.$nonReferencedPostVar['A']."\n\n";

// Testing Globals
$GLOBALS['A'] = 'B';

$nonReferencedGlobalsVar = $GLOBALS;
$nonReferencedGlobalsVar['A'] = 'C';

echo 'GLOBALS: '.$GLOBALS['A'].', Variable: '.$nonReferencedGlobalsVar['A']."\n\n";`

[up](https://www.php.net/manual/vote-note.php?id=120071&page=reserved.variables.globals&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120071&page=reserved.variables.globals&vote=down "Vote down!")

12


[**_vittorio.zamparella at famous googlemail_**](https://www.php.net/manual/en/reserved.variables.globals.php#120071) [¶](https://www.php.net/manual/en/reserved.variables.globals.php#120071)

**8 years ago**

`I finally found information about superglobals not being found in $GLOBALS:
[https://bugs.php.net/bug.php?id=65223&edit=2](https://bugs.php.net/bug.php?id=65223&edit=2)
-------------------------------------
[2013-07-09 12:00 UTC] johannes @php.net
[...]super-globals (aka. auto globals) are not added to symbol tables by default for performance reasons unless the parser sees need. i.e.
<?php
$_SERVER;
print_r($GLOBALS);
?>
will list it. You can also control this using auto_gloals_jit in php.ini: [http://www.php.net/manual/en/ini.core.php#ini.auto-globals-jit](http://www.php.net/manual/en/ini.core.php#ini.auto-globals-jit)
-------------------------------------
[http://www.php.net/manual/en/language.variables.variable.php](http://www.php.net/manual/en/language.variables.variable.php)
-------------------------------------
Warning
Please note that variable variables cannot be used with PHP's Superglobal arrays within functions or class methods. The variable $this is also a special variable that cannot be referenced dynamically.
-------------------------------------`

[＋add a note](https://www.php.net/manual/add-note.php?sect=reserved.variables.globals&repo=en&redirect=https://www.php.net/manual/en/reserved.variables.globals.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google