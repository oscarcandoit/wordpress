---
url: https://www.php.net/manual/en/migration83.other-changes.php
scraped_at: 2025-10-20T02:30:44.793Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Other Changes [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes)

### Core changes [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.core)

#### FFI [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.core.ffi)

[FFI::load()](https://www.php.net/manual/en/ffi.load.php) is now allowed during preloading
when [opcache.preload\_user](https://www.php.net/manual/en/opcache.configuration.php#ini.opcache.preload-user)
is the current system user. Previously,
calling [FFI::load()](https://www.php.net/manual/en/ffi.load.php) was not possible
during preloading if the
[opcache.preload\_user](https://www.php.net/manual/en/opcache.configuration.php#ini.opcache.preload-user)
directive was set.


#### FPM [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.core.fpm)

FPM CLI test now fails if the socket path is longer than supported by the OS.


#### Opcache [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.core.opcache)

In the CLI and phpdbg SAPIs, preloading does not require the
[opcache.preload\_user](https://www.php.net/manual/en/opcache.configuration.php#ini.opcache.preload-user)
directive to be set anymore when running as root.
In other SAPIs, this directive is required when running as root because
preloading is done before the SAPI switches to an unprivileged user.


#### Streams [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.core.streams)

Blocking [fread()](https://www.php.net/manual/en/function.fread.php) on a socket connection returns
immediately if there are any buffered data instead of waiting for more data.


A memory stream no longer fails if the seek offset is past the end.
Instead, the memory will be increased on the next write and the data between
the old end and the offset is filled with zero bytes, similar to how files work.


[stat()](https://www.php.net/manual/en/function.stat.php) access operations like
[file\_exists()](https://www.php.net/manual/en/function.file-exists.php) and similar will now use real
path instead of the actual stream path. This is consistent with stream
opening.


### Changes in SAPI Modules [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.sapi)

#### CLI [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.sapi.cli)

The **`[STDOUT](https://www.php.net/manual/en/reserved.constants.php#constant.stdout)`**, **`[STDERR](https://www.php.net/manual/en/reserved.constants.php#constant.stderr)`** and
**`[STDIN](https://www.php.net/manual/en/reserved.constants.php#constant.stdin)`** streams are no longer closed on resource
destruction which is mostly when the CLI finishes.
It is however still possible to explicitly close those streams using
[fclose()](https://www.php.net/manual/en/function.fclose.php) and similar.


### Changed Functions [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions)

#### Core [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.core)

[gc\_status()](https://www.php.net/manual/en/function.gc-status.php) has added the following 8 fields:



- `"running"` =\> bool
- `"protected"` =\> bool
- `"full"` =\> bool
- `"buffer_size"` =\> int
- `"application_time"` =\> float: Total application
time, in seconds (including collector\_time)
- `"collector_time"` =\> float: Time spent collecting
cycles, in seconds (including destructor\_time and free\_time)
- `"destructor_time"` =\> float: Time spent executing
destructors during cycle collection, in seconds
- `"free_time"` =\> float: Time spent freeing values
during cycle collection, in seconds

[class\_alias()](https://www.php.net/manual/en/function.class-alias.php) now supports creating an alias of an
internal class.


Setting [open\_basedir](https://www.php.net/manual/en/ini.core.php#ini.open-basedir) at runtime
using `ini_set('open_basedir', ...);` no longer accepts paths
containing the parent directory ( `..`). Previously,
only paths starting with `..` were disallowed. This could
easily be circumvented by prepending `./` to the path.


User exception handlers now catch exceptions during shutdown.


The resultant HTML of [highlight\_string()](https://www.php.net/manual/en/function.highlight-string.php) and
[highlight\_file()](https://www.php.net/manual/en/function.highlight-file.php) has changed.
Whitespace between outer HTML tags is removed. Newlines and spaces
are no longer converted to HTML entities. The whole HTML is now wrapped in a
`<pre>` tag. The outer `<span>`
tag has been merged with the `<code>` tag.


#### Calendar [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.calendar)

[easter\_date()](https://www.php.net/manual/en/function.easter-date.php) now supports years from 1970 to
2,000,000,000 on 64-bit systems, previously it only supported years in the
range from 1970 to 2037.


#### Curl [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.curl)

[curl\_getinfo()](https://www.php.net/manual/en/function.curl-getinfo.php) now supports two new constants:
**`[CURLINFO\_CAPATH](https://www.php.net/manual/en/curl.constants.php#constant.curlinfo-capath)`** and
**`[CURLINFO\_CAINFO](https://www.php.net/manual/en/curl.constants.php#constant.curlinfo-cainfo)`**. If option is **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, the following
two additional keys are present:
`"capath"` and `"cainfo"`.


#### DOM [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.dom)

Changed [DOMCharacterData::appendData()](https://www.php.net/manual/en/domcharacterdata.appenddata.php) tentative
return type to [true](https://www.php.net/manual/en/language.types.singleton.php).


[DOMDocument::loadHTML()](https://www.php.net/manual/en/domdocument.loadhtml.php),
[DOMDocument::loadHTMLFile()](https://www.php.net/manual/en/domdocument.loadhtmlfile.php), and
[DOMDocument::loadXML()](https://www.php.net/manual/en/domdocument.loadxml.php) now have a tentative
return type of [bool](https://www.php.net/manual/en/language.types.boolean.php). Previously, this was documented as having a return
type of `DOMDocument|bool`, but, as of PHP 8.0.0,
[DOMDocument](https://www.php.net/manual/en/class.domdocument.php)
cannot be returned as it is no longer statically callable.


#### Gd [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.gd)

The signature of [imagerotate()](https://www.php.net/manual/en/function.imagerotate.php) has changed.
The `$ignore_transparent` parameter has been removed,
as it was ignored since PHP 5.5.0.


#### Intl [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.intl)

[datefmt\_set\_timezone()](https://www.php.net/manual/en/intldateformatter.settimezone.php) (and its alias
[IntlDateformatter::setTimeZone()](https://www.php.net/manual/en/intldateformatter.settimezone.php))
now returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success, previously **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** was returned.


[IntlBreakiterator::setText()](https://www.php.net/manual/en/intlbreakiterator.settext.php) now returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**
on failure, previously **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** was returned.
It now returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success, previously **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** was returned.


[IntlChar::enumCharNames()](https://www.php.net/manual/en/intlchar.enumcharnames.php) is now returning a boolean.
Previously it returned **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** on success and **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


[IntlDateFormatter::\_\_construct()](https://www.php.net/manual/en/intldateformatter.create.php) throws an **`[U\_ILLEGAL\_ARGUMENT\_ERROR](https://www.php.net/manual/en/intl.constants.php#constant.u-illegal-argument-error)`**
exception when an invalid locale had been set.


#### MBString [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.mbstring)

[mb\_strtolower()](https://www.php.net/manual/en/function.mb-strtolower.php) and [mb\_convert\_case()](https://www.php.net/manual/en/function.mb-convert-case.php)
implement conditional casing rules for the Greek letter sigma.
For [mb\_convert\_case()](https://www.php.net/manual/en/function.mb-convert-case.php),
conditional casing only applies to **`[MB\_CASE\_LOWER](https://www.php.net/manual/en/mbstring.constants.php#constant.mb-case-lower)`**
and **`[MB\_CASE\_TITLE](https://www.php.net/manual/en/mbstring.constants.php#constant.mb-case-title)`** modes, not to
**`[MB\_CASE\_LOWER\_SIMPLE](https://www.php.net/manual/en/mbstring.constants.php#constant.mb-case-lower-simple)`** and
**`[MB\_CASE\_TITLE\_SIMPLE](https://www.php.net/manual/en/mbstring.constants.php#constant.mb-case-title-simple)`**.


[mb\_decode\_mimeheader()](https://www.php.net/manual/en/function.mb-decode-mimeheader.php) interprets underscores in
QPrint-encoded MIME encoded words as required by RFC 2047; they are
converted to spaces.
Underscores must be encoded as `"=5F"` in such MIME
encoded words.


In rare cases, [mb\_encode\_mimeheader()](https://www.php.net/manual/en/function.mb-encode-mimeheader.php) will transfer-encode
its input string where it would pass it through as raw ASCII in PHP 8.2.


[mb\_encode\_mimeheader()](https://www.php.net/manual/en/function.mb-encode-mimeheader.php) no longer drops NUL (zero)
bytes when QPrint-encoding the input string.
This previously caused strings in certain text encodings, especially
UTF-16 and UTF-32, to be corrupted by mb\_encode\_mimeheader.


[mb\_detect\_encoding()](https://www.php.net/manual/en/function.mb-detect-encoding.php)'s "non-strict" mode now behaves
as described in the documentation.
Previously, it would return **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if the same byte (for example, the first
byte) of the input string was invalid in all candidate encodings.
More generally, it would eliminate candidate encodings from consideration
when an invalid byte was seen, and if the same input byte eliminated all
remaining encodings still under consideration, it would return **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**.
On the other hand, if all candidate encodings but one were eliminated
from consideration, it would return the last remaining one without regard
for how many encoding errors might be encountered later in the string.
This is different from the behavior described in the documentation, which
says: "If strict is set to false, the closest matching encoding will be
returned."


#### mysqli [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.mysqli)

[mysqli\_fetch\_object()](https://www.php.net/manual/en/mysqli-result.fetch-object.php) now raises a
[ValueError](https://www.php.net/manual/en/class.valueerror.php) instead of an [Exception](https://www.php.net/manual/en/class.exception.php)
when the `$constructor_args` argument is non empty with
the class not having constructor.


[mysqli\_poll()](https://www.php.net/manual/en/mysqli.poll.php) now raises a [ValueError](https://www.php.net/manual/en/class.valueerror.php)
when neither the `$read`
nor the `$error` arguments are passed.


[mysqli\_field\_seek()](https://www.php.net/manual/en/mysqli-result.field-seek.php) and
[mysqli\_result::field\_seek()](https://www.php.net/manual/en/mysqli-result.field-seek.php) now specify the return
type as [true](https://www.php.net/manual/en/language.types.singleton.php) instead of [bool](https://www.php.net/manual/en/language.types.boolean.php).


#### ODBC [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.odbc)

[odbc\_autocommit()](https://www.php.net/manual/en/function.odbc-autocommit.php) now accepts **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** for the
`$enable` parameter.
Passing **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** has the same behaviour as passing only 1 parameter,
namely indicating if the autocommit feature is enabled or not.


#### PGSQL [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.pgsql)

[pg\_fetch\_object()](https://www.php.net/manual/en/function.pg-fetch-object.php) now raises a
[ValueError](https://www.php.net/manual/en/class.valueerror.php) instead of an [Exception](https://www.php.net/manual/en/class.exception.php)
when the `$constructor_args` argument is non empty with
the class not having constructor.


[pg\_insert()](https://www.php.net/manual/en/function.pg-insert.php) now raises a [ValueError](https://www.php.net/manual/en/class.valueerror.php)
instead of a **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** when the table specified is invalid.


[pg\_insert()](https://www.php.net/manual/en/function.pg-insert.php) and [pg\_convert()](https://www.php.net/manual/en/function.pg-convert.php) raises
a [ValueError](https://www.php.net/manual/en/class.valueerror.php) or a [TypeError](https://www.php.net/manual/en/class.typeerror.php)
instead of a **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** when the value/type of a field
does not match properly with a PostgreSQL's type.


The `$row` parameter of
[pg\_fetch\_result()](https://www.php.net/manual/en/function.pg-fetch-result.php),
[pg\_field\_prtlen()](https://www.php.net/manual/en/function.pg-field-prtlen.php), and
[pg\_field\_is\_null()](https://www.php.net/manual/en/function.pg-field-is-null.php) is now nullable.


#### Random [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.random)

Changed [mt\_srand()](https://www.php.net/manual/en/function.mt-srand.php) and [srand()](https://www.php.net/manual/en/function.srand.php) to
not check the number of arguments to determine whether a random seed should
be used. Passing **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** will generate a random seed, `0`
will use zero as the seed. The functions are now consistent with
[Random\\Engine\\Mt19937::\_\_construct()](https://www.php.net/manual/en/random-engine-mt19937.construct.php).


#### Reflection [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.reflection)

Return type of [ReflectionClass::getStaticProperties()](https://www.php.net/manual/en/reflectionclass.getstaticproperties.php)
is no longer nullable.


#### Standard [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.functions.standard)

**`[E\_NOTICE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-notice)`** s emitted by [unserialize()](https://www.php.net/manual/en/function.unserialize.php)
have been promoted to **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**.



[unserialize()](https://www.php.net/manual/en/function.unserialize.php) now emits a new **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**
if the input contains unconsumed bytes.



[array\_pad()](https://www.php.net/manual/en/function.array-pad.php) is now only limited by the maximum number of
elements an array can have. Before, it was only possible to add at most 1048576
elements at a time.


[strtok()](https://www.php.net/manual/en/function.strtok.php) raises an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** in the
case token is not provided when starting tokenization.


[password\_hash()](https://www.php.net/manual/en/function.password-hash.php) will now chain the underlying
[Random\\RandomException](https://www.php.net/manual/en/class.random-randomexception.php)
as the [ValueError](https://www.php.net/manual/en/class.valueerror.php)'s `$previous` [Exception](https://www.php.net/manual/en/class.exception.php) when salt generation fails.


If using an array as the `$command`
for [proc\_open()](https://www.php.net/manual/en/function.proc-open.php), it must now have at least one
non empty element. Otherwise a [ValueError](https://www.php.net/manual/en/class.valueerror.php)
is thrown.


[proc\_open()](https://www.php.net/manual/en/function.proc-open.php) returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if `$command`
array is invalid command instead of resource object that produces warning later.
This was already the case for Windows but it is now also the case if a posix\_spawn
implementation is in use (most Linux, BSD and MacOS platforms). There are still
some old platforms where this behavior is not changed as posix\_spawn is not
supported there.


[array\_sum()](https://www.php.net/manual/en/function.array-sum.php) and [array\_product()](https://www.php.net/manual/en/function.array-product.php) now
warn when values in the array cannot be converted to int/float.
Previously arrays and objects where ignored whilst every other value was
cast to int. Moreover, objects that define a numeric cast (e.g.
[GMP](https://www.php.net/manual/en/book.gmp.php)) are now casted instead of ignored.



The `$decimals` of [number\_format()](https://www.php.net/manual/en/function.number-format.php)
now properly handles negative integers.
Rounding with a negative value for `$decimals` means
that `$num` is rounded to `$decimals`
significant digits before the decimal point.
Previously negative `$decimals` were silently
ignored and the number got rounded to zero decimal places.


A new `$before_needle` argument has been added to
[strrchr()](https://www.php.net/manual/en/function.strrchr.php). It behaves like its counterpart in the
[strstr()](https://www.php.net/manual/en/function.strstr.php) or [stristr()](https://www.php.net/manual/en/function.stristr.php) functions.


[str\_getcsv()](https://www.php.net/manual/en/function.str-getcsv.php) and [fgetcsv()](https://www.php.net/manual/en/function.fgetcsv.php) now return
an empty string instead of a string with a single null byte for the last field
which only contains an unterminated enclosure.


### Other Changes to Extensions [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.extensions)

#### Core [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.extensions.core)

Using the [increment/decrement](https://www.php.net/manual/en/language.operators.increment.php)
operators ( `++`/ `--`) on values of type
[bool](https://www.php.net/manual/en/language.types.boolean.php) now emit warnings.
This is because it currently has no effect, but will behave like
`$bool += 1` in the future.


Using the [decrement](https://www.php.net/manual/en/language.operators.increment.php)
operator ( `--`) on values of type [null](https://www.php.net/manual/en/language.types.null.php) now emit warnings.
This is because it currently has no effect, but will behave like
`$null -= 1` in the future.


Internal objects that implement an \_IS\_NUMBER cast but not a do\_operator
handler that overrides addition and subtraction now can be incremented
and decrement as if one would do `$o += 1` or `$o -= 1`

#### DOM [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.extensions.dom)

The DOM lifetime mechanism has been reworked such that implicitly removed
nodes can still be fetched. Previously this resulted in an exception.


#### SQLite3 [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.extensions.sqlite3)

The [SQLite3](https://www.php.net/manual/en/class.sqlite3.php) class now throws
[SQLite3Exception](https://www.php.net/manual/en/class.sqlite3exception.php) (extends
[Exception](https://www.php.net/manual/en/class.exception.php)) instead of [Exception](https://www.php.net/manual/en/class.exception.php).


The SQLite error code is now passed in the exception error code instead of
being included in the error message.


### Changes to INI File Handling [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.ini)

- The `assert.*` INI settings have been deprecated.
This comprises the following INI settings:



  - [assert.active](https://www.php.net/manual/en/info.configuration.php#ini.assert.active)
  - [assert.bail](https://www.php.net/manual/en/info.configuration.php#ini.assert.bail)
  - [assert.callback](https://www.php.net/manual/en/info.configuration.php#ini.assert.callback)
  - [assert.exception](https://www.php.net/manual/en/info.configuration.php#ini.assert.exception)
  - [assert.warning](https://www.php.net/manual/en/info.configuration.php#ini.assert.warning)

If the value of the setting is equal to the default value, no deprecation
notice is emitted.
The [zend.assertions](https://www.php.net/manual/en/ini.core.php#ini.zend.assertions) INI setting
should be used instead.


- [zend.max\_allowed\_stack\_size](https://www.php.net/manual/en/info.configuration.php#ini.zend.max-allowed-stack-size)
is a new INI directive to set the maximum allowed stack size.
Possible values are `0` (detect the process or thread maximum stack size),
`-1` (no limit), or a positive number of bytes.
The default is `0`.
When it is not possible to detect the process or thread maximum stack
size, a known system default is used.
Setting this value too high has the same effect as disabling the stack size limit.
Fibers use
[fiber.stack\_size](https://www.php.net/manual/en/info.configuration.php#ini.fiber.stack-size)
as maximum allowed stack size.
An [Error](https://www.php.net/manual/en/class.error.php) is thrown when the process call stack exceeds
[zend.max\_allowed\_stack\_size](https://www.php.net/manual/en/info.configuration.php#ini.zend.max-allowed-stack-size)- [zend.reserved\_stack\_size](https://www.php.net/manual/en/info.configuration.php#ini.zend.reserved-stack-size)
bytes, to prevent stack-overflow-induced segmentation faults, with
the goal of making debugging easier.
The stack size increases during uncontrolled recursions involving internal functions
or the magic methods
[\_\_toString()](https://www.php.net/manual/en/language.oop5.magic.php#object.tostring),
[\_\_clone()](https://www.php.net/manual/en/language.oop5.cloning.php#object.clone),
[\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep),
[\_\_destruct()](https://www.php.net/manual/en/language.oop5.decon.php#object.destruct).
This is not related to stack buffer overflows, and is not a security feature.


- [zend.reserved\_stack\_size](https://www.php.net/manual/en/info.configuration.php#ini.zend.reserved-stack-size)
is a new INI directive to set the reserved stack size, in bytes.
This is subtracted from the max allowed stack size,
as a buffer, when checking the stack size.



### Performance [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.performance)

#### DOM [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.performance.dom)

Looping over a [DOMNodeList](https://www.php.net/manual/en/class.domnodelist.php) now uses caching. Therefore
requesting items no longer takes quadratic time by default.


Getting text content from nodes now avoids an allocation, resulting in a
performance gain.


[DOMChildNode::remove()](https://www.php.net/manual/en/domchildnode.remove.php) now runs in O(1) performance.


#### Standard [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.performance.standard)

The [file()](https://www.php.net/manual/en/function.file.php) flags error check is now about 7% faster.


#### SPL [¶](https://www.php.net/manual/en/migration83.other-changes.php\#migration83.other-changes.performance.spl)

[RecursiveDirectoryIterator](https://www.php.net/manual/en/class.recursivedirectoryiterator.php) now performs less I/O
when looping over a directory.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/appendices/migration83/other-changes.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmigration83.other-changes%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=migration83.other-changes&repo=en&redirect=https://www.php.net/manual/en/migration83.other-changes.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google