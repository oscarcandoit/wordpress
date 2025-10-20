---
url: https://www.php.net/manual/en/pdo.construct.php
scraped_at: 2025-10-20T02:58:40.478Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# PDO::\_\_construct

(PHP 5 >= 5.1.0, PHP 7, PHP 8, PECL pdo >= 0.1.0)

PDO::\_\_construct —
Creates a PDO instance representing a connection to a database


### Description [¶](https://www.php.net/manual/en/pdo.construct.php\#refsect1-pdo.construct-description)

public**PDO::\_\_construct**(

[string](https://www.php.net/manual/en/language.types.string.php) `$dsn`,

[?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$username` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[#\[\\SensitiveParameter\]](https://www.php.net/manual/en/class.sensitiveparameter.php)[?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$password` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[?](https://www.php.net/manual/en/language.types.null.php)[array](https://www.php.net/manual/en/language.types.array.php) `$options` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**

)

Creates a PDO instance to represent a connection to the requested
database.


### Parameters [¶](https://www.php.net/manual/en/pdo.construct.php\#refsect1-pdo.construct-parameters)

`dsn`

The Data Source Name, or DSN, contains the information required to
connect to the database.


In general, a DSN consists of the PDO driver name, followed by a colon,
followed by the PDO driver-specific connection syntax. Further
information is available from the [PDO\\
driver-specific documentation](https://www.php.net/manual/en/pdo.drivers.php).


The `dsn` parameter supports three
different methods of specifying the arguments required to create
a database connection:


Driver invocation

`dsn` contains the full DSN.


URI invocation

`dsn` consists of **`uri:`**
followed by a URI that defines the location of a file containing
the DSN string. The URI can specify a local file or a remote URL.


**`uri:file:///path/to/dsnfile`**

Aliasing

`dsn` consists of a name
`name` that maps to
`pdo.dsn.name` in php.ini
defining the DSN string.


> **Note**:
>
>
> The alias must be defined in php.ini, and not .htaccess or httpd.conf

`username`

The user name for the DSN string. This parameter is optional for
some PDO drivers.


`password`

The password for the DSN string. This parameter is optional for
some PDO drivers.


`options`

A key=>value array of driver-specific connection options.


### Errors/Exceptions [¶](https://www.php.net/manual/en/pdo.construct.php\#refsect1-pdo.construct-errors)

A [PDOException](https://www.php.net/manual/en/class.pdoexception.php) is thrown if the attempt
to connect to the requested database fails,
regardless of which **`[PDO::ATTR\_ERRMODE](https://www.php.net/manual/en/pdo.constants.php#pdo.constants.attr-errmode)`** is currently set.


### Examples [¶](https://www.php.net/manual/en/pdo.construct.php\#refsect1-pdo.construct-examples)

**Example #1 Create a PDO instance via driver invocation**

`<?php
$dsn = 'mysql:dbname=testdb;host=127.0.0.1';
$user = 'dbuser';
$password = 'dbpass';
$dbh = new PDO($dsn, $user, $password);
?>`

**Example #2 Create a PDO instance via URI invocation**

The following example assumes that the file
/usr/local/dbconnect exists with file permissions
that enable PHP to read the file. The file contains the PDO DSN to
connect to a DB2 database through the PDO\_ODBC driver:


```
odbc:DSN=SAMPLE;UID=john;PWD=mypass
```

The PHP script can then create a database connection by simply
passing the `uri:` parameter and pointing to
the file URI:


`<?php
$dsn = 'uri:file:///usr/local/dbconnect';
$user = '';
$password = '';
$dbh = new PDO($dsn, $user, $password);
?>`

**Example #3 Create a PDO instance using an alias**

The following example assumes that php.ini contains the following
entry to enable a connection to a MySQL database using only the
alias `mydb`:


```
[PDO]
pdo.dsn.mydb="mysql:dbname=testdb;host=localhost"
```

`<?php
$dsn = 'mydb';
$user = '';
$password = '';
$dbh = new PDO($dsn, $user, $password);
?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/pdo/pdo/construct.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fpdo.construct%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=pdo.construct&repo=en&redirect=https://www.php.net/manual/en/pdo.construct.php)

### User Contributed Notes 9 notes

[up](https://www.php.net/manual/vote-note.php?id=113498&page=pdo.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113498&page=pdo.construct&vote=down "Vote down!")

123


[**_Kiipa at live dot com_**](https://www.php.net/manual/en/pdo.construct.php#113498) [¶](https://www.php.net/manual/en/pdo.construct.php#113498)

**12 years ago**

`To get UTF-8 charset you can specify that in the DSN.
$link = new PDO("mysql:host=localhost;dbname=DB;charset=UTF8");`

[up](https://www.php.net/manual/vote-note.php?id=87231&page=pdo.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87231&page=pdo.construct&vote=down "Vote down!")

41


[**_subme at interia dot pl_**](https://www.php.net/manual/en/pdo.construct.php#87231) [¶](https://www.php.net/manual/en/pdo.construct.php#87231)

**16 years ago**

`To specify a database connection port use the following DSN string
<?php
$dsn = 'mysql:dbname=testdb;host=127.0.0.1;port=3333';
?>`

[up](https://www.php.net/manual/vote-note.php?id=99923&page=pdo.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=99923&page=pdo.construct&vote=down "Vote down!")

28


[**_piotrekkr at o2 dot pl_**](https://www.php.net/manual/en/pdo.construct.php#99923) [¶](https://www.php.net/manual/en/pdo.construct.php#99923)

**15 years ago**

`To connect throught unix socket you need to use
<?php
$dsn = 'mysql:dbname=testdb;unix_socket=/path/to/socket';
?>
You musn't specify host when using socket.`

[up](https://www.php.net/manual/vote-note.php?id=125292&page=pdo.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125292&page=pdo.construct&vote=down "Vote down!")

7


[**_Aymeric S_**](https://www.php.net/manual/en/pdo.construct.php#125292) [¶](https://www.php.net/manual/en/pdo.construct.php#125292)

**5 years ago**

`When trying to connect to a local database, it seems "uri:file:///" is no longer needed. Just write the PDO pilot name followed by the absolute path of the file.
Example : sqlite:C:\VirtualHosts\phpliteadmin\dbs\surveillance_logeas.s3DB`

[up](https://www.php.net/manual/vote-note.php?id=118288&page=pdo.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118288&page=pdo.construct&vote=down "Vote down!")

20


[**_daviddlavier at gmail dot com_**](https://www.php.net/manual/en/pdo.construct.php#118288) [¶](https://www.php.net/manual/en/pdo.construct.php#118288)

**9 years ago**

`I'd like to point out that in PHP 7.0 in the dsn parameter you can't use 'host=localhost' to solve this you can use 'host=127.0.0.1' instead.`

[up](https://www.php.net/manual/vote-note.php?id=128169&page=pdo.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128169&page=pdo.construct&vote=down "Vote down!")

5


[**_theking2 at king dot ma_**](https://www.php.net/manual/en/pdo.construct.php#128169) [¶](https://www.php.net/manual/en/pdo.construct.php#128169)

**2 years ago**

`A generic pattern to connect to a mariadb or mysql database using a settings file
<?php
$_SETTINGS = parse_ini_file('./settings.ini', true);
$db = new \PDO(
"mysql:hostname={$_SETTINGS['db']['host']};dbname={$_SETTINGS['db']['name']}",
$_SETTINGS['db']['user'],
$_SETTINGS['db']['pass'],
[\
    \PDO::ATTR_DEFAULT_FETCH_MODE => \PDO::FETCH_ASSOC,\
    \PDO::MYSQL_ATTR_INIT_COMMAND => "SET NAMES 'utf8mb4'"\
]
);
?>
You might not need the options depicted here but I find them convenient.
Works with a settings.ini file containing for instance:
[db]
host = "localhost"
name = "dbname"
user = "dbuser"
pass = "dbpassword"`

[up](https://www.php.net/manual/vote-note.php?id=124951&page=pdo.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124951&page=pdo.construct&vote=down "Vote down!")

11


[**_Francesco Montanari_**](https://www.php.net/manual/en/pdo.construct.php#124951) [¶](https://www.php.net/manual/en/pdo.construct.php#124951)

**5 years ago**

`Most of the information in the comment here is outdated or wrong.
You do can use host=localhost to connect via socket, which is faster than TCP, so setting 127.0.0.1 is a performance loss.
To use proper utf you should use utf8mb4, for example:
$db = new PDO('mysql:host=' . DATABASE_HOST . ';dbname='. DATABASE_NAME .';charset=utf8mb4', DATABASE_USER, DATABASE_PASSWORD);`

[up](https://www.php.net/manual/vote-note.php?id=96325&page=pdo.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96325&page=pdo.construct&vote=down "Vote down!")

13


[**_Victor T._**](https://www.php.net/manual/en/pdo.construct.php#96325) [¶](https://www.php.net/manual/en/pdo.construct.php#96325)

**15 years ago**

`If you use the UTF-8 encoding, you have to use the fourth parameter :
<?php
$db = new PDO('mysql:host=myhost;dbname=mydb', 'login', 'password', array(PDO::MYSQL_ATTR_INIT_COMMAND => 'SET NAMES \'UTF8\''));
?>`

[up](https://www.php.net/manual/vote-note.php?id=128014&page=pdo.construct&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128014&page=pdo.construct&vote=down "Vote down!")

 -1


[**_Michal Stefanak_**](https://www.php.net/manual/en/pdo.construct.php#128014) [¶](https://www.php.net/manual/en/pdo.construct.php#128014)

**2 years ago**

``If you override PDO with own class and you want to implement alias from php.ini, you have to get it with `get_cfg_var` instead of `ini_get`.
<?php
class PDO extends \PDO
{
    public function __construct(string $dsn, ?string $username = null, ?string $password = null, ?array $options = null)
    {
        //alias
        if (!str_contains($dsn, ':')) {
            $dsn = get_cfg_var('pdo.dsn.' . $dsn);
            if (!$dsn) {
                throw new PDOException('Argument #1 ($dsn) must be a valid data source name');
            }
        }
        // your additional logic
        parent::__construct($dsn, $username, $password, $options);
    }
}
?>``

[＋add a note](https://www.php.net/manual/add-note.php?sect=pdo.construct&repo=en&redirect=https://www.php.net/manual/en/pdo.construct.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google