---
url: https://www.php.net/manual/en/function.igbinary-serialize.php
scraped_at: 2025-10-20T02:54:11.308Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# igbinary\_serialize

(PECL igbinary >= 1.1.1)

igbinary\_serialize — Generates a compact, storable binary representation of a value

### Description [¶](https://www.php.net/manual/en/function.igbinary-serialize.php\#refsect1-function.igbinary-serialize-description)

**igbinary\_serialize**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$value`): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

Generates a storable representation of a value.


This is useful for storing or passing PHP values around without
losing their type and structure.


To make the serialized string into a PHP value again,
[igbinary\_unserialize()](https://www.php.net/manual/en/function.igbinary-unserialize.php) can be used.


### Parameters [¶](https://www.php.net/manual/en/function.igbinary-serialize.php\#refsect1-function.igbinary-serialize-parameters)

`value`

The value to be serialized. **igbinary\_serialize()**
handles all types, except the [resource](https://www.php.net/manual/en/language.types.resource.php)-type and some [object](https://www.php.net/manual/en/language.types.object.php)s (see note below).
Even [array](https://www.php.net/manual/en/language.types.array.php)s that contain references to itself can be processed by **igbinary\_serialize()**.
Circular references inside the [array](https://www.php.net/manual/en/language.types.array.php) or [object](https://www.php.net/manual/en/language.types.object.php) that is being serializend will also be stored.
Any other reference will be lost.


When serializing objects, igbinary will attempt to call the member functions
[\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize) or
[\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep) prior to serialization.
This is to allow the object to do any last minute clean-up, etc. prior
to being serialized. Likewise, when the object is restored using
[igbinary\_unserialize()](https://www.php.net/manual/en/function.igbinary-unserialize.php) the [\_\_unserialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.unserialize) or
[\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php#object.wakeup) member function is called.


> **Note**:
>
>
> Private members of [object](https://www.php.net/manual/en/language.types.object.php)s have the class name prepended to the member
> name; protected members have a `'*'` prepended to the member name.
> These prepended values have null bytes on either side.

### Return Values [¶](https://www.php.net/manual/en/function.igbinary-serialize.php\#refsect1-function.igbinary-serialize-returnvalues)

Returns a string containing a byte-stream representation of
`value` that can be stored anywhere.


Note that this is a binary string which can include any byte value, and needs
to be stored and handled as such. For example,
**igbinary\_serialize()** output should generally be stored in a `BLOB`
field in a database, rather than a `CHAR` or `TEXT` field.


### Examples [¶](https://www.php.net/manual/en/function.igbinary-serialize.php\#refsect1-function.igbinary-serialize-examples)

**Example #1 **igbinary\_serialize()** example**

`<?php
$ser = igbinary_serialize(['test', 'test']);
echo urlencode($ser), "\n";
var_export(igbinary_unserialize($ser));
?>`

The above example will output:

```
%00%00%00%02%14%02%06%00%11%04test%06%01%0E%00
array (
  0 => 'test',
  1 => 'test',
)
```

### Notes [¶](https://www.php.net/manual/en/function.igbinary-serialize.php\#refsect1-function.igbinary-serialize-notes)

> **Note**:
>
>
> Note that many built-in PHP objects cannot be serialized. However, those with
> this ability either implement the [Serializable](https://www.php.net/manual/en/class.serializable.php) interface or the
> magic [\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize)/ [\_\_unserialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.unserialize)
> or [\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep)/ [\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php#object.wakeup) methods. If an
> internal class does not fulfill any of those requirements, it cannot reliably be
> serialized with any serializer.
>
>
> There are some historical exceptions to the above rule, where some internal objects
> could be serialized without implementing the interface or exposing the methods.

### See Also [¶](https://www.php.net/manual/en/function.igbinary-serialize.php\#refsect1-function.igbinary-serialize-seealso)

- [serialize()](https://www.php.net/manual/en/function.serialize.php) \- Generates a storable representation of a value
- [igbinary\_unserialize()](https://www.php.net/manual/en/function.igbinary-unserialize.php) \- Creates a PHP value from a stored representation from igbinary\_serialize
- [var\_export()](https://www.php.net/manual/en/function.var-export.php) \- Outputs or returns a parsable string representation of a variable
- [json\_encode()](https://www.php.net/manual/en/function.json-encode.php) \- Returns the JSON representation of a value
- [Serializing Objects](https://www.php.net/manual/en/language.oop5.serialization.php)
- [\_\_sleep()](https://www.php.net/manual/en/language.oop5.magic.php#object.sleep)
- [\_\_wakeup()](https://www.php.net/manual/en/language.oop5.magic.php#object.wakeup)
- [\_\_serialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.serialize)
- [\_\_unserialize()](https://www.php.net/manual/en/language.oop5.magic.php#object.unserialize)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/igbinary/functions/igbinary-serialize.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.igbinary-serialize%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.igbinary-serialize&repo=en&redirect=https://www.php.net/manual/en/function.igbinary-serialize.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google