---
url: https://www.php.net/manual/en/security.hiding.php
scraped_at: 2025-10-20T02:32:43.618Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Hiding PHP [¶](https://www.php.net/manual/en/security.hiding.php\#security.hiding)

In general, security by obscurity is one of the weakest forms of security.
But in some cases, every little bit of extra security is desirable.


A few simple techniques can help to hide PHP, possibly slowing
down an attacker who is attempting to discover weaknesses in your
system. By setting expose\_php to `off` in your
php.ini file, you reduce the amount of information available to them.


Another tactic is to configure web servers such as apache to
parse different filetypes through PHP, either with an .htaccess
directive, or in the apache configuration file itself. You can
then use misleading file extensions:


**Example #1 Hiding PHP as another language**

```
# Make PHP code look like other code types
AddType application/x-httpd-php .asp .py .pl
```

Or obscure it completely:


**Example #2 Using unknown types for PHP extensions**

```
# Make PHP code look like unknown types
AddType application/x-httpd-php .bop .foo .133t
```

Or hide it as HTML code, which has a slight performance hit because
all HTML will be parsed through the PHP engine:


**Example #3 Using HTML types for PHP extensions**

```
# Make all PHP code look like HTML
AddType application/x-httpd-php .htm .html
```

For this to work effectively, you must rename your PHP files with
the above extensions. While it is a form of security through
obscurity, it's a minor preventative measure with few drawbacks.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/security/hiding.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsecurity.hiding%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=security.hiding&repo=en&redirect=https://www.php.net/manual/en/security.hiding.php)

### User Contributed Notes 22 notes

[up](https://www.php.net/manual/vote-note.php?id=72630&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72630&page=security.hiding&vote=down "Vote down!")

44


[**_rustamabd at google mail_**](https://www.php.net/manual/en/security.hiding.php#72630) [¶](https://www.php.net/manual/en/security.hiding.php#72630)

**18 years ago**

`So far I haven't seen a working rewriter of /foo/bar into /foo/bar.php, so I created my own. It does work in top-level directory AND subdirectories and it doesn't need hardcoding the RewriteBase.
.htaccess:
RewriteEngine on
# Rewrite /foo/bar to /foo/bar.php
RewriteRule ^([^.?]+)$ %{REQUEST_URI}.php [L]
# Return 404 if original request is /foo/bar.php
RewriteCond %{THE_REQUEST} "^[^ ]* .*?\.php[? ].*$"
RewriteRule .* - [L,R=404]
# NOTE! FOR APACHE ON WINDOWS: Add [NC] to RewriteCond like this:
# RewriteCond %{THE_REQUEST} "^[^ ]* .*?\.php[? ].*$" [NC]`

[up](https://www.php.net/manual/vote-note.php?id=113970&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113970&page=security.hiding&vote=down "Vote down!")

26


[**_anon at example dot com_**](https://www.php.net/manual/en/security.hiding.php#113970) [¶](https://www.php.net/manual/en/security.hiding.php#113970)

**11 years ago**

`The session name defaults to PHPSESSID.  This is used as the name of the session cookie that is sent to the user's web browser / client. (Example: PHPSESSID=kqjqper294faui343o98ts8k77).
To hide this, call session_name() with the $name parameter set to a generic name, before calling session_start().  Example:
session_name("id");
session_start();
Cheers.`

[up](https://www.php.net/manual/vote-note.php?id=128154&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128154&page=security.hiding&vote=down "Vote down!")

6


[**_Sajith Karunatilake @_**](https://www.php.net/manual/en/security.hiding.php#128154) [¶](https://www.php.net/manual/en/security.hiding.php#128154)

**2 years ago**

`Just hiding it doesn't look like good "security" if the code itself is flawed. At the end of the day the code has to run regardless of its file extension. There could be some advantages to this. But it does not prevent someone (who is not a script-kiddie or some kind of automated bot) from exploiting the flaws in the code.
Just a thought.
Just leaving this comment to prevent a beginner from using this as a legitimate security measure (assuming they read documentation). Cool feature though.`

[up](https://www.php.net/manual/vote-note.php?id=40772&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=40772&page=security.hiding&vote=down "Vote down!")

15


[**_mmj_**](https://www.php.net/manual/en/security.hiding.php#40772) [¶](https://www.php.net/manual/en/security.hiding.php#40772)

**21 years ago**

`You can see if somebody's using PHP just by adding the following to the end of the URL:
?=PHPB8B5F2A0-3C92-11d3-A3A9-4C7B08C10000
If the page is using PHP, this will show the PHP credits.
Setting expose_php to Off in php.ini prevents this.`

[up](https://www.php.net/manual/vote-note.php?id=28980&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=28980&page=security.hiding&vote=down "Vote down!")

10


[**_Anonymous_**](https://www.php.net/manual/en/security.hiding.php#28980) [¶](https://www.php.net/manual/en/security.hiding.php#28980)

**22 years ago**

`PS. If you want to use pretty URLs (i.e. hide your .php extensions) AND you have safe-mode=on, the previous example (ForceType) won't work for you.  The problem is that safe-mode forces Apache to honor trailing characters in a requested URL.  This means that:
[http://www.example.com/home](http://www.example.com/home)
would still be processed by the home script in our doc root, but for:
[http://www.example.com/home/contact\_us.html](http://www.example.com/home/contact_us.html)
apache would actually look for the /home/contact_us.html file in our doc root.
The best solution I've found is to set up a virtual host (which I do for everything, even the default doc root) and override the trailing characters handling within the virtual host.  So, for a virtual host listening on port 8080, the apache directives would look like this:
<VirtualHost *:8080>
    DocumentRoot /web/doc_root
    Alias /home "/web/doc_root/home.php"
    AcceptPathInfo On
</VirtualHost>
Some people might question why we are overriding the trailing characters handling (with the AcceptPathInfo directive) instead of just turning safe-mode=off.  The reason is that safe mode sets global limitations on the entire server, which can then be turned on or left off for each specific virtual host.  This is the equivilent of blocking all connections on a firewall, and then opening up only the ones you want, which is a lot safer than leaving everything open globally, and assuming your programmers will never overlook a possible security hole.`

[up](https://www.php.net/manual/vote-note.php?id=86623&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86623&page=security.hiding&vote=down "Vote down!")

10


[**_sandaimespaceman at gmail dot com_**](https://www.php.net/manual/en/security.hiding.php#86623) [¶](https://www.php.net/manual/en/security.hiding.php#86623)

**16 years ago**

`Set INI directive "expose_php" to "off" will also help.
You can spoof your PHP to ASP.NET by using:
<?php
error_reporting(0);
header("X-Powered-By: ASP.NET");
?>`

[up](https://www.php.net/manual/vote-note.php?id=64278&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=64278&page=security.hiding&vote=down "Vote down!")

13


[**_marpetr at NOSPAM dot gmail dot com_**](https://www.php.net/manual/en/security.hiding.php#64278) [¶](https://www.php.net/manual/en/security.hiding.php#64278)

**19 years ago**

`I think the best way to hide PHP on Apache and Apache itself is this:
httpd.conf
-------------
# ...
# Minimize 'Server' header information
ServerTokens Prod
# Disable server signature on server generated pages
ServerSignature Off
# ...
# Set default file type to PHP
DefaultType application/x-httpd-php
# ...
php.ini
------------
; ...
expose_php = Off
; ...
Now the URLs will look like this:
[http://my.server.com/forums/post?forumid=15](http://my.server.com/forums/post?forumid=15)
Now hacker knows only that you are using Apache.`

[up](https://www.php.net/manual/vote-note.php?id=99001&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99001&page=security.hiding&vote=down "Vote down!")

10


[**_CD001_**](https://www.php.net/manual/en/security.hiding.php#99001) [¶](https://www.php.net/manual/en/security.hiding.php#99001)

**15 years ago**

`It's a good idea to "hide" PHP anyway so you can write a RESTful web application.
Using Apache Mod Rewrite:
RewriteEngine On
RewriteRule ^control/([^/]+)/(.*)$ sitecontroller.php?control=$1&query=$2
You then use a function like the following as a way to retrieve data (in a zero indexed fashion) from the $_GET superglobal.
<?php
function myGET() {
$aGet = array();
if(isset($_GET['query'])) {
    $aGet = explode('/', $_GET['query']);
}
return $aGet;
}
?>
This is only a really basic example of course - you can do a lot with Mod Rewrite and a custom 'GET' function.`

[up](https://www.php.net/manual/vote-note.php?id=86286&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=86286&page=security.hiding&vote=down "Vote down!")

8


[**_Pyornide_**](https://www.php.net/manual/en/security.hiding.php#86286) [¶](https://www.php.net/manual/en/security.hiding.php#86286)

**17 years ago**

`The idea of hiding the X-Powered-By in PHP is a flawed attempt at establishing security. As the manual indicates, obscurity is not security. If I were exploiting a site, I wouldn't check what scripting language the site runs on, because all that would matter to me is exploiting it. Hiding the fact that you use [x] language isn't going to prevent me from bypassing poor security.`

[up](https://www.php.net/manual/vote-note.php?id=53144&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=53144&page=security.hiding&vote=down "Vote down!")

7


[**_benjamin at sonntag dot fr_**](https://www.php.net/manual/en/security.hiding.php#53144) [¶](https://www.php.net/manual/en/security.hiding.php#53144)

**20 years ago**

`In response to the previous messages, for apache, there is a easier way to set files without "." to be executed by PHP, just put this in a ".htaccess" file :
DefaultType  application/x-httpd-php`

[up](https://www.php.net/manual/vote-note.php?id=18520&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=18520&page=security.hiding&vote=down "Vote down!")

8


[**_yasuo\_ohgaki at yahoo dot com_**](https://www.php.net/manual/en/security.hiding.php#18520) [¶](https://www.php.net/manual/en/security.hiding.php#18520)

**23 years ago**

`To hide PHP, you need following php.ini settings
expose_php=Off
display_errors=Off
and in httpd.conf
ServerSignature Off
(min works, but I prefer off)`

[up](https://www.php.net/manual/vote-note.php?id=36936&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=36936&page=security.hiding&vote=down "Vote down!")

8


[**_ldemailly at qualysNOSPAM dot com_**](https://www.php.net/manual/en/security.hiding.php#36936) [¶](https://www.php.net/manual/en/security.hiding.php#36936)

**21 years ago**

`adding MultiViews to your apache Options config
lets you hide/omit .php in the url without any rewriting, etc...`

[up](https://www.php.net/manual/vote-note.php?id=117586&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117586&page=security.hiding&vote=down "Vote down!")

7


[**_info at frinteractives dot com_**](https://www.php.net/manual/en/security.hiding.php#117586) [¶](https://www.php.net/manual/en/security.hiding.php#117586)

**10 years ago**

`try this
RewriteEngine On
# Unless directory, remove trailing slash
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^([^/]+)/$ [http://example.com/folder/$1](http://example.com/folder/$1) [R=301,L]
# Redirect external .php requests to extensionless url
RewriteCond %{THE_REQUEST} ^(.+)\.php([#?][^\ ]*)?\ HTTP/
RewriteRule ^(.+)\.php$ [http://example.com/folder/$1](http://example.com/folder/$1) [R=301,L]
# Resolve .php file for extensionless php urls
RewriteRule ^([^/.]+)$ $1.php [L]`

[up](https://www.php.net/manual/vote-note.php?id=54313&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=54313&page=security.hiding&vote=down "Vote down!")

5


[**_jtw90210_**](https://www.php.net/manual/en/security.hiding.php#54313) [¶](https://www.php.net/manual/en/security.hiding.php#54313)

**20 years ago**

`In order to get the PATH_INFO to work in order to pass parameters using a hidden program/trailing slash/"pretty url" in more recent versions of PHP you MUST add "AcceptPathInfo On" to your httpd.conf.
AddType application/x-httpd-php .php .html
AcceptPathInfo On
Try it out with your phpinfo page and you'll be able to search for PATH_INFO.
[http://example.com/myphpinfo.php/showmetheway](http://example.com/myphpinfo.php/showmetheway)
If you want to drop the .php use one or both of these:
DefaultType application/x-httpd-php
ForceType application/x-httpd-php`

[up](https://www.php.net/manual/vote-note.php?id=42332&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=42332&page=security.hiding&vote=down "Vote down!")

6


[**_Anonymous_**](https://www.php.net/manual/en/security.hiding.php#42332) [¶](https://www.php.net/manual/en/security.hiding.php#42332)

**21 years ago**

`Keep in mind, if your really freaked out over hiding PHP, GD will expose you.
Go ahead - make an image with GD and open with a text editor.. Somewhere in there you'll see a comment with gd & php all over it.`

[up](https://www.php.net/manual/vote-note.php?id=17872&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=17872&page=security.hiding&vote=down "Vote down!")

5


[**_istvan dot takacsNOSPAM at hungax dot com_**](https://www.php.net/manual/en/security.hiding.php#17872) [¶](https://www.php.net/manual/en/security.hiding.php#17872)

**23 years ago**

`And use the
ServerTokens min
directive in your httpd.conf to hide installed PHP modules in apache.`

[up](https://www.php.net/manual/vote-note.php?id=34285&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=34285&page=security.hiding&vote=down "Vote down!")

5


[**_l0rdphi1 at liquefyr dot com_**](https://www.php.net/manual/en/security.hiding.php#34285) [¶](https://www.php.net/manual/en/security.hiding.php#34285)

**22 years ago**

`More fun includes files without file extensions.
Simply add that ForceType application/x-httpd-php bit to an Apache .htaccess and you're set.
Oh yea, it gets even better when you play with stuff like the following:
<?php
substr($_SERVER['PATH_INFO'],1);
?>
e.g. www.example.com/somepage/55
And:
<?php
foreach ( explode('/',$_SERVER['PATH_INFO']) as $pair ) {
    list($key,$value) = split('=',$pair,2);
    $param[$key] = stripslashes($value);
}
?>
e.g. www.example.com/somepage/param1=value1/param2=value2/etc=etc
Enjoy =)`

[up](https://www.php.net/manual/vote-note.php?id=23561&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=23561&page=security.hiding&vote=down "Vote down!")

4


[**_m1tk4 at hotmail dot com_**](https://www.php.net/manual/en/security.hiding.php#23561) [¶](https://www.php.net/manual/en/security.hiding.php#23561)

**23 years ago**

`I usually do:
<code>
RewriteEngine on<br>
RewriteOptions inherit<br>
RewriteRule (.*)\.htm[l]?(.*) $1.php$2 [nocase]<br>
</code>
in .htaccess. You'll need mod_rewrite installed for this .`

[up](https://www.php.net/manual/vote-note.php?id=30751&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=30751&page=security.hiding&vote=down "Vote down!")

0


[**_Bryce Nesbitt at Obviously.COM_**](https://www.php.net/manual/en/security.hiding.php#30751) [¶](https://www.php.net/manual/en/security.hiding.php#30751)

**22 years ago**

`Using the .php extension for all your scripts is not necessary, and in fact can be harmful (by exposing too much information about your server, and by limiting what you can do in the future without breaking links). There are several ways to hide your .php script extension:
(1) Don't hard code file types at all.  Don't specify any dots, and most web servers will automatically find your .php, .html, .pdf, .gif or other matching file. This is called canonical URL format:
     www.xxxxxx.com/page
    www.xxxxxx.com/directory/
This gives you great flexibility to change your mind in the future, and prevents Windows browsers from making improper assumptions about the file type.
(2) In an Apache .htaccess file use:
    RewriteEngine on
    RewriteRule page.html page.php
(3) Force the webserver to interpret ALL .html files as .php:
    AddType application/x-httpd-php .php3 .php .html`

[up](https://www.php.net/manual/vote-note.php?id=68777&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=68777&page=security.hiding&vote=down "Vote down!")

 -1


[**_simon at carbontwelevedesign dot co dot uk_**](https://www.php.net/manual/en/security.hiding.php#68777) [¶](https://www.php.net/manual/en/security.hiding.php#68777)

**19 years ago**

`I use the following in the .htaccess document
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteBase /
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.php [L]
</IfModule>
then the following simple code
<?php
$permalinks = explode("/",$_SERVER['REQUEST_URI']);
$varone = $permalinks[1];
$vartwo = $permalinks[2];
...
?>`

[up](https://www.php.net/manual/vote-note.php?id=43240&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=43240&page=security.hiding&vote=down "Vote down!")

 -4


[**_php at vfmedia dot de_**](https://www.php.net/manual/en/security.hiding.php#43240) [¶](https://www.php.net/manual/en/security.hiding.php#43240)

**21 years ago**

`I?ve found an easy way to hide php code and the uri is searchable by google and others...(only for unix or linux)
At first I have some rules in my hide.conf (i made an extra .conf for it (apache 2.0))
For example when I want to mask the index.php
<Files index>
ForceType application/x-httpd-php
</Files>
My problem is, that my code should be readable...
so I made an extra folder for example srv/www/htdocs/static_output
My phpcode is in the includefolder....(for ex. mnt/source/index.php)
Then I made a link in the shell  > ln mnt/source/index.php srv/www/htdocs/static_output/index
So the code is readable (with .php extension) in my includefolder and there is only the link in the srv folder without extension(which is called by the browser...).`

[up](https://www.php.net/manual/vote-note.php?id=122229&page=security.hiding&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122229&page=security.hiding&vote=down "Vote down!")

 -5


[**_omolewastephen at gmail dot com_**](https://www.php.net/manual/en/security.hiding.php#122229) [¶](https://www.php.net/manual/en/security.hiding.php#122229)

**7 years ago**

`I used this on my site and it works great for me
# RewriteEngine on
# Rewrite /foo/bar to /foo/bar.php
# RewriteRule ^([^.?]+)$ %{REQUEST_URI}.php [L]
# Return 404 if original request is /foo/bar.php
# RewriteCond %{THE_REQUEST} "^[^ ]* .*?\.php[? ].*$"
# RewriteRule .* - [L,R=404]
# NOTE! FOR APACHE ON WINDOWS: Add [NC] to RewriteCond like this:
# RewriteCond %{THE_REQUEST} "^[^ ]* .*?\.php[? ].*$" [NC]`

[＋add a note](https://www.php.net/manual/add-note.php?sect=security.hiding&repo=en&redirect=https://www.php.net/manual/en/security.hiding.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google