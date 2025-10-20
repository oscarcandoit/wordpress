---
url: https://www.php.net/manual/en/reserved.variables.argv.php
scraped_at: 2025-10-20T02:53:45.314Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# $argv

(PHP 4, PHP 5, PHP 7, PHP 8)

$argv — Array of arguments passed to script

### Description [¶](https://www.php.net/manual/en/reserved.variables.argv.php\#refsect1-reserved.variables.argv-description)

Contains an [array](https://www.php.net/manual/en/language.types.array.php) of all the arguments passed to the script when running
from the [command line](https://www.php.net/manual/en/features.commandline.php).


> **Note**:
>
> The first argument $argv\[0\] is always the name that was
> used to run the script.

> **Note**:
>
> This variable is not available when [register\_argc\_argv](https://www.php.net/manual/en/ini.core.php#ini.register-argc-argv)
> is disabled.

**Warning**

To test if a script is being run from the command
line, [php\_sapi\_name()](https://www.php.net/manual/en/function.php-sapi-name.php) should be used
instead of checking whether $argv or
[$\_SERVER\['argv'\]](https://www.php.net/manual/en/reserved.variables.server.php) is set.


### Examples [¶](https://www.php.net/manual/en/reserved.variables.argv.php\#refsect1-reserved.variables.argv-examples)

**Example #1 $argv example**

`<?php
var_dump($argv);
?>`

When executing the example with: php script.php arg1 arg2 arg3


The above example will output
something similar to:

```
array(4) {
  [0]=>
  string(10) "script.php"
  [1]=>
  string(4) "arg1"
  [2]=>
  string(4) "arg2"
  [3]=>
  string(4) "arg3"
}
```

### Notes [¶](https://www.php.net/manual/en/reserved.variables.argv.php\#refsect1-reserved.variables.argv-notes)

> **Note**:
>
>
> This is also available as [$\_SERVER\['argv'\]](https://www.php.net/manual/en/reserved.variables.server.php).

### See Also [¶](https://www.php.net/manual/en/reserved.variables.argv.php\#refsect1-reserved.variables.argv-seealso)

- [getopt()](https://www.php.net/manual/en/function.getopt.php) \- Gets options from the command line argument list
- [$argc](https://www.php.net/manual/en/reserved.variables.argc.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/predefined/variables/argv.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Freserved.variables.argv%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=reserved.variables.argv&repo=en&redirect=https://www.php.net/manual/en/reserved.variables.argv.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=105491&page=reserved.variables.argv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105491&page=reserved.variables.argv&vote=down "Vote down!")

89


[**_tufan dot oezduman at googlemail dot com_**](https://www.php.net/manual/en/reserved.variables.argv.php#105491) [¶](https://www.php.net/manual/en/reserved.variables.argv.php#105491)

**14 years ago**

`Please note that, $argv and $argc need to be declared global, while trying to access within a class method.
<?php
class A
{
    public static function b()
    {
        var_dump($argv);
        var_dump(isset($argv));
    }
}
A::b();
?>
will output NULL bool(false)  with a notice of "Undefined variable ..."
whereas global $argv fixes that.`

[up](https://www.php.net/manual/vote-note.php?id=113614&page=reserved.variables.argv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113614&page=reserved.variables.argv&vote=down "Vote down!")

32


[**_hamboy75 at example dot com_**](https://www.php.net/manual/en/reserved.variables.argv.php#113614) [¶](https://www.php.net/manual/en/reserved.variables.argv.php#113614)

**11 years ago**

`To use $_GET so you dont need to support both if it could be used from command line and from web browser.
foreach ($argv as $arg) {
    $e=explode("=",$arg);
    if(count($e)==2)
        $_GET[$e[0]]=$e[1];
    else
        $_GET[$e[0]]=0;
}`

[up](https://www.php.net/manual/vote-note.php?id=128419&page=reserved.variables.argv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128419&page=reserved.variables.argv&vote=down "Vote down!")

0


[**_vatruski at t dot me_**](https://www.php.net/manual/en/reserved.variables.argv.php#128419) [¶](https://www.php.net/manual/en/reserved.variables.argv.php#128419)

**2 years ago**

`You can reinitialize the argument variables for web applications.
So if you created a command line, with some additional tweaks you can make it work on the web.`

[up](https://www.php.net/manual/vote-note.php?id=93532&page=reserved.variables.argv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93532&page=reserved.variables.argv&vote=down "Vote down!")

2


[**_Steve Schmitt_**](https://www.php.net/manual/en/reserved.variables.argv.php#93532) [¶](https://www.php.net/manual/en/reserved.variables.argv.php#93532)

**16 years ago**

`If you come from a shell scripting background, you might expect to find this topic under the heading "positional parameters".`

[up](https://www.php.net/manual/vote-note.php?id=118368&page=reserved.variables.argv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118368&page=reserved.variables.argv&vote=down "Vote down!")

0


[**_php at simoneast dot net_**](https://www.php.net/manual/en/reserved.variables.argv.php#118368) [¶](https://www.php.net/manual/en/reserved.variables.argv.php#118368)

**9 years ago**

`Sometimes $argv can be null, such as when "register-argc-argv" is set to false.  In some cases I've found the variable is populated correctly when running "php-cli" instead of just "php" from the command line (or cron).`

[up](https://www.php.net/manual/vote-note.php?id=126643&page=reserved.variables.argv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126643&page=reserved.variables.argv&vote=down "Vote down!")

 -1


[**_Radon8472_**](https://www.php.net/manual/en/reserved.variables.argv.php#126643) [¶](https://www.php.net/manual/en/reserved.variables.argv.php#126643)

**3 years ago**

``I discovered that `register_argc_argv` is alway OFF if you use php internal webserver, even if it is set to `On` in the php.ini.
What means there seems to be no way to access argv / argc in php internal commandline server.``

[＋add a note](https://www.php.net/manual/add-note.php?sect=reserved.variables.argv&repo=en&redirect=https://www.php.net/manual/en/reserved.variables.argv.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google