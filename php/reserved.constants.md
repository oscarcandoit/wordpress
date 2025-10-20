---
url: https://www.php.net/manual/en/reserved.constants.php
scraped_at: 2025-10-20T02:33:27.255Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Predefined Constants [¶](https://www.php.net/manual/en/reserved.constants.php\#reserved.constants)

### Core Predefined Constants [¶](https://www.php.net/manual/en/reserved.constants.php\#reserved.constants.core)

These constants are defined by the PHP core. This includes PHP,
the Zend engine, and SAPI modules.


**`[PHP\_VERSION](https://www.php.net/manual/en/reserved.constants.php#constant.php-version)`**
([string](https://www.php.net/manual/en/language.types.string.php))

The current PHP version as a string in
"major.minor.release\[extra\]" notation.
**`[PHP\_MAJOR\_VERSION](https://www.php.net/manual/en/reserved.constants.php#constant.php-major-version)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The current PHP "major" version as an integer (e.g., int(5)
from version "5.2.7-extra").
**`[PHP\_MINOR\_VERSION](https://www.php.net/manual/en/reserved.constants.php#constant.php-minor-version)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The current PHP "minor" version as an integer (e.g., int(2)
from version "5.2.7-extra").
**`[PHP\_RELEASE\_VERSION](https://www.php.net/manual/en/reserved.constants.php#constant.php-release-version)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The current PHP "release" version as an integer (e.g., int(7)
from version "5.2.7-extra").
**`[PHP\_VERSION\_ID](https://www.php.net/manual/en/reserved.constants.php#constant.php-version-id)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The current PHP version as an integer, useful for
version comparisons (e.g., int(50207) from version "5.2.7-extra").
**`[PHP\_EXTRA\_VERSION](https://www.php.net/manual/en/reserved.constants.php#constant.php-extra-version)`**
([string](https://www.php.net/manual/en/language.types.string.php))

The current PHP "extra" version as a string (e.g., '-extra'
from version "5.2.7-extra"). Often used by distribution
vendors to indicate a package version.
**`[ZEND\_THREAD\_SAFE](https://www.php.net/manual/en/reserved.constants.php#constant.zend-thread-safe)`**
([bool](https://www.php.net/manual/en/language.types.boolean.php))

Indicates whether the current build of PHP is thread safe.
**`[ZEND\_DEBUG\_BUILD](https://www.php.net/manual/en/reserved.constants.php#constant.zend-debug-build)`**
([bool](https://www.php.net/manual/en/language.types.boolean.php))

Indicates whether the current build of PHP is a debug build.
**`[PHP\_ZTS](https://www.php.net/manual/en/reserved.constants.php#constant.php-zts)`**
([bool](https://www.php.net/manual/en/language.types.boolean.php))
Alias of **`[ZEND\_THREAD\_SAFE](https://www.php.net/manual/en/reserved.constants.php#constant.zend-thread-safe)`**
Indicates whether the current build of PHP is thread safe.
**`[PHP\_DEBUG](https://www.php.net/manual/en/reserved.constants.php#constant.php-debug)`**
([bool](https://www.php.net/manual/en/language.types.boolean.php))
Alias of **`[ZEND\_DEBUG\_BUILD](https://www.php.net/manual/en/reserved.constants.php#constant.zend-debug-build)`**
Indicates whether the current build of PHP is a debug build.
**`[DEBUG\_BACKTRACE\_PROVIDE\_OBJECT](https://www.php.net/manual/en/reserved.constants.php#constant.debug-backtrace-provide-object)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Populate the "object" index.
**`[DEBUG\_BACKTRACE\_IGNORE\_ARGS](https://www.php.net/manual/en/reserved.constants.php#constant.debug-backtrace-ignore-args)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Don't include the argument information for functions in the stack trace.
**`[PHP\_MAXPATHLEN](https://www.php.net/manual/en/reserved.constants.php#constant.php-maxpathlen)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The maximum length of filenames (including path) supported
by this build of PHP.
**`[PHP\_OS](https://www.php.net/manual/en/reserved.constants.php#constant.php-os)`**
([string](https://www.php.net/manual/en/language.types.string.php))

The operating system PHP was built for.
**`[PHP\_OS\_FAMILY](https://www.php.net/manual/en/reserved.constants.php#constant.php-os-family)`**
([string](https://www.php.net/manual/en/language.types.string.php))

The operating system family PHP was built for. One of
`'Windows'`, `'BSD'`,
`'Darwin'`, `'Solaris'`,
`'Linux'` or `'Unknown'`.
Available as of PHP 7.2.0.
**`[PHP\_SAPI](https://www.php.net/manual/en/reserved.constants.php#constant.php-sapi)`**
([string](https://www.php.net/manual/en/language.types.string.php))

The Server API for this build of PHP.
See also [php\_sapi\_name()](https://www.php.net/manual/en/function.php-sapi-name.php).
**`[PHP\_EOL](https://www.php.net/manual/en/reserved.constants.php#constant.php-eol)`**
([string](https://www.php.net/manual/en/language.types.string.php))

The correct 'End Of Line' symbol for this platform.
**`[PHP\_INT\_MAX](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-max)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The largest integer supported in this build of PHP. Usually int(2147483647)
in 32 bit systems and int(9223372036854775807) in 64 bit systems.
**`[PHP\_INT\_MIN](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-min)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The smallest integer supported in this build of PHP. Usually int(-2147483648) in 32 bit systems and
int(-9223372036854775808) in 64 bit systems.
Usually, PHP\_INT\_MIN === ~PHP\_INT\_MAX.
**`[PHP\_INT\_SIZE](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-size)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The size of an integer in bytes in this build of PHP.
**`[PHP\_FLOAT\_DIG](https://www.php.net/manual/en/reserved.constants.php#constant.php-float-dig)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Number of decimal digits that can be rounded into a float and back
without precision loss.
Available as of PHP 7.2.0.
**`[PHP\_FLOAT\_EPSILON](https://www.php.net/manual/en/reserved.constants.php#constant.php-float-epsilon)`**
([float](https://www.php.net/manual/en/language.types.float.php))

Smallest representable positive number x, so that `x + 1.0 !=
     1.0`.
Available as of PHP 7.2.0.
**`[PHP\_FLOAT\_MIN](https://www.php.net/manual/en/reserved.constants.php#constant.php-float-min)`**
([float](https://www.php.net/manual/en/language.types.float.php))

Smallest representable _positive_ floating point number.
If you need the smallest representable _negative_ floating point number, use `- PHP_FLOAT_MAX`.
Available as of PHP 7.2.0.
**`[PHP\_FLOAT\_MAX](https://www.php.net/manual/en/reserved.constants.php#constant.php-float-max)`**
([float](https://www.php.net/manual/en/language.types.float.php))

Largest representable floating point number.
Available as of PHP 7.2.0.
**`[DEFAULT\_INCLUDE\_PATH](https://www.php.net/manual/en/reserved.constants.php#constant.default-include-path)`**
([string](https://www.php.net/manual/en/language.types.string.php))
**`[PEAR\_INSTALL\_DIR](https://www.php.net/manual/en/reserved.constants.php#constant.pear-install-dir)`**
([string](https://www.php.net/manual/en/language.types.string.php))
**`[PEAR\_EXTENSION\_DIR](https://www.php.net/manual/en/reserved.constants.php#constant.pear-extension-dir)`**
([string](https://www.php.net/manual/en/language.types.string.php))
**`[PHP\_EXTENSION\_DIR](https://www.php.net/manual/en/reserved.constants.php#constant.php-extension-dir)`**
([string](https://www.php.net/manual/en/language.types.string.php))

The default directory where to look for dynamically loadable extensions
(unless overridden by [extension\_dir](https://www.php.net/manual/en/ini.core.php#ini.extension-dir)).
Defaults to **`[PHP\_PREFIX](https://www.php.net/manual/en/reserved.constants.php#constant.php-prefix)`** (or `PHP_PREFIX . "\\ext"` on Windows).
**`[PHP\_PREFIX](https://www.php.net/manual/en/reserved.constants.php#constant.php-prefix)`**
([string](https://www.php.net/manual/en/language.types.string.php))

The value **--prefix** was set to at configure.
On Windows, it is the value **--with-prefix**
was set to at configure.
**`[PHP\_BINDIR](https://www.php.net/manual/en/reserved.constants.php#constant.php-bindir)`**
([string](https://www.php.net/manual/en/language.types.string.php))

The value **--bindir** was set to at configure.
On Windows, it is the value **--with-prefix**
was set to at configure.
**`[PHP\_SBINDIR](https://www.php.net/manual/en/reserved.constants.php#constant.php-sbindir)`**
([string](https://www.php.net/manual/en/language.types.string.php))

The value **--sbindir** was set to at configure.
On Windows, it is the value **--with-prefix**
was set to at configure. Available as of PHP 8.4.0.
**`[PHP\_BINARY](https://www.php.net/manual/en/reserved.constants.php#constant.php-binary)`**
([string](https://www.php.net/manual/en/language.types.string.php))

Specifies the PHP binary path during script execution.
**`[PHP\_MANDIR](https://www.php.net/manual/en/reserved.constants.php#constant.php-mandir)`**
([string](https://www.php.net/manual/en/language.types.string.php))

Specifies where the manpages were installed into.
**`[PHP\_LIBDIR](https://www.php.net/manual/en/reserved.constants.php#constant.php-libdir)`**
([string](https://www.php.net/manual/en/language.types.string.php))
**`[PHP\_DATADIR](https://www.php.net/manual/en/reserved.constants.php#constant.php-datadir)`**
([string](https://www.php.net/manual/en/language.types.string.php))
**`[PHP\_SYSCONFDIR](https://www.php.net/manual/en/reserved.constants.php#constant.php-sysconfdir)`**
([string](https://www.php.net/manual/en/language.types.string.php))
**`[PHP\_LOCALSTATEDIR](https://www.php.net/manual/en/reserved.constants.php#constant.php-localstatedir)`**
([string](https://www.php.net/manual/en/language.types.string.php))
**`[PHP\_CONFIG\_FILE\_PATH](https://www.php.net/manual/en/reserved.constants.php#constant.php-config-file-path)`**
([string](https://www.php.net/manual/en/language.types.string.php))
**`[PHP\_CONFIG\_FILE\_SCAN\_DIR](https://www.php.net/manual/en/reserved.constants.php#constant.php-config-file-scan-dir)`**
([string](https://www.php.net/manual/en/language.types.string.php))
**`[PHP\_SHLIB\_SUFFIX](https://www.php.net/manual/en/reserved.constants.php#constant.php-shlib-suffix)`**
([string](https://www.php.net/manual/en/language.types.string.php))

The build-platform's shared library suffix, such as "so" (most Unixes)
or "dll" (Windows).
**`[PHP\_FD\_SETSIZE](https://www.php.net/manual/en/reserved.constants.php#constant.php-fd-setsize)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

The maximum number of file descriptors for select system calls. Available
as of PHP 7.1.0.
**`[E\_ERROR](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_PARSE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-parse)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_NOTICE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-notice)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_CORE\_ERROR](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-core-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_CORE\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-core-warning)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_COMPILE\_ERROR](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-compile-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_COMPILE\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-compile-warning)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_USER\_ERROR](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-user-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_USER\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-user-warning)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_USER\_NOTICE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-user-notice)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_RECOVERABLE\_ERROR](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-recoverable-error)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_DEPRECATED](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-deprecated)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_USER\_DEPRECATED](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-user-deprecated)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_ALL](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-all)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[E\_STRICT](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-strict)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
[Error reporting constants](https://www.php.net/manual/en/errorfunc.constants.php)**`[\_\_COMPILER\_HALT\_OFFSET\_\_](https://www.php.net/manual/en/misc.constants.php#constant.compiler-halt-offset)`**
([int](https://www.php.net/manual/en/language.types.integer.php))
**`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**
([bool](https://www.php.net/manual/en/language.types.boolean.php))

See [Booleans](https://www.php.net/manual/en/language.types.boolean.php).
**`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**
([bool](https://www.php.net/manual/en/language.types.boolean.php))

See [Booleans](https://www.php.net/manual/en/language.types.boolean.php).
**`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**
([null](https://www.php.net/manual/en/language.types.null.php))

See [Null](https://www.php.net/manual/en/language.types.null.php).
**`[PHP\_WINDOWS\_EVENT\_CTRL\_C](https://www.php.net/manual/en/reserved.constants.php#constant.php-windows-event-ctrl-c)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

A Windows
`
      CTRL
      +C
     `
event.
Available as of PHP 7.4.0 (Windows only).
**`[PHP\_WINDOWS\_EVENT\_CTRL\_BREAK](https://www.php.net/manual/en/reserved.constants.php#constant.php-windows-event-ctrl-break)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

A Windows
`
      CTRL
      +BREAK
     `
event.
Available as of PHP 7.4.0 (Windows only).
**`[PHP\_CLI\_PROCESS\_TITLE](https://www.php.net/manual/en/reserved.constants.php#constant.php-cli-process-title)`**
([bool](https://www.php.net/manual/en/language.types.boolean.php))

Indicates whether the setting and getting of the process title is available.
Available only under the CLI SAPI.
**`[STDERR](https://www.php.net/manual/en/reserved.constants.php#constant.stderr)`**
([resource](https://www.php.net/manual/en/language.types.resource.php))

An already opened stream to `stderr`.
Available only under the CLI SAPI.
**`[STDIN](https://www.php.net/manual/en/reserved.constants.php#constant.stdin)`**
([resource](https://www.php.net/manual/en/language.types.resource.php))

An already opened stream to `stdin`.
Available only under the CLI SAPI.
**`[STDOUT](https://www.php.net/manual/en/reserved.constants.php#constant.stdout)`**
([resource](https://www.php.net/manual/en/language.types.resource.php))

An already opened stream to `stdout`.
Available only under the CLI SAPI.


See also: [Magic\\
constants](https://www.php.net/manual/en/language.constants.magic.php).


### Standard Predefined Constants [¶](https://www.php.net/manual/en/reserved.constants.php\#reserved.constants.standard)

All constants from [core\\
extensions](https://www.php.net/manual/en/extensions.membership.php#extensions.membership.core) are defined in PHP by default.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/appendices/reserved.constants.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Freserved.constants%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=reserved.constants&repo=en&redirect=https://www.php.net/manual/en/reserved.constants.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google