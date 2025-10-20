---
url: https://www.php.net/manual/en/install.fpm.php
scraped_at: 2025-10-20T02:48:01.609Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# FastCGI Process Manager (FPM) [¶](https://www.php.net/manual/en/install.fpm.php\#install.fpm)

## Table of Contents [¶](https://www.php.net/manual/en/install.fpm.php\#install.fpm)

- [Installation](https://www.php.net/manual/en/install.fpm.install.php)
- [Configuration](https://www.php.net/manual/en/install.fpm.configuration.php)

FPM (FastCGI Process Manager) is
a primary PHP FastCGI implementation containing some features (mostly) useful for heavy-loaded sites.

These features include:


- advanced process management with graceful stop/start;


- pools that give ability to start workers with different
uid/gid/chroot/environment, listening on different ports and using
different php.ini (replaces safe\_mode);


- configurable stdout and stderr logging;


- emergency restart in case of accidental opcode cache destruction;


- accelerated upload support;


- "slowlog" - logging scripts (not just their names, but their PHP
backtraces too, using ptrace and similar things to read remote
process' execute\_data) that are executed unusually slow;


- [fastcgi\_finish\_request()](https://www.php.net/manual/en/function.fastcgi-finish-request.php) \- special function to finish
request and flush all data while continuing to do something
time-consuming (video converting, stats processing etc.);


- dynamic/ondemand/static child spawning;


- basic and extended status info (similar to Apache mod\_status) with
various formats like json, xml and openmetrics supported;


- php.ini-based config file.



### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/install/fpm/index.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Finstall.fpm%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=install.fpm&repo=en&redirect=https://www.php.net/manual/en/install.fpm.php)

### User Contributed Notes 11 notes

[up](https://www.php.net/manual/vote-note.php?id=123758&page=install.fpm&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123758&page=install.fpm&vote=down "Vote down!")

22


[**_info at f1-outsourcing dot eu_**](https://www.php.net/manual/en/install.fpm.php#123758) [¶](https://www.php.net/manual/en/install.fpm.php#123758)

**6 years ago**

`It looks like the php-fpm daemon is not able to use its groups it is running with.
[https://bugs.php.net/bug.php?id=77837](https://bugs.php.net/bug.php?id=77837)`

[up](https://www.php.net/manual/vote-note.php?id=121890&page=install.fpm&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121890&page=install.fpm&vote=down "Vote down!")

20


[**_ganlvtech at qq dot com_**](https://www.php.net/manual/en/install.fpm.php#121890) [¶](https://www.php.net/manual/en/install.fpm.php#121890)

**7 years ago**

````php-fpm is not avaliable on Windows, but you can use IIS or Apache as the "fastcgi process manager".
If you have to use Nginx, here is a solution. Nginx provides a load balancing module. We can distribute the request to different php-cgi.exe process.
< [http://nginx.org/en/docs/http/load\_balancing.html>](http://nginx.org/en/docs/http/load_balancing.html%3E)
< [http://nginx.org/en/docs/http/ngx\_http\_upstream\_module.html>](http://nginx.org/en/docs/http/ngx_http_upstream_module.html%3E)
This is the origin nginx conf.
```
location ~ \.php$ {
    try_files  $uri = 404;
    fastcgi_pass  127.0.0.1:9000;
    fastcgi_index  index.php;
    include  fastcgi.conf;
}
```
You can replace it by
```
upstream php {
    server  127.0.0.1:9000;
    server  127.0.0.1:9001;
    server  127.0.0.1:9002;
    server  127.0.0.1:9003;
}
location ~ \.php$ {
    try_files  $uri = 404;
    fastcgi_pass  php;
    fastcgi_index  index.php;
    include  fastcgi.conf;
}
```
CAUTION!!
php-cgi.exe process will die after several requests, so you have to restart the php-cgi.exe manually to keep a process listening the port.
DON'T USE THIS SOLUTION IN PRODUCTION!!````

[up](https://www.php.net/manual/vote-note.php?id=101366&page=install.fpm&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101366&page=install.fpm&vote=down "Vote down!")

22


[**_robin at robinwinslow dot co dot uk_**](https://www.php.net/manual/en/install.fpm.php#101366) [¶](https://www.php.net/manual/en/install.fpm.php#101366)

**14 years ago**

`Init script setup
===
You will probably want to create an init script for your new php-fpm. Fortunately, PHP 5.3.3 provides one for you, which you should copy to your init directory and change permissions:
$ cp <php-5.3.3-source-dir>/sapi/fpm/init.d.php-fpm.in /etc/init.d/php-fpm
$ chmod 755 /etc/init.d/php-fpm
It requires a certain amount of setup. First of all, make sure your php-fpm.conf file is set up to  create a PID file when php-fpm starts. E.g.:
----
pid = /var/run/php-fpm.pid
----
(also make sure your php-fpm user has permission to create this file).
Now open up your new init script (/etc/init.d/php-fpm) and set the variables at the top to their relevant values. E.g.:
---
prefix=
exec_prefix=
php_fpm_BIN=/sbin/php-fpm
php_fpm_CONF=/etc/php-fpm.conf
php_fpm_PID=/var/run/php-fpm.pid
---
Your init script is now ready. You should now be able to start, stop and reload php-fpm:
$ /etc/init.d/php-fpm start
$ /etc/init.d/php-fpm stop
$ /etc/init.d/php-fpm reload
The one remaining thing you may wish to do is to add your new php-fpm init script to system start-up. E.g. in CentOS:
$ /sbin/chkconfig php-fpm on
===========
Disclaimer: Although I did just do this on my own server about 20 mins ago, everything I've written here is off the top of my head, so it may not be 100% correct. Also, allow for differences in system setup. Some understanding of what you are doing is assumed.`

[up](https://www.php.net/manual/vote-note.php?id=104691&page=install.fpm&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104691&page=install.fpm&vote=down "Vote down!")

20


[**_joel k_**](https://www.php.net/manual/en/install.fpm.php#104691) [¶](https://www.php.net/manual/en/install.fpm.php#104691)

**14 years ago**

`the fpm process supports the USER2 signal, which is used to reload the config file.
kill -USR2 [pid]
should do the trick.`

[up](https://www.php.net/manual/vote-note.php?id=115045&page=install.fpm&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115045&page=install.fpm&vote=down "Vote down!")

18


[**_dreamcat4 at gmail dot com_**](https://www.php.net/manual/en/install.fpm.php#115045) [¶](https://www.php.net/manual/en/install.fpm.php#115045)

**11 years ago**

`Doesn't work? Enable logging!
The php-fpm.log file is a great place to fault-find errors and get to the bottom of a problem. But be sure to enable logging for your specific worker pool. Or you won't see anything!
Example:
To enable error logging for the default [www] worker pool, add this line in the [www] section of your php-fpm.conf:
[www]
catch_workers_output = yes`

[up](https://www.php.net/manual/vote-note.php?id=121725&page=install.fpm&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121725&page=install.fpm&vote=down "Vote down!")

13


[**_user at NOSPAM dot example dot com_**](https://www.php.net/manual/en/install.fpm.php#121725) [¶](https://www.php.net/manual/en/install.fpm.php#121725)

**8 years ago**

`It is important to note that FPM is not built with the windows binaries.  Many of the guides you may find online rely on php-cgi.exe.  Unfortunately they call it FPM but this is incorrect!
The executable php-cgi.exe that is bundled with the windows binaries is a FastCGI interface but it is *not* FPM (Fastcgi Process Manager).  php-cgi.exe does not have multi-threading or concurrent request support, nor support for any of the FPM configuration options.
The only solid information I've gathered into why FPM is not available is a bug report explaining that FPM is built around fork(), which is not natively available on windows ( [https://bugs.php.net/bug.php?id=62447](https://bugs.php.net/bug.php?id=62447)).`

[up](https://www.php.net/manual/vote-note.php?id=122457&page=install.fpm&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122457&page=install.fpm&vote=down "Vote down!")

10


[**_ikrabbe dot ask at gmail dot com_**](https://www.php.net/manual/en/install.fpm.php#122457) [¶](https://www.php.net/manual/en/install.fpm.php#122457)

**7 years ago**

`I'm very unhappy with the way php-fpm handles requests.
There isn't even some SCRIPT_FILENAME in the RFC for CGI, an that's the only standard I found to handle the requests.
Actually what you are doing with PATH_TRANSLATED is supposed to translate to the path, which is broken by media wikis, as they use the PATH_INFO to find the ressource, not some script.
In the original CGI context, the PATH_INFO is passed to the CGI binary to specify some ressource argument. So actually
    SCRIPT_NAME  ~ argv0
    PATH_INFO      ~ argv1
in command context.
Conclusion: We should rewrite php-fpm to obey the rfc3875 CGI standard.
Having SCRIPT_NAME pointing to /something.php, must translate to
    CWD/something.php
CWD is the working directory where php-fpm is started (or configured to change to).
In case of chroot CWD = "".
In any case the SCRIPT_NAME php script can be found with ./SCRIPT_NAME, from the CWD. So the undocumented not standardized SCRIPT_FILENAME should vanish! It breaks the CGI standard.`

[up](https://www.php.net/manual/vote-note.php?id=112045&page=install.fpm&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112045&page=install.fpm&vote=down "Vote down!")

12


[**_kokushibyou at gmail dot com_**](https://www.php.net/manual/en/install.fpm.php#112045) [¶](https://www.php.net/manual/en/install.fpm.php#112045)

**12 years ago**

`PHP-FPM is FAST - but be wary of using it while your code base is stored on NFS - under average load your NFS server will feel some serious strain. I have yet to find a work around for this bug: [https://bugs.php.net/bug.php?id=52312](https://bugs.php.net/bug.php?id=52312)`

[up](https://www.php.net/manual/vote-note.php?id=128948&page=install.fpm&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128948&page=install.fpm&vote=down "Vote down!")

2


[**_&#34;atesin&#34; at the free google mail service_**](https://www.php.net/manual/en/install.fpm.php#128948) [¶](https://www.php.net/manual/en/install.fpm.php#128948)

**2 years ago**

`in response to "ikrabbe dot ask at gmail dot com" about SCRIPT_NAME and PATH_INFO being empty, this could be related...
while configuring php-fpm with nginx in debian (actually raspberry pi), a comment line in .conf grabbed my attention
there is a "feature" (that looks more like a bug) reported about 10 years ago in [http://trac.nginx.org/nginx/ticket/321](http://trac.nginx.org/nginx/ticket/321) ... in which "try_files" could reset the contents of $fastcgi_script_name and $fastcgi_path_info ... this is a workaround mentioned in forums by user "zakaria"
<?php /* not actual php code but nginx .conf */
location ~ [^/]\.php(/|$)
{
fastcgi_split_path_info ^(.+?\.php)(/.*)$;
# Save the $fastcgi_path_info before try_files clear it
set $path_info $fastcgi_path_info;
fastcgi_param PATH_INFO $path_info;
try_files $fastcgi_script_name =404;
fastcgi_pass unix:/var/run/php5-fpm.sock;
fastcgi_index index.php;
include fastcgi_params;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=128604&page=install.fpm&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128604&page=install.fpm&vote=down "Vote down!")

1


[**_jpmkn.iki.fi_**](https://www.php.net/manual/en/install.fpm.php#128604) [¶](https://www.php.net/manual/en/install.fpm.php#128604)

**2 years ago**

`@ ikrabbe you might want to look at mod_rewrite to address the environment variable variation(!) between cgi and cli php.`

[up](https://www.php.net/manual/vote-note.php?id=128950&page=install.fpm&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128950&page=install.fpm&vote=down "Vote down!")

0


[**_&#34;atesin&#34; at the free google mail service_**](https://www.php.net/manual/en/install.fpm.php#128950) [¶](https://www.php.net/manual/en/install.fpm.php#128950)

**2 years ago**

`in response to "dreamcat4 at gmail dot com" about enabling logs in php-fpm
i *hate* going blind, so enabling logs is generally the first thing i do...
by doing dreamcat4 suggestion, logs got enabled but mixed with php process logs ... instead doing that and to isolate logs from [www] worker pool in its own file, these directives worked for me in "www" worker .ini file (you have to set directories and permissions before)
php_admin_flag[log_errors] = on
php_admin_value[error_log] = /var/log/php-fpm/www-error.log`

[＋add a note](https://www.php.net/manual/add-note.php?sect=install.fpm&repo=en&redirect=https://www.php.net/manual/en/install.fpm.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google