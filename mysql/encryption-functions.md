---
url: https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html
scraped_at: 2025-10-20T03:01:58.487Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html "Hide Sidebar")

[Previous: Bit Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/bit-functions.html "Previous: Bit Functions and Operators")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html "Up: Functions and Operators")[Next: Locking Functions](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html "Next: Locking Functions")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html)

[PDF (US Ltr)](https://downloads.mysql.com/docs/refman-8.0-en.pdf)
\- 43.3Mb

[PDF (A4)](https://downloads.mysql.com/docs/refman-8.0-en.a4.pdf)
\- 43.4Mb

[Man Pages (TGZ)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.tar.gz)
\- 297.2Kb

[Man Pages (Zip)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.zip)
\- 402.4Kb

[Info (Gzip)](https://downloads.mysql.com/docs/mysql-8.0.info.gz)
\- 4.3Mb

[Info (Zip)](https://downloads.mysql.com/docs/mysql-8.0.info.zip)
\- 4.3Mb

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html)

[MySQL Backup and Recovery](https://dev.mysql.com/doc/mysql-backup-excerpt/8.0/en/)

[MySQL Globalization](https://dev.mysql.com/doc/mysql-g11n-excerpt/8.0/en/)

[MySQL Information Schema](https://dev.mysql.com/doc/mysql-infoschema-excerpt/8.0/en/)

[MySQL Installation Guide](https://dev.mysql.com/doc/mysql-installation-excerpt/8.0/en/)

[Security in MySQL](https://dev.mysql.com/doc/mysql-security-excerpt/8.0/en/)

[Starting and Stopping MySQL](https://dev.mysql.com/doc/mysql-startstop-excerpt/8.0/en/)

[MySQL and Linux/Unix](https://dev.mysql.com/doc/mysql-linuxunix-excerpt/8.0/en/)

[MySQL and Windows](https://dev.mysql.com/doc/mysql-windows-excerpt/8.0/en/)

[MySQL and macOS](https://dev.mysql.com/doc/mysql-macos-excerpt/8.0/en/)

[MySQL and Solaris](https://dev.mysql.com/doc/mysql-solaris-excerpt/8.0/en/)

[Building MySQL from Source](https://dev.mysql.com/doc/mysql-sourcebuild-excerpt/8.0/en/)

[MySQL Restrictions and Limitations](https://dev.mysql.com/doc/mysql-reslimits-excerpt/8.0/en/)

[MySQL Partitioning](https://dev.mysql.com/doc/mysql-partitioning-excerpt/8.0/en/)

[MySQL Tutorial](https://dev.mysql.com/doc/mysql-tutorial-excerpt/8.0/en/)

[MySQL Performance Schema](https://dev.mysql.com/doc/mysql-perfschema-excerpt/8.0/en/)

[MySQL Replication](https://dev.mysql.com/doc/mysql-replication-excerpt/8.0/en/)

[Using the MySQL Yum Repository](https://dev.mysql.com/doc/mysql-repo-excerpt/8.0/en/)

[MySQL NDB Cluster 8.0](https://dev.mysql.com/doc/mysql-cluster-excerpt/8.0/en/)

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/encryption-functions.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/encryption-functions.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/encryption-functions.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/encryption-functions.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/encryption-functions.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/encryption-functions.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/encryption-functions.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/encryption-functions.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html)  /
Encryption and Compression Functions


## 14.13 Encryption and Compression Functions

**Table 14.18 Encryption Functions**

| Name | Description |
| --- | --- |
| [`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt) | Decrypt using AES |
| [`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) | Encrypt using AES |
| [`COMPRESS()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_compress) | Return result as a binary string |
| [`MD5()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_md5) | Calculate MD5 checksum |
| [`RANDOM_BYTES()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_random-bytes) | Return a random byte vector |
| [`SHA1()`, `SHA()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha1) | Calculate an SHA-1 160-bit checksum |
| [`SHA2()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha2) | Calculate an SHA-2 checksum |
| [`STATEMENT_DIGEST()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_statement-digest) | Compute statement digest hash value |
| [`STATEMENT_DIGEST_TEXT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_statement-digest-text) | Compute normalized statement digest |
| [`UNCOMPRESS()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_uncompress) | Uncompress a string compressed |
| [`UNCOMPRESSED_LENGTH()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_uncompressed-length) | Return the length of a string before compression |
| [`VALIDATE_PASSWORD_STRENGTH()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_validate-password-strength) | Determine strength of password |

Many encryption and compression functions return strings for which
the result might contain arbitrary byte values. If you want to
store these results, use a column with a
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types") or
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") binary string data type. This
avoids potential problems with trailing space removal or character
set conversion that would change data values, such as may occur if
you use a nonbinary string data type
( [`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types")).


Some encryption functions return strings of ASCII characters:
[`MD5()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_md5),
[`SHA()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha1),
[`SHA1()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha1),
[`SHA2()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha2),
[`STATEMENT_DIGEST()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_statement-digest),
[`STATEMENT_DIGEST_TEXT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_statement-digest-text). Their
return value is a string that has a character set and collation
determined by the
[`character_set_connection`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_character_set_connection) and
[`collation_connection`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_collation_connection) system
variables. This is a nonbinary string unless the character set is
`binary`.


If an application stores values from a function such as
[`MD5()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_md5) or
[`SHA1()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha1) that returns a string of hex
digits, more efficient storage and comparisons can be obtained by
converting the hex representation to binary using
[`UNHEX()`](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html#function_unhex) and storing the result in a
[`BINARY(N)`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types")
column. Each pair of hexadecimal digits requires one byte in
binary form, so the value of _`N`_ depends
on the length of the hex string. _`N`_ is
16 for an [`MD5()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_md5) value and 20 for a
[`SHA1()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha1) value. For
[`SHA2()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha2),
_`N`_ ranges from 28 to 32 depending on the
argument specifying the desired bit length of the result.


The size penalty for storing the hex string in a
[`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") column is at least two times,
up to eight times if the value is stored in a column that uses the
`utf8mb4` character set (where each character
uses 4 bytes). Storing the string also results in slower
comparisons because of the larger values and the need to take
character set collation rules into account.


Suppose that an application stores
[`MD5()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_md5) string values in a
[`CHAR(32)`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") column:


```sql
CREATE TABLE md5_tbl (md5_val CHAR(32), ...);
INSERT INTO md5_tbl (md5_val, ...) VALUES(MD5('abcdef'), ...);
```

To convert hex strings to more compact form, modify the
application to use [`UNHEX()`](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html#function_unhex) and
[`BINARY(16)`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types") instead as follows:


```sql
CREATE TABLE md5_tbl (md5_val BINARY(16), ...);
INSERT INTO md5_tbl (md5_val, ...) VALUES(UNHEX(MD5('abcdef')), ...);
```

Applications should be prepared to handle the very rare case that
a hashing function produces the same value for two different input
values. One way to make collisions detectable is to make the hash
column a primary key.

Note

Exploits for the MD5 and SHA-1 algorithms have become known. You
may wish to consider using another one-way encryption function
described in this section instead, such as
[`SHA2()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha2).

Caution

Passwords or other sensitive values supplied as arguments to
encryption functions are sent as cleartext to the MySQL server
unless an SSL connection is used. Also, such values appear in
any MySQL logs to which they are written. To avoid these types
of exposure, applications can encrypt sensitive values on the
client side before sending them to the server. The same
considerations apply to encryption keys. To avoid exposing
these, applications can use stored procedures to encrypt and
decrypt values on the server side.

- [`AES_DECRYPT(crypt_str,key_str[,init_vector][,kdf_name][,salt][,info\\
            | iterations])`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt)


This function decrypts data using the official AES (Advanced
Encryption Standard) algorithm. For more information, see the
description of [`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt).



Statements that use
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt) are unsafe for
statement-based replication.


- [`AES_ENCRYPT(str,key_str[,init_vector][,kdf_name][,salt][,info\\
            | iterations])`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt)

[`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) and
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt) implement
encryption and decryption of data using the official AES
(Advanced Encryption Standard) algorithm, previously known as
“Rijndael.” The AES standard permits various key
lengths. By default these functions implement AES with a
128-bit key length. Key lengths of 196 or 256 bits can be
used, as described later. The key length is a trade off
between performance and security.


[`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) encrypts the
string _`str`_ using the key string
_`key_str`_, and returns a binary
string containing the encrypted output.
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt) decrypts the
encrypted string _`crypt_str`_ using
the key string _`key_str`_, and returns
the original (binary) string in hexadecimal format. (To obtain
the string as plaintext, cast the result to
`CHAR`. Alternatively, start the
[**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client with
[`--skip-binary-as-hex`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_binary-as-hex)
to cause all binary values to be displayed as text.) If either
function argument is `NULL`, the function
returns `NULL`. If
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt) detects invalid
data or incorrect padding, it returns `NULL`.
However, it is possible for
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt) to return a
non- `NULL` value (possibly garbage) if the
input data or the key is invalid.



As of MySQL 8.0.30, these functions support the use of a key
derivation function (KDF) to create a cryptographically strong
secret key from the information passed in
_`key_str`_. The derived key is used to
encrypt and decrypt the data, and it remains in the MySQL
Server instance and is not accessible to users. Using a KDF is
highly recommended, as it provides better security than
specifying your own premade key or deriving it by a simpler
method as you use the function. The functions support HKDF
(available from OpenSSL 1.1.0), for which you can specify an
optional salt and context-specific information to include in
the keying material, and PBKDF2 (available from OpenSSL
1.0.2), for which you can specify an optional salt and set the
number of iterations used to produce the key.


[`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) and
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt) permit control of
the block encryption mode. The
[`block_encryption_mode`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_block_encryption_mode) system
variable controls the mode for block-based encryption
algorithms. Its default value is
`aes-128-ecb`, which signifies encryption
using a key length of 128 bits and ECB mode. For a description
of the permitted values of this variable, see
[Section 7.1.8, “Server System Variables”](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html "7.1.8 Server System Variables"). The optional
_`init_vector`_ argument is used to
provide an initialization vector for block encryption modes
that require it.



Statements that use
[`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) or
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt) are unsafe for
statement-based replication.



If [`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) is invoked
from within the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client, binary
strings display using hexadecimal notation, depending on the
value of the [`--binary-as-hex`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_binary-as-hex).
For more information about that option, see
[Section 6.5.1, “mysql — The MySQL Command-Line Client”](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client").



The arguments for the
[`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) and
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt) functions are as
follows:


_`str`_


The string for
[`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) to encrypt
using the key string _`key_str`_,
or (from MySQL 8.0.30) the key derived from it by the
specified KDF. The string can be any length. Padding is
automatically added to _`str`_ so
it is a multiple of a block as required by block-based
algorithms such as AES. This padding is automatically
removed by the
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt) function.


_`crypt_str`_


The encrypted string for
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt) to decrypt
using the key string _`key_str`_,
or (from MySQL 8.0.30) the key derived from it by the
specified KDF. The string can be any length. The length
of _`crypt_str`_ can be
calculated from the length of the original string using
this formula:




```clike
16 * (trunc(string_length / 16) + 1)
```

_`key_str`_


The encryption key, or the input keying material that is
used as the basis for deriving a key using a key
derivation function (KDF). For the same instance of
data, use the same value of
_`key_str`_ for encryption with
[`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) and
decryption with
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt).





If you are using a KDF, which you can from MySQL 8.0.30,
_`key_str`_ can be any arbitrary
information such as a password or passphrase. In the
further arguments for the function, you specify the KDF
name, then add further options to increase the security
as appropriate for the KDF.





When you use a KDF, the function creates a
cryptographically strong secret key from the information
passed in _`key_str`_ and any
salt or additional information that you provide in the
other arguments. The derived key is used to encrypt and
decrypt the data, and it remains in the MySQL Server
instance and is not accessible to users. Using a KDF is
highly recommended, as it provides better security than
specifying your own premade key or deriving it by a
simpler method as you use the function.





If you are not using a KDF, for a key length of 128
bits, the most secure way to pass a key to the
_`key_str`_ argument is to create
a truly random 128-bit value and pass it as a binary
value. For example:




```sql
INSERT INTO t
VALUES (1,AES_ENCRYPT('text',UNHEX('F3229A0B371ED2D9441B830D21A390C3')));
```




A passphrase can be used to generate an AES key by
hashing the passphrase. For example:




```sql
INSERT INTO t
VALUES (1,AES_ENCRYPT('text', UNHEX(SHA2('My secret passphrase',512))));
```




If you exceed the maximum key length of 128 bits, a
warning is returned. If you are not using a KDF, do not
pass a password or passphrase directly to
_`key_str`_, hash it first.
Previous versions of this documentation suggested the
former approach, but it is no longer recommended as the
examples shown here are more secure.


_`init_vector`_


An initialization vector, for block encryption modes
that require it. The
[`block_encryption_mode`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_block_encryption_mode)
system variable controls the mode. For the same instance
of data, use the same value of
_`init_vector`_ for encryption
with [`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) and
decryption with
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt).







Note





If you are using a KDF, you must specify an
initialization vector or a null string for this
argument, in order to access the later arguments to
define the KDF.







For modes that require an initialization vector, it must
be 16 bytes or longer (bytes in excess of 16 are
ignored). An error occurs if
_`init_vector`_ is missing. For
modes that do not require an initialization vector, it
is ignored and a warning is generated if
_`init_vector`_ is specified,
unless you are using a KDF.





The default value for the
[`block_encryption_mode`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_block_encryption_mode)
system variable is `aes-128-ecb`, or
ECB mode, which does not require an initialization
vector. The alternative permitted block encryption modes
CBC, CFB1, CFB8, CFB128, and OFB all require an
initialization vector.





A random string of bytes to use for the initialization
vector can be produced by calling
[`RANDOM_BYTES(16)`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_random-bytes).


_`kdf_name`_


The name of the key derivation function (KDF) to create
a key from the input keying material passed in
_`key_str`_, and other arguments
as appropriate for the KDF. This optional argument is
available from MySQL 8.0.30.





For the same instance of data, use the same value of
_`kdf_name`_ for encryption with
[`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) and
decryption with
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt). When you
specify _`kdf_name`_, you must
specify _`init_vector`_, using
either a valid initialization vector, or a null string
if the encryption mode does not require an
initialization vector.





The following values are supported:




`hkdf`


HKDF, which is available from OpenSSL 1.1.0. HKDF
extracts a pseudorandom key from the keying
material then expands it into additional keys.
With HKDF, you can specify an optional salt
( _`salt`_) and
context-specific information such as application
details ( _`info`_) to
include in the keying material.


`pbkdf2_hmac`


PBKDF2, which is available from OpenSSL 1.0.2.
PBKDF2 applies a pseudorandom function to the
keying material, and repeats this process a large
number of times to produce the key. With PBKDF2,
you can specify an optional salt
( _`salt`_) to include in
the keying material, and set the number of
iterations used to produce the key
( _`iterations`_).







In this example, HKDF is specified as the key derivation
function, and a salt and context information are
provided. The argument for the initialization vector is
included but is the empty string:




```sql
SELECT AES_ENCRYPT('mytext','mykeystring', '', 'hkdf', 'salt', 'info');
```




In this example, PBKDF2 is specified as the key
derivation function, a salt is provided, and the number
of iterations is doubled from the recommended minimum:




```sql
SELECT AES_ENCRYPT('mytext','mykeystring', '', 'pbkdf2_hmac','salt', '2000');
```

_`salt`_


A salt to be passed to the key derivation function
(KDF). This optional argument is available from MySQL
8.0.30. Both HKDF and PBKDF2 can use salts, and their
use is recommended to help prevent attacks based on
dictionaries of common passwords or rainbow tables.





A salt consists of random data, which for security must
be different for each encryption operation. A random
string of bytes to use for the salt can be produced by
calling [`RANDOM_BYTES()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_random-bytes).
This example produces a 64-bit salt:




```sql
SET @salt = RANDOM_BYTES(8);
```




For the same instance of data, use the same value of
_`salt`_ for encryption with
[`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) and
decryption with
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt). The salt
can safely be stored along with the encrypted data.


_`info`_


Context-specific information for HKDF to include in the
keying material, such as information about the
application. This optional argument is available from
MySQL 8.0.30 when you specify `hkdf` as
the KDF name. HKDF adds this information to the keying
material specified in _`key_str`_
and the salt specified in
_`salt`_ to produce the key.





For the same instance of data, use the same value of
_`info`_ for encryption with
[`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) and
decryption with
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt).


_`iterations`_


The iteration count for PBKDF2 to use when producing the
key. This optional argument is available from MySQL
8.0.30 when you specify `pbkdf2_hmac`
as the KDF name. A higher count gives greater resistance
to brute-force attacks because it has a greater
computational cost for the attacker, but the same is
necessarily true for the key derivation process. The
default if you do not specify this argument is 1000,
which is the minimum recommended by the OpenSSL
standard.





For the same instance of data, use the same value of
_`iterations`_ for encryption
with [`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) and
decryption with
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt).







```sql
mysql> SET block_encryption_mode = 'aes-256-cbc';
mysql> SET @key_str = SHA2('My secret passphrase',512);
mysql> SET @init_vector = RANDOM_BYTES(16);
mysql> SET @crypt_str = AES_ENCRYPT('text',@key_str,@init_vector);
mysql> SELECT CAST(AES_DECRYPT(@crypt_str,@key_str,@init_vector) AS CHAR);
+-------------------------------------------------------------+
| CAST(AES_DECRYPT(@crypt_str,@key_str,@init_vector) AS CHAR) |
+-------------------------------------------------------------+
| text                                                        |
+-------------------------------------------------------------+
```

- [`COMPRESS(string_to_compress)`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_compress)


Compresses a string and returns the result as a binary string.
This function requires MySQL to have been compiled with a
compression library such as `zlib`.
Otherwise, the return value is always `NULL`.
The return value is also `NULL` if
_`string_to_compress`_ is
`NULL`. The compressed string can be
uncompressed with [`UNCOMPRESS()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_uncompress).



```sql
mysql> SELECT LENGTH(COMPRESS(REPEAT('a',1000)));
          -> 21
mysql> SELECT LENGTH(COMPRESS(''));
          -> 0
mysql> SELECT LENGTH(COMPRESS('a'));
          -> 13
mysql> SELECT LENGTH(COMPRESS(REPEAT('a',16)));
          -> 15
```



The compressed string contents are stored the following way:




- Empty strings are stored as empty strings.


- Nonempty strings are stored as a 4-byte length of the
uncompressed string (low byte first), followed by the
compressed string. If the string ends with space, an extra
`.` character is added to avoid problems
with endspace trimming should the result be stored in a
[`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") or
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") column. (However,
use of nonbinary string data types such as
[`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") or
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types") to store compressed
strings is not recommended anyway because character set
conversion may occur. Use a
[`VARBINARY`](https://dev.mysql.com/doc/refman/8.0/en/binary-varbinary.html "13.3.3 The BINARY and VARBINARY Types") or
[`BLOB`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") binary string column
instead.)


If [`COMPRESS()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_compress) is invoked from
within the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client, binary strings
display using hexadecimal notation, depending on the value of
the [`--binary-as-hex`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_binary-as-hex). For more
information about that option, see [Section 6.5.1, “mysql — The MySQL Command-Line Client”](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client").


- [`MD5(str)`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_md5)


Calculates an MD5 128-bit checksum for the string. The value
is returned as a string of 32 hexadecimal digits, or
`NULL` if the argument was
`NULL`. The return value can, for example, be
used as a hash key. See the notes at the beginning of this
section about storing hash values efficiently.



The return value is a string in the connection character set.



If FIPS mode is enabled,
`MD5()` returns
`NULL`. See [Section 8.8, “FIPS Support”](https://dev.mysql.com/doc/refman/8.0/en/fips-mode.html "8.8 FIPS Support").



```sql
mysql> SELECT MD5('testing');
          -> 'ae2b1fca515949e5d54fb22b8ed95575'
```



This is the “RSA Data Security, Inc. MD5 Message-Digest
Algorithm.”


See the note regarding the MD5 algorithm at the beginning this
section.


- [`RANDOM_BYTES(len)`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_random-bytes)


This function returns a binary string of
_`len`_ random bytes generated using
the random number generator of the SSL library. Permitted
values of _`len`_ range from 1 to 1024.
For values outside that range, an error occurs. Returns
`NULL` if _`len`_ is
`NULL`.


[`RANDOM_BYTES()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_random-bytes) can be used to
provide the initialization vector for the
[`AES_DECRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-decrypt) and
[`AES_ENCRYPT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_aes-encrypt) functions. For
use in that context, _`len`_ must be at
least 16. Larger values are permitted, but bytes in excess of
16 are ignored.


[`RANDOM_BYTES()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_random-bytes) generates a
random value, which makes its result nondeterministic.
Consequently, statements that use this function are unsafe for
statement-based replication.



If [`RANDOM_BYTES()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_random-bytes) is invoked
from within the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") client, binary
strings display using hexadecimal notation, depending on the
value of the [`--binary-as-hex`](https://dev.mysql.com/doc/refman/8.0/en/mysql-command-options.html#option_mysql_binary-as-hex).
For more information about that option, see
[Section 6.5.1, “mysql — The MySQL Command-Line Client”](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client").


- [`SHA1(str)`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha1),
[`SHA(str)`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha1)


Calculates an SHA-1 160-bit checksum for the string, as
described in RFC 3174 (Secure Hash Algorithm). The value is
returned as a string of 40 hexadecimal digits, or
`NULL` if the argument is
`NULL`. One of the possible uses for this
function is as a hash key. See the notes at the beginning of
this section about storing hash values efficiently.
[`SHA()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha1) is
synonymous with [`SHA1()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha1).



The return value is a string in the connection character set.



```sql
mysql> SELECT SHA1('abc');
          -> 'a9993e364706816aba3e25717850c26c9cd0d89d'
```


[`SHA1()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha1) can be considered a
cryptographically more secure equivalent of
[`MD5()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_md5). However, see the note
regarding the MD5 and SHA-1 algorithms at the beginning this
section.


- [`SHA2(str,\\
            hash_length)`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha2)


Calculates the SHA-2 family of hash functions (SHA-224,
SHA-256, SHA-384, and SHA-512). The first argument is the
plaintext string to be hashed. The second argument indicates
the desired bit length of the result, which must have a value
of 224, 256, 384, 512, or 0 (which is equivalent to 256). If
either argument is `NULL` or the hash length
is not one of the permitted values, the return value is
`NULL`. Otherwise, the function result is a
hash value containing the desired number of bits. See the
notes at the beginning of this section about storing hash
values efficiently.



The return value is a string in the connection character set.



```sql
mysql> SELECT SHA2('abc', 224);
          -> '23097d223405d8228642a477bda255b32aadbce4bda0b3f7e36c9da7'
```



This function works only if MySQL has been configured with SSL
support. See [Section 8.3, “Using Encrypted Connections”](https://dev.mysql.com/doc/refman/8.0/en/encrypted-connections.html "8.3 Using Encrypted Connections").


[`SHA2()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha2) can be considered
cryptographically more secure than
[`MD5()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_md5) or
[`SHA1()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_sha1).


- [`STATEMENT_DIGEST(statement)`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_statement-digest)


Given an SQL statement as a string, returns the statement
digest hash value as a string in the connection character set,
or `NULL` if the argument is
`NULL`. The related
[`STATEMENT_DIGEST_TEXT()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_statement-digest-text)
function returns the normalized statement digest. For
information about statement digesting, see
[Section 29.10, “Performance Schema Statement Digests and Sampling”](https://dev.mysql.com/doc/refman/8.0/en/performance-schema-statement-digests.html "29.10 Performance Schema Statement Digests and Sampling").



Both functions use the MySQL parser to parse the statement. If
parsing fails, an error occurs. The error message includes the
parse error only if the statement is provided as a literal
string.



The [`max_digest_length`](https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_max_digest_length) system
variable determines the maximum number of bytes available to
these functions for computing normalized statement digests.



```sql
mysql> SET @stmt = 'SELECT * FROM mytable WHERE cola = 10 AND colb = 20';
mysql> SELECT STATEMENT_DIGEST(@stmt);
+------------------------------------------------------------------+
| STATEMENT_DIGEST(@stmt)                                          |
+------------------------------------------------------------------+
| 3bb95eeade896657c4526e74ff2a2862039d0a0fe8a9e7155b5fe492cbd78387 |
+------------------------------------------------------------------+
mysql> SELECT STATEMENT_DIGEST_TEXT(@stmt);
+----------------------------------------------------------+
| STATEMENT_DIGEST_TEXT(@stmt)                             |
+----------------------------------------------------------+
| SELECT * FROM `mytable` WHERE `cola` = ? AND `colb` = ?  |
+----------------------------------------------------------+
```

- [`STATEMENT_DIGEST_TEXT(statement)`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_statement-digest-text)


Given an SQL statement as a string, returns the normalized
statement digest as a string in the connection character set,
or `NULL` if the argument is
`NULL`. For additional discussion and
examples, see the description of the related
[`STATEMENT_DIGEST()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_statement-digest) function.


- [`UNCOMPRESS(string_to_uncompress)`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_uncompress)


Uncompresses a string compressed by the
[`COMPRESS()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_compress) function. If the
argument is not a compressed value, the result is
`NULL`; if
_`string_to_uncompress`_ is
`NULL`, the result is also
`NULL`. This function requires MySQL to have
been compiled with a compression library such as
`zlib`. Otherwise, the return value is always
`NULL`.



```sql
mysql> SELECT UNCOMPRESS(COMPRESS('any string'));
          -> 'any string'
mysql> SELECT UNCOMPRESS('any string');
          -> NULL
```

- [`UNCOMPRESSED_LENGTH(compressed_string)`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_uncompressed-length)


Returns the length that the compressed string had before being
compressed. Returns `NULL` if
_`compressed_string`_ is
`NULL`.



```sql
mysql> SELECT UNCOMPRESSED_LENGTH(COMPRESS(REPEAT('a',30)));
          -> 30
```

- [`VALIDATE_PASSWORD_STRENGTH(str)`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_validate-password-strength)


Given an argument representing a plaintext password, this
function returns an integer to indicate how strong the
password is, or `NULL` if the argument is
`NULL`. The return value ranges from 0 (weak)
to 100 (strong).



Password assessment by
[`VALIDATE_PASSWORD_STRENGTH()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_validate-password-strength) is
done by the `validate_password` component. If
that component is not installed, the function always returns
0\. For information about installing
`validate_password`, see
[Section 8.4.3, “The Password Validation Component”](https://dev.mysql.com/doc/refman/8.0/en/validate-password.html "8.4.3 The Password Validation Component"). To examine or configure
the parameters that affect password testing, check or set the
system variables implemented by
`validate_password`. See
[Section 8.4.3.2, “Password Validation Options and Variables”](https://dev.mysql.com/doc/refman/8.0/en/validate-password-options-variables.html "8.4.3.2 Password Validation Options and Variables").



The password is subjected to increasingly strict tests and the
return value reflects which tests were satisfied, as shown in
the following table. In addition, if the
[`validate_password.check_user_name`](https://dev.mysql.com/doc/refman/8.0/en/validate-password-options-variables.html#sysvar_validate_password.check_user_name)
system variable is enabled and the password matches the user
name,
[`VALIDATE_PASSWORD_STRENGTH()`](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html#function_validate-password-strength)
returns 0 regardless of how other
`validate_password` system variables are set.





| Password Test | Return Value |
| --- | --- |
| Length < 4 | 0 |
| Length ≥ 4 and <<br> [`validate_password.length`](https://dev.mysql.com/doc/refman/8.0/en/validate-password-options-variables.html#sysvar_validate_password.length) | 25 |
| Satisfies policy 1 ( `LOW`) | 50 |
| Satisfies policy 2 ( `MEDIUM`) | 75 |
| Satisfies policy 3 ( `STRONG`) | 100 |


[PREV](https://dev.mysql.com/doc/refman/8.0/en/bit-functions.html "Previous: Bit Functions and Operators") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/functions.html "Up: Functions and Operators") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/locking-functions.html "Next: Locking Functions")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html)

[PDF (US Ltr)](https://downloads.mysql.com/docs/refman-8.0-en.pdf)
\- 43.3Mb

[PDF (A4)](https://downloads.mysql.com/docs/refman-8.0-en.a4.pdf)
\- 43.4Mb

[Man Pages (TGZ)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.tar.gz)
\- 297.2Kb

[Man Pages (Zip)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.zip)
\- 402.4Kb

[Info (Gzip)](https://downloads.mysql.com/docs/mysql-8.0.info.gz)
\- 4.3Mb

[Info (Zip)](https://downloads.mysql.com/docs/mysql-8.0.info.zip)
\- 4.3Mb

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/encryption-functions.html)

[MySQL Backup and Recovery](https://dev.mysql.com/doc/mysql-backup-excerpt/8.0/en/)

[MySQL Globalization](https://dev.mysql.com/doc/mysql-g11n-excerpt/8.0/en/)

[MySQL Information Schema](https://dev.mysql.com/doc/mysql-infoschema-excerpt/8.0/en/)

[MySQL Installation Guide](https://dev.mysql.com/doc/mysql-installation-excerpt/8.0/en/)

[Security in MySQL](https://dev.mysql.com/doc/mysql-security-excerpt/8.0/en/)

[Starting and Stopping MySQL](https://dev.mysql.com/doc/mysql-startstop-excerpt/8.0/en/)

[MySQL and Linux/Unix](https://dev.mysql.com/doc/mysql-linuxunix-excerpt/8.0/en/)

[MySQL and Windows](https://dev.mysql.com/doc/mysql-windows-excerpt/8.0/en/)

[MySQL and macOS](https://dev.mysql.com/doc/mysql-macos-excerpt/8.0/en/)

[MySQL and Solaris](https://dev.mysql.com/doc/mysql-solaris-excerpt/8.0/en/)

[Building MySQL from Source](https://dev.mysql.com/doc/mysql-sourcebuild-excerpt/8.0/en/)

[MySQL Restrictions and Limitations](https://dev.mysql.com/doc/mysql-reslimits-excerpt/8.0/en/)

[MySQL Partitioning](https://dev.mysql.com/doc/mysql-partitioning-excerpt/8.0/en/)

[MySQL Tutorial](https://dev.mysql.com/doc/mysql-tutorial-excerpt/8.0/en/)

[MySQL Performance Schema](https://dev.mysql.com/doc/mysql-perfschema-excerpt/8.0/en/)

[MySQL Replication](https://dev.mysql.com/doc/mysql-replication-excerpt/8.0/en/)

[Using the MySQL Yum Repository](https://dev.mysql.com/doc/mysql-repo-excerpt/8.0/en/)

[MySQL NDB Cluster 8.0](https://dev.mysql.com/doc/mysql-cluster-excerpt/8.0/en/)