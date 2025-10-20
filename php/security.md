---
url: https://www.php.net/manual/en/security.php
scraped_at: 2025-10-20T02:37:58.675Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Security [¶](https://www.php.net/manual/en/security.php\#security)

- [Introduction](https://www.php.net/manual/en/security.intro.php)
- [General considerations](https://www.php.net/manual/en/security.general.php)
- [Installed as CGI binary](https://www.php.net/manual/en/security.cgi-bin.php)
  - [Possible attacks](https://www.php.net/manual/en/security.cgi-bin.attacks.php)
  - [Case 1: only public files served](https://www.php.net/manual/en/security.cgi-bin.default.php)
  - [Case 2: using cgi.force\_redirect](https://www.php.net/manual/en/security.cgi-bin.force-redirect.php)
  - [Case 3: setting doc\_root or user\_dir](https://www.php.net/manual/en/security.cgi-bin.doc-root.php)
  - [Case 4: PHP parser outside of web tree](https://www.php.net/manual/en/security.cgi-bin.shell.php)
- [Installed as an Apache module](https://www.php.net/manual/en/security.apache.php)
- [Session Security](https://www.php.net/manual/en/security.sessions.php)
- [Filesystem Security](https://www.php.net/manual/en/security.filesystem.php)
  - [Null bytes related issues](https://www.php.net/manual/en/security.filesystem.nullbytes.php)
- [Database Security](https://www.php.net/manual/en/security.database.php)
  - [Designing Databases](https://www.php.net/manual/en/security.database.design.php)
  - [Connecting to Database](https://www.php.net/manual/en/security.database.connection.php)
  - [Encrypted Storage Model](https://www.php.net/manual/en/security.database.storage.php)
  - [SQL Injection](https://www.php.net/manual/en/security.database.sql-injection.php)
- [Error Reporting](https://www.php.net/manual/en/security.errors.php)
- [User Submitted Data](https://www.php.net/manual/en/security.variables.php)
- [Hiding PHP](https://www.php.net/manual/en/security.hiding.php)
- [Keeping Current](https://www.php.net/manual/en/security.current.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-base/blob/master/manual.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsecurity%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=security&repo=en&redirect=https://www.php.net/manual/en/security.php)

### User Contributed Notes 11 notes

[up](https://www.php.net/manual/vote-note.php?id=72806&page=security&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=72806&page=security&vote=down "Vote down!")

23


[**_dangan at blackjaguargaming dot net_**](https://www.php.net/manual/en/security.php#72806) [¶](https://www.php.net/manual/en/security.php#72806)

**18 years ago**

`I'd recommend a 404 over a 403 considering a 403 proves there is something worth hacking into.
index.php:
<?php
define('isdoc',1);
include('includes/include.sqlfunctions.php');
// Rest of code for index.php
?>
include.sqlfunctions.php (or other include file):
<?php
if(isdoc !== 1) // Not identical to 1
{
    header('HTTP/1.1 404 Not Found');
    echo "<!DOCTYPE HTML PUBLIC \"-//IETF//DTD HTML 2.0//EN\">\n<html><head>\n<title>404 Not Found</title>\n</head>";
    echo "<body>\n<h1>Not Found</h1>\n<p>The requested URL ".$_SERVER['REQUEST_URI']." was not found on this server.</p>\n";
    echo "<hr>\n".$_SERVER['SERVER_SIGNATURE']."\n</body></html>\n";
    // Echo output similar to Apache's default 404 (if thats what you're using)
    exit;
}
// Rest of code for this include
?>`

[up](https://www.php.net/manual/vote-note.php?id=64840&page=security&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=64840&page=security&vote=down "Vote down!")

18


[**_djjokla AT gmail dot com_**](https://www.php.net/manual/en/security.php#64840) [¶](https://www.php.net/manual/en/security.php#64840)

**19 years ago**

`If a single file has to be included than I use the following
index.php ( where the file is gonna be included )
___________
<?php
    define('thefooter', TRUE);
    include('folder/footer.inc.php');
?>
and the footer file (for example) looks this way then
footer.inc.php ( the file to be inluded )
___________
<?php
    defined('thefooter') or die('Not with me my friend');
    echo('Copyright to me in the year 2000');
?>
So when someone tries to access the footer.php file directly he/she/it will get the "Not with me my friend" messages written on the screen. An alternative option is to redirect the person who wants to access the file directly to a different location, so instead of the above code you would have to write the following in the footer.inc.php file.
<?php
    defined('thefooter') or header('Location: [http://www.location.com](http://www.location.com/)');
    echo('Copyright to me in the year 2000');
?>
In normal case a redirection to an external site would be annoying to the visitor, but since this visitor is more interested in hacking the site than in reading the content, I think it's only fair to create such an redirection. We dont' realy want someome like this on our sites.
For the file protection I use .htaccess in which I say to protect the file itself and every .inc file
<Files ~ "^.*\.([Hh][Tt]|[Ii][Nn][Cc])">
Order allow,deny
Deny from all
Satisfy All
</Files>
The .htaccess file should result an Error 403 if someone tries to access the files directly. If for some reason this shouldn't work, then the "Not with me my friend" text apears or a redirection (depending what is used)
In my eyes this looks o.k. and safe.`

[up](https://www.php.net/manual/vote-note.php?id=70740&page=security&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70740&page=security&vote=down "Vote down!")

11


[**_k_**](https://www.php.net/manual/en/security.php#70740) [¶](https://www.php.net/manual/en/security.php#70740)

**18 years ago**

`How about not putting the php code in the web-root at all...?
You can create a public directory with the css, html, etc and index.php there. Then use the include_path setting to point to the actual php code, eg...
webstuff
phpcode
public
    images
    css
    index.php
then set the include path to "../phpcode" and, as php is executed from the directory of the script, all should be well.
I'd also call the main index "main.page", or something else, instead of "index.php" and change the web server default index page. That way you cant get hit by things trawlling the web for index pages.`

[up](https://www.php.net/manual/vote-note.php?id=57851&page=security&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=57851&page=security&vote=down "Vote down!")

9


[**_Thomas "Balu" Walter_**](https://www.php.net/manual/en/security.php#57851) [¶](https://www.php.net/manual/en/security.php#57851)

**20 years ago**

`Since many users can not modify apache configurations or use htaccess files, the best way to avoid unwanted access to include files would be a line at the beginning of the include-file:
<?php if (!defined('APPLICATION')) exit; ?>
And in all files that are allowed to be called externally:
<?php define('APPLICATION', true); ?>
     Balu`

[up](https://www.php.net/manual/vote-note.php?id=33627&page=security&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=33627&page=security&vote=down "Vote down!")

10


[**_ocrow at simplexity dot net_**](https://www.php.net/manual/en/security.php#33627) [¶](https://www.php.net/manual/en/security.php#33627)

**22 years ago**

`If your PHP pages include() or require() files that live within the web server document root, for example library files in the same directory as the PHP pages, you must account for the possibility that attackers may call those library files directly.
Any program level code in the library files (ie code not part of function definitions) will be directly executable by the caller outside of the scope of the intended calling sequence.  An attacker may be able to leverage this ability to cause unintended effects.
The most robust way to guard against this possibility is to prevent your webserver from calling the library scripts directly, either by moving them out of the document root, or by putting them in a folder configured to refuse web server access. With Apache for example, create a .htaccess file in the library script folder with these directives:
Order Allow,Deny
Deny from any`

[up](https://www.php.net/manual/vote-note.php?id=123517&page=security&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123517&page=security&vote=down "Vote down!")

4


[**_inland14 at live dot com_**](https://www.php.net/manual/en/security.php#123517) [¶](https://www.php.net/manual/en/security.php#123517)

**6 years ago**

`Good Dharma tokens which are basically in the feed somewhere that allow users that are not reprogramming and injecting to get into the site.
Change this POST AJAX call URL every couple minutes to exclude users who didn't follow your portal. You can combine this with where they came from. Just in the case of advertised click-thrus.
You can make a perfectly good token from time() and some measure away from it every ~5th minute(?). Balance the load by free token grasping at login, or even if they just got to the site. And don't let them into the feed past the designated 5th minute, or algorithmic sum for your timed change of the guard, without knowledge of the token. This can be caught up by passing variables across pages. Directly injecting the POST token with a curl to your own site. And combining that like a session ID.`

[up](https://www.php.net/manual/vote-note.php?id=69775&page=security&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=69775&page=security&vote=down "Vote down!")

6


[**_steffen at morkland dot com_**](https://www.php.net/manual/en/security.php#69775) [¶](https://www.php.net/manual/en/security.php#69775)

**19 years ago**

`In Reply to djjokla and others
Consider placing all incude files as mentioned before in a seperate folder containing a .htaccess containing a Order Deny,Allow
the create a index file, which is intended to handle ALL request made to you php application, then call it with index.php?view=index
the index file could look a bit like this:
<?php
switch($_GET['view']){
    case 'index':
        include('libs/index.php');
        break;
    default:
        include('libs/404.php');
        break;
}
?>
this could be an array or something even more creative. it actually does'nt matter how you do it... running all pages through one central script has one big advantage.... CONTROL.
at any givin time, you can easily implement access control to functions without forgetting crucial files.`

[up](https://www.php.net/manual/vote-note.php?id=120039&page=security&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120039&page=security&vote=down "Vote down!")

1


[**_Ray.Paseur sometimes uses Gmail_**](https://www.php.net/manual/en/security.php#120039) [¶](https://www.php.net/manual/en/security.php#120039)

**9 years ago**

`Password hashing should be linked here:
[http://php.net/manual/en/faq.passwords.php](http://php.net/manual/en/faq.passwords.php)`

[up](https://www.php.net/manual/vote-note.php?id=117637&page=security&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117637&page=security&vote=down "Vote down!")

0


[**_Anonymous_**](https://www.php.net/manual/en/security.php#117637) [¶](https://www.php.net/manual/en/security.php#117637)

**10 years ago**

`chroot is NOT a security feature. Don't use it as one. Please read the man pages of chroot to understand what its really used for`

[up](https://www.php.net/manual/vote-note.php?id=31678&page=security&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=31678&page=security&vote=down "Vote down!")

 -1


[**_ManifoldNick at columbus dot rr dot com_**](https://www.php.net/manual/en/security.php#31678) [¶](https://www.php.net/manual/en/security.php#31678)

**22 years ago**

`Remember that security risks often don't involve months of prep work or backdoors or whatever else you saw on Swordfish ;) In fact one of the bigges newbie mistakes is not removing "<" from user input (especially when using message boards) so in theory a user could secerely mess up a page or even have your server run php scripts which would allow them to wreak havoc on your site.`

[up](https://www.php.net/manual/vote-note.php?id=33483&page=security&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=33483&page=security&vote=down "Vote down!")

 -2


[**_annonymous at domain dot com_**](https://www.php.net/manual/en/security.php#33483) [¶](https://www.php.net/manual/en/security.php#33483)

**22 years ago**

`best bet is to build php as cgi, run under suexec, with chroot jailed users. Not the best, but fairly unobtrusive, provides several levels of checkpoints, and has only the detriment of being, well, kinda slow. 8)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=security&repo=en&redirect=https://www.php.net/manual/en/security.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google