---
url: https://www.php.net/manual/en/tutorial.firstpage.php
scraped_at: 2025-10-20T02:51:22.026Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Your first PHP-enabled page

Create a file named hello.php and put it
in your web server's root directory (DOCUMENT\_ROOT)
with the following content:


**Example #1 Our first PHP script: hello.php**

`<?php
echo "Hello World!";
?>`

Use your browser to access the file with your web server's URL, ending
with the `/hello.php` file reference. When developing locally this
URL will be something like `http://localhost/hello.php`
or `http://127.0.0.1/hello.php` but this depends on the
web server's configuration. If everything is configured correctly, this
file will be parsed by PHP and you will see the "Hello World" output displayed
in your browser.


PHP can be embedded within a normal HTML web page. That means inside your HTML document
you can write the PHP statements, as demonstrated in the following example:


`<!DOCTYPE html>
<html>
    <head>
        <title>PHP Test</title>
    </head>
    <body>
        <?php echo '<p>Hello World</p>'; ?>
    </body>
</html>`

This will result in the following output:


```
<!DOCTYPE html>
<html>
    <head>
        <title>PHP Test</title>
    </head>
    <body>
        <p>Hello World</p>
    </body>
</html>

```

This program is extremely simple and you really did not need to use
PHP to create a page like this. All it does is display:
`Hello World` using the PHP [echo](https://www.php.net/manual/en/function.echo.php)
statement. Note that the file _does not need to be executable_
or special in any way. The server finds out that this file needs to be interpreted
by PHP because you used the ".php" extension, which the server is configured
to pass on to PHP. Think of this as a normal HTML file which happens to have
a set of special tags available to you that do a lot of interesting things.


If you tried this example and it did not output anything, it prompted
for download, or you see the whole file as text, chances are that the
server you are on does not have PHP enabled, or is not configured properly.
Ask your administrator to enable it for you using the
[Installation](https://www.php.net/manual/en/install.php) chapter
of the manual. If you are developing locally, also read the
installation chapter to make sure everything is configured
properly. Make sure that you access the file via http with the server
providing you the output. If you just call up the file from your file
system, then it will not be parsed by PHP. If the problems persist anyway,
do not hesitate to use one of the many
[» PHP support](https://www.php.net/support.php) options.


The point of the example is to show the special PHP tag format.
In this example we used `<?php` to indicate the
start of a PHP tag. Then we put the PHP statement and left PHP mode by
adding the closing tag, `?>`. You may jump in
and out of PHP mode in an HTML file like this anywhere you want. For more
details, read the manual section on the [basic PHP syntax](https://www.php.net/manual/en/language.basic-syntax.php).


> **Note**:
> **A Note on Line Feeds**
>
> Line feeds have little meaning in HTML, however it is still a good idea
> to make your HTML look nice and clean by putting line feeds in. A
> linefeed that follows immediately after a closing
> `?>` will be removed by PHP. This can be extremely
> useful when you are putting in many blocks of PHP or include files
> containing PHP that aren't supposed to output anything. At the same time
> it can be a bit confusing. You can put a space after the closing
> `?>` to force a space and a line feed to be output,
> or you can put an explicit line feed in the last echo/print from within
> your PHP block.

> **Note**:
> **A Note on Text Editors**
>
> There are many text editors and Integrated Development Environments (IDEs)
> that you can use to create, edit and manage PHP files. A partial list of
> these tools is maintained at [» PHP Editors\\
> List](http://en.wikipedia.org/wiki/List_of_PHP_editors). If you wish to recommend an editor, please visit the above
> page and ask the page maintainer to add the editor to the list. Having
> an editor with syntax highlighting can be helpful.

> **Note**:
> **A Note on Word Processors**
>
> Word processors such as StarOffice Writer, Microsoft Word and Abiword are
> not optimal for editing PHP files. If you wish to use one for this
> test script, you must ensure that you save the file as _plain_
> _text_ or PHP will not be able to read and execute the script.

Now that you have successfully created a working PHP script, it is
time to create the most famous PHP script! Make a call to the
[phpinfo()](https://www.php.net/manual/en/function.phpinfo.php) function and you will see a lot of useful
information about your system and setup such as available
[predefined variables](https://www.php.net/manual/en/language.variables.predefined.php),
loaded PHP modules, and [configuration](https://www.php.net/manual/en/configuration.php)
settings. Take some time and review this important information.


**Example #2 Get system information from PHP**

`<?php phpinfo(); ?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/chapters/tutorial.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ftutorial.firstpage%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=tutorial.firstpage&repo=en&redirect=https://www.php.net/manual/en/tutorial.firstpage.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google