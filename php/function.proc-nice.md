---
url: https://www.php.net/manual/en/function.proc-nice.php
scraped_at: 2025-10-20T02:53:35.161Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# proc\_nice

(PHP 5, PHP 7, PHP 8)

proc\_nice — Change the priority of the current process

### Description [¶](https://www.php.net/manual/en/function.proc-nice.php\#refsect1-function.proc-nice-description)

**proc\_nice**([int](https://www.php.net/manual/en/language.types.integer.php) `$priority`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**proc\_nice()** changes the priority of the current
process by the amount specified in `priority`. A
positive `priority` will lower the priority of the
current process, whereas a negative `priority`
will raise the priority.


**proc\_nice()** is not related to
[proc\_open()](https://www.php.net/manual/en/function.proc-open.php) and its associated functions in any way.


### Parameters [¶](https://www.php.net/manual/en/function.proc-nice.php\#refsect1-function.proc-nice-parameters)

`priority`

The new priority value, the value of this may differ on platforms.


On Unix, a low value, such as `-20` means high priority
whereas positive values have a lower priority.


For Windows the `priority` parameter has the
following meaning:


| Priority class | Possible values |
| --- | --- |
| High priority | `priority` `< -9` |
| Above normal priority | `priority` `< -4` |
| Normal priority | `priority` `< 5` & <br> `priority` `> -5` |
| Below normal priority | `priority` `> 5` |
| Idle priority | `priority` `> 9` |

### Return Values [¶](https://www.php.net/manual/en/function.proc-nice.php\#refsect1-function.proc-nice-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.
If an error occurs, like the user lacks permission to change the priority,
an error of level **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is also generated.


### Changelog [¶](https://www.php.net/manual/en/function.proc-nice.php\#refsect1-function.proc-nice-changelog)

| Version | Description |
| --- | --- |
| 7.2.0 | This function is now available on Windows. |

### Examples [¶](https://www.php.net/manual/en/function.proc-nice.php\#refsect1-function.proc-nice-examples)

**Example #1 Using **proc\_nice()** to set the process priority to high**

`<?php
// Highest priority
proc_nice(-20);
?>`

### Notes [¶](https://www.php.net/manual/en/function.proc-nice.php\#refsect1-function.proc-nice-notes)

> **Note**:
> **Availability**
>
> **proc\_nice()** will only exist if your system has 'nice'
> capabilities. 'nice' conforms to: SVr4, SVID EXT, AT&T, X/OPEN, BSD
> 4.3.

> **Note**:
> **Windows only**
>
> **proc\_nice()** will change the current _process_
> priority, even if PHP was compiled using thread safety.

### See Also [¶](https://www.php.net/manual/en/function.proc-nice.php\#refsect1-function.proc-nice-seealso)

- [pcntl\_setpriority()](https://www.php.net/manual/en/function.pcntl-setpriority.php) \- Change the priority of any process

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/exec/functions/proc-nice.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.proc-nice%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.proc-nice&repo=en&redirect=https://www.php.net/manual/en/function.proc-nice.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=111994&page=function.proc-nice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111994&page=function.proc-nice&vote=down "Vote down!")

7


[**_kevin AT REMOVETHIS mrkmg.com_**](https://www.php.net/manual/en/function.proc-nice.php#111994) [¶](https://www.php.net/manual/en/function.proc-nice.php#111994)

**12 years ago**

`On a Linux system, running apache2 as a non-privileged user you can not increase the niceness of the process after decreasing it. Also, you can not use the apache_child_ terminate either. I found the following does work though:
<?php
//decrease niceness
proc_nice(19);
//kill child process to "reset" niceness
posix_kill( getmypid(), 28 );
?>`

[up](https://www.php.net/manual/vote-note.php?id=98574&page=function.proc-nice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=98574&page=function.proc-nice&vote=down "Vote down!")

3


[**_php at richardneill dot org_**](https://www.php.net/manual/en/function.proc-nice.php#98574) [¶](https://www.php.net/manual/en/function.proc-nice.php#98574)

**15 years ago**

`If a process is reniced, then all its children inherit that niceness. So a PHP script can call proc_nice on itself, then invoke system(), and the command executed via system() will also be niced.
Also worth making a note of ionice. There's no PHP function for this, but it's important. A nice'd program will happily try to chew up all i/o bandwidth with very little CPU usage, it can therefore make the entire computer non-responsive despite the programmer's intention.  Use "ionice -c3"  or see "man ionice"`

[up](https://www.php.net/manual/vote-note.php?id=101944&page=function.proc-nice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101944&page=function.proc-nice&vote=down "Vote down!")

2


[**_Marek_**](https://www.php.net/manual/en/function.proc-nice.php#101944) [¶](https://www.php.net/manual/en/function.proc-nice.php#101944)

**14 years ago**

`Regarding ionice - on linux the impact of the ionice -c3 class is similar to that of nice, because the CPU "niceness" is taken into account when calculating the io niceness.`

[up](https://www.php.net/manual/vote-note.php?id=126009&page=function.proc-nice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126009&page=function.proc-nice&vote=down "Vote down!")

0


[**_phil\_php at zieaon dot com_**](https://www.php.net/manual/en/function.proc-nice.php#126009) [¶](https://www.php.net/manual/en/function.proc-nice.php#126009)

**4 years ago**

`It is important to note that this is a relative change. I didn't read the description properly and couldn't figure out why setting proc_nice(0) didn't take the forked children back to 0!
For example if you run:
<?php
proc_nice(-5);
proc_nice(0); // will have no effect
proc_nice(5); // will take the niceness back to 0

?>
In PHP CLI under Debian (and probably many other Linux flavours) you can read the 'niceness' from the proc filesystem.  (There may be a PHP command that gives this info but there doesn't seem to be a link to it on this page.)
E.g
<?php
$Current_Niceness_Value = intval(explode(" ",file_get_contents("/proc/".getmypid()."/stat"))[18]);
// Note: Older versions of Linux return an unsigned integer which has to be converted to a signed integer.
$Current_Niceness_Value = unpack("l",pack("L",intval(explode(" ",file_get_contents("/proc/".getmypid()."/stat"))[18])))[1];
?>`

[up](https://www.php.net/manual/vote-note.php?id=87225&page=function.proc-nice&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87225&page=function.proc-nice&vote=down "Vote down!")

0


[**_pandi at home dot pl_**](https://www.php.net/manual/en/function.proc-nice.php#87225) [¶](https://www.php.net/manual/en/function.proc-nice.php#87225)

**16 years ago**

``Simple function for check process nice, by default returns nice of current process:
<?php
public static function getProcessNice ($pid = null) {
    if (!$pid) {
        $pid = getmypid ();
    }

    $res = `ps -p $pid -o "%p %n"`;

    preg_match ('/^\s*\w+\s+\w+\s*(\d+)\s+(\d+)/m', $res, $matches);

    return array ('pid' => (isset ($matches[1]) ? $matches[1] : null), 'nice' => (isset ($matches[2]) ? $matches[2] : null));
}
?>``

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.proc-nice&repo=en&redirect=https://www.php.net/manual/en/function.proc-nice.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google