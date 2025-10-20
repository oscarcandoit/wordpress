---
url: https://www.php.net/manual/en/migration81.new-features.php
scraped_at: 2025-10-20T02:46:36.073Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## New Features [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features)

### PHP Core [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core)

#### Integer Octal Literal Prefix [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core.octal-literal-prefix)

Octal integers can now use an explicit
`0o`/ `0O`
prefix in integer literals,
similarly to binary and hexadecimal integer literals.


`<?php
014;  // Non-prefix octal literal
0o14; // Prefixed octal literal
?>`

#### Array Unpacking with String Keys [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core.unpacking-string-keys)

Added support for [array unpacking with strings keys](https://www.php.net/manual/en/language.types.array.php#language.types.array.unpacking).


`<?php
$arr1 = [1, 'a' => 'b'];
$arr2 = [...$arr1, 'c' => 'd']; //[1, 'a' => 'b', 'c' => 'd']
?>`

#### Named Argument After Argument Unpacking [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core.named-arg-after-unpack)

It is now possible to specify named arguments after an argument unpack.

e.g.
foo(...$args, named: $arg).


#### full-path Key for File Uploads [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core.upload-full-path-key)

File uploads now provide an additional `full_path` key,
which contains the full path (rather than just the basename) of the uploaded file.
This is intended for use in conjunction with "upload webkitdirectory".


#### Enumerations [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core.enums)

Support for [Enumerations](https://www.php.net/manual/en/language.enumerations.php) has been added.



#### Fibers [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core.fibers)

Support for [Fibers](https://www.php.net/manual/en/language.fibers.php) has been added.



#### First Class Callable Syntax [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core.callable-syntax)

Closures for callables can now be created using [the syntax `myFunc(...)`](https://www.php.net/manual/en/functions.first_class_callable_syntax.php),
which is identical to `Closure::fromCallable('myFunc')`.



> **Note**:
>
> The `...` is part of the syntax, and not an omission.

#### Intersection Types [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core.intersection-types)

Support for [intersection types](https://www.php.net/manual/en/language.types.type-system.php#language.types.type-system.composite.intersection) has been added.



**Caution**

[Intersection types](https://www.php.net/manual/en/language.types.type-system.php#language.types.type-system.composite.intersection) cannot be used together with
[union types](https://www.php.net/manual/en/language.types.declarations.php#language.types.declarations.composite.union)

#### Never type [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core.never-type)

A new return only type [never](https://www.php.net/manual/en/language.types.never.php) has been added.
This indicates that a function either [exit()](https://www.php.net/manual/en/function.exit.php),
throws an exception, or doesn't terminate.



#### [`new`](https://www.php.net/manual/en/language.oop5.basic.php\#language.oop5.basic.new) in Initializers [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core.new-in-initializer)

It is now possible to use `new ClassName()` expressions as the
default value of a parameter, static variable, global constant initializers,
and as attribute arguments.
Objects can also be passed to [define()](https://www.php.net/manual/en/function.define.php) now.



#### Readonly properties [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core.readonly)

Support for [readonly](https://www.php.net/manual/en/language.oop5.properties.php#language.oop5.properties.readonly-properties) has been added.



#### Final class constants [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.core.final-constants)

Added support for [the final modifier for class constants](https://www.php.net/manual/en/language.oop5.final.php#language.oop5.final.example.php81).
Also, interface constants become overridable by default.



### CURL [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.curl)

Added the **`[CURLOPT\_DOH\_URL](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-doh-url)`** option.


Added options for blob certificate when libcurl >= 7.71.0:


- **`[CURLOPT\_ISSUERCERT\_BLOB](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-issuercert-blob)`**
- **`[CURLOPT\_PROXY\_ISSUERCERT](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-proxy-issuercert)`**
- **`[CURLOPT\_PROXY\_ISSUERCERT\_BLOB](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-proxy-issuercert-blob)`**
- **`[CURLOPT\_PROXY\_SSLCERT\_BLOB](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-proxy-sslcert-blob)`**
- **`[CURLOPT\_PROXY\_SSLKEY\_BLOB](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-proxy-sslkey-blob)`**
- **`[CURLOPT\_SSLCERT\_BLOB](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-sslcert-blob)`**
- **`[CURLOPT\_SSLKEY\_BLOB](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-sslkey-blob)`**

Added [CURLStringFile](https://www.php.net/manual/en/class.curlstringfile.php), which can be used to post
a file from a [string](https://www.php.net/manual/en/language.types.string.php) rather than a file:


`<?php
$file = new CURLStringFile($data, 'filename.txt', 'text/plain');
curl_setopt($curl, CURLOPT_POSTFIELDS, ['file' => $file]);
?>`

### FPM [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.fpm)

Added openmetrics status format. It can be used by Prometheus to fetch FPM
metrics.


Added new pool option for the dynamic process manager called
`pm.max_spawn_rate`. It allows to start a number of children
at a faster rate when dynamic pm is selected.
The default value is `32` which was the previous
hard coded value.


### GD [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.gd)

Avif support is now available through
[imagecreatefromavif()](https://www.php.net/manual/en/function.imagecreatefromavif.php) and
[imageavif()](https://www.php.net/manual/en/function.imageavif.php),
if libgd has been built with Avif support.


### Hash [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.hash)

The following functions [hash()](https://www.php.net/manual/en/function.hash.php),
[hash\_file()](https://www.php.net/manual/en/function.hash-file.php), and [hash\_init()](https://www.php.net/manual/en/function.hash-init.php)
now support an additional optional `options`
argument, which can be used to pass algorithm specific data.


#### MurmurHash3 [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.hash.murmurhash3)

Added support for `MurmurHash3` with streaming
support. The following variants are implemented:


- murmur3a, 32-bit hash
- murmur3c, 128-bit hash for x86
- murmur3f, 128-bit hash for x64

The initial hash state can be passed through the `seed`
key in the `options` array, for example:



`<?php
$h = hash("murmur3f", $data, options: ["seed" => 42]);
echo $h, "\n";
?>`

A valid seed value is within the range from `0`
to the platform defined **`UINT_MAX`**, usually
`4294967295`.


#### xxHash [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.hash.xxhash)

Added support for `xxHash`.
The following variants are implemented:


- xxh32, 32-bit hash
- xxh64, 64-bit hash
- xxh3, 64-bit hash
- xxh128, 128-bit hash

The initial hash state can be passed through the `seed`
key in the `options` array, for example:



`<?php
$h = hash("xxh3", $data, options: ["seed" => 42]);
echo $h, "\n";
?>`

Secret usage is supported through passing the `secret`
key in the `options` array, too:



`<?php
$h = hash("xxh3", $data, options: ["secret" => "at least 136 bytes long secret here"]);
echo $h, "\n";
?>`

The quality of the custom secret is crucial for the quality of the resulting hash.
It is highly recommended for the secret to use the best possible entropy.


### MySQLi [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.mysqli)

#### New INI directive `mysqli.local_infile_directory` [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.mysqli.local_infile_directory)

The [mysqli.local\_infile\_directory](https://www.php.net/manual/en/mysqli.configuration.php#ini.mysqli.local-infile-directory)
INI directive has been added, which can be used to specify a directory from
which files are allowed to be loaded. It is only meaningful if
[mysqli.allow\_local\_infile](https://www.php.net/manual/en/mysqli.configuration.php#ini.mysqli.allow-local-infile)
is not enabled, as all directories are allowed in that case.


#### Binding parameters in execute [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.mysqli.bind-in-execute)

It is now possible to bind parameters by passing them as an array to
[mysqli\_stmt::execute()](https://www.php.net/manual/en/mysqli-stmt.execute.php). All values will be bound as
strings. Only list arrays are allowed. This new feature is not available
when MySQLi is compiled with libmysqlclient.



`<?php
$stmt = $mysqli->prepare('INSERT INTO users(id, name) VALUES(?,?)');
$stmt->execute([1, $username]);
?>`

#### New method [mysqli\_result::fetch\_column()](https://www.php.net/manual/en/mysqli-result.fetch-column.php) [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.mysqli.mysqli_fetch_column)

[mysqli\_result::fetch\_column()](https://www.php.net/manual/en/mysqli-result.fetch-column.php)
has been added to allow fetching a single scalar value from the result set.
The new method accepts an optional 0-based `column`
parameter of type [int](https://www.php.net/manual/en/language.types.integer.php) specifying which column to fetch from.



`<?php
$result = $mysqli->query('SELECT username FROM users WHERE id = 123');
echo $result->fetch_column();
?>`

### PDO [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.pdo_mysql)

The **`[PDO::MYSQL\_ATTR\_LOCAL\_INFILE\_DIRECTORY](https://www.php.net/manual/en/ref.pdo-mysql.php#pdo.constants.mysql-attr-local-infile-directory)`** attribute
has been added, which can be used to specify a directory from which files
are allowed to be loaded.
It is only meaningful if **`[PDO::MYSQL\_ATTR\_LOCAL\_INFILE](https://www.php.net/manual/en/ref.pdo-mysql.php#pdo.constants.mysql-attr-local-infile)`**
is not enabled, as all directories are allowed in that case.


### PDO\_SQLite [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.pdo_sqlite)

SQLite's `"file:"` DSN syntax is now supported,
which allows specifying additional flags.
This feature is not available if open\_basedir is set.


`<?php
new PDO('sqlite:file:path/to/sqlite.db?mode=ro')
?>`

### POSIX [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.posix)

Added **`[POSIX\_RLIMIT\_KQUEUES](https://www.php.net/manual/en/posix.constants.setrlimit.php#constant.posix-rlimit-kqueues)`** and **`[POSIX\_RLIMIT\_NPTS](https://www.php.net/manual/en/posix.constants.setrlimit.php#constant.posix-rlimit-npts)`**.
These rlimits are only available on FreeBSD.


### Standard [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.standard)

[fputcsv()](https://www.php.net/manual/en/function.fputcsv.php) now accepts a new
`eol` argument which allows to define a custom
End of Line sequence, the default remains the same and is `"\n"`.


### SPL [¶](https://www.php.net/manual/en/migration81.new-features.php\#migration81.new-features.spl)

[SplFileObject::fputcsv()](https://www.php.net/manual/en/splfileobject.fputcsv.php) now accepts a new
`eol` argument which allows to define a custom
End of Line sequence, the default remains the same and is `"\n"`.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/appendices/migration81/new-features.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmigration81.new-features%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=migration81.new-features&repo=en&redirect=https://www.php.net/manual/en/migration81.new-features.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google