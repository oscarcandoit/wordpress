---
url: https://www.php.net/manual/en/function.escapeshellarg.php
scraped_at: 2025-10-20T02:49:24.402Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# escapeshellarg

(PHP 4 >= 4.0.3, PHP 5, PHP 7, PHP 8)

escapeshellarg — Escape a string to be used as a shell argument

### Description [¶](https://www.php.net/manual/en/function.escapeshellarg.php\#refsect1-function.escapeshellarg-description)

**escapeshellarg**([string](https://www.php.net/manual/en/language.types.string.php) `$arg`): [string](https://www.php.net/manual/en/language.types.string.php)

**escapeshellarg()** adds single quotes around a string
and quotes/escapes any existing single quotes allowing you to pass a
string directly to a shell function and having it be treated as a single
safe argument. This function should be used to escape individual
arguments to shell functions coming from user input. The shell functions
include [exec()](https://www.php.net/manual/en/function.exec.php), [system()](https://www.php.net/manual/en/function.system.php) and the
[backtick operator](https://www.php.net/manual/en/language.operators.execution.php).


On Windows, **escapeshellarg()** instead replaces percent
signs, exclamation marks (delayed variable substitution) and double quotes
with spaces and adds double quotes around the string.
Furthermore, each streak of consecutive backslashes ( `\`)
is escaped by one additional backslash.


### Parameters [¶](https://www.php.net/manual/en/function.escapeshellarg.php\#refsect1-function.escapeshellarg-parameters)

`arg`

The argument that will be escaped.


### Return Values [¶](https://www.php.net/manual/en/function.escapeshellarg.php\#refsect1-function.escapeshellarg-returnvalues)

The escaped string.


### Examples [¶](https://www.php.net/manual/en/function.escapeshellarg.php\#refsect1-function.escapeshellarg-examples)

**Example #1 **escapeshellarg()** example**

`<?php
system('ls '.escapeshellarg($dir));
?>`

### See Also [¶](https://www.php.net/manual/en/function.escapeshellarg.php\#refsect1-function.escapeshellarg-seealso)

- [escapeshellcmd()](https://www.php.net/manual/en/function.escapeshellcmd.php) \- Escape shell metacharacters
- [exec()](https://www.php.net/manual/en/function.exec.php) \- Execute an external program
- [popen()](https://www.php.net/manual/en/function.popen.php) \- Opens process file pointer
- [system()](https://www.php.net/manual/en/function.system.php) \- Execute an external program and display the output
- [backtick operator](https://www.php.net/manual/en/language.operators.execution.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/exec/functions/escapeshellarg.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.escapeshellarg%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.escapeshellarg&repo=en&redirect=https://www.php.net/manual/en/function.escapeshellarg.php)

### User Contributed Notes 19 notes

[up](https://www.php.net/manual/vote-note.php?id=99213&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99213&page=function.escapeshellarg&vote=down "Vote down!")

105


[**_phil at philfreo dot com_**](https://www.php.net/manual/en/function.escapeshellarg.php#99213) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#99213)

**15 years ago**

`When escapeshellarg() was stripping my non-ASCII characters from a UTF-8 string, adding the following fixed the problem:
<?php
setlocale(LC_CTYPE, "en_US.UTF-8");
?>`

[up](https://www.php.net/manual/vote-note.php?id=128249&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128249&page=function.escapeshellarg&vote=down "Vote down!")

9


[**_lucgommans.nl_**](https://www.php.net/manual/en/function.escapeshellarg.php#128249) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#128249)

**2 years ago**

`This does not prevent all forms of command injection.
<?php
// GET /example.php?file[]=x&file[]=-I&file[]=bash%20-c%20touch\%20/tmp/lucwashere
$files_to_archive = [];
foreach ($_GET['file'] as $file) {
    $files_to_archive[] = escapeshellarg($file);
}
exec("tar cf my.tar " . implode(' ', $files_to_archive));
?>
Despite correct escaping to prevent shell injection, this will run the specified code. The arguments instruct tar to run a command in bash. You can then check the /tmp directory to verify that the code ran.
Of course, an attacker would replace this with a more malicious variant. For black box vulnerability testing, a sleep of a few seconds can be safely used to determine whether the parameter is vulnerable.
The vulnerability here is that tar, like nearly every other program, will interpret arguments that start with a hyphen as an option that modifies its behaviour. Many programs, such as tcpdump, man, zip, gpg, tar, etc., have an option to execute another command. Even if you use a program that does not (and will never) have such an execution option, its functioning would be influenced by the specified extra options, either on purpose or by accident because some string just happens to start with a hyphen (similar to how fields vulnerable to SQL injection accidentally break on any data with an apostrophe or quote symbol in it: it's just bad UX).
Many programs allow using a double hyphen, --, to separate positional arguments from options. If you change the above code to use this exec line, it is no longer vulnerable:
<?php
// notice the -- after specifying the options we want
exec("tar cf my.tar -- " . implode(' ', $files_to_archive));
?>
Not every program supports this separator, in which case you need to find an alternative input method (e.g., nmap -iL targets.txt instead of nmap 2001:db8::/96) or deny starting arguments with a hyphen.
Of course, ideally one would use data bindings via libraries to avoid having to do the dangerous escaping dance altogether, similar to parameterized SQL queries, but I did not yet see this caveat mentioned and thought it worth adding for when escapeshellarg() is still used.`

[up](https://www.php.net/manual/vote-note.php?id=123718&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123718&page=function.escapeshellarg&vote=down "Vote down!")

14


[**_daverandom_**](https://www.php.net/manual/en/function.escapeshellarg.php#123718) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#123718)

**6 years ago**

`On Windows, this function naively strips special characters and replaces them with spaces. The resulting string is always safe for use with exec() etc, but the operation is not lossless - strings containing " or % will not be passed through to the child process correctly.
Correctly escaping shell commands on Windows is not a simple matter. Programs must consider two distinct escape mechanisms which serve different purposes:
1) The convention used by the CommandLineToArgV() windows system function, used by the child process to interpret the command line string
2) The convention used by cmd.exe to escape shell meta-characters (e.g. output redirection controls)
All commands should be escaped for CommandLineToArgV() - this mechanism is applied to each argument individually before it is appended to the command line string. The resulting string may be safely used with the CreateProcess() family of system functions. However...
In almost all cases when creating a child process from PHP on Windows, it is done indirectly by invoking cmd.exe - this is to enable the use of shell functionality such as I/O redirection and environment variable substitution. As a consequence, the entire command string must be further escaped for cmd.exe. If the executed command contains further indirect calls through cmd.exe, each child command must be escaped again for each level of indirection.
The following functions can be used to correctly escape strings such that they are safely passed through to a child process:
<?php
/**
* Escape a single value in accordance with CommandLineToArgV()
* [https://docs.microsoft.com/en-us/previous-versions/17w5ykft(v=vs.85](https://docs.microsoft.com/en-us/previous-versions/17w5ykft(v=vs.85))
*/
function escape_win32_argv(string $value): string
{
    static $expr = '(
        [\x00-\x20\x7F"] # control chars, whitespace or double quote
      | \\\\++ (?=("|$)) # backslashes followed by a quote or at the end
    )ux';
    if ($value === '') {
        return '""';
    }
    $quote = false;
    $replacer = function($match) use($value, &$quote) {
        switch ($match[0][0]) { // only inspect the first byte of the match
            case '"': // double quotes are escaped and must be quoted
                $match[0] = '\\"';
            case ' ': case "\t": // spaces and tabs are ok but must be quoted
                $quote = true;
                return $match[0];
            case '\\': // matching backslashes are escaped if quoted
                return $match[0] . $match[0];
            default: throw new InvalidArgumentException(sprintf(
                "Invalid byte at offset %d: 0x%02X",
                strpos($value, $match[0]), ord($match[0])
            ));
        }
    };
    $escaped = preg_replace_callback($expr, $replacer, (string)$value);
    if ($escaped === null) {
        throw preg_last_error() === PREG_BAD_UTF8_ERROR
            ? new InvalidArgumentException("Invalid UTF-8 string")
            : new Error("PCRE error: " . preg_last_error());
    }
    return $quote // only quote when needed
        ? '"' . $escaped . '"'
        : $value;
}
/** Escape cmd.exe metacharacters with ^ */
function escape_win32_cmd(string $value): string
{
    return preg_replace('([()%!^"<>&|])', '^$0', $value);
}
/** Like shell_exec() but bypass cmd.exe */
function noshell_exec(string $command): string
{
    static $descriptors = [['pipe', 'r'],['pipe', 'w'],['pipe', 'w']],
           $options = ['bypass_shell' => true];
    if (!$proc = proc_open($command, $descriptors, $pipes, null, null, $options)) {
        throw new \Error('Creating child process failed');
    }
    fclose($pipes[0]);
    $result = stream_get_contents($pipes[1]);
    fclose($pipes[1]);
    stream_get_contents($pipes[2]);
    fclose($pipes[2]);
    proc_close($proc);
    return $result;
}
// usage
$badString = 'String with "C:\\quotes\\" or malicious %OS% stuff \\';
$cmdParts = [\
    'php',\
    '-d', 'display_errors=1', '-d', 'error_reporting=-1',\
    '-r', 'echo $argv[1];',\
    $badString // child process $argv[1] value\
];
/* The typical approach - works fine on POSIX shells but totally wrong
on Windows */
$wrong = implode(' ', array_map('escapeshellarg', $cmdParts));
/* Always escape each argument individually */
$escaped = implode(' ', array_map('escape_win32_argv', $cmdParts));
/* In almost all cases, escape for cmd.exe as well - the only exception is
when using proc_open() with the bypass_shell option. cmd doesn't handle
arguments individually, so the entire command line string can be escaped,
no need to process arguments individually */
$cmd = escape_win32_cmd($escaped);
$cmds = [\
    'escapeshellarg() - wrong' => $wrong,\
    'escape_win32_argv() - correct for bypass_shell' => $escaped,\
    'escape_win32_cmd(escape_win32_argv()) - correct everywhere else' => $cmd,\
];
function check($original, $received)
{
    $match = $original === $received ? '=' : 'X';
    return "$match '$received'";
}
foreach ($cmds as $description => $cmd) {
    echo "$description\n";
    echo " $cmd\n";
    echo "  original:         '$badString'\n";
    echo "  shell_exec():   " . check($badString, shell_exec($cmd)) . "\n";
    echo "  noshell_exec(): " . check($badString, noshell_exec($cmd)) . "\n";
    echo "\n";
}`

[up](https://www.php.net/manual/vote-note.php?id=74815&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74815&page=function.escapeshellarg&vote=down "Vote down!")

15


[**_egorinsk at gmail dot com_**](https://www.php.net/manual/en/function.escapeshellarg.php#74815) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#74815)

**18 years ago**

`Under Windows, this function puts string into double-quotes, not single, and replaces %(percent sign) with a space, that's why it's impossible to pass a filename with percents in its name through this function.`

[up](https://www.php.net/manual/vote-note.php?id=66430&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=66430&page=function.escapeshellarg&vote=down "Vote down!")

22


[**_Anonymous_**](https://www.php.net/manual/en/function.escapeshellarg.php#66430) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#66430)

**19 years ago**

``Most of the comments above have misunderstood this function. It does not need to escape characters such as '$' and '`' - it uses the fact that the shell does not treat any characters as special inside single quotes (except the single quote character itself). The correct way to use this function is to call it on a variable that is intended to be passed to a command-line program as a single argument to that program - you do not call it on command-line as a whole.
The person above who comments that this function behaves badly if given the empty string as input is correct - this is a bug. It should indeed return two single quotes in this case.``

[up](https://www.php.net/manual/vote-note.php?id=123281&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123281&page=function.escapeshellarg&vote=down "Vote down!")

5


[**_Jasen_**](https://www.php.net/manual/en/function.escapeshellarg.php#123281) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#123281)

**6 years ago**

`if you want empty arguments for empty input
use the form

     escapeshellarg($input)."''"
the shell will treat foo'' as foo  but empty input will become an empty argument instead of a missing one.`

[up](https://www.php.net/manual/vote-note.php?id=94020&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=94020&page=function.escapeshellarg&vote=down "Vote down!")

7


[**_phpman at crustynet dot org dot uk_**](https://www.php.net/manual/en/function.escapeshellarg.php#94020) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#94020)

**16 years ago**

``The comment from 'rmays at castlecomm dot com' is incorrect: single quotes cannot be backslash-escaped inside a single-quoted string when constructing a shell argument. The output from this function is in fact correct. It drops out of the single-quoted string, includes a literal single quote with a backslash-escape, then resumes the single-quoted string. Observe:
[shellarg.php]
<?php
system("echo ' single quote\'d '");
system("echo ' single quote'\''d '");
?>
$ php shellarg.php
sh: -c: line 0: unexpected EOF while looking for matching `''
sh: -c: line 1: syntax error: unexpected end of file
single quote'd``

[up](https://www.php.net/manual/vote-note.php?id=84789&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84789&page=function.escapeshellarg&vote=down "Vote down!")

9


[**_Audun_**](https://www.php.net/manual/en/function.escapeshellarg.php#84789) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#84789)

**17 years ago**

`The reason why % are replaced with space on windows is that it is impossible in cmd.exe to escape or quote them so that environment variables are not expanded.  If for instance %path% is in your argument it will always be expanded, so the only safe thing to do is to replace % with something else.
Alternatively, you could wipe the environment before making the call to exec(), but that has its side-effects.`

[up](https://www.php.net/manual/vote-note.php?id=88325&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88325&page=function.escapeshellarg&vote=down "Vote down!")

4


[**_info at infosoporte dot com_**](https://www.php.net/manual/en/function.escapeshellarg.php#88325) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#88325)

**16 years ago**

`If escapeshellarg() function removes your accents (like á, a with an 'accute') from the given string, ensure your LC_ALL variable is correct. If using it via web, you need to restart Apache or the corresponding web server after setting LC_ALL with a export LC_ALL=es_ES.utf8 (for example) from your shell.`

[up](https://www.php.net/manual/vote-note.php?id=127603&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127603&page=function.escapeshellarg&vote=down "Vote down!")

1


[**_Tony C_**](https://www.php.net/manual/en/function.escapeshellarg.php#127603) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#127603)

**3 years ago**

`While using this function to pass filenames to the command line I noticed shell_exec() was failing. Upon further investigation it appears escapeshellarg() removes double spaces from file names.
For example:
$filename = "my  super file.txt"; // notice the double space after "my"
echo escapeshellarg($filename);
Produces:
'my super file.txt'
(second space was removed)`

[up](https://www.php.net/manual/vote-note.php?id=126916&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126916&page=function.escapeshellarg&vote=down "Vote down!")

1


[**_Jannis_**](https://www.php.net/manual/en/function.escapeshellarg.php#126916) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#126916)

**3 years ago**

`escapeshellarg() will strip all invalid characters according to your locale settings (e.g. latin-1 characters are stripped when locale/LC_CTYPE is UTF-8).
Please keep in mind that the locale support depends on your C standard library while compiling. This might result in strange behavior on embedded systems that use a standard library with poor locale support, other  than glibc.`

[up](https://www.php.net/manual/vote-note.php?id=109514&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=109514&page=function.escapeshellarg&vote=down "Vote down!")

7


[**_sblyons+php at gmail dot com_**](https://www.php.net/manual/en/function.escapeshellarg.php#109514) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#109514)

**13 years ago**

`Take care if using escapeshellarg() on serialized objects. Serialized objects contain null bytes, and escapeshellarg stops on the first null byte so you will not receive the full argument. (I consider this a bug, though not sure what it should do in this case. Probably serialize shouldn't have used null bytes, but too late for that now).
The workaround I've found to pass serialized objects on the command line is to base64_encode() them first and decode on the other side.`

[up](https://www.php.net/manual/vote-note.php?id=125018&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125018&page=function.escapeshellarg&vote=down "Vote down!")

0


[**_crose_**](https://www.php.net/manual/en/function.escapeshellarg.php#125018) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#125018)

**5 years ago**

``Ubuntu: wondering why your system locale (e.g. 'en_US.UTF-8') is  not inherited to your Apache (still 'C')?
Check `/etc/apache2/envvars`  ... activate the line `. /etc/default/locale` ``

[up](https://www.php.net/manual/vote-note.php?id=125808&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125808&page=function.escapeshellarg&vote=down "Vote down!")

 -1


[**_divinity76 at gmail dot com_**](https://www.php.net/manual/en/function.escapeshellarg.php#125808) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#125808)

**4 years ago**

`if you need to generate Linux arguments even when running on Windows, try
<?php
    /**
     * quote arguments using linux escape rules, regardless of host OS
     * (eg, it will use linux escape rules even when running on Windows)
     *
     * @param string $arg
     * @throws \InvalidArgumentException if argument contains null bytes
     * @return string
     */
    /*public static*/ function linux_escapeshellarg(string $arg): string
    {
        if (false !== strpos($arg, "\x00")) {
            throw new \InvalidArgumentException("argument contains null bytes, it's impossible to escape null bytes!");
        }
        return "'" . strtr($arg, [\
            "'" => "'\\''"\
        ]) . "'";
    }`

[up](https://www.php.net/manual/vote-note.php?id=125807&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125807&page=function.escapeshellarg&vote=down "Vote down!")

 -1


[**_Anonymous_**](https://www.php.net/manual/en/function.escapeshellarg.php#125807) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#125807)

**4 years ago**

`if you need to generate Linux arguments even when running on Windows, try
<?php
    /**
     * quote arguments using linux escape rules, regardless of host OS
     * (eg, it will use linux escape rules even when running on Windows)
     *
     * @param string $arg
     * @throws \InvalidArgumentException if argument contains null bytes
     * @return string
     */
    /*public static*/ function linux_escapeshellarg(string $arg): string
    {
        if (false !== strpos($arg, "\x00")) {
            throw new \InvalidArgumentException("argument contains null bytes, it's impossible to escape null bytes!");
        }
        return "'" . strtr($arg, [\
            "'" => "'\\''"\
        ]) . "'";
    }`

[up](https://www.php.net/manual/vote-note.php?id=114873&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114873&page=function.escapeshellarg&vote=down "Vote down!")

0


[**_jon at wroth dot org_**](https://www.php.net/manual/en/function.escapeshellarg.php#114873) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#114873)

**11 years ago**

`the best alternative to escapeshellarg() for windows i've come up with is this:
<?php
function w32escapeshellarg($s)
{ return '"' . addcslashes($s, '\\"') . '"'; }
?>`

[up](https://www.php.net/manual/vote-note.php?id=111919&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111919&page=function.escapeshellarg&vote=down "Vote down!")

 -1


[**_wijnand at jpresult dot nl_**](https://www.php.net/manual/en/function.escapeshellarg.php#111919) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#111919)

**12 years ago**

`Here's a quick and dirty replacement of this function in case you need to deal with special characters.
<?php
/**
* An ugly, non-ASCII-character safe replacement of escapeshellarg().
*/
function escapeshellarg_special($file) {
return "'" . str_replace("'", "'\"'\"'", $file) . "'";
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=91814&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91814&page=function.escapeshellarg&vote=down "Vote down!")

 -1


[**_jrbeaure at uvm dot edu_**](https://www.php.net/manual/en/function.escapeshellarg.php#91814) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#91814)

**16 years ago**

`When running a string of LaTeX code containing hyphens through as an argument to pdflatex escaped using this command, it will result in failure.`

[up](https://www.php.net/manual/vote-note.php?id=40996&page=function.escapeshellarg&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=40996&page=function.escapeshellarg&vote=down "Vote down!")

 -5


[**_vosechu at roman-fleuve dot com_**](https://www.php.net/manual/en/function.escapeshellarg.php#40996) [¶](https://www.php.net/manual/en/function.escapeshellarg.php#40996)

**21 years ago**

`If escapeshellarg() returned something on a null input it would probably break more programs than it helps. Even if it's two "'s or two ''s, this function wouldn't work the way it's supposed to (that is, returning nothing).
However, most people do not put "" into their commands but I can see where it might be useful at the same time.
Perhaps an option in the command that would return the type of null we want. I might want the null character to be returned, someone else might want '', and someone else might want nothing at all.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.escapeshellarg&repo=en&redirect=https://www.php.net/manual/en/function.escapeshellarg.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google