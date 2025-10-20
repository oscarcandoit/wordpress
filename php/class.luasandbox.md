---
url: https://www.php.net/manual/en/class.luasandbox.php
scraped_at: 2025-10-20T02:32:21.781Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The LuaSandbox class [¶](https://www.php.net/manual/en/class.luasandbox.php\#class.luasandbox)

(PECL luasandbox >= 1.0.0)

## Introduction [¶](https://www.php.net/manual/en/class.luasandbox.php\#luasandbox.intro)

The LuaSandbox class creates a Lua environment and allows for execution of
Lua code.


## Class synopsis [¶](https://www.php.net/manual/en/class.luasandbox.php\#luasandbox.synopsis)

class **LuaSandbox**
{

/\\* Constants \*/

const[int](https://www.php.net/manual/en/language.types.integer.php)[SAMPLES](https://www.php.net/manual/en/class.luasandbox.php#luasandbox.constants.samples) = 0;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SECONDS](https://www.php.net/manual/en/class.luasandbox.php#luasandbox.constants.seconds) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[PERCENT](https://www.php.net/manual/en/class.luasandbox.php#luasandbox.constants.percent) = 2;

/\\* Methods \*/

public[callFunction](https://www.php.net/manual/en/luasandbox.callfunction.php)([string](https://www.php.net/manual/en/language.types.string.php) `$name`, [mixed](https://www.php.net/manual/en/language.types.mixed.php) `...$args`): [array](https://www.php.net/manual/en/language.types.array.php)\|[bool](https://www.php.net/manual/en/language.types.boolean.php)

public[disableProfiler](https://www.php.net/manual/en/luasandbox.disableprofiler.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[enableProfiler](https://www.php.net/manual/en/luasandbox.enableprofiler.php)([float](https://www.php.net/manual/en/language.types.float.php) `$period` = 0.02): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getCPUUsage](https://www.php.net/manual/en/luasandbox.getcpuusage.php)(): [float](https://www.php.net/manual/en/language.types.float.php)

public[getMemoryUsage](https://www.php.net/manual/en/luasandbox.getmemoryusage.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getPeakMemoryUsage](https://www.php.net/manual/en/luasandbox.getpeakmemoryusage.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getProfilerFunctionReport](https://www.php.net/manual/en/luasandbox.getprofilerfunctionreport.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$units` = LuaSandbox::SECONDS): [array](https://www.php.net/manual/en/language.types.array.php)

publicstatic[getVersionInfo](https://www.php.net/manual/en/luasandbox.getversioninfo.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[loadBinary](https://www.php.net/manual/en/luasandbox.loadbinary.php)([string](https://www.php.net/manual/en/language.types.string.php) `$code`, [string](https://www.php.net/manual/en/language.types.string.php) `$chunkName` = ''): [LuaSandboxFunction](https://www.php.net/manual/en/class.luasandboxfunction.php)

public[loadString](https://www.php.net/manual/en/luasandbox.loadstring.php)([string](https://www.php.net/manual/en/language.types.string.php) `$code`, [string](https://www.php.net/manual/en/language.types.string.php) `$chunkName` = ''): [LuaSandboxFunction](https://www.php.net/manual/en/class.luasandboxfunction.php)

public[pauseUsageTimer](https://www.php.net/manual/en/luasandbox.pauseusagetimer.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[registerLibrary](https://www.php.net/manual/en/luasandbox.registerlibrary.php)([string](https://www.php.net/manual/en/language.types.string.php) `$libname`, [array](https://www.php.net/manual/en/language.types.array.php) `$functions`): [void](https://www.php.net/manual/en/language.types.void.php)

public[setCPULimit](https://www.php.net/manual/en/luasandbox.setcpulimit.php)([float](https://www.php.net/manual/en/language.types.float.php)\|[bool](https://www.php.net/manual/en/language.types.boolean.php) `$limit`): [void](https://www.php.net/manual/en/language.types.void.php)

public[setMemoryLimit](https://www.php.net/manual/en/luasandbox.setmemorylimit.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$limit`): [void](https://www.php.net/manual/en/language.types.void.php)

public[unpauseUsageTimer](https://www.php.net/manual/en/luasandbox.unpauseusagetimer.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[wrapPhpFunction](https://www.php.net/manual/en/luasandbox.wrapphpfunction.php)([callable](https://www.php.net/manual/en/language.types.callable.php) `$function`): [LuaSandboxFunction](https://www.php.net/manual/en/class.luasandboxfunction.php)

}

## Predefined Constants [¶](https://www.php.net/manual/en/class.luasandbox.php\#luasandbox.constants)

**`[LuaSandbox::SAMPLES](https://www.php.net/manual/en/class.luasandbox.php#luasandbox.constants.samples)`**

Used with [LuaSandbox::getProfilerFunctionReport()](https://www.php.net/manual/en/luasandbox.getprofilerfunctionreport.php) to return timings in samples.


**`[LuaSandbox::SECONDS](https://www.php.net/manual/en/class.luasandbox.php#luasandbox.constants.seconds)`**

Used with [LuaSandbox::getProfilerFunctionReport()](https://www.php.net/manual/en/luasandbox.getprofilerfunctionreport.php) to return timings in seconds.


**`[LuaSandbox::PERCENT](https://www.php.net/manual/en/class.luasandbox.php#luasandbox.constants.percent)`**

Used with [LuaSandbox::getProfilerFunctionReport()](https://www.php.net/manual/en/luasandbox.getprofilerfunctionreport.php) to return timings in percentages of the total.


## Table of Contents [¶](https://www.php.net/manual/en/class.luasandbox.php\#class.luasandbox)

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

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/luasandbox/luasandbox.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.luasandbox%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.luasandbox&repo=en&redirect=https://www.php.net/manual/en/class.luasandbox.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google