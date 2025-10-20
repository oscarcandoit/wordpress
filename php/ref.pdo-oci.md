---
url: https://www.php.net/manual/en/ref.pdo-oci.php
scraped_at: 2025-10-20T02:58:00.813Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Oracle PDO Driver (PDO\_OCI) [¶](https://www.php.net/manual/en/ref.pdo-oci.php\#ref.pdo-oci)

## Installation [¶](https://www.php.net/manual/en/ref.pdo-oci.php\#ref.pdo-oci.installation)

If the Oracle Database is on the same machine as PHP, the database
software already contains the necessary libraries. When PHP is on
a different machine, use the free
[» Oracle Instant Client](https://www.oracle.com/database/technologies/instant-client.html) libraries.
For details refer to the [OCI8 Requirements](https://www.php.net/manual/en/oci8.requirements.php) section.


## PHP 8.4 [¶](https://www.php.net/manual/en/ref.pdo-oci.php\#pdo-oci.installation.php84)

This extension has been moved to the [» PECL](https://pecl.php.net/)
repository and is no longer bundled with PHP as of PHP 8.4.0


Information for installing this PECL extension may be
found in the manual chapter titled [Installation\\
of PECL extensions](https://www.php.net/manual/en/install.pecl.php). Additional information such as new releases,
downloads, source files, maintainer information, and a CHANGELOG, can be
located here:
[» https://pecl.php.net/package/PDO\_OCI](https://pecl.php.net/package/PDO_OCI).


## PHP < 8.4 [¶](https://www.php.net/manual/en/ref.pdo-oci.php\#pdo-oci.installation.phplt84)

Use **--with-pdo-oci\[=DIR\]** to install
the PDO Oracle OCI extension, where the optional `[=DIR]`
is the Oracle Home directory. `[=DIR]` defaults to
the $ORACLE\_HOME environment variable.


Use **--with-pdo-oci=instantclient,prefix,version**
for an Oracle Instant Client SDK, where prefix and
version are configured.


```
// Using $ORACLE_HOME
$ ./configure --with-pdo-oci

// Using OIC for Linux with 10.2.0.3 RPMs with a /usr prefix
$ ./configure --with-pdo-oci=instantclient,/usr,10.2.0.3

```

## Predefined Constants [¶](https://www.php.net/manual/en/ref.pdo-oci.php\#pdo-oci.constants)

The constants below are defined by
this driver, and will only be available when the extension has been either
compiled into PHP or dynamically loaded at runtime. In addition, these
driver-specific constants should only be used if you are using this driver.
Using driver-specific attributes with another driver may result in
unexpected behaviour. [PDO::getAttribute()](https://www.php.net/manual/en/pdo.getattribute.php) may be used to
obtain the **`[PDO::ATTR\_DRIVER\_NAME](https://www.php.net/manual/en/pdo.constants.php#pdo.constants.attr-driver-name)`** attribute to check the
driver, if your code can run against multiple drivers.

**`[PDO::OCI\_ATTR\_ACTION](https://www.php.net/manual/en/ref.pdo-oci.php#pdo.constants.oci-attr-action)`**
([int](https://www.php.net/manual/en/language.types.integer.php))


Provides a way to specify the action on the database session.


This exists as of PHP 7.2.16 and 7.3.3


**`[PDO::OCI\_ATTR\_CLIENT\_INFO](https://www.php.net/manual/en/ref.pdo-oci.php#pdo.constants.oci-attr-client-info)`**
([int](https://www.php.net/manual/en/language.types.integer.php))


Provides a way to specify the client info on the database session.


This exists as of PHP 7.2.16 and 7.3.3


**`[PDO::OCI\_ATTR\_CLIENT\_IDENTIFIER](https://www.php.net/manual/en/ref.pdo-oci.php#pdo.constants.oci-attr-client-identifier)`**
([int](https://www.php.net/manual/en/language.types.integer.php))


Provides a way to specify the client identifier on the database session.


This exists as of PHP 7.2.16 and 7.3.3


**`[PDO::OCI\_ATTR\_MODULE](https://www.php.net/manual/en/ref.pdo-oci.php#pdo.constants.oci-attr-module)`**
([int](https://www.php.net/manual/en/language.types.integer.php))


Provides a way to specify the module on the database session.


This exists as of PHP 7.2.16 and 7.3.3


## Table of Contents [¶](https://www.php.net/manual/en/ref.pdo-oci.php\#ref.pdo-oci)

- [PDO\_OCI DSN](https://www.php.net/manual/en/ref.pdo-oci.connection.php) — Connecting to Oracle databases

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/pdo_oci/reference.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fref.pdo-oci%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.pdo-oci&repo=en&redirect=https://www.php.net/manual/en/ref.pdo-oci.php)

### User Contributed Notes 8 notes

[up](https://www.php.net/manual/vote-note.php?id=128538&page=ref.pdo-oci&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128538&page=ref.pdo-oci&vote=down "Vote down!")

6


[**_Wolfgang Riedmann_**](https://www.php.net/manual/en/ref.pdo-oci.php#128538) [¶](https://www.php.net/manual/en/ref.pdo-oci.php#128538)

**2 years ago**

`An important hint: if you are using prebuilt PHP packages where PDO_OCI is not compiled in, you should download the original PHP sources for the PHP version your server is using.
These sources contain the PDO_OCI source in the ext/pdo_oci directory.
Change to that directory, build the module using
phpize
./configure
make
and then install the newly build module to your PHP extension directory and add it to your configuration.
For me this has worked on a Debian server with the sury.org modules (PHP 8.2).`

[up](https://www.php.net/manual/vote-note.php?id=64819&page=ref.pdo-oci&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=64819&page=ref.pdo-oci&vote=down "Vote down!")

9


[**_cursade at hotmail dot com_**](https://www.php.net/manual/en/ref.pdo-oci.php#64819) [¶](https://www.php.net/manual/en/ref.pdo-oci.php#64819)

**19 years ago**

`if oracle and oracle instant client has been installed,
without db in the same host
For UNIX/LINUX，set $LD_LIBRARY_PATH
appent your instant client path  and  client/lib path to it,
For windows set PATH like this
After set the path ,set TNS_ADMIN everioment ,point to
where  tnsnames.ora located.
Then,you can use service name to connect to your Database
Test coding
<?php
$param = $_POST;
$db_username = "youusername";
$db_password = "yourpassword";
$db = "oci:dbname=yoursid";
$conn = new PDO($db,$db_username,$db_password);
$name = $param['module'];
$file = $param['file'];
$stmt = $conn->exec("INSERT INTO AL_MODULE (AL_MODULENAME, AL_MODULEFILE) VALUES ('$name', '$file')");
?>`

[up](https://www.php.net/manual/vote-note.php?id=106139&page=ref.pdo-oci&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106139&page=ref.pdo-oci&vote=down "Vote down!")

6


[**_php at ideacode dot com_**](https://www.php.net/manual/en/ref.pdo-oci.php#106139) [¶](https://www.php.net/manual/en/ref.pdo-oci.php#106139)

**14 years ago**

`If you're getting the "I'm too dumb to find oci.h" error, try creating a variety of paths.  One variety uses just the major and minor of your OIC version (eg, 11.2 for 11.2.0.2) and another variety uses client64 as well as client.
Something like this (for 11.2.0.2):
ln -s /usr/include/oracle/11.2.0.2/ /usr/include/oracle/11.2
ln -s /usr/include/oracle/11.2/client /usr/include/oracle/11.2/client64
ln -s /usr/lib/oracle/11.2.0.2/ /usr/lib/oracle/11.2
ln -s /usr/lib/oracle/11.2/client /usr/lib/oracle/11.2/client64
This should cover your bases for 64-bit systems, as well as PHP patched to use the major.minor version number only.  See also PHP bug #44989.`

[up](https://www.php.net/manual/vote-note.php?id=88331&page=ref.pdo-oci&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88331&page=ref.pdo-oci&vote=down "Vote down!")

4


[**_fernando dot wendt at gmail dot com_**](https://www.php.net/manual/en/ref.pdo-oci.php#88331) [¶](https://www.php.net/manual/en/ref.pdo-oci.php#88331)

**16 years ago**

`To enable PDO support on PHP for Oracle Instant Client 11.1.x, you should follow the syntax above in the compile command, just as pointed by Andrew [http://bugs.php.net/bug.php?id=39312,](http://bugs.php.net/bug.php?id=39312,) taking by default you have installed the OIC at /usr/lib/oracle (instant client and sdk at subfolder):
./configure --with-oci8=shared,instantclient,/usr/lib/oracle
--with-pdo-oci=instantclient,/usr/lib/oracle,11.1
Just saying your release version from the Oracle OIC.
It compiles fine then.
Best regards.`

[up](https://www.php.net/manual/vote-note.php?id=130418&page=ref.pdo-oci&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130418&page=ref.pdo-oci&vote=down "Vote down!")

0


[**_wriedmann at gmail dot com_**](https://www.php.net/manual/en/ref.pdo-oci.php#130418) [¶](https://www.php.net/manual/en/ref.pdo-oci.php#130418)

**3 months ago**

`As addition to what I wrote 2 years ago:
if you are installing on Debian with a Debian provided package, install the source with
apt source php8.2
Then you have to set ORACLE_HOME like that:
ORACLE_HOME=/usr/lib/oracle/19.6
export ORACLE_HOME
before running ./configure.
After that, I had to add the include directory
-I/usr/include/oracle/19.6/client64/
into the Makefile to successfully build the module.`

[up](https://www.php.net/manual/vote-note.php?id=104350&page=ref.pdo-oci&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=104350&page=ref.pdo-oci&vote=down "Vote down!")

 -3


[**_redlorry919 at gmail dot com_**](https://www.php.net/manual/en/ref.pdo-oci.php#104350) [¶](https://www.php.net/manual/en/ref.pdo-oci.php#104350)

**14 years ago**

`Take note of the note at the top, this really is an experimental extension. I had a problem trying to read data from Oracle which resulted in some strange behaviour in PHP. i.e. foreach loops not ending, with no error messages. I also managed to get the data from Oracle into an array in PHP, but then couldn't return the array from a function.
After pulling my hair out for a day, it turned out to be a CLOB column in Oracle that caused the strange behaviour in PHP. I assume this extension doesn't fully support them.
Instead I've typecast it within the SQL to a VARCHAR2 which seems to resolve it:
SELECT CAST(columnx AS VARCHAR2(4000)) AS columnx ...
It might help someone else having similar issues.`

[up](https://www.php.net/manual/vote-note.php?id=66972&page=ref.pdo-oci&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=66972&page=ref.pdo-oci&vote=down "Vote down!")

 -2


[**_moc.aciremi@yvelj_**](https://www.php.net/manual/en/ref.pdo-oci.php#66972) [¶](https://www.php.net/manual/en/ref.pdo-oci.php#66972)

**19 years ago**

`A Statement of Warning:
PDO::oci does not support REF CURSORS.
This is mentioned nowhere (until now!) on this page.
And now you know!
If you want ref cursors avoid PDO for now.
My Reference for this claim:
[http://www.oracle.com/technology/pub/articles/](http://www.oracle.com/technology/pub/articles/)
php_experts/otn_pdo_oracle5.html
GREAT article, excellent piece, really. It's not clear to me
how old this document is, but it must have some dust on it,
given it's references to "PHP5.1 ...' which is a little way off yet' "
... as of 2006-06-01, PHP5.1 has been with us for quite some time.`

[up](https://www.php.net/manual/vote-note.php?id=98629&page=ref.pdo-oci&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=98629&page=ref.pdo-oci&vote=down "Vote down!")

 -4


[**_geompse at gmail dot com_**](https://www.php.net/manual/en/ref.pdo-oci.php#98629) [¶](https://www.php.net/manual/en/ref.pdo-oci.php#98629)

**15 years ago**

`Notice the red block at the beginning of this page... pdo_oci is HIGHLY experimental.
Even though it is under dev from 2004, it lakes today support for things that _do_ matters :
 - bind a varchar2 of 3500 chars
 - get selected metas
 - left join with blobs/clobs
 - etc.
For the story, since we use pdo_pgsql in our software, I thought it would be viable to use pdo_oci for running under Oracle. After a long battle, I finally won :
1) If requested driver has a non-experimental pdo version available, use it.
2) else (well, for pdo_oci at least), use an abstraction layer of your own.
3) you're done.
What I did in more details...
2 "main" classes for being compliant with "$obj instanceof PDO" or such :
 - class PhpDb extends PDO
 - class PhpDbStatement extends PDOStatement
2 "abstract" classes that defines what PDO actually does :
 - abstract class PhpDbAbstract
 - abstract class PhpDbAbstractStatement
And at last for each driver, 2 classes doing the abstraction :
 - class PhpDbDriverOracle extends PhpDbAbstract
 - class PhpDbDriverOracleStatement extends PhpDbAbstractStatement
"main" classes are accessed from your script, simply replace "new PDO" with "new PhpDb".
"abstract" classes are mainly there for the documentation :p
"driver" classes do the job in background, they are instances by the main classes.
My PhpDb will be in an open source project sooner or later, search google or mail me !`

[＋add a note](https://www.php.net/manual/add-note.php?sect=ref.pdo-oci&repo=en&redirect=https://www.php.net/manual/en/ref.pdo-oci.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google