---
url: https://www.php.net/manual/en/function.session-start.php
scraped_at: 2025-10-20T02:53:51.947Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# session\_start

(PHP 4, PHP 5, PHP 7, PHP 8)

session\_start — Start new or resume existing session

### Description [¶](https://www.php.net/manual/en/function.session-start.php\#refsect1-function.session-start-description)

**session\_start**([array](https://www.php.net/manual/en/language.types.array.php) `$options` = \[\]): [bool](https://www.php.net/manual/en/language.types.boolean.php)

**session\_start()** creates a session or resumes the
current one based on a session identifier passed via a GET or POST
request, or passed via a cookie.


When **session\_start()** is called or when a session auto starts,
PHP will call the open and read session save handlers. These will either be a built-in
save handler provided by default or by PHP extensions (such as SQLite or Memcached); or can be
custom handler as defined by [session\_set\_save\_handler()](https://www.php.net/manual/en/function.session-set-save-handler.php).
The read callback will retrieve any existing session data (stored in a special serialized format)
and will be unserialized and used to automatically populate the $\_SESSION superglobal when the
read callback returns the saved session data back to PHP session handling.


To use a named session, call
[session\_name()](https://www.php.net/manual/en/function.session-name.php) before calling
**session\_start()**.


When [session.use\_trans\_sid](https://www.php.net/manual/en/session.configuration.php#ini.session.use-trans-sid)
is enabled, the **session\_start()** function will
register an internal output handler for URL rewriting.


If a user uses `ob_gzhandler` or similar with
[ob\_start()](https://www.php.net/manual/en/function.ob-start.php), the function order is important for
proper output. For example,
`ob_gzhandler` must be registered before starting the session.


### Parameters [¶](https://www.php.net/manual/en/function.session-start.php\#refsect1-function.session-start-parameters)

`options`

If provided, this is an associative array of options that will override
the currently set
[session configuration directives](https://www.php.net/manual/en/session.configuration.php).
The keys should not include the `session.` prefix.


In addition to the normal set of configuration directives, a
`read_and_close` option may also be provided. If set to
**`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, this will result in the session being closed immediately after
being read, thereby avoiding unnecessary locking if the session data
won't be changed.


### Return Values [¶](https://www.php.net/manual/en/function.session-start.php\#refsect1-function.session-start-returnvalues)

This function returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if a session was successfully started,
otherwise **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.


### Changelog [¶](https://www.php.net/manual/en/function.session-start.php\#refsect1-function.session-start-changelog)

| Version | Description |
| --- | --- |
| 7.1.0 | **session\_start()** now returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** and no longer<br> initializes [$\_SESSION](https://www.php.net/manual/en/reserved.variables.session.php) when it failed to start the<br> session. |

### Examples [¶](https://www.php.net/manual/en/function.session-start.php\#refsect1-function.session-start-examples)

#### A basic session example [¶](https://www.php.net/manual/en/function.session-start.php\#refsect2-function.session-start-unknown-34)

**Example #1 page1.php**

`<?php
// page1.php
session_start();
echo 'Welcome to page #1';
$_SESSION['favcolor'] = 'green';
$_SESSION['animal']   = 'cat';
$_SESSION['time']     = time();
// Works if session cookie was accepted
echo '<br /><a href="page2.php">page 2</a>';
// Or maybe pass along the session id, if needed
echo '<br /><a href="page2.php?' . SID . '">page 2</a>';
?>`

After viewing page1.php, the second page
page2.php will magically contain the session
data. Read the [session reference](https://www.php.net/manual/en/ref.session.php)
for information on [propagating\\
session ids](https://www.php.net/manual/en/session.idpassing.php) as it, for example, explains what the constant
**`[SID](https://www.php.net/manual/en/session.constants.php#constant.sid)`** is all about.


**Example #2 page2.php**

`<?php
// page2.php
session_start();
echo 'Welcome to page #2<br />';
echo $_SESSION['favcolor']; // green
echo $_SESSION['animal'];   // cat
echo date('Y m d H:i:s', $_SESSION['time']);
// You may want to use SID here, like we did in page1.php
echo '<br /><a href="page1.php">page 1</a>';
?>`

#### Providing options to **session\_start()** [¶](https://www.php.net/manual/en/function.session-start.php\#refsect2-function.session-start-unknown-37)

**Example #3 Overriding the cookie lifetime**

`<?php
// This sends a persistent cookie that lasts a day.
session_start([\
    'cookie_lifetime' => 86400,\
]);
?>`

**Example #4 Reading the session and closing it**

`<?php
// If we know we don't need to change anything in the
// session, we can just read and close rightaway to avoid
// locking the session file and blocking other pages
session_start([\
    'cookie_lifetime' => 86400,\
    'read_and_close'  => true,\
]);`

### Notes [¶](https://www.php.net/manual/en/function.session-start.php\#refsect1-function.session-start-notes)

> **Note**:
>
>
> To use cookie-based sessions, **session\_start()**
> must be called before outputting anything to the browser.

> **Note**:
>
>
> Use of [zlib.output\_compression](https://www.php.net/manual/en/zlib.configuration.php#ini.zlib.output-compression)
> is recommended instead of [ob\_gzhandler()](https://www.php.net/manual/en/function.ob-gzhandler.php)

> **Note**:
>
>
> This function sends out several HTTP headers depending on the
> configuration. See [session\_cache\_limiter()](https://www.php.net/manual/en/function.session-cache-limiter.php) to
> customize these headers.

### See Also [¶](https://www.php.net/manual/en/function.session-start.php\#refsect1-function.session-start-seealso)

- [$\_SESSION](https://www.php.net/manual/en/reserved.variables.session.php)
- The [session.auto\_start](https://www.php.net/manual/en/session.configuration.php#ini.session.auto-start)
configuration directive

- [session\_id()](https://www.php.net/manual/en/function.session-id.php) \- Get and/or set the current session id

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/session/functions/session-start.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.session-start%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.session-start&repo=en&redirect=https://www.php.net/manual/en/function.session-start.php)

### User Contributed Notes 35 notes

[up](https://www.php.net/manual/vote-note.php?id=102460&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=102460&page=function.session-start&vote=down "Vote down!")

33


[**_linblow at hotmail dot fr_**](https://www.php.net/manual/en/function.session-start.php#102460) [¶](https://www.php.net/manual/en/function.session-start.php#102460)

**14 years ago**

`If you want to handle sessions with a class, I wrote this little class:
<?php
/*
    Use the static method getInstance to get the object.
*/
class Session
{
    const SESSION_STARTED = TRUE;
    const SESSION_NOT_STARTED = FALSE;

    // The state of the session
    private $sessionState = self::SESSION_NOT_STARTED;

    // THE only instance of the class
    private static $instance;


    private function __construct() {}


    /**
    *    Returns THE instance of 'Session'.
    *    The session is automatically initialized if it wasn't.
    *
    *    @return    object
    **/

    public static function getInstance()
    {
        if ( !isset(self::$instance))
        {
            self::$instance = new self;
        }

        self::$instance->startSession();

        return self::$instance;
    }


    /**
    *    (Re)starts the session.
    *
    *    @return    bool    TRUE if the session has been initialized, else FALSE.
    **/

    public function startSession()
    {
        if ( $this->sessionState == self::SESSION_NOT_STARTED )
        {
            $this->sessionState = session_start();
        }

        return $this->sessionState;
    }


    /**
    *    Stores datas in the session.
    *    Example: $instance->foo = 'bar';
    *
    *    @param    name    Name of the datas.
    *    @param    value    Your datas.
    *    @return    void
    **/

    public function __set( $name , $value )
    {
        $_SESSION[$name] = $value;
    }


    /**
    *    Gets datas from the session.
    *    Example: echo $instance->foo;
    *
    *    @param    name    Name of the datas to get.
    *    @return    mixed    Datas stored in session.
    **/

    public function __get( $name )
    {
        if ( isset($_SESSION[$name]))
        {
            return $_SESSION[$name];
        }
    }


    public function __isset( $name )
    {
        return isset($_SESSION[$name]);
    }


    public function __unset( $name )
    {
        unset( $_SESSION[$name] );
    }


    /**
    *    Destroys the current session.
    *
    *    @return    bool    TRUE is session has been deleted, else FALSE.
    **/

    public function destroy()
    {
        if ( $this->sessionState == self::SESSION_STARTED )
        {
            $this->sessionState = !session_destroy();
            unset( $_SESSION );

            return !$this->sessionState;
        }

        return FALSE;
    }
}
/*
    Examples:
*/
// We get the instance
$data = Session::getInstance();
// Let's store datas in the session
$data->nickname = 'Someone';
$data->age = 18;
// Let's display datas
printf( '<p>My name is %s and I\'m %d years old.</p>' , $data->nickname , $data->age );
/*
    It will display:

    Array
    (
        [nickname] => Someone
        [age] => 18
    )
*/
printf( '<pre>%s</pre>' , print_r( $_SESSION , TRUE ));
// TRUE
var_dump( isset( $data->nickname ));
// We destroy the session
$data->destroy();
// FALSE
var_dump( isset( $data->nickname ));
?>
I prefer using this class instead of using directly the array $_SESSION.`

[up](https://www.php.net/manual/vote-note.php?id=117157&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117157&page=function.session-start&vote=down "Vote down!")

22


[**_aaronw at catalyst dot net dot nz_**](https://www.php.net/manual/en/function.session-start.php#117157) [¶](https://www.php.net/manual/en/function.session-start.php#117157)

**10 years ago**

`As others have noted, PHP's session handler is blocking. When one of your scripts calls session_start(), any other script that also calls session_start() with the same session ID will sleep until the first script closes the session.
A common workaround to this is call session_start() and session_write_close() each time you want to update the session.
The problem with this, is that each time you call session_start(), PHP prints a duplicate copy of the session cookie to the HTTP response header. Do this enough times (as you might do in a long-running script), and the response header can get so large that it causes web servers & browsers to crash or reject your response as malformed.
This error has been reported to PHP HQ, but they've marked it "Won't fix" because they say you're not supposed to open and close the session during a single script like this. [https://bugs.php.net/bug.php?id=31455](https://bugs.php.net/bug.php?id=31455)
As a workaround, I've written a function that uses headers_list() and header_remove() to clear out the duplicate cookies. It's interesting to note that even on requests when PHP sends duplicate session cookies, headers_list() still only lists one copy of the session cookie. Nonetheless, calling header_remove() removes all the duplicate copies.
<?php
/**
* Every time you call session_start(), PHP adds another
* identical session cookie to the response header. Do this
* enough times, and your response header becomes big enough
* to choke the web server.
*
* This method clears out the duplicate session cookies. You can
* call it after each time you've called session_start(), or call it
* just before you send your headers.
*/
function clear_duplicate_cookies() {
    // If headers have already been sent, there's nothing we can do
    if (headers_sent()) {
        return;
    }
    $cookies = array();
    foreach (headers_list() as $header) {
        // Identify cookie headers
        if (strpos($header, 'Set-Cookie:') === 0) {
            $cookies[] = $header;
        }
    }
    // Removes all cookie headers, including duplicates
    header_remove('Set-Cookie');
    // Restore one copy of each cookie
    foreach(array_unique($cookies) as $cookie) {
        header($cookie, false);
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=113985&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113985&page=function.session-start&vote=down "Vote down!")

14


[**_ohcc at 163 dot com_**](https://www.php.net/manual/en/function.session-start.php#113985) [¶](https://www.php.net/manual/en/function.session-start.php#113985)

**11 years ago**

`The constant SID would always be '' (an empty string) if directive session.use_trans_sid in php ini file is set to 0.
So remember to set session.use_trans_sid to 1 and restart your server before you use SID in your php script.`

[up](https://www.php.net/manual/vote-note.php?id=120589&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120589&page=function.session-start&vote=down "Vote down!")

12


[**_bachtel at \[googles email service\]dotcom_**](https://www.php.net/manual/en/function.session-start.php#120589) [¶](https://www.php.net/manual/en/function.session-start.php#120589)

**8 years ago**

`If you are using a custom session handler via session_set_save_handler() then calling session_start() in PHP 7.1 you might see an error like this:
session_start(): Failed to read session data: user (path: /var/lib/php/session) in ...
As of this writing, it seems to be happening in PHP 7.1, and things look OK in PHP7.0.
It is also hard to track down because if a session already exists for this id (maybe created by an earlier version of PHP), it will not trigger this issue because the $session_data will not be null.
The fix is simple... you just need to check for 'null' during your read function:
<?php
function read($id)
{
//... pull the data out of the DB, off the disk, memcache, etc
$session_data = getSessionDataFromSomewhere($id);

//check to see if $session_data is null before returning (CRITICAL)
if(is_null($session_data))
{
    $session_data = '';  //use empty string instead of null!
}
return $session_data;
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=114209&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114209&page=function.session-start&vote=down "Vote down!")

10


[**_elitescripts2000 at yahoo dot com_**](https://www.php.net/manual/en/function.session-start.php#114209) [¶](https://www.php.net/manual/en/function.session-start.php#114209)

**11 years ago**

`3 easy but vital things about Sessions in AJAX Apps.
<?php
// session start
//  It is VERY important to include a Period if using
// a whole domain.  (.yourdomain.com)
// It is VERY important to set the root path your session will always
// operate in... (/members) will ensure sessions will NOT be interfered
// with a session with a path of say (/admin) ... so you can log in
// as /admin and as /members... NEVER do unset($_SESSION)
// $_SESSION=array(); is preferred, session_unset();  session_destroy();
session_set_cookie_params(0, '/members', '.yourdomain.com', 0, 1);
session_start();
$_SESSION = array();
session_unset();
session_destroy();
session_set_cookie_params(0, '/members', '.yourdomain.com', 0, 1);
session_start();
$_SESSION['whatever'] = 'youwhat';
// session destroying
// To be safe, clear out your $_SESSION array
// Next, what most people do NOT do is delete the session cookie!
// It is easy to delete a cookie by expiring it long before the current time.
// The ONLY WAY to delete a cookie, is to make sure ALL parameters match the
// cookie to be deleted...which is easy to get those params with
// session_get_cookie_params()...
// FInally, use  session_unset(); and session_destroy(); in this order to ensure
// Chrome, IE, Firefox and others, are properly destroying the session.
$_SESSION = array();
if (ini_get('session.use_cookies'))
{
    $p = session_get_cookie_params();
    setcookie(session_name(), '', time() - 31536000, $p['path'], $p['domain'], $p['secure'], $p['httponly']);
}
session_unset();
session_destroy();
// AJAX and SESSIONS.
// Example... you start a session based PHP page, which then calls an Ajax (XMLHTTP) authenticated
// using the SAME SESSION to Poll and output the data, for example.  But, you notice when you
// try to start the Polling AJAX call always HANGS and seems to hang at the session_start().
// This is because the session is opened in the first page, calls the AJAX polling example, and
// tries to open the same session (for authentication) and do the AJAX call, you MUST call
// session_write_close(); meaning you are done writing to the $_SESSION variable, which really
// represents a file that must be CLOSED with session_write_close();....
// THAN you can call your AJAX Polling code to reopen the same session and do its polling...
// Normally, the $_SESSION is closed automatically when the script is closed or finished executing
// So, if you need to keep a PHP page running after opening a SESSION, simply close it when finished
// writing to $_SESSION so the AJAX polling page can authenticate and use the same session in a
// seperate web page...
session_write_close();
?>
Hope this helps someone with their sessions...
Thanks.`

[up](https://www.php.net/manual/vote-note.php?id=121507&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121507&page=function.session-start&vote=down "Vote down!")

9


[**_marco dot agnoli at me dot com_**](https://www.php.net/manual/en/function.session-start.php#121507) [¶](https://www.php.net/manual/en/function.session-start.php#121507)

**8 years ago**

````I recently made an interesting observation:
It seems that `session_start()` can return `true` even if the session was not properly created. In my case, the disk storage was full and so the session data could not be written to disk. I had some logic that resulted in an infinite loop when the session was not written to disk.
To check if the session really was saved to disk I used:
```
<?php
function safe_session_start() {
    # Attempt to start a session
    if (!@\session_start()) return false;
    #
    # Check if we need to perform
    # the write test.
    #
    if (!isset($_SESSION['__validated'])) {
        $_SESSION['__validated'] = 1;
        # Attempt to write session to disk
        @\session_write_close();
        # Unset the variable from memory.
        # This step may be unnecessary
        unset($_SESSION['__validated']);
        # Re-start session
        @\session_start();
        # Check if variable value is retained
        if (!isset($_SESSION['__validated'])) {
            # Session was not written to disk
            return false;
        }
    }
    return true;
}
if (!safe_session_start()) {
    # Sessions are probably not written to disk...
    # Handle error accordingly.
}
?>
```
Took me quite a while to figure this out.
Maybe it helps someone!````

[up](https://www.php.net/manual/vote-note.php?id=125487&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125487&page=function.session-start&vote=down "Vote down!")

5


[**_Anonymous_**](https://www.php.net/manual/en/function.session-start.php#125487) [¶](https://www.php.net/manual/en/function.session-start.php#125487)

**4 years ago**

`Be careful with the 'read_and_close' option. It doesn't update the session file's last modification time unlike the default PHP behaviour when you don't close the session (or when you use session_write_close explicitly).
Old session files (for me, older than 24 minutes) will be occasionally cleared by the garbage collector (for me every 09 and 39 minute of every hour).
So a session can disappear even if the page regularly sends requests to the server that only reads and closes the session.`

[up](https://www.php.net/manual/vote-note.php?id=92432&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92432&page=function.session-start&vote=down "Vote down!")

8


[**_emre@yazici_**](https://www.php.net/manual/en/function.session-start.php#92432) [¶](https://www.php.net/manual/en/function.session-start.php#92432)

**16 years ago**

`PHP Manual specifically denotes this common mistake:
Depending on the session handler, not all characters are allowed within the session id. For example, the file session handler only allows characters in the range a-z A-Z 0-9 , (comma) and - (minus)!
See session_id() manual page for more details.`

[up](https://www.php.net/manual/vote-note.php?id=101452&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101452&page=function.session-start&vote=down "Vote down!")

10


[**_dave1010 at gmail dot com_**](https://www.php.net/manual/en/function.session-start.php#101452) [¶](https://www.php.net/manual/en/function.session-start.php#101452)

**14 years ago**

`PHP locks the session file until it is closed. If you have 2 scripts using the same session (i.e. from the same user) then the 2nd script will not finish its call to session_start() until the first script finishes execution.
If you have scripts that run for more than a second and users may be making more than 1 request at a time then it is worth calling session_write_close() as soon as you've finished writing session data.
<?php
// a lock is places on the session, so other scripts will have to wait
session_start();
// do all your writing to $_SESSION
$_SESSION['a'] = 1;
// $_SESSION can still be read, but writing will not update the session.
// the lock is removed and other scripts can now read the session
session_write_close();
do_something_slow();
?>
Found this out from [http://konrness.com/php5/how-to-prevent-blocking-php-requests/](http://konrness.com/php5/how-to-prevent-blocking-php-requests/)`

[up](https://www.php.net/manual/vote-note.php?id=110649&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110649&page=function.session-start&vote=down "Vote down!")

9


[**_someOne\_01 at somewhere dot com_**](https://www.php.net/manual/en/function.session-start.php#110649) [¶](https://www.php.net/manual/en/function.session-start.php#110649)

**12 years ago**

`When you have an import script that takes long to execute, the browser seem to lock up and you cannot access the website anymore. this is because a request is reading and locking the session file to prevent corruption.
you can either
- use a different session handler with session_set_save_handler()
- use session_write_close() in the import script as soon you don't need session anymore (best moment is just before the long during part takes place), you can session_start when ever you want and as many times you like if your import script requires session variables changed.
example
<?php
session_start(); //initiate / open session
$_SESSION['count'] = 0; // store something in the session
session_write_close(); //now close it,
# from here every other script can be run (and makes it seem like multitasking)
for($i=0; $i<=100; $i++){ //do 100 cycles
    session_start(); //open the session again for editing a variable
    $_SESSION['count'] += 1; //change variable
    session_write_close(); //now close the session again!
    sleep(2); //every cycle sleep two seconds, or do a heavy task
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=128197&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128197&page=function.session-start&vote=down "Vote down!")

1


[**_bwz_**](https://www.php.net/manual/en/function.session-start.php#128197) [¶](https://www.php.net/manual/en/function.session-start.php#128197)

**2 years ago**

`Be warned of another issue with blocking sessions: if you want to call an external program (or use an external service) that needs to access your website using the same session.
For example I am printing a page as a PDF. I can just save the web page as a HTML file. But the images in the HTML are also private and require the current user session to be seen.
What will happen is that this program might hang indefinitely (or timeout) as session_start waits for the parent PHP process to release the lock. And session_start doesn't obey max_execution_time (as documented in this bug: [https://bugs.php.net/bug.php?id=72345](https://bugs.php.net/bug.php?id=72345) ), so this will effectively kill the server after a few requests, as each one will be hanging forever
It's the same if you use an external HTTP service:
<?php
$pdf = file_get_contents(' [http://pdf.website.tld/?url=http://website.tld/print.php](http://pdf.website.tld/?url=http://website.tld/print.php)');
?>
The service will wait for the website host to release the lock, but it can't as it is waiting for the PDF service to finish...
The nice solution is to release the lock immediately by calling session_write_close after session_start, and when you need to write to the session you do the same again, but as noted it has its own issues. Using a custom session handler is probably the best solution.`

[up](https://www.php.net/manual/vote-note.php?id=95372&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95372&page=function.session-start&vote=down "Vote down!")

4


[**_jamestrowbridge at gmail dot com_**](https://www.php.net/manual/en/function.session-start.php#95372) [¶](https://www.php.net/manual/en/function.session-start.php#95372)

**15 years ago**

`Unfortunately, after pulling my hair out trying to figure out why my application was working fine in every browser other than IE ( Internet Explorer) (Opera, Chrome, Firefox, Safari are what I've tested this in) - when using a DNS CNAME record (like a vanity name that is different from the DNS A record, which is the hostname of the server) sessions do not work correctly.
If you store a session var while on the CNAME:
vanity.example.com and the hostname of the server is hosname.example.com
Then try to call the variable from a different page, it will not find it because of the CNAME (I guess it store the variable under the hostname, then when trying to read it it's still looking under the CNAME) the same application works fine when accessing it under the hostname directly.  Keep in mind that I was testing this on an internal network.`

[up](https://www.php.net/manual/vote-note.php?id=68123&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=68123&page=function.session-start&vote=down "Vote down!")

3


[**_James_**](https://www.php.net/manual/en/function.session-start.php#68123) [¶](https://www.php.net/manual/en/function.session-start.php#68123)

**19 years ago**

`To avoid the notice commited by PHP since 4.3.3 when you start a session twice, check session_id() first:
if (session_id() == "")
session_start();`

[up](https://www.php.net/manual/vote-note.php?id=70007&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=70007&page=function.session-start&vote=down "Vote down!")

2


[**_ben dot morin at spaboom dot com_**](https://www.php.net/manual/en/function.session-start.php#70007) [¶](https://www.php.net/manual/en/function.session-start.php#70007)

**19 years ago**

`James at skinsupport dot com raises a good point (warning) about additional requests from the browser.  The request for favicon.ico, depending on how it is handled, can have unintended results on your sessions.
For example, suppose you have ErrorDocument 404 /signin.php, no favicon.ico file and all pages in your site where the user signs in are also redirected to /signin.php if they're not already signed in.
If signin.php does any clean up or reassigning of session_id (as all good signin.php pages should) then the additional request from the browser for favicon.ico could potentially corrupt the session as set by the actual request.
Kudos to James for pointing it out and shame on me for skimming past it and not seeing how it applied to my problem.  Thanks too to the Firefox Live HTTP Headers extension for showing the additional request.
Don't waste days or even hours on this if your session cookies are not being sent or if the session data isn't what you expect it to be.  At a minimum, eliminate this case and see if any additional requests could be at fault.`

[up](https://www.php.net/manual/vote-note.php?id=87069&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87069&page=function.session-start&vote=down "Vote down!")

3


[**_andy\_isherwood at hotmail dot com_**](https://www.php.net/manual/en/function.session-start.php#87069) [¶](https://www.php.net/manual/en/function.session-start.php#87069)

**16 years ago**

`A session created with session_start will only be available to pages within the directory tree of the page that first created it.
i.e. If the page that first creates the session is /dir1/dir2/index.php and the user then goes to any page above dir2 (e.g. /dir1/index.php), session_start will create a new session rather than use the existing one.`

[up](https://www.php.net/manual/vote-note.php?id=123917&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123917&page=function.session-start&vote=down "Vote down!")

2


[**_hu60 dot cn at gmail dot com_**](https://www.php.net/manual/en/function.session-start.php#123917) [¶](https://www.php.net/manual/en/function.session-start.php#123917)

**6 years ago**

`The following code shows how the PHP session works. The function my_session_start() does almost the same thing as session_start().
<?php
error_reporting(E_ALL);
ini_set('display_errors', true);
ini_set('session.save_path', __DIR__);
my_session_start();
echo '<p>session id: '.my_session_id().'</p>';
echo '<code><pre>';
var_dump($_SESSION);
echo '</pre></code>';
$now = date('H:i:s');
if (isset($_SESSION['last_visit_time'])) {
echo '<p>Last Visit Time: '.$_SESSION['last_visit_time'].'</p>';
}
echo '<p>Current Time: '.$now.'</p>';
$_SESSION['last_visit_time'] = $now;
function my_session_start() {
global $phpsessid, $sessfile;

if (!isset($_COOKIE['PHPSESSID']) || empty($_COOKIE['PHPSESSID'])) {
    $phpsessid = my_base32_encode(my_random_bytes(16));
    setcookie('PHPSESSID', $phpsessid, ini_get('session.cookie_lifetime'), ini_get('session.cookie_path'), ini_get('session.cookie_domain'), ini_get('session.cookie_secure'), ini_get('session.cookie_httponly'));
} else {
    $phpsessid = substr(preg_replace('/[^a-z0-9]/', '', $_COOKIE['PHPSESSID']), 0, 26);
}

$sessfile = ini_get('session.save_path').'/sess_'.$phpsessid;
if (is_file($sessfile)) {
    $_SESSION = unserialize(file_get_contents($sessfile));
} else {
    $_SESSION = array();
}
register_shutdown_function('my_session_save');
}
function my_session_save() {
global $sessfile;

file_put_contents($sessfile, serialize($_SESSION));
}
function my_session_id() {
global $phpsessid;
return $phpsessid;
}
function my_random_bytes($length) {
if (function_exists('random_bytes')) {
      return random_bytes($length);
}
$randomString = '';
for ($i = 0; $i < $length; $i++) {
      $randomString .= chr(rand(0, 255));
}
return $randomString;
}
function my_base32_encode($input) {
$BASE32_ALPHABET = 'abcdefghijklmnopqrstuvwxyz234567';
$output = '';
$v = 0;
$vbits = 0;
for ($i = 0, $j = strlen($input); $i < $j; $i++) {
    $v <<= 8;
    $v += ord($input[$i]);
    $vbits += 8;
    while ($vbits >= 5) {
      $vbits -= 5;
      $output .= $BASE32_ALPHABET[$v >> $vbits];
      $v &= ((1 << $vbits) - 1);
    }
}
if ($vbits > 0) {
    $v <<= (5 - $vbits);
    $output .= $BASE32_ALPHABET[$v];
}
return $output;
}`

[up](https://www.php.net/manual/vote-note.php?id=112973&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112973&page=function.session-start&vote=down "Vote down!")

2


[**_ilnomedellaccount at gmail dot com_**](https://www.php.net/manual/en/function.session-start.php#112973) [¶](https://www.php.net/manual/en/function.session-start.php#112973)

**12 years ago**

`A note about session_start(), custom handlers and database foreign key constraints, which I think may be of some use...
We know that if we want our sessions into a database table (rather than the default storage), we can refer to session_set_save_handler(...) to get them there. Note that session_set_save_handler must (obviously) be called before session_start(), but let me get to the point...
Upon calling session_start() the "first time", when the session does not already exist, php will spawn a new session but will not call the write handler until script execution finishes.
Thus, the session at this point exists in the server process memory, but won't be visible as a row in the DB before the script ends.
This seems reasonable, because this avoids some unnecessary database access and resource usage before we even populate our session with meaningfull and definitive data, but this also has side-effects.
In my case, the script called session_start() to make sure a session was initiated, then used session_id() to populate another table in the DB, which had foreign_key constraint to the "sessions" table. This failed because no session was in the db at that point, yet!
I know I could simply force the creation of the row in the DB by manually calling the write handler after session_start(), when necessary, but I am not sure if this is the best possible approach.
As soon as I find an "elegant" solution, or a completely different approach, I will post some working sample code.
In the meanwhile... have fun!`

[up](https://www.php.net/manual/vote-note.php?id=92490&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92490&page=function.session-start&vote=down "Vote down!")

2


[**_schlang_**](https://www.php.net/manual/en/function.session-start.php#92490) [¶](https://www.php.net/manual/en/function.session-start.php#92490)

**16 years ago**

`if you store your sessions in a database, always ensure that the type of the database column is large enough for your session values`

[up](https://www.php.net/manual/vote-note.php?id=51520&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=51520&page=function.session-start&vote=down "Vote down!")

2


[**_jorrizza at gmail dot com_**](https://www.php.net/manual/en/function.session-start.php#51520) [¶](https://www.php.net/manual/en/function.session-start.php#51520)

**20 years ago**

`If you open a popup window (please no commercial ones!) with javascript window.open it might happen IE blocks the session cookie.
A simple fix for that is opening the new window with the session ID in a GET value. Note I don't use SID for this, because it will not allways be available.
----page.php----
//you must have a session active here
window.open('popup.php?sid=<?php echo session_id(); ?>', '700x500', 'toolbar=no, status=no, scrollbars=yes, location=no, menubar=no, directories=no, width=700, height=500');
----popup.php----
<?php
session_id(strip_tags($_GET['sid']));
session_start();
//and go on with your session vars
?>`

[up](https://www.php.net/manual/vote-note.php?id=121313&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121313&page=function.session-start&vote=down "Vote down!")

1


[**_axew3 at axew3 dot com_**](https://www.php.net/manual/en/function.session-start.php#121313) [¶](https://www.php.net/manual/en/function.session-start.php#121313)

**8 years ago**

`X Maintainers ... Sorry to be such pain the ass, please delete this duplicate, because submitted in a crazy 'session' where i've mess things between browser tabs ... sorry again, alessio
[http://php.net/manual/en/function.session-start.php#121310](http://php.net/manual/en/function.session-start.php#121310)`

[up](https://www.php.net/manual/vote-note.php?id=130222&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130222&page=function.session-start&vote=down "Vote down!")

0


[**_guy dot sartorelli at silverstripe dot com_**](https://www.php.net/manual/en/function.session-start.php#130222) [¶](https://www.php.net/manual/en/function.session-start.php#130222)

**6 months ago**

``Sessions are blocking by default - i.e. after calling `session_start()` the session file will be locked for reading until you either close that connection or explicitly call `session_write_close()`.
That means any additional requests from that user (e.g. opening a new tab or XHR requests) which also open the session will have to wait for the previous request to finish - or at least wait for you to close the session.
You can get around this by closing the session immediately after opening it (which lets you read session data), and then opening it again temporarily whenever you want to update the session:
<?php
// Passing an empty string here explicitly disables automatic cookie headers being generated
session_cache_limiter('');
// You can then set your own session cookie header - and it's the ONLY session cookie header that will be included in the response
setcookie(session_name(), session_id(), /* any other options you want */);
// Note: I avoid using `session_start(['read_and_close' => true]);` because that doesn't update the last-modified date on the session file, which can result in sessions expiring even when they're being actively used.
session_start();
session_write_close();
// ... some processing here
session_start();
$_SESSION['myData'] = 'my value';
session_write_close();
?>
Note that the call to `session_cache_limiter('')` is important to avoid multiple set-cookie headers from being included in the response as others have noted. You then MUST set the cookie yourself, or it won't be set at all.
Take a careful look at all the session cookie related options for `session_start()` and in php.ini to make sure you respect those options appropriately when setting your own cookies.``

[up](https://www.php.net/manual/vote-note.php?id=129844&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129844&page=function.session-start&vote=down "Vote down!")

0


[**_polygon dot co dot in at gmail dot com_**](https://www.php.net/manual/en/function.session-start.php#129844) [¶](https://www.php.net/manual/en/function.session-start.php#129844)

**11 months ago**

`<?php
session_start([\
    'read_and_close'  => true,\
]);
?>
The read_and_close option I believed was to work as a read only mode session
To the surprise it works even if no sessionId cookie is present in the http request and generates a new sessionId.
Secondly, the function with this option also generates new session files with respect to the newly generated sessionId
Third, if the sessionId is invalid (no file is present with respect to sessionId) it creates a new one.`

[up](https://www.php.net/manual/vote-note.php?id=129579&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129579&page=function.session-start&vote=down "Vote down!")

0


[**_theking2(at)king.ma_**](https://www.php.net/manual/en/function.session-start.php#129579) [¶](https://www.php.net/manual/en/function.session-start.php#129579)

**1 year ago**

`I generally use this to start a new session
<?php
    session_start( [\
        'name' => DEBUG ? 'SessionId' : '__Secure-SessionId',\
        'cookie_lifetime' => 0,\
        'cookie_path' => '/',\
        'cookie_secure' => true,\
        'cookie_httponly' => true,\
        'cookie_samesite' => 'Strict',\
        'sid_length' => 96,\
        'sid_bits_per_character' => 5,\
        'use_strict_mode' => true,\
        'referer_check' => $_SERVER['HTTP_HOST'],\
    ] );
?>
which will create a session with increased entropy in the session cookie name, requires a secure session, make sure roque refers have no chance at my logon page among other things.
According to MDN[1] prefix "__Secure-" must be set for secure sessions.
[1]( [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie))`

[up](https://www.php.net/manual/vote-note.php?id=120497&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120497&page=function.session-start&vote=down "Vote down!")

0


[**_chris at ocproducts dot com_**](https://www.php.net/manual/en/function.session-start.php#120497) [¶](https://www.php.net/manual/en/function.session-start.php#120497)

**8 years ago**

`Initiating a session may overwrite your own custom cache control header, which may break clicking back to get back to a prior post request (on Chrome at least).
On my system it was setting 'no-store', which is much more severe than 'no-cache' and what was breaking the back-button.
If you are controlling your own cache headers carefully you need to call:
session_cache_limiter('');
...to stop it changing your cache control headers.`

[up](https://www.php.net/manual/vote-note.php?id=118561&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118561&page=function.session-start&vote=down "Vote down!")

0


[**_fabmlk at hotmail dot com_**](https://www.php.net/manual/en/function.session-start.php#118561) [¶](https://www.php.net/manual/en/function.session-start.php#118561)

**9 years ago**

`If you ever need to open multiple distinct sessions in the same script and still let PHP generate session ids for you, here is a simple function I came up with (PHP default session handler is assumed):
<?php
/**
* Switch to or transparently create session with name $name.
* It can easily be expanded to manage different sessions lifetime.
*/
function session_switch($name = "PHPSESSID") {
        static $created_sessions = array();
        if (session_id() != '') { // if a session is currently opened, close it
            session_write_close();
        }
        session_name($name);
        if (isset($_COOKIE[$name])) {    // if a specific session already exists, merge with $created_sessions
            $created_sessions[$name] = $_COOKIE[$name];
        }
        if (isset($created_sessions[$name])) { // if existing session, impersonate it
            session_id($created_sessions[$name]);
            session_start();
        } else { // create new session
            session_start();
            $_SESSION = array(); // empty content before duplicating session file
                        // duplicate last session file with new id and current $_SESSION content
                        // If this is the first created session, there is nothing to duplicate from and passing true as argument will take care of "creating" only one session file
            session_regenerate_id(empty($created_sessions));
            $created_sessions[$name] = session_id();
        }
}
session_switch("SESSION1");
$_SESSION["key"] = "value1"; // specific to session 1
session_switch("SESSION2");
$_SESSION["key"] = "value2"; // specific to session 2
session_switch("SESSION1");
// back to session 1
// ...
?>
When using this function, session_start() should not be called on its own anymore (can be replaced with a call to session_switch() without argument).
Also remember that session_start() sets a Set-Cookie HTTP header on each call, so if you echo in-between sessions, wrap with ouput buffering.
Note: it's probably rarely a good idea to handle multiple sessions so think again if you think you have a good use for it.
Personally it played its role for some quick patching of legacy code I had to maintain.`

[up](https://www.php.net/manual/vote-note.php?id=95377&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95377&page=function.session-start&vote=down "Vote down!")

0


[**_info at nospam dot mmfilm dot sk_**](https://www.php.net/manual/en/function.session-start.php#95377) [¶](https://www.php.net/manual/en/function.session-start.php#95377)

**15 years ago**

`For those of you running in problems with UTF-8 encoded files:
I was getting an error because of the BOM, although i set Dreamweaver to "save as" the without the BOM. It appears that DW will not change this setting in already existing files. After creating a new file withou the BOM, everything worked well.
I also recommend [http://people.w3.org/rishida/utils/bomtester/index.php](http://people.w3.org/rishida/utils/bomtester/index.php) - a utility that remote checks for the presence of BOM.`

[up](https://www.php.net/manual/vote-note.php?id=121310&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121310&page=function.session-start&vote=down "Vote down!")

 -1


[**_axew3 at axew3 dot com_**](https://www.php.net/manual/en/function.session-start.php#121310) [¶](https://www.php.net/manual/en/function.session-start.php#121310)

**8 years ago**

`I need, with easy, count how many times the page reload over the site, may to add a warning popup, while the counter is 0 ...
session_start();
if(isset($_SESSION['count'])){
$count = $_SESSION['count'];
$count++;
$count = $_SESSION['count'] = $count;
} else {
    $count = $_SESSION['count'] = 0;
}
echo $count;
//session_destroy();`

[up](https://www.php.net/manual/vote-note.php?id=93673&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93673&page=function.session-start&vote=down "Vote down!")

 -1


[**_Charlie at NOSPAM dot example dot com_**](https://www.php.net/manual/en/function.session-start.php#93673) [¶](https://www.php.net/manual/en/function.session-start.php#93673)

**16 years ago**

`Be warned that depending on end of script to close the session will effectively serialize concurrent session requests.   Concurrent background "data retrieval" (e.g. applications such as AJAX or amfphp/Flex) expecting to retrieve data in parallel can fall into this trap easily.
Holding the session_write_close until after an expensive operation is likewise problematic.
To minimize effects, call session_write_close (aka session_commit) as early as practical (e.g. without introducing race conditions) or otherwise avoid the serialization bottleneck.`

[up](https://www.php.net/manual/vote-note.php?id=121311&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=121311&page=function.session-start&vote=down "Vote down!")

 -2


[**_axew3 at axew3 dot com_**](https://www.php.net/manual/en/function.session-start.php#121311) [¶](https://www.php.net/manual/en/function.session-start.php#121311)

**8 years ago**

`I just need with easy, count how many times the page reload over the site, may to add a warning popup, while the counter is 0:
session_start();
if(isset($_SESSION['count'])){
$count = $_SESSION['count'];
$count++;
$count = $_SESSION['count'] = $count;
} else {
    $count = $_SESSION['count'] = 0;
}
echo $count;
//session_destroy();`

[up](https://www.php.net/manual/vote-note.php?id=102254&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=102254&page=function.session-start&vote=down "Vote down!")

 -3


[**_anon at ymous dot com_**](https://www.php.net/manual/en/function.session-start.php#102254) [¶](https://www.php.net/manual/en/function.session-start.php#102254)

**14 years ago**

`I am trying to get a session created by a browser call to be used by a command line cli->curl php call (in this case, both calls to the same server and php.ini), for a set of flexible media import routines,
but the cli->curl call always starts a new session despite me putting PHPSESSID=validID as the first parameter for the url called by curl.
I was able to fix it by calling session_id($_GET['PHPSESSID']) before calling session_start() in the script called via curl.`

[up](https://www.php.net/manual/vote-note.php?id=126566&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126566&page=function.session-start&vote=down "Vote down!")

 -2


[**_polygon dot co dot in at gmail dot com_**](https://www.php.net/manual/en/function.session-start.php#126566) [¶](https://www.php.net/manual/en/function.session-start.php#126566)

**3 years ago**

`Websites are prone to Session Attack where its proper usage is not done.
There are tools like "Apache Benchmark" (ab) and many others which can hit the website with load for load / performance testing.
Code below starts the session for every request.
<?php
session_start();
$username = $_POST['username'];
$password = $_POST['password'];
if(isValidUser($username, $password)) {
    Suserdetails = getUserDetails($username);
    $_SESSION['user_id']    = Suserdetails['user_id'];
    $_SESSION['username']    = Suserdetails['username'];
    $_SESSION['firstname']    = Suserdetails['firstname'];
    header('Location: dashboard.php');
}
?>
This generates session file for every request irrespective of PHPSESSID cookie value when I use tools like ab, there by creating inode issue.
One should start the session after properly authenticating.
<?php
$username = $_POST['username'];
$password = $_POST['password'];
if(isValidUser($username, $password)) {
    Suserdetails = getUserDetails($username);
    session_start();
    $_SESSION['user_id']    = Suserdetails['user_id'];
    $_SESSION['username']    = Suserdetails['username'];
    $_SESSION['firstname']    = Suserdetails['firstname'];
    header('Location: dashboard.php');
}
?>
Scripts other then login first validates session which requires session.
<?php
    if(session_status()!=PHP_SESSION_NONE)  header('Location: login.php');
    session_start();
    if(!isset($_SESSION['user_id'])) header('Location: login.php');
    code logic below....
}
?>
This example is for file based session.
For other modes of session check function session_set_save_handler.`

[up](https://www.php.net/manual/vote-note.php?id=105447&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105447&page=function.session-start&vote=down "Vote down!")

 -4


[**_sanjuro at 1up-games dot com_**](https://www.php.net/manual/en/function.session-start.php#105447) [¶](https://www.php.net/manual/en/function.session-start.php#105447)

**14 years ago**

`The problem with SID is that if on occasions you don't start a session, instead of outputting an empty string for transparent integration it will return the regular undefined constant notice. So you might want to test the constant with defined() beforehand.`

[up](https://www.php.net/manual/vote-note.php?id=96491&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96491&page=function.session-start&vote=down "Vote down!")

 -5


[**_info.at.merchandisinginteractive.sk_**](https://www.php.net/manual/en/function.session-start.php#96491) [¶](https://www.php.net/manual/en/function.session-start.php#96491)

**15 years ago**

`A handy script that checks fot the presence of uft-8 byte order mark (BOM) in all files in all directories starting on current dir. Combined from the work of other people here...
<?php
function fopen_utf8 ($filename) {
    $file = @fopen($filename, "r");
    $bom = fread($file, 3);
    if ($bom != b"\xEF\xBB\xBF")
    {
        return false;
    }
    else
    {
        return true;
    }
}
function file_array($path, $exclude = ".|..|design", $recursive = true) {
    $path = rtrim($path, "/") . "/";
    $folder_handle = opendir($path);
    $exclude_array = explode("|", $exclude);
    $result = array();
    while(false !== ($filename = readdir($folder_handle))) {
        if(!in_array(strtolower($filename), $exclude_array)) {
            if(is_dir($path . $filename . "/")) {
                                // Need to include full "path" or it's an infinite loop
                if($recursive) $result[] = file_array($path . $filename . "/", $exclude, true);
            } else {
                if ( fopen_utf8($path . $filename) )
                {
                    //$result[] = $filename;
                    echo ($path . $filename . "<br>");
                }
            }
        }
    }
    return $result;
}
$files = file_array(".");
?>`

[up](https://www.php.net/manual/vote-note.php?id=33369&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=33369&page=function.session-start&vote=down "Vote down!")

 -5


[**_m dot kuiphuis at hccnet dot nl_**](https://www.php.net/manual/en/function.session-start.php#33369) [¶](https://www.php.net/manual/en/function.session-start.php#33369)

**22 years ago**

`[Editors Note: For more information about this\
[http://www.zvon.org/tmRFC/RFC882/Output/chapter5.html](http://www.zvon.org/tmRFC/RFC882/Output/chapter5.html) ]

I use name-based virtual hosting on Linux with Apache and PHP 4.3.2.
Every time when I refreshed (by pressing F5 in Internet Explorer) I noticed that I got a new session_id. Simultaneously browsing the same site with Netscape didn't give me that problem. First I thought this was some PHP issue (before I tested it with Netscape), but after searching a lot on the internet I found the problem.
Since I was using name based virtual hosting for my testserver and we have different webshops for different customers I used the syntax webshop_customername.servername.nl as the domain-name.
The _ in the domain name seemed to be the problem. Internet Explorer just denies setting the cookie on the client when there is a special character (like an _ ) in the domain name. For more information regarding this issue: [http://support.microsoft.com/default.aspx?scid=kb;EN-US;316112](http://support.microsoft.com/default.aspx?scid=kb;EN-US;316112)
Stupidly enough, this information was related to asp (yuk :o)`

[up](https://www.php.net/manual/vote-note.php?id=92356&page=function.session-start&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=92356&page=function.session-start&vote=down "Vote down!")

 -4


[**_dstuff at brainsware dot org_**](https://www.php.net/manual/en/function.session-start.php#92356) [¶](https://www.php.net/manual/en/function.session-start.php#92356)

**16 years ago**

`It seems like spaces in the name don't work either - got a new session id generated each time`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.session-start&repo=en&redirect=https://www.php.net/manual/en/function.session-start.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google