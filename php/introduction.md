---
url: https://www.php.net/manual/en/introduction.php
scraped_at: 2025-10-20T02:40:57.375Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# What is PHP and what can it do?

# What is PHP?

PHP (recursive acronym for _PHP: Hypertext_
_Preprocessor_) is a widely-used open source general-purpose
scripting language that is especially suited for web
development and can be embedded into HTML.


Nice, but what does that mean? An example:


**Example #1 An introductory example**

`<!DOCTYPE html>
<html>
    <head>
        <title>Example</title>
    </head>
    <body>
        <?php
            echo "Hi, I'm a PHP script!";
        ?>
    </body>
</html>`

Instead of lots of commands to output HTML (as seen in C or Perl),
PHP pages contain HTML with embedded code that does
something (in this case, output Hi, I'm a PHP script!).
The PHP code is enclosed in special [start and end processing\\
instructions `<?php` and `?>`](https://www.php.net/manual/en/language.basic-syntax.phpmode.php)
that allow jumping in and out of PHP mode.

What distinguishes PHP from something like client-side JavaScript
is that the code is executed on the server, generating HTML which
is then sent to the client. The client would receive
the results of running that script, but would not know
what the underlying code was. A web server can even be configured
to process all HTML files with PHP, and then there's no
way that users can tell that PHP is being used.


The best part about using PHP is that it is extremely simple
for a newcomer, but offers many advanced features for
a professional programmer. Don't be afraid to read the long
list of PHP's features. With PHP, almost anyone can get up and running and be
writing simple scripts in no time at all.


Although PHP's development is focused on server-side scripting,
much more can be done with it. Read on, and see more in the
[What can PHP do?](https://www.php.net/manual/en/introduction.php#intro-whatcando) section,
or go right to the [introductory\\
tutorial](https://www.php.net/manual/en/tutorial.php) to jump straight to learning about web programming.


# What can PHP do?

Anything. PHP is mainly focused on server-side scripting,
so it can do anything any other CGI program can do, such
as collect form data, generate dynamic page content, or
send and receive cookies. But PHP can do much more.


There are two main areas where PHP scripts are used.


- Server-side scripting. This is the most widely used
and main target field for PHP. Three things are needed
to make this work: the PHP parser (CGI or server
module), a web server, and a web browser. All these can
run on a local machine in order to just experiment
with PHP programming. See the
[installation instructions](https://www.php.net/manual/en/install.php)
section for more information.

- Command line scripting. A PHP script can be run
without any server or browser, only the
PHP parser is needed to use it this way.
This type of usage is ideal for scripts regularly
executed using **cron** (on Unix or macOS) or Task Scheduler (on
Windows). These scripts can also be used for simple text
processing tasks. See the section about
[Command line usage of PHP](https://www.php.net/manual/en/features.commandline.php)
for more information.


PHP can be [used](https://www.php.net/manual/en/install.php) on all major operating systems, including
Linux, many Unix variants (including HP-UX, Solaris and OpenBSD),
Microsoft Windows, macOS, RISC OS, and probably others.
PHP also has support for most of the web servers today. This
includes Apache, IIS, and many others. And this includes any
web server that can utilize the FastCGI PHP binary, like lighttpd
and nginx. PHP works as either a module, or as a CGI processor.


So with PHP, developers have the freedom of choosing an operating
system and a web server. Furthermore, they also have the choice
of using procedural programming or object-oriented
programming (OOP), or a mixture of them both.


PHP is not limited to outputting HTML. PHP's abilities include
outputting rich file types, such as images or PDF files, encrypting data,
and sending emails. It can also output easily any text, such as JSON
or XML. PHP can autogenerate these files, and save them in the
file system, instead of printing it out, forming a server-side cache for
dynamic content.


One of the strongest and most significant features in PHP is its
support for a [wide range of databases](https://www.php.net/manual/en/refs.database.php).
Writing a database-enabled web page is incredibly simple using one of
the database specific extensions (e.g., for [mysql](https://www.php.net/manual/en/book.mysqli.php)),
or using an abstraction layer like [PDO](https://www.php.net/manual/en/book.pdo.php), or connect
to any database supporting the Open Database Connection standard via the
[ODBC](https://www.php.net/manual/en/book.uodbc.php) extension. Other databases may utilize
[cURL](https://www.php.net/manual/en/book.curl.php) or [sockets](https://www.php.net/manual/en/book.sockets.php),
like CouchDB.


PHP also has support for talking to other services using protocols
such as LDAP, IMAP, SNMP, NNTP, POP3, HTTP, COM (on Windows) and
countless others. It can also open raw network sockets and
interact using any other protocol. PHP has support for the WDDX
complex data exchange between virtually all Web programming
languages. Talking about interconnection, PHP has support for
instantiation of Java objects and using them transparently
as PHP objects.


PHP has useful [text processing](https://www.php.net/manual/en/refs.basic.text.php) features,
which includes the Perl compatible regular expressions ( [PCRE](https://www.php.net/manual/en/book.pcre.php)),
and many extensions and tools to [parse and access XML documents](https://www.php.net/manual/en/refs.xml.php).
PHP standardizes all of the XML extensions on the solid base of [libxml2](https://www.php.net/manual/en/book.libxml.php),
and extends the feature set adding [SimpleXML](https://www.php.net/manual/en/book.simplexml.php),
[XMLReader](https://www.php.net/manual/en/book.xmlreader.php) and [XMLWriter](https://www.php.net/manual/en/book.xmlwriter.php) support.


And many other interesting extensions exist, which are categorized both
[alphabetically](https://www.php.net/manual/en/extensions.php) and by [category](https://www.php.net/manual/en/funcref.php).
And there are additional [PECL extensions](https://www.php.net/manual/en/install.pecl.intro.php) that may or may not be documented
within the PHP manual itself, like [» XDebug](http://xdebug.org/).


This page is not enough to list all
the features and benefits PHP can offer. Read on in
the sections about [installing\\
PHP](https://www.php.net/manual/en/install.php), and see the [function\\
reference](https://www.php.net/manual/en/funcref.php) part for explanation of the extensions
mentioned here.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/chapters/intro.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fintroduction%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=introduction&repo=en&redirect=https://www.php.net/manual/en/introduction.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google