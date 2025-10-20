---
url: https://www.php.net/manual/en/book.luasandbox.php
scraped_at: 2025-10-20T02:41:22.664Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# LuaSandbox [¶](https://www.php.net/manual/en/book.luasandbox.php\#book.luasandbox)

- [Introduction](https://www.php.net/manual/en/intro.luasandbox.php)
- [Installing/Configuring](https://www.php.net/manual/en/luasandbox.setup.php)
  - [Requirements](https://www.php.net/manual/en/luasandbox.requirements.php)
  - [Installation](https://www.php.net/manual/en/luasandbox.installation.php)
- [Differences from Standard Lua](https://www.php.net/manual/en/reference.luasandbox.differences.php)
- [Examples](https://www.php.net/manual/en/luasandbox.examples.php)
  - [Basic usage for LuaSandbox](https://www.php.net/manual/en/luasandbox.examples-basic.php)
- [LuaSandbox](https://www.php.net/manual/en/class.luasandbox.php) — The LuaSandbox class
  - [LuaSandbox::callFunction](https://www.php.net/manual/en/luasandbox.callfunction.php) — Call a function in a Lua global variable
  - [LuaSandbox::disableProfiler](https://www.php.net/manual/en/luasandbox.disableprofiler.php) — Disable the profiler
  - [LuaSandbox::enableProfiler](https://www.php.net/manual/en/luasandbox.enableprofiler.php) — Enable the profiler.
  - [LuaSandbox::getCPUUsage](https://www.php.net/manual/en/luasandbox.getcpuusage.php) — Fetch the current CPU time usage of the Lua environment
  - [LuaSandbox::getMemoryUsage](https://www.php.net/manual/en/luasandbox.getmemoryusage.php) — Fetch the current memory usage of the Lua environment
  - [LuaSandbox::getPeakMemoryUsage](https://www.php.net/manual/en/luasandbox.getpeakmemoryusage.php) — Fetch the peak memory usage of the Lua environment
  - [LuaSandbox::getProfilerFunctionReport](https://www.php.net/manual/en/luasandbox.getprofilerfunctionreport.php) — Fetch profiler data
  - [LuaSandbox::getVersionInfo](https://www.php.net/manual/en/luasandbox.getversioninfo.php) — Return the versions of LuaSandbox and Lua
  - [LuaSandbox::loadBinary](https://www.php.net/manual/en/luasandbox.loadbinary.php) — Load a precompiled binary chunk into the Lua environment
  - [LuaSandbox::loadString](https://www.php.net/manual/en/luasandbox.loadstring.php) — Load Lua code into the Lua environment
  - [LuaSandbox::pauseUsageTimer](https://www.php.net/manual/en/luasandbox.pauseusagetimer.php) — Pause the CPU usage timer
  - [LuaSandbox::registerLibrary](https://www.php.net/manual/en/luasandbox.registerlibrary.php) — Register a set of PHP functions as a Lua library
  - [LuaSandbox::setCPULimit](https://www.php.net/manual/en/luasandbox.setcpulimit.php) — Set the CPU time limit for the Lua environment
  - [LuaSandbox::setMemoryLimit](https://www.php.net/manual/en/luasandbox.setmemorylimit.php) — Set the memory limit for the Lua environment
  - [LuaSandbox::unpauseUsageTimer](https://www.php.net/manual/en/luasandbox.unpauseusagetimer.php) — Unpause the timer paused by LuaSandbox::pauseUsageTimer
  - [LuaSandbox::wrapPhpFunction](https://www.php.net/manual/en/luasandbox.wrapphpfunction.php) — Wrap a PHP callable in a LuaSandboxFunction
- [LuaSandboxFunction](https://www.php.net/manual/en/class.luasandboxfunction.php) — The LuaSandboxFunction class
  - [LuaSandboxFunction::call](https://www.php.net/manual/en/luasandboxfunction.call.php) — Call a Lua function
  - [LuaSandboxFunction::\_\_construct](https://www.php.net/manual/en/luasandboxfunction.construct.php) — Unused
  - [LuaSandboxFunction::dump](https://www.php.net/manual/en/luasandboxfunction.dump.php) — Dump the function as a binary blob
- [LuaSandboxError](https://www.php.net/manual/en/class.luasandboxerror.php) — The LuaSandboxError class
- [LuaSandboxErrorError](https://www.php.net/manual/en/class.luasandboxerrorerror.php) — The LuaSandboxErrorError class
- [LuaSandboxFatalError](https://www.php.net/manual/en/class.luasandboxfatalerror.php) — The LuaSandboxFatalError class
- [LuaSandboxMemoryError](https://www.php.net/manual/en/class.luasandboxmemoryerror.php) — The LuaSandboxMemoryError class
- [LuaSandboxRuntimeError](https://www.php.net/manual/en/class.luasandboxruntimeerror.php) — The LuaSandboxRuntimeError class
- [LuaSandboxSyntaxError](https://www.php.net/manual/en/class.luasandboxsyntaxerror.php) — The LuaSandboxSyntaxError class
- [LuaSandboxTimeoutError](https://www.php.net/manual/en/class.luasandboxtimeouterror.php) — The LuaSandboxTimeoutError class

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/luasandbox/book.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fbook.luasandbox%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=book.luasandbox&repo=en&redirect=https://www.php.net/manual/en/book.luasandbox.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google