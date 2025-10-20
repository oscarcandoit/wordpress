---
url: https://www.php.net/manual/en/function.getenv.php
scraped_at: 2025-10-20T02:40:40.159Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# getenv

(PHP 4, PHP 5, PHP 7, PHP 8)

getenv — Gets the value of a single or all environment variables

### Description [¶](https://www.php.net/manual/en/function.getenv.php\#refsect1-function.getenv-description)

**getenv**([?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$name` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$local_only` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**): [string](https://www.php.net/manual/en/language.types.string.php)\|[array](https://www.php.net/manual/en/language.types.array.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Gets the value of a single or all environment variables.


You can see a list of all the environmental variables by using
[phpinfo()](https://www.php.net/manual/en/function.phpinfo.php). Many of these variables are listed within
[» RFC 3875](https://datatracker.ietf.org/doc/html/rfc3875), specifically
section 4.1, "Request Meta-Variables".


### Parameters [¶](https://www.php.net/manual/en/function.getenv.php\#refsect1-function.getenv-parameters)

`name`

The variable name as a [string](https://www.php.net/manual/en/language.types.string.php) or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**.


`local_only`

When set to **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, only local environment variables are returned, set by the operating system or putenv. It only has
an effect when `name` is a [string](https://www.php.net/manual/en/language.types.string.php).


### Return Values [¶](https://www.php.net/manual/en/function.getenv.php\#refsect1-function.getenv-returnvalues)

Returns the value of the environment variable
`name`, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if the environment
variable `name` does not exist.
If `name` is **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, all environment variables are
returned as an associative [array](https://www.php.net/manual/en/language.types.array.php).


### Changelog [¶](https://www.php.net/manual/en/function.getenv.php\#refsect1-function.getenv-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | The `name` is now nullable. |
| 7.1.0 | The `name` can now be omitted to retrieve an<br> associative [array](https://www.php.net/manual/en/language.types.array.php) of all environment variables. |
| 7.0.9 | The `local_only` parameter has been added. |

### Examples [¶](https://www.php.net/manual/en/function.getenv.php\#refsect1-function.getenv-examples)

**Example #1 **getenv()** Example**

`<?php
// Example use of getenv()
$ip = getenv('REMOTE_ADDR');
// Or simply use a Superglobal ($_SERVER or $_ENV)
$ip = $_SERVER['REMOTE_ADDR'];
// Safely get the value of an environment variable, ignoring whether
// or not it was set by a SAPI or has been changed with putenv
$ip = getenv('REMOTE_ADDR', true) ?: getenv('REMOTE_ADDR')
?>`

### Notes [¶](https://www.php.net/manual/en/function.getenv.php\#refsect1-function.getenv-notes)

**Warning**

If PHP is running in a SAPI such as Fast CGI, this function will
always return the value of an environment variable set by the SAPI,
even if [putenv()](https://www.php.net/manual/en/function.putenv.php) has been used to set a local
environment variable of the same name. Use the `local_only`
parameter to return the value of locally-set environment variables.


### See Also [¶](https://www.php.net/manual/en/function.getenv.php\#refsect1-function.getenv-seealso)

- [putenv()](https://www.php.net/manual/en/function.putenv.php) \- Sets the value of an environment variable
- [apache\_getenv()](https://www.php.net/manual/en/function.apache-getenv.php) \- Get an Apache subprocess\_env variable
- [Superglobals](https://www.php.net/manual/en/language.variables.superglobals.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/info/functions/getenv.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.getenv%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.getenv&repo=en&redirect=https://www.php.net/manual/en/function.getenv.php)

### User Contributed Notes 12 notes

[up](https://www.php.net/manual/vote-note.php?id=122599&page=function.getenv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122599&page=function.getenv&vote=down "Vote down!")

56


[**_Anonymous_**](https://www.php.net/manual/en/function.getenv.php#122599) [¶](https://www.php.net/manual/en/function.getenv.php#122599)

**7 years ago**

`Contrary to what eng.mrkto.com said, getenv() isn't always case-insensitive. On Linux it is not:
<?php
var_dump(getenv('path')); // bool(false)
var_dump(getenv('Path')); // bool(false)
var_dump(getenv('PATH')); // string(13) "/usr/bin:/bin"`

[up](https://www.php.net/manual/vote-note.php?id=119680&page=function.getenv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119680&page=function.getenv&vote=down "Vote down!")

12


[**_yw()beeznest!com_**](https://www.php.net/manual/en/function.getenv.php#119680) [¶](https://www.php.net/manual/en/function.getenv.php#119680)

**9 years ago**

`As noted on httpoxy.org, getenv() can confuse you in having you believe that all variables come from a "safe" environment (not all of them do).
In particular, $_SERVER['HTTP_PROXY'] (or its equivalent getenv('HTTP_PROXY')) can be manually set in the HTTP request header, so it should not be considered safe in a CGI environment.
In short, try to avoid using getenv('HTTP_PROXY') without properly filtering it.`

[up](https://www.php.net/manual/vote-note.php?id=107421&page=function.getenv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107421&page=function.getenv&vote=down "Vote down!")

17


[**_php at keith tyler dot com_**](https://www.php.net/manual/en/function.getenv.php#107421) [¶](https://www.php.net/manual/en/function.getenv.php#107421)

**13 years ago**

`All of the notes and examples so far have been strictly CGI.
It should not be understated the usefulness of getenv()/putenv() in CLI as well.
You can pass a number of variables to a CLI script via environment variables, either in Unix/Linux bash/sh with the "VAR='foo'; export $VAR" paradigm, or in Windows with the "set VAR='foo'" paradigm. (Csh users, you're on your own!) getenv("VAR") will retrieve that value from the environment.
We have a system by which we include a file full of putenv() statements storing configuration values that can apply to many different CLI PHP programs. But if we want to override these values, we can use the shell's (or calling application, such as ant) environment variable setting method to do so.
This saves us from having to manage an unmanageable amount of one-off configuration changes per execution via command line arguments; instead we just set the appropriate env var first.`

[up](https://www.php.net/manual/vote-note.php?id=99134&page=function.getenv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99134&page=function.getenv&vote=down "Vote down!")

23


[**_eng.mrkto.com_**](https://www.php.net/manual/en/function.getenv.php#99134) [¶](https://www.php.net/manual/en/function.getenv.php#99134)

**15 years ago**

`This function is useful (compared to $_SERVER, $_ENV) because it searches $varname key in those array case-insensitive manner.
For example on Windows $_SERVER['Path'] is like you see Capitalized, not 'PATH' as you expected.
So just: <?php getenv('path') ?>`

[up](https://www.php.net/manual/vote-note.php?id=125403&page=function.getenv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125403&page=function.getenv&vote=down "Vote down!")

8


[**_jcastromail at yahoo dot es_**](https://www.php.net/manual/en/function.getenv.php#125403) [¶](https://www.php.net/manual/en/function.getenv.php#125403)

**5 years ago**

`I did a benchmark about env.
constants :
0.00067687034606934 ms
getenv :
0.056761026382446 ms
(less is better)
[https://github.com/eftec/php-benchmarks#define--const--env](https://github.com/eftec/php-benchmarks#define--const--env)
And, in Windows at leat, reading the env value is considerably slow (in comparison with a constant), so PHP doesn't cache the information and asks to the OS the env value per call.
So, if you are calling once per request, then there is not a problem. However, if you are calling it many times per request, then it could affects the performance.`

[up](https://www.php.net/manual/vote-note.php?id=39603&page=function.getenv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=39603&page=function.getenv&vote=down "Vote down!")

7


[**_kyong_**](https://www.php.net/manual/en/function.getenv.php#39603) [¶](https://www.php.net/manual/en/function.getenv.php#39603)

**21 years ago**

`As you know, getenv('DOCUMENT_ROOT') is useful.
However, under CLI environment(I tend to do quick check
if it works or not), it doesn't work without modified php.ini
file. So I add "export DOCUMENT_ROOT=~" in my .bash_profile.`

[up](https://www.php.net/manual/vote-note.php?id=123833&page=function.getenv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123833&page=function.getenv&vote=down "Vote down!")

2


[**_Anonymous_**](https://www.php.net/manual/en/function.getenv.php#123833) [¶](https://www.php.net/manual/en/function.getenv.php#123833)

**6 years ago**

`It is worth noting that since getenv('MY_VARIABLE') will return false when the variable given is not set, there is no direct way to distinguish between a variable that is unset and one that is explicitly set to the value bool(false) when using getenv().
This makes it somewhat tricky to have boolean environment variables default to true if unset, which you can work around either by using "falsy" values such as 0 with the strict comparison operators or by using the superglobal arrays and isset().`

[up](https://www.php.net/manual/vote-note.php?id=117301&page=function.getenv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117301&page=function.getenv&vote=down "Vote down!")

2


[**_pritisn at gmail dot com_**](https://www.php.net/manual/en/function.getenv.php#117301) [¶](https://www.php.net/manual/en/function.getenv.php#117301)

**10 years ago**

`for quick check of getenv() adding a new env variable -
if you add a new env variable, make sure not only apache but xampp is also restarted.
Otherwise getenv() will return false for the newly added env variable.`

[up](https://www.php.net/manual/vote-note.php?id=81771&page=function.getenv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81771&page=function.getenv&vote=down "Vote down!")

1


[**_sam at sambarrow dot com_**](https://www.php.net/manual/en/function.getenv.php#81771) [¶](https://www.php.net/manual/en/function.getenv.php#81771)

**17 years ago**

`SERVER_NAME is the name defined in the apache configuration.
HTTP_HOST is the host header sent by the client when using the more recent versions of the http protocol.`

[up](https://www.php.net/manual/vote-note.php?id=117022&page=function.getenv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117022&page=function.getenv&vote=down "Vote down!")

0


[**_hello at jabran dot me_**](https://www.php.net/manual/en/function.getenv.php#117022) [¶](https://www.php.net/manual/en/function.getenv.php#117022)

**10 years ago**

`Beware that when using this function with PHP built-in server – i.e. php -S localhost:8000 – it will return boolean FALSE.`

[up](https://www.php.net/manual/vote-note.php?id=122994&page=function.getenv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122994&page=function.getenv&vote=down "Vote down!")

 -1


[**_larby dot robert at gmail dot com_**](https://www.php.net/manual/en/function.getenv.php#122994) [¶](https://www.php.net/manual/en/function.getenv.php#122994)

**7 years ago**

`From PHP 7.1 => getenv() no longer requires its parameter. If the parameter is omitted, then the current environment variables will be returned as an associative array.
Source: [http://php.net/manual/en/migration71.changed-functions.php](http://php.net/manual/en/migration71.changed-functions.php)`

[up](https://www.php.net/manual/vote-note.php?id=97763&page=function.getenv&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=97763&page=function.getenv&vote=down "Vote down!")

 -1


[**_chuck dot reeves at gmail dot com_**](https://www.php.net/manual/en/function.getenv.php#97763) [¶](https://www.php.net/manual/en/function.getenv.php#97763)

**15 years ago**

`When writing CLI applications, not that any environment variables that are set in your web server config will not be passed through.  PHP will pass through system environment variables that are prefixed based off the safe_mode_allowed_env_vars directive in your php.ini`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.getenv&repo=en&redirect=https://www.php.net/manual/en/function.getenv.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google