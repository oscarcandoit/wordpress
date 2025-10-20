---
url: https://www.php.net/manual/en/function.session-destroy.php
scraped_at: 2025-10-20T02:53:55.254Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# session\_destroy

(PHP 4, PHP 5, PHP 7, PHP 8)

session\_destroy — Destroys all data registered to a session

### Description [¶](https://www.php.net/manual/en/function.session-destroy.php\#refsect1-function.session-destroy-description)

**session\_destroy**(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**session\_destroy()** destroys all of the data associated
with the current session. It does not unset any of the global variables
associated with the session, or unset the session cookie.
To use the session variables again, [session\_start()](https://www.php.net/manual/en/function.session-start.php) has
to be called.


> **Note**:
>
> You do not have to call **session\_destroy()** from usual
> code. Cleanup $\_SESSION array rather than destroying session data.

In order to kill the session altogether, the
session ID must also be unset. If a cookie is used to propagate the
session ID (default behavior), then the session cookie must be deleted.
[setcookie()](https://www.php.net/manual/en/function.setcookie.php) may be used for that.


When [session.use\_strict\_mode](https://www.php.net/manual/en/session.configuration.php#ini.session.use-strict-mode)
is enabled. You do not have to remove obsolete session ID cookie because
session module will not accept session ID cookie when there is no
data associated to the session ID and set new session ID cookie.
Enabling [session.use\_strict\_mode](https://www.php.net/manual/en/session.configuration.php#ini.session.use-strict-mode)
is recommended for all sites.


**Warning**

Immediate session deletion may cause unwanted results. When there is
concurrent requests, other connections may see sudden session data
loss. e.g. Requests from JavaScript and/or requests from URL links.


Although current session module does not accept empty session ID
cookie, but immediate session deletion may result in empty session ID
cookie due to client(browser) side race condition. This will result
that the client creates many session ID needlessly.


To avoid these, you must set deletion time-stamp to $\_SESSION and
reject access while later. Or make sure your application does not
have concurrent requests. This applies to [session\_regenerate\_id()](https://www.php.net/manual/en/function.session-regenerate-id.php) also.


### Parameters [¶](https://www.php.net/manual/en/function.session-destroy.php\#refsect1-function.session-destroy-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/function.session-destroy.php\#refsect1-function.session-destroy-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/function.session-destroy.php\#refsect1-function.session-destroy-examples)

**Example #1 Destroying a session with [$\_SESSION](https://www.php.net/manual/en/reserved.variables.session.php)**

`<?php
// Initialize the session.
// If you are using session_name("something"), don't forget it now!
session_start();
// Unset all of the session variables.
$_SESSION = array();
// If it's desired to kill the session, also delete the session cookie.
// Note: This will destroy the session, and not just the session data!
if (ini_get("session.use_cookies")) {
    $params = session_get_cookie_params();
    setcookie(session_name(), '', time() - 42000,
        $params["path"], $params["domain"],
        $params["secure"], $params["httponly"]
    );
}
// Finally, destroy the session.
session_destroy();
?>`

### See Also [¶](https://www.php.net/manual/en/function.session-destroy.php\#refsect1-function.session-destroy-seealso)

- [session.use\_strict\_mode](https://www.php.net/manual/en/session.configuration.php#ini.session.use-strict-mode)
- [session\_reset()](https://www.php.net/manual/en/function.session-reset.php) \- Re-initialize session array with original values
- [session\_regenerate\_id()](https://www.php.net/manual/en/function.session-regenerate-id.php) \- Update the current session id with a newly generated one
- [unset()](https://www.php.net/manual/en/function.unset.php) \- unset a given variable
- [setcookie()](https://www.php.net/manual/en/function.setcookie.php) \- Send a cookie

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/session/functions/session-destroy.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.session-destroy%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.session-destroy&repo=en&redirect=https://www.php.net/manual/en/function.session-destroy.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=110043&page=function.session-destroy&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110043&page=function.session-destroy&vote=down "Vote down!")

54


[**_Praveen V_**](https://www.php.net/manual/en/function.session-destroy.php#110043) [¶](https://www.php.net/manual/en/function.session-destroy.php#110043)

**13 years ago**

`If you want to change the session id on each log in, make sure to use session_regenerate_id(true) during the log in process.
<?php
session_start();
session_regenerate_id(true);
?>
[Edited by moderator (googleguy at php dot net)]`

[up](https://www.php.net/manual/vote-note.php?id=114709&page=function.session-destroy&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114709&page=function.session-destroy&vote=down "Vote down!")

20


[**_Jack Luo_**](https://www.php.net/manual/en/function.session-destroy.php#114709) [¶](https://www.php.net/manual/en/function.session-destroy.php#114709)

**11 years ago**

`It took me a while to figure out how to destroy a particular session in php. Note I'm not sure if solution provided below is perfect but it seems work for me. Please feel free to post any easier way to destroy a particular session. Because it's quite useful for functionality of force an user offline.
1. If you're using db or memcached to manage session, you can always delete that session entry directly from db or memcached.
2. Using generic php session methods to delete a particular session(by session id).
<?php
$session_id_to_destroy = 'nill2if998vhplq9f3pj08vjb1';
// 1. commit session if it's started.
if (session_id()) {
    session_commit();
}
// 2. store current session id
session_start();
$current_session_id = session_id();
session_commit();
// 3. hijack then destroy session specified.
session_id($session_id_to_destroy);
session_start();
session_destroy();
session_commit();
// 4. restore current session id. If don't restore it, your current session will refer to the session you just destroyed!
session_id($current_session_id);
session_start();
session_commit();
?>`

[up](https://www.php.net/manual/vote-note.php?id=130441&page=function.session-destroy&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130441&page=function.session-destroy&vote=down "Vote down!")

0


[**_mavudurumuralik at hotmail dot com_**](https://www.php.net/manual/en/function.session-destroy.php#130441) [¶](https://www.php.net/manual/en/function.session-destroy.php#130441)

**2 months ago**

`I have provided a solution to avoid opening of pages directly through url without entering login page.. hope this serves the purpose.
session_start();
if (!isset($_POST['loginid']) && !isset($_SESSION['loginid']))
    echo "<script language=javascript>{alert('Please Log in..'); window.open('index.php','_parent')}</script>";`

[up](https://www.php.net/manual/vote-note.php?id=129863&page=function.session-destroy&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129863&page=function.session-destroy&vote=down "Vote down!")

 -2


[**_vitas dot lowang at gmail dot com_**](https://www.php.net/manual/en/function.session-destroy.php#129863) [¶](https://www.php.net/manual/en/function.session-destroy.php#129863)

**10 months ago**

`I found out that in order to really have the session data cleared after calling session_destroy(), you need to refresh the page. For example by calling
header('Location: '.$_SERVER['PHP_SELF']."?page=profile");
if you don't then there are still data in $_SESSION which was there before. I don't know if this is intended behavior but it's kind of confusing IMO...`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.session-destroy&repo=en&redirect=https://www.php.net/manual/en/function.session-destroy.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google