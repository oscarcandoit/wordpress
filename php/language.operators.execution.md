---
url: https://www.php.net/manual/en/language.operators.execution.php
scraped_at: 2025-10-20T02:35:39.840Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Execution Operators [¶](https://www.php.net/manual/en/language.operators.execution.php\#language.operators.execution)

PHP supports one execution operator: backticks ( ``` `` ```). Note that
these are not single-quotes! PHP will attempt to execute the
contents of the backticks as a shell command; the output will be
returned (i.e., it won't simply be dumped to output; it can be
assigned to a variable). Use of the backtick operator is identical
to [shell\_exec()](https://www.php.net/manual/en/function.shell-exec.php).


**Example #1 Backtick Operator**

``<?php
$output = `ls -al`;
echo "<pre>$output</pre>";
?>``

> **Note**:
>
>
> The backtick operator is disabled when
> [shell\_exec()](https://www.php.net/manual/en/function.shell-exec.php) is disabled.

> **Note**:
>
>
> Unlike some other languages, backticks have no special meaning
> within double-quoted strings.

### See Also

- [Program Execution functions](https://www.php.net/manual/en/ref.exec.php)
- [popen()](https://www.php.net/manual/en/function.popen.php)
- [proc\_open()](https://www.php.net/manual/en/function.proc-open.php)
- [Using PHP from the commandline](https://www.php.net/manual/en/features.commandline.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/operators/execution.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.operators.execution%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.execution&repo=en&redirect=https://www.php.net/manual/en/language.operators.execution.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=62489&page=language.operators.execution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62489&page=language.operators.execution&vote=down "Vote down!")

159


[**_robert_**](https://www.php.net/manual/en/language.operators.execution.php#62489) [¶](https://www.php.net/manual/en/language.operators.execution.php#62489)

**19 years ago**

``Just a general usage note.  I had a very difficult time solving a problem with my script, when I accidentally put one of these backticks at the beginning of a line, like so:
[lots of code]
`    $URL = "blah...";
[more code]
Since the backtick is right above the tab key, I probably just fat-fingered it while indenting the code.
What made this so hard to find, was that PHP reported a parse error about 50 or so lines *below* the line containing the backtick.  (There were no other backticks anywhere in my code.)  And the error message was rather cryptic:
Parse error: parse error, expecting `T_STRING' or `T_VARIABLE' or `T_NUM_STRING' in /blah.php on line 446
Just something to file away in case you're pulling your hair out trying to find an error that "isn't there."``

[up](https://www.php.net/manual/vote-note.php?id=120273&page=language.operators.execution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120273&page=language.operators.execution&vote=down "Vote down!")

123


[**_ohcc at 163 dot com_**](https://www.php.net/manual/en/language.operators.execution.php#120273) [¶](https://www.php.net/manual/en/language.operators.execution.php#120273)

**8 years ago**

```You can use variables within a pair of backticks (``).
<?php
    $host = 'www.wuxiancheng.cn';
    echo `ping -n 3 {$host}`;
?>```

[up](https://www.php.net/manual/vote-note.php?id=127915&page=language.operators.execution&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127915&page=language.operators.execution&vote=down "Vote down!")

5


[**_paolo.bertani_**](https://www.php.net/manual/en/language.operators.execution.php#127915) [¶](https://www.php.net/manual/en/language.operators.execution.php#127915)

**2 years ago**

``If you want to avoid situations like the one described by @robert you may want to disable `shell_exec` and -as a consequence- the backtick operator.
To do this just edit the `php.ini` file and add `shell_exec` to the `disable_functions` setting:
    ; This directive allows you to disable certain functions.
    ; It receives a comma-delimited list of function names.
    ; [https://php.net/disable-functions](https://php.net/disable-functions)
    disable_functions = "shell_exec"
Then you can still use `exec()` to run terminal commands.``

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.operators.execution&repo=en&redirect=https://www.php.net/manual/en/language.operators.execution.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google