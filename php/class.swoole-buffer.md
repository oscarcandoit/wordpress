---
url: https://www.php.net/manual/en/class.swoole-buffer.php
scraped_at: 2025-10-20T02:32:30.657Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\Buffer class [¶](https://www.php.net/manual/en/class.swoole-buffer.php\#class.swoole-buffer)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-buffer.php\#swoole-buffer.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-buffer.php\#swoole-buffer.synopsis)

class **Swoole\\Buffer**
{

/\\* Methods \*/

public[append](https://www.php.net/manual/en/swoole-buffer.append.php)([string](https://www.php.net/manual/en/language.types.string.php) `$data`): [int](https://www.php.net/manual/en/language.types.integer.php)

public[clear](https://www.php.net/manual/en/swoole-buffer.clear.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[\_\_destruct](https://www.php.net/manual/en/swoole-buffer.destruct.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[expand](https://www.php.net/manual/en/swoole-buffer.expand.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$size`): [int](https://www.php.net/manual/en/language.types.integer.php)

public[read](https://www.php.net/manual/en/swoole-buffer.read.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$offset`, [int](https://www.php.net/manual/en/language.types.integer.php) `$length`): [string](https://www.php.net/manual/en/language.types.string.php)

public[recycle](https://www.php.net/manual/en/swoole-buffer.recycle.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[substr](https://www.php.net/manual/en/swoole-buffer.substr.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$offset`, [int](https://www.php.net/manual/en/language.types.integer.php) `$length` = ?, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$remove` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[\_\_toString](https://www.php.net/manual/en/swoole-buffer.tostring.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[write](https://www.php.net/manual/en/swoole-buffer.write.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$offset`, [string](https://www.php.net/manual/en/language.types.string.php) `$data`): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-buffer.php\#class.swoole-buffer)

- [Swoole\\Buffer::append](https://www.php.net/manual/en/swoole-buffer.append.php) — Append the string or binary data at the end of the memory buffer and return the new size of memory allocated.
- [Swoole\\Buffer::clear](https://www.php.net/manual/en/swoole-buffer.clear.php) — Reset the memory buffer.
- [Swoole\\Buffer::\_\_construct](https://www.php.net/manual/en/swoole-buffer.construct.php) — Fixed size memory blocks allocation.
- [Swoole\\Buffer::\_\_destruct](https://www.php.net/manual/en/swoole-buffer.destruct.php) — Destruct the Swoole memory buffer.
- [Swoole\\Buffer::expand](https://www.php.net/manual/en/swoole-buffer.expand.php) — Expand the size of memory buffer.
- [Swoole\\Buffer::read](https://www.php.net/manual/en/swoole-buffer.read.php) — Read data from the memory buffer based on offset and length.
- [Swoole\\Buffer::recycle](https://www.php.net/manual/en/swoole-buffer.recycle.php) — Release the memory to OS which is not used by the memory buffer.
- [Swoole\\Buffer::substr](https://www.php.net/manual/en/swoole-buffer.substr.php) — Read data from the memory buffer based on offset and length. Or remove data from the memory buffer.
- [Swoole\\Buffer::\_\_toString](https://www.php.net/manual/en/swoole-buffer.tostring.php) — Get the string value of the memory buffer.
- [Swoole\\Buffer::write](https://www.php.net/manual/en/swoole-buffer.write.php) — Write data to the memory buffer. The memory allocated for the buffer will not be changed.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.buffer.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-buffer%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-buffer&repo=en&redirect=https://www.php.net/manual/en/class.swoole-buffer.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google