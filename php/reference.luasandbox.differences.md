---
url: https://www.php.net/manual/en/reference.luasandbox.differences.php
scraped_at: 2025-10-20T02:35:28.249Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Differences from Standard Lua [¶](https://www.php.net/manual/en/reference.luasandbox.differences.php\#reference.luasandbox.differences)

LuaSandbox provides a sandboxed environment which differs in some ways from standard Lua 5.1.


### Features that are not available [¶](https://www.php.net/manual/en/reference.luasandbox.differences.php\#reference.luasandbox.differences.unavailable)

- `dofile()`, `loadfile()`, and the `io` package, as they allow direct filesystem access. If needed, filesystem access should be done via PHP callbacks.


- The `package` package, including `require()` and `module()`, as it depends heavily on direct filesystem access. A pure-Lua rewrite such as that used in the MediaWiki Scribunto extension may be used instead.


- `load()` and `loadstring()`, to allow for static analysis of Lua code.


- `print()`, since it outputs to standard output. If needed, output should be done via PHP callbacks.


- Most of the `os` package, as it allows manipulation of the process and executing of other processes.





  - `os.clock()`, `os.date()`, `os.difftime()`, and `os.time()` remain available.



- Most of the `debug` package, as it allows manipulation of Lua state and metadata in ways that can break sandboxing.





  - `debug.traceback()` remains available.



- `string.dump()`, as it may expose internal data.


- `collectgarbage()`, `gcinfo()`, and the `coroutine` package have not been reviewed for security.



### Features that have been modified [¶](https://www.php.net/manual/en/reference.luasandbox.differences.php\#reference.luasandbox.differences.modified)

- `pcall()` and `xpcall()` cannot catch certain errors, particularly timeout errors.


- `tostring()` does not include pointer addresses.


- `string.match()` has been patched to limit the recursion depth and to periodically check for a timeout.


- `math.random()` and `math.randomseed()` are replaced with versions that don't share state with PHP's `rand()`.


- The Lua 5.2 `__pairs` and `__ipairs` metamethods are supported by `pairs()` and `ipairs()`.



### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/luasandbox/differences.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Freference.luasandbox.differences%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=reference.luasandbox.differences&repo=en&redirect=https://www.php.net/manual/en/reference.luasandbox.differences.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google