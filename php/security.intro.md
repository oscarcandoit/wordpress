---
url: https://www.php.net/manual/en/security.intro.php
scraped_at: 2025-10-20T02:38:26.190Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Introduction [¶](https://www.php.net/manual/en/security.intro.php\#security.intro)

PHP is a powerful language and the interpreter, whether included
in a web server as a module or executed as a separate
CGI binary, is able to access files, execute
commands and open network connections on the server. These
properties make anything run on a web server insecure by default.
PHP is designed specifically to be a more secure language for
writing CGI programs than Perl or C, and with correct selection of
compile-time and runtime configuration options, and proper coding
practices, it can give you exactly the combination of freedom and
security you need.


As there are many different ways of utilizing PHP, there are many
configuration options controlling its behaviour. A large
selection of options guarantees you can use PHP for a lot of
purposes, but it also means there are combinations of these
options and server configurations that result in an insecure
setup.


The configuration flexibility of PHP is equally rivalled by the
code flexibility. PHP can be used to build complete server
applications, with all the power of a shell user, or it can be used
for simple server-side includes with little risk in a tightly
controlled environment. How you build that environment, and how
secure it is, is largely up to the PHP developer.


This chapter starts with some general security advice, explains
the different configuration option combinations and the situations
they can be safely used, and describes different considerations in
coding for different levels of security.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/security/intro.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsecurity.intro%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=security.intro&repo=en&redirect=https://www.php.net/manual/en/security.intro.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google