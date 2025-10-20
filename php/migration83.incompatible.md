---
url: https://www.php.net/manual/en/migration83.incompatible.php
scraped_at: 2025-10-20T02:41:54.704Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Backward Incompatible Changes [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible)

### PHP Core [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.core)

#### Programs that were very close to overflowing the call stack [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.core.overflowing-call-stack)

Programs that were very close to overflowing the call stack may now throw an
[Error](https://www.php.net/manual/en/class.error.php) when using more than
zend.max\_allowed\_stack\_size-zend.reserved\_stack\_size bytes of stack
(fiber.stack\_size-zend.reserved\_stack\_size for fibers).


#### Executing proc\_get\_status() multiple times [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.core.proc-get-status-multiple-times)

Executing [proc\_get\_status()](https://www.php.net/manual/en/function.proc-get-status.php) multiple times will now always
return the right value on POSIX systems. Previously, only the first call
of the function returned the right value. Executing
[proc\_close()](https://www.php.net/manual/en/function.proc-close.php) after [proc\_get\_status()](https://www.php.net/manual/en/function.proc-get-status.php)
will now also return the right exit code. Previously this would return
`-1`.
Internally, this works by caching the result on POSIX systems.
If the previous behaviour is required, it is possible to check the
`"cached"` key in the array returned by
[proc\_get\_status()](https://www.php.net/manual/en/function.proc-get-status.php) to check whether the result was cached.


#### Zend Max Execution Timers [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.core.zend-max-execution-timers)

Zend Max Execution Timers is now enabled by default for ZTS builds on
Linux.


#### Uses of traits with static properties [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.core.traits-with-static-properties)

Uses of traits with static properties will now redeclare static properties
inherited from the parent class. This will create a separate static
property storage for the current class. This is analogous to adding the
static property to the class directly without traits.


#### Assigning a negative index to an empty array [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.core.negative-index-to-empty-array)

Assigning a negative index $n to an empty array will now make sure that the
next index is `$n+1` instead of `0`.


#### Class constant visibility variance check [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.core.class-constant-visibility-check)

Class constant visibility variance is now correctly checked when inherited
from interfaces.


#### WeakMap entries whose key maps to itself [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.core.weakmap-entries-maps-to-itself)

[WeakMap](https://www.php.net/manual/en/class.weakmap.php) entries whose key maps to itself (possibly
transitively) may now be removed during cycle collection if the key is not
reachable except by iterating over the WeakMap (reachability via iteration is
considered weak).
Previously, such entries would never be automatically removed.


### Date [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.date)

The DateTime extension has introduced Date extension specific exceptions
and errors under the [DateError](https://www.php.net/manual/en/class.dateerror.php) and
[DateException](https://www.php.net/manual/en/class.dateexception.php) hierarchies, instead of warnings and
generic exceptions. This improves error handling, at the expense
of having to check for errors and exceptions.


### DOM [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.dom)

Calling [DOMChildNode::after()](https://www.php.net/manual/en/domchildnode.after.php),
[DOMChildNode::before()](https://www.php.net/manual/en/domchildnode.before.php),
[DOMChildNode::replaceWith()](https://www.php.net/manual/en/domchildnode.replacewith.php)
on a node that has no parent is now a no-op instead of a hierarchy
exception, which is the behaviour demanded by the DOM specification.


Using the [DOMParentNode](https://www.php.net/manual/en/class.domparentnode.php)
and [DOMChildNode](https://www.php.net/manual/en/class.domchildnode.php) methods without a document now
works instead of throwing a **`[DOM\_HIERARCHY\_REQUEST\_ERR](https://www.php.net/manual/en/dom.constants.php#constant.dom-hierarchy-request-err)`** [DOMException](https://www.php.net/manual/en/class.domexception.php).
This is in line with the behaviour demanded by the DOM specification.


Calling [DOMDocument::createAttributeNS()](https://www.php.net/manual/en/domdocument.createattributens.php) without specifying
a prefix would incorrectly create a default namespace, placing the element
inside the namespace instead of the attribute. This bug is now fixed.


[DOMDocument::createAttributeNS()](https://www.php.net/manual/en/domdocument.createattributens.php) would previously
incorrectly throw a **`DOM_NAMESPACE_ERRNAMESPACE_ERR`** [DOMException](https://www.php.net/manual/en/class.domexception.php) when the prefix was already used for a
different URI. It now correctly chooses a different prefix when there's a
prefix name conflict.


New methods and properties were added to some DOM classes.
If a userland class inherits from these classes and declare a method or property
with the same name, the declarations must be compatible. Otherwise, a typical
compile error about incompatible declarations will be thrown.
See the [list of new features](https://www.php.net/manual/en/migration83.new-features.php#migration83.new-features.dom)
and [new functions](https://www.php.net/manual/en/migration83.new-functions.php#migration83.new-functions.dom) for
a list of the newly implemented methods and properties.


### FFI [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.ffi)

C functions that have a return type of [void](https://www.php.net/manual/en/language.types.void.php) now return **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** instead of
returning the following object `object(FFI\CData:void) { }`

### Opcache [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.opcache)

The [opcache.consistency\_checks](https://www.php.net/manual/en/opcache.configuration.php#ini.opcache.consistency-checks)
INI directive was removed. This feature was broken with the tracing JIT,
as well as with inheritance cache, and has been disabled without a way to
enable it since PHP 8.1.18 and PHP 8.2.5.
Both the tracing JIT and inheritance cache may modify shm after the script
has been persisted by invalidating its checksum. The attempted fix skipped
over the modifiable pointers but was rejected due to complexity. For this
reason, it was decided to remove the feature instead.


### Phar [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.phar)

The type of [Phar](https://www.php.net/manual/en/class.phar.php) class constants are now declared.


### Standard [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.standard)

The [range()](https://www.php.net/manual/en/function.range.php) function has had various changes:


- A [TypeError](https://www.php.net/manual/en/class.typeerror.php) is now thrown when passing [object](https://www.php.net/manual/en/language.types.object.php)s,
[resource](https://www.php.net/manual/en/language.types.resource.php)s, or [array](https://www.php.net/manual/en/language.types.array.php)s as the boundary inputs.
- A more descriptive [ValueError](https://www.php.net/manual/en/class.valueerror.php) is thrown when
passing `0` for `$step`.
- A [ValueError](https://www.php.net/manual/en/class.valueerror.php) is now thrown when using a
negative `$step` for increasing ranges.
- If `$step` is a float that can be interpreted
as an int, it is now done so.
- A [ValueError](https://www.php.net/manual/en/class.valueerror.php) is now thrown if any argument
is infinity or NAN.
- An **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is now emitted if
`$start` or `$end` is the empty
string. The value continues to be cast to the value `0`.
- An **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is now emitted if
`$start` or `$end` has more than
one byte, only if it is a non-numeric string.
- An **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is now emitted if
`$start` or `$end` is cast to an
integer because the other boundary input is a number.
(e.g. `range(5, 'z');`).
- An **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** is now emitted if
`$step` is a float when trying to generate a range of
characters, except if both boundary inputs are numeric strings (e.g.
`range('5', '9', 0.5);` does not produce a warning).
- [range()](https://www.php.net/manual/en/function.range.php) now produce a list of characters if one
of the boundary inputs is a string digit instead of casting the other input
to int (e.g. `range('9', 'A');`).

`<?php
range('9', 'A');  // ["9", ":", ";", "<", "=", ">", "?", "@", "A"], as of PHP 8.3.0
range('9', 'A');  // [9, 8, 7, 6, 5, 4, 3, 2, 1, 0], prior to PHP 8.3.0
?>`

[number\_format()](https://www.php.net/manual/en/function.number-format.php) now handles negative
`$decimals` values by rounding
`$num` to `abs($decimals)` digits before the
decimal point. Previously, negative `$decimals` values
were ignored.


The [file()](https://www.php.net/manual/en/function.file.php) flags error check now catches all invalid flags.
Notably **`[FILE\_APPEND](https://www.php.net/manual/en/filesystem.constants.php#constant.file-append)`** was previously silently accepted.


### SNMP [¶](https://www.php.net/manual/en/migration83.incompatible.php\#migration83.incompatible.SNMP)

The type of [SNMP](https://www.php.net/manual/en/class.snmp.php) class constants are now declared.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/appendices/migration83/incompatible.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fmigration83.incompatible%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=migration83.incompatible&repo=en&redirect=https://www.php.net/manual/en/migration83.incompatible.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google