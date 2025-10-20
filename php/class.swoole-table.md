---
url: https://www.php.net/manual/en/class.swoole-table.php
scraped_at: 2025-10-20T02:33:13.183Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\Table class [¶](https://www.php.net/manual/en/class.swoole-table.php\#class.swoole-table)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-table.php\#swoole-table.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-table.php\#swoole-table.synopsis)

class **Swoole\\Table**implements [Iterator](https://www.php.net/manual/en/class.iterator.php), [Countable](https://www.php.net/manual/en/class.countable.php) {

/\\* Constants \*/

const[int](https://www.php.net/manual/en/language.types.integer.php)[TYPE\_INT](https://www.php.net/manual/en/class.swoole-table.php#swoole-table.constants.type-int) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[TYPE\_STRING](https://www.php.net/manual/en/class.swoole-table.php#swoole-table.constants.type-string) = 7;

const[int](https://www.php.net/manual/en/language.types.integer.php)[TYPE\_FLOAT](https://www.php.net/manual/en/class.swoole-table.php#swoole-table.constants.type-float) = 6;

/\\* Methods \*/

public[column](https://www.php.net/manual/en/swoole-table.column.php)([string](https://www.php.net/manual/en/language.types.string.php) `$name`, [string](https://www.php.net/manual/en/language.types.string.php) `$type`, [int](https://www.php.net/manual/en/language.types.integer.php) `$size` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[count](https://www.php.net/manual/en/swoole-table.count.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[create](https://www.php.net/manual/en/swoole-table.create.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[current](https://www.php.net/manual/en/swoole-table.current.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[decr](https://www.php.net/manual/en/swoole-table.decr.php)([string](https://www.php.net/manual/en/language.types.string.php) `$key`, [string](https://www.php.net/manual/en/language.types.string.php) `$column`, [int](https://www.php.net/manual/en/language.types.integer.php) `$decrby` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[del](https://www.php.net/manual/en/swoole-table.del.php)([string](https://www.php.net/manual/en/language.types.string.php) `$key`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[destroy](https://www.php.net/manual/en/swoole-table.destroy.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[exist](https://www.php.net/manual/en/swoole-table.exist.php)([string](https://www.php.net/manual/en/language.types.string.php) `$key`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[get](https://www.php.net/manual/en/swoole-table.get.php)([string](https://www.php.net/manual/en/language.types.string.php) `$key`, [string](https://www.php.net/manual/en/language.types.string.php) `$field` = ?): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[incr](https://www.php.net/manual/en/swoole-table.incr.php)([string](https://www.php.net/manual/en/language.types.string.php) `$key`, [string](https://www.php.net/manual/en/language.types.string.php) `$column`, [int](https://www.php.net/manual/en/language.types.integer.php) `$incrby` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[key](https://www.php.net/manual/en/swoole-table.key.php)(): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[next](https://www.php.net/manual/en/swoole-table.next.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[rewind](https://www.php.net/manual/en/swoole-table.rewind.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[set](https://www.php.net/manual/en/swoole-table.set.php)([string](https://www.php.net/manual/en/language.types.string.php) `$key`, [array](https://www.php.net/manual/en/language.types.array.php) `$value`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[valid](https://www.php.net/manual/en/swoole-table.valid.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

}

## Predefined Constants [¶](https://www.php.net/manual/en/class.swoole-table.php\#swoole-table.constants)

**`[Swoole\\Table::TYPE\_INT](https://www.php.net/manual/en/class.swoole-table.php#swoole-table.constants.type-int)`**

**`[Swoole\\Table::TYPE\_STRING](https://www.php.net/manual/en/class.swoole-table.php#swoole-table.constants.type-string)`**

**`[Swoole\\Table::TYPE\_FLOAT](https://www.php.net/manual/en/class.swoole-table.php#swoole-table.constants.type-float)`**

## Table of Contents [¶](https://www.php.net/manual/en/class.swoole-table.php\#class.swoole-table)

- [Swoole\\Table::column](https://www.php.net/manual/en/swoole-table.column.php) — Set the data type and size of the columns.
- [Swoole\\Table::\_\_construct](https://www.php.net/manual/en/swoole-table.construct.php) — Construct a Swoole memory table with fixed size.
- [Swoole\\Table::count](https://www.php.net/manual/en/swoole-table.count.php) — Count the rows in the table, or count all the elements in the table if $mode = 1.
- [Swoole\\Table::create](https://www.php.net/manual/en/swoole-table.create.php) — Create the swoole memory table.
- [Swoole\\Table::current](https://www.php.net/manual/en/swoole-table.current.php) — Get the current row.
- [Swoole\\Table::decr](https://www.php.net/manual/en/swoole-table.decr.php) — Decrement the value in the Swoole table by $key and $column
- [Swoole\\Table::del](https://www.php.net/manual/en/swoole-table.del.php) — Delete a row in the Swoole table by $key
- [Swoole\\Table::destroy](https://www.php.net/manual/en/swoole-table.destroy.php) — Destroy the Swoole table.
- [Swoole\\Table::exist](https://www.php.net/manual/en/swoole-table.exist.php) — Check if a row is existed by $row\_key.
- [Swoole\\Table::get](https://www.php.net/manual/en/swoole-table.get.php) — Get the value in the Swoole table by $key and $field.
- [Swoole\\Table::incr](https://www.php.net/manual/en/swoole-table.incr.php) — Increment the value by $key and $column
- [Swoole\\Table::key](https://www.php.net/manual/en/swoole-table.key.php) — Get the key of current row.
- [Swoole\\Table::next](https://www.php.net/manual/en/swoole-table.next.php) — Iterator the next row
- [Swoole\\Table::rewind](https://www.php.net/manual/en/swoole-table.rewind.php) — Rewind the iterator.
- [Swoole\\Table::set](https://www.php.net/manual/en/swoole-table.set.php) — Update a row of the table by $key.
- [Swoole\\Table::valid](https://www.php.net/manual/en/swoole-table.valid.php) — Check if the current row is valid.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.table.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-table%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-table&repo=en&redirect=https://www.php.net/manual/en/class.swoole-table.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google