---
url: https://www.php.net/manual/en/features.remote-files.php
scraped_at: 2025-10-20T02:37:56.429Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Using remote files [¶](https://www.php.net/manual/en/features.remote-files.php\#features.remote-files)

As long as **allow\_url\_fopen** is enabled in
php.ini, you can use HTTP and FTP
URLs with most of the functions
that take a filename as a parameter. In addition, URLs can be
used with the [include](https://www.php.net/manual/en/function.include.php),
[include\_once](https://www.php.net/manual/en/function.include-once.php), [require](https://www.php.net/manual/en/function.require.php) and
[require\_once](https://www.php.net/manual/en/function.require-once.php) statements
( **allow\_url\_include** must be enabled for these).
See [Supported Protocols and Wrappers](https://www.php.net/manual/en/wrappers.php) for more information about the protocols
supported by PHP.


For example, you can use this to open a file on a remote web server,
parse the output for the data you want, and then use that data in a
database query, or simply to output it in a style matching the rest
of your website.


**Example #1 Getting the title of a remote page**

`<?php
$file = fopen ("http://www.example.com/", "r");
if (!$file) {
    echo "<p>Unable to open remote file.\n";
    exit;
}
while (!feof ($file)) {
    $line = fgets ($file, 1024);
    /* This only works if the title and its tags are on one line */
    if (preg_match ("@\<title\>(.*)\</title\>@i", $line, $out)) {
        $title = $out[1];
        break;
    }
}
fclose($file);
?>`

You can also write to files on an FTP server (provided that you
have connected as a user with the correct access rights). You
can only create new files using this method; if you try to overwrite
a file that already exists, the [fopen()](https://www.php.net/manual/en/function.fopen.php) call will
fail.


To connect as a user other than 'anonymous', you need to specify
the username (and possibly password) within the URL, such as
' `ftp://user:password@ftp.example.com/path/to/file`'.
(You can use the same sort of syntax to access files via
HTTP when they require Basic authentication.)


**Example #2 Storing data on a remote server**

`<?php
$file = fopen ("ftp://ftp.example.com/incoming/outputfile", "w");
if (!$file) {
    echo "<p>Unable to open remote file for writing.\n";
    exit;
}
/* Write the data here. */
fwrite ($file, $_SERVER['HTTP_USER_AGENT'] . "\n");
fclose ($file);
?>`

> **Note**:
>
>
> You might get the idea from the example above that you can use
> this technique to write to a remote log file. Unfortunately
> that would not work because the [fopen()](https://www.php.net/manual/en/function.fopen.php) call will
> fail if the remote file already exists. To do distributed logging
> like that, you should take a look at [syslog()](https://www.php.net/manual/en/function.syslog.php).

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/features/remote-files.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffeatures.remote-files%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=features.remote-files&repo=en&redirect=https://www.php.net/manual/en/features.remote-files.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google