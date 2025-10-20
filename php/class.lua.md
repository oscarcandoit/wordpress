---
url: https://www.php.net/manual/en/class.lua.php
scraped_at: 2025-10-20T02:39:40.666Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Lua class [¶](https://www.php.net/manual/en/class.lua.php\#class.lua)

(PECL lua >=0.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.lua.php\#lua.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.lua.php\#lua.synopsis)

class **Lua**
{

/\\* Constants \*/

const[string](https://www.php.net/manual/en/language.types.string.php)[LUA\_VERSION](https://www.php.net/manual/en/class.lua.php#lua.constants.lua-version) = Lua 5.1.4;

/\\* Methods \*/

public[assign](https://www.php.net/manual/en/lua.assign.php)([string](https://www.php.net/manual/en/language.types.string.php) `$name`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[call](https://www.php.net/manual/en/lua.call.php)([callable](https://www.php.net/manual/en/language.types.callable.php) `$lua_func`, [array](https://www.php.net/manual/en/language.types.array.php) `$args` = ?, [int](https://www.php.net/manual/en/language.types.integer.php) `$use_self` = 0): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[\_\_call](https://www.php.net/manual/en/lua.call.php)([callable](https://www.php.net/manual/en/language.types.callable.php) `$lua_func`, [array](https://www.php.net/manual/en/language.types.array.php) `$args` = ?, [int](https://www.php.net/manual/en/language.types.integer.php) `$use_self` = 0): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[\_\_construct](https://www.php.net/manual/en/lua.construct.php)([string](https://www.php.net/manual/en/language.types.string.php) `$lua_script_file` = NULL)

public[eval](https://www.php.net/manual/en/lua.eval.php)([string](https://www.php.net/manual/en/language.types.string.php) `$statements`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[getVersion](https://www.php.net/manual/en/lua.getversion.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[include](https://www.php.net/manual/en/lua.include.php)([string](https://www.php.net/manual/en/language.types.string.php) `$file`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[registerCallback](https://www.php.net/manual/en/lua.registercallback.php)([string](https://www.php.net/manual/en/language.types.string.php) `$name`, [callable](https://www.php.net/manual/en/language.types.callable.php) `$function`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

}

## Predefined Constants [¶](https://www.php.net/manual/en/class.lua.php\#lua.constants)

**`[Lua::LUA\_VERSION](https://www.php.net/manual/en/class.lua.php#lua.constants.lua-version)`**

## Table of Contents [¶](https://www.php.net/manual/en/class.lua.php\#class.lua)

- [Lua::assign](https://www.php.net/manual/en/lua.assign.php) — Assign a PHP variable to Lua
- [Lua::call](https://www.php.net/manual/en/lua.call.php) — Call Lua functions
- [Lua::\_\_construct](https://www.php.net/manual/en/lua.construct.php) — Lua constructor
- [Lua::eval](https://www.php.net/manual/en/lua.eval.php) — Evaluate a string as Lua code
- [Lua::getVersion](https://www.php.net/manual/en/lua.getversion.php) — The getversion purpose
- [Lua::include](https://www.php.net/manual/en/lua.include.php) — Parse a Lua script file
- [Lua::registerCallback](https://www.php.net/manual/en/lua.registercallback.php) — Register a PHP function to Lua

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/lua/lua.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.lua%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.lua&repo=en&redirect=https://www.php.net/manual/en/class.lua.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google