---
url: https://www.php.net/manual/en/security.variables.php
scraped_at: 2025-10-20T02:37:45.720Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# User Submitted Data [¶](https://www.php.net/manual/en/security.variables.php\#security.variables)

The greatest weakness in many PHP programs is not inherent in the
language itself, but merely an issue of code not being written with
security in mind. For this reason, you should always take the time
to consider the implications of a given piece of code, to ascertain
the possible damage if an unexpected variable is submitted to it.


**Example #1 Dangerous Variable Usage**

`<?php
// remove a file from the user's home directory... or maybe
// somebody else's?
unlink ($evil_var);
// Write logging of their access... or maybe an /etc/passwd entry?
fwrite ($fp, $evil_var);
// Execute something trivial.. or rm -rf *?
system ($evil_var);
exec ($evil_var);
?>`

You should always carefully examine your code to make sure that any
variables being submitted from a web browser are being properly
checked, and ask yourself the following questions:


- Will this script only affect the intended files?

- Can unusual or undesirable data be acted upon?

- Can this script be used in unintended ways?

- Can this be used in conjunction with other scripts in a negative
manner?

- Will any transactions be adequately logged?


By adequately asking these questions while writing the script,
rather than later, you prevent an unfortunate re-write when you
need to increase your security. By starting out with this mindset,
you won't guarantee the security of your system, but you can help
improve it.


Improve security by disabling convenience settings that obscure input
data's origin, validity, or integrity. Implicit variable creation and
unchecked input can lead to vulnerabilities like injection attacks and
data manipulation.


Features like `register_globals` and
`magic_quotes` (both removed in PHP 5.4.0) once contributed
to these risks by automatically creating variables from user input and
escaping data inconsistently. While no longer in PHP, similar risks persist
if input handling is mismanaged.


Enable [error\_reporting(E\_ALL)](https://www.php.net/manual/en/function.error-reporting.php) to
help detect uninitialized variables and validate input. Use strict types
( [declare(strict\_types=1)](https://www.php.net/manual/en/language.types.declarations.php#language.types.declarations.strict),
introduced in PHP 7) to enforce type safety, prevent unintended type conversions,
and improving overall security.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/security/variables.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsecurity.variables%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=security.variables&repo=en&redirect=https://www.php.net/manual/en/security.variables.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=56715&page=security.variables&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=56715&page=security.variables&vote=down "Vote down!")

76


[**_Uli Kusterer_**](https://www.php.net/manual/en/security.variables.php#56715) [¶](https://www.php.net/manual/en/security.variables.php#56715)

**20 years ago**

`One thing I would repeat in the docs here is what information actually comes from the user. Many people think a Cookie, since it's written by PHP, was safe. But the fact is that it's stored on the user's computer, transferred by the user's browser, and thus very easy to manipulate.
So, it'd be handy to mention here again that:
CGI parameters in the URL, HTTP POST data and cookie variables are considered "user data" and thus need to be validated. Session data and SQL database contents only need to be validated if they came from untrustworthy sources (like the ones just mentioned).
Not new, but I would have expected this info under this headline, at least as a short recap plus linlk to the actual docs.`

[up](https://www.php.net/manual/vote-note.php?id=80829&page=security.variables&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=80829&page=security.variables&vote=down "Vote down!")

6


[**_Livingstone@stonyhills\[dot\]com_**](https://www.php.net/manual/en/security.variables.php#80829) [¶](https://www.php.net/manual/en/security.variables.php#80829)

**17 years ago**

`making sure your form is submitted from your page! Could also be adapted to url, by additing &token to the query string and checking this against session data(or what ever array you like) with $_GET, not that this string is randomly generated and stored. If you like you could build your own array to store the generated string if you dont want to use $_SESSION, say you could make yours like $tokens = array(), and in your easysecure class you store all the stuff in that array!
<?php
class easysecure {

    var $curr_user;
    var $curr_permission;
    var $curr_task;
    var $validpermission;
    var $error;


    function &setVar( $name, $value=null ) {
        if (!is_null( $value )) {
            $this->$name = $value;
        }
        return $this->$name;
    }
    function maketoken($formname, $id){

        $token = md5(uniqid(rand(), true));

        $_SESSION[$formname.$id] = $token;

        return $token;
    }

    function checktoken($token, $formname, $id){
        //print_r($_SESSION);
        //echo ($token);
        //if we dont have a valid token, return invalid;
        if(!$token){
            $this->setVar('validpermission', 0);
            $this->setVar('error', 'no token found, security bridgedetected');
            return false;
        }

        //if we have a valid token check that is is valid
        $key = $_SESSION[$formname.$id];
        if($key !== $token ){
            $this->setVar('validpermission', 0);
            $this->setVar('error', 'invalid token');
            return false;
        }

        if($this->validpermission !==1){
              echo 'invalid Permissions to run this script';
              return false;
        }else{
            return true;
        }
    }

}
?>
<?php $userid = *** //make it what ever id you like ?>
<form name="newform" action="index.php" method="post">
<input type="text" name="potentialeveilfield" value="" size 30 />
<input type="hidden" name="token" value="<?php echo maketoken(newform, $userid); //$userid here could be user profile id ?>" />
<input type="submit" />
</form>
Now when processing the form... check the value of your token
<?php
//well you know the form name
if(!checktoken($_POST['token'], 'newform', $userid))
{ //failed
exit(); //or what ever termination and notification method best suits you.
//you could also design the class your way to get more accurate fail (error messages from the var)
}
//you can now continue with input data clean up (validation)
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=security.variables&repo=en&redirect=https://www.php.net/manual/en/security.variables.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google