---
url: https://www.php.net/manual/en/language.constants.predefined.php
scraped_at: 2025-10-20T02:37:39.122Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Predefined constants [¶](https://www.php.net/manual/en/language.constants.predefined.php\#language.constants.predefined)

PHP provides a large number of [predefined constants](https://www.php.net/manual/en/reserved.constants.php) to any script
which it runs. Many of these constants, however, are created by
various extensions, and will only be present when those extensions
are available, either via dynamic loading or because they have
been compiled in.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/constants.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.constants.predefined%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.constants.predefined&repo=en&redirect=https://www.php.net/manual/en/language.constants.predefined.php)

### User Contributed Notes 5 notes

[up](https://www.php.net/manual/vote-note.php?id=57033&page=language.constants.predefined&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=57033&page=language.constants.predefined&vote=down "Vote down!")

289


[**_vijaykoul\_007 at rediffmail dot com_**](https://www.php.net/manual/en/language.constants.predefined.php#57033) [¶](https://www.php.net/manual/en/language.constants.predefined.php#57033)

**20 years ago**

`the difference between
__FUNCTION__ and __METHOD__ as in PHP 5.0.4 is that
__FUNCTION__ returns only the name of the function
while as __METHOD__ returns the name of the class alongwith the name of the function
class trick
{
      function doit()
      {
                echo __FUNCTION__;
      }
      function doitagain()
      {
                echo __METHOD__;
      }
}
$obj=new trick();
$obj->doit();
output will be ----  doit
$obj->doitagain();
output will be ----- trick::doitagain`

[up](https://www.php.net/manual/vote-note.php?id=71064&page=language.constants.predefined&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=71064&page=language.constants.predefined&vote=down "Vote down!")

48


[**_Tomek Perlak \[tomekperlak at tlen pl\]_**](https://www.php.net/manual/en/language.constants.predefined.php#71064) [¶](https://www.php.net/manual/en/language.constants.predefined.php#71064)

**18 years ago**

`The __CLASS__ magic constant nicely complements the get_class() function.
Sometimes you need to know both:
- name of the inherited class
- name of the class actually executed
Here's an example that shows the possible solution:
<?php
class base_class
{
    function say_a()
    {
        echo "'a' - said the " . __CLASS__ . "<br/>";
    }
    function say_b()
    {
        echo "'b' - said the " . get_class($this) . "<br/>";
    }
}
class derived_class extends base_class
{
    function say_a()
    {
        parent::say_a();
        echo "'a' - said the " . __CLASS__ . "<br/>";
    }
    function say_b()
    {
        parent::say_b();
        echo "'b' - said the " . get_class($this) . "<br/>";
    }
}
$obj_b = new derived_class();
$obj_b->say_a();
echo "<br/>";
$obj_b->say_b();
?>
The output should look roughly like this:
'a' - said the base_class
'a' - said the derived_class
'b' - said the derived_class
'b' - said the derived_class`

[up](https://www.php.net/manual/vote-note.php?id=114723&page=language.constants.predefined&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114723&page=language.constants.predefined&vote=down "Vote down!")

13


[**_php at kenman dot net_**](https://www.php.net/manual/en/language.constants.predefined.php#114723) [¶](https://www.php.net/manual/en/language.constants.predefined.php#114723)

**11 years ago**

`Just learned an interesting tidbit regarding __FILE__ and the newer __DIR__ with respect to code run from a network share: the constants will return the *share* path when executed from the context of the share.
Examples:
// normal context
// called as "php -f c:\test.php"
__DIR__ === 'c:\';
__FILE__ === 'c:\test.php';
// network share context
// called as "php -f \\computerName\c$\test.php"
__DIR__ === '\\computerName\c$';
__FILE__ === '\\computerName\c$\test.php';
NOTE: realpath('.') always seems to return an actual filesystem path regardless of the execution context.`

[up](https://www.php.net/manual/vote-note.php?id=119175&page=language.constants.predefined&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119175&page=language.constants.predefined&vote=down "Vote down!")

8


[**_Sbastien Fauvel_**](https://www.php.net/manual/en/language.constants.predefined.php#119175) [¶](https://www.php.net/manual/en/language.constants.predefined.php#119175)

**9 years ago**

`Note a small inconsistency when using __CLASS__ and __METHOD__ in traits (stand php 7.0.4): While __CLASS__ is working as advertized and returns dynamically the name of the class the trait is being used in, __METHOD__ will actually prepend the trait name instead of the class name!`

[up](https://www.php.net/manual/vote-note.php?id=125170&page=language.constants.predefined&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125170&page=language.constants.predefined&vote=down "Vote down!")

 -1


[**_public at taliesinnuin dot net_**](https://www.php.net/manual/en/language.constants.predefined.php#125170) [¶](https://www.php.net/manual/en/language.constants.predefined.php#125170)

**5 years ago**

`If you're using PHP with fpm (common in this day and age), be aware that __DIR__ and __FILE__ will return values based on the fpm root which MAY differ from its actual location on the file system.
This can cause temporary head-scratching if deploying an app where php files within the web root pull in PHP files from outside of itself (a very common case). You may be wondering why __DIR__ returns "/" when the file itself lives in /var/www/html or whathaveyou.
You might handle such a situation by having NGINX explicitly add the necessary part of the path in its fastcgi request and then you can set the root on the FPM process / server / container to be something other than the webroot (so long as no other way it could become publicly accessible).
Hope that saves someone five minutes who's moving code to FPM that uses __DIR__.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.constants.predefined&repo=en&redirect=https://www.php.net/manual/en/language.constants.predefined.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google