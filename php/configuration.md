---
url: https://www.php.net/manual/en/configuration.php
scraped_at: 2025-10-20T02:38:28.069Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Runtime Configuration [¶](https://www.php.net/manual/en/configuration.php\#configuration)

## Table of Contents [¶](https://www.php.net/manual/en/configuration.php\#configuration)

- [The configuration file](https://www.php.net/manual/en/configuration.file.php)
- [.user.ini files](https://www.php.net/manual/en/configuration.file.per-user.php)
- [Where a configuration setting may be set](https://www.php.net/manual/en/configuration.changes.modes.php)
- [How to change configuration settings](https://www.php.net/manual/en/configuration.changes.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/install/ini.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fconfiguration%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=configuration&repo=en&redirect=https://www.php.net/manual/en/configuration.php)

### User Contributed Notes 8 notes

[up](https://www.php.net/manual/vote-note.php?id=75989&page=configuration&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75989&page=configuration&vote=down "Vote down!")

20


[**_jaw at jawspeak dot com - Jonathan Andrew Wolte_**](https://www.php.net/manual/en/configuration.php#75989) [¶](https://www.php.net/manual/en/configuration.php#75989)

**18 years ago**

`Be sure to use double quotes in the php.ini file. For instance:
(lines broken for readability)
this will work:
# xdebug debugging
zend_extension="/usr/local/php5/lib/php/extensions
/no-debug-non-zts-20060613/xdebug.so"
this won't:
# xdebug debugging
zend_extension='/usr/local/php5/lib/php/extensions
/no-debug-non-zts-20060613/xdebug.so'
You'll get this error:
Failed loading '/usr/local/php5/lib/php/extensions/
no-debug-non-zts-20060613/xdebug.so':  (null)
So... double quotes are the way! I know this is obvious, but it's a good thing to remember for the php.ini file.`

[up](https://www.php.net/manual/vote-note.php?id=75798&page=configuration&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75798&page=configuration&vote=down "Vote down!")

11


[**_alvaro at demogracia dot com_**](https://www.php.net/manual/en/configuration.php#75798) [¶](https://www.php.net/manual/en/configuration.php#75798)

**18 years ago**

`About Apache 2.0 module:
For whatever reason, the Windows installer for PHP/5.2.3 tries to set the PHPIniDir directive using "\\" as directory separator:
PHPIniDir "C:\\Archivos de programa\\PHP\\"
It didn't work for me until I edited httpd.conf and replaced it with "/":
PHPIniDir "C:/Archivos de programa/PHP/"`

[up](https://www.php.net/manual/vote-note.php?id=74256&page=configuration&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=74256&page=configuration&vote=down "Vote down!")

9


[**_henrick at streamsec dot se_**](https://www.php.net/manual/en/configuration.php#74256) [¶](https://www.php.net/manual/en/configuration.php#74256)

**18 years ago**

`In order to get PHP 5.2 stable running on Windows Server 2003 x64 (IIS 6.0), I discovered three things (in addition to the other comments above):
* Some PHP web applications make use of the SCRIPT_NAME server variable which is not available under CGI. You have to use php5isapi.dll, which is a 32 bit dll, so you have to run IIS in 32 bit mode. Confer [http://support.microsoft.com/kb/894435.](http://support.microsoft.com/kb/894435.) This applies to all ISAPI extensions and not just ASP.NET.
* It appears you must leave the doc_root entry in php.ini blank. At least, that is what finally made my installation work. (Note that others have suggested to set it to e.g. C:\inetpub\wwwroot or equivalent. That won't work if your server hosts more than one domain, each placed in a separate directory.)
* If you are e.g. using MySQL you will have to edit php.ini. In order for it to be found, you must set the PHPRC system environment variable or the registry entry. Note that if you edit the registry using regedit.exe, the PHP key should be placed under the [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node] key. This happens automatically if you set it using a 32 bit legacy application.`

[up](https://www.php.net/manual/vote-note.php?id=101176&page=configuration&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101176&page=configuration&vote=down "Vote down!")

8


[**_salivatears at gmail dot com_**](https://www.php.net/manual/en/configuration.php#101176) [¶](https://www.php.net/manual/en/configuration.php#101176)

**14 years ago**

`For windows with limited file permission (Windows XP)
1. Install Apache in your folder profile "C:\Documents and Settings\your_profile"
2. Add the following directives to you httpd.conf
PHPINIDir "C:\Documents and Settings\your_profile\php"
LoadModule php5_module "C:\Documents and Settings\your_profile\php\php5apache2_2.dll"
AddType application/x-httpd-php .php
3. Edit the following directive to you php.ini
extension_dir = "C:\Documents and Settings\your_profile\php\ext"
4. Move the file libmysql.dll from C:\Documents and Settings\your_profile\php\ to C:\Documents and Settings\your_profile\php\ext\
5. Restart httpd using command line`

[up](https://www.php.net/manual/vote-note.php?id=53246&page=configuration&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=53246&page=configuration&vote=down "Vote down!")

8


[**_randy AT rcs-comp DOT com_**](https://www.php.net/manual/en/configuration.php#53246) [¶](https://www.php.net/manual/en/configuration.php#53246)

**20 years ago**

`(copied from another page)
Please note that the SetEnv PHPRC "directory/to/phpini/" only works when using PHP as CGI, but _not_ when you use the PHP Apache Module!`

[up](https://www.php.net/manual/vote-note.php?id=72212&page=configuration&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72212&page=configuration&vote=down "Vote down!")

7


[**_cduke420 at gmail dot com_**](https://www.php.net/manual/en/configuration.php#72212) [¶](https://www.php.net/manual/en/configuration.php#72212)

**18 years ago**

`[ When php run as Apache Module ]
DOCUMENT_ROOT .htaccess
+======================================+
SetEnv PHPRC /home/user/dir-containing-phpinifile
+======================================+
[ When php run as CGI ]
Place your php.ini file in the dir of your cgi'd php binary, in this case /cgi-bin/
DOCUMENT_ROOT .htaccess
+======================================+
AddHandler php-cgi .php .htm
Action php-cgi /cgi-bin/php5.cgi
+======================================+
[ PHP run as cgi with wrapper (for FastCGI) ]
Your wrapper script should look something like:
+======================================+
#!/bin/sh
export PHP_FCGI_CHILDREN=3
exec /user/htdocs/cgi-bin/php.cgi -c /home/user/php.ini
+======================================+
original article:
[http://www.askapache.com/2007/php/custom-phpini-tips-and-tricks.html](http://www.askapache.com/2007/php/custom-phpini-tips-and-tricks.html)`

[up](https://www.php.net/manual/vote-note.php?id=113242&page=configuration&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113242&page=configuration&vote=down "Vote down!")

6


[**_goran_**](https://www.php.net/manual/en/configuration.php#113242) [¶](https://www.php.net/manual/en/configuration.php#113242)

**12 years ago**

`To run separate apache and php processes on centos (at least) without
having to compile and install separate versions for every instance
this should work:
Install apache and php with yum.
This will give you (for the first instance):
/etc/httpd/*, /etc/sysconfig/httpd, /etc/init.d/httpd, /etc/php.ini
and /etc/php.d/*.
Copy all this stuff to:
/etc/httpd2/*, /etc/sysconfig/httpd2, /etc/init.d/httpd2,  /etc/php2.ini
and /etc/php2.d/*.
Then:
Edit the apache config files in /etc/httpd2/* to reflect the new
ports you want to have this apache listen on (don't forget ssl.conf
under conf.d) and any other differing settings, like log file
destinations and virtualhosts.
Edit the php2.ini for any specific settings you want the other php
instance to have.
To have a completely separate php in this new apache instance with its own
modules included, edit /etc/sysconfig/httpd2 and add the following:
PHPRC=/etc/php2.ini
export PHPRC
PHP_INI_SCAN_DIR=/etc/php2.d
export PHP_INI_SCAN_DIR
This will set the environment variables for the second apache/php
instance before it is started.
Then edit /etc/init.d/httpd2 and change all references to httpd
(like lockfile, pidfile and sysconfig) to httpd2. Don't touch the
executable name, though :)
And change this:
LANG=$HTTPD_LANG daemon --pidfile=${pidfile} $httpd $OPTIONS
to this:
LANG=$HTTPD_LANG daemon --pidfile=${pidfile} $httpd -f /etc/httpd2/conf/httpd.conf $OPTIONS
.. so this apache can find its own configuration file.
Then, if necessary 'chkconfig --add /etc/init.d/httpd2' to have it
in startup and you should have two apache instances with two separate
php modules with their own dedicated settings.`

[up](https://www.php.net/manual/vote-note.php?id=63096&page=configuration&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=63096&page=configuration&vote=down "Vote down!")

7


[**_c dot affolter at stepping-stone dot ch_**](https://www.php.net/manual/en/configuration.php#63096) [¶](https://www.php.net/manual/en/configuration.php#63096)

**19 years ago**

`For those people who want to use the PHPRC environment variable:
You have to specify the path to the directory containing your php.ini, not the direct path to the php.ini.
Example (php.ini resides in /your/path/php.ini):
right:
export PHPRC=/your/path
wrong:
export PHPRC=/your/path/php.ini`

[＋add a note](https://www.php.net/manual/add-note.php?sect=configuration&repo=en&redirect=https://www.php.net/manual/en/configuration.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google