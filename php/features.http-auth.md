---
url: https://www.php.net/manual/en/features.http-auth.php
scraped_at: 2025-10-20T02:34:19.238Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# HTTP authentication with PHP [¶](https://www.php.net/manual/en/features.http-auth.php\#features.http-auth)

It is possible to use the
[header()](https://www.php.net/manual/en/function.header.php) function to send an `"Authentication Required"`
message to the client browser causing it to pop up a Username/Password
input window. Once the user has filled in a username and a password,
the URL containing the PHP script will be called again with the
[predefined variables](https://www.php.net/manual/en/reserved.variables.php) PHP\_AUTH\_USER, PHP\_AUTH\_PW,
and AUTH\_TYPE set to the user name, password and
authentication type respectively. These predefined variables are found
in the [$\_SERVER](https://www.php.net/manual/en/reserved.variables.server.php) array. _Only_
the "Basic" authentication method is supported. See the
[header()](https://www.php.net/manual/en/function.header.php) function for more information.


An example script fragment which would force client authentication
on a page is as follows:


**Example #1 Basic HTTP Authentication example**

`<?php
if (!isset($_SERVER['PHP_AUTH_USER'])) {
    header('WWW-Authenticate: Basic realm="My Realm"');
    header('HTTP/1.0 401 Unauthorized');
    echo 'Text to send if user hits Cancel button';
    exit;
} else {
    echo "<p>Hello {$_SERVER['PHP_AUTH_USER']}.</p>";
    echo "<p>You entered {$_SERVER['PHP_AUTH_PW']} as your password.</p>";
}
?>`

> **Note**:
> **Compatibility Note**
>
> Please be careful when coding the HTTP header lines. In order to guarantee maximum
> compatibility with all clients, the keyword "Basic" should be written with an
> uppercase "B", the realm string must be enclosed in double (not single) quotes,
> and exactly one space should precede the _401_ code in the
> _HTTP/1.0 401_ header line. Authentication parameters have
> to be comma-separated.

Instead of simply printing out PHP\_AUTH\_USER
and PHP\_AUTH\_PW, as done in the above example,
you may want to check the username and password for validity.
Perhaps by sending a query to a database, or by looking up the
user in a dbm file.


Watch out for buggy Internet Explorer browsers out there. They
seem very picky about the order of the headers. Sending the
_WWW-Authenticate_ header before the
`HTTP/1.0 401` header seems to do the trick
for now.


> **Note**:
> **Configuration Note**
>
> PHP uses the presence of an `AuthType` directive
> to determine whether external authentication is in effect.

Note, however, that the above does not prevent someone who
controls a non-authenticated URL from stealing passwords from
authenticated URLs on the same server.


Both Netscape Navigator and Internet Explorer will clear the local browser
window's authentication cache for the realm upon receiving a
server response of 401. This can effectively "log out" a user,
forcing them to re-enter their username and password. Some people
use this to "time out" logins, or provide a "log-out" button.


**Example #2 HTTP Authentication example forcing a new name/password**

`<?php
function authenticate() {
    header('WWW-Authenticate: Basic realm="Test Authentication System"');
    header('HTTP/1.0 401 Unauthorized');
    echo "You must enter a valid login ID and password to access this resource\n";
    exit;
}

if (!isset($_SERVER['PHP_AUTH_USER']) ||
    ($_POST['SeenBefore'] == 1 && $_POST['OldAuth'] == $_SERVER['PHP_AUTH_USER'])) {
    authenticate();
} else {
    echo "<p>Welcome: " . htmlspecialchars($_SERVER['PHP_AUTH_USER']) . "<br />";
    echo "Old: " . htmlspecialchars($_REQUEST['OldAuth']);
    echo "<form action='' method='post'>\n";
    echo "<input type='hidden' name='SeenBefore' value='1' />\n";
    echo "<input type='hidden' name='OldAuth' value=\"" . htmlspecialchars($_SERVER['PHP_AUTH_USER']) . "\" />\n";
    echo "<input type='submit' value='Re Authenticate' />\n";
    echo "</form></p>\n";
}
?>`

This behavior is not required by the `HTTP Basic`
authentication standard, so you should never depend on this. Testing with
`Lynx` has shown that `Lynx` does not clear
the authentication credentials with a 401 server response, so pressing back
and then forward again will open the resource as long as the credential
requirements haven't changed. The user can press the
`'_'` key to clear their authentication information, however.


In order to get HTTP Authentication to work using IIS server with the CGI version
of PHP you must edit your IIS configuration " `Directory Security`".
Click on " `Edit`" and only check
" `Anonymous Access`", all other fields
should be left unchecked.


> **Note**:
> **IIS Note:**
>
> For HTTP Authentication to work with IIS, the PHP directive
> [cgi.rfc2616\_headers](https://www.php.net/manual/en/ini.core.php#ini.cgi.rfc2616-headers) must
> be set to `0` (the default value).

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/features/http-auth.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffeatures.http-auth%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=features.http-auth&repo=en&redirect=https://www.php.net/manual/en/features.http-auth.php)

### User Contributed Notes 46 notes

[up](https://www.php.net/manual/vote-note.php?id=114877&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114877&page=features.http-auth&vote=down "Vote down!")

76


[**_derkontrollfreak+9hy5l at gmail dot com_**](https://www.php.net/manual/en/features.http-auth.php#114877) [¶](https://www.php.net/manual/en/features.http-auth.php#114877)

**11 years ago**

`Workaround for missing Authorization header under CGI/FastCGI Apache:
SetEnvIf Authorization .+ HTTP_AUTHORIZATION=$0
Now PHP should automatically declare $_SERVER[PHP_AUTH_*] variables if the client sends the Authorization header.`

[up](https://www.php.net/manual/vote-note.php?id=73386&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73386&page=features.http-auth&vote=down "Vote down!")

69


[**_webmaster at kratia dot com_**](https://www.php.net/manual/en/features.http-auth.php#73386) [¶](https://www.php.net/manual/en/features.http-auth.php#73386)

**18 years ago**

`This is the simplest form I found to do a Basic authorization with retries.
<?php
$valid_passwords = array ("mario" => "carbonell");
$valid_users = array_keys($valid_passwords);
$user = $_SERVER['PHP_AUTH_USER'];
$pass = $_SERVER['PHP_AUTH_PW'];
$validated = (in_array($user, $valid_users)) && ($pass == $valid_passwords[$user]);
if (!$validated) {
header('WWW-Authenticate: Basic realm="My Realm"');
header('HTTP/1.0 401 Unauthorized');
die ("Not authorized");
}
// If arrives here, is a valid user.
echo "<p>Welcome $user.</p>";
echo "<p>Congratulation, you are into the system.</p>";
?>`

[up](https://www.php.net/manual/vote-note.php?id=76708&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=76708&page=features.http-auth&vote=down "Vote down!")

28


[**_gbelyh at gmail dot com_**](https://www.php.net/manual/en/features.http-auth.php#76708) [¶](https://www.php.net/manual/en/features.http-auth.php#76708)

**18 years ago**

`Back to the autherisation in CGI mode. this is the full working example:
#  Create the .htaccess file with following contents:
# also you can use the condition (search at this page)
RewriteEngine on
RewriteRule .* - [E=REMOTE_USER:%{HTTP:Authorization},L]
# In the beginning the script checking the authorization place the code:
$userpass = base64_decode(substr($_SERVER["REDIRECT_REMOTE_USER"],6)) ;
$userpass = explode(":", $userpass);
if (  count($userpass) == 2  ){
     #this part work not for all.
     #print_r($userpass);die; #<- this can help find out right username and password
     list($name, $password) = explode(':', $userpass);
     $_SERVER['PHP_AUTH_USER'] = $name;
     $_SERVER['PHP_AUTH_PW'] = $password;
}`

[up](https://www.php.net/manual/vote-note.php?id=108132&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=108132&page=features.http-auth&vote=down "Vote down!")

34


[**_kazakevichilya at gmail dot com_**](https://www.php.net/manual/en/features.http-auth.php#108132) [¶](https://www.php.net/manual/en/features.http-auth.php#108132)

**13 years ago**

`In case of CGI/FastCGI you would hot be able to access PHP_AUTH* info because CGI protocol does not declare such variables (that is why their names start from PHP) and server would not pass them to the interpreter. In CGI server should authenticate user itself and pass REMOTE_USER to CGI script after it.
So you need to "fetch" request headers and pass them to your script somehow.
In apache you can do it via environment variables if mod_env is installed.
Following construction in .htaccess copies request header "Authorization" to the env variable PHP_AUTH_DIGEST_RAW
SetEnvIfNoCase ^Authorization$ "(.+)" PHP_AUTH_DIGEST_RAW=$1
You can now access it via $_ENV.
Do not forget to strip auth type ("Digest" in my case) from your env variable because PHP_AUTH_DIGEST does not have it.
If mod_env is not installed you probably have mod_rewrite (everyone has it because of "human readable URLs").
You can fetch header and pass it as GET parameter using rewrite rule:
RewriteRule ^.*$ site.php?PHP_AUTH_DIGEST_RAW=%{HTTP:Authorization} [NC,L]
Here HTTP request header Authorization would be acessible as PHP_AUTH_DIGEST_RAW via $_GET.
---
If you use ZF you probably use Zend_Auth_Adapter_Http to auth user.
It takes Authorization info using "Zend_Controller_Request::getHeader"
This method uses apache_request_header which is likely not to be accessible in old CGI/FastCGI installations or _$_SERVER['HTTP_<HeaderName>] , so you need to put your authentication data, obtained via _GET or ENV to
_$_SERVER['HTTP_AUTHORIZATION'].
It will make ZF work transparently with you solution and I believe any other framework should work also`

[up](https://www.php.net/manual/vote-note.php?id=126030&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126030&page=features.http-auth&vote=down "Vote down!")

20


[**_bitman at bitworks dot de_**](https://www.php.net/manual/en/features.http-auth.php#126030) [¶](https://www.php.net/manual/en/features.http-auth.php#126030)

**4 years ago**

`the alternative text should contain the complete text af a (small) valid HTML-Ressource.  It also can contain link relations to CSS.`

[up](https://www.php.net/manual/vote-note.php?id=107642&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107642&page=features.http-auth&vote=down "Vote down!")

21


[**_vog at notjusthosting dot com_**](https://www.php.net/manual/en/features.http-auth.php#107642) [¶](https://www.php.net/manual/en/features.http-auth.php#107642)

**13 years ago**

`You shouldn't use the "last" ("L") directive in the RewriteRule! This will prevent all further rewrite rules to be skipped whenever a Basic or Digest Auth is given, which is almost certainly not what you want.
So the following lines are sufficient for the .htaccess (or httpd.conf) file:
RewriteEngine On
RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]`

[up](https://www.php.net/manual/vote-note.php?id=70305&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70305&page=features.http-auth&vote=down "Vote down!")

24


[**_roychri at php dot net_**](https://www.php.net/manual/en/features.http-auth.php#70305) [¶](https://www.php.net/manual/en/features.http-auth.php#70305)

**19 years ago**

`For PHP with CGI, make sure you put the rewrite rule above any other rewrite rule you might have.
In my case, I put this at the top of the .htaccess (below RewriteEngine On):
RewriteRule .* - [E=REMOTE_USER:%{HTTP:Authorization}]
My symptom was that the REMOTE_USER (or REDIRECT_REMOTE_USER in my case) was not being set at all.
The cause: I had some other RewriteRule that was kickin in and was set as LAST rule.
I hope this helps.`

[up](https://www.php.net/manual/vote-note.php?id=93427&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93427&page=features.http-auth&vote=down "Vote down!")

21


[**_Anonymous_**](https://www.php.net/manual/en/features.http-auth.php#93427) [¶](https://www.php.net/manual/en/features.http-auth.php#93427)

**16 years ago**

`The regex in http_digest_parse from Example #2 does not work for me (PHP 5.2.6), because back references are not allowed in a character class.  This worked for me:
<?php
// function to parse the http auth header
function http_digest_parse($txt)
{
// protect against missing data
$needed_parts = array('nonce'=>1, 'nc'=>1, 'cnonce'=>1, 'qop'=>1, 'username'=>1, 'uri'=>1, 'response'=>1);
$data = array();
preg_match_all('@(\w+)=(?:(?:\'([^\']+)\'|"([^"]+)")|([^\s,]+))@', $txt, $matches, PREG_SET_ORDER);
foreach ($matches as $m) {
       $data[$m[1]] = $m[2] ? $m[2] : ($m[3] ? $m[3] : $m[4]);
       unset($needed_parts[$m[1]]);
}
return $needed_parts ? false : $data;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=52405&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=52405&page=features.http-auth&vote=down "Vote down!")

23


[**_charly at towebs dot com_**](https://www.php.net/manual/en/features.http-auth.php#52405) [¶](https://www.php.net/manual/en/features.http-auth.php#52405)

**20 years ago**

`A simpler approach on the post of:
bernard dot paques at bigfoot dot com
24-Sep-2004 01:42
This is another "patch" to the PHP_AUTH_USER and PHP_AUTH_PW server variables problem running PHP as a CGI.
First of all don't forget this fragment of code in your .htaccess (it's the only thing you need to make it work with mod_rewrite):
<IfModule mod_rewrite.c>
RewriteEngine on
RewriteRule .* - [E=REMOTE_USER:%{HTTP:Authorization},L]
</IfModule>
Then login.php
<?php
$a = base64_decode( substr($_SERVER["REMOTE_USER"],6)) ;
if ( (strlen($a) == 0) || ( strcasecmp($a, ":" )  == 0 ))
{
header( 'WWW-Authenticate: Basic realm="Private"' );
header( 'HTTP/1.0 401 Unauthorized' );
}
else
{
list($name, $password) = explode(':', $a);
$_SERVER['PHP_AUTH_USER'] = $name;
$_SERVER['PHP_AUTH_PW']    = $password;
}
echo 'PHP_AUTH_USER =' . $_SERVER['PHP_AUTH_USER'] . '<br>';
echo 'PHP_AUTH_PW =' . $_SERVER['PHP_AUTH_PW'] . '<br>';
echo 'REMOTE_USER =' . $_SERVER['REMOTE_USER'] . '<br>';
?>
First, we decode the base64 encoded string discarding the first 6 characters of "Basic " and then we do a regular validation.
At the end of the script we print the variables to verify it's working. This should be ommited in the production version.
It's a variation of the script by Bernard Paques.
Thanks to him for that snippet.`

[up](https://www.php.net/manual/vote-note.php?id=44686&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=44686&page=features.http-auth&vote=down "Vote down!")

24


[**_php at cscott dot net_**](https://www.php.net/manual/en/features.http-auth.php#44686) [¶](https://www.php.net/manual/en/features.http-auth.php#44686)

**21 years ago**

`Note that Microsoft has released a 'security update' which disables the use of username:password@host in http urls.
[http://support.microsoft.com/default.aspx?scid=kb;en-us;834489](http://support.microsoft.com/default.aspx?scid=kb;en-us;834489)
The methods described above which rely on this will no longer work in Microsoft browsers, sadly.
You can re-enable this functionality as described at
[http://weblogs.asp.net/cumpsd/archive/2004/02/07/69366.aspx](http://weblogs.asp.net/cumpsd/archive/2004/02/07/69366.aspx)
but your users will probably be unwilling to do this.`

[up](https://www.php.net/manual/vote-note.php?id=73642&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=73642&page=features.http-auth&vote=down "Vote down!")

24


[**_Nicolas Merlet - admin(at)merletn.org_**](https://www.php.net/manual/en/features.http-auth.php#73642) [¶](https://www.php.net/manual/en/features.http-auth.php#73642)

**18 years ago**

`Be careful using http digest authentication (see above, example 34.2) if you have to use the 'setlocale' function *before* validating response with the 'http_digest_parse' function, because there's a conflict with \w in the pattern of 'preg_match_all' function :
In fact, as \w is supposed to be any letter or digit or the underscore character, you must not forgot that this may vary depending on your locale configuration (eg. it accepts accented letters in french)...
Due to this different pattern interpretation by the 'preg_match_all' function, the 'http_digest_parse' function will always return a false result if you have modified your locale (I mean if your locale accepts some extended characters, see [http://fr.php.net/manual/en/reference.pcre.pattern.syntax.php](http://fr.php.net/manual/en/reference.pcre.pattern.syntax.php) for further information).
IMHO, I suggest you not to use setlocale before having your authentication completed...
PS : Here's a non-compatible setlocale declaration...
setlocale ( LC_ALL, 'fr_FR', 'fr', 'FR', 'french', 'fra', 'france', 'French', 'fr_FR.ISO8859-1' ) ;`

[up](https://www.php.net/manual/vote-note.php?id=110219&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110219&page=features.http-auth&vote=down "Vote down!")

25


[**_xsanychx at mail dot ru_**](https://www.php.net/manual/en/features.http-auth.php#110219) [¶](https://www.php.net/manual/en/features.http-auth.php#110219)

**13 years ago**

`New auth:
<?php
$login = 'test_login';
$pass = 'test_pass';
if(($_SERVER['PHP_AUTH_PW']!= $pass || $_SERVER['PHP_AUTH_USER'] != $login)|| !$_SERVER['PHP_AUTH_USER'])
{
    header('WWW-Authenticate: Basic realm="Test auth"');
    header('HTTP/1.0 401 Unauthorized');
    echo 'Auth failed';
    exit;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=118359&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118359&page=features.http-auth&vote=down "Vote down!")

21


[**_john\_2232 at gmail dot com_**](https://www.php.net/manual/en/features.http-auth.php#118359) [¶](https://www.php.net/manual/en/features.http-auth.php#118359)

**9 years ago**

`Here is my attempt to create a digest authentication class that will log the user in and out without using a cookie,session,db,or file. At the core is this simple code to parse the digest string into variables works for several browsers.
<?php
// explode the digest with multibrowser support by Tony Wyatt 21jun07
public function explodethedigest($instring) {
$quote = '"';
$equal = '=';
$comma = ',';
$space = ' ';
$a = explode( $comma, $instring);
$ax = explode($space, $a[0]);
$b = explode( $equal, $ax[1], 2);
$c = explode( $equal, $a[1], 2);
$d = explode( $equal, $a[2], 2);
$e = explode( $equal, $a[3], 2);
$f = explode( $equal, $a[4], 2);
$g = explode( $equal, $a[5], 2);
$h = explode( $equal, $a[6], 2);
$i = explode( $equal, $a[7], 2);
$j = explode( $equal, $a[8], 2);
$k = explode( $equal, $a[9], 2);
$l = explode( $equal, $a[10], 2);
$parts = array(trim($b[0])=>trim($b[1], '"'), trim($c[0])=>trim($c[1], '"'), trim($d[0])=>trim($d[1], '"'), trim($e[0])=>trim($e[1], '"'), trim($f[0])=>trim($f[1], '"'), trim($g[0])=>trim($g[1], '"'), trim($h[0])=>trim($h[1], '"'), trim($i[0])=>trim($i[1], '"'), trim($j[0])=>trim($j[1], '"'), trim($k[0])=>trim($k[1], '"'), trim($l[0])=>trim($l[1], '"'));
return $parts;
}
?>
Give it a try at [http://www.creativetheory.ca/](http://www.creativetheory.ca/) /tests/ta1.php Log in with user test password pass or user guest password guest. Go to page two for links to the code. Comments, ideas, suggestions, or critique welcome.`

[up](https://www.php.net/manual/vote-note.php?id=18618&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=18618&page=features.http-auth&vote=down "Vote down!")

19


[**_sjeffrey at inquesis dot com_**](https://www.php.net/manual/en/features.http-auth.php#18618) [¶](https://www.php.net/manual/en/features.http-auth.php#18618)

**23 years ago**

`To get it to work with IIS try using this code before setting your "$auth = 0" and the "if (isset($PHP_AUTH_USER) && isset($PHP_AUTH_PW))"
<?php
//////////////////////////////////////////
if ($PHP_AUTH_USER == "" && $PHP_AUTH_PW == "" && ereg("^Basic ", $HTTP_AUTHORIZATION))
{
list($PHP_AUTH_USER, $PHP_AUTH_PW) =
    explode(":", base64_decode(substr($HTTP_AUTHORIZATION, 6)));
}
//////////////////////////////////////////
?>
It worked for me on IIS 5 and PHP 4 in ISAPI`

[up](https://www.php.net/manual/vote-note.php?id=118088&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118088&page=features.http-auth&vote=down "Vote down!")

22


[**_jake22 at gmail dot com_**](https://www.php.net/manual/en/features.http-auth.php#118088) [¶](https://www.php.net/manual/en/features.http-auth.php#118088)

**10 years ago**

`I came up with another approach to work around the problem of browsers caching WWW authentication credentials and creating logout problems. While most browsers have some kind of way to wipe this information, I prefer having my website to take care of the task instead of relying on the user's sanity.
Even with Lalit's method of creating a random realm name, it was still possible to get back into the protected area using the back button in Firefox, so that didn't work. Here's my solution:
Since browsers attach the credentials to specific URLs, use virtual paths where a component of the path is actually a PHP script, and everything following it is part of the URI, such as:
[http://velocitypress.ca/some\_dir/login.php/auth/8f631b92/](http://velocitypress.ca/some_dir/login.php/auth/8f631b92/)
By choosing a different number for the last component of the URL, browsers can be tricked into thinking that they are dealing with a completely different website, and thus prompting the user for credentials again.
Note that using a random, unrestricted number will still allow the user to hit the back button to get back into the page. You should keep track of this number in a server-side file or database and regenerate it upon each successful login, so that the last number(s) become invalid. Using an invalid number might result in a 403 response or, depending on how you feel that day, a 302 to a nasty website.
Care should be taken when linking from the page generated in this case, since relative links will be relative to the virtual and non-existant directory rather than the true script directory.`

[up](https://www.php.net/manual/vote-note.php?id=121898&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121898&page=features.http-auth&vote=down "Vote down!")

18


[**_Carlos_**](https://www.php.net/manual/en/features.http-auth.php#121898) [¶](https://www.php.net/manual/en/features.http-auth.php#121898)

**7 years ago**

`Simpler WorkAround for missing Authorization header under CGI/FastCGI available in Apache HTTP Server 2.4.13 and later
     CGIPassAuth On
Please don't enable Authorization header with Basic Authentication, is very insecure.`

[up](https://www.php.net/manual/vote-note.php?id=67146&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=67146&page=features.http-auth&vote=down "Vote down!")

23


[**_Louis_**](https://www.php.net/manual/en/features.http-auth.php#67146) [¶](https://www.php.net/manual/en/features.http-auth.php#67146)

**19 years ago**

`I couldn't get authentication to work properly with any of the examples. Finally, I started from ZEND's tutorial example at:
[http://www.zend.com/zend/tut/authentication.php?article=authentication](http://www.zend.com/zend/tut/authentication.php?article=authentication) (validate using .htpasswd) and tried to deal with the additional cases. My general conclusion is that changing the realm is the only reliable way to cause the browser to ask again, and I like to thank the person who put that example in the manual, as it got me on the right path. No matter what, the browser refuses to discard the values that it already has in mind otherwise. The problem with changing the realm, of course, is that you don't want to do it within a given session, else it causes a new request for a password. So, here goes, hopefully the spacing isn't too messed up by the cut'n'paste.
I spent the better part of a day getting this to work right. I had a very hard time thinking through what the browser does when it encounters an authentication request: seems to me that it tries to get the password, then reloads the page... so the HTML doesn't get run. At least, this was the case with IE, I haven't tested it with anything else.
<?php
session_start() ;
if (!isset($_SESSION['realm'])) {
        $_SESSION['realm'] = mt_rand( 1, 1000000000 ).
                " SECOND level: Enter your !!!COMPANY!!! password.";
        header( "WWW-Authenticate: Basic realm=".$_SESSION['realm'] );
        //  Below here runs HTML-wise only if there isn't a $_SESSION,
        // and the browser *can't* set $PHP_AUTH_USER... normally
        // the browser, having gotten the auth info, runs the page
        // again without getting here.
        //  What I'm basically getting to is that the way to get
        // here is to escape past the login screen. I tried
        // putting a session_destroy() here originally, but the
        // problem is that the PHP runs regardless, so the
        // REFRESH seems like the best way to deal with it.
        echo "<meta http-equiv=\"REFRESH\"
                content=\"0;url=index.php\">" ;
        exit;
        }
if ($_POST['logout'] == "logout") {
        session_destroy() ;
        header('Location: comeagain.php');
        exit ;
        }
// "standard" authentication code here, from the ZEND tutorial above.
comeagain.php is as follows:
<?
session_start();
unset($_SESSION['realm']);
session_destroy();
echo "<html><head><title>Logged Out</title><h1>Logout Page</h1><body>" ;
echo "You have successfully logged out of TOGEN";
echo " at ".date("h:m:s")." on ".date("d F Y") ;
echo "<p><a href=\"index.php\">Login Again</a>" ;
echo "</body></html>" ;
?>
The idea is to be able to trash the session (and thus reset the realm) without prompting the browser to ask again... because it has been redirected to logout.php.
With this combination, I get things to work. Just make sure not to have apache run htpasswd authentication at the same time, then things get really weird :-).`

[up](https://www.php.net/manual/vote-note.php?id=28491&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=28491&page=features.http-auth&vote=down "Vote down!")

18


[**_emmanuel dot keller at net2000 dot ch_**](https://www.php.net/manual/en/features.http-auth.php#28491) [¶](https://www.php.net/manual/en/features.http-auth.php#28491)

**22 years ago**

`Some servers won't support the HTTP1.0 specification and will give an error 500 (for instance). This happened with a server where I uploaded an authentication script.
If it happens, you can try the HTTP1.1 header syntax :
<?php
header("WWW-Authenticate: Basic realm=\"My Realm\"");
header('status: 401 Unauthorized');
?>`

[up](https://www.php.net/manual/vote-note.php?id=42372&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=42372&page=features.http-auth&vote=down "Vote down!")

12


[**_nuno at mail dot ideianet dot pt_**](https://www.php.net/manual/en/features.http-auth.php#42372) [¶](https://www.php.net/manual/en/features.http-auth.php#42372)

**21 years ago**

`In Windows 2003 Server/IIS6 with the php4+ cgi I only get HTTP authentication working with:
<?php header("Status: 401 Access Denied"); ?>
with
<?php header('HTTP/1.0 401 Unauthorized'); ?>
doesn't work !
I also need in "Custom Errors" to select the range of "401;1" through "401;5" and click the "Set to Default" button.
Thanks rob at theblip dot com`

[up](https://www.php.net/manual/vote-note.php?id=70693&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70693&page=features.http-auth&vote=down "Vote down!")

21


[**_SlamJam_**](https://www.php.net/manual/en/features.http-auth.php#70693) [¶](https://www.php.net/manual/en/features.http-auth.php#70693)

**18 years ago**

`I used Louis example (03-Jun-2006) and it works well for me (thanks).
However, I added some lines, to make sure, the user does only get the Authentification-Window a few times:
<?php
$realm = mt_rand( 1, 1000000000)."@YourCompany";
$_SESSION['realm'] = $realm;
// In the beginning, when the realm ist defined:
$_SESSION['CountTrials'] = 1;
?>
And then when it comes to check the authentification (ZEND-Tutorial):
<?php
// Not more than 3 Trials
if (!$auth) {
$_SESSION['CountTrials']++;
if ($_SESSION['CountTrials'] == 4) {
       session_destroy() ;
       header('Location: noentry.php');
       exit ;
} else {
       header("WWW-Authenticate: Basic realm=".$_SESSION['realm']);
       header("HTTP/1.0 401 Unauthorized");
       echo 'Authorization Required.';
       exit;
}
} else {
         echo '<P>You are authorized!</P>';
}
?>
noentry.php is slightely different from comeagain.php.`

[up](https://www.php.net/manual/vote-note.php?id=88957&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88957&page=features.http-auth&vote=down "Vote down!")

25


[**_Yuriy_**](https://www.php.net/manual/en/features.http-auth.php#88957) [¶](https://www.php.net/manual/en/features.http-auth.php#88957)

**16 years ago**

`Good day.
Sorry for my english.
This example shows programming "LOGIN", "LOGOUT" and "RE-LOGIN".
This script must use in the protected pages.
For work this script the browser address string must be following:
" [http://localhost/admin/?login](http://localhost/admin/?login)" - for Login,
" [http://localhost/admin/?logout](http://localhost/admin/?logout)" - for Logout,
" [http://localhost/admin/?logout&login](http://localhost/admin/?logout&login)" - for Re-Login.
<?php
session_start();
$authorized = false;
# LOGOUT
if (isset($_GET['logout']) && !isset($_GET["login"]) && isset($_SESSION['auth']))
{
    $_SESSION = array();
    unset($_COOKIE[session_name()]);
    session_destroy();
    echo "logging out...";
}
# checkup login and password
if (isset($_SERVER['PHP_AUTH_USER']) && isset($_SERVER['PHP_AUTH_PW']))
{
    $user = 'test';
    $pass = 'test';
    if (($user == $_SERVER['PHP_AUTH_USER']) && ($pass == ($_SERVER['PHP_AUTH_PW'])) && isset($_SESSION['auth']))
    {
    $authorized = true;
    }
}
# login
if (isset($_GET["login"]) && !$authorized ||
# relogin
    isset($_GET["login"]) && isset($_GET["logout"]) && !isset($_SESSION['reauth']))
{
    header('WWW-Authenticate: Basic Realm="Login please"');
    header('HTTP/1.0 401 Unauthorized');
    $_SESSION['auth'] = true;
    $_SESSION['reauth'] = true;
    echo "Login now or forever hold your clicks...";
    exit;
}
$_SESSION['reauth'] = null;
?>
<h1>you have <? echo ($authorized) ? (isset($_GET["login"]) && isset($_GET["logout"]) ? 're' : '') : 'not '; ?>logged!</h1>`

[up](https://www.php.net/manual/vote-note.php?id=70864&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70864&page=features.http-auth&vote=down "Vote down!")

23


[**_admin at isprohosting dot com_**](https://www.php.net/manual/en/features.http-auth.php#70864) [¶](https://www.php.net/manual/en/features.http-auth.php#70864)

**18 years ago**

`There are .htaccess which actually works for us (cPanel + phpsuexec) unless others failed. Perhaps it may help someone.
# PHP (CGI mode) HTTP Authorization with ModRewrite:
RewriteEngine on
RewriteCond %{HTTP:Authorization} ^(.*)
RewriteRule ^(.*) - [E=HTTP_AUTHORIZATION:%1]
Then you need small piece of php code to parse this line and then everything will work like with mod_php:
if (isset($_SERVER['HTTP_AUTHORIZATION']))
{
$ha = base64_decode( substr($_SERVER['HTTP_AUTHORIZATION'],6) );
list($_SERVER['PHP_AUTH_USER'], $_SERVER['PHP_AUTH_PW']) = explode(':', $ha);
unset $ha;
}
Enjoy!`

[up](https://www.php.net/manual/vote-note.php?id=96970&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96970&page=features.http-auth&vote=down "Vote down!")

21


[**_Ome Ko_**](https://www.php.net/manual/en/features.http-auth.php#96970) [¶](https://www.php.net/manual/en/features.http-auth.php#96970)

**15 years ago**

`a link to [http://logout:logout@](http://logout:logout@/) <?=$_SERVER['HTTP_HOST'];?>/SECRET/ would force a fresh login for the /SECRET directory if no user logout with password logout exists.
[NOTE BY danbrown AT php DOT net: The following note was added by "Anonymous" on 01-APR-2010 (though we presume it's not an April Fool's Day joke).]
this logout method does not work 100% anymore, because of another bulls**t from M$:
[http://support.microsoft.com/kb/834489](http://support.microsoft.com/kb/834489)`

[up](https://www.php.net/manual/vote-note.php?id=118089&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118089&page=features.http-auth&vote=down "Vote down!")

16


[**_dan223 at gmail dot com_**](https://www.php.net/manual/en/features.http-auth.php#118089) [¶](https://www.php.net/manual/en/features.http-auth.php#118089)

**10 years ago**

`A simple script for SSL Client Certificate authentication with a basic authentication fall-back. I use this on my site using LDAP server to check username/passwords and client certificate to user mapping.
<?
// Check if and how we are authenticated
if ($_SERVER['SSL_CLIENT_VERIFY'] != "SUCCESS") { // Not using a client certificate
    if ((!$_SERVER['PHP_AUTH_USER']) && (!$_SERVER['PHP_AUTH_PW'])) { // Not logged in using basic authentication
        authenticate(); // Send basic authentication headers
    }
}
if ($_SERVER['SSL_CLIENT_S_DN_CN'] != "chris") { // Check CN name of cert
    if (!(($_SERVER['PHP_AUTH_USER'] == "test") && ($_SERVER['PHP_AUTH_PW'] == "123"))) { // Check username and password
        authenticate(); // Send basic authentication headers because username and/or password didnot match
    }
}
phpinfo();
// Call authentication display
function authenticate() {
    Header("WWW-Authenticate: Basic realm=Website");
        Header("HTTP/1.0 401 Unauthorized");
        error401();
        exit;
}
?>
See my website ( [http://velocitypress.ca/index.php?page=/manuals/](http://velocitypress.ca/index.php?page=/manuals/)) for more details on client certificate with Apache and PHP.`

[up](https://www.php.net/manual/vote-note.php?id=117415&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117415&page=features.http-auth&vote=down "Vote down!")

20


[**_sergio dot carvalho at gmail dot com_**](https://www.php.net/manual/en/features.http-auth.php#117415) [¶](https://www.php.net/manual/en/features.http-auth.php#117415)

**10 years ago**

`The only effective way I've found to wipe out the PHP_AUTH_DIGEST or PHP_AUTH_USER AND PHP_AUTH_PW credentials is to call the header HTTP/1.1 401 Unauthorized.
function clear_admin_access(){
    header('HTTP/1.1 401 Unauthorized');
    die('Admin access turned off');
}`

[up](https://www.php.net/manual/vote-note.php?id=106285&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=106285&page=features.http-auth&vote=down "Vote down!")

17


[**_h3ndrik_**](https://www.php.net/manual/en/features.http-auth.php#106285) [¶](https://www.php.net/manual/en/features.http-auth.php#106285)

**13 years ago**

`On my configuration with php-cgi - after setting the RewriteRule - the correct variable would be: $_SERVER['REDIRECT_HTTP_AUTHORIZATION']
So the workaround for PhpCGI is:
Set in your .htaccess:
RewriteEngine on
RewriteRule .* - [env=HTTP_AUTHORIZATION:%{HTTP:Authorization},last]
Php workaround:
<?php
//set http auth headers for apache+php-cgi work around
if (isset($_SERVER['HTTP_AUTHORIZATION']) && preg_match('/Basic\s+(.*)$/i', $_SERVER['HTTP_AUTHORIZATION'], $matches)) {
    list($name, $password) = explode(':', base64_decode($matches[1]));
    $_SERVER['PHP_AUTH_USER'] = strip_tags($name);
    $_SERVER['PHP_AUTH_PW'] = strip_tags($password);
}
//set http auth headers for apache+php-cgi work around if variable gets renamed by apache
if (isset($_SERVER['REDIRECT_HTTP_AUTHORIZATION']) && preg_match('/Basic\s+(.*)$/i', $_SERVER['REDIRECT_HTTP_AUTHORIZATION'], $matches)) {
    list($name, $password) = explode(':', base64_decode($matches[1]));
    $_SERVER['PHP_AUTH_USER'] = strip_tags($name);
    $_SERVER['PHP_AUTH_PW'] = strip_tags($password);
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=114080&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114080&page=features.http-auth&vote=down "Vote down!")

19


[**_Robb\_Bean at gmx dot net_**](https://www.php.net/manual/en/features.http-auth.php#114080) [¶](https://www.php.net/manual/en/features.http-auth.php#114080)

**11 years ago**

`In the german example #2 (digest), the <?php $realm = "Geschützter Bereich"; ?>. As far as I have tested the umlaut ü is problematic, resulting in an password enter infinity loop. In my case it was written in UTF-8. So I suggest using only plain ASCII characters for the realm.`

[up](https://www.php.net/manual/vote-note.php?id=66468&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=66468&page=features.http-auth&vote=down "Vote down!")

14


[**_kembl at example dot com_**](https://www.php.net/manual/en/features.http-auth.php#66468) [¶](https://www.php.net/manual/en/features.http-auth.php#66468)

**19 years ago**

`# PHP (CGI mode) HTTP Authorization with ModRewrite:
# most right example with header check for non empty:
RewriteEngine on
RewriteCond %{HTTP:Authorization}  !^$
RewriteRule .* - [E=REMOTE_USER:%{HTTP:Authorization}, \\
E=PHP_AUTH_USER:%{HTTP:Authorization},L]`

[up](https://www.php.net/manual/vote-note.php?id=44745&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=44745&page=features.http-auth&vote=down "Vote down!")

14


[**_jason_**](https://www.php.net/manual/en/features.http-auth.php#44745) [¶](https://www.php.net/manual/en/features.http-auth.php#44745)

**21 years ago**

`on the php+mysql auth code by tigran at freenet dot am
There are some security weaknesses.
First
$user
and
$pass
are both insecure, they could leave this code open to SQL injection, you should always remove invalid characters in both, or at least encode them.
Actually storing passwords as MD5 hashes leaves you less work to secure.
Second security risks
The same mysql user has rights to both update and select, and possibly even insert and on your auth database no less.
Again the SQL inject attack may occur with this., and the end user could then change the users username, password, or anything else in relation to this.
Third items is more of a performance issue,

Do you really need to update the database, as updates are slower then selects, and if you do them every time they access the page, you are costing some speed penalty.
One option, if you want to use sql (I think mysql has it) is memory only databases, and create a table within memory, the stores a unique session identifier for each user, that is logged in, or alternatively if it's a single front end system, you could use db files.`

[up](https://www.php.net/manual/vote-note.php?id=126079&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126079&page=features.http-auth&vote=down "Vote down!")

12


[**_spam at angstzustaen dot de_**](https://www.php.net/manual/en/features.http-auth.php#126079) [¶](https://www.php.net/manual/en/features.http-auth.php#126079)

**4 years ago**

`public function loginUser(){
        $username = filter_var($_GET['username'],FILTER_SANITIZE_STRING);
        $pw = filter_var($_GET['pw'],FILTER_SANITIZE_STRING);
        $row = $this->userModel->selectUser($username);
       if (password_verify($pw,$row['pw'])){
           $_SESSION["userId"] = $row['id'];
           $this->isLogin();
       } else{
           new Msg(true,"Benutzername und Passwort stimmen nicht überein!");
       }
    }
A short example for an user Login`

[up](https://www.php.net/manual/vote-note.php?id=53962&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=53962&page=features.http-auth&vote=down "Vote down!")

13


[**_snagnever at gmail dot com_**](https://www.php.net/manual/en/features.http-auth.php#53962) [¶](https://www.php.net/manual/en/features.http-auth.php#53962)

**20 years ago**

`It forces a auth each time the page is accessed:
(maybe can save someone)
<?
header("Expires: Sat, 01 Jan 2000 00:00:00 GMT");
header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT");
header("Cache-Control: post-check=0, pre-check=0",false);
header("Pragma: no-cache");
session_cache_limiter("public, no-store");
session_start();
function http_auth()
{
    $_SESSION['AUTH'] = 1;
    header('HTTP/1.0 401 Unauthorized');
    header('WWW-Authenticate: Basic realm="sn4g auth system"');
    // The actions to be done when the user clicks on 'cancel'
    exit();
}
if( !isset($_SERVER['PHP_AUTH_USER']) or @$_SESSION['AUTH'] != 1 )
{
    http_auth();
    exit();
}
// Actions do be done when the user has logged
// rest, must clean the session array
$_SESSION = array();
session_destroy();
?>`

[up](https://www.php.net/manual/vote-note.php?id=100396&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100396&page=features.http-auth&vote=down "Vote down!")

22


[**_ceo at l-i-e dot com_**](https://www.php.net/manual/en/features.http-auth.php#100396) [¶](https://www.php.net/manual/en/features.http-auth.php#100396)

**15 years ago**

`To force a logout with Basic Auth, you can change the Realm out from under them to a different Realm.
This forces a new set of credentials for a new "Realm" on your server.
You just need to track the Realm name with the user/pass and change it around to something new/random as they log in and out.
I believe that this is the only 100% guaranteed way to get a logout in HTTP Basic Auth, and if it were part of the docs a whole lot of BAD user-contributed comments here could be deleted.`

[up](https://www.php.net/manual/vote-note.php?id=81049&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81049&page=features.http-auth&vote=down "Vote down!")

14


[**_Lars Stecken_**](https://www.php.net/manual/en/features.http-auth.php#81049) [¶](https://www.php.net/manual/en/features.http-auth.php#81049)

**17 years ago**

`To anybody who tried the digest example above and didn't get it to work.
For me the problem seemed to be the deprecated use of '\' (backslash) in the regex instead of the '$' (Dollar) to indicate a backreference. Also the results have to be trimmed off the remaining double and single quotes.
Here's the working example:
// function to parse the http auth header
function http_digest_parse($txt)
{

    // protect against missing data
    $needed_parts = array('nonce'=>1, 'nc'=>1, 'cnonce'=>1, 'qop'=>1, 'username'=>1, 'uri'=>1, 'response'=>1);
    $data = array();
    preg_match_all('@(\w+)=(?:([\'"])([^$2]+)$2|([^\s,]+))@', $txt, $matches, PREG_SET_ORDER);

    foreach ($matches as $m) {
        $data[$m[1]] = $m[3] ? trim($m[3],"\",'") : trim($m[4],"\",'");
        unset($needed_parts[$m[1]]);
    }

    return $needed_parts ? false : $data;
}
Probably there's a more sophisticated way to trim the quotes within the regex, but I couldn't be bothered :-)
Greets, Lars`

[up](https://www.php.net/manual/vote-note.php?id=60503&page=features.http-auth&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=60503&page=features.http-auth&vote=down "Vote down!")

12


[**_marco dot moser at oltrefersina dot it_**](https://www.php.net/manual/en/features.http-auth.php#60503) [¶](https://www.php.net/manual/en/features.http-auth.php#60503)

**19 years ago**

`I suggest to demand user's authentication and management to the web server (by .htaccess, ...):
1. configure a global /logon/ directory with a .htaccess file restricted access
2. use fopen wrapper:
$hh = @fopen(" [http://{$\_SERVER\[](http://{$_server[/)'PHP_AUTH_USER']}:{$_SERVER['PHP_AUTH_PW']}".\
    @{$_SERVER['SERVER_NAME']}/logon/", "r");\
if (!$hh) authenticate(); // usual header WWW-Authenticate ...\
fclose($hh);`\
\
[up](https://www.php.net/manual/vote-note.php?id=68088&page=features.http-auth&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=68088&page=features.http-auth&vote=down "Vote down!")\
\
12\
\
\
[**_web at kwi dot dk_**](https://www.php.net/manual/en/features.http-auth.php#68088) [¶](https://www.php.net/manual/en/features.http-auth.php#68088)\
\
**19 years ago**\
\
`While Digest authentication is still far superior to Basic authentication, there are a number of security issues that one must keep in mind.\
In this respect, the Digest example given above is somewhat flawed, because the nonce never times out or otherwise become invalid. It thus becomes a password-equivalent (although to that specific URL only) and can be used by an eavesdropper to fetch the page at any time in the future, thus allowing the attacker to always access the latest version of the page, or (much worse) repeatedly invoke a CGI script -- for instance, if the user requests the URL "/filemanager?delete=somefile", the attacker can repeat this deletion at any point in the future, possibly after the file has been recreated.\
And while it might not be possible to change GET data without reauthentication, cookies and POST data *can* be changed.\
To protect against the first problem, the nonce can be made to include a timestamp, and a check added to ensure that nonces older than e.g. 30 minutes result in a new authentication request.\
To solve the second problem, a one-time only nonce needs to be generated -- that is, all further requests using a particular nonce must be refused.\
One way to do this: When the user requests an action such as "deletefile", store a randomly generated nonce in a session variable, issue a 401 authentication challenge with that nonce, and then check against the stored value when receiving the authentication (and clear the session variable).\
This way, although a possible eavesdropper receives the nonce and thus gains the ability to perform the action, he can only perform it once -- and the user was going to perform it anyway. (Only the user or the attacker, but not both, gets to perform the action, so it's safe.)\
Of course, at some point, the security can only be improved by switching to HTTPS / SSL / TLS (this is for instance the only way to defend against man-in-the-middle attacks). You decide the level of security.`\
\
[up](https://www.php.net/manual/vote-note.php?id=41941&page=features.http-auth&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=41941&page=features.http-auth&vote=down "Vote down!")\
\
10\
\
\
[**_najprogramato at post dot sk_**](https://www.php.net/manual/en/features.http-auth.php#41941) [¶](https://www.php.net/manual/en/features.http-auth.php#41941)\
\
**21 years ago**\
\
`Don't use apache authentification in plain text. Is more better to use own script to generete new ID which is relevant to password. Apache auth data are sent to every page, so the posible mistake are known.`\
\
[up](https://www.php.net/manual/vote-note.php?id=61922&page=features.http-auth&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=61922&page=features.http-auth&vote=down "Vote down!")\
\
12\
\
\
[**_djreficul at yahoo dot com_**](https://www.php.net/manual/en/features.http-auth.php#61922) [¶](https://www.php.net/manual/en/features.http-auth.php#61922)\
\
**19 years ago**\
\
`Well, I think it's easy to make authentification works correctly. I use a session var to force authentication everytime a user visit the logging area.\
<?php\
if (!isset ($_SESSION['firstauthenticate'])) {\
    session_start();\
}\
function authenticate() {\
    header('WWW-Authenticate: Basic realm="Sistema autentificaci?n UnoAutoSur"');\
    header('HTTP/1_0 401 Unauthorized');\
//    header("Status: 401 Access Denied");\
    echo "Unauthorized\n";\
    exit;\
}\
if (!isset($_SERVER['PHP_AUTH_USER']) || strcmp ($_SERVER['PHP_AUTH_USER'],$user)!=0 ||\
      !isset ($_SERVER['PHP_AUTH_PW']) || strcmp($_SERVER['PHP_AUTH_PW'],$pass)!=0 || !isset ($_SESSION['firstauthenticate']) || !$_SESSION['firstauthenticate']) {\
     $_SESSION['firstauthenticate']=true;\
authenticate();\
} else {\
            //I destroy the session var now\
    session_unset();\
            //Your code below\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=93376&page=features.http-auth&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=93376&page=features.http-auth&vote=down "Vote down!")\
\
9\
\
\
[**_s dot i dot g at gmx dot com_**](https://www.php.net/manual/en/features.http-auth.php#93376) [¶](https://www.php.net/manual/en/features.http-auth.php#93376)\
\
**16 years ago**\
\
`<?php\
// try to mimic cpanel logout style\
// only diff is usr & pwd field is cleared when re-login\
// tested with ff2 & ie8\
session_start();\
$username = "test";\
$password = "test";\
if(isset($_GET['logout']))\
{\
unset($_SESSION["login"]);\
echo "You have logout ... ";\
echo "[<a href='" . $_SERVER['PHP_SELF'] . "'>Login</a>]";\
exit;\
}\
if (!isset($_SERVER['PHP_AUTH_USER']) || !isset($_SERVER['PHP_AUTH_PW']) || !isset($_SESSION["login"]))\
{\
header("WWW-Authenticate: Basic realm=\"Test\"");\
header("HTTP/1.0 401 Unauthorized");\
$_SESSION["login"] = true;\
echo "You are unauthorized ... ";\
echo "[<a href='" . $_SERVER['PHP_SELF'] . "'>Login</a>]";\
exit;\
}\
else\
{\
if($_SERVER['PHP_AUTH_USER'] == $username && $_SERVER['PHP_AUTH_PW'] == $password)\
{\
    echo "You have logged in ... ";\
    echo "[<a href='" . $_SERVER['PHP_SELF'] . "?logout'>Logout</a>]";\
}\
else\
{\
    unset($_SESSION["login"]);\
    header("Location: " . $_SERVER['PHP_SELF']);\
}\
}\
// content here\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=100101&page=features.http-auth&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=100101&page=features.http-auth&vote=down "Vote down!")\
\
11\
\
\
[**_Ollie L_**](https://www.php.net/manual/en/features.http-auth.php#100101) [¶](https://www.php.net/manual/en/features.http-auth.php#100101)\
\
**15 years ago**\
\
`I tried example 7, and at first I couldn't get it to work. It took me a while to spot that somewhere along the line, probably by the server, a seemingly random number was being added to the realm - so the valid_result variable wasn't calculated using the correct realm.\
To get around this, or any similar problems, make the following changes to the example:\
Around line 43 (44 if after next step ;) ):\
$needed_parts = array('nonce'=>1, 'nc'=>1, 'cnonce'=>1, 'qop'=>1, 'username'=>1, 'uri'=>1, 'response'=>1, 'realm'=>1);\
Before line 24:\
$realm = $data['realm'];\
These two steps get the real realm used for the authentication request, and substitute it into the "valid_response" query.\
Hope this helps :)`\
\
[up](https://www.php.net/manual/vote-note.php?id=99348&page=features.http-auth&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=99348&page=features.http-auth&vote=down "Vote down!")\
\
13\
\
\
[**_idbobby at rambler dot ru_**](https://www.php.net/manual/en/features.http-auth.php#99348) [¶](https://www.php.net/manual/en/features.http-auth.php#99348)\
\
**15 years ago**\
\
`First of all, sorry for my English.\
One more authorization script with logout solution.\
In script given by meint_at_meint_dot_net ( [http://www.php.net/manual/en/features.http-auth.php#93859](http://www.php.net/manual/en/features.http-auth.php#93859)) rewrite_module is used. If there are any problems with that module and possibilities of administration of the web-server are restricted (including restrictions for use of .htaccess) then you can use this solution.\
index.php\
---------\
<?php\
$auth_realm = 'My realm';\
require_once 'auth.php';\
echo "You've logged in as {$_SESSION['username']}<br>";\
echo '<p><a href="?action=logOut">LogOut</a></p>'\
?>\
auth.php\
--------\
<?php\
$_user_ = 'test';\
$_password_ = 'test';\
session_start();\
$url_action = (empty($_REQUEST['action'])) ? 'logIn' : $_REQUEST['action'];\
$auth_realm = (isset($auth_realm)) ? $auth_realm : '';\
if (isset($url_action)) {\
    if (is_callable($url_action)) {\
        call_user_func($url_action);\
    } else {\
        echo 'Function does not exist, request terminated';\
    };\
};\
function logIn() {\
    global $auth_realm;\
    if (!isset($_SESSION['username'])) {\
        if (!isset($_SESSION['login'])) {\
            $_SESSION['login'] = TRUE;\
            header('WWW-Authenticate: Basic realm="'.$auth_realm.'"');\
            header('HTTP/1.0 401 Unauthorized');\
            echo 'You must enter a valid login and password';\
            echo '<p><a href="?action=logOut">Try again</a></p>';\
            exit;\
        } else {\
            $user = isset($_SERVER['PHP_AUTH_USER']) ? $_SERVER['PHP_AUTH_USER'] : '';\
            $password = isset($_SERVER['PHP_AUTH_PW']) ? $_SERVER['PHP_AUTH_PW'] : '';\
            $result = authenticate($user, $password);\
            if ($result == 0) {\
                $_SESSION['username'] = $user;\
            } else {\
                session_unset($_SESSION['login']);\
                errMes($result);\
                echo '<p><a href="">Try again</a></p>';\
                exit;\
            };\
        };\
    };\
}\
function authenticate($user, $password) {\
    global $_user_;\
    global $_password_;\
    if (($user == $_user_)&&($password == $_password_)) { return 0; }\
    else { return 1; };\
}\
function errMes($errno) {\
    switch ($errno) {\
        case 0:\
            break;\
        case 1:\
            echo 'The username or password you entered is incorrect';\
            break;\
        default:\
            echo 'Unknown error';\
    };\
}\
function logOut() {\
    session_destroy();\
    if (isset($_SESSION['username'])) {\
        session_unset($_SESSION['username']);\
        echo "You've successfully logged out<br>";\
        echo '<p><a href="?action=logIn">LogIn</a></p>';\
    } else {\
        header("Location: ?action=logIn", TRUE, 301);\
    };\
    if (isset($_SESSION['login'])) { session_unset($_SESSION['login']); };\
    exit;\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=42198&page=features.http-auth&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=42198&page=features.http-auth&vote=down "Vote down!")\
\
8\
\
\
[**_steuber at aego dot de_**](https://www.php.net/manual/en/features.http-auth.php#42198) [¶](https://www.php.net/manual/en/features.http-auth.php#42198)\
\
**21 years ago**\
\
`Quite a good solution for the logout problem:\
Just tell browser that it is successfully logged in!\
This works as follows:\
1. User clicks logout button\
2. Script sends 401 Header\
3. User does NOT enter a password\
4. If no password is entered, script sends 200 Header\
So the browser remembers no password as a valid password.\
Example:\
<?php\
if (\
       (!isset($_SERVER['PHP_AUTH_USER']))\
    ||(\
           ($_GET["login"]=="login")\
    && !(\
             ($_SERVER['PHP_AUTH_USER']=="validuser")\
             && ($_SERVER['PHP_AUTH_PW']=="validpass")\
           )\
        )\
    ||(\
           ($_GET["logout"]=="logout")\
     && !($_SERVER['PHP_AUTH_PW']=="")\
        )\
     ) {\
Header("WWW-Authenticate: Basic realm=\"Realm\"");\
Header("HTTP/1.0 401 Unauthorized");\
echo "Not logged out...<br>\n";\
echo "<a href=\"index.php?login=login\">Login</a>";\
exit;\
} else if ($_SERVER['PHP_AUTH_PW']=="") {\
echo "Logged out...<br>\n";\
echo "<a href=\"index.php?login=login\">Login</a>";\
exit;\
}\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=40445&page=features.http-auth&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=40445&page=features.http-auth&vote=down "Vote down!")\
\
9\
\
\
[**_rob at theblip dot com_**](https://www.php.net/manual/en/features.http-auth.php#40445) [¶](https://www.php.net/manual/en/features.http-auth.php#40445)\
\
**21 years ago**\
\
`Regarding HTTP authentication in IIS with the php cgi 4.3.4, there's one more step. I searched mightily and didn't find this information anywhere else, so here goes. When using HTTP auth with the php CGI, you need to do the following things:\
1. In your php.ini file, set "cgi.rfc2616_headers = 0"\
2. In Web Site Properties -> File/Directory Security -> Anonymous Access dialog box, check the "Anonymous access" checkbox and uncheck any other checkboxes (i.e. uncheck "Basic authentication," "Integrated Windows authentication," and "Digest" if it's enabled.) Click OK.\
3. In "Custom Errors", select the range of "401;1" through "401;5" and click the "Set to Default" button.\
It's this last step that is crucial, yet not documented anywhere. If you don't, instead of the headers asking for credentials, IIS will return its own fancy but useless 'you are not authenticated' page. But if you do, then the browser will properly ask for credentials, and supply them in the $_SERVER['PHP_AUTH_*'] elements.`\
\
[up](https://www.php.net/manual/vote-note.php?id=56134&page=features.http-auth&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=56134&page=features.http-auth&vote=down "Vote down!")\
\
7\
\
\
[**_siberion at hotmail dot com_**](https://www.php.net/manual/en/features.http-auth.php#56134) [¶](https://www.php.net/manual/en/features.http-auth.php#56134)\
\
**20 years ago**\
\
`I came up with another approach to work around the problem of browsers caching WWW authentication credentials and creating logout problems. While most browsers have some kind of way to wipe this information, I prefer having my website to take care of the task instead of relying on the user's sanity.\
Even with Lalit's method of creating a random realm name, it was still possible to get back into the protected area using the back button in Firefox, so that didn't work. Here's my solution:\
Since browsers attach the credentials to specific URLs, use virtual paths where a component of the path is actually a PHP script, and everything following it is part of the URI, such as:\
[http://www.example.com/some\_dir/login.php/auth/8f631b92/](http://www.example.com/some_dir/login.php/auth/8f631b92/)\
By choosing a different number for the last component of the URL, browsers can be tricked into thinking that they are dealing with a completely different website, and thus prompting the user for credentials again.\
Note that using a random, unrestricted number will still allow the user to hit the back button to get back into the page. You should keep track of this number in a server-side file or database and regenerate it upon each successful login, so that the last number(s) become invalid. Using an invalid number might result in a 403 response or, depending on how you feel that day, a 302 to a nasty website.\
Care should be taken when linking from the page generated in this case, since relative links will be relative to the virtual and non-existant directory rather than the true script directory.\
Hope this helps somebody.`\
\
[up](https://www.php.net/manual/vote-note.php?id=37280&page=features.http-auth&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=37280&page=features.http-auth&vote=down "Vote down!")\
\
6\
\
\
[**_Paul_**](https://www.php.net/manual/en/features.http-auth.php#37280) [¶](https://www.php.net/manual/en/features.http-auth.php#37280)\
\
**21 years ago**\
\
`Here is a extremely easy way to successfully logout.\
<?php\
if ( $realm == '' )\
$realm = mt_rand( 1, 1000000000 );\
    header( 'WWW-Authenticate: Basic realm='.$realm );\
?>\
To log the user out simply change the value of $realm`\
\
[up](https://www.php.net/manual/vote-note.php?id=125122&page=features.http-auth&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=125122&page=features.http-auth&vote=down "Vote down!")\
\
3\
\
\
[**_patrick dot moire at socopa dot fr_**](https://www.php.net/manual/en/features.http-auth.php#125122) [¶](https://www.php.net/manual/en/features.http-auth.php#125122)\
\
**5 years ago**\
\
`Samples Login / Logout script\
login.php :\
<?php\
    // Initisalition\
    if ($_COOKIE["SESSION"]=='') {\
        setcookie("SESSION", 'AUTH', 0,'/');\
\
    // Identification perdu (time-out ou logoff)\
    } else if ($_SERVER['PHP_AUTH_USER']!='' && $_COOKIE["USER_SESSION"]=='') {\
        $_SERVER['PHP_AUTH_USER'] = '';\
    }\
    // Controle identification à la base\
    $ident = executeSQL("SELECT * FROM UTILISATEURS WHERE upper(IDENTIFIANT)=Upper('".$_SERVER['PHP_AUTH_USER']."')");\
    if ($_SERVER['PHP_AUTH_USER']!='' && strtoupper($ident['IDENTIFIANT'])==strtoupper($_SERVER['PHP_AUTH_USER']) && $ident['MOT_DE_PASSE']==$_SERVER['PHP_AUTH_PW']) {\
        $user = $_SERVER['PHP_AUTH_USER'];\
        setcookie("USER_SESSION", $user, time()+300,'/'); // 5 Minutes !\
\
    // Mot de passe incorecte : demande identification\
    } else {\
        setcookie("SESSION", '', 1,'/');\
        header('WWW-Authenticate: Basic realm="My Realm"');\
        header('HTTP/1.0 401 Unauthorized');\
        die;\
    }\
\
?>\
<html>\
    <body >\
        Bonjour <?php echo $ident['NOM'].' '.$ident['PRENOM']; ?>\
        <br>\
        <br>\
        <a href=" [http://logout.php](http://logout.php/)">Deconnexion</a>\
    </body>\
</html>\
logout.php :\
<?php\
setcookie("USER_SESSION", '', 1,'/');\
header('Location: [http://login.php](http://login.php/)');\
?>`\
\
[up](https://www.php.net/manual/vote-note.php?id=71069&page=features.http-auth&vote=up "Vote up!")\
\
[down](https://www.php.net/manual/vote-note.php?id=71069&page=features.http-auth&vote=down "Vote down!")\
\
 -2\
\
\
[**_Whatabrain_**](https://www.php.net/manual/en/features.http-auth.php#71069) [¶](https://www.php.net/manual/en/features.http-auth.php#71069)\
\
**18 years ago**\
\
`Back to the problem of authenticating in CGI mode... mcbethh suggested using this to set a local variable in php:\
RewriteRule .* - [E=REMOTE_USER:%{HTTP:Authorization},L]\
It didn't work. I couldn't see the variable. My solution is pretty round-about, but it works:\
RewriteEngine on\
RewriteCond %{HTTP:Authorization} !^$\
RewriteCond %{REQUEST_METHOD} =GET\
RewriteCond %{QUERY_STRING} =""\
RewriteRule ^page.php$ page.php?login=%{HTTP:Authorization}$1\
This causes the Auth string to be added to the URL if there are no parameters and it's a GET request. This prevents POSTs and parameter lists from being corrupted.\
Then, in the PHP script, I store the Auth string as a session cookie.\
So the only way to log in to my script is to go to the url with no parameters.`\
\
[＋add a note](https://www.php.net/manual/add-note.php?sect=features.http-auth&repo=en&redirect=https://www.php.net/manual/en/features.http-auth.php)\
\
![To Top](https://www.php.net/images/to-top@2x.png)\
\
`↑` and `↓` to navigate •\
`Enter` to select •\
`Esc` to close\
\
\
Press `Enter` without\
selection to search using Google