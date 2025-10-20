---
url: https://www.php.net/manual/en/function.session-id.php
scraped_at: 2025-10-20T02:53:58.100Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# session\_id

(PHP 4, PHP 5, PHP 7, PHP 8)

session\_id — Get and/or set the current session id

### Description [¶](https://www.php.net/manual/en/function.session-id.php\#refsect1-function.session-id-description)

**session\_id**([?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$id` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

**session\_id()** is used to get or set the session id for
the current session.


The constant **`[SID](https://www.php.net/manual/en/session.constants.php#constant.sid)`** can also be used to
retrieve the current name and session id as a string suitable for
adding to URLs. See also [Session\\
handling](https://www.php.net/manual/en/ref.session.php).


### Parameters [¶](https://www.php.net/manual/en/function.session-id.php\#refsect1-function.session-id-parameters)

`id`

If `id` is specified and not **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, it will replace the current
session id. **session\_id()** needs to be called before
[session\_start()](https://www.php.net/manual/en/function.session-start.php) for that purpose. Depending on the
session handler, not all characters are allowed within the session id.
For example, the file session handler only allows characters in the
range `[a-zA-Z0-9,-]`!


> **Note**:
>
> When using session cookies, specifying an `id`
> for **session\_id()** will always send a new cookie
> when [session\_start()](https://www.php.net/manual/en/function.session-start.php) is called, regardless if the
> current session id is identical to the one being set.

### Return Values [¶](https://www.php.net/manual/en/function.session-id.php\#refsect1-function.session-id-returnvalues)

**session\_id()** returns the session id for the current
session or the empty string ( `""`) if there is no current
session (no current session id exists).
On failure, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** is returned.


### Changelog [¶](https://www.php.net/manual/en/function.session-id.php\#refsect1-function.session-id-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | `id` is nullable now. |

### See Also [¶](https://www.php.net/manual/en/function.session-id.php\#refsect1-function.session-id-seealso)

- [session\_regenerate\_id()](https://www.php.net/manual/en/function.session-regenerate-id.php) \- Update the current session id with a newly generated one
- [session\_start()](https://www.php.net/manual/en/function.session-start.php) \- Start new or resume existing session
- [session\_set\_save\_handler()](https://www.php.net/manual/en/function.session-set-save-handler.php) \- Sets user-level session storage functions
- [session.save\_handler](https://www.php.net/manual/en/session.configuration.php#ini.session.save-handler)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/session/functions/session-id.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.session-id%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.session-id&repo=en&redirect=https://www.php.net/manual/en/function.session-id.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=116836&page=function.session-id&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116836&page=function.session-id&vote=down "Vote down!")

44


[**_Riikka K_**](https://www.php.net/manual/en/function.session-id.php#116836) [¶](https://www.php.net/manual/en/function.session-id.php#116836)

**10 years ago**

`It may be good to note that PHP does not allow arbitrary session ids. The session id validation in PHP source is defined in ext/session/session.c in the function php_session_valid_key:
[https://github.com/php/php-src/blob/master/ext/session/session.c](https://github.com/php/php-src/blob/master/ext/session/session.c)
To put it short, a valid session id may consists of digits, letters A to Z (both upper and lower case), comma and dash. Described as a character class, it would be [-,a-zA-Z0-9]. A valid session id may have the length between 1 and 128 characters. To validate session ids, the easiest way to do it use a function like:
<?php
function session_valid_id($session_id)
{
    return preg_match('/^[-,a-zA-Z0-9]{1,128}$/', $session_id) > 0;
}
?>
session_id() itself will happily accept invalid session ids, but if you try to start a session using an invalid id, you will get the following error:
Warning: session_start(): The session id is too long or contains illegal characters, valid characters are a-z, A-Z, 0-9 and '-,'`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.session-id&repo=en&redirect=https://www.php.net/manual/en/function.session-id.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google