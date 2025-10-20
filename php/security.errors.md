---
url: https://www.php.net/manual/en/security.errors.php
scraped_at: 2025-10-20T02:36:25.600Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Error Reporting [¶](https://www.php.net/manual/en/security.errors.php\#security.errors)

With PHP security, there are two sides to error reporting. One is
beneficial to increasing security, the other is detrimental.


A standard attack tactic involves profiling a system by feeding
it improper data, and checking for the kinds, and contexts, of the
errors which are returned. This allows the system cracker to probe
for information about the server, to determine possible weaknesses.
For example, if an attacker had gleaned information about a page
based on a prior form submission, they may attempt to override
variables, or modify them:


**Example #1 Attacking Variables with a custom HTML page**

```
<form method="post" action="attacktarget?username=badfoo&amp;password=badfoo">
<input type="hidden" name="username" value="badfoo" />
<input type="hidden" name="password" value="badfoo" />
</form>
```

The PHP errors which are normally returned can be quite helpful to a
developer who is trying to debug a script, indicating such things
as the function or file that failed, the PHP file it failed in,
and the line number which the failure occurred in. This is all
information that can be exploited. It is not uncommon for a php
developer to use [show\_source()](https://www.php.net/manual/en/function.show-source.php),
[highlight\_string()](https://www.php.net/manual/en/function.highlight-string.php), or
[highlight\_file()](https://www.php.net/manual/en/function.highlight-file.php) as a debugging measure, but in
a live site, this can expose hidden variables, unchecked syntax,
and other dangerous information. Especially dangerous is running
code from known sources with built-in debugging handlers, or using
common debugging techniques. If the attacker can determine what
general technique you are using, they may try to brute-force a page,
by sending various common debugging strings:


**Example #2 Exploiting common debugging variables**

```
<form method="post" action="attacktarget?errors=Y&amp;showerrors=1&amp;debug=1">
<input type="hidden" name="errors" value="Y" />
<input type="hidden" name="showerrors" value="1" />
<input type="hidden" name="debug" value="1" />
</form>
```

Regardless of the method of error handling, the ability to probe a
system for errors leads to providing an attacker with more
information.


For example, the very style of a generic PHP error indicates a system
is running PHP. If the attacker was looking at an `.html` page, and
wanted to probe for the back-end (to look for known weaknesses in
the system), by feeding it the wrong data they may be able to
determine that a system was built with PHP.


A function error can indicate whether a system may be running a
specific database engine, or give clues as to how a web page or
programmed or designed. This allows for deeper investigation into
open database ports, or to look for specific bugs or weaknesses
in a web page. By feeding different pieces of bad data, for example,
an attacker can determine the order of authentication in a script,
(from the line number errors) as well as probe for exploits that
may be exploited in different locations in the script.


A filesystem or general PHP error can indicate what permissions
the web server has, as well as the structure and organization of
files on the web server. Developer written error code can aggravate
this problem, leading to easy exploitation of formerly "hidden"
information.


There are three major solutions to this issue. The first is to
scrutinize all functions, and attempt to compensate for the bulk
of the errors. The second is to disable error reporting entirely
on the running code. The third is to use PHP's custom error
handling functions to create your own error handler. Depending
on your security policy, you may find all three to be applicable
to your situation.


One way of catching this issue ahead of time is to make use of
PHP's own [error\_reporting()](https://www.php.net/manual/en/function.error-reporting.php), to help you
secure your code and find variable usage that may be dangerous.
By testing your code, prior to deployment, with **`[E\_ALL](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-all)`**,
you can quickly find areas where your variables may be open to poisoning
or modification in other ways. Once you are ready for deployment,
you should either disable error reporting completely by setting
[error\_reporting()](https://www.php.net/manual/en/function.error-reporting.php) to 0, or turn off the error
display using the php.ini option `display_errors`,
to insulate your code from probing. If you choose to do the latter,
you should also define the path to your log file using the
`error_log` ini directive, and turn
`log_errors` on.


**Example #3 Finding dangerous variables with E\_ALL**

`<?php
if ($username) {  // Not initialized or checked before usage
    $good_login = 1;
}
if ($good_login == 1) { // If above test fails, not initialized or checked before usage
    readfile ("/highly/sensitive/data/index.html");
}
?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/security/errors.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsecurity.errors%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=security.errors&repo=en&redirect=https://www.php.net/manual/en/security.errors.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=88727&page=security.errors&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88727&page=security.errors&vote=down "Vote down!")

15


[**_earlz- -NO SPAM-- at earlz dot biz DOT tm_**](https://www.php.net/manual/en/security.errors.php#88727) [¶](https://www.php.net/manual/en/security.errors.php#88727)

**16 years ago**

`Note for those of you using OpenBSD and PHP.  The default php.ini has display_errors=off . This is contrary to the PHP default of display_errors=on . If your having trouble seeing errors on OpenBSD make sure to edit your php.ini to have display_errors=on. (I had this problem on OpenBSD 4.4)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=security.errors&repo=en&redirect=https://www.php.net/manual/en/security.errors.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google