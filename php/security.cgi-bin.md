---
url: https://www.php.net/manual/en/security.cgi-bin.php
scraped_at: 2025-10-20T02:34:37.461Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Installed as CGI binary [¶](https://www.php.net/manual/en/security.cgi-bin.php\#security.cgi-bin)

## Table of Contents [¶](https://www.php.net/manual/en/security.cgi-bin.php\#security.cgi-bin)

- [Possible attacks](https://www.php.net/manual/en/security.cgi-bin.attacks.php)
- [Case 1: only public files served](https://www.php.net/manual/en/security.cgi-bin.default.php)
- [Case 2: using cgi.force\_redirect](https://www.php.net/manual/en/security.cgi-bin.force-redirect.php)
- [Case 3: setting doc\_root or user\_dir](https://www.php.net/manual/en/security.cgi-bin.doc-root.php)
- [Case 4: PHP parser outside of web tree](https://www.php.net/manual/en/security.cgi-bin.shell.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/security/cgi-bin.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsecurity.cgi-bin%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=security.cgi-bin&repo=en&redirect=https://www.php.net/manual/en/security.cgi-bin.php)

### User Contributed Notes 12 notes

[up](https://www.php.net/manual/vote-note.php?id=108524&page=security.cgi-bin&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=108524&page=security.cgi-bin&vote=down "Vote down!")

23


[**_Anonymous_**](https://www.php.net/manual/en/security.cgi-bin.php#108524) [¶](https://www.php.net/manual/en/security.cgi-bin.php#108524)

**13 years ago**

`IMPORTANT INFORMATION
There was a serious vulnerability in certain CGI-based PHP setups that has gone unnoticed for at least 8 years.
For PHP this means that a request containing ?-s may dump the PHP source code for the page.
Make sure to update to current versions and/or use an .htaccess patch, both available here:
PHP 5.3.12 and PHP 5.4.2 Released:
[http://www.php.net/archive/2012.php#id2012-05-03-1](http://www.php.net/archive/2012.php#id2012-05-03-1)`

[up](https://www.php.net/manual/vote-note.php?id=5542&page=security.cgi-bin&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=5542&page=security.cgi-bin&vote=down "Vote down!")

20


[**_kstone at trivergent dot net_**](https://www.php.net/manual/en/security.cgi-bin.php#5542) [¶](https://www.php.net/manual/en/security.cgi-bin.php#5542)

**25 years ago**

`Better yet, use binfmt_misc:  (linux only)
echo :php3:E::php3::/usr/bin/php: > /proc/sys/fs/binfmt_misc/register
Eliminates the need for the #! at the top of the file.`

[up](https://www.php.net/manual/vote-note.php?id=25347&page=security.cgi-bin&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=25347&page=security.cgi-bin&vote=down "Vote down!")

16


[**_ruben at puettmann dot net_**](https://www.php.net/manual/en/security.cgi-bin.php#25347) [¶](https://www.php.net/manual/en/security.cgi-bin.php#25347)

**23 years ago**

`To use php-cgi with suexec it will be nice that each virtual host has ist's own php.ini. This goes with :
SetEnv PHPRC /var/www/server/www.test.com/conf
But suexec will kill this enviromet cause It don't know that it is "save" so you must edit the suexec.c for compiling ....`

[up](https://www.php.net/manual/vote-note.php?id=60508&page=security.cgi-bin&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60508&page=security.cgi-bin&vote=down "Vote down!")

8


[**_phpD0TnetATmoritzHYPHONnaumannD0Tcom_**](https://www.php.net/manual/en/security.cgi-bin.php#60508) [¶](https://www.php.net/manual/en/security.cgi-bin.php#60508)

**19 years ago**

`One of the most common reasons why you get 'No input file specified' (AKA 'the second most useful error message in the world') is that you have set 'doc_root' (in php.ini) to a value which is to the 'DocumentRoot' defined in the apache configuration.
This is the same for other webservers. For example, on lighttpd, make sure the 'server.document-root' value is the same as what is defined as 'doc_root' in php.ini.`

[up](https://www.php.net/manual/vote-note.php?id=51182&page=security.cgi-bin&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=51182&page=security.cgi-bin&vote=down "Vote down!")

7


[**_phil dot ross at gmail dot com_**](https://www.php.net/manual/en/security.cgi-bin.php#51182) [¶](https://www.php.net/manual/en/security.cgi-bin.php#51182)

**20 years ago**

`In response to grange at club-internet dot fr:
There are a couple of errors in the mod_rewrite directives given. I found that the following works:
RewriteEngine on
RewriteCond %{ENV:REDIRECT_STATUS} !200
RewriteRule ^cgi-bin/php.cgi - [F]
I removed the = from the RewriteCond and took out the leading / from the RewriteRule.`

[up](https://www.php.net/manual/vote-note.php?id=25577&page=security.cgi-bin&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=25577&page=security.cgi-bin&vote=down "Vote down!")

6


[**_matled at gmx dot net_**](https://www.php.net/manual/en/security.cgi-bin.php#25577) [¶](https://www.php.net/manual/en/security.cgi-bin.php#25577)

**23 years ago**

`If you are using php per cgi and have additionally mod_gzip enabled you have to disable mod_gzip for the php cgi binary to use --enable-cgi-redirect. mod_gzip sets the REDIRECT_STATUS always to 200 which makes it impossible for the php binary to know when it was called directly or when it was called by a redirect.`

[up](https://www.php.net/manual/vote-note.php?id=12432&page=security.cgi-bin&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=12432&page=security.cgi-bin&vote=down "Vote down!")

6


[**_yohgaki at hotmail dot com_**](https://www.php.net/manual/en/security.cgi-bin.php#12432) [¶](https://www.php.net/manual/en/security.cgi-bin.php#12432)

**24 years ago**

`If you care about security, you are better of setting
register_globals = off
enable_track_vars = on (Always on from PHP4.0.3)
Default setting for variable order is
EGPCS
(ENV VARS/GET VARS/POST VARS/COOKIE VARS/SESSION VARS)
Imagine if you are rely on ENV VAR but it was orver written with GET/POST/COOKIE vars?`

[up](https://www.php.net/manual/vote-note.php?id=30546&page=security.cgi-bin&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=30546&page=security.cgi-bin&vote=down "Vote down!")

5


[**_pookey at pookey dot co dot uk_**](https://www.php.net/manual/en/security.cgi-bin.php#30546) [¶](https://www.php.net/manual/en/security.cgi-bin.php#30546)

**22 years ago**

`I have setup a guide to installing PHP with SuEXEC in such a way that shebangs (!#/usr/bin/php4) are not needed.  Hope this is of some help to you.
[http://www.pookey.co.uk/php-security.xml](http://www.pookey.co.uk/php-security.xml)`

[up](https://www.php.net/manual/vote-note.php?id=12380&page=security.cgi-bin&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=12380&page=security.cgi-bin&vote=down "Vote down!")

5


[**_michel dot jansens at ulb dot ac dot be_**](https://www.php.net/manual/en/security.cgi-bin.php#12380) [¶](https://www.php.net/manual/en/security.cgi-bin.php#12380)

**24 years ago**

`If you want to use suexec and reference your php interpreter via #!/usr/local/bin/php,  be shure to compile php WITHOUT  --enable-force-cgi-redirect.
This might seems obvious, but I spent 2 days on this :-(`

[up](https://www.php.net/manual/vote-note.php?id=77041&page=security.cgi-bin&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=77041&page=security.cgi-bin&vote=down "Vote down!")

3


[**_Craig Buchek_**](https://www.php.net/manual/en/security.cgi-bin.php#77041) [¶](https://www.php.net/manual/en/security.cgi-bin.php#77041)

**18 years ago**

`NOTE: Running PHP as a CGI program will change the value of $_SERVER['SCRIPT_NAME']. When running via the (normal) mod_PHP mechanism, it will be set to the name of (actually, path to) the PHP script that's running. When running via CGI, it will instead point to the path of the CGI binary.`

[up](https://www.php.net/manual/vote-note.php?id=35492&page=security.cgi-bin&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=35492&page=security.cgi-bin&vote=down "Vote down!")

3


[**_geeky at geeky dot de_**](https://www.php.net/manual/en/security.cgi-bin.php#35492) [¶](https://www.php.net/manual/en/security.cgi-bin.php#35492)

**22 years ago**

`a replacement for suexec is suphp ( [http://www.suphp.org](http://www.suphp.org/)).
"suPHP is a tool for executing PHP scripts with the permissions of their owners. It consists of an Apache module (mod_suphp) and a setuid root binary (suphp) that is called by the Apache module to change the uid of the process executing the PHP interpreter." (from the website)`

[up](https://www.php.net/manual/vote-note.php?id=10714&page=security.cgi-bin&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=10714&page=security.cgi-bin&vote=down "Vote down!")

 -1


[**_steeven at kali dot com dot cn_**](https://www.php.net/manual/en/security.cgi-bin.php#10714) [¶](https://www.php.net/manual/en/security.cgi-bin.php#10714)

**24 years ago**

`suEXEC require CGI mode, and slow down the scripts. I did them like this:
1. Install php as DSO mode. (for max speed and low secure)
2. Make a seperate CGI install with --enable-force-cgi-redirect, place php to cgi-bin
3 For more secure with suEXEC, choose one of the following method:
3-1: Place a .htaccess file containing this to override main config:
AddType application/x-httpd-wphp php
Action application/x-httpd-wphp /cgi-bin/php
All php files in subdirectory will be protected.
3-2: add following in httpd.conf:
AddType application/x-httpd-wphp sphp
Action application/x-httpd-wphp /cgi-bin/php
then each sensitive php file should be renamed to .sphp
Add "php_value doc_root /home/user/html_docs" to each virtual host directive in httpd.conf`

[＋add a note](https://www.php.net/manual/add-note.php?sect=security.cgi-bin&repo=en&redirect=https://www.php.net/manual/en/security.cgi-bin.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google