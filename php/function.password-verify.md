---
url: https://www.php.net/manual/en/function.password-verify.php
scraped_at: 2025-10-20T03:00:39.675Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# password\_verify

(PHP 5 >= 5.5.0, PHP 7, PHP 8)

password\_verify — Verifies that a password matches a hash

### Description [¶](https://www.php.net/manual/en/function.password-verify.php\#refsect1-function.password-verify-description)

**password\_verify**([#\[\\SensitiveParameter\]](https://www.php.net/manual/en/class.sensitiveparameter.php)[string](https://www.php.net/manual/en/language.types.string.php) `$password`, [string](https://www.php.net/manual/en/language.types.string.php) `$hash`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Verifies that the given hash matches the given password.
**password\_verify()** is compatible with [crypt()](https://www.php.net/manual/en/function.crypt.php).
Therefore, password hashes created by [crypt()](https://www.php.net/manual/en/function.crypt.php) can be used with
**password\_verify()**.


Note that [password\_hash()](https://www.php.net/manual/en/function.password-hash.php) returns the algorithm, cost and salt
as part of the returned hash. Therefore, all information that's needed to verify
the hash is included in it. This allows the verify function to verify the hash
without needing separate storage for the salt or algorithm information.


This function is safe against timing attacks.


### Parameters [¶](https://www.php.net/manual/en/function.password-verify.php\#refsect1-function.password-verify-parameters)

`password`

The user's password.


`hash`

A hash created by [password\_hash()](https://www.php.net/manual/en/function.password-hash.php).


### Return Values [¶](https://www.php.net/manual/en/function.password-verify.php\#refsect1-function.password-verify-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if the password and hash match, or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.


### Examples [¶](https://www.php.net/manual/en/function.password-verify.php\#refsect1-function.password-verify-examples)

**Example #1 **password\_verify()** example**

This is a simplified example; it is recommended to rehash a correct password
if necessary; see [password\_needs\_rehash()](https://www.php.net/manual/en/function.password-needs-rehash.php) for an example.


`<?php
// See the password_hash() example to see where this came from.
$hash = '$2y$12$4Umg0rCJwMswRw/l.SwHvuQV01coP0eWmGzd61QH2RvAOMANUBGC.';
if (password_verify('rasmuslerdorf', $hash)) {
    echo 'Password is valid!';
} else {
    echo 'Invalid password.';
}
?>`

The above example will output:

```
Password is valid!
```

### See Also [¶](https://www.php.net/manual/en/function.password-verify.php\#refsect1-function.password-verify-seealso)

- [password\_needs\_rehash()](https://www.php.net/manual/en/function.password-needs-rehash.php) \- Checks if the given hash matches the given options
- [password\_hash()](https://www.php.net/manual/en/function.password-hash.php) \- Creates a password hash
- [sodium\_crypto\_pwhash\_str\_verify()](https://www.php.net/manual/en/function.sodium-crypto-pwhash-str-verify.php) \- Verifies that a password matches a hash

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/password/functions/password-verify.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.password-verify%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.password-verify&repo=en&redirect=https://www.php.net/manual/en/function.password-verify.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google